---
title: CMDIChildWndEx 클래스
ms.date: 10/18/2018
f1_keywords:
- CMDIChildWndEx
- AFXMDICHILDWNDEX/CMDIChildWndEx
- AFXMDICHILDWNDEX/CMDIChildWndEx::ActivateTopLevelFrame
- AFXMDICHILDWNDEX/CMDIChildWndEx::AddPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::AddTabbedPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::AdjustDockingLayout
- AFXMDICHILDWNDEX/CMDIChildWndEx::CanShowOnMDITabs
- AFXMDICHILDWNDEX/CMDIChildWndEx::CanShowOnTaskBarTabs
- AFXMDICHILDWNDEX/CMDIChildWndEx::CanShowOnWindowsList
- AFXMDICHILDWNDEX/CMDIChildWndEx::DockPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::DockPaneLeftOf
- AFXMDICHILDWNDEX/CMDIChildWndEx::EnableAutoHidePanes
- AFXMDICHILDWNDEX/CMDIChildWndEx::EnableDocking
- AFXMDICHILDWNDEX/CMDIChildWndEx::EnableTaskbarThumbnailClipRect
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetDockingManager
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetDocumentName
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetFrameIcon
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetFrameText
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetRelatedTabGroup
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetTabbedPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetTabProxyWnd
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetTaskbarPreviewWnd
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetTaskbarThumbnailClipRect
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetToolbarButtonToolTipText
- AFXMDICHILDWNDEX/CMDIChildWndEx::InsertPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::InvalidateIconicBitmaps
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsPointNearDockSite
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsReadOnly
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsRegisteredWithTaskbarTabs
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsTabbedPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsTaskbarTabsSupportEnabled
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsTaskbarThumbnailClipRectEnabled
- AFXMDICHILDWNDEX/CMDIChildWndEx::m_dwDefaultTaskbarTabPropertyFlags
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnGetIconicLivePreviewBitmap
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnGetIconicThumbnail
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnMoveMiniFrame
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnPressTaskbarThmbnailCloseButton
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnSetPreviewMode
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnTaskbarTabThumbnailActivate
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnTaskbarTabThumbnailMouseActivate
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnTaskbarTabThumbnailStretch
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnUpdateFrameTitle
- AFXMDICHILDWNDEX/CMDIChildWndEx::PaneFromPoint
- AFXMDICHILDWNDEX/CMDIChildWndEx::RecalcLayout
- AFXMDICHILDWNDEX/CMDIChildWndEx::RegisterTaskbarTab
- AFXMDICHILDWNDEX/CMDIChildWndEx::RemovePaneFromDockManager
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetRelatedTabGroup
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetTaskbarTabActive
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetTaskbarTabOrder
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetTaskbarTabProperties
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetTaskbarThumbnailClipRect
- AFXMDICHILDWNDEX/CMDIChildWndEx::ShowPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::UnregisterTaskbarTab
- AFXMDICHILDWNDEX/CMDIChildWndEx::UpdateTaskbarTabIcon
helpviewer_keywords:
- CMDIChildWndEx [MFC], ActivateTopLevelFrame
- CMDIChildWndEx [MFC], AddPane
- CMDIChildWndEx [MFC], AddTabbedPane
- CMDIChildWndEx [MFC], AdjustDockingLayout
- CMDIChildWndEx [MFC], CanShowOnMDITabs
- CMDIChildWndEx [MFC], CanShowOnTaskBarTabs
- CMDIChildWndEx [MFC], CanShowOnWindowsList
- CMDIChildWndEx [MFC], DockPane
- CMDIChildWndEx [MFC], DockPaneLeftOf
- CMDIChildWndEx [MFC], EnableAutoHidePanes
- CMDIChildWndEx [MFC], EnableDocking
- CMDIChildWndEx [MFC], EnableTaskbarThumbnailClipRect
- CMDIChildWndEx [MFC], GetDockingManager
- CMDIChildWndEx [MFC], GetDocumentName
- CMDIChildWndEx [MFC], GetFrameIcon
- CMDIChildWndEx [MFC], GetFrameText
- CMDIChildWndEx [MFC], GetPane
- CMDIChildWndEx [MFC], GetRelatedTabGroup
- CMDIChildWndEx [MFC], GetTabbedPane
- CMDIChildWndEx [MFC], GetTabProxyWnd
- CMDIChildWndEx [MFC], GetTaskbarPreviewWnd
- CMDIChildWndEx [MFC], GetTaskbarThumbnailClipRect
- CMDIChildWndEx [MFC], GetToolbarButtonToolTipText
- CMDIChildWndEx [MFC], InsertPane
- CMDIChildWndEx [MFC], InvalidateIconicBitmaps
- CMDIChildWndEx [MFC], IsPointNearDockSite
- CMDIChildWndEx [MFC], IsReadOnly
- CMDIChildWndEx [MFC], IsRegisteredWithTaskbarTabs
- CMDIChildWndEx [MFC], IsTabbedPane
- CMDIChildWndEx [MFC], IsTaskbarTabsSupportEnabled
- CMDIChildWndEx [MFC], IsTaskbarThumbnailClipRectEnabled
- CMDIChildWndEx [MFC], m_dwDefaultTaskbarTabPropertyFlags
- CMDIChildWndEx [MFC], OnGetIconicLivePreviewBitmap
- CMDIChildWndEx [MFC], OnGetIconicThumbnail
- CMDIChildWndEx [MFC], OnMoveMiniFrame
- CMDIChildWndEx [MFC], OnPressTaskbarThmbnailCloseButton
- CMDIChildWndEx [MFC], OnSetPreviewMode
- CMDIChildWndEx [MFC], OnTaskbarTabThumbnailActivate
- CMDIChildWndEx [MFC], OnTaskbarTabThumbnailMouseActivate
- CMDIChildWndEx [MFC], OnTaskbarTabThumbnailStretch
- CMDIChildWndEx [MFC], OnUpdateFrameTitle
- CMDIChildWndEx [MFC], PaneFromPoint
- CMDIChildWndEx [MFC], RecalcLayout
- CMDIChildWndEx [MFC], RegisterTaskbarTab
- CMDIChildWndEx [MFC], RemovePaneFromDockManager
- CMDIChildWndEx [MFC], SetRelatedTabGroup
- CMDIChildWndEx [MFC], SetTaskbarTabActive
- CMDIChildWndEx [MFC], SetTaskbarTabOrder
- CMDIChildWndEx [MFC], SetTaskbarTabProperties
- CMDIChildWndEx [MFC], SetTaskbarThumbnailClipRect
- CMDIChildWndEx [MFC], ShowPane
- CMDIChildWndEx [MFC], UnregisterTaskbarTab
- CMDIChildWndEx [MFC], UpdateTaskbarTabIcon
ms.assetid: d39fec06-0bd6-4271-917d-35aae3b24d8e
ms.openlocfilehash: e12cf9f65e6fd6dd7f68edc4a94103baa5a8df62
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58781759"
---
# <a name="cmdichildwndex-class"></a>CMDIChildWndEx 클래스

