---
title: AFX 메시지
ms.date: 11/04/2016
f1_keywords:
- SB_LINELEFT
- SB_THUMBTRACK
- AFX_TOOLTIP_TYPE_EDIT
- AFX_WM_ON_HSCROLL
- SB_PAGERIGHT
- AFX_WM_RESETPROMPT
- AFX_WM_CHANGE_RIBBON_CATEGORY
- AFX_TOOLTIP_TYPE_MINIFRAME
- AFX_WM_CUSTOMIZETOOLBAR
- AFX_WM_CHANGE_ACTIVE_TAB
- AFX_WM_ACCGETOBJECT
- AFX_WM_TOOLBARMENU
- AFX_TOOLTIP_TYPE_DOCKBAR
- AFX_WM_CUSTOMIZEHELP
- AFX_WM_ON_GET_TAB_TOOLTIP
- AFX_WM_ON_RIBBON_CUSTOMIZE
- AFX_WM_ON_DRAGCOMPLETE
- AFX_WM_RESETTOOLBAR
- AFX_WM_ON_MOVETOTABGROUP
- AFX_WM_CHECKEMPTYMINIFRAME
- AFX_WM_GETDOCUMENTCOLORS
- SB_RIGHT
- AFX_WM_ON_BEFORE_SHOW_RIBBON_ITEM_MENU
- AFX_WM_ACCGETSTATE
- SB_PAGELEFT
- SB_ENDSCROLL
- AFX_WM_ON_CANCELTABMOVE
- AFX_TOOLTIP_TYPE_TAB
- AFX_WM_WINDOW_HELP
- AFX_WM_HIGHLIGHT_RIBBON_LIST_ITEM
- AFX_WM_SHOWREGULARMENU
- AFX_TOOLTIP_TYPE_TOOLBAR
- AFX_WM_CHANGE_CURRENT_FOLDER
- AFX_WM_UPDATETOOLTIPS
- AFX_WM_ON_MOVE_TAB
- AFX_WM_CHANGING_ACTIVE_TAB
- AFX_WM_RESETMENU
- AFX_WM_GETDRAGBOUNDS
- AFX_WM_RESETCONTEXTMENU
- AFX_TOOLTIP_TYPE_BUTTON
- AFX_WM_ON_CLOSEPOPUPWINDOW
- AFX_TOOLTIP_TYPE_TOOLBOX
- AFX_WM_CHANGEVISUALMANAGER
- SB_LINERIGHT
- AFX_WM_ON_RENAME_TAB
- AFX_TOOLTIP_TYPE_DEFAULT
- AFX_WM_ON_TABGROUPMOUSEMOVE
- SB_LEFT
- AFX_WM_DELETETOOLBAR
- AFX_WM_PROPERTY_CHANGED
- AFX_TOOLTIP_TYPE_ALL
- AFX_WM_ACCHITTEST
- AFX_WM_ON_AFTER_SHELL_COMMAND
- AFX_WM_ON_PRESS_CLOSE_BUTTON
- AFX_WM_RESETKEYBOARD
- AFX_WM_ON_MOVETABCOMPLETE
- AFX_WM_CREATETOOLBAR
- SB_THUMBPOSITION
- AFX_WM_POSTSETPREVIEWFRAME
helpviewer_keywords:
- AFX messages [MFC]
ms.assetid: 3d601f3c-af6d-47d3-8553-34f1318fa74f
ms.openlocfilehash: 5caf40fc757e2c5c90c06e1698ce4c15d1ed6240
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62338061"
---
# <a name="afx-messages"></a>AFX 메시지

이러한 메시지는 MFC에서 사용 됩니다.

## <a name="messages"></a>메시지

다음 표에서 MFC 라이브러리에서 사용 되는 메시지를 나열 합니다.

