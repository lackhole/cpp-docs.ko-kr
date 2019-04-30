---
title: 'TN017: 창 개체 소멸시키기'
ms.date: 11/04/2016
f1_keywords:
- vc.objects
helpviewer_keywords:
- destroying windows
- TN017
- PostNcDestroy method [MFC]
ms.assetid: 5bf208a5-5683-439b-92a1-547c5ded26cd
ms.openlocfilehash: 9e52112bed0f583a3f5652f9213bd5049d543a80
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62306157"
---
# <a name="tn017-destroying-window-objects"></a>TN017: 창 개체 소멸시키기

이 참고의 사용 방법을 설명 합니다 [CWnd::PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy) 메서드. 사용자 지정 된 할당을 수행 하려는 경우이 메서드를 사용 하 여 `CWnd`-파생 개체입니다. 이 여기서도 사용 하는 이유에 설명 [CWnd::DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow) 제거할를 C++ Windows 대신 개체를 **삭제** 연산자입니다.

이 항목의 지침을 따르는 경우에 정리 문제를 최소화 해야 합니다. 삭제/해제 하지 않으면 같은 문제에서 이러한 문제가 발생할 수 있습니다 C++ 와 같은 시스템 리소스를 해제 하지 않으면 메모리 `HWND`s, 개체를 너무 여러 번 해제 합니다.

## <a name="the-problem"></a>문제

각 windows 개체 (에서 파생 된 클래스의 개체 `CWnd`) 둘 다 나타냅니다는 C++ 개체와 `HWND`합니다. C++개체가 응용 프로그램의 힙에 할당 되 고 `HWND`의창 관리자가 시스템 리소스에 할당 됩니다. 창 개체를 제거 하는 여러 방법 이기 때문에 시스템을 방해 하는 규칙 집합을 제공 해야 리소스 또는 메모리 누수입니다. 이러한 규칙 개체 및 Windows 핸들 번 이상 소멸 되도 차단 해야 합니다.

## <a name="destroying-windows"></a>Windows를 제거합니다.

다음의 두 가지 허용 되는 Windows 개체를 삭제 하려면:

- 호출 `CWnd::DestroyWindow` 또는 Windows API `DestroyWindow`합니다.

- 사용 하 여 명시적으로 삭제 합니다 **삭제** 연산자입니다.

첫 번째 경우가 단연코 가장 일반적입니다. 이 경우 코드를 호출 하지 않습니다 하는 경우에 적용 됩니다. `DestroyWindow` 직접. 사용자는 직접 프레임 창을 닫는이 이렇게 WM_CLOSE 메시지를 생성 하 고 호출 하는 것이 메시지에 대 한 기본 응답 `DestroyWindow.` Windows를 호출 하는 부모 창을 소멸 될 때 `DestroyWindow` 모든 자식에 대 한 합니다.

두 번째 경우, 사용 된 **삭제** Windows 개체에 연산자는 거의 발생 하지 않아야 합니다. 다음은 사용 하는 경우 일부 **삭제** 올바른 선택입니다.

## <a name="auto-cleanup-with-cwndpostncdestroy"></a>CWnd::PostNcDestroy 사용 하 여 자동 정리

