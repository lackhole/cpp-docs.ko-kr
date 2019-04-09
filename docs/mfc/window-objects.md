---
title: 창 개체
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], window
- Windows window [MFC]
- MFC, windows
- frame windows [MFC], C++ window objects
- window objects [MFC]
- windows [MFC], C++ window objects
- window messages [MFC]
- HWND
- messages [MFC], Windows
- Visual C++, window objects [MFC]
- HWND, window objects [MFC]
ms.assetid: 28b33ce2-af05-4617-9d03-1cb9a02be687
ms.openlocfilehash: b62f43aa0d37c5e614636b3d7543bc927d41039b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57299870"
---
# <a name="window-objects"></a>창 개체

MFC 클래스를 제공 [CWnd](../mfc/reference/cwnd-class.md) 캡슐화 하는 `HWND` 는 창의 핸들입니다. `CWnd` 개체는 Windows 창을 나타내는 `HWND`와 다른 C++ 창 개체이지만 이를 포함합니다. `CWnd`를 사용하여 고유한 자식 창 클래스를 파생시키거나 `CWnd`에서 파생된 여러 MFC 클래스 중 하나를 사용합니다. `CWnd` 클래스는 프레임 창, 대화 상자, 자식 창, 컨트롤 및 컨트롤 막대(예: 도구 모음)를 포함하는 모든 창에 대한 기본 클래스입니다. 이해가 [c + + 창 개체와 HWND 간 관계](../mfc/relationship-between-a-cpp-window-object-and-an-hwnd.md) MFC 통한 효율적인 프로그래밍에 대 한 중요 합니다.

MFC에서는 몇 가지 기본 기능 및 창 관리를 제공하지만 `CWnd`에서 고유한 클래스를 파생시킬 수 있고 해당 멤버 함수를 사용하여 제공된 기능을 사용자 지정할 수 있습니다. 자식 창을 만들거나 구성 하 여는 `CWnd` 개체와 호출 해당 [Create](../mfc/reference/cwnd-class.md#create) 멤버 함수를 사용 하 여 자식 창을 사용자 지정할 `CWnd` 멤버 함수입니다. 파생 된 개체를 포함할 수 있습니다 [CView](../mfc/reference/cview-class.md)예: 폼 뷰 또는 프레임 창에서 트리 보기입니다. 클래스에서 제공 하는 분할자 창을 통해 문서의 여러 뷰를 지원할 수 있습니다 [CSplitterWnd](../mfc/reference/csplitterwnd-class.md)합니다.

`CWnd` 클래스에서 파생된 각 개체에는 Windows 메시지 또는 명령 ID를 고유한 처리기에 매핑할 수 있는 메시지 맵이 포함됩니다.

Windows 프로그래밍에 대한 일반 문서는 `CWnd` API를 캡슐화하는 `HWND` 멤버 함수를 사용하는 방법을 학습하기 위한 좋은 리소스입니다.

## <a name="functions-for-operating-on-a-cwnd"></a>CWnd에서 작동하는 함수

`CWnd` 및 해당 [파생 된 창 클래스](../mfc/derived-window-classes.md) 생성자, 소멸자 및 개체를 초기화 하는 멤버 함수 내부 Windows 구조를 만들고 캡슐화 된 액세스 제공 `HWND`합니다. `CWnd`는 메시지 전송, 창 상태에 액세스, 좌표 변환, 업데이트, 스크롤, 클립보드에 액세스 및 기타 여러 작업을 위해 Windows API를 캡슐화하는 멤버 함수도 제공합니다. `HWND` 인수를 사용하는 대부분의 Windows 창 관리 API는 `CWnd` 멤버 함수로 캡슐화됩니다. 함수와 매개 변수 이름은 `CWnd` 멤버 함수에서 유지됩니다. Windows Api를 캡슐화 하는 방법에 대 한 자세한 `CWnd`, 클래스를 참조 하세요 [CWnd](../mfc/reference/cwnd-class.md)합니다.

## <a name="cwnd-and-windows-messages"></a>CWnd 및 Windows 메시지

주요 목적 중 `CWnd` WM_PAINT 또는 WM_MOUSEMOVE 같은 Windows 메시지를 처리 하기 위한 인터페이스를 제공 하는 것입니다. 멤버 함수는 많은 `CWnd` 표준 메시지에 대 한 처리기-식별자를 사용 하 여 시작 하 **afx_msg** 와 접두사 "On"와 같은 `OnPaint` 고 `OnMouseMove`입니다. [메시지 처리 및 매핑](../mfc/message-handling-and-mapping.md) 메시지 및 메시지 처리에서 자세히 다룹니다. 프레임워크의 창과 특수 목적을 위해 사용자가 직접 만든 창에 정보가 동일하게 적용됩니다.

### <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [C + + 창 개체와 HWND 간 관계](../mfc/relationship-between-a-cpp-window-object-and-an-hwnd.md)

- [파생 된 창 클래스](../mfc/derived-window-classes.md)

- [창 만들기](../mfc/creating-windows.md)

- [창 개체 제거](../mfc/destroying-window-objects.md)

- [CWnd를 해당 HWND에서 분리](../mfc/detaching-a-cwnd-from-its-hwnd.md)

- [창 개체 작업](../mfc/working-with-window-objects.md)

- [장치 컨텍스트](../mfc/device-contexts.md): Windows 그리기 장치 독립화 개체

- [그래픽 개체](../mfc/graphic-objects.md): 펜, 브러시, 글꼴, 비트맵, 색상표, 영역

## <a name="see-also"></a>참고자료

[Windows](../mfc/windows.md)