||||||
|-|-|-|-|-|
|메시지|설명|[in] *wParam*|*lParam* (모든 매개 변수는 [in] 언급이.)|반환 값|
|AFX_WM_ACCGETOBJECT|사용되지 않습니다.|사용되지 않습니다.|해당 사항 없음.|해당 사항 없음.|
|AFX_WM_ACCGETSTATE|내게 필요한 옵션 지원에 사용 됩니다. 이 메시지를 보내 `CMFCPopupMenu` 또는 `CMFCRibbonPanelMenu` 를 현재 요소의 상태를 검색 합니다.|메뉴 단추 또는 구분 기호 일 수 있는 요소의 인덱스입니다.|사용되지 않습니다.|요소의 상태입니다. 인덱스가 유효 하지 않은 경우에-1을은 메뉴 단추에 특별 한 특성이 없는 경우 0입니다. 그렇지 않은 경우 다음 플래그의 조합을 것:<br /><br /> TBBS_DISABLED-항목은 사용할 수 없습니다.<br /><br /> 항목이 선택 되어 TBBS_CHECKED-<br /><br /> TBBS_BUTTON-항목은 표준 누름<br /><br /> TBBS_PRESSED-단추가 눌러져<br /><br /> TBBS_INDETERMINATE-정의 되지 않은 상태<br /><br /> TBBS_SEPARATOR-대신 메뉴 단추를 다른 메뉴 항목과 구분을이 요소 폼|
|AFX_WM_CHANGE_ACTIVE_TAB|프레임 워크는 크기 조정 가능한 컨트롤 막대 컨트롤에이 메시지를 보냅니다. 알림을 받으려면이 메시지를 처리 `CMFCTabCtrl` 사용자는 활성 탭 변경 될 때 개체입니다.|탭의 인덱스입니다.|사용되지 않습니다.|0이 아닙니다.|
|AFX_WM_CHANGE_CURRENT_FOLDER|프레임 워크의 부모에 대 한이 메시지를 보냅니다 `CMFCShellListCtrl` 사용자가 현재 폴더를 변경 하는 경우.|사용되지 않습니다.|사용되지 않습니다.|사용되지 않습니다.|
|AFX_WM_CHANGEVISUALMANAGER|프레임 워크는 사용자는 현재 비주얼 관리자를 변경할 때 모든 프레임 창에이 메시지를 보냅니다. 이 메시지에 대 한 응답으로 프레임 창을 해당 영역을 다시 계산 하 고 필요에 따라 다른 매개 변수를 조정 합니다. 이 이벤트에 대 한 알림을 받을 경우 응용 프로그램에서 AFX_WM_CHANGEVISUALMANAGER 메시지를 처리할 수 있습니다. 기본 클래스 처리기를 호출 해야 합니다 (`OnChangeVisualManager`) 프레임 워크의 내부는 되도록이 이벤트의 처리는 수행 합니다.|사용되지 않습니다.|사용되지 않습니다.|사용되지 않습니다.|
|AFX_WM_CHANGING_ACTIVE_TAB|부모에 전송 `CMFCTabCtrl` 개체입니다.  알림을 받으려는 경우이 메시지를 처리할 `CMFCTabCtrl` 사용자 탭으로 다시 설정 하는 경우 개체입니다.|활성화 되는 탭 인덱스입니다.|사용되지 않습니다.|0이 아닙니다.|
|AFX_WM_CHECKEMPTYMINIFRAME|내부 전용입니다.|해당 사항 없음.|해당 사항 없음.|해당 사항 없음.|
|AFX_WM_CREATETOOLBAR|보낸 `CMFCToolBarsListPropertyPage` 만드는 사용자는 새 도구 모음 사용자 지정 프로세스 중입니다. 사용자 지정 CMFCToolBar 파생 개체를 인스턴스화하기 위해이 메시지를 처리할 수 있습니다. 이 메시지를 처리 하 고 도구 모음을 직접 만들 경우 기본 처리기로 호출을 생략 합니다.|사용되지 않습니다.|도구 모음의 이름을 포함 하는 문자열에 대 한 포인터입니다.|새로 만든된 도구 모음에 대 한 포인터입니다. NULL은 도구 모음 만들기가 취소 되었음을 나타냅니다.|
|AFX_WM_CUSTOMIZEHELP|사용자 지정 속성 시트에서 주 프레임 창으로 전송 `CMFCToolbarCustomize Dialog` 를 누를 때 합니다 **도움말** 단추나 F1 키입니다.|사용자 지정 속성 시트의 현재 페이지를 지정합니다.|`CMFCToolbarCustomize Dialog` 개체에 대한 포인터입니다.|0입니다.|
|AFX_WM_CUSTOMIZETOOLBAR|`CMFCToolbarCustomize Dialog` 는 사용자가 새 도구 모음을 만들 부모 프레임에 알리기 위해이 메시지를 보냅니다.|사용자 지정 시작 되 면 FALSE 사용자 지정이 완료 되 면 TRUE입니다.|사용되지 않습니다.|0입니다.|
|AFX_WM_DELETETOOLBAR|사용자가 사용자 지정 모드에서 도구 모음을 삭제 하려고 하면 주 프레임 창으로 전송 합니다.<br /><br /> 사용자 사용자 지정 모드에서 도구 모음을 삭제할 때 추가 작업을 수행 하려면이 메시지를 처리 합니다. 또한 기본 처리기를 호출 해야 (`OnToolbarDelete`), 도구 모음에서 삭제 합니다. 기본 처리기가 도구 모음을 삭제할 수 있는지 여부를 나타내는 값을 반환 합니다.|사용되지 않습니다.|에 대 한 포인터를 `CMFCToolBar` 삭제할 개체입니다.|0이 아닌 경우 도구 모음을 삭제할 수 없습니다. 그렇지 않으면 0입니다.|
|AFX_WM_GETDOCUMENTCOLORS|`CMFCColorMenuButton` 문서 색 검색할 주 프레임 창에이 메시지를 보냅니다.|사용되지 않습니다.|[out에서] 에 대 한 포인터를 `CList<COLORREF, COLORREF>` 개체입니다.|0입니다.|
|AFX_WM_GETDRAGBOUNDS|내부 전용입니다.|해당 사항 없음.|해당 사항 없음.|해당 사항 없음.|
|AFX_WM_HIGHLIGHT_RIBBON_LIST_ITEM|사용자는 리본 목록 항목을 강조 하는 경우 주 프레임 창으로 전송 합니다.|강조 표시 된 항목의 인덱스|에 대 한 포인터 `CMFCBaseRibbonElement`|사용되지 않습니다.|
|AFX_WM_ON_AFTER_SHELL_COMMAND|부모에 보냅니다 `CMFCShellListCtrl` 또는 `CMFCShellTreeCtrl` 사용자 완료 셸 명령을 실행 하는 경우를 제어 합니다.|사용자가 실행 된 명령 ID|사용되지 않습니다.|응용 프로그램에서이 메시지를 처리할 경우 0을 반환 해야 합니다.|
|AFX_WM_ON_BEFORE_SHOW_RIBBON_ITEM_MENU|프레임 워크는 팝업 메뉴를 표시 하기 전에 리본 메뉴의 부모에이 메시지를 보냅니다. 이 메시지를 처리 하 고 언제 든 지 팝업 메뉴를 수정할 수 있습니다.|사용되지 않습니다.|에 대 한 포인터 `CMFCBaseRibbonElement`|사용되지 않습니다.|
|AFX_WM_ON_CANCELTABMOVE|내부 전용입니다.|해당 사항 없음.|해당 사항 없음.||
|AFX_WM_ON_CHANGE_RIBBON_CATEGORY|프레임 워크는 사용자가 활성 리본 컨트롤 범주를 변경할 때 주 프레임에이 메시지를 보냅니다.|사용되지 않습니다.|에 대 한 포인터를 `CMFCRibbonBar` 해당 범주가 변경 되었습니다.|사용되지 않습니다.|
|AFX_WM_ON_CLOSEPOPUPWINDOW|프레임 워크의 관리자에 게 알리는이 메시지를 보냅니다 `CMFCDesktopAlertWnd` 기간은을 닫아야 합니다.|사용되지 않습니다.|에 대 한 포인터 `CMFCDesktopAlertWnd` 개체입니다.|사용되지 않습니다.|
|AFX_WM_ON_DRAGCOMPLETE|내부 전용입니다.|해당 사항 없음.|해당 사항 없음.|해당 사항 없음.|
|AFX_WM_ON_GET_TAB_TOOLTIP|되려고 할 때 탭 창 탭에 대 한 도구 설명이 표시 사용자 지정 도구 설명을 사용 하는 경우 주 프레임 창으로 전송 합니다.|사용되지 않습니다.|에 대 한 포인터를 `CMFCTabToolTipInfo` 구조입니다.|사용되지 않습니다.|
|AFX_WM_ON_HSCROLL|크기 조정 가능한 컨트롤 막대 컨트롤에 전달 합니다. 알림을 받으려면이 메시지를 처리 `CMFCTabCtrl` 탭된 위젯의 가로 스크롤 막대의 스크롤 이벤트를 발생 하는 경우 개체입니다.|하위 워드 사용자 지정 하는 스크롤 막대 값의 요청을 스크롤 하는 것을 지정 합니다.  자세한 내용은 이 항목 뒷부분에 나오는 표를 참조하십시오.|사용되지 않습니다.|0이 아닙니다.|
|AFX_WM_ON_MOVE_TAB|사용자가 탭을 새 위치로 끌 때 탭된 창의 부모에 전송 합니다.|원래 위치에 있는 탭의 0부터 시작 하는 인덱스입니다.|[out] 새로운 위치에 있는 탭의 0부터 시작 하는 인덱스입니다.|0입니다.|
|AFX_WM_ON_MOVETABCOMPLETE|내부 전용입니다.|해당 사항 없음.|해당 사항 없음.|해당 사항 없음.|
|AFX_WM_ON_MOVETOTABGROUP|사용자 MDI 자식 창에 하나의 탭된 그룹에서 다른 위치로 이동 하는 경우 주 프레임 창으로 전송 합니다.|탭된 창에 대 한 핸들 (`CMFCTabCtrl`) MDI 자식 창을 제거 되었습니다.|[out] 탭된 창에 대 한 핸들 (`CMFCTabCtrl`)는 MDI 자식 창에 삽입 되었습니다.|무시됩니다.|
|AFX_WM_ON_PRESS_CLOSE_BUTTON|부모에 보냅니다 `CDockablePane` 을 클릭할 때 합니다 **닫기** 컨트롤 막대의 캡션 단추입니다.|사용되지 않습니다.|사용자가 클릭 하는 도킹 가능한 창에 대 한 포인터를 **닫기** 단추입니다.|TRUE 이면 창을 닫을 수 없습니다. 그렇지 않으면 FALSE입니다.|
|AFX_WM_ON_RENAME_TAB|사용자는 편집 가능한 탭 이름을 바꾼 후 탭 창의 부모에 전송 합니다.|이름이 바뀐된 탭의 0부터 시작 하는 인덱스입니다.|[out] 새 탭 이름을 포함 하는 문자열에 대 한 포인터입니다.|응용 프로그램입니다;이 메시지를 처리 하는 경우 0이 아닌 값 프레임 워크에 대 한 호출 표시 되지 것입니다 `CMFCBaseTabCtrl::SetTabLabel`합니다.  0이 반환 되 면 다음 `CMFCBaseTabCtrl::SetTabLabel` 프레임 워크에서 호출 됩니다.|
|AFX_WM_ON_RIBBON_CUSTOMIZE|사용자가 사용자 지정을 시작할 때 부모 프레임에 전송 합니다. 사용자 고유의 사용자 지정 대화 상자를 표시 하려는 경우이 메시지를 처리 합니다.|사용되지 않습니다.|사용자 지정 리본 컨트롤에 대 한 포인터입니다.|응용 프로그램이이 메시지를 처리 하 고 자체 사용자 지정 대화 상자를 표시 하는 경우에 0이 아닙니다. 응용 프로그램에서 0을 반환 하는 경우 프레임 워크에는 기본 제공 사용자 지정 대화 상자가 표시 됩니다.|
|AFX_WM_ON_TABGROUPMOUSEMOVE|내부 전용입니다.|해당 사항 없음.|해당 사항 없음.|해당 사항 없음.|
|AFX_WM_POSTSETPREVIEWFRAME|인쇄 미리 보기 모드를 변경한는 주 프레임에 알리기 위해 전송|True 이면 인쇄 미리 보기 모드가 설정 되어 있는지를 나타냅니다. FALSE 이면 해당 인쇄 미리 보기 모드를 해제 합니다.|사용되지 않습니다.|사용되지 않습니다.|
|AFX_WM_PROPERTY_CHANGED|속성 그리드 컨트롤의 소유자에 게 전송 (`CMFCPropertyGridCtrl`) 사용자는 선택한 속성의 값을 변경 하는 경우.|컨트롤의 ID는 속성 목록입니다.|속성에 대 한 포인터 (`CMFCPropertyGridProperty`) 변경 합니다.|사용되지 않습니다.|
|AFX_WM_RESETCONTEXTMENU|사용자가 상황에 맞는 메뉴 사용자 지정 하는 동안 다시 때 주 프레임 창으로 보냅니다.|상황에 맞는 메뉴의 리소스 ID입니다.|현재 상황에 맞는 메뉴에 대 한 포인터로 `CMFCPopupMenu`합니다.|사용되지 않습니다.|
|AFX_WM_RESETKEYBOARD|프레임 워크를 사용자 지정 하는 동안 모든 키보드 액셀러레이터 키를 다시 설정 하는 경우 주 프레임 창에이 메시지를 보냅니다.|사용되지 않습니다.|사용되지 않습니다.|사용되지 않습니다.|
|AFX_WM_RESETMENU|프레임 워크 (프레임 창) 메뉴 소유자에 게이 메시지를 보냅니다는 사용자가 사용자 지정 하는 동안 응용 프로그램 프레임 메뉴를 재설정 하는 경우|메뉴 리소스 id입니다.|사용되지 않습니다.|사용되지 않습니다.|
|AFX_WM_RESETPROMPT|프레임 워크는 사용자 지정 대화 상자 도구 모음에서 도구 모음을 사용자 다시 설정 하는 경우이 메시지를 보냅니다. 기본 처리기는 사용자가 도구 모음 다시 설정 하려고 하는지 여부를 묻는 메시지 상자를 표시 합니다.|사용되지 않습니다.|사용되지 않습니다.|사용되지 않습니다.|
|AFX_WM_RESETTOOLBAR|`CMFCToolBar` 개체 도구 모음 복원 되 면 원래 상태로, 리소스에서 로드 합니다.이 메시지를 보냅니다. 해당 클래스에서 파생 되는 도구 모음 단추를 삽입 합니다.이 메시지를 처리 `CMFCToolbarButton`합니다. 자세한 내용은 `CMFCToolbarComboBoxButton`을 참조하세요.|상태가 복원 도구 모음의 리소스 ID입니다.|사용되지 않습니다.|0입니다.|
|AFX_WM_SHOWREGULARMENU|`CMFCToolbarMenuButton` 개체는 일반 메뉴 단추를 클릭 하면 해당 소유자에 게이 메시지를 보냅니다. 사용 될 때마다가이 메시지를 처리 `CMFCToolbarMenuButton` 단추를 클릭할 때 팝업 메뉴를 표시 합니다.|메시지를 전송 하는 단추의 명령 ID입니다.|커서의 화면 좌표입니다. 하위 단어에 대 한 x-좌표를 지정합니다. 상위 word에 대 한 y-좌표를 지정합니다.|사용되지 않습니다.|
|AFX_WM_TOOLBARMENU|마우스 포인터가 클라이언트나 창의 비클라이언트 영역에 있는 동안 마우스 오른쪽 단추를 놓으면 주 프레임 창으로 전송 합니다.|사용되지 않습니다.|마우스 포인터의 화면 좌표입니다. 하위 단어에 대 한 x-좌표를 지정합니다. 상위 word에 대 한 y-좌표를 지정합니다.|응용 프로그램이이 메시지를 처리 하는 경우 0 그렇지 않으면, 0이 아닌 값입니다.|
|AFX_WM_UPDATETOOLTIPS|모든 도구 설명 소유자에 게 전송 되어 해당 도구 설명 컨트롤을 다시 만들어야 합니다를 나타냅니다.|이 메시지를 처리 해야 하는 컨트롤의 형식입니다. 가능한 값 목록은이 항목 뒷부분에 나오는 표를 참조 하세요.|사용되지 않습니다.|사용되지 않습니다.|
|AFX_WM_WINDOW_HELP|`CMFCWindowsManagerDialog` 클릭할 때 부모 프레임에이 메시지를 보냅니다는 **도움말** 단추를 클릭 하 여 도움말 모드를 시작 또는 합니다 **도움말** 캡션 단추나 F1 키입니다.|사용되지 않습니다.|인스턴스에 대 한 포인터 `CMFCWindowsManagerDialog`합니다.|사용되지 않습니다.|

