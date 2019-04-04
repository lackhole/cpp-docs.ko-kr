---
title: CDockingManager 클래스
ms.date: 11/04/2016
f1_keywords:
- CDockingManager
- AFXDOCKINGMANAGER/CDockingManager
- AFXDOCKINGMANAGER/CDockingManager::AddDockSite
- AFXDOCKINGMANAGER/CDockingManager::AddHiddenMDITabbedBar
- AFXDOCKINGMANAGER/CDockingManager::AddMiniFrame
- AFXDOCKINGMANAGER/CDockingManager::AddPane
- AFXDOCKINGMANAGER/CDockingManager::AdjustDockingLayout
- AFXDOCKINGMANAGER/CDockingManager::AdjustPaneFrames
- AFXDOCKINGMANAGER/CDockingManager::AdjustRectToClientArea
- AFXDOCKINGMANAGER/CDockingManager::AlignAutoHidePane
- AFXDOCKINGMANAGER/CDockingManager::AutoHidePane
- AFXDOCKINGMANAGER/CDockingManager::BringBarsToTop
- AFXDOCKINGMANAGER/CDockingManager::BuildPanesMenu
- AFXDOCKINGMANAGER/CDockingManager::CalcExpectedDockedRect
- AFXDOCKINGMANAGER/CDockingManager::Create
- AFXDOCKINGMANAGER/CDockingManager::DeterminePaneAndStatus
- AFXDOCKINGMANAGER/CDockingManager::DisableRestoreDockState
- AFXDOCKINGMANAGER/CDockingManager::DockPane
- AFXDOCKINGMANAGER/CDockingManager::DockPaneLeftOf
- AFXDOCKINGMANAGER/CDockingManager::EnableAutoHidePanes
- AFXDOCKINGMANAGER/CDockingManager::EnableDocking
- AFXDOCKINGMANAGER/CDockingManager::EnableDockSiteMenu
- AFXDOCKINGMANAGER/CDockingManager::EnablePaneContextMenu
- AFXDOCKINGMANAGER/CDockingManager::FindDockSite
- AFXDOCKINGMANAGER/CDockingManager::FindDockSiteByPane
- AFXDOCKINGMANAGER/CDockingManager::FindPaneByID
- AFXDOCKINGMANAGER/CDockingManager::FixupVirtualRects
- AFXDOCKINGMANAGER/CDockingManager::FrameFromPoint
- AFXDOCKINGMANAGER/CDockingManager::GetClientAreaBounds
- AFXDOCKINGMANAGER/CDockingManager::GetDockingMode
- AFXDOCKINGMANAGER/CDockingManager::GetDockSiteFrameWnd
- AFXDOCKINGMANAGER/CDockingManager::GetEnabledAutoHideAlignment
- AFXDOCKINGMANAGER/CDockingManager::GetMiniFrames
- AFXDOCKINGMANAGER/CDockingManager::GetOuterEdgeBounds
- AFXDOCKINGMANAGER/CDockingManager::GetPaneList
- AFXDOCKINGMANAGER/CDockingManager::GetSmartDockingManager
- AFXDOCKINGMANAGER/CDockingManager::GetSmartDockingManagerPermanent
- AFXDOCKINGMANAGER/CDockingManager::GetSmartDockingParams
- AFXDOCKINGMANAGER/CDockingManager::GetSmartDockingTheme
- AFXDOCKINGMANAGER/CDockingManager::HideAutoHidePanes
- AFXDOCKINGMANAGER/CDockingManager::InsertDockSite
- AFXDOCKINGMANAGER/CDockingManager::InsertPane
- AFXDOCKINGMANAGER/CDockingManager::IsDockSiteMenu
- AFXDOCKINGMANAGER/CDockingManager::IsInAdjustLayout
- AFXDOCKINGMANAGER/CDockingManager::IsOLEContainerMode
- AFXDOCKINGMANAGER/CDockingManager::IsPointNearDockSite
- AFXDOCKINGMANAGER/CDockingManager::IsPrintPreviewValid
- AFXDOCKINGMANAGER/CDockingManager::LoadState
- AFXDOCKINGMANAGER/CDockingManager::LockUpdate
- AFXDOCKINGMANAGER/CDockingManager::OnActivateFrame
- AFXDOCKINGMANAGER/CDockingManager::OnClosePopupMenu
- AFXDOCKINGMANAGER/CDockingManager::OnMoveMiniFrame
- AFXDOCKINGMANAGER/CDockingManager::OnPaneContextMenu
- AFXDOCKINGMANAGER/CDockingManager::PaneFromPoint
- AFXDOCKINGMANAGER/CDockingManager::ProcessPaneContextMenuCommand
- AFXDOCKINGMANAGER/CDockingManager::RecalcLayout
- AFXDOCKINGMANAGER/CDockingManager::ReleaseEmptyPaneContainers
- AFXDOCKINGMANAGER/CDockingManager::RemoveHiddenMDITabbedBar
- AFXDOCKINGMANAGER/CDockingManager::RemoveMiniFrame
- AFXDOCKINGMANAGER/CDockingManager::RemovePaneFromDockManager
- AFXDOCKINGMANAGER/CDockingManager::ReplacePane
- AFXDOCKINGMANAGER/CDockingManager::ResortMiniFramesForZOrder
- AFXDOCKINGMANAGER/CDockingManager::SaveState
- AFXDOCKINGMANAGER/CDockingManager::SendMessageToMiniFrames
- AFXDOCKINGMANAGER/CDockingManager::Serialize
- AFXDOCKINGMANAGER/CDockingManager::SetAutohideZOrder
- AFXDOCKINGMANAGER/CDockingManager::SetDockingMode
- AFXDOCKINGMANAGER/CDockingManager::SetDockState
- AFXDOCKINGMANAGER/CDockingManager::SetPrintPreviewMode
- AFXDOCKINGMANAGER/CDockingManager::SetSmartDockingParams
- AFXDOCKINGMANAGER/CDockingManager::ShowDelayShowMiniFrames
- AFXDOCKINGMANAGER/CDockingManager::ShowPanes
- AFXDOCKINGMANAGER/CDockingManager::StartSDocking
- AFXDOCKINGMANAGER/CDockingManager::StopSDocking
- AFXDOCKINGMANAGER/CDockingManager::m_bHideDockingBarsInContainerMode
- AFXDOCKINGMANAGER/CDockingManager::m_dockModeGlobal
- AFXDOCKINGMANAGER/CDockingManager::m_nDockSensitivity
- AFXDOCKINGMANAGER/CDockingManager::m_nTimeOutBeforeDockingBarDock
- AFXDOCKINGMANAGER/CDockingManager::m_nTimeOutBeforeToolBarDock
helpviewer_keywords:
- CDockingManager [MFC], AddDockSite
- CDockingManager [MFC], AddHiddenMDITabbedBar
- CDockingManager [MFC], AddMiniFrame
- CDockingManager [MFC], AddPane
- CDockingManager [MFC], AdjustDockingLayout
- CDockingManager [MFC], AdjustPaneFrames
- CDockingManager [MFC], AdjustRectToClientArea
- CDockingManager [MFC], AlignAutoHidePane
- CDockingManager [MFC], AutoHidePane
- CDockingManager [MFC], BringBarsToTop
- CDockingManager [MFC], BuildPanesMenu
- CDockingManager [MFC], CalcExpectedDockedRect
- CDockingManager [MFC], Create
- CDockingManager [MFC], DeterminePaneAndStatus
- CDockingManager [MFC], DisableRestoreDockState
- CDockingManager [MFC], DockPane
- CDockingManager [MFC], DockPaneLeftOf
- CDockingManager [MFC], EnableAutoHidePanes
- CDockingManager [MFC], EnableDocking
- CDockingManager [MFC], EnableDockSiteMenu
- CDockingManager [MFC], EnablePaneContextMenu
- CDockingManager [MFC], FindDockSite
- CDockingManager [MFC], FindDockSiteByPane
- CDockingManager [MFC], FindPaneByID
- CDockingManager [MFC], FixupVirtualRects
- CDockingManager [MFC], FrameFromPoint
- CDockingManager [MFC], GetClientAreaBounds
- CDockingManager [MFC], GetDockingMode
- CDockingManager [MFC], GetDockSiteFrameWnd
- CDockingManager [MFC], GetEnabledAutoHideAlignment
- CDockingManager [MFC], GetMiniFrames
- CDockingManager [MFC], GetOuterEdgeBounds
- CDockingManager [MFC], GetPaneList
- CDockingManager [MFC], GetSmartDockingManager
- CDockingManager [MFC], GetSmartDockingManagerPermanent
- CDockingManager [MFC], GetSmartDockingParams
- CDockingManager [MFC], GetSmartDockingTheme
- CDockingManager [MFC], HideAutoHidePanes
- CDockingManager [MFC], InsertDockSite
- CDockingManager [MFC], InsertPane
- CDockingManager [MFC], IsDockSiteMenu
- CDockingManager [MFC], IsInAdjustLayout
- CDockingManager [MFC], IsOLEContainerMode
- CDockingManager [MFC], IsPointNearDockSite
- CDockingManager [MFC], IsPrintPreviewValid
- CDockingManager [MFC], LoadState
- CDockingManager [MFC], LockUpdate
- CDockingManager [MFC], OnActivateFrame
- CDockingManager [MFC], OnClosePopupMenu
- CDockingManager [MFC], OnMoveMiniFrame
- CDockingManager [MFC], OnPaneContextMenu
- CDockingManager [MFC], PaneFromPoint
- CDockingManager [MFC], ProcessPaneContextMenuCommand
- CDockingManager [MFC], RecalcLayout
- CDockingManager [MFC], ReleaseEmptyPaneContainers
- CDockingManager [MFC], RemoveHiddenMDITabbedBar
- CDockingManager [MFC], RemoveMiniFrame
- CDockingManager [MFC], RemovePaneFromDockManager
- CDockingManager [MFC], ReplacePane
- CDockingManager [MFC], ResortMiniFramesForZOrder
- CDockingManager [MFC], SaveState
- CDockingManager [MFC], SendMessageToMiniFrames
- CDockingManager [MFC], Serialize
- CDockingManager [MFC], SetAutohideZOrder
- CDockingManager [MFC], SetDockingMode
- CDockingManager [MFC], SetDockState
- CDockingManager [MFC], SetPrintPreviewMode
- CDockingManager [MFC], SetSmartDockingParams
- CDockingManager [MFC], ShowDelayShowMiniFrames
- CDockingManager [MFC], ShowPanes
- CDockingManager [MFC], StartSDocking
- CDockingManager [MFC], StopSDocking
- CDockingManager [MFC], m_bHideDockingBarsInContainerMode
- CDockingManager [MFC], m_dockModeGlobal
- CDockingManager [MFC], m_nDockSensitivity
- CDockingManager [MFC], m_nTimeOutBeforeDockingBarDock
- CDockingManager [MFC], m_nTimeOutBeforeToolBarDock
ms.assetid: 98e69c43-55d8-4f43-b861-4fda80ec1e32
ms.openlocfilehash: 6d3bbafa15ada97f53710f0faf6a18ea8e892f6c
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58771320"
---
# <a name="cdockingmanager-class"></a>CDockingManager 클래스

