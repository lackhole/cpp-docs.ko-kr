---
title: 인터페이스 요소
ms.date: 11/19/2018
helpviewer_keywords:
- architecture [MFC], MFC Feature Pack
- MFC Feature Pack, architecture
ms.assetid: eead6827-9602-40a3-8038-8986e8207385
ms.openlocfilehash: fa6dc78c95717f9201e18346f1cbe573fa3c48d2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62153585"
---
# <a name="interface-elements"></a>인터페이스 요소

이 문서는 Visual Studio 2008 SP1에서 도입 된 인터페이스 요소에 설명 하 고 또한 이전 버전의 라이브러리를 사용 하 여 차이점을 설명 합니다.

다음 그림에서는 새 인터페이스 요소를 사용 하 여 빌드된 응용 프로그램을 보여 줍니다.

![MFC 기능 팩 예제 응용 프로그램](../mfc/media/mfc_featurepack.png "MFC 기능 팩 예제 응용 프로그램")

## <a name="window-docking"></a>창 도킹

창 도킹 기능에는 Visual Studio 그래픽 사용자 인터페이스는 도킹 창와 유사 합니다.

## <a name="control-bars-are-now-panes"></a>컨트롤 막대는 이제 창이

컨트롤 막대 창이 이제 라고 하며에서 파생 됩니다 [CBasePane 클래스](../mfc/reference/cbasepane-class.md)합니다. 컨트롤 막대의 기본 클래스를 이전 버전의 MFC `CControlBar`입니다.

응용 프로그램 주 프레임 창은 일반적으로 표현 합니다 [CFrameWndEx 클래스](../mfc/reference/cframewndex-class.md) 또는 [CMDIFrameWndEx 클래스](../mfc/reference/cmdiframewndex-class.md)합니다. 주 프레임 라고 합니다 *도킹 사이트*합니다. 창 부모의 세 가지 유형 중 하나일 수 있습니다: 도킹 사이트, 도킹 모음 또는 미니 프레임 창입니다.

창의 두 종류가 있습니다: 크기 조정이 불가능 하 고 크기를 조정할 수 있습니다. 상태 표시줄 및 도구 모음 등의 크기를 조정할 창 분할자 또는 슬라이더를 사용 하 여 조정할 수 있습니다. 크기를 조정할 창 (하나의 창에 도킹할 수 간의 분할자를 만드는 다른 창) 컨테이너를 구성할 수 있습니다. 그러나 크기를 조정할 창 (고정) 막대를 도킹 하려면 연결할 수 없습니다.

크기 조정이 불가능 창을 사용 하 여 응용 프로그램에서 파생 [CPane 클래스](../mfc/reference/cpane-class.md)합니다.  응용 프로그램 크기를 조정할 창에서는 파생에서 [CDockablePane 클래스](../mfc/reference/cdockablepane-class.md)

## <a name="dock-site"></a>도킹 사이트

도킹 사이트 (또는 주 프레임 창)에 모든 창 및 응용 프로그램에서 미니 프레임 창을 소유합니다. 도킹 사이트에 포함 된 [CDockingManager](../mfc/reference/cdockingmanager-class.md) 멤버입니다. 이 멤버는 도킹 사이트에 속하는 모든 창 목록을 유지 관리 합니다. 도킹 사이트의 바깥쪽 가장자리에서 만든 창 목록의 시작에 배치 됩니다 있도록 목록 정렬 되어 있습니다. 프레임 워크를 다시 그립니다 도킹 사이트에이 목록을 통해 루프 및 도킹 사이트의 현재 경계 사각형을 포함 하도록 각 창 레이아웃을 조정 합니다. 호출할 수 있습니다 `AdjustDockingLayout` 또는 `RecalcLayout` 도킹 레이아웃을 조정 해야 하는 시기와 프레임 워크 도킹 관리자에 게이 호출을 리디렉션합니다.

## <a name="dock-bars"></a>도킹 막대

각 주 프레임 창에 배치할 수 있습니다 *막대를 도킹* 테두리를 따라 합니다. 도킹 막대는 속해 있는 창에 [CDockSite 클래스](../mfc/reference/cdocksite-class.md)합니다. 도킹 막대에서 파생 된 개체를 사용할 수 있습니다 [CPane](../mfc/reference/cpane-class.md), 도구 모음 등입니다. 도킹 막대를 만들려면 주 프레임 창 초기화 될 때 호출 `EnableDocking`합니다. 자동 숨기기 막대를 사용 하도록 설정 하려면 호출 `EnableAutoHideBars`합니다. `EnableAutoHideBars` 만듭니다 [CAutoHideDockSite](../mfc/reference/cautohidedocksite-class.md) 개체 이며 각 도킹 표시줄 옆에 있는를 배치 합니다.

각 도킹 모음 도킹 행으로 구분 됩니다. 고정 행으로 표시 됩니다는 [CDockingPanesRow 클래스](../mfc/reference/cdockingpanesrow-class.md)합니다. 각 고정 행에는 도구 모음 목록이 포함 되어 있습니다. 사용자 도구 모음 도킹 또는 같은 도킹 모음 내에서 다른 한 행에서 도구 모음을 이동 하는 경우 프레임 워크 중 하나 새 행을 만들고 그에 따라 도킹 표시줄의 크기를 조정 또는 기존 행에 도구 모음을 배치 하는 것입니다.

## <a name="mini-frame-windows"></a>미니 프레임 Windows

