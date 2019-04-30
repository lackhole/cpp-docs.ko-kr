---
title: 'TN003: 핸들을 개체로 매핑 Windows의'
ms.date: 11/04/2016
f1_keywords:
- vc.mapping
helpviewer_keywords:
- TN003
- handle maps
- Windows handles to objects [MFC]
- mappings [MFC], Windows handles to objects
ms.assetid: fbea9f38-992c-4091-8dbc-f29e288617d6
ms.openlocfilehash: e7844398ebaf5a8fdf8c56ab18b33d8c7717d1ad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62306381"
---
# <a name="tn003-mapping-of-windows-handles-to-objects"></a>TN003: 핸들을 개체로 매핑 Windows의

이 MFC를 설명 합니다. Windows 매핑 지 루틴 개체 핸들을 C++ 개체입니다.

## <a name="the-problem"></a>문제

Windows는 일반적으로 나타내는 개체가 여러 [처리할](/windows/desktop/WinProg/windows-data-types) The MFC 클래스 개체에는 Windows 개체 핸들을 래핑할 C++ 개체입니다. MFC 클래스 라이브러리의 함수를 래핑하는 핸들을 통해 찾을 수는 C++ Windows 가진 개체를 특정 핸들을 래핑하는 개체입니다. 그러나 경우에 따라 개체 없는 C++ 래퍼 개체 하 고 해당이 시간에 시스템 역할을 하도록 임시 개체를 만듭니다는 C++ 래퍼.

핸들 맵을 사용 하는 Windows 개체는 다음과 같습니다.

- HWND ([CWnd](../mfc/reference/cwnd-class.md) 고 `CWnd`-파생 클래스)

- HDC ([CDC](../mfc/reference/cdc-class.md) 고 `CDC`-파생 클래스)

- HMENU ([CMenu](../mfc/reference/cmenu-class.md))

- HPEN ([CGdiObject](../mfc/reference/cgdiobject-class.md))

- HBRUSH (`CGdiObject`)

- HFONT (`CGdiObject`)

- HBITMAP (`CGdiObject`)

- HPALETTE (`CGdiObject`)

- HRGN (`CGdiObject`)

- HIMAGELIST ([CImageList](../mfc/reference/cimagelist-class.md))

- 소켓 ([CSocket](../mfc/reference/csocket-class.md))

이러한 개체 중 하나에 대 한 핸들을 지정 된 정적 메서드를 호출 하 여 핸들을 래핑하는 MFC 개체를 찾을 수 `FromHandle`입니다. 예를 들어, HWND 라는 지정 된 *hWnd*, 다음 줄에 대 한 포인터를 반환 합니다 합니다 `CWnd` 래핑하 *hWnd*:

```
CWnd::FromHandle(hWnd)
```

하는 경우 *hWnd* 임시 개체를 특정 래퍼 없습니다 `CWnd` 래핑할 만들어집니다 *hWnd*합니다. 이렇게 하면 올바른 가져올 수 C++ 모든 핸들에서 개체입니다.

래퍼 개체를 만든 후에 래퍼 클래스의 public 멤버 변수에서 해당 핸들을 검색할 수 있습니다. 경우는 `CWnd`하십시오 *m_hWnd* 해당 개체에 대 한 HWND를 포함 합니다.

## <a name="attaching-handles-to-mfc-objects"></a>MFC 개체를 핸들에 연결

Windows 개체에 대 한 핸들 및 새로 만든된 핸들 래퍼 개체를 들어 두 호출 하 여 연결할 수 있습니다는 `Attach` 이 예제와 같이 작동 합니다.

```
CWnd myWnd;
myWnd.Attach(hWnd);
```

이렇게 하면 항목의 영구 맵에 연결 *myWnd* 하 고 *hWnd*합니다. 호출 `CWnd::FromHandle(hWnd)` 반환에 대 한 포인터 *myWnd*합니다. 때 *myWnd* 는 삭제 소멸자가 자동으로 파괴 *hWnd* 는 Windows를 호출 하 여 [DestroyWindow](/windows/desktop/api/winuser/nf-winuser-destroywindow) 함수입니다. 이 원하지 않는 경우 *hWnd* 에서 분리 해야 *myWnd* 하기 전에 *myWnd* 소멸 됩니다 (범위를 종료 하는 경우에 일반적으로 *myWnd*정의한). `Detach` 메서드가이 수행 합니다.

```
myWnd.Detach();
```

## <a name="more-about-temporary-objects"></a>임시 개체에 대 한 자세한 정보

임시 개체가 만들어지는 때마다 `FromHandle` 래퍼 개체를 이미 있지 않은 핸들을 지정 합니다. 이러한 임시 개체는 핸들에서 분리 되며가 삭제 된 `DeleteTempMap` 함수입니다. 기본적으로 [CWinThread::OnIdle](../mfc/reference/cwinthread-class.md#onidle) 자동으로 호출 `DeleteTempMap` 임시 핸들 맵을 지 원하는 각 클래스에 대 한 합니다. 즉, 임시 개체에 대 한 포인터를 유효 하 게 함수 종료 지점 지난 포인터를 가져온 위치 가정할 수 없습니다.

## <a name="wrapper-objects-and-multiple-threads"></a>래퍼 개체 및 여러 스레드

임시 및 영구 개체는 스레드별 기준 유지 됩니다. 즉, 하나의 스레드가 다른 스레드의 액세스할 수 없습니다 C++ 임시 또는 영구 인지에 관계 없이 래퍼 개체입니다.

이러한 개체 한 스레드에서 다른을 전달 하려면 항상 보내야 기본 `HANDLE` 형식입니다. 전달 된 C++ 래퍼 개체를 다른 스레드에서는 예기치 않은 결과가 발생할 경우가 많습니다.

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