주 프레임 창에서 도킹 레이아웃을 제어하는 핵심 기능을 구현합니다.

## <a name="syntax"></a>구문

```
class CDockingManager : public CObject
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CDockingManager::AddDockSite](#adddocksite)|도킹 창을 만들고 컨트롤 막대 목록에 추가 합니다.|
|[CDockingManager::AddHiddenMDITabbedBar](#addhiddenmditabbedbar)|막대에 대 한 핸들을 추가 하는 숨겨진된 MDI 탭 창 막대 목록에는 창입니다.|
|[CDockingManager::AddMiniFrame](#addminiframe)|미니 프레임 목록에는 프레임을 추가합니다.|
|[CDockingManager::AddPane](#addpane)|창을 도킹 관리자에 등록합니다.|
|[CDockingManager::AdjustDockingLayout](#adjustdockinglayout)|다시 계산 하 고 프레임 창에서 모든 창의 레이아웃을 조정 합니다.|
|[CDockingManager::AdjustPaneFrames](#adjustpaneframes)|모든 창에 전송할 WM_NCCALCSIZE 메시지 및 `CPaneFrameWnd` windows.|
|[CDockingManager::AdjustRectToClientArea](#adjustrecttoclientarea)|사각형의 맞춤을 조정 합니다.|
|[CDockingManager::AlignAutoHidePane](#alignautohidepane)|전체 너비를 걸리는 또는 둘러싸인 프레임의 클라이언트 영역 높이 도킹 사이트 도킹 창을 자동 숨기기 모드에서 크기를 조정 합니다.|
|[CDockingManager::AutoHidePane](#autohidepane)|자동 숨기기 도구 모음을 만듭니다.|
|[CDockingManager::BringBarsToTop](#bringbarstotop)|지정된 된 맞춤 맨 위에 있는 도킹 된 막대를 제공 합니다.|
|[CDockingManager::BuildPanesMenu](#buildpanesmenu)|도킹 창 및 도구 모음 이름 메뉴에 추가합니다.|
|[CDockingManager::CalcExpectedDockedRect](#calcexpecteddockedrect)|도킹 된 창의 예상된 사각형을 계산합니다.|
|[CDockingManager::Create](#create)|도킹 관리자를 만듭니다.|
|[CDockingManager::DeterminePaneAndStatus](#determinepaneandstatus)|지정된 된 지점 및 도킹 상태를 포함 하는 창을 확인 합니다.|
|[CDockingManager::DisableRestoreDockState](#disablerestoredockstate)|사용 하거나 레지스트리에서 도킹 레이아웃의 로드를 사용 하지 않도록 설정 합니다.|
|[CDockingManager::DockPane](#dockpane)|창을 다른 창 또는 프레임 창에 도킹합니다.|
|[CDockingManager::DockPaneLeftOf](#dockpaneleftof)|창을 다른 창의 왼쪽에 도킹합니다.|
|[CDockingManager::EnableAutoHidePanes](#enableautohidepanes)|주 프레임 창의 도킹을 사용 하도록 설정 하 고가 도킹 창을 만들고 컨트롤 막대 목록에 추가 합니다.|
|[CDockingManager::EnableDocking](#enabledocking)|도킹 창을 만들고를 주 프레임 창의 도킹을 사용 하도록 설정 합니다.|
|[CDockingManager::EnableDockSiteMenu](#enabledocksitemenu)|모든 도킹 창의 캡션에 팝업 메뉴를 열고 추가 단추를 표시 합니다.|
|[CDockingManager::EnablePaneContextMenu](#enablepanecontextmenu)|라이브러리 WM_CONTEXTMENU 메시지를 처리 하 고 마우스 오른쪽 단추를 클릭할 때 응용 프로그램 도구 모음 및 도킹 창 목록에 있는 특수 한 상황에 맞는 메뉴를 표시 하도록 라이브러리를 알려 줍니다.|
|[CDockingManager::FindDockSite](#finddocksite)|검색 표시줄 창 지정된 된 위치에 있고 지정된 된 맞춤 형식을 포함 합니다.|
|[CDockingManager::FindDockSiteByPane](#finddocksitebypane)|막대를 반환 합니다. 대상 표시줄 창의 id가 있는 창입니다.|
|[CDockingManager::FindPaneByID](#findpanebyid)|지정 된 컨트롤 id 창을 찾습니다.|
|[CDockingManager::FixupVirtualRects](#fixupvirtualrects)|모든 현재 도구 모음 위치를 가상 사각형에 커밋합니다.|
|[CDockingManager::FrameFromPoint](#framefrompoint)|지정된 된 점을 포함 하는 프레임을 반환 합니다.|
|[CDockingManager::GetClientAreaBounds](#getclientareabounds)|클라이언트 영역의 범위를 포함 하는 사각형을 가져옵니다.|
|[CDockingManager::GetDockingMode](#getdockingmode)|현재 도킹 모드를 반환합니다.|
|[CDockingManager::GetDockSiteFrameWnd](#getdocksiteframewnd)|부모 창 프레임에 대 한 포인터를 가져옵니다.|
|[CDockingManager::GetEnabledAutoHideAlignment](#getenabledautohidealignment)|창 활성화 맞춤을 반환합니다.|
|[CDockingManager::GetMiniFrames](#getminiframes)|미니 컴퓨터의 목록을 가져옵니다.|
|[CDockingManager::GetOuterEdgeBounds](#getouteredgebounds)|프레임의 가장자리를 포함 하는 사각형을 가져옵니다.|
|[CDockingManager::GetPaneList](#getpanelist)|창 고 도킹 관리자에 속하는 목록을 반환 합니다. 모든 부동 창 포함 됩니다.|
|[CDockingManager::GetSmartDockingManager](#getsmartdockingmanager)|스마트 도킹 관리자에 대 한 포인터를 검색합니다.|
|[CDockingManager::GetSmartDockingManagerPermanent](#getsmartdockingmanagerpermanent)|스마트 도킹 관리자에 대 한 포인터를 검색합니다.|
|[CDockingManager::GetSmartDockingParams](#getsmartdockingparams)|도킹 관리자에 대 한 스마트 도킹 매개 변수를 반환 합니다.|
|[CDockingManager::GetSmartDockingTheme](#getsmartdockingtheme)|스마트 도킹 표식 표시 하는 데 사용 되는 테마를 반환 하는 정적 메서드.|
|[CDockingManager::HideAutoHidePanes](#hideautohidepanes)|자동 숨기기 모드에 있는 창을 숨깁니다.|
|[CDockingManager::InsertDockSite](#insertdocksite)|도킹 창을 만들고 컨트롤 막대 목록에 삽입 합니다.|
|[CDockingManager::InsertPane](#insertpane)|컨트롤 창의 컨트롤 막대 목록에 삽입합니다.|
|[CDockingManager::IsDockSiteMenu](#isdocksitemenu)|팝업 메뉴는 모든 창 캡션을에 표시할지 여부를 지정 합니다.|
|[CDockingManager::IsInAdjustLayout](#isinadjustlayout)|모든 창 레이아웃을 조정 하는 경우를 결정 합니다.|
|[CDockingManager::IsOLEContainerMode](#isolecontainermode)|OLE 컨테이너 모드 고 도킹 관리자 인지 여부를 지정 합니다.|
|[CDockingManager::IsPointNearDockSite](#ispointneardocksite)|도킹 사이트 근처에 지정된 된 지점 인지 여부를 결정 합니다.|
|[CDockingManager::IsPrintPreviewValid](#isprintpreviewvalid)|인쇄 미리 보기 모드가 설정 된 경우를 결정 합니다.|
|[CDockingManager::LoadState](#loadstate)|레지스트리에서 고 도킹 관리자의 상태를 로드합니다.|
|[CDockingManager::LockUpdate](#lockupdate)|지정된 된 창을 잠급니다.|
|[CDockingManager::OnActivateFrame](#onactivateframe)|프레임 창 활성화 또는 비활성화 될 때 프레임 워크에서 호출 됩니다.|
|[CDockingManager::OnClosePopupMenu](#onclosepopupmenu)|활성 팝업 메뉴에서 WM_DESTROY 메시지를 처리할 때 프레임워크에서 호출됩니다.|
|[CDockingManager::OnMoveMiniFrame](#onmoveminiframe)|미니 프레임 창을 이동 하기 위해 프레임 워크에서 호출 됩니다.|
|[CDockingManager::OnPaneContextMenu](#onpanecontextmenu)|창의 목록에 있는 메뉴를 빌드할 때 프레임 워크에서 호출 됩니다.|
|[CDockingManager::PaneFromPoint](#panefrompoint)|지정된 된 점을 포함 하는 창을 반환 합니다.|
|[CDockingManager::ProcessPaneContextMenuCommand](#processpanecontextmenucommand)|선택 또는 지정된 된 명령에 대 한 확인란의 선택을 취소 하 고 표시 된 창의 레이아웃을 다시 계산 하는 프레임 워크에서 호출 됩니다.|
|[CDockingManager::RecalcLayout](#recalclayout)|컨트롤의 목록에 있는 컨트롤의 내부 레이아웃을 다시 계산 됩니다.|
|[CDockingManager::ReleaseEmptyPaneContainers](#releaseemptypanecontainers)|빈 창 컨테이너를 해제합니다.|
|[CDockingManager::RemoveHiddenMDITabbedBar](#removehiddenmditabbedbar)|지정 된 숨겨진 창 막대를 제거 합니다.|
|[CDockingManager::RemoveMiniFrame](#removeminiframe)|미니 프레임 목록에서 지정된 된 프레임을 제거합니다.|
|[CDockingManager::RemovePaneFromDockManager](#removepanefromdockmanager)|창을 등록을 취소 하 고 도킹 관리자 목록에서 제거 합니다.|
|[CDockingManager::ReplacePane](#replacepane)|한 창을 다른 창으로 대체합니다.|
|[CDockingManager::ResortMiniFramesForZOrder](#resortminiframesforzorder)|미니 프레임 목록에서 프레임을 사용 합니다.|
|[CDockingManager::SaveState](#savestate)|레지스트리에 고 도킹 관리자의 상태를 저장합니다.|
|[CDockingManager::SendMessageToMiniFrames](#sendmessagetominiframes)|모든 미니 프레임에 지정된 된 메시지를 보냅니다.|
|[CDockingManager::Serialize](#serialize)|보관 하 고 도킹 관리자를 씁니다. ( [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize)를 재정의합니다.)|
|[CDockingManager::SetAutohideZOrder](#setautohidezorder)|크기, 너비 및 지정 된 창과 컨트롤 막대의 높이 설정합니다.|
|[CDockingManager::SetDockingMode](#setdockingmode)|도킹 모드를 설정합니다.|
|[CDockingManager::SetDockState](#setdockstate)|컨트롤 막대, 미니 프레임 및 자동 숨기기 막대의 도킹 상태를 설정 합니다.|
|[CDockingManager::SetPrintPreviewMode](#setprintpreviewmode)|인쇄 미리 보기에 표시 되는 막대의 인쇄 미리 보기 모드를 설정 합니다.|
|[CDockingManager::SetSmartDockingParams](#setsmartdockingparams)|스마트 도킹의 동작을 정의 하는 매개 변수를 설정 합니다.|
|[CDockingManager::ShowDelayShowMiniFrames](#showdelayshowminiframes)|표시 하거나 미니 프레임 창을 숨깁니다.|
|[CDockingManager::ShowPanes](#showpanes)|표시 하거나 제어 및 자동 숨기기 막대의 창을 숨깁니다.|
|[CDockingManager::StartSDocking](#startsdocking)|스마트 도킹 관리자의 맞춤에 따라 지정 된 창의 스마트 도킹을 시작 합니다.|
|[CDockingManager::StopSDocking](#stopsdocking)|중지 스마트 도킹 합니다.|

### <a name="data-members"></a>데이터 멤버

|이름|설명|
|----------|-----------------|
|[CDockingManager::m_bHideDockingBarsInContainerMode](#m_bhidedockingbarsincontainermode)|도킹 관리자 OLE 컨테이너 모드의 창을 숨깁니다 여부를 지정 합니다.|
|[CDockingManager::m_dockModeGlobal](#m_dockmodeglobal)|전역 도킹 모드를 지정합니다.|
|[CDockingManager::m_nDockSensitivity](#m_ndocksensitivity)|도킹 민감도 지정합니다.|
|[CDockingManager::m_nTimeOutBeforeDockingBarDock](#m_ntimeoutbeforedockingbardock)|도킹 창을 즉시 도킹 모드에 도킹 된 전에 시간을 밀리초 단위로 지정 합니다.|
|[CDockingManager::m_nTimeOutBeforeToolBarDock](#m_ntimeoutbeforetoolbardock)|주 프레임 창으로 도킹 도구 모음 전에 밀리초 단위로 시간을 지정 합니다.|

## <a name="remarks"></a>설명

주 프레임 창을 만들고이 클래스를 자동으로 초기화 합니다.

도킹 관리자 개체를 도킹 레이아웃에 있는 모든 창 목록 및 모든 목록을 보유 [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) 주 프레임 창에 속한 창에 있습니다.

합니다 `CDockingManager` 창을 찾는 데 사용할 수 있는 몇 가지 서비스를 구현 하는 클래스 또는 `CPaneFrameWnd` 창입니다. 일반적으로 호출 하지 않으면 이러한 서비스 직접 주 프레임 창 개체에 래핑되고 합니다. 자세한 내용은 [CPaneFrameWnd 클래스](../../mfc/reference/cpaneframewnd-class.md)합니다.

## <a name="customization-tips"></a>사용자 지정 팁

다음 팁을 적용할 `CDockingManager` 개체:

- [CDockingManager 클래스](../../mfc/reference/cdockingmanager-class.md) 이러한 도킹 모드를 지원 합니다.

  - `AFX_DOCK_TYPE::DT_IMMEDIATE`

  - `AFX_DOCK_TYPE::DT_STANDARD`

  - `AFX_DOCK_TYPE::DT_SMART`

  이러한 도킹 모드가 정의한 [CDockingManager::m_dockModeGlobal](#m_dockmodeglobal) 를 호출 하 여 설정 됩니다 [CDockingManager::SetDockingMode](#setdockingmode)합니다.

- 비 부동, 크기 조정이 불가능 창을 만들려는 경우 호출 된 [CDockingManager::AddPane](#addpane) 메서드. 이 메서드는 창의 레이아웃을 담당 하 고 도킹 관리자를 사용 하 여 창에 등록 합니다.

## <a name="example"></a>예제

다음 예제에서 다양 한 메서드를 사용 하는 방법에 설명 합니다 `CDockingManager` 구성 하는 클래스를 `CDockingManager` 개체입니다. 이 예제에서는 모든 도킹 창의 캡션에 팝업 메뉴를 열고 추가 단추를 표시 하는 방법 및 개체의 도킹 모드를 설정 하는 방법을 보여 줍니다. 이 코드 조각은의 일부인 합니다 [Visual Studio 데모 샘플](../../overview/visual-cpp-samples.md)합니다.

[!code-cpp[NVC_MFC_VisualStudioDemo#24](../../mfc/codesnippet/cpp/cdockingmanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층

[CObject](../../mfc/reference/cobject-class.md)

[CDockingManager](../../mfc/reference/cdockingmanager-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxDockingManager.h

##  <a name="adddocksite"></a>  CDockingManager::AddDockSite

도킹 창을 만들고 컨트롤 막대 목록에 추가 합니다.

```
BOOL AddDockSite(
    const AFX_DOCKSITE_INFO& info,
    CDockSite** ppDockBar = NULL);