`CMDIChildWndEx` 클래스 여러 문서 MDI (인터페이스) 자식 창은 Windows의 기능을 제공 합니다. 기능을 확장 [CMDIChildWnd 클래스](../../mfc/reference/cmdichildwnd-class.md)합니다. MDI 애플리케이션에서 특정 MFC 클래스를 사용하면 프레임워크에 이 클래스가 필요합니다.

더 자세한 내용은 Visual Studio 설치의 **VC\\atlmfc\\src\\mfc** 폴더에 있는 소스 코드를 참조하세요.

## <a name="syntax"></a>구문

```
class CMDIChildWndEx : public CMDIChildWnd
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMDIChildWndEx::ActivateTopLevelFrame](#activatetoplevelframe)|작업 표시줄 탭에서 응용 프로그램을 활성화 해야 하는 경우 상위 수준 프레임을 활성화 하기 위해 프레임 워크에서 내부적으로 호출 됩니다.|
|`CMDIChildWndEx::AddDockSite`|이 메서드는 사용 되지 않거나 구현 합니다.|
|[CMDIChildWndEx::AddPane](#addpane)|창을 추가합니다.|
|[CMDIChildWndEx::AddTabbedPane](#addtabbedpane)|탭된 창에 추가 합니다.|
|[CMDIChildWndEx::AdjustDockingLayout](#adjustdockinglayout)|도킹 레이아웃을 조정합니다.|
|[CMDIChildWndEx::CanShowOnMDITabs](#canshowonmditabs)||
|[CMDIChildWndEx::CanShowOnTaskBarTabs](#canshowontaskbartabs)|이 MDI 자식이 Windows 7 작업 표시줄 탭에 표시 될 수 있는지 여부 프레임 워크에 지시 합니다.|
|[CMDIChildWndEx::CanShowOnWindowsList](#canshowonwindowslist)|MDI 자식 창 이름에 표시할 수 있으면 TRUE를 반환 합니다 [CMFCWindowsManagerDialog 클래스](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) 대화 상자. 그렇지 않으면 FALSE를 반환합니다.|
|`CMDIChildWndEx::CreateObject`|이 클래스 형식의 동적 인스턴스를 만드는 프레임 워크에서 호출 됩니다.|
|[CMDIChildWndEx::DockPane](#dockpane)|창을 도킹합니다.|
|[CMDIChildWndEx::DockPaneLeftOf](#dockpaneleftof)|창을 다른 창의 왼쪽에 도킹합니다.|
|[CMDIChildWndEx::EnableAutoHidePanes](#enableautohidepanes)|수 있도록 자동 숨기기 창에 대 한 모드 창의 지정 된 측면에 도킹 된 해당 하는 경우.|
|[CMDIChildWndEx::EnableDocking](#enabledocking)|주 프레임에 하면 자식 창의 도킹 합니다.|
|[CMDIChildWndEx::EnableTaskbarThumbnailClipRect](#enabletaskbarthumbnailcliprect)|사용 하거나 자동으로 선택 작업 표시줄에서 해당 창의 축소판 그림으로 표시 하려면 창의 클라이언트 영역의 일부를 사용 하지 않도록 설정 합니다.|
|[CMDIChildWndEx::GetDockingManager](#getdockingmanager)||
|[CMDIChildWndEx::GetDocumentName](#getdocumentname)|MDI 자식 창에 표시 되는 문서의 이름을 반환 합니다.|
|[CMDIChildWndEx::GetFrameIcon](#getframeicon)|MDI 자식 창 아이콘을 검색 하기 위해 프레임 워크에서 호출 됩니다.|
|[CMDIChildWndEx::GetFrameText](#getframetext)|MDI 자식 창에 대 한 텍스트를 검색 하기 위해 프레임 워크에서 호출 됩니다.|
|[CMDIChildWndEx::GetPane](#getpane)|지정 된 컨트롤 id 창을 찾습니다.|
|[CMDIChildWndEx::GetRelatedTabGroup](#getrelatedtabgroup)||
|[CMDIChildWndEx::GetTabbedPane](#gettabbedpane)|탭 문서로 변환 된 포함 된 도킹 창에 대 한 포인터를 반환 합니다.|
|[CMDIChildWndEx::GetTabProxyWnd](#gettabproxywnd)|반환은 프록시 창 실제로 Windows 7 작업 표시줄 탭을 사용 하 여 등록을 탭 합니다.|
|[CMDIChildWndEx::GetTaskbarPreviewWnd](#gettaskbarpreviewwnd)|Windows 7 작업 표시줄 탭 미리 보기에 표시할 자식 창 (일반적으로 뷰 또는 분할자 창)을 가져오려고 하면 프레임 워크에서 호출 됩니다.|
|[CMDIChildWndEx::GetTaskbarThumbnailClipRect](#gettaskbarthumbnailcliprect)|작업 표시줄에서 해당 창의 축소판 그림으로 표시 하려면 창의 클라이언트 영역의 일부를 선택 해야 할 때 프레임 워크에서 호출 됩니다.|
|`CMDIChildWndEx::GetThisClass`|에 대 한 포인터를 얻으려면 프레임 워크에서 호출 된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식과 연결 된 개체입니다.|
|[CMDIChildWndEx::GetToolbarButtonToolTipText](#gettoolbarbuttontooltiptext)|도구 모음 단추에 대 한 도구 설명을 검색 하기 위해 프레임 워크에서 호출 됩니다.|
|[CMDIChildWndEx::InsertPane](#insertpane)|지정 된 창 고 도킹 관리자에 등록합니다.|
|[CMDIChildWndEx::InvalidateIconicBitmaps](#invalidateiconicbitmaps)|MDI 자식 아이콘 비트맵 표현을 무효화합니다.|
|[CMDIChildWndEx::IsPointNearDockSite](#ispointneardocksite)|도킹 사이트 근처에 지정된 된 지점 인지 여부를 결정 합니다.|
|[CMDIChildWndEx::IsReadOnly](#isreadonly)|자식 창에 표시 되는 문서 읽기 전용 이면 TRUE를 반환 합니다. 그렇지 않으면 FALSE를 반환합니다.|
|[CMDIChildWndEx::IsRegisteredWithTaskbarTabs](#isregisteredwithtaskbartabs)|MDI 자식 Windows 7 작업 표시줄 탭을 사용 하 여 성공적으로 등록 된 경우 TRUE를 반환 합니다.|
|[CMDIChildWndEx::IsTabbedPane](#istabbedpane)|MDI 자식 창을 도킹 창을 포함 하는 경우 TRUE를 반환 합니다. 그렇지 않으면 FALSE를 반환합니다.|
|[CMDIChildWndEx::IsTaskbarTabsSupportEnabled](#istaskbartabssupportenabled)|MDI 자식 Windows 7 작업 표시줄 탭에 표시 될 수 있는지 여부를 알려 줍니다.|
|[CMDIChildWndEx::IsTaskbarThumbnailClipRectEnabled](#istaskbarthumbnailcliprectenabled)|작업 표시줄에서 해당 창의 축소판 그림으로 표시 하려면 창의 클라이언트 영역의 일부를 자동으로 선택 사용 되는지 여부를 알려 줍니다.|
|[CMDIChildWndEx::m_dwDefaultTaskbarTabPropertyFlags](#m_dwdefaulttaskbartabpropertyflags)|Windows 7 작업 표시줄 탭을 사용 하 여 탭 (MDI 자식)을 등록할 때 SetTaskbarTabProperties 메서드에 프레임 워크에 의해 전달 되는 플래그의 조합입니다. 기본 조합이 STPF_USEAPPTHUMBNAILWHENACTIVE입니다 &#124; STPF_USEAPPPEEKWHENACTIVE 합니다.|
|[CMDIChildWndEx::OnGetIconicLivePreviewBitmap](#ongeticoniclivepreviewbitmap)|MDI 자식의 실시간 미리 보기에 대 한 비트맵을 가져와야 하는 경우 프레임 워크에서 호출 됩니다.|
|[CMDIChildWndEx::OnGetIconicThumbnail](#ongeticonicthumbnail)|MDI 자식 아이콘 미리 보기에 대 한 비트맵을 가져와야 하는 경우 프레임 워크에서 호출 됩니다.|
|[CMDIChildWndEx::OnMoveMiniFrame](#onmoveminiframe)|미니 프레임 창을 이동 하기 위해 프레임 워크에서 호출 됩니다.|
|[CMDIChildWndEx::OnPressTaskbarThmbnailCloseButton](#onpresstaskbarthmbnailclosebutton)|사용자가 작업 표시줄 탭 미리 보기에서 [닫기] 단추를 누를 때 프레임 워크에서 호출 하 고...|
|[CMDIChildWndEx::OnSetPreviewMode](#onsetpreviewmode)|인쇄 미리 보기 모드로 들어가거나 종료 하기 위해 프레임 워크에서 호출 됩니다.|
|[CMDIChildWndEx::OnTaskbarTabThumbnailActivate](#ontaskbartabthumbnailactivate)|작업 표시줄 탭 축소판 그림 WM_ACTIVATE 메시지를 처리 해야 하는 경우 프레임 워크에서 호출 됩니다.|
|[CMDIChildWndEx::OnTaskbarTabThumbnailMouseActivate](#ontaskbartabthumbnailmouseactivate)|작업 표시줄 탭 축소판 그림 WM_MOUSEACTIVATE 메시지를 처리 해야 하는 경우 프레임 워크에서 호출 됩니다.|
|[CMDIChildWndEx::OnTaskbarTabThumbnailStretch](#ontaskbartabthumbnailstretch)|Windows 7 작업 표시줄 탭 축소판 그림 미리 보기의 MDI 자식에 대 한 비트맵 확장 해야 할 때 프레임 워크에서 호출 됩니다.|
|[CMDIChildWndEx::OnUpdateFrameTitle](#onupdateframetitle)|프레임 제목을 업데이트 하기 위해 프레임 워크에서 호출 됩니다. ( `CMDIChildWnd::OnUpdateFrameTitle`을 재정의합니다.)|
|[CMDIChildWndEx::PaneFromPoint](#panefrompoint)|지정된 된 점을 포함 하는 창을 반환 합니다.|
|`CMDIChildWndEx::PreTranslateMessage`|창 메시지가 [TranslateMessage](../../mfc/reference/cwinapp-class.md) 및 [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) Windows 함수로 디스패치되기 전에 [CWinApp](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) 클래스가 이 메시지를 해석하는 데 사용됩니다. ( [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)를 재정의합니다.)|
|[CMDIChildWndEx::RecalcLayout](#recalclayout)|창 레이아웃 다시 계산 됩니다.|
|[CMDIChildWndEx::RegisterTaskbarTab](#registertaskbartab)|Windows 7 작업 표시줄 탭 MDI 자식에 등록합니다.|
|[CMDIChildWndEx::RemovePaneFromDockManager](#removepanefromdockmanager)|창을 도킹 관리자에서 제거합니다.|
|[CMDIChildWndEx::SetRelatedTabGroup](#setrelatedtabgroup)||
|[CMDIChildWndEx::SetTaskbarTabActive](#settaskbartabactive)|해당 Windows 7 작업 표시줄 탭을 활성화 합니다.|
|[CMDIChildWndEx::SetTaskbarTabOrder](#settaskbartaborder)|Windows 7 작업 표시줄 탭에 지정 된 기간 전에 MDI 자식을 삽입합니다.|
|[CMDIChildWndEx::SetTaskbarTabProperties](#settaskbartabproperties)|Windows 7 작업 표시줄 탭에 대한 속성을 설정합니다.|
|[CMDIChildWndEx::SetTaskbarThumbnailClipRect](#settaskbarthumbnailcliprect)|작업 표시줄에서 해당 창의 축소판 그림으로 표시 하려면 창의 클라이언트 영역의 일부를 선택 하려면 클리핑 사각형을 설정 하기 위해 프레임 워크에서 내부적으로 호출 됩니다.|
|[CMDIChildWndEx::ShowPane](#showpane)||
|[CMDIChildWndEx::UnregisterTaskbarTab](#unregistertaskbartab)|Windows 7 작업 표시줄 탭에서 MDI 자식을 제거합니다.|
|[CMDIChildWndEx::UpdateTaskbarTabIcon](#updatetaskbartabicon)|Windows 7 작업 표시줄 탭 아이콘을 업데이트합니다.|

## <a name="remarks"></a>설명

MDI 응용 프로그램에서 도킹 확장된 기능을 사용 하려면 응용 프로그램에서 MDI 자식 창 클래스를 파생 `CMDIChildWndEx` of [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)합니다.

## <a name="example"></a>예제

다음 예제에서는 파생 클래스에서 `CMDIChildWndEx`합니다. 이 코드 조각에서 제공 되는 [VisualStudioDemo 샘플: Visual Studio 응용 프로그램 MFC](../../overview/visual-cpp-samples.md)합니다.

[!code-cpp[NVC_MFC_VisualStudioDemo#3](../../mfc/codesnippet/cpp/cmdichildwndex-class_1.h)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

[CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)

[CMDIChildWndEx](../../mfc/reference/cmdichildwndex-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxMDIChildWndEx.h

##  <a name="addpane"></a>  CMDIChildWndEx::AddPane

창을 추가합니다.

```
BOOL AddPane(
    CBasePane* pControlBar,
    BOOL bTail = TRUE);