다음 표에서 값의 하위 워드를 *lParam* AFX_WM_HSCROLL 메서드의 매개 변수:

|||
|-|-|
|값|의미|
|SB_ENDSCROLL|사용자는 스크롤을 종료합니다.|
|SB_LEFT|사용자는 왼쪽 위를 스크롤합니다.|
|SB_RIGHT|사용자는 오른쪽 아래로 스크롤합니다.|
|SB_LINELEFT|사용자는 하나의 단위로 왼쪽을 스크롤합니다.|
|SB_LINERIGHT|사용자에는 하나의 단위로 오른쪽으로 스크롤합니다.|
|SB_PAGELEFT|사용자는 창의 너비 만큼 왼쪽으로 스크롤합니다.|
|SB_PAGERIGHT|사용자는 창의 너비 만큼 오른쪽을 스크롤합니다.|
|SB_THUMBPOSITION|사용자가 끌어 스크롤 상자 (엄지 단추) 하 고 마우스 단추를 놓을 합니다. 상위 단어의 끌기 작업의 끝에 있는 스크롤 상자 위치를 나타냅니다.|
|SB_THUMBTRACK|사용자가 스크롤 상자를 끌고 있습니다. AFX_WM_ON_HSCROLL 메시지는 사용자가 마우스 단추를 놓을 때까지이 값을 사용 하 여 반복적으로 전송 됩니다. 상위 단어는 스크롤 상자 끌어왔습니다 위치를 나타냅니다.|

> [!NOTE]
>  상위 단어를 *lParam* 매개 변수 인지 하위 단어 SB_THUMBPOSITION SB_THUMBTRACK 스크롤 상자의 현재 위치를 지정;이 고, 그렇지이 단어를 사용 되지 않습니다.

다음 표에서 대 한 플래그 값을 *lParam* AFX_WM_UPDATETOOLTIPS 메시지의 매개 변수:

|||
|-|-|
|플래그|값|
|AFX_TOOLTIP_TYPE_DEFAULT|0x0001|
|AFX_TOOLTIP_TYPE_TOOLBAR|0x0002|
|AFX_TOOLTIP_TYPE_TAB|0x0004|
|AFX_TOOLTIP_TYPE_MINIFRAME|0x0008|
|AFX_TOOLTIP_TYPE_DOCKBAR|0x0010|
|AFX_TOOLTIP_TYPE_EDIT|0x0020|
|AFX_TOOLTIP_TYPE_BUTTON|0x0040|
|AFX_TOOLTIP_TYPE_TOOLBOX|0x0080|
|AFX_TOOLTIP_TYPE_ALL|0xFFFF|

## <a name="see-also"></a>참고자료

[매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