```

### <a name="parameters"></a>매개 변수

*info*<br/>
[in] 포함 된 정보 구조에 대 한 참조를 도킹 창 맞춤 합니다.

*ppDockBar*<br/>
[out] 새 도킹 창에 대 한 포인터에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

도킹 창에 성공적으로 만들어진 경우 TRUE입니다. FALSE이 고, 그렇지 합니다.

##  <a name="addhiddenmditabbedbar"></a>  CDockingManager::AddHiddenMDITabbedBar

막대에 대 한 핸들을 추가 하는 숨겨진된 MDI 탭 창 막대 목록에는 창입니다.

```
void AddHiddenMDITabbedBar(CDockablePane* pBar);
```

### <a name="parameters"></a>매개 변수

*pBar*<br/>
[in] 막대에 대 한 포인터 창

##  <a name="addpane"></a>  CDockingManager::AddPane

창을 도킹 관리자에 등록합니다.

```
BOOL AddPane(
    CBasePane* pWnd,
    BOOL bTail = TRUE,
    BOOL bAutoHide = FALSE,
    BOOL bInsertForOuterEdge = FALSE);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
[out에서] 창 고 도킹 관리자에 추가 하려면를 지정 합니다.

*bTail*<br/>
[in] 도킹 관리자에 대 한 창 창의 목록 끝에 추가. 그렇지 않으면 FALSE입니다.

*bAutoHide*<br/>
[in] 내부용 으로만 사용 합니다. 항상 기본값 FALSE를 사용 합니다.

*bInsertForOuterEdge*<br/>
[in] 내부용 으로만 사용 합니다. 항상 기본값 FALSE를 사용 합니다.

### <a name="return-value"></a>반환 값

창 고 도킹 관리자; 성공적으로 등록 된 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

비 부동, 크기 조정이 불가능 창 고 도킹 관리자를 사용 하 여 등록 하려면이 메서드를 호출 합니다. 창에 등록 하지 않은 경우 나타나지 않습니다 올바르게 고 도킹 관리자 배치 되는 경우.