```

### <a name="parameters"></a>매개 변수

*pControlBar*<br/>
[in] 창에 대 한 포인터입니다.

*bTail*<br/>
[in] 도킹 관리자에 대 한 창 창의 목록 끝에 추가. 그렇지 않으면 FALSE입니다.

### <a name="return-value"></a>반환 값

창 고 도킹 관리자; 성공적으로 등록 된 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

##  <a name="addtabbedpane"></a>  CMDIChildWndEx::AddTabbedPane

탭된 창에 추가 합니다.

```
void AddTabbedPane(CDockablePane* pControlBar);
```

### <a name="parameters"></a>매개 변수

*pControlBar*<br/>
[in] 창에 대 한 포인터입니다.

##  <a name="adjustdockinglayout"></a>  CMDIChildWndEx::AdjustDockingLayout

도킹 레이아웃을 조정합니다.

```
virtual void AdjustDockingLayout(HDWP hdwp = NULL);
```

### <a name="parameters"></a>매개 변수

*hdwp*<br/>
[in] 지연 된 창 위치 구조에 대 한 핸들입니다.

##  <a name="canshowonmditabs"></a>  CMDIChildWndEx::CanShowOnMDITabs

```
virtual BOOL CanShowOnMDITabs();
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="canshowonwindowslist"></a>  CMDIChildWndEx::CanShowOnWindowsList

