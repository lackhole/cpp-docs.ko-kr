---
title: 컨트롤 막대
ms.date: 11/04/2016
helpviewer_keywords:
- command bars [MFC], types of
- toolbars [MFC], control bars
- control bars [MFC]
- MFC, control bars
- control bars [MFC], types of
- CDialogBar class [MFC], control bars
- status bars [MFC], control bars
- CControlBar class [MFC], MFC control bars
- dialog bars [MFC], control bars
- CToolBar class [MFC], control bars
- CStatusBar class [MFC], control bars
ms.assetid: 31831910-3d23-4d70-9e71-03cc02f01ec4
ms.openlocfilehash: 4b75d9a96f091d0424592f34bdb1ed7ce76c2372
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152780"
---
# <a name="control-bars"></a>컨트롤 막대

"컨트롤 막대"에 도구 모음, 상태 표시줄 및 대화 상자 막대에 대 한 일반 이름입니다. MFC 클래스 `CToolBar`, `CStatusBar`를 `CDialogBar`를 `COleResizeBar`, 및 `CReBar` 클래스에서 파생 [CControlBar](../mfc/reference/ccontrolbar-class.md), 해당 일반 기능을 구현 하는 합니다.

컨트롤 막대는 사용자 수 옵션을 선택, 명령을 실행 하거나 있는 프로그램 정보를 가져올 컨트롤의 행을 표시 하는 창입니다. 컨트롤 막대 유형의 도구 모음, 대화 상자 모음 및 상태 표시줄을 포함 합니다.

- 클래스의 도구 모음 [CToolBar](../mfc/reference/ctoolbar-class.md)

- 클래스에서 상태 표시줄, [CStatusBar](../mfc/reference/cstatusbar-class.md)

- 클래스에서 대화 상자 모음 [CDialogBar](../mfc/reference/cdialogbar-class.md)

- 클래스에서 rebars [CReBar](../mfc/reference/crebar-class.md)

> [!IMPORTANT]
>  구현 되는 시스템 기능을 사용 하 여 팁의 구현 하는 MFC 버전 4.0, 도구 모음, 상태 표시줄 및 도구를 *comctl32.dll* MFC에 특정 이전 구현 대신 합니다. 버전 6.0, MFC의 `CReBar`, comctl32.dll 기능을 래핑하는 추가 되었습니다.

컨트롤 막대 형식에 대 한 간략 한 소개를 수행 합니다. 자세한 내용은 아래 링크를 참조 하세요.

## <a name="control-bars"></a>컨트롤 막대

컨트롤 막대 빠른, 1 단계 작업을 제공 하 여 프로그램의 유용성을 크게 향상 합니다. 클래스 `CControlBar` 모든 도구 모음, 상태 표시줄 및 대화 상자 막대의 공통 기능을 제공 합니다. `CControlBar` 부모 프레임 창에서 컨트롤 막대 위치를 지정 하는 기능을 제공 합니다. 컨트롤 막대는 일반적으로 부모 프레임 창의 자식 창, 이므로 "형제" 클라이언트 뷰 또는 프레임 창의 MDI 클라이언트를 합니다. 컨트롤 막대 개체를 자체의 위치는 부모 창의 클라이언트 사각형에 대 한 정보를 사용 합니다. 그런 다음 클라이언트 뷰 또는 MDI 클라이언트 창을 채우도록 클라이언트 창의 나머지 부모의 나머지 클라이언트 창 영역을 변경 합니다.

> [!NOTE]
>  단추 컨트롤 막대에 없는 경우에 **명령** 또는 **UPDATE_COMMAND_UI** 처리기 프레임 워크 단추를 자동으로 비활성화 합니다.

## <a name="toolbars"></a>도구 모음

도구 모음에는 명령을 수행 하는 비트맵 단추 행을 표시 하는 컨트롤 막대입니다. 해당 메뉴 항목을 선택 하는 도구 모음 단추를 누르면 메뉴 항목에 매핑된 해당 메뉴 항목에 도구 모음 단추와 동일한 ID를 하는 경우 동일한 처리기를 호출 합니다. 단추는 누름 단추, 라디오 단추나 확인란 기호로 표시 및 동작을 구성할 수 있습니다. 도구 모음에 일반적으로 프레임 창의 맨 위에 맞춰집니다 있지만 MFC 도구 모음 "도킹" 해당 부모 창 또는 미니 프레임 창에는 float 모든 측면에 합니다. 도구 모음도 "부동 상태로 있을 수" 및 해당 크기를 변경할 수 있으며 마우스를 놓습니다. 사용자는 도구 모음 단추 위로 마우스를 이동 하는 대로 도구 모음에 도구 설명을 표시할 수도 있습니다. 도구 설명에 간략하게 단추의 용도 설명 하는 작은 팝업 창입니다.

> [!NOTE]
>  MFC 버전 4.0부터 클래스 [CToolBar](../mfc/reference/ctoolbar-class.md) Windows 도구 모음 공용 컨트롤을 사용 합니다. A `CToolBar` 포함 된 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)합니다. 하지만 이전 도구 모음 계속 지원 되기는 합니다. 문서를 참조 하세요 [도구 모음](../mfc/mfc-toolbar-implementation.md)합니다.

## <a name="status-bars"></a>상태 표시줄

상태 표시줄은 텍스트 출력 창 또는 "지표입니다."를 포함 하는 컨트롤 막대 출력 창 메시지 줄으로 상태 표시기에 자주 사용 됩니다. 메시지 줄 예제 선택한 메뉴 또는 도구 모음 명령 MFC 응용 프로그램 마법사에서 만든 기본 상태 표시줄의 왼쪽 창에서 간략하게 설명 하는 명령 도움말 메시지 줄을 포함 합니다. 상태 표시기 예로 SCROLL LOCK, NUM LOCK 및 기타 키입니다. 상태 표시줄은 일반적으로 프레임 창의 아래쪽에 정렬 됩니다. 클래스를 참조 하세요 [CStatusBar](../mfc/reference/cstatusbar-class.md) 및 클래스 [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)합니다.

## <a name="dialog-bars"></a>대화 상자 모음

대화 상자 막대는 모덜리스 대화 상자의 기능을 사용 하 여 대화 상자 템플릿 리소스에 따라 컨트롤 막대입니다. 대화 상자 막대에는 Windows에 포함 될 수 있습니다 ActiveX 컨트롤 또는 사용자 지정 합니다. 대화 상자와 같이 사용자 컨트롤 간의 탭 수입니다. 대화 상자 막대를 위쪽, 아래쪽, 왼쪽 또는 오른쪽 프레임 창의 맞출 수 있습니다 및 프레임 창에 움직이는 수도 있습니다. 클래스를 참조 하세요 [CDialogBar](../mfc/reference/cdialogbar-class.md)합니다.

## <a name="rebars"></a>Rebars

A [rebar](../mfc/using-crebarctrl.md) rebar 컨트롤에 대 한 도킹, 레이아웃, 상태 및 지 속성 정보를 제공 하는 컨트롤 막대입니다. Rebar 개체는 다양 한 자식 창에 일반적으로 다른 컨트롤 편집 상자, 도구 모음, 목록 상자 등을 포함할 수 있습니다. Rebar 개체는 지정 된 비트맵을 통해 해당 자식 창을 표시할 수 있습니다. 해당 자동 또는 수동으로 크기를 조정할 수 그리퍼 막대를 끌거나 클릭 합니다. 클래스를 참조 하세요 [CReBar](../mfc/reference/crebar-class.md)합니다.

## <a name="see-also"></a>참고자료

[사용자 인터페이스 요소](../mfc/user-interface-elements-mfc.md)