부동 창 미니 프레임 창에 상주합니다. 미니 프레임 창은 두 클래스로 표현 됩니다. [CMDITabInfo 클래스](../mfc/reference/cmditabinfo-class.md) (창 하나만 포함할 수 있는) 및 [CMultiPaneFrameWnd 클래스](../mfc/reference/cmultipaneframewnd-class.md) (여러 개의 창이 포함할 수 있음). 코드에서 창을 float, 호출 [CBasePane::FloatPane](../mfc/reference/cbasepane-class.md#floatpane)합니다. 창을 부동 프레임 워크에는 자동으로 미니 프레임 창을 만듭니다 후 해당 미니 프레임 창이 부동 창의 부모 됩니다. 부동 창 도킹 프레임 워크에는 부모를 다시 설정 되 고 부동 창 (도구 모음)에 대 한 도킹 막대나 도킹 사이트 (예: 크기 조정 가능한 창) 됩니다.

## <a name="pane-dividers"></a>창 구분선

창 구분선 (슬라이더 또는 분할자 라고도 함)으로 표시 됩니다는 [CPaneDivider 클래스](../mfc/reference/cpanedivider-class.md)합니다. 창을 도킹 하는 사용자, 프레임 워크 창 도킹 사이트에 또는 다른 창에서 도킹 여부에 관계 없이 창 구분선을 만듭니다. 창을 도킹 사이트에 도킹을 하는 경우 창 구분선 라고 합니다 *기본 창 구분선*합니다. 기본 창 구분선 도킹 사이트에 대 한 모든 도킹 창 레이아웃을 담당 합니다. 도킹 관리자에는 기본 창 구분선 목록과 창 목록을 유지 관리합니다. 도킹 관리자는 모든 도킹 창의 레이아웃을 처리 합니다.

## <a name="containers"></a>컨테이너

모든 크기를 조정할 창, 도킹 될 때 컨테이너에 유지 됩니다. 컨테이너에서 표시 되는 [CPaneContainer 클래스](../mfc/reference/cpanecontainer-class.md)합니다. 각 컨테이너는 왼쪽 및 오른쪽 부분 간에 해당 왼쪽, 오른쪽 창, 왼쪽된 하위 컨테이너, 오른쪽 하위 컨테이너 및 분할자에 대 한 포인터에 있습니다. (*왼쪽* 하 고 *오른쪽* 실제 양쪽을 가리키지 않습니다 하지만 대신 분기 트리 구조를 식별 합니다.) 이 방식으로 창 및 분할 창을 트리를 빌드할 수 있으며 따라서 창 크기를 조정할 수 함께 하는 복잡 한 레이아웃을 달성 했습니다. `CPaneContainer` 창과이 트리에서 상주 하는 슬라이더의 두 목록도 유지 관리; 클래스는 컨테이너 트리와 유지 관리 합니다. 창 컨테이너 관리자는 일반적으로 기본 슬라이더 및 여러 창을 수행 하는 미니 프레임 창에 포함 됩니다.

## <a name="auto-hide-control-bars"></a>자동 숨기기 컨트롤 막대

기본적으로 각 `CDockablePane` 자동 숨기기 기능을 지원 합니다. 캡션에 있는 핀 단추를 클릭할 때는 `CDockablePane`, 프레임 워크 창 자동 숨기기 모드로 전환 합니다. 프레임 워크를 처리 하기 위해 클릭 만듭니다는 [CMFCAutoHideBar 클래스](../mfc/reference/cmfcautohidebar-class.md) 및 [CMFCAutoHideButton 클래스](../mfc/reference/cmfcautohidebutton-class.md) 연관는 `CMFCAutoHideBar` 개체입니다. 새 배치 프레임 워크 `CMFCAutoHideBar` 에 [CAutoHideDockSite](../mfc/reference/cautohidedocksite-class.md)합니다. 프레임 워크 또한 연결 된 `CMFCAutoHideButton` 도구 모음에 있습니다. 합니다 [CDockingManager 클래스](../mfc/reference/cdockingmanager-class.md) 유지 관리는 `CDockablePane`합니다.

## <a name="tabbed-control-bars-and-outlook-bars"></a>탭된 컨트롤 막대 및 Outlook 표시줄

합니다 [CMFCBaseTabCtrl 클래스](../mfc/reference/cmfcbasetabctrl-class.md) 분리 가능한 탭을 사용 하 여 탭 창의 기본 기능을 구현 합니다. 사용 하는 `CMFCBaseTabCtrl` 개체를 초기화 한 [CBaseTabbedPane 클래스](../mfc/reference/cbasetabbedpane-class.md) 응용 프로그램에서 합니다. `CBaseTabbedPane` 파생 됩니다 `CDockablePane` 에 대 한 포인터를 유지 관리는 `CMFCBaseTabCtrl` 개체입니다. `CBaseTabbedPane` 도킹 및 탭된 컨트롤 막대의 크기를 조정할 수 있습니다. 사용 하 여 [cdockablepane:: Attachtotabwnd](../mfc/reference/cdockablepane-class.md#attachtotabwnd) 을 동적으로 도킹 있으며 탭 컨트롤 막대를 만듭니다.

Outlook 표시줄 컨트롤은 또한 탭된 표시줄 기반으로 합니다. 합니다 [CMFCOutlookBar 클래스](../mfc/reference/cmfcoutlookbar-class.md) 에서 파생 된 `CBaseTabbedPane`합니다. Outlook 표시줄을 사용 하는 방법에 대 한 자세한 내용은 참조 하세요. [CMFCOutlookBar 클래스](../mfc/reference/cmfcoutlookbar-class.md)합니다.

## <a name="see-also"></a>참고자료

[개념](../mfc/mfc-concepts.md)