##  <a name="adjustdockinglayout"></a>  CDockingManager::AdjustDockingLayout

다시 계산 하 고 프레임 창에서 모든 창의 레이아웃을 조정 합니다.

```
virtual void AdjustDockingLayout(HDWP hdwp = NULL);
```

### <a name="parameters"></a>매개 변수

*hdwp*<br/>
[in] 지연 된 창 위치 구조를 지정합니다. 자세한 내용은 [Windows 데이터 형식](/windows/desktop/WinProg/windows-data-types)을 참조하세요.

### <a name="remarks"></a>설명

##  <a name="addminiframe"></a>  CDockingManager::AddMiniFrame

미니 프레임 목록에는 프레임을 추가합니다.

```
virtual BOOL AddMiniFrame(CPaneFrameWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
[in] 프레임 포인터입니다.

### <a name="return-value"></a>반환 값

미니 프레임 목록에 없는 프레임과 성공적으로 추가 된 경우 TRUE FALSE이 고, 그렇지 합니다.

##  <a name="adjustpaneframes"></a>  CDockingManager::AdjustPaneFrames

모든 창에 전송할 WM_NCCALCSIZE 메시지 및 `CPaneFrameWnd` windows.

```
virtual void AdjustPaneFrames();
```

### <a name="remarks"></a>설명

##  <a name="adjustrecttoclientarea"></a>  CDockingManager::AdjustRectToClientArea

사각형의 맞춤을 조정 합니다.

```
virtual BOOL AdjustRectToClientArea(
    CRect& rectResult,
    DWORD dwAlignment);
```

### <a name="parameters"></a>매개 변수

*rectResult*<br/>
[in] 에 대 한 참조를 `CRect` 개체

*dwAlignment*<br/>
[in] 맞춤을 `CRect` 개체

### <a name="return-value"></a>반환 값

TRUE 이면의 맞춤을 `CRect` 개체 조정 되었습니다. FALSE이 고, 그렇지 합니다.

### <a name="remarks"></a>설명

합니다 *dwAlignment* 매개 변수는 다음 값 중 하나일 수 있습니다.

- CBRS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

##  <a name="alignautohidepane"></a>  CDockingManager::AlignAutoHidePane

전체 너비를 걸리는 또는 둘러싸인 프레임의 클라이언트 영역 높이 도킹 사이트 도킹 창을 자동 숨기기 모드에서 크기를 조정 합니다.

```
void AlignAutoHidePane(
    CPaneDivider* pDefaultSlider,
    BOOL bIsVisible = TRUE);
```

### <a name="parameters"></a>매개 변수

*pDefaultSlider*<br/>
[in] 도킹 슬라이더 창입니다.

*bIsVisible*<br/>
[in] 도킹 창에 표시 되 면 TRUE입니다. FALSE이 고, 그렇지 합니다.

##  <a name="autohidepane"></a>  CDockingManager::AutoHidePane

자동 숨기기 도구 모음을 만듭니다.

```
CMFCAutoHideToolBar* AutoHidePane(
    CDockablePane* pBar,
    CMFCAutoHideToolBar* pCurrAutoHideToolBar = NULL);
```

### <a name="parameters"></a>매개 변수

*pBar*<br/>
[in] 모음에 대 한 포인터 창입니다.

*pCurrAutoHideToolBar*<br/>
[in] 자동 숨기기 도구 모음에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

자동 숨기기 도구 모음을 만들지 않은; 경우 NULL 그렇지 않으면 새 도구 모음에 대 한 포인터입니다.

##  <a name="bringbarstotop"></a>  CDockingManager::BringBarsToTop

지정된 된 맞춤 맨 위에 있는 도킹 된 막대를 제공 합니다.

```
void BringBarsToTop(
    DWORD dwAlignment = 0,
    BOOL bExcludeDockedBars = TRUE);
```

### <a name="parameters"></a>매개 변수

*dwAlignment*<br/>
[in] 다른 windows의 맨 위에 표시 되는 도킹 막대의 맞춤입니다.

*bExcludeDockedBars*<br/>
[in] 도킹 된 막대 위에;에서 제외. 그렇지 않으면 FALSE입니다.

##  <a name="buildpanesmenu"></a>  CDockingManager::BuildPanesMenu

도킹 창 및 도구 모음 이름 메뉴에 추가합니다.

```
void BuildPanesMenu(
    CMenu& menu,
    BOOL bToolbarsOnly);
```

### <a name="parameters"></a>매개 변수

*menu*<br/>
[in] 도킹 창 및 도구 모음을 이름을 추가 하려면 메뉴입니다.

*bToolbarsOnly*<br/>
[in] TRUE는 메뉴에만 도구 모음 이름을 추가 하려면 FALSE이 고, 그렇지 합니다.

##  <a name="calcexpecteddockedrect"></a>  CDockingManager::CalcExpectedDockedRect

도킹 된 창의 예상된 사각형을 계산합니다.

```
void CalcExpectedDockedRect(
    CWnd* pWnd,
    CPoint ptMouse,
    CRect& rectResult,
    BOOL& bDrawTab,
    CDockablePane** ppTargetBar);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
[in] 창 도킹에 대 한 포인터입니다.

*ptMouse*<br/>
[in] 마우스 위치입니다.

*rectResult*<br/>
[out] 계산 된 사각형입니다.

*bDrawTab*<br/>
[in] 탭; 그리기 true로 설정 하면 그렇지 않으면 FALSE입니다.

*ppTargetBar*<br/>
[out] 대상 창에 대 한 포인터에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드를 사용자 지정 된 지점에 창을 끌 경우 창이 차지 하는 사각형을 계산 *ptMouse* 있습니다 도킹 하 고 있습니다.

##  <a name="create"></a>  CDockingManager::Create

도킹 관리자를 만듭니다.

```
BOOL Create(CFrameWnd* pParentWnd);
```

### <a name="parameters"></a>매개 변수

*pParentWnd*<br/>
[in] 도킹 관리자의 부모 프레임 포인터입니다. 이 값에 NULL이 아니어야 합니다.

### <a name="return-value"></a>반환 값

항상 TRUE입니다.

##  <a name="determinepaneandstatus"></a>  CDockingManager::DeterminePaneAndStatus

지정된 된 지점 및 도킹 상태를 포함 하는 창을 확인 합니다.

```
virtual AFX_CS_STATUS DeterminePaneAndStatus(
    CPoint pt,
    int nSensitivity,
    DWORD dwEnabledAlignment,
    CBasePane** ppTargetBar,
    const CBasePane* pBarToIgnore,
    const CBasePane* pBarToDock);
```

### <a name="parameters"></a>매개 변수

*pt*<br/>
[in] 검사할 창의 위치입니다.

*nSensitivity*<br/>
[in] 각 선택 창의 창 사각형을 증가 값입니다. 지정 된 점이이 향상 된 지역의 경우 검색 조건을 충족 하는 창입니다.

*dwEnabledAlignment*<br/>
[in] 맞춤 도킹 창입니다.

*ppTargetBar*<br/>
[out] 대상 창에 대 한 포인터에 대 한 포인터입니다.

*pBarToIgnore*<br/>
[in] 메서드를 무시 하는 창입니다.

*pBarToDock*<br/>
[in] 도킹 된 창입니다.

### <a name="return-value"></a>반환 값

도킹 상태입니다.

### <a name="remarks"></a>설명

도킹 상태는 다음 값 중 하나일 수 있습니다.

|AFX_CS_STATUS value|의미|
|---------------------------|-------------|
|CS_NOTHING|포인터는 도킹 사이트를 통해 없습니다. 따라서 창 유지할 부동 합니다.|
|CS_DOCK_IMMEDIATELY|포인터가 직접 실행 모드에서 도킹 사이트에 있는 (DT_IMMEDIATE 스타일 사용), 있도록 창에 즉시 도킹 해야 합니다.|
|CS_DELAY_DOCK|포인터가 있는 다른 도킹 창을 주 프레임의에 지가 또는 도킹 사이트입니다.|
|CS_DELAY_DOCK_TO_TAB|포인터가 있는 탭된 창에 도킹할 창이 도킹 사이트입니다. 이 탭 창의 탭 영역을 위 또는 다른 도킹 창의 캡션을 위에 마우스가 있을 때 발생 합니다.|

##  <a name="disablerestoredockstate"></a>  CDockingManager::DisableRestoreDockState

사용 하거나 레지스트리에서 도킹 레이아웃의 로드를 사용 하지 않도록 설정 합니다.

```
void DisableRestoreDockState(BOOL bDisable = TRUE);
```

### <a name="parameters"></a>매개 변수

*bDisable*<br/>
[in] 레지스트리에서; 도킹 레이아웃을 사용 하지 않도록 설정 로드 하려면 true로 설정 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

응용 프로그램 상태를 로드 하는 경우 현재 레이아웃 도킹 창 및 도구 모음을 유지 해야 하는 경우이 메서드를 호출 합니다.

##  <a name="dockpane"></a>  CDockingManager::DockPane

창을 다른 창 또는 프레임 창에 도킹합니다.

```
void DockPane(
    CBasePane* pBar,
    UINT nDockBarID = 0,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>매개 변수

*pBar*<br/>
[in] 막대에 대 한 포인터를 창에 도킹 합니다.

*nDockBarID*<br/>
[in] 도킹 모음의 id입니다.

*lpRect*<br/>
[in] 대상 사각형입니다.

##  <a name="dockpaneleftof"></a>  CDockingManager::DockPaneLeftOf

창을 다른 창의 왼쪽에 도킹합니다.

```
BOOL DockPaneLeftOf(
    CPane* pBarToDock,
    CPane* pTargetBar);