MDI 자식 창 이름에 표시할 수 있는지 여부를 지정 합니다 [CMFCWindowsManagerDialog 클래스](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) 대화 상자.

```
virtual BOOL CanShowOnWindowsList();
```

### <a name="return-value"></a>반환 값

창에 표시할 수 있으면 TRUE를 **Windows** 대화 상자, 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

파생된 클래스에서이 메서드를 재정의 하 고 창에 표시 되어서는 안 되는 경우 FALSE를 반환 합니다 **Windows** 대화 상자. 이 함수에서 호출 됩니다 `CMFCWindowsManagerDialog`합니다.

##  <a name="dockpane"></a>  CMDIChildWndEx::DockPane

창을 도킹합니다.

```
void DockPane(
    CBasePane* pBar,
    UINT nDockBarID = 0,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>매개 변수

*pBar*<br/>
[in] 창에 대 한 포인터입니다.

*nDockBarID*<br/>
[in] ID는 창입니다.

*lpRect*<br/>
[in] 사각형에 대 한 포인터입니다.

### <a name="remarks"></a>설명

합니다 *lpRect* 매개 변수가 사용 되지 않습니다.

##  <a name="dockpaneleftof"></a>  CMDIChildWndEx::DockPaneLeftOf

창을 다른 창의 왼쪽에 도킹합니다.

```
BOOL DockPaneLeftOf(
    CPane* pBar,
    CPane* pLeftOf);
```

### <a name="parameters"></a>매개 변수

*pBar*<br/>
도킹 된 창에 대 한 포인터입니다.

*pLeftOf*<br/>
참조 지점으로 사용 되는 창에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

성공 시 TRUE이 고, 실패 하면 FALSE를 합니다.

### <a name="remarks"></a>설명

이 메서드는 지정 된 창 *pBar* 로 지정 된 창의 왼쪽에 도킹 *pLeftOf*합니다.

미리 정의 된 순서 대로 여러 개의 창이 도킹 하고자 하는 경우이 메서드를 호출 합니다.

##  <a name="enableautohidepanes"></a>  CMDIChildWndEx::EnableAutoHidePanes

수 있도록 자동 숨기기 창에 대 한 모드 창의 지정 된 측면에 도킹 된 해당 하는 경우.

```
BOOL EnableAutoHidePanes(DWORD dwDockStyle);
```

### <a name="parameters"></a>매개 변수

*dwDockStyle*<br/>
[in] 사용 되는 주 프레임 창 측면을 지정 합니다. 다음 플래그 중 하나 이상을 사용 합니다.

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

- CBRS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

### <a name="return-value"></a>반환 값

메서드가 성공 하면 TRUE입니다. 그렇지 않으면 FALSE입니다.

##  <a name="enabledocking"></a>  CMDIChildWndEx::EnableDocking

주 프레임에 하면 자식 창의 도킹 합니다.

```
BOOL EnableDocking(DWORD dwDockStyle);
```

### <a name="parameters"></a>매개 변수

*dwDockStyle*<br/>
[in] 사용할 수 있도록 도킹 맞춤을 지정 합니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

주 프레임에 도킹 맞춤을 사용 하도록 설정 하려면이 메서드를 호출 합니다. CBRS_ALIGN_ 플래그의 조합에 전달할 수 있습니다 (자세한 내용은 [CControlBar::EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking)).

##  <a name="getdockingmanager"></a>  CMDIChildWndEx::GetDockingManager

```
CDockingManager* GetDockingManager();
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="getdocumentname"></a>  CMDIChildWndEx::GetDocumentName

MDI 자식 창에 표시 되는 문서의 이름을 반환 합니다.

```
virtual LPCTSTR GetDocumentName(CObject** pObj);
```

### <a name="return-value"></a>반환 값

문서 이름이 포함 된 문자열에 대 한 포인터입니다.

### <a name="remarks"></a>설명

문서는 MDI 자식 창에 표시 됩니다. 일반적으로 창에서 로드 되거나 파일에 저장 되는 데이터를 표시 합니다. 따라서 문서의 이름을 파일의 이름이입니다. 기본 구현의 `GetDocumentName` 에서 가져온 문자열을 반환 합니다 `CDocument::GetPathName`합니다.

창 파일에서 로드 되지 않은 문서를 표시 하는 경우 파생된 클래스에서이 메서드를 재정의 하 고 고유한 문서 식별자를 반환 합니다.

`GetDocumentName` 모든 열린된 문서의 상태를 저장 하는 경우에 프레임 워크에서 호출 됩니다. 반환된 된 문자열은 레지스트리에 기록 됩니다.