창에 보낸 마지막 Windows 메시지는 Windows 창을 제거 하는 시스템 때 WM_NCDESTROY 합니다. 기본값 `CWnd` 해당 메시지에 대 한 처리기가 [:: Onncdestroy](../mfc/reference/cwnd-class.md#onncdestroy)합니다. `OnNcDestroy` 분리 됩니다 합니다 `HWND` 에서 C++ 개체 및 가상 함수를 호출 `PostNcDestroy`합니다. 삭제 하려면이 함수를 재정의 하는 일부 클래스는 C++ 개체입니다.

기본 구현을 `CWnd::PostNcDestroy` 스택 프레임에 할당 되거나 다른 개체에 포함 되는 창 개체에 대 한 적절 한는 아무 것도 않습니다. 이 다른 개체 없이 힙에 할당 하도록 설계 된 창 개체에 대 한 적합 하지 않습니다. 즉, 다른 포함 되지 않은 창 개체에 대 한 적절 한 하지는 C++ 개체입니다.

힙에 단독으로 할당 되도록 설계 된 이러한 클래스를 재정의 하는 `PostNcDestroy` 수행 하는 방법을 **삭제**합니다. 본이 방침에 연결 된 모든 메모리를 해제 합니다는 C++ 개체입니다. 경우에 기본값 `CWnd` 소멸자 호출 `DestroyWindow` 하는 경우 *m_hWnd* 는 NULL이 아닌 경우이으로 이어지지 무한 재귀 이기 때문에 핸들을 분리 하 고 NULL 정리 단계 중입니다.

> [!NOTE]
>  시스템에서 일반적으로 호출할 `CWnd::PostNcDestroy` WM_NCDESTROY Windows 메시지를 처리 한 후 및 `HWND` 및 C++ 창 개체에 연결 되어 있지 않습니다. 시스템은 또한 호출 `CWnd::PostNcDestroy` 구현의 대부분 [CWnd::Create](../mfc/reference/cwnd-class.md#create) 오류가 발생 하는 경우 호출 합니다. 자동 정리 규칙은이 항목의 뒷부분에 설명 되어 있습니다.

## <a name="auto-cleanup-classes"></a>자동 정리 클래스

다음 클래스는 자동 정리를 위해 설계 되지 않았습니다. 일반적으로 다른 포함 되기 C++ 개체 또는 스택:

- 모든 표준 Windows 컨트롤 (`CStatic`하십시오 `CEdit`, `CListBox`등).

- 모든 자식 창에서 직접 파생 `CWnd` (예를 들어, 사용자 지정 컨트롤).

- 분할 창 (`CSplitterWnd`).

- 기본 컨트롤 막대 (클래스에서 파생 된 `CControlBar`를 참조 하세요 [Technical Note 31](../mfc/tn031-control-bars.md) 컨트롤 막대 개체 자동 삭제를 사용 하도록 설정).

- 대화 상자 (`CDialog`) 스택 프레임에 모달 대화 상자에 대 한 설계 되었습니다.

- 제외한 모든 표준 대화 상자 `CFindReplaceDialog`합니다.

- 클래스 마법사에서 만든 기본 대화 상자입니다.

다음 클래스는 자동 정리를 위해 설계 되었습니다. 이러한 오류는 일반적으로 자체적으로 힙에 할당 됩니다.

- 주 프레임 창 (에서 직접 또는 간접적으로 파생 `CFrameWnd`).

- 뷰 창 (에서 직접 또는 간접적으로 파생 `CView`).

이러한 규칙을 중단 하려는 경우 재정의 해야 합니다는 `PostNcDestroy` 파생된 클래스에서 메서드. 자동 정리에 클래스를 추가 하려면 기본 클래스를 호출 하 고 다음 실행을 **삭제**합니다. 자동 정리 클래스에서 제거할 호출 `CWnd::PostNcDestroy` of 직접는 `PostNcDestroy` 직접 기본 클래스의 메서드.

자동 정리 동작을 변경 하는 가장 일반적인 사용 힙에 할당 될 수 있는 모덜리스 대화 상자를 만드는 것입니다.

## <a name="when-to-call-delete"></a>호출 삭제 해야 하는 경우

호출 하는 것이 좋습니다 `DestroyWindow` 중 하나는 Windows 개체를 제거 하는 C++ 메서드 또는 전역 `DestroyWindow` API.

전역 호출 하지 마십시오 `DestroyWindow` MDI 자식 창을 제거 하는 API입니다. 가상 메서드를 사용 해야 `CWnd::DestroyWindow` 대신 합니다.

에 대 한 C++ 자동 정리를 수행 하지 않는 창 개체를 사용 하 여는 **삭제** 연산자를 호출 하려고 할 때 메모리 누수가 발생할 수 있습니다 `DestroyWindow` 에 `CWnd::~CWnd` 소멸자의 VTBL 올바르게 파생을 가리키지 않을 경우 클래스입니다. 적절 한 destroy 메서드를 호출 하는 시스템을 찾을 수 없어이 발생 합니다. 사용 하 여 `DestroyWindow` of **삭제** 이러한 문제를 방지 합니다. 이 일 수 있으므로 사소한 오류를 디버그 모드에서 컴파일하면 생성 됩니다 다음 경고가 위험에 노출 하려는 경우.

```
Warning: calling DestroyWindow in CWnd::~CWnd
    OnDestroy or PostNcDestroy in derived class will not be called
```

경우 C++ 를 호출 해야 자동 정리를 수행 하는 Windows 개체 `DestroyWindow`합니다. 사용 하는 경우는 **삭제** 연산자를 직접 MFC 진단 메모리 할당자 알려는 하는 메모리를 해제 두 배입니다. 2 개는 첫 번째 명시적 호출 및 간접 호출 **삭제** 자동 정리 구현의 `PostNcDestroy`합니다.

호출한 후 `DestroyWindow` 자동 정리 되지 않은 개체에는 C++ 개체, 수 있지만 *m_hWnd* NULL이 됩니다. 호출한 후 `DestroyWindow` 자동 정리 개체에는 C++ 개체 됩니다 사라지고 해제는 C++ delete 연산자의 자동 정리 구현에서 `PostNcDestroy`합니다.

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
