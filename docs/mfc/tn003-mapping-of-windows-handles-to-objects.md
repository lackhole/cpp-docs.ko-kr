---
title: 'TN003: Windows 핸들을 개체로 매핑'
ms.date: 11/04/2016
f1_keywords:
- vc.mapping
helpviewer_keywords:
- TN003
- handle maps
- Windows handles to objects [MFC]
- mappings [MFC], Windows handles to objects
ms.assetid: fbea9f38-992c-4091-8dbc-f29e288617d6
ms.openlocfilehash: 45492963e1b686e03eb59c320fdc3d52d1534f7d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69513531"
---
# <a name="tn003-mapping-of-windows-handles-to-objects"></a>TN003: Windows 핸들을 개체로 매핑

이 참고는 개체에 대 한 C++ Windows 개체 핸들 매핑을 지 원하는 MFC 루틴에 대해 설명 합니다.

## <a name="the-problem"></a>문제

Windows 개체는 일반적으로 다양 한 [핸들](/windows/win32/WinProg/windows-data-types) 개체로 표시 되며, MFC 클래스는 개체를 C++ 사용 하 여 windows 개체 핸들을 래핑합니다. MFC 클래스 라이브러리의 핸들 래핑 함수를 사용 하면 특정 핸들이 포함 C++ 된 Windows 개체를 래핑하는 개체를 찾을 수 있습니다. 그러나 개체에 C++ 래퍼 개체가 없고 이러한 시간에 시스템이 C++ 래퍼 역할을 하는 임시 개체를 만드는 경우가 있습니다.

핸들 맵을 사용 하는 Windows 개체는 다음과 같습니다.

- HWND ([CWnd](../mfc/reference/cwnd-class.md) 및 `CWnd`파생 클래스)

- HDC ([CDC](../mfc/reference/cdc-class.md) 및 `CDC`파생 클래스)

- HMENU ([CMenu](../mfc/reference/cmenu-class.md))

- HPEN ([CGdiObject](../mfc/reference/cgdiobject-class.md))

- HBRUSH (`CGdiObject`)

- HFONT (`CGdiObject`)

- HBITMAP (`CGdiObject`)

- HPALETTE (`CGdiObject`)

- HRGN (`CGdiObject`)

- HIMAGELIST ([CImageList](../mfc/reference/cimagelist-class.md))

- 소켓 ([CSocket](../mfc/reference/csocket-class.md))

이러한 개체 중 하나에 대 한 핸들을 지정 하면 정적 메서드 `FromHandle`를 호출 하 여 핸들을 래핑하는 MFC 개체를 찾을 수 있습니다. 예를 들어 hwnd 라는 hwnd가제공 되는 경우 다음 줄은 *hwnd*를 래핑하는 `CWnd` 에 대 한 포인터를 반환 합니다.

```
CWnd::FromHandle(hWnd)
```

*Hwnd* 에 특정 래퍼 개체가 없으면 `CWnd` *hwnd*를 래핑하는 임시가 만들어집니다. 그러면 모든 핸들에서 유효한 C++ 개체를 가져올 수 있습니다.

래퍼 개체를 만든 후에는 래퍼 클래스의 public 멤버 변수에서 해당 핸들을 검색할 수 있습니다. 의 `CWnd`경우 *m_hWnd* 는 해당 개체에 대 한 hWnd를 포함 합니다.

## <a name="attaching-handles-to-mfc-objects"></a>MFC 개체에 핸들 연결

새로 만든 핸들-래퍼 개체와 Windows 개체에 대 한 핸들을 지정 하는 경우이 예제에서와 같이 함수 `Attach` 를 호출 하 여 두 개체를 연결할 수 있습니다.

```
CWnd myWnd;
myWnd.Attach(hWnd);
```

이렇게 하면 *myWnd* 및 *hWnd*를 연결 하는 영구 맵에 항목이 적용 됩니다. 이제 `CWnd::FromHandle(hWnd)` 를 호출 하면 *myWnd*에 대 한 포인터가 반환 됩니다. *MyWnd* 가 삭제 되 면 소멸자는 Windows [DestroyWindow](/windows/win32/api/winuser/nf-winuser-destroywindow) 함수를 호출 하 여 *hWnd* 를 자동으로 삭제 합니다. 이 작업이 필요 하지 않은 경우 *myWnd* 가 제거 되기 전에 *myWnd* 에서 *hWnd* 를 분리 해야 합니다 (일반적으로 *myWnd* 가 정의 된 범위를 벗어날 때). 메서드 `Detach` 는이를 수행 합니다.

```
myWnd.Detach();
```

## <a name="more-about-temporary-objects"></a>임시 개체에 대 한 자세한 정보

에 이미 래퍼 개체가 없는 `FromHandle` 핸들이 제공 될 때마다 임시 개체가 만들어집니다. 이러한 임시 개체는 핸들에서 분리 되 고 함수에 `DeleteTempMap` 의해 삭제 됩니다. 기본적으로 [CWinThread:: OnIdle](../mfc/reference/cwinthread-class.md#onidle) 은 임시 `DeleteTempMap` 핸들 맵을 지 원하는 각 클래스에 대해를 자동으로 호출 합니다. 즉, 포인터를 가져온 함수에서 종료 지점을 지난 후에 임시 개체에 대 한 포인터를 사용할 수 있습니다.

## <a name="wrapper-objects-and-multiple-threads"></a>래퍼 개체 및 다중 스레드

임시 및 영구 개체는 모두 스레드별 방식으로 유지 관리 됩니다. 즉, 임시 인지 영구적인 지에 관계 없이 한 C++ 스레드가 다른 스레드의 래퍼 개체에 액세스할 수 없습니다.

이러한 개체를 한 스레드에서 다른 스레드로 전달 하려면 항상 네이티브 `HANDLE` 형식으로 보냅니다. 한 스레드에서 C++ 다른 스레드로 래퍼 개체를 전달 하면 예기치 않은 결과가 발생 하는 경우가 많습니다.

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