```

### <a name="parameters"></a>매개 변수

*pBarToDock*<br/>
[in] 왼쪽에 도킹 창에 대 한 포인터 *pTargetBar*합니다.

*pTargetBar*<br/>
[in] 대상 창에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

창에 성공적으로 도킹 된 경우 TRUE 그렇지 않으면 FALSE입니다.

##  <a name="enableautohidepanes"></a>  CDockingManager::EnableAutoHidePanes

주 프레임 창의 도킹을 사용 하도록 설정 하 고가 도킹 창을 만들고 컨트롤 막대 목록에 추가 합니다.

```
BOOL EnableAutoHidePanes(DWORD dwStyle);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
[in] 도킹 맞춤입니다.

### <a name="return-value"></a>반환 값

도킹 창에 성공적으로 만들어진 경우 TRUE입니다. FALSE이 고, 그렇지 합니다.

##  <a name="enabledocking"></a>  CDockingManager::EnableDocking

도킹 창을 만들고를 주 프레임 창의 도킹을 사용 하도록 설정 합니다.

```
BOOL EnableDocking(DWORD dwStyle);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
[in] 도킹 맞춤입니다.

### <a name="return-value"></a>반환 값

도킹 창에 성공적으로 만들어진 경우 TRUE입니다. FALSE이 고, 그렇지 합니다.

##  <a name="enabledocksitemenu"></a>  CDockingManager::EnableDockSiteMenu

모든 도킹 창의 캡션에 팝업 메뉴를 열고 추가 단추를 표시 합니다.

```
static void EnableDockSiteMenu(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
[in] 도킹 사이트 메뉴;를 사용 하도록 설정. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

도킹 사이트 메뉴 창의 도킹 상태를 변경 하는 것에 대 한 다음 옵션이 표시 됩니다.

- `Floating` -창을 부동합니다.

- `Docking` -창을 주 프레임 창에 마지막으로 도킹 위치를 위치에 도킹 합니다.

- `AutoHide` -창 자동 숨기기 모드로 전환

- `Hide` -창을 숨깁니다.

이 메뉴는 기본적으로 표시 되지 않습니다.

##  <a name="enablepanecontextmenu"></a>  CDockingManager::EnablePaneContextMenu

라이브러리 WM_CONTEXTMENU 메시지를 처리 하 고 마우스 오른쪽 단추를 클릭할 때 응용 프로그램 도구 모음 및 도킹 창 목록에 있는 특수 한 상황에 맞는 메뉴를 표시 하도록 라이브러리를 알려 줍니다.

```
void EnablePaneContextMenu(
    BOOL bEnable,
    UINT uiCustomizeCmd,
    const CString& strCustomizeText,
    BOOL bToolbarsOnly = FALSE);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
[in] True 이면 라이브러리 자동 상황에 맞는 메뉴에 대 한 지원 설정 FALSE 이면 라이브러리 자동 상황에 맞는 메뉴에 대 한 지원을 해제 합니다.

*uiCustomizeCmd*<br/>
[in] 에 대 한 명령 id를 **사용자 지정** 메뉴의 항목입니다.

*strCustomizeText*<br/>
[in] 텍스트를 **사용자 지정** 항목입니다.

*bToolbarsOnly*<br/>
[in] True 이면 메뉴만 목록을 표시 응용 프로그램 도구 모음입니다. FALSE 인 경우 라이브러리는이 목록에 도킹 창 응용 프로그램을 추가 합니다.

##  <a name="finddocksite"></a>  CDockingManager::FindDockSite

검색 표시줄 창 지정된 된 위치에 있고 지정된 된 맞춤 형식을 포함 합니다.

```
virtual CDockSite* FindDockSite(
    DWORD dwAlignment,
    BOOL bOuter);
```

### <a name="parameters"></a>매개 변수

*dwAlignment*<br/>
[in] 막대의 맞춤 창입니다.

*bOuter*<br/>
[in] TRUE 이면 컨트롤 막대 목록에서 헤드 위치에서 가로 막대를 검색 합니다. 그렇지 않으면 컨트롤 막대 목록에서 비상 위치에서 가로 막대를 검색 합니다.

### <a name="return-value"></a>반환 값

지정된 된 맞춤 형식을;에 있는 도킹 창 그렇지 않으면 NULL입니다.

##  <a name="findpanebyid"></a>  CDockingManager::FindPaneByID

지정 된 컨트롤 id 창을 찾습니다.

```
virtual CBasePane* FindPaneByID(
    UINT uBarID,
    BOOL bSearchMiniFrames = FALSE);
```

### <a name="parameters"></a>매개 변수

*uBarID*<br/>
[in] 검색할 창의 컨트롤 ID를 지정 합니다.

*bSearchMiniFrames*<br/>
[in] 모든 부동 창 검색에 포함 하려면 TRUE입니다. 도킹 된 창에만 포함 하려면 FALSE입니다.

### <a name="return-value"></a>반환 값

합니다 [CBasePane](../../mfc/reference/cbasepane-class.md) 지정한 창을 찾을 수 없는 경우 지정된 된 컨트롤 ID 또는 NULL을 가진 개체입니다.

### <a name="remarks"></a>설명

##  <a name="finddocksitebypane"></a>  CDockingManager::FindDockSiteByPane

막대를 반환 합니다. 대상 표시줄 창의 id가 있는 창입니다.

```
virtual CDockSite* FindDockSiteByPane(CPane* pTargetBar);
```

### <a name="parameters"></a>매개 변수

*pTargetBar*<br/>
[in] 대상 표시줄 창에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

막대 대상 표시줄 창의; id가 있는 창 없으면 NULL 창 가로 막대형 같은 존재 합니다.

##  <a name="fixupvirtualrects"></a>  CDockingManager::FixupVirtualRects

모든 현재 도구 모음 위치를 가상 사각형에 커밋합니다.

```
virtual void FixupVirtualRects();
```

### <a name="remarks"></a>설명

사용자 도구 모음을 끌기 시작 되 면 응용 프로그램은에서 원래 위치를 기억 하는 *가상 사각형*합니다. 도킹 사이트에서 도구 모음을 이동 하면 도구 모음 다른 도구 모음을 이동할 수도 있습니다. 다른 도구 모음 원래 위치를 해당 가상 사각형에 저장 됩니다.

##  <a name="framefrompoint"></a>  CDockingManager::FrameFromPoint

지정된 된 점을 포함 하는 프레임을 반환 합니다.

```
virtual CPaneFrameWnd* FrameFromPoint(
    CPoint pt,
    CPaneFrameWnd* pFrameToExclude,
    BOOL bFloatMultiOnly) const;
```

### <a name="parameters"></a>매개 변수

*pt*<br/>
[in] 확인 화면 좌표에서 지점에 지정 합니다.

*pFrameToExclude*<br/>
[in] 제외할 프레임 포인터입니다.

*bFloatMultiOnly*<br/>
[in] 인스턴스는 제외 프레임 true로 설정 하면 `CMultiPaneFrameWnd`; FALSE이 고, 그렇지 합니다.

### <a name="return-value"></a>반환 값

지정된 된 점을; 포함 된 프레임 그렇지 않으면 NULL입니다.

##  <a name="getclientareabounds"></a>  CDockingManager::GetClientAreaBounds

클라이언트 영역의 범위를 포함 하는 사각형을 가져옵니다.

```
CRect GetClientAreaBounds() const;

void GetClientAreaBounds(CRect& rcClient);
```

### <a name="parameters"></a>매개 변수

*rcClient*<br/>
[out] 클라이언트 영역의 범위를 포함 하는 사각형에 대 한 참조입니다.

### <a name="return-value"></a>반환 값

클라이언트 영역의 범위를 포함 하는 사각형입니다.

##  <a name="getdockingmode"></a>  CDockingManager::GetDockingMode

현재 도킹 모드를 반환합니다.

```
static AFX_DOCK_TYPE GetDockingMode();
```

### <a name="return-value"></a>반환 값

현재 도킹 모드를 나타내는 열거자 값입니다. 다음 값 중 하나일 수 있습니다.

- DT_STANDARD

- DT_IMMEDIATE

- DT_SMART

### <a name="remarks"></a>설명

도킹 모드를 설정 하려면 호출 [CDockingManager::SetDockingMode](#setdockingmode)합니다.

##  <a name="getdocksiteframewnd"></a>  CDockingManager::GetDockSiteFrameWnd

부모 창 프레임에 대 한 포인터를 가져옵니다.

```
CFrameWnd* GetDockSiteFrameWnd() const;
```

### <a name="return-value"></a>반환 값

부모 창 프레임에 대 한 포인터입니다.

##  <a name="getenabledautohidealignment"></a>  CDockingManager::GetEnabledAutoHideAlignment

창 활성화 맞춤을 반환합니다.

```
DWORD GetEnabledAutoHideAlignment() const;
```

### <a name="return-value"></a>반환 값

자동 숨기기 창을 사용할 수 없는 경우 0 CBRS_ALIGN_ 플래그의 비트 조합입니다. 자세한 내용은 [CFrameWnd::EnableDocking](../../mfc/reference/cframewnd-class.md#enabledocking)합니다.

### <a name="remarks"></a>설명

메서드 자동 숨기기 컨트롤 막대에 설정 된 맞춤을 반환합니다. 자동 숨기기 막대를 사용 하도록 설정 하려면 호출 [CFrameWndEx::EnableAutoHidePanes](../../mfc/reference/cframewndex-class.md#enableautohidepanes)합니다.

##  <a name="getminiframes"></a>  CDockingManager::GetMiniFrames

미니 컴퓨터의 목록을 가져옵니다.

```
const CObList& GetMiniFrames() const;
```

### <a name="return-value"></a>반환 값

목록 고 도킹 관리자에 속하는 컨트롤 막대를 포함 하는 미니 컴퓨터입니다.

##  <a name="getouteredgebounds"></a>  CDockingManager::GetOuterEdgeBounds

프레임의 가장자리를 포함 하는 사각형을 가져옵니다.

```
CRect GetOuterEdgeBounds() const;
```

### <a name="return-value"></a>반환 값

프레임의 가장자리를 포함 하는 사각형입니다.

##  <a name="getpanelist"></a>  CDockingManager::GetPaneList

창 고 도킹 관리자에 속하는 목록을 반환 합니다. 모든 부동 창 포함 됩니다.

```
void GetPaneList(
    CObList& lstBars,
    BOOL bIncludeAutohide = FALSE,
    CRuntimeClass* pRTCFilter = NULL,
    BOOL bIncludeTabs = FALSE);
```

### <a name="parameters"></a>매개 변수

*lstBars*<br/>
[out에서] 현재 도킹 관리자의 모든 창에 포함 되어 있습니다.

*bIncludeAutohide*<br/>
[in] 창 자동 숨기기 모드에 있는 포함. 그렇지 않으면 FALSE입니다.

*pRTCFilter*<br/>
[in] NULL이 아닌 경우 반환된 된 목록에 지정 된 런타임 클래스의만 창이 있습니다.

*bIncludeTabs*<br/>
[in] True 이면 포함 탭이 있습니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

도킹 관리자에서 모든 탭된 창이 없으면 반환에 대 한 포인터 [CBaseTabbedPane 클래스](../../mfc/reference/cbasetabbedpane-class.md) 개체 탭을 명시적으로 열거 해야 합니다.

사용 하 여 *pRTCFilter* 창의 특정 클래스를 가져오려고 합니다. 예를 들어이 값을 적절 하 게 설정 하 여 도구 모음만 가져올 수 있습니다.

##  <a name="getsmartdockingmanager"></a>  CDockingManager::GetSmartDockingManager

스마트 도킹 관리자에 대 한 포인터를 검색합니다.

```
CSmartDockingManager* GetSmartDockingManager();
```

### <a name="return-value"></a>반환 값

스마트 도킹 관리자에 대 한 포인터입니다.

##  <a name="getsmartdockingmanagerpermanent"></a>  CDockingManager::GetSmartDockingManagerPermanent

스마트 도킹 관리자에 대 한 포인터를 검색합니다.

```
CSmartDockingManager* GetSmartDockingManagerPermanent() const;
```

### <a name="return-value"></a>반환 값

스마트 도킹 관리자에 대 한 포인터입니다.

##  <a name="getsmartdockingparams"></a>  CDockingManager::GetSmartDockingParams

도킹 관리자에 대 한 스마트 도킹 매개 변수를 반환 합니다.

```
static CSmartDockingInfo& GetSmartDockingParams();
```

### <a name="return-value"></a>반환 값

현재 도킹 관리자에 대 한 스마트 도킹 매개 변수를 포함 하는 클래스입니다. 자세한 내용은 [CSmartDockingInfo 클래스](../../mfc/reference/csmartdockinginfo-class.md)합니다.

### <a name="remarks"></a>설명

##  <a name="hideautohidepanes"></a>  CDockingManager::HideAutoHidePanes

자동 숨기기 모드에 있는 창을 숨깁니다.

```
void HideAutoHidePanes(
    CDockablePane* pBarToExclude = NULL,
    BOOL bImmediately = FALSE);
```

### <a name="parameters"></a>매개 변수

*pBarToExclude*<br/>
[in] 숨기기에서 제외할 막대에 대 한 포인터입니다.

*bImmediately*<br/>
[in] 즉시; 창을 숨기려면 TRUE 자동 숨기기 효과 사용 하 여 창을 숨기려면 FALSE입니다.

##  <a name="insertdocksite"></a>  CDockingManager::InsertDockSite

도킹 창을 만들고 컨트롤 막대 목록에 삽입 합니다.

```
BOOL InsertDockSite(
    const AFX_DOCKSITE_INFO& info,
    DWORD dwAlignToInsertAfter,
    CDockSite** ppDockBar = NULL);
```

### <a name="parameters"></a>매개 변수

*info*<br/>
[in] 도킹 창에 대 한 맞춤 정보를 포함 하는 구조체입니다.

*dwAlignToInsertAfter*<br/>
[in] 도킹 창의 맞춤입니다.

*ppDockBar*<br/>
[out] 도킹 창에 대 한 포인터에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

도킹 창에 성공적으로 만들어진 경우 TRUE입니다. FALSE이 고, 그렇지 합니다.

##  <a name="insertpane"></a>  CDockingManager::InsertPane

컨트롤 창의 컨트롤 막대 목록에 삽입합니다.

```
BOOL InsertPane(
    CBasePane* pControlBar,
    CBasePane* pTarget,
    BOOL bAfter = TRUE);
```

### <a name="parameters"></a>매개 변수

*pControlBar*<br/>
[in] 제어 창에 대 한 포인터입니다.

*pTarget*<br/>
[in] 대상 창에 대 한 포인터입니다.

*bAfter*<br/>
[in] True 이면 삽입의 대상 창; 위치 후 창 FALSE이 고, 그렇지 합니다.

### <a name="return-value"></a>반환 값

컨트롤 창의 컨트롤 막대 목록에 성공적으로 추가 되 면 TRUE입니다. FALSE이 고, 그렇지 합니다.

### <a name="remarks"></a>설명

컨트롤 막대 목록에 없으면 대상 창 또는 컨트롤 창 컨트롤 막대 목록에 이미 있으면이 메서드는 false를 반환 합니다.

##  <a name="isdocksitemenu"></a>  CDockingManager::IsDockSiteMenu

팝업 메뉴는 모든 창 캡션을에 표시할지 여부를 지정 합니다.

```
static BOOL IsDockSiteMenu();
```

### <a name="return-value"></a>반환 값

도킹 사이트 메뉴 캡션 모든 도킹 창의;에 표시 되 면 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

도킹 사이트 메뉴를 호출 하 여 설정할 수 있습니다 [CDockingManager::EnableDockSiteMenu](#enabledocksitemenu)합니다.

##  <a name="isinadjustlayout"></a>  CDockingManager::IsInAdjustLayout

모든 창 레이아웃을 조정 하는 경우를 결정 합니다.

```
BOOL IsInAdjustLayout() const;
```

### <a name="return-value"></a>반환 값

TRUE 이면 모든 창의 레이아웃 조정 됩니다. FALSE이 고, 그렇지 합니다.

##  <a name="isolecontainermode"></a>  CDockingManager::IsOLEContainerMode

OLE 컨테이너 모드 고 도킹 관리자 인지 여부를 지정 합니다.

```
BOOL IsOLEContainerMode() const;
```

### <a name="return-value"></a>반환 값

도킹 관리자 OLE 컨테이너 모드에 있으면 TRUE 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

OLE 컨테이너 모드에서는 모든 도킹 창 및 응용 프로그램 도구 모음이 숨겨져 있습니다. 창 에서도 숨길지이 모드로 설정한 경우 [CDockingManager::m_bHideDockingBarsInContainerMode](#m_bhidedockingbarsincontainermode) TRUE로 합니다.

##  <a name="ispointneardocksite"></a>  CDockingManager::IsPointNearDockSite

도킹 사이트 근처에 지정된 된 지점 인지 여부를 결정 합니다.

```
BOOL IsPointNearDockSite(
    CPoint point,
    DWORD& dwBarAlignment,
    BOOL& bOuterEdge) const;
```

### <a name="parameters"></a>매개 변수

*point*<br/>
[in] 지정 된 지점입니다.

*dwBarAlignment*<br/>
[out] 요점은 가까운 가장자리를 지정 합니다. 가능한 값은 CBRS_ALIGN_LEFT, CBRS_ALIGN_RIGHT, CBRS_ALIGN_TOP, CBRS_ALIGN_BOTTOM입니다.

*bOuterEdge*<br/>
[out] TRUE 이면 포인터가 거의 도킹 사이트;의 바깥쪽 테두리 FALSE이 고, 그렇지 합니다.

### <a name="return-value"></a>반환 값

도킹 사이트; 가까운 지점이 있으면 TRUE입니다. 그렇지 않으면 FALSE입니다.

##  <a name="isprintpreviewvalid"></a>  CDockingManager::IsPrintPreviewValid

인쇄 미리 보기 모드가 설정 된 경우를 결정 합니다.

```
BOOL IsPrintPreviewValid() const;
```

### <a name="return-value"></a>반환 값

TRUE 이면 인쇄 미리 보기 모드를 설정 됩니다. FALSE이 고, 그렇지 합니다.

##  <a name="loadstate"></a>  CDockingManager::LoadState

레지스트리에서 고 도킹 관리자의 상태를 로드합니다.

```
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>매개 변수

*lpszProfileName*<br/>
[in] 프로필 이름입니다.

*uiID*<br/>
[in] 도킹 관리자의 id입니다.

### <a name="return-value"></a>반환 값

도킹 관리자 상태를 성공적으로 로드 된 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

##  <a name="lockupdate"></a>  CDockingManager::LockUpdate

지정된 된 창을 잠급니다.

```
void LockUpdate(BOOL bLock);
```

### <a name="parameters"></a>매개 변수

*bLock*<br/>
[in] 창 잠 겼으 면 TRUE FALSE이 고, 그렇지 합니다.

### <a name="remarks"></a>설명

창 잠긴 경우 이동할 수 없습니다 하 고 다시 그릴 수 없습니다.

##  <a name="m_bhidedockingbarsincontainermode"></a>  CDockingManager::m_bHideDockingBarsInContainerMode

도킹 관리자 OLE 컨테이너 모드의 창을 숨깁니다 여부를 지정 합니다.

```
AFX_IMPORT_DATA static BOOL m_bHideDockingBarsInContainerMode;
```

### <a name="remarks"></a>설명

응용 프로그램이 OLE 컨테이너 모드에 있을 때 표시 되는 주 프레임에 도킹 된 창을 모두 유지 하려는 경우이 값을 FALSE로 설정 합니다. 기본적으로이 값은 TRUE입니다.

##  <a name="m_dockmodeglobal"></a>  CDockingManager::m_dockModeGlobal

전역 도킹 모드를 지정합니다.

```
AFX_IMPORT_DATA static AFX_DOCK_TYPE m_dockModeGlobal;
```

### <a name="remarks"></a>설명

기본적으로 각 도킹 창 도킹이 모드를 사용 합니다. 이 필드를 설정할 수 있는 값에 대 한 자세한 내용은 참조 하세요. [cbasepane:: Getdockingmode](../../mfc/reference/cbasepane-class.md#getdockingmode)합니다.

##  <a name="m_ndocksensitivity"></a>  CDockingManager::m_nDockSensitivity

도킹 민감도 지정합니다.

```
AFX_IMPORT_DATA static int m_nDockSensitivity;
```

### <a name="remarks"></a>설명

도킹 민감도 얼마나 근접 부동 정의 도킹 상태를 변경 하는 프레임 워크 전에 창 도킹 창, 도킹 사이트 또는 다른 창을 높일 수 있습니다.

##  <a name="m_ntimeoutbeforedockingbardock"></a>  CDockingManager::m_nTimeOutBeforeDockingBarDock

도킹 창을 즉시 도킹 모드에 도킹 된 전에 시간을 밀리초 단위로 지정 합니다.

```
static UINT m_nTimeOutBeforeDockingBarDock;
```

### <a name="remarks"></a>설명

창이 도킹 되어 전에 프레임 워크를 지정 된 기간 동안 대기 합니다. 이 창에서 실수로 사용자가 끌고 계속 하는 동안 위치에 도킹 되 방지 합니다.

##  <a name="m_ntimeoutbeforetoolbardock"></a>  CDockingManager::m_nTimeOutBeforeToolBarDock

주 프레임 창으로 도킹 도구 모음 전에 밀리초 단위로 시간을 지정 합니다.

```
static UINT m_nTimeOutBeforeToolBarDock;
```

### <a name="remarks"></a>설명

도구 모음을 도킹 하려면 먼저 프레임 워크는 지정 된 기간 동안 대기 합니다. 이렇게 하면 도구 모음을에서 실수로 사용자가 끌고 계속 하는 동안 위치에 도킹 되지 않습니다.

##  <a name="onactivateframe"></a>  CDockingManager::OnActivateFrame

프레임 창 활성화 또는 비활성화 될 때 프레임 워크에서 호출 됩니다.

```
virtual void OnActivateFrame(BOOL bActivate);
```

### <a name="parameters"></a>매개 변수

*bActivate*<br/>
[in] True 이면 프레임 창에서 활성; 이루어집니다. FALSE 인 경우에 프레임 창이 비활성화 됩니다.

##  <a name="onclosepopupmenu"></a>  CDockingManager::OnClosePopupMenu

활성 팝업 메뉴에서 WM_DESTROY 메시지를 처리할 때 프레임워크에서 호출됩니다.

```
void OnClosePopupMenu();
```

### <a name="remarks"></a>설명

현재 주 창을 닫 히 려는 경우 프레임 워크에서 WM_DESTROY 메시지를 보냅니다. 알림을 처리 하려면이 메서드를 재정의 `CMFCPopupMenu` 프레임 창에 속하는 개체 때는 `CMFCPopupMenu` WM_DESTROY 메시지를 처리 하는 개체입니다.

##  <a name="onmoveminiframe"></a>  CDockingManager::OnMoveMiniFrame

미니 프레임 창을 이동 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```

### <a name="parameters"></a>매개 변수

*pFrame*<br/>
[in] 미니 프레임 창에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 TRUE입니다. 그렇지 않으면 FALSE입니다.

##  <a name="onpanecontextmenu"></a>  CDockingManager::OnPaneContextMenu

창의 목록에 있는 메뉴를 빌드할 때 프레임 워크에서 호출 됩니다.

```
void OnPaneContextMenu(CPoint point);
```

### <a name="parameters"></a>매개 변수

*point*<br/>
[in] 메뉴의 위치를 지정 합니다.

##  <a name="panefrompoint"></a>  CDockingManager::PaneFromPoint

지정된 된 점을 포함 하는 창을 반환 합니다.

```
virtual CBasePane* PaneFromPoint(
    CPoint point,
    int nSensitivity,
    bool bExactBar = false,
    CRuntimeClass* pRTCBarType = NULL,
    BOOL bCheckVisibility = FALSE,
    const CBasePane* pBarToIgnore = NULL) const;

virtual CBasePane* PaneFromPoint(
    CPoint point,
    int nSensitivity,
    DWORD& dwAlignment,
    CRuntimeClass* pRTCBarType = NULL,
    const CBasePane* pBarToIgnore = NULL) const;
```

### <a name="parameters"></a>매개 변수

*point*<br/>
[in] 확인 화면 좌표에서 지점에 지정 합니다.

*nSensitivity*<br/>
[in] 각 선택 창의 창 사각형을 확장 값입니다. 지정 된 점이이 높을 지역의 경우 검색 조건을 충족 하는 창입니다.

*bExactBar*<br/>
[in] 무시 하려면 TRUE를 *nSensitivity* 매개 변수, 그렇지 않으면 FALSE입니다.

*pRTCBarType*<br/>
[in] NULL이 아닌 경우 메서드는 지정 된 형식의 창만 검색 합니다.

*bCheckVisibility*<br/>
[in] 확인 표시만 창; true로 설정 하면 그렇지 않으면 FALSE입니다.

*dwAlignment*<br/>
[out] 창이 지정된 된 지점에 있으면이 매개 변수는 지정된 된 위치에 가장 가까운 창 옆쪽에 포함 합니다. 자세한 내용은 설명 섹션을 참조하세요.

*pBarToIgnore*<br/>
[in] NULL이 아닌 경우이 매개 변수로 지정 된 창 무시 합니다.

### <a name="return-value"></a>반환 값

합니다 [CBasePane](../../mfc/reference/cbasepane-class.md)-찾을 수 없는 창 하는 경우 지정 된 지점 또는 NULL을 포함 하는 파생 된 개체입니다.

### <a name="remarks"></a>설명

함수를 반환 하 고 창의 찾을 때 *dwAlignment* 지정 된 요소의 맞춤을 포함 합니다. 예를 들어, 창의 위쪽에 가장 가까운 점 되었으면 *dwAlignment* CBRS_ALIGN_TOP로 설정 됩니다.

##  <a name="processpanecontextmenucommand"></a>  CDockingManager::ProcessPaneContextMenuCommand

선택 또는 지정된 된 명령에 대 한 확인란의 선택을 취소 하 고 표시 된 창의 레이아웃을 다시 계산 하는 프레임 워크에서 호출 됩니다.

```
BOOL ProcessPaneContextMenuCommand(
    UINT nID,
    int nCode,
    void* pExtra,
    AFX_CMDHANDLERINFO* pHandlerInfo);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
[in] 메뉴에서 컨트롤 막대의 id입니다.

*nCode*<br/>
[in] 명령 알림 코드입니다.

*pExtra*<br/>
[in] void에 대 한 포인터에 대 한 포인터로 캐스팅 되 `CCmdUI` 하는 경우 *nCode* CN_UPDATE_COMMAND_UI 됩니다.

*pHandlerInfo*<br/>
[in] 정보 구조에 대 한 포인터입니다. 이 매개 변수는 사용되지 않습니다.

### <a name="return-value"></a>반환 값

TRUE 이면 *pEXtra* NULL이 아닌 및 *nCode* CN_UPDATE_COMMAND_UI, 같음 경우 지정 된 컨트롤 막대 *nID*합니다.

##  <a name="recalclayout"></a>  CDockingManager::RecalcLayout

컨트롤의 목록에 있는 컨트롤의 내부 레이아웃을 다시 계산 됩니다.

```
virtual void RecalcLayout(BOOL bNotify = TRUE);
```

### <a name="parameters"></a>매개 변수

*bNotify*<br/>
[in] 이 매개 변수 사용 되지 않습니다.

##  <a name="releaseemptypanecontainers"></a>  CDockingManager::ReleaseEmptyPaneContainers

빈 창 컨테이너를 해제합니다.

```
void ReleaseEmptyPaneContainers();
```

##  <a name="removehiddenmditabbedbar"></a>  CDockingManager::RemoveHiddenMDITabbedBar

지정 된 숨겨진 창 막대를 제거 합니다.

```
void RemoveHiddenMDITabbedBar(CDockablePane* pBar);
```

### <a name="parameters"></a>매개 변수

*pBar*<br/>
[in] 막대에 대 한 포인터를 제거 하는 창입니다.

##  <a name="removeminiframe"></a>  CDockingManager::RemoveMiniFrame

미니 프레임 목록에서 지정된 된 프레임을 제거합니다.

```
virtual BOOL RemoveMiniFrame(CPaneFrameWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
[in] 제거할 프레임 포인터입니다.

### <a name="return-value"></a>반환 값

지정된 된 프레임이 제거 하는 경우 TRUE입니다. FALSE이 고, 그렇지 합니다.

##  <a name="removepanefromdockmanager"></a>  CDockingManager::RemovePaneFromDockManager

창을 등록을 취소 하 고 도킹 관리자 목록에서 제거 합니다.

```
void RemovePaneFromDockManager(
    CBasePane* pWnd,
    BOOL bDestroy,
    BOOL bAdjustLayout,
    BOOL bAutoHide = FALSE,
    CBasePane* pBarReplacement = NULL);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
[in] 제거할 창에 대 한 포인터입니다.

*bDestroy*<br/>
[in] TRUE 이면 제거 창 소멸 됩니다.

*bAdjustLayout*<br/>
[in] TRUE 이면 즉시 도킹 레이아웃을 조정 합니다.

*bAutoHide*<br/>
[in] True 이면 창 자동 숨기기 막대의 목록에서 제거 됩니다. FALSE 이면 창 일반 창의 목록에서 제거 됩니다.

*pBarReplacement*<br/>
[in] 제거 창을 대체 하는 창에 대 한 포인터입니다.

##  <a name="replacepane"></a>  CDockingManager::ReplacePane

한 창을 다른 창으로 대체합니다.

```
BOOL ReplacePane(
    CDockablePane* pOriginalBar,
    CDockablePane* pNewBar);
```

### <a name="parameters"></a>매개 변수

*pOriginalBar*<br/>
[in] 원래 창에 대 한 포인터입니다.

*pNewBar*<br/>
[in] 원래 창을 대체 하는 창에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

TRUE 이면 창 성공적으로 바뀝니다. FALSE이 고, 그렇지 합니다.

##  <a name="resortminiframesforzorder"></a>  CDockingManager::ResortMiniFramesForZOrder

미니 프레임 목록에서 프레임을 사용 합니다.

```
void ResortMiniFramesForZOrder();
```

##  <a name="savestate"></a>  CDockingManager::SaveState

레지스트리에 고 도킹 관리자의 상태를 저장합니다.

```
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>매개 변수

*lpszProfileName*<br/>
[in] 레지스트리 키 경로입니다.

*uiID*<br/>
[in] 도킹 관리자 id입니다.

### <a name="return-value"></a>반환 값

TRUE 이면 상태 저장 했습니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

레지스트리에 고 도킹 관리자의 상태 저장 컨트롤 막대의 상태, 자동 숨기기 막대의 상태 및 도킹 관리자에 있는 미니 프레임의 상태를 저장 하는 것입니다.

##  <a name="sendmessagetominiframes"></a>  CDockingManager::SendMessageToMiniFrames

모든 미니 프레임에 지정된 된 메시지를 보냅니다.

```
BOOL SendMessageToMiniFrames(
    UINT uMessage,
    WPARAM wParam = 0,
    LPARAM lParam = 0);
```

### <a name="parameters"></a>매개 변수

*uMessage*<br/>
[in] 메시지를 보냅니다.

*wParam*<br/>
[in] 추가 메시지 종속 정보입니다.

*lParam*<br/>
[in] 추가 메시지 종속 정보입니다.

### <a name="return-value"></a>반환 값

항상 TRUE입니다.

##  <a name="serialize"></a>  CDockingManager::Serialize

보관 하 고 도킹 관리자를 씁니다.

```
void Serialize(CArchive& ar);
```

### <a name="parameters"></a>매개 변수

*ar*<br/>
[in] 보관 개체에 대 한 참조입니다.

### <a name="remarks"></a>설명

보관 하 고 도킹 관리자 작성 도킹 컨트롤 막대 및 슬라이더 및 컨트롤 막대, 미니 프레임, 자동 숨기기 막대 및 MDI 탭 표시줄 보관 파일에 쓸 수를 결정 하는 작업을 포함 합니다.

##  <a name="setautohidezorder"></a>  CDockingManager::SetAutohideZOrder

크기, 너비 및 지정 된 창과 컨트롤 막대의 높이 설정합니다.

```
void SetAutohideZOrder(CDockablePane* pAHDockingBar);
```

### <a name="parameters"></a>매개 변수

*pAHDockingBar*<br/>
[in] 도킹 가능한 창에 대 한 포인터입니다.

##  <a name="setdockingmode"></a>  CDockingManager::SetDockingMode

도킹 모드를 설정합니다.

```
static void SetDockingMode(
    AFX_DOCK_TYPE dockMode,
    AFX_SMARTDOCK_THEME theme = AFX_SDT_DEFAULT);
```

### <a name="parameters"></a>매개 변수

*dockMode*<br/>
새 도킹 모드를 지정합니다. 자세한 내용은 설명 섹션을 참조하세요.

*테마*<br/>
스마트 도킹 표식에 사용 되는 테마를 지정 합니다. 다음 열거형된 값 중 하나일 수 있습니다. AFX_SDT_DEFAULT, AFX_SDT_VS2005, AFX_SDT_VS2008.

### <a name="remarks"></a>설명

도킹 모드를 설정 하려면이 정적 메서드를 호출 합니다.

*dockMode* 다음 값 중 하나일 수 있습니다.

- DT_STANDARD-Visual Studio.NET 2003에서 구현 되는 표준 도킹 모드입니다. 끌기 컨텍스트 없이 창 드래그 됩니다.

- DT_IMMEDIATE-Microsoft Visio의 구현으로 즉시 도킹 모드입니다. 창 끌기 컨텍스트를 사용 하 여 끈 있지만 마커가 없는 표시 됩니다.

- DT_SMART-Visual Studio 2005의 구현으로 스마트 도킹 모드입니다. 창 끌기 컨텍스트와 끈 및 스마트 표식이 표시 되는 표시 창에 도킹할 수 있습니다.

##  <a name="setdockstate"></a>  CDockingManager::SetDockState

컨트롤 막대, 미니 프레임 및 자동 숨기기 막대의 도킹 상태를 설정 합니다.

```
virtual void SetDockState();
```

##  <a name="setprintpreviewmode"></a>  CDockingManager::SetPrintPreviewMode

인쇄 미리 보기에 표시 되는 막대의 인쇄 미리 보기 모드를 설정 합니다.

```
void SetPrintPreviewMode(
    BOOL bPreview,
    CPrintPreviewState* pState);
```

### <a name="parameters"></a>매개 변수

*bPreview*<br/>
[in] TRUE 이면 인쇄 미리 보기 모드를 설정 합니다. FALSE이 고, 그렇지 합니다.

*pState*<br/>
[in] 미리 보기 상태에 대 한 포인터입니다. 이 매개 변수는 사용되지 않습니다.

##  <a name="setsmartdockingparams"></a>  CDockingManager::SetSmartDockingParams

스마트 도킹의 동작을 정의 하는 매개 변수를 설정 합니다.

```
static void SetSmartDockingParams(CSmartDockingInfo& params);
```

### <a name="parameters"></a>매개 변수

*params*<br/>
[out에서] 스마트 도킹의 매개 변수를 정의합니다.

### <a name="remarks"></a>설명

모양, 색 또는 스마트 도킹 표식의 모양을 사용자 지정 하려는 경우이 메서드를 호출 합니다.

스마트 도킹 표식에 대 한 기본 모양을 사용 하려면 초기화 되지 않은 인스턴스를 전달할 [CSmartDockingInfo 클래스](../../mfc/reference/csmartdockinginfo-class.md) 하 *params*합니다.

##  <a name="showdelayshowminiframes"></a>  CDockingManager::ShowDelayShowMiniFrames

표시 하거나 미니 프레임 창을 숨깁니다.

```
void ShowDelayShowMiniFrames(BOOL bshow);
```

### <a name="parameters"></a>매개 변수

*bShow*<br/>
[in] TRUE로 표시 된 프레임의 창; 활성화 프레임 창을 숨기려면 FALSE입니다.

##  <a name="showpanes"></a>  CDockingManager::ShowPanes

표시 하거나 제어 및 자동 숨기기 막대의 창을 숨깁니다.

```
virtual BOOL ShowPanes(BOOL bShow);
```

### <a name="parameters"></a>매개 변수

*bShow*<br/>
[in] 창을 표시 하 여; TRUE 창을 숨기려면 FALSE입니다.

### <a name="return-value"></a>반환 값

항상 FALSE입니다.

##  <a name="startsdocking"></a>  CDockingManager::StartSDocking

스마트 도킹 관리자의 맞춤에 따라 지정 된 창의 스마트 도킹을 시작 합니다.

```
void StartSDocking(CWnd* pDockingWnd);
```

### <a name="parameters"></a>매개 변수

*pDockingWnd*<br/>
[in] 도킹 창에 대 한 포인터입니다.

##  <a name="stopsdocking"></a>  CDockingManager::StopSDocking

중지 스마트 도킹 합니다.

```
void StopSDocking();
```

##  <a name="getsmartdockingtheme"></a>  CDockingManager::GetSmartDockingTheme

스마트 도킹 표식 표시 하는 데 사용 되는 테마를 반환 하는 정적 메서드.

```
static AFX_SMARTDOCK_THEME __stdcall GetSmartDockingTheme();
```

### <a name="return-value"></a>반환 값

다음 열거형된 값 중 하나를 반환합니다. AFX_SDT_DEFAULT, AFX_SDT_VS2005, AFX_SDT_VS2008.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[CFrameWndEx 클래스](../../mfc/reference/cframewndex-class.md)<br/>
[CDockablePane Class](../../mfc/reference/cdockablepane-class.md)<br/>
[CPaneFrameWnd 클래스](../../mfc/reference/cpaneframewnd-class.md)