프레임 워크는 상태를 복원할 때 나중에 문서 이름을 레지스트리에서 읽고 전달할 [CMDIFrameWndEx::CreateDocumentWindow](../../mfc/reference/cmdiframewndex-class.md#createdocumentwindow)합니다. 이 메서드를 재정의 하는 [CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md)-파생 클래스 또는이 이름이 있는 문서를 열고 만들고이 이름을 가진 파일을 읽어. 문서 파일을 기반으로 하지 않는 경우에 자체 문서 식별자를 기반으로 문서를 만듭니다. 저장 하 고 문서를 복원 하려는 경우에 이전 작업을 해야 합니다.

### <a name="example"></a>예제

다음 예제에서는 `GetDocumentName` 메서드를 사용하는 방법을 보여 줍니다. 이 코드 조각에서 제공 되는 [VisualStudioDemo 샘플: Visual Studio 응용 프로그램 MFC](../../overview/visual-cpp-samples.md)합니다.

[!code-cpp[NVC_MFC_VisualStudioDemo#17](../../mfc/codesnippet/cpp/cmdichildwndex-class_2.cpp)]

##  <a name="getframeicon"></a>  CMDIChildWndEx::GetFrameIcon

MDI 자식 창의 아이콘을 검색 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual HICON GetFrameIcon() const;
```

### <a name="return-value"></a>반환 값

창 아이콘에 대 한 핸들입니다.

### <a name="remarks"></a>설명

이 메서드는 MDI 자식 프레임 창에 포함 된 MDI 탭에 표시 하는 아이콘을 확인 하기 위해 프레임 워크에서 호출 됩니다.

이 메서드는 기본적으로 창 아이콘을 반환합니다. 재정의 `GetFrameIcon` 에 `CMDIChildWndEx`-이 동작을 사용자 지정 클래스를 파생 합니다.

##  <a name="getframetext"></a>  CMDIChildWndEx::GetFrameText

MDI 자식 창에 대 한 텍스트를 검색 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual CString GetFrameText() const;
```

### <a name="return-value"></a>반환 값

프레임 창 텍스트를 포함 하는 문자열입니다.

### <a name="remarks"></a>설명

이 메서드는 MDI 자식 프레임 창에 포함 된 MDI 탭에 표시할 텍스트를 확인 하기 위해 프레임 워크에서 호출 됩니다.

이 메서드는 기본적으로 창 텍스트를 반환합니다. 재정의 `GetFrameText` 에 `CMDIChildWndEx`-이 동작을 사용자 지정 클래스를 파생 합니다.

##  <a name="getpane"></a>  CMDIChildWndEx::GetPane

지정 된 컨트롤 id 창을 찾습니다.

```
CBasePane* GetPane(UINT nID);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
[in] 검색할 창의 컨트롤 ID입니다.

### <a name="return-value"></a>반환 값

창 고, 그렇지 않으면 NULL 포인터입니다.

##  <a name="getrelatedtabgroup"></a>  CMDIChildWndEx::GetRelatedTabGroup

```
CMFCTabCtrl* GetRelatedTabGroup();
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="gettabbedpane"></a>  CMDIChildWndEx::GetTabbedPane

탭 문서 MDI 그룹의 일부인 도킹 창에 대 한 포인터를 반환 합니다.

```
CDockablePane* GetTabbedPane() const;
```

### <a name="return-value"></a>반환 값

MDI 그룹의 일부인 도킹 창에 대 한 포인터는 문서를 탭 합니다.

##  <a name="gettoolbarbuttontooltiptext"></a>  CMDIChildWndEx::GetToolbarButtonToolTipText

도구 모음 단추에 대 한 도구 설명을 검색 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual BOOL GetToolbarButtonToolTipText(
    CMFCToolBarButton*,
    CString&);
```

### <a name="return-value"></a>반환 값

도구 설명이 표시 되 면 TRUE입니다. 기본 구현은 FALSE를 반환합니다.

### <a name="remarks"></a>설명

도구 모음 단추에 대 한 사용자 지정 도구 설명을 표시 하려는 경우이 메서드를 재정의 합니다.

##  <a name="insertpane"></a>  CMDIChildWndEx::InsertPane

지정 된 창 고 도킹 관리자에 등록합니다.

```
BOOL InsertPane(
    CBasePane* pControlBar,
    CBasePane* pTarget,
    BOOL bAfter = TRUE);
```

### <a name="parameters"></a>매개 변수

*pControlBar*<br/>
[in] 삽입할 창에 대 한 포인터입니다.

*pTarget*<br/>
[in] 인접 한 창에 대 한 포인터입니다.

*후에는*<br/>
[in] TRUE 이면 *pControlBar* 뒤에 삽입 됩니다 *pTarget*합니다. FALSE 이면 *pControlBar* 앞에 삽입 됩니다 *pTarget*합니다.

### <a name="return-value"></a>반환 값

메서드가 성공 FALSE이 고, 그렇지 면 TRUE입니다.

##  <a name="ispointneardocksite"></a>  CMDIChildWndEx::IsPointNearDockSite

도킹 사이트 근처에 지정된 된 지점 인지 여부를 결정 합니다.

```
BOOL IsPointNearDockSite(
    CPoint point,
    DWORD& dwBarAlignment,
    BOOL& bOuterEdge) const;
```

### <a name="parameters"></a>매개 변수

*지점*<br/>
[in] 지정 된 지점입니다.

*dwBarAlignment*<br/>
[in] 요점은 가까운 가장자리를 지정 합니다. 가능한 값은 CBRS_ALIGN_LEFT, CBRS_ALIGN_RIGHT, CBRS_ALIGN_TOP, 및 CBRS_ALIGN_BOTTOM

*bOuterEdge*<br/>
[in] TRUE 이면 포인터가 거의 도킹 사이트;의 바깥쪽 테두리 FALSE이 고, 그렇지 합니다.

### <a name="return-value"></a>반환 값

도킹 사이트; 가까운 지점이 있으면 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

요점은 도킹 사이트 거의 고 도킹 관리자에 설정 민감도 내에 없을 때입니다. 기본 민감도 15 픽셀입니다.

##  <a name="isreadonly"></a>  CMDIChildWndEx::IsReadOnly

자식 창에 표시 되는 문서 읽기 전용인 지 여부를 지정 합니다.

```
virtual BOOL IsReadOnly();
```

### <a name="return-value"></a>반환 값

TRUE 이면 문서가 읽기 전용입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

방지 하기 위해이 함수는 읽기 전용으로 문서를 저장 합니다.

### <a name="example"></a>예제

다음 예제에서는 재정의 `IsReadOnly` 메서드. 이 코드 조각에서 제공 되는 [VisualStudioDemo 샘플: Visual Studio 응용 프로그램 MFC](../../overview/visual-cpp-samples.md)합니다.

[!code-cpp[NVC_MFC_VisualStudioDemo#2](../../mfc/codesnippet/cpp/cmdichildwndex-class_3.cpp)]

##  <a name="istabbedpane"></a>  CMDIChildWndEx::IsTabbedPane

MDI 자식 창을 도킹 창에 포함 되는지 여부를 지정 합니다.

```
BOOL IsTabbedPane() const;
```

### <a name="return-value"></a>반환 값

MDI 자식 창을 탭 된 문서로; 변환 된 도킹 창을 포함 하는 경우 TRUE 그렇지 않으면 FALSE입니다.

##  <a name="onmoveminiframe"></a>  CMDIChildWndEx::OnMoveMiniFrame

미니 프레임 창을 이동 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```

### <a name="parameters"></a>매개 변수

*pFrame*<br/>
[in] 미니 프레임 창에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

TRUE는 메서드가 성공 하면, 그렇지 않으면 FALSE입니다.

##  <a name="onsetpreviewmode"></a>  CMDIChildWndEx::OnSetPreviewMode

인쇄 미리 보기 모드로 들어가거나 종료 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual void OnSetPreviewMode(
    BOOL bPreview,
    CPrintPreviewState* pState);
```

### <a name="parameters"></a>매개 변수

*bPreview*<br/>
[in] TRUE 이면 인쇄 미리 보기 모드로 전환 합니다. FALSE 이면 종료 인쇄 미리 보기 모드입니다.

*pState*<br/>
[in] 인쇄 미리 보기 상태 구조에 대 한 포인터입니다.

##  <a name="onupdateframetitle"></a>  CMDIChildWndEx::OnUpdateFrameTitle

프레임 제목을 업데이트 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual void OnUpdateFrameTitle(BOOL bAddToTitle);
```

### <a name="parameters"></a>매개 변수

*bAddToTitle*<br/>
[in] TRUE 이면 제목에 문서 이름을 추가 합니다.

##  <a name="panefrompoint"></a>  CMDIChildWndEx::PaneFromPoint

지정된 된 점을 포함 하는 창을 반환 합니다.

```
CBasePane* PaneFromPoint(
    CPoint point,
    int nSensitivity,
    bool bExactBar,
    CRuntimeClass* pRTCBarType) const;

CBasePane* PaneFromPoint(
    CPoint point,
    int nSensitivity,
    DWORD& dwAlignment,
    CRuntimeClass* pRTCBarType) const;
```

### <a name="parameters"></a>매개 변수

*지점*<br/>
[in] 확인 화면 좌표에서 지점에 지정 합니다.

*nSensitivity*<br/>
[in] 검색 영역에이 용량을 늘립니다. 지정 된 증가 된 영역에 해당 하는 경우 검색 조건을 충족 하는 창입니다.

*bExactBar*<br/>
[in] 무시 하려면 TRUE를 *nSensitivity* 매개 변수, 그렇지 않으면 FALSE입니다.

*pRTCBarType*<br/>
[in] NULL이 아닌 경우 메서드는 지정 된 형식의 창만 검색 합니다.

*dwAlignment*<br/>
[in] 창이 지정된 된 지점에 있으면이 매개 변수는 지정된 된 위치에 가장 가까운 창 옆쪽에 포함 합니다. 자세한 내용은 설명 섹션을 참조하세요.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 `CBasePane`-찾을 수 없는 창 하는 경우 지정 된 지점 또는 NULL을 포함 하는 파생 된 개체입니다.

### <a name="remarks"></a>설명

창을 런타임 클래스 및 표시와 같은 지정된 된 조건에 따라 지정된 된 지점이 들어 있는지 여부를 확인 하려면이 메서드를 호출 합니다.

함수를 반환 하 고 창의 찾을 때 *dwAlignment* 지정 된 요소의 맞춤을 포함 합니다. 예를 들어, 창의 위쪽에 가장 가까운 점 되었으면 *dwAlignment* CBRS_ALIGN_TOP로 설정 됩니다.

##  <a name="recalclayout"></a>  CMDIChildWndEx::RecalcLayout

창 레이아웃 다시 계산 됩니다.

```
virtual void RecalcLayout(BOOL bNotify = TRUE);
```

### <a name="parameters"></a>매개 변수

*bNotify*<br/>
[in] TRUE 인 경우 활성 현재 위치 항목 창에 대 한 레이아웃 변경의 알림을 수신 합니다.

##  <a name="removepanefromdockmanager"></a>  CMDIChildWndEx::RemovePaneFromDockManager

창을 도킹 관리자에서 제거합니다.

```
void RemovePaneFromDockManager(
    CBasePane* pControlBar,
    BOOL bDestroy,
    BOOL bAdjustLayout,
    BOOL bAutoHide,
    CBasePane* pBarReplacement);
```

### <a name="parameters"></a>매개 변수

*pControlBar*<br/>
[in] 제거할 창에 대 한 포인터입니다.

*bDestroy*<br/>
[in] TRUE 이면 제거 창 소멸 됩니다.

*bAdjustLayout*<br/>
[in] TRUE 이면 즉시 도킹 레이아웃을 조정 합니다.

*bAutoHide*<br/>
[in] TRUE 이면 도킹 레이아웃을 자동 숨기기 막대의 목록 관련이 있습니다. False 인 경우, 일반 창 목록을 도킹 레이아웃 관련이 있습니다.

*pBarReplacement*<br/>
[in] 제거 창을 대체 하는 창에 대 한 포인터입니다.

##  <a name="setrelatedtabgroup"></a>  CMDIChildWndEx::SetRelatedTabGroup

```
void SetRelatedTabGroup(CMFCTabCtrl* p);
```

### <a name="parameters"></a>매개 변수

[in] *p*<br/>

### <a name="remarks"></a>설명

##  <a name="showpane"></a>  CMDIChildWndEx::ShowPane

```
void ShowPane(
    CBasePane* pBar,
    BOOL bShow,
    BOOL bDelay,
    BOOL bActivate);
```

### <a name="parameters"></a>매개 변수

[in] *pBar*<br/>

[in] *bShow*<br/>

[in] *bDelay*<br/>

[in] *bActivate*<br/>

### <a name="remarks"></a>설명

##  <a name="updatetaskbartabicon"></a>  CMDIChildWndEx::UpdateTaskbarTabIcon

Windows 7 작업 표시줄 탭 아이콘을 업데이트합니다.

```
virtual void UpdateTaskbarTabIcon(HICON hIcon);
```

### <a name="parameters"></a>매개 변수

*hIcon*<br/>
Windows 7 작업 표시줄 탭에 표시할 아이콘에 대 한 핸들입니다.

### <a name="remarks"></a>설명

##  <a name="unregistertaskbartab"></a>  CMDIChildWndEx::UnregisterTaskbarTab

Windows 7 작업 표시줄 탭에서 MDI 자식을 제거합니다.

```
void UnregisterTaskbarTab(BOOL bCheckRegisteredMDIChildCount = TRUE);
```

### <a name="parameters"></a>매개 변수

*bCheckRegisteredMDIChildCount*<br/>
이 함수를 등록 된 MDI 탭 MDI 자식의 수를 확인 해야 하는지 여부를 지정 합니다. 이 값이 0 이면이 함수는 응용 프로그램의 작업 표시줄 축소판 그림에서 클리핑 사각형을 제거 합니다.

### <a name="remarks"></a>설명

##  <a name="settaskbarthumbnailcliprect"></a>  CMDIChildWndEx::SetTaskbarThumbnailClipRect

작업 표시줄에서 해당 창의 축소판 그림으로 표시 하려면 창의 클라이언트 영역의 일부를 선택 하려면 클리핑 사각형을 설정 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual BOOL SetTaskbarThumbnailClipRect(CRect rect);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
새 클리핑 사각형을 지정합니다. 사각형이 비어 있거나 null 인 경우 클리핑을 제거 됩니다.

### <a name="return-value"></a>반환 값

성공하면 TRUE이고, 실패하면 FALSE입니다.

### <a name="remarks"></a>설명

##  <a name="settaskbartabproperties"></a>  CMDIChildWndEx::SetTaskbarTabProperties

Windows 7 작업 표시줄 탭에 대한 속성을 설정합니다.

```
void SetTaskbarTabProperties(DWORD dwFlags);
```

### <a name="parameters"></a>매개 변수

*dwFlags*<br/>
STPFLAG 값의 조합입니다. 자세한 내용은 [ITaskbarList4::SetTabProperties](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-itaskbarlist4-settabproperties)합니다.

### <a name="remarks"></a>설명

##  <a name="settaskbartaborder"></a>  CMDIChildWndEx::SetTaskbarTabOrder

Windows 7 작업 표시줄 탭에 지정 된 기간 전에 MDI 자식을 삽입합니다.

```
void SetTaskbarTabOrder(CMDIChildWndEx* pWndBefore = NULL);
```

### <a name="parameters"></a>매개 변수

*pWndBefore*<br/>
MDI 자식 창에 있는 축소판 그림이 왼쪽에 삽입 되는 포인터입니다. 이 창을 통해 이미 등록 되어 있어야 `RegisterTaskbarTab`합니다. 이 값이 NULL 인 경우 새 미리 보기는 목록 끝에 추가 됩니다.

### <a name="remarks"></a>설명

##  <a name="settaskbartabactive"></a>  CMDIChildWndEx::SetTaskbarTabActive

해당 Windows 7 작업 표시줄 탭을 활성화합니다.

```
void SetTaskbarTabActive();
```

### <a name="remarks"></a>설명

##  <a name="registertaskbartab"></a>  CMDIChildWndEx::RegisterTaskbarTab

Windows 7 작업 표시줄 탭 MDI 자식에 등록합니다.

```
virtual void RegisterTaskbarTab(CMDIChildWndEx* pWndBefore = NULL);
```

### <a name="parameters"></a>매개 변수

*pWndBefore*<br/>
MDI 자식 창에 있는 축소판 그림이 왼쪽에 삽입 되는 포인터입니다. 이 창을 통해 이미 등록 되어 있어야 `RegisterTaskbarTab`합니다. 이 값이 NULL 인 경우 새 미리 보기는 목록 끝에 추가 됩니다.

### <a name="remarks"></a>설명

##  <a name="ontaskbartabthumbnailstretch"></a>  CMDIChildWndEx::OnTaskbarTabThumbnailStretch

Windows 7 작업 표시줄 탭 미리 MDI 자식에 대 한 비트맵 확장 해야 할 때 프레임 워크에서 호출 됩니다.

```
virtual BOOL OnTaskbarTabThumbnailStretch(
    HBITMAP hBmpDst,
    const CRect& rectDst,
    HBITMAP hBmpSrc,
    const CRect& rectSrc);
```

### <a name="parameters"></a>매개 변수

*hBmpDst*<br/>
대상 비트맵 핸들입니다.

*rectDst*<br/>
대상 사각형을 지정합니다.

*hBmpSrc*<br/>
소스 비트맵 핸들입니다.

*rectSrc*<br/>
소스 사각형을 지정합니다.

### <a name="remarks"></a>설명

요구 사항: afxmdichildwndex.h

##  <a name="ontaskbartabthumbnailmouseactivate"></a>  CMDIChildWndEx::OnTaskbarTabThumbnailMouseActivate

작업 표시줄 탭 축소판 그림 WM_MOUSEACTIVATE 메시지를 처리할 때 프레임 워크에서 호출 됩니다.

```
virtual int OnTaskbarTabThumbnailMouseActivate(
    CWnd* pDesktopWnd,
    UINT nHitTest,
    UINT message);
```

### <a name="parameters"></a>매개 변수

*pDesktopWnd*<br/>
활성화 되 고 창의 최상위 부모 창에 대 한 포인터를 지정 합니다. 포인터는 임시 수 있으며 저장 되어야 합니다.

*nHitTest*<br/>
적중 테스트 영역 코드를 지정합니다. 적중 횟수 테스트에는 커서의 위치를 결정 하는 테스트가입니다.

*message*<br/>
마우스 메시지 수를 지정합니다.

### <a name="remarks"></a>설명

관련된 MDI 자식 프레임을 활성화 하는 기본 구현입니다.

##  <a name="ontaskbartabthumbnailactivate"></a>  CMDIChildWndEx::OnTaskbarTabThumbnailActivate

작업 표시줄 탭 축소판 그림 WM_ACTIVATE 메시지를 처리할 때 프레임 워크에서 호출 됩니다.

```
virtual void OnTaskbarTabThumbnailActivate(
    UINT nState,
    CWnd* pWndOther,
    BOOL bMinimized);
```

### <a name="parameters"></a>매개 변수

*nState*<br/>
지정 여부는 `CWnd` 활성화 또는 비활성화 되는 합니다.

*pWndOther*<br/>
에 대 한 포인터를 `CWnd` 활성화 되거나 비활성화 합니다. 포인터는 NULL 일 수 및 임시 수 있습니다.

*bMinimized*<br/>
최소화 된 상태를 지정 된 `CWnd` 활성화 되거나 비활성화 합니다. 값이 true 이면 창을 최소화 됨을 나타냅니다.

### <a name="remarks"></a>설명

관련된 MDI 자식 프레임을 활성화 하는 기본 구현입니다.

##  <a name="onpresstaskbarthmbnailclosebutton"></a>  CMDIChildWndEx::OnPressTaskbarThmbnailCloseButton

사용자가 작업 표시줄 탭 미리 보기에서 닫기 단추를 누를 때 프레임 워크에서 호출 합니다.

```
virtual void OnPressTaskbarThmbnailCloseButton();
```

### <a name="remarks"></a>설명

##  <a name="ongeticonicthumbnail"></a>  CMDIChildWndEx::OnGetIconicThumbnail

MDI 자식 아이콘 미리 보기에 대 한 비트맵을 가져와야 하는 경우 프레임 워크에서 호출 됩니다.

```
virtual HBITMAP OnGetIconicThumbnail(
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>매개 변수

*nWidth*<br/>
필요한 비트맵의 너비를 지정합니다.

*nHeight*<br/>
필요한 비트맵의 높이 지정합니다.

### <a name="remarks"></a>설명

##  <a name="ongeticoniclivepreviewbitmap"></a>  CMDIChildWndEx::OnGetIconicLivePreviewBitmap

MDI 자식의 실시간 미리 보기에 대 한 비트맵을 가져와야 하는 경우 프레임 워크에서 호출 됩니다.

```
virtual HBITMAP OnGetIconicLivePreviewBitmap(
    BOOL bIsMDIChildActive,
    CPoint& ptLocation);
```

### <a name="parameters"></a>매개 변수

*bIsMDIChildActive*<br/>
이 매개 변수는 현재 활성 상태인 MDI 자식에 대 한 비트맵이 요청 되었고 주 창을 최소화 하지 하는 경우 TRUE입니다. 기본이 경우 처리에 주 창의 스냅숏을 만듭니다.

*ptLocation*<br/>
Main (최상위 수준)에서 비트맵의 위치를 지정 합니다. 창 클라이언트 좌표입니다. 이 여기서는 호출 수신자가 제공 되어야 합니다.

### <a name="return-value"></a>반환 값

처리 하는 경우 유효한 32bpp 비트맵으로 핸들을 반환 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

파생된 클래스에서이 메서드를 재정의 하 고 MDI 자식의 실시간 미리 보기에 대 한 유효한 32bpp 비트맵을 반환 합니다. 이 메서드는 MDI 자식 Windows 7 작업 표시줄 탭에 표시 되는 경우에 호출 됩니다. NULL을 반환 하는 경우 MFC 기본 처리기를 호출 하 고 사용 하 여 비트맵을 가져옵니다 `PrintClient` 또는 `PrintWindow`합니다.

##  <a name="m_dwdefaulttaskbartabpropertyflags"></a>  CMDIChildWndEx::m_dwDefaultTaskbarTabPropertyFlags

프레임 워크에 의해 전달 되는 플래그의 조합 된 `SetTaskbarTabProperties` 메서드를 Windows 7 작업 표시줄 탭을 사용 하 여 탭 (MDI 자식)를 등록 하는 경우.

```
AFX_IMPORT_DATA static DWORD m_dwDefaultTaskbarTabPropertyFlags;
```

### <a name="remarks"></a>설명

기본 조합이 STPF_USEAPPTHUMBNAILWHENACTIVE입니다 &#124; STPF_USEAPPPEEKWHENACTIVE 합니다.

##  <a name="istaskbarthumbnailcliprectenabled"></a>  CMDIChildWndEx::IsTaskbarThumbnailClipRectEnabled

작업 표시줄에서 해당 창의 축소판 그림으로 표시 하려면 창의 클라이언트 영역의 일부를 자동으로 선택 사용 되는지 여부를 알려 줍니다.

```
BOOL IsTaskbarThumbnailClipRectEnabled() const;
```

### <a name="return-value"></a>반환 값

창의 클라이언트 영역에 표시할 부분의 반환 자동 인 경우 TRUE 선택 기능이 활성화 되어; 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

##  <a name="istaskbartabssupportenabled"></a>  CMDIChildWndEx::IsTaskbarTabsSupportEnabled

MDI 자식 Windows 7 작업 표시줄 탭에 표시 될 수 있는지 여부를 알려 줍니다.

```
BOOL IsTaskbarTabsSupportEnabled();
```

### <a name="return-value"></a>반환 값

MDI 자식 Windows 7 작업 표시줄 탭;에 표시할 수 있는 경우 TRUE입니다. FALSE 이면 MDI 자식 Windows 7 작업 표시줄 탭에 나타날 수 없습니다.

### <a name="remarks"></a>설명

##  <a name="isregisteredwithtaskbartabs"></a>  CMDIChildWndEx::IsRegisteredWithTaskbarTabs

MDI 자식 Windows 7 작업 표시줄 탭을 사용 하 여 성공적으로 등록 된 경우 TRUE를 반환 합니다.

```
BOOL IsRegisteredWithTaskbarTabs();
```

### <a name="return-value"></a>반환 값

MDI 자식 Windows 7 작업 표시줄 탭;에 등록 되어 있으면 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

##  <a name="invalidateiconicbitmaps"></a>  CMDIChildWndEx::InvalidateIconicBitmaps

MDI 자식 아이콘 비트맵 표현을 무효화합니다.

```
BOOL InvalidateIconicBitmaps();
```

### <a name="return-value"></a>반환 값

Windows 7 작업 표시줄 지원이 해제 되어 있으면 FALSE 반환 또는 MDI 자식 등록 되지 않은 Windows 7 작업 표시줄 탭이 있습니다. 그렇지 않으면 TRUE를 반환합니다.

### <a name="remarks"></a>설명

라이브 콘텐츠 또는 MDI 자식의 크기를 변경 될 때 호출 되어야 합니다.

##  <a name="gettaskbarthumbnailcliprect"></a>  CMDIChildWndEx::GetTaskbarThumbnailClipRect

작업 표시줄에서 해당 창의 축소판 그림으로 표시 하려면 창의 클라이언트 영역의 일부를 선택 해야 할 때 프레임 워크에서 호출 됩니다.

```
virtual CRect GetTaskbarThumbnailClipRect() const;
```

### <a name="return-value"></a>반환 값

Windows 좌표에는 사각형입니다. 이 사각형은 최상위 수준 프레임의 클라이언트 영역에 매핑됩니다. 사각형은 클리핑 사각형을 지우려면 비어 있어야 합니다.

### <a name="remarks"></a>설명

##  <a name="gettaskbarpreviewwnd"></a>  CMDIChildWndEx::GetTaskbarPreviewWnd

Windows 7 작업 표시줄 탭 미리 보기에 표시할 자식 창 (일반적으로 뷰 또는 분할자 창)을 가져오려고 하면 프레임 워크에서 호출 됩니다.

```
virtual CWnd* GetTaskbarPreviewWnd();
```

### <a name="return-value"></a>반환 값

에 대 한 유효한 포인터를 반환 해야는 `CWnd` 이 MDI 자식으로 관련 개체를 Windows 7 작업 표시줄 탭에 있는 미리 보기를 표시 합니다. 기본 구현은 반환이 MDI 자식 AFX_IDW_PANE_FIRST 컨트롤 ID 사용 하 여 자식 창 (일반적으로 `CView`-파생 클래스).

### <a name="remarks"></a>설명

##  <a name="gettabproxywnd"></a>  CMDIChildWndEx::GetTabProxyWnd

Windows 7 작업 표시줄 탭을 사용 하 여 등록 탭 프록시 창을 반환 합니다.

```
CMDITabProxyWnd* GetTabProxyWnd();
```

### <a name="return-value"></a>반환 값

에 대 한 포인터를 `CMDITabProxyWnd` Windows 7 작업 표시줄 탭을 사용 하 여 등록 되는 개체입니다.

### <a name="remarks"></a>설명

##  <a name="enabletaskbarthumbnailcliprect"></a>  CMDIChildWndEx::EnableTaskbarThumbnailClipRect

사용 하거나 자동으로 선택 작업 표시줄에서 해당 창의 축소판 그림으로 표시 하려면 창의 클라이언트 영역의 일부를 사용 하지 않도록 설정 합니다.

```
void EnableTaskbarThumbnailClipRect(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
(TRUE)을 사용할 것인지 또는 표시할 창의 클라이언트 영역의 일부 자동 선택을 사용 하지 않도록 설정 (FALSE)를 지정 합니다.

### <a name="remarks"></a>설명

##  <a name="canshowontaskbartabs"></a>  CMDIChildWndEx::CanShowOnTaskBarTabs

이 MDI 자식이 Windows 7 작업 표시줄 탭에 표시 될 수 있는지 여부 프레임 워크에 지시 합니다.

```
virtual BOOL CanShowOnTaskBarTabs();
```

### <a name="return-value"></a>반환 값

Windows 7 작업 표시줄 축소판 그림에 MDI 자식 콘텐츠를 표시할 수 있으면 TRUE입니다.

### <a name="remarks"></a>설명

파생된 클래스에서이 메서드를 재정의 하 고 Windows 7 작업 표시줄 탭 MDI 자식이 모양을 사용 하지 않도록 설정 하려면 FALSE를 반환 합니다.

##  <a name="activatetoplevelframe"></a>  CMDIChildWndEx::ActivateTopLevelFrame

작업 표시줄 탭에서 응용 프로그램 활성화 될 때 최상위 프레임을 활성화 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual void ActivateTopLevelFrame();
```

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMDIChildWnd 클래스](../../mfc/reference/cmdichildwnd-class.md)<br/>
[CMFCWindowsManagerDialog 클래스](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)<br/>
[CMDIFrameWndEx 클래스](../../mfc/reference/cmdiframewndex-class.md)
