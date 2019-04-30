---
title: CPaneFrameWnd 클래스
ms.date: 11/04/2016
f1_keywords:
- CPaneFrameWnd
- AFXPANEFRAMEWND/CPaneFrameWnd
- AFXPANEFRAMEWND/CPaneFrameWnd::AddPane
- AFXPANEFRAMEWND/CPaneFrameWnd::AddRemovePaneFromGlobalList
- AFXPANEFRAMEWND/CPaneFrameWnd::AdjustLayout
- AFXPANEFRAMEWND/CPaneFrameWnd::AdjustPaneFrames
- AFXPANEFRAMEWND/CPaneFrameWnd::CalcBorderSize
- AFXPANEFRAMEWND/CPaneFrameWnd::CalcExpectedDockedRect
- AFXPANEFRAMEWND/CPaneFrameWnd::CanBeAttached
- AFXPANEFRAMEWND/CPaneFrameWnd::CanBeDockedToPane
- AFXPANEFRAMEWND/CPaneFrameWnd::CheckGripperVisibility
- AFXPANEFRAMEWND/CPaneFrameWnd::ConvertToTabbedDocument
- AFXPANEFRAMEWND/CPaneFrameWnd::Create
- AFXPANEFRAMEWND/CPaneFrameWnd::CreateEx
- AFXPANEFRAMEWND/CPaneFrameWnd::DockPane
- AFXPANEFRAMEWND/CPaneFrameWnd::FindFloatingPaneByID
- AFXPANEFRAMEWND/CPaneFrameWnd::FrameFromPoint
- AFXPANEFRAMEWND/CPaneFrameWnd::GetCaptionHeight
- AFXPANEFRAMEWND/CPaneFrameWnd::GetCaptionRect
- AFXPANEFRAMEWND/CPaneFrameWnd::GetCaptionText
- AFXPANEFRAMEWND/CPaneFrameWnd::GetDockingManager
- AFXPANEFRAMEWND/CPaneFrameWnd::GetDockingMode
- AFXPANEFRAMEWND/CPaneFrameWnd::GetFirstVisiblePane
- AFXPANEFRAMEWND/CPaneFrameWnd::GetHotPoint
- AFXPANEFRAMEWND/CPaneFrameWnd::GetPane
- AFXPANEFRAMEWND/CPaneFrameWnd::GetPaneCount
- AFXPANEFRAMEWND/CPaneFrameWnd::GetParent
- AFXPANEFRAMEWND/CPaneFrameWnd::GetPinState
- AFXPANEFRAMEWND/CPaneFrameWnd::GetRecentFloatingRect
- AFXPANEFRAMEWND/CPaneFrameWnd::GetVisiblePaneCount
- AFXPANEFRAMEWND/CPaneFrameWnd::HitTest
- AFXPANEFRAMEWND/CPaneFrameWnd::IsCaptured
- AFXPANEFRAMEWND/CPaneFrameWnd::IsDelayShow
- AFXPANEFRAMEWND/CPaneFrameWnd::IsRollDown
- AFXPANEFRAMEWND/CPaneFrameWnd::IsRollUp
- AFXPANEFRAMEWND/CPaneFrameWnd::KillDockingTimer
- AFXPANEFRAMEWND/CPaneFrameWnd::LoadState
- AFXPANEFRAMEWND/CPaneFrameWnd::OnBeforeDock
- AFXPANEFRAMEWND/CPaneFrameWnd::OnDockToRecentPos
- AFXPANEFRAMEWND/CPaneFrameWnd::OnKillRollUpTimer
- AFXPANEFRAMEWND/CPaneFrameWnd::OnMovePane
- AFXPANEFRAMEWND/CPaneFrameWnd::OnPaneRecalcLayout
- AFXPANEFRAMEWND/CPaneFrameWnd::OnSetRollUpTimer
- AFXPANEFRAMEWND/CPaneFrameWnd::OnShowPane
- AFXPANEFRAMEWND/CPaneFrameWnd::PaneFromPoint
- AFXPANEFRAMEWND/CPaneFrameWnd::Pin
- AFXPANEFRAMEWND/CPaneFrameWnd::RedrawAll
- AFXPANEFRAMEWND/CPaneFrameWnd::RemoveNonValidPanes
- AFXPANEFRAMEWND/CPaneFrameWnd::RemovePane
- AFXPANEFRAMEWND/CPaneFrameWnd::ReplacePane
- AFXPANEFRAMEWND/CPaneFrameWnd::SaveState
- AFXPANEFRAMEWND/CPaneFrameWnd::SetCaptionButtons
- AFXPANEFRAMEWND/CPaneFrameWnd::SetDelayShow
- AFXPANEFRAMEWND/CPaneFrameWnd::SetDockingManager
- AFXPANEFRAMEWND/CPaneFrameWnd::SetDockingTimer
- AFXPANEFRAMEWND/CPaneFrameWnd::SetDockState
- AFXPANEFRAMEWND/CPaneFrameWnd::SetHotPoint
- AFXPANEFRAMEWND/CPaneFrameWnd::SetPreDockState
- AFXPANEFRAMEWND/CPaneFrameWnd::SizeToContent
- AFXPANEFRAMEWND/CPaneFrameWnd::StartTearOff
- AFXPANEFRAMEWND/CPaneFrameWnd::StoreRecentDockSiteInfo
- AFXPANEFRAMEWND/CPaneFrameWnd::StoreRecentTabRelatedInfo
- AFXPANEFRAMEWND/CPaneFrameWnd::OnCheckRollState
- AFXPANEFRAMEWND/CPaneFrameWnd::OnDrawBorder
- AFXPANEFRAMEWND/CPaneFrameWnd::m_bUseSaveBits
helpviewer_keywords:
- CPaneFrameWnd [MFC], AddPane
- CPaneFrameWnd [MFC], AddRemovePaneFromGlobalList
- CPaneFrameWnd [MFC], AdjustLayout
- CPaneFrameWnd [MFC], AdjustPaneFrames
- CPaneFrameWnd [MFC], CalcBorderSize
- CPaneFrameWnd [MFC], CalcExpectedDockedRect
- CPaneFrameWnd [MFC], CanBeAttached
- CPaneFrameWnd [MFC], CanBeDockedToPane
- CPaneFrameWnd [MFC], CheckGripperVisibility
- CPaneFrameWnd [MFC], ConvertToTabbedDocument
- CPaneFrameWnd [MFC], Create
- CPaneFrameWnd [MFC], CreateEx
- CPaneFrameWnd [MFC], DockPane
- CPaneFrameWnd [MFC], FindFloatingPaneByID
- CPaneFrameWnd [MFC], FrameFromPoint
- CPaneFrameWnd [MFC], GetCaptionHeight
- CPaneFrameWnd [MFC], GetCaptionRect
- CPaneFrameWnd [MFC], GetCaptionText
- CPaneFrameWnd [MFC], GetDockingManager
- CPaneFrameWnd [MFC], GetDockingMode
- CPaneFrameWnd [MFC], GetFirstVisiblePane
- CPaneFrameWnd [MFC], GetHotPoint
- CPaneFrameWnd [MFC], GetPane
- CPaneFrameWnd [MFC], GetPaneCount
- CPaneFrameWnd [MFC], GetParent
- CPaneFrameWnd [MFC], GetPinState
- CPaneFrameWnd [MFC], GetRecentFloatingRect
- CPaneFrameWnd [MFC], GetVisiblePaneCount
- CPaneFrameWnd [MFC], HitTest
- CPaneFrameWnd [MFC], IsCaptured
- CPaneFrameWnd [MFC], IsDelayShow
- CPaneFrameWnd [MFC], IsRollDown
- CPaneFrameWnd [MFC], IsRollUp
- CPaneFrameWnd [MFC], KillDockingTimer
- CPaneFrameWnd [MFC], LoadState
- CPaneFrameWnd [MFC], OnBeforeDock
- CPaneFrameWnd [MFC], OnDockToRecentPos
- CPaneFrameWnd [MFC], OnKillRollUpTimer
- CPaneFrameWnd [MFC], OnMovePane
- CPaneFrameWnd [MFC], OnPaneRecalcLayout
- CPaneFrameWnd [MFC], OnSetRollUpTimer
- CPaneFrameWnd [MFC], OnShowPane
- CPaneFrameWnd [MFC], PaneFromPoint
- CPaneFrameWnd [MFC], Pin
- CPaneFrameWnd [MFC], RedrawAll
- CPaneFrameWnd [MFC], RemoveNonValidPanes
- CPaneFrameWnd [MFC], RemovePane
- CPaneFrameWnd [MFC], ReplacePane
- CPaneFrameWnd [MFC], SaveState
- CPaneFrameWnd [MFC], SetCaptionButtons
- CPaneFrameWnd [MFC], SetDelayShow
- CPaneFrameWnd [MFC], SetDockingManager
- CPaneFrameWnd [MFC], SetDockingTimer
- CPaneFrameWnd [MFC], SetDockState
- CPaneFrameWnd [MFC], SetHotPoint
- CPaneFrameWnd [MFC], SetPreDockState
- CPaneFrameWnd [MFC], SizeToContent
- CPaneFrameWnd [MFC], StartTearOff
- CPaneFrameWnd [MFC], StoreRecentDockSiteInfo
- CPaneFrameWnd [MFC], StoreRecentTabRelatedInfo
- CPaneFrameWnd [MFC], OnCheckRollState
- CPaneFrameWnd [MFC], OnDrawBorder
- CPaneFrameWnd [MFC], m_bUseSaveBits
ms.assetid: ea3423a3-2763-482e-b763-817036ded10d
ms.openlocfilehash: 3172556b3b12141aaae45992dee36061aebf2a15
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62372909"
---
# <a name="cpaneframewnd-class"></a>CPaneFrameWnd 클래스

더 자세한 내용은 Visual Studio 설치의 **VC\\atlmfc\\src\\mfc** 폴더에 있는 소스 코드를 참조하세요.

하나의 창이 포함된 미니 프레임 창을 구현합니다. 창은 창의 클라이언트 영역을 채웁니다.

## <a name="syntax"></a>구문

```
class CPaneFrameWnd : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CPaneFrameWnd::AddPane](#addpane)|창을 추가합니다.|
|[CPaneFrameWnd::AddRemovePaneFromGlobalList](#addremovepanefromgloballist)|전역 목록에서 창을 추가하거나 제거합니다.|
|[CPaneFrameWnd::AdjustLayout](#adjustlayout)|미니 프레임 창의 레이아웃을 조정합니다.|
|[CPaneFrameWnd::AdjustPaneFrames](#adjustpaneframes)||
|[CPaneFrameWnd::CalcBorderSize](#calcbordersize)|미니 프레임 창의 테두리 크기를 계산합니다.|
|[CPaneFrameWnd::CalcExpectedDockedRect](#calcexpecteddockedrect)|도킹된 창의 예상 사각형을 계산합니다.|
|[CPaneFrameWnd::CanBeAttached](#canbeattached)|현재 창을 다른 창이나 프레임 창에 도킹할 수 있는지 여부를 결정합니다.|
|[CPaneFrameWnd::CanBeDockedToPane](#canbedockedtopane)|미니 프레임 창을 창에 도킹할 수 있는지 여부를 결정합니다.|
|[CPaneFrameWnd::CheckGripperVisibility](#checkgrippervisibility)||
|[CPaneFrameWnd::ConvertToTabbedDocument](#converttotabbeddocument)|창을 탭된 문서로 변환합니다.|
|[CPaneFrameWnd::Create](#create)|미니 프레임 창을 만들고 `CPaneFrameWnd` 개체에 연결합니다.|
|[CPaneFrameWnd::CreateEx](#createex)|미니 프레임 창을 만들고 `CPaneFrameWnd` 개체에 연결합니다.|
|[CPaneFrameWnd::DockPane](#dockpane)|창을 도킹합니다.|
|[CPaneFrameWnd::FindFloatingPaneByID](#findfloatingpanebyid)|부동 창의 전역 목록에서 지정된 컨트롤 ID를 가진 창을 찾습니다.|
|[CPaneFrameWnd::FrameFromPoint](#framefrompoint)|사용자가 제공한 지점을 포함하는 미니 프레임 창을 찾습니다.|
|[CPaneFrameWnd::GetCaptionHeight](#getcaptionheight)|미니 프레임 창 캡션의 높이를 반환합니다.|
|[CPaneFrameWnd::GetCaptionRect](#getcaptionrect)|미니 프레임 창 캡션의 경계 사각형을 계산합니다.|
|[CPaneFrameWnd::GetCaptionText](#getcaptiontext)|캡션 텍스트를 반환합니다.|
|[CPaneFrameWnd::GetDockingManager](#getdockingmanager)||
|[CPaneFrameWnd::GetDockingMode](#getdockingmode)|도킹 모드를 반환합니다.|
|[CPaneFrameWnd::GetFirstVisiblePane](#getfirstvisiblepane)|미니 프레임 창에 포함된 첫 번째 표시 창을 반환합니다.|
|[CPaneFrameWnd::GetHotPoint](#gethotpoint)||
|[CPaneFrameWnd::GetPane](#getpane)|미니 프레임 창에 포함된 창을 반환합니다.|
|[CPaneFrameWnd::GetPaneCount](#getpanecount)|미니 프레임 창에 포함된 창 수를 반환합니다.|
|[CPaneFrameWnd::GetParent](#getparent)||
|[CPaneFrameWnd::GetPinState](#getpinstate)||
|[CPaneFrameWnd::GetRecentFloatingRect](#getrecentfloatingrect)||
|[CPaneFrameWnd::GetVisiblePaneCount](#getvisiblepanecount)|미니 프레임 창에 포함된 표시 창 수를 반환합니다.|
|[CPaneFrameWnd::HitTest](#hittest)|미니 프레임 창의 어떤 부분이 지정된 지점에 있는지 결정합니다.|
|[CPaneFrameWnd::IsCaptured](#iscaptured)||
|[CPaneFrameWnd::IsDelayShow](#isdelayshow)||
|[CPaneFrameWnd::IsRollDown](#isrolldown)|미니 프레임 창이 롤다운되어야 하는지 여부를 결정합니다.|
|[CPaneFrameWnd::IsRollUp](#isrollup)|미니 프레임 창이 롤업되어야 하는지 여부를 결정합니다.|
|[CPaneFrameWnd::KillDockingTimer](#killdockingtimer)|도킹 타이머를 중지합니다.|
|[CPaneFrameWnd::LoadState](#loadstate)|레지스트리에서 창의 상태를 로드합니다.|
|[CPaneFrameWnd::OnBeforeDock](#onbeforedock)|도킹 가능한지 여부를 결정합니다.|
|[CPaneFrameWnd::OnDockToRecentPos](#ondocktorecentpos)|가장 최근 위치에 미니 프레임 창을 도킹합니다.|
|[CPaneFrameWnd::OnKillRollUpTimer](#onkillrolluptimer)|롤업 타이머를 중지합니다.|
|[CPaneFrameWnd::OnMovePane](#onmovepane)|지정된 오프셋만큼 미니 프레임 창을 이동합니다.|
|[CPaneFrameWnd::OnPaneRecalcLayout](#onpanerecalclayout)|포함된 창의 레이아웃을 조정합니다.|
|[CPaneFrameWnd::OnSetRollUpTimer](#onsetrolluptimer)|롤업 타이머를 설정합니다.|
|[CPaneFrameWnd::OnShowPane](#onshowpane)|미니 프레임 창의 창이 숨겨지거나 표시될 때 프레임워크에서 호출됩니다.|
|[CPaneFrameWnd::PaneFromPoint](#panefrompoint)|미니 프레임 창 안에 사용자가 제공한 지점을 포함하는 경우 창을 반환합니다.|
|[CPaneFrameWnd::Pin](#pin)||
|`CPaneFrameWnd::PreTranslateMessage`|창 메시지가 [TranslateMessage](../../mfc/reference/cwinapp-class.md) 및 [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) Windows 함수로 디스패치되기 전에 [CWinApp](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) 클래스가 이 메시지를 해석하는 데 사용됩니다.|
|[CPaneFrameWnd::RedrawAll](#redrawall)|모든 미니 프레임 창을 다시 그립니다.|
|[CPaneFrameWnd::RemoveNonValidPanes](#removenonvalidpanes)|잘못된 창을 제거하기 위해 프레임워크에서 호출됩니다.|
|[CPaneFrameWnd::RemovePane](#removepane)|미니 프레임 창에서 창을 제거합니다.|
|[CPaneFrameWnd::ReplacePane](#replacepane)|한 창을 다른 창으로 대체합니다.|
|[CPaneFrameWnd::SaveState](#savestate)|레지스트리에 창의 상태를 저장합니다.|
|`CPaneFrameWnd::Serialize`|이 개체를 보관 저장소에서 읽어오거나 보관 저장소에 씁니다.|
|[CPaneFrameWnd::SetCaptionButtons](#setcaptionbuttons)|캡션 단추를 설정합니다.|
|[CPaneFrameWnd::SetDelayShow](#setdelayshow)||
|[CPaneFrameWnd::SetDockingManager](#setdockingmanager)||
|[CPaneFrameWnd::SetDockingTimer](#setdockingtimer)|도킹 타이머를 설정합니다.|
|[CPaneFrameWnd::SetDockState](#setdockstate)|도킹 상태를 설정합니다.|
|[CPaneFrameWnd::SetHotPoint](#sethotpoint)||
|[CPaneFrameWnd::SetPreDockState](#setpredockstate)|사전 도킹 상태를 설정하기 위해 프레임워크에서 호출됩니다.|
|[CPaneFrameWnd::SizeToContent](#sizetocontent)|포함된 창과 크기가 같도록 미니 프레임 창의 크기를 조정합니다.|
|[CPaneFrameWnd::StartTearOff](#starttearoff)|메뉴를 분리합니다.|
|[CPaneFrameWnd::StoreRecentDockSiteInfo](#storerecentdocksiteinfo)||
|[CPaneFrameWnd::StoreRecentTabRelatedInfo](#storerecenttabrelatedinfo)||

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[CPaneFrameWnd::OnCheckRollState](#oncheckrollstate)|미니 프레임 창이 롤업 또는 롤다운되어야 하는지를 결정합니다.|
|[CPaneFrameWnd::OnDrawBorder](#ondrawborder)|미니 프레임 창의 테두리를 그립니다.|

### <a name="data-members"></a>데이터 멤버

|이름|설명|
|----------|-----------------|
|[CPaneFrameWnd::m_bUseSaveBits](#m_busesavebits)|CS_SAVEBITS 클래스 스타일을 사용 하 여 창 클래스를 등록할지 여부를 지정 합니다.|

## <a name="remarks"></a>설명

창이 도킹된 상태에서 부동 상태로 전환되면 프레임워크에서 자동으로 `CPaneFrameWnd` 개체를 만듭니다.

내용을 표시(즉시 도킹)하거나 끌기 사각형을 사용하여(표준 도킹) 미니 프레임 창을 끌 수 있습니다. 미니 프레임 컨테이너 창의 도킹 모드에 따라 미니 프레임의 끌기 동작이 결정됩니다. 자세한 내용은 [cbasepane:: Getdockingmode](../../mfc/reference/cbasepane-class.md#getdockingmode)합니다.

미니 프레임 창에 포함된 창 스타일에 따라 캡션에 단추가 표시됩니다. 창을 닫을 수 있는 경우 ( [cbasepane:: Canbeclosed](../../mfc/reference/cbasepane-class.md#canbeclosed)), 닫기 단추를 표시 합니다. 창 스타일을 AFX_CBRS_AUTO_ROLLUP 있으면 핀이 표시 됩니다.

`CPaneFrameWnd`에서 클래스를 파생하는 경우 프레임워크에 만드는 방법을 알려야 합니다. 재정의 하 여 클래스를 만들거나 [cpane:: Createdefaultminiframe](../../mfc/reference/cpane-class.md#createdefaultminiframe)를 설정 또는 `CPane::m_pMiniFrameRTC` 멤버는 클래스에 대 한 런타임 클래스 정보를 가리킵니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CPaneFrameWnd`

## <a name="requirements"></a>요구 사항

**헤더:** afxPaneFrameWnd.h

##  <a name="addpane"></a>  CPaneFrameWnd::AddPane

창을 추가합니다.

```
virtual void AddPane(CBasePane* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
[in] 추가할 창입니다.

##  <a name="addremovepanefromgloballist"></a>  CPaneFrameWnd::AddRemovePaneFromGlobalList

전역 목록에서 창을 추가하거나 제거합니다.

```
static BOOL __stdcall AddRemovePaneFromGlobalList(
    CBasePane* pWnd,
    BOOL bAdd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
[in] 추가 하거나 제거 하려면 창입니다.

*bAdd*<br/>
[in] 0이 아닌 경우에 창에 추가 합니다. 0 인 경우 창을 제거 합니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 0이 아닌 값 그렇지 않으면 0입니다.

##  <a name="adjustlayout"></a>  CPaneFrameWnd::AdjustLayout

미니 프레임 창의 레이아웃을 조정합니다.

```
virtual void AdjustLayout();
```

##  <a name="adjustpaneframes"></a>  CPaneFrameWnd::AdjustPaneFrames

```
virtual void AdjustPaneFrames();
```

### <a name="remarks"></a>설명

##  <a name="calcbordersize"></a>  CPaneFrameWnd::CalcBorderSize

미니 프레임 창의 테두리의 크기를 계산 합니다.

```
virtual void CalcBorderSize(CRect& rectBorderSize) const;
```

### <a name="parameters"></a>매개 변수

*rectBorderSize*<br/>
[out] 미니 프레임 창의 테두리의 픽셀에서 크기를 포함합니다.

### <a name="remarks"></a>설명

이 메서드는 미니 프레임 창의 테두리의 크기를 계산 하기 위해 프레임 워크에서 호출 됩니다. 미니 프레임 창 도구 모음 포함 여부는 반환 되는 크기에 따라 다릅니다 [CDockablePane](../../mfc/reference/cdockablepane-class.md)합니다.

##  <a name="calcexpecteddockedrect"></a>  CPaneFrameWnd::CalcExpectedDockedRect

도킹된 창의 예상 사각형을 계산합니다.

```
virtual void CalcExpectedDockedRect(
    CWnd* pWndToDock,
    CPoint ptMouse,
    CRect& rectResult,
    BOOL& bDrawTab,
    CDockablePane** ppTargetBar);
```

### <a name="parameters"></a>매개 변수

*pWndToDock*<br/>
[in] 창 도킹에 대 한 포인터입니다.

*ptMouse*<br/>
[in] 마우스 위치입니다.

*rectResult*<br/>
[out] 계산 된 사각형입니다.

*bDrawTab*<br/>
[out] TRUE 인 경우 탭을 그립니다. FALSE 인 경우 탭을 그리지 않습니다.

*ppTargetBar*<br/>
[out] 대상 창에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드를 사용자 지정 된 지점에 창을 끌 경우 창이 차지 하는 사각형을 계산 *ptMouse* 있습니다 도킹 하 고 있습니다.

##  <a name="canbeattached"></a>  CPaneFrameWnd::CanBeAttached

현재 창을 다른 창이나 프레임 창에 도킹할 수 있는지 여부를 결정합니다.

```
virtual BOOL CanBeAttached() const;
```

### <a name="return-value"></a>반환 값

창의 다른 창이 나 프레임 창에 도킹할 수 있는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

##  <a name="canbedockedtopane"></a>  CPaneFrameWnd::CanBeDockedToPane

미니 프레임 창을 창에 도킹할 수 있는지 여부를 결정합니다.

```
virtual BOOL CanBeDockedToPane(const CDockablePane* pDockingBar) const;
```

### <a name="parameters"></a>매개 변수

*pDockingBar*<br/>
[in] 창입니다.

### <a name="return-value"></a>반환 값

미니 프레임에 도킹할 수 있는 경우 0이 아닌 *pDockingBar*그렇지 않으면 0입니다.

##  <a name="checkgrippervisibility"></a>  CPaneFrameWnd::CheckGripperVisibility

```
virtual void CheckGripperVisibility();
```

### <a name="remarks"></a>설명

##  <a name="converttotabbeddocument"></a>  CPaneFrameWnd::ConvertToTabbedDocument

창을 탭된 문서로 변환합니다.

```
virtual void ConvertToTabbedDocument();
```

##  <a name="create"></a>  CPaneFrameWnd::Create

미니 프레임 창을 만들고에 연결 합니다 [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) 개체입니다.

```
virtual BOOL Create(
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszWindowName*<br/>
[in] 미니 프레임 창에 표시할 텍스트를 지정 합니다.

*dwStyle*<br/>
[in] 창 스타일을 지정합니다. 자세한 내용은 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles)합니다.

*rect*<br/>
[in] 초기 크기와 미니 프레임 창의 위치를 지정 합니다.

*pParentWnd*<br/>
[out에서] 미니 프레임 창의 부모 프레임을 지정합니다. 이 값에 NULL이 아니어야 합니다.

*pContext*<br/>
[out에서] 사용자 정의 컨텍스트를 지정합니다.

### <a name="return-value"></a>반환 값

창 성공적으로 만들어진 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

미니 프레임 창은 두 단계에서 만들어집니다. 먼저, 프레임 워크를 만들어는 `CPaneFrameWnd` 개체입니다. 둘째, 호출 `Create` Windows 미니 프레임 창을 만들고에 연결 하는 `CPaneFrameWnd` 개체입니다.

##  <a name="createex"></a>  CPaneFrameWnd::CreateEx

미니 프레임 창을 만들고에 연결 합니다 [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) 개체입니다.

```
virtual BOOL CreateEx(
    DWORD dwStyleEx,
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    CCreateContext* pContext=NULL);
```

### <a name="parameters"></a>매개 변수

*dwStyleEx*<br/>
[in] 확장된 창 스타일을 지정합니다. 자세한 내용은 참조 하세요. [확장 창 스타일](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)

*lpszWindowName*<br/>
[in] 미니 프레임 창에 표시할 텍스트를 지정 합니다.

*dwStyle*<br/>
[in] 창 스타일을 지정합니다. 자세한 내용은 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles)합니다.

*rect*<br/>
[in] 초기 크기와 미니 프레임 창의 위치를 지정 합니다.

*pParentWnd*<br/>
[out에서] 미니 프레임 창의 부모 프레임을 지정합니다. 이 값에 NULL이 아니어야 합니다.

*pContext*<br/>
[out에서] 사용자 정의 컨텍스트를 지정합니다.

### <a name="return-value"></a>반환 값

창 성공적으로 만들어진 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

미니 프레임 창은 두 단계에서 만들어집니다. 먼저, 프레임 워크를 만들어는 `CPaneFrameWnd` 개체입니다. 둘째, 호출 `Create` Windows 미니 프레임 창을 만들고에 연결 하는 `CPaneFrameWnd` 개체입니다.

##  <a name="dockpane"></a>  CPaneFrameWnd::DockPane

창을 도킹합니다.

```
virtual CDockablePane* DockPane(BOOL& bWasDocked);
```

### <a name="parameters"></a>매개 변수

*bWasDocked*<br/>
[out] 창 도킹 되어 이미; 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="return-value"></a>반환 값

작업이 성공한 경우의 `CDockablePane` 창에 도킹 된 되었으면 NULL는 합니다.

##  <a name="findfloatingpanebyid"></a>  CPaneFrameWnd::FindFloatingPaneByID

부동 창의 전역 목록에서 지정된 컨트롤 ID를 가진 창을 찾습니다.

```
static CBasePane* FindFloatingPaneByID(UINT nID);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
[in] 검색할 창의 컨트롤 ID를 나타냅니다.

### <a name="return-value"></a>반환 값

지정 된 컨트롤 ID; 인 창 그렇지 않은 경우 NULL을 없는 창에 지정 된 컨트롤 id입니다.

##  <a name="framefrompoint"></a>  CPaneFrameWnd::FrameFromPoint

지정 된 지점이 포함 된 미니 프레임 창을 찾습니다.

```
static CPaneFrameWnd* __stdcall FrameFromPoint(
    CPoint pt,
    int nSensitivity,
    CPaneFrameWnd* pFrameToExclude = NULL,
    BOOL bFloatMultiOnly = FALSE);
```

### <a name="parameters"></a>매개 변수

*pt*<br/>
[in] 화면 좌표 지점입니다.

*nSensitivity*<br/>
[in] 이 크기에 따라 미니 프레임 창의 검색 영역을 늘립니다. 미니 프레임 창을 지정 된 증가 된 영역에 해당 하는 경우 검색 조건을 충족 합니다.

*pFrameToExclude*<br/>
[in] 검색에서 제외할 미니 프레임 창을 지정 합니다.

*bFloatMultiOnly*<br/>
[in] TRUE 이면 CBRS_FLOAT_MULTI 스타일이 적용 된 미니 프레임 창을 검색 합니다. FALSE 이면 모든 미니 프레임 창을 검색 합니다.

### <a name="return-value"></a>반환 값

포함 된 미니 프레임 창에 대 한 포인터 *pt*그렇지 않으면 NULL입니다.

##  <a name="getcaptionheight"></a>  CPaneFrameWnd::GetCaptionHeight

미니 프레임 창 캡션의 높이를 반환합니다.

```
virtual int GetCaptionHeight() const;
```

### <a name="return-value"></a>반환 값

미니 프레임 창의 픽셀 높이입니다.

### <a name="remarks"></a>설명

미니 프레임 창의 높이 확인 하려면이 메서드를 호출 합니다. 기본적으로 높이 SM_CYSMCAPTION에 설정 됩니다. 자세한 내용은 [GetSystemMetrics 함수](/windows/desktop/api/winuser/nf-winuser-getsystemmetrics)합니다.

##  <a name="getcaptionrect"></a>  CPaneFrameWnd::GetCaptionRect

미니 프레임 창 캡션의 경계 사각형을 계산합니다.

```
virtual void GetCaptionRect(CRect& rectCaption) const;
```

### <a name="parameters"></a>매개 변수

*rectCaption*<br/>
[out] 화면 좌표에 미니 프레임 창 캡션의 위치와 크기를 포함합니다.

### <a name="remarks"></a>설명

이 메서드는 미니 프레임 창 캡션의 경계 사각형을 계산 하기 위해 프레임 워크에서 호출 됩니다.

##  <a name="getcaptiontext"></a>  CPaneFrameWnd::GetCaptionText

캡션 텍스트를 반환합니다.

```
virtual CString GetCaptionText();
```

### <a name="return-value"></a>반환 값

미니 프레임 창의 캡션 텍스트입니다.

### <a name="remarks"></a>설명

캡션 텍스트를 표시 하는 경우이 메서드는 프레임 워크에서 호출 됩니다.

##  <a name="getdockingmanager"></a>  CPaneFrameWnd::GetDockingManager

```
CDockingManager* GetDockingManager() const;
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="getdockingmode"></a>  CPaneFrameWnd::GetDockingMode

도킹 모드를 반환합니다.

```
virtual AFX_DOCK_TYPE GetDockingMode() const;
```

### <a name="return-value"></a>반환 값

도킹 모드입니다. 다음 값 중 하나입니다.

- DT_STANDARD

- DT_IMMEDIATE

- DT_SMART

##  <a name="getfirstvisiblepane"></a>  CPaneFrameWnd::GetFirstVisiblePane

미니 프레임 창에 포함된 첫 번째 표시 창을 반환합니다.

```
virtual CWnd* GetFirstVisiblePane() const;
```

### <a name="return-value"></a>반환 값

미니 프레임 창 또는 미니 프레임 창 없는 창을 포함 하는 경우 NULL의 첫 번째 창입니다.

##  <a name="gethotpoint"></a>  CPaneFrameWnd::GetHotPoint

```
CPoint GetHotPoint() const;
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="getpane"></a>  CPaneFrameWnd::GetPane

미니 프레임 창에 포함된 창을 반환합니다.

```
virtual CWnd* GetPane() const;
```

### <a name="return-value"></a>반환 값

미니 프레임 창 없는 창을 포함 하는 경우 NULL을 미니 프레임에 포함 된 창입니다.

### <a name="remarks"></a>설명

##  <a name="getpanecount"></a>  CPaneFrameWnd::GetPaneCount

미니 프레임 창에 포함된 창 수를 반환합니다.

```
virtual int GetPaneCount() const;
```

### <a name="return-value"></a>반환 값

미니 프레임 창의 창이 횟수입니다. 이 값은 0 일 수 있습니다.

### <a name="remarks"></a>설명

##  <a name="getparent"></a>  CPaneFrameWnd::GetParent

```
CWnd* GetParent();
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="getpinstate"></a>  CPaneFrameWnd::GetPinState

```
BOOL GetPinState() const;
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="getrecentfloatingrect"></a>  CPaneFrameWnd::GetRecentFloatingRect

```
CRect GetRecentFloatingRect() const;
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="getvisiblepanecount"></a>  CPaneFrameWnd::GetVisiblePaneCount

미니 프레임 창에 포함된 표시 창 수를 반환합니다.

```
virtual int GetVisiblePaneCount() const;
```

### <a name="return-value"></a>반환 값

표시 창 수를 지정 합니다.

### <a name="remarks"></a>설명

##  <a name="hittest"></a>  CPaneFrameWnd::HitTest

미니 프레임 창의 어떤 부분이 지정된 지점에 있는지 결정합니다.

```
virtual LRESULT HitTest(
    CPoint point,
    BOOL bDetectCaption);
```

### <a name="parameters"></a>매개 변수

*point*<br/>
[in] 테스트할 지점입니다.

*bDetectCaption*<br/>
[in] TRUE 이면 캡션에 대해 시점을 확인 합니다. FALSE 이면 캡션을 무시 합니다.

### <a name="return-value"></a>반환 값

다음 값 중 하나입니다.

|값|의미|
|-----------|-------------|
|HTNOWHERE|미니 프레임 창 외부 점은입니다.|
|HTCLIENT|클라이언트 영역에 점이 합니다.|
|HTCAPTION|캡션에 점은입니다.|
|HTTOP|맨 위에 있는 점은입니다.|
|HTTOPLEFT|점은 맨 왼쪽에 있습니다.|
|HTTOPRIGHT|오른쪽 맨 위에 있는 점은입니다.|
|HTLEFT|점은 왼쪽에 있습니다.|
|HTRIGHT|점은 오른쪽에 있습니다.|
|HTBOTTOM|점은 맨 아래에 있습니다.|
|HTBOTTOMLEFT|점은 왼쪽 아래에 있습니다.|
|HTBOTTOMRIGHT|점은 오른쪽 아래에 있습니다.|

##  <a name="iscaptured"></a>  CPaneFrameWnd::IsCaptured

```
BOOL IsCaptured() const;
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="isdelayshow"></a>  CPaneFrameWnd::IsDelayShow

```
BOOL IsDelayShow() const;
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="isrolldown"></a>  CPaneFrameWnd::IsRollDown

미니 프레임 창이 롤다운되어야 하는지 여부를 결정합니다.

```
virtual BOOL IsRollDown() const;
```

### <a name="return-value"></a>반환 값

미니 프레임 창을 아래로; 롤포워드해야 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 미니 프레임 창을 롤 다운 되어야 하는지 여부를 확인 하기 위해 프레임 워크에서 호출 됩니다. 롤업/롤 다운 기능 AFX_CBRS_AUTO_ROLLUP 플래그가 있는 하나 이상의 창을 포함 하는 경우 미니 프레임 창에 대 한 활성화 됩니다. 이 플래그는 창이 만들어질 때 설정 됩니다. 자세한 내용은 [cbasepane:: Createex](../../mfc/reference/cbasepane-class.md#createex)합니다.

기본적으로 프레임 창이 롤 다운 되어야 하는지 여부를 확인 하는 미니 프레임 창 경계 사각형 안에 마우스 포인터 인지 여부를 확인 합니다. 파생된 클래스에서이 동작을 재정의할 수 있습니다.

##  <a name="isrollup"></a>  CPaneFrameWnd::IsRollUp

미니 프레임 창이 롤업되어야 하는지 여부를 결정합니다.

```
virtual BOOL IsRollUp() const;
```

### <a name="return-value"></a>반환 값

미니 프레임 창을; 롤포워드해야 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 지 여부를 미니 프레임 창이 롤업 되어야 확인 하기 위해 프레임 워크에서 호출 됩니다. 롤업/롤 다운 기능 AFX_CBRS_AUTO_ROLLUP 플래그가 있는 하나 이상의 창을 포함 하는 경우 미니 프레임 창에 대 한 활성화 됩니다. 이 플래그는 창이 만들어질 때 설정 됩니다. 자세한 내용은 [cbasepane:: Createex](../../mfc/reference/cbasepane-class.md#createex)합니다.

기본적으로 프레임 창이 롤업 되어야 하는지 여부를 확인 하는 미니 프레임 창 경계 사각형 안에 마우스 포인터 인지 여부를 확인 합니다. 파생된 클래스에서이 동작을 재정의할 수 있습니다.

##  <a name="killdockingtimer"></a>  CPaneFrameWnd::KillDockingTimer

도킹 타이머를 중지합니다.

```
void KillDockingTimer();
```

##  <a name="loadstate"></a>  CPaneFrameWnd::LoadState

레지스트리에서 창의 상태를 로드합니다.

```
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>매개 변수

*lpszProfileName*<br/>
[in] 프로필 이름입니다.

*uiID*<br/>
[in] 창 ID

### <a name="return-value"></a>반환 값

창 상태를 성공적으로 로드 된 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

##  <a name="m_busesavebits"></a>  CPaneFrameWnd::m_bUseSaveBits

CS_SAVEBITS 클래스 스타일이 적용 된 창 클래스를 등록할지 여부를 지정 합니다.

```
AFX_IMPORT_DATA static BOOL m_bUseSaveBits;
```

### <a name="remarks"></a>설명

이 정적 멤버 CS_SAVEBITS 스타일이 적용 된 미니 프레임 창 클래스를 등록 하려면 true를 설정 합니다. 이 줄일 수 있습니다 미니 프레임 창을 끌 때 깜박임 합니다.

##  <a name="onbeforedock"></a>  CPaneFrameWnd::OnBeforeDock

도킹 가능한지 여부를 결정합니다.

```
virtual BOOL OnBeforeDock();
```

### <a name="return-value"></a>반환 값

도킹 가능한; 이면 TRUE입니다. 그렇지 않으면 FALSE입니다.

##  <a name="oncheckrollstate"></a>  CPaneFrameWnd::OnCheckRollState

미니 프레임 창이 롤업 또는 롤다운되어야 하는지를 결정합니다.

```
virtual void OnCheckRollState();
```

### <a name="remarks"></a>설명

이 메서드는 위나 아래로 미니 프레임 창을 롤백할 수 있는지 여부를 확인 하기 위해 프레임 워크에서 호출 됩니다.

기본적으로 프레임 워크는 다음과 같이 호출 됩니다. [CPaneFrameWnd::IsRollUp](#isrollup) 하 고 [CPaneFrameWnd::IsRollDown](#isrolldown) 및 방금 확장 또는 미니 프레임 창을 복원 합니다. 다른 시각 효과 사용 하 여 파생된 클래스에서이 메서드를 재정의할 수 있습니다.

##  <a name="ondocktorecentpos"></a>  CPaneFrameWnd::OnDockToRecentPos

가장 최근 위치에 미니 프레임 창을 도킹합니다.

```
virtual void OnDockToRecentPos();
```

##  <a name="ondrawborder"></a>  CPaneFrameWnd::OnDrawBorder

미니 프레임 창의 테두리를 그립니다.

```
virtual void OnDrawBorder(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 테두리를 그리는 데 디바이스 컨텍스트입니다.

### <a name="remarks"></a>설명

이 메서드는 미니 프레임 창의 테두리를 그리는 데 프레임 워크에서 호출 됩니다.

##  <a name="onkillrolluptimer"></a>  CPaneFrameWnd::OnKillRollUpTimer

롤업 타이머를 중지합니다.

```
virtual void OnKillRollUpTimer();
```

##  <a name="onmovepane"></a>  CPaneFrameWnd::OnMovePane

지정된 오프셋만큼 미니 프레임 창을 이동합니다.

```
virtual void OnMovePane(
    CPane* pBar,
    CPoint ptOffset);
```

### <a name="parameters"></a>매개 변수

*pBar*<br/>
[in] 창 (무시 됨)에 대 한 포인터입니다.

*ptOffset*<br/>
[in] 창을 이동에 사용 되는 오프셋입니다.

##  <a name="onpanerecalclayout"></a>  CPaneFrameWnd::OnPaneRecalcLayout

미니 프레임 창 내에서 창 레이아웃을 조정합니다.

```
virtual void OnPaneRecalcLayout();
```

### <a name="remarks"></a>설명

미니 프레임 창 내에서 창 레이아웃을 조정 해야 하는 경우이 메서드를 호출 하는 프레임 워크입니다.

기본적으로 창에는 미니 프레임 창의 전체 클라이언트 영역에 배치 됩니다.

##  <a name="onsetrolluptimer"></a>  CPaneFrameWnd::OnSetRollUpTimer

롤업 타이머를 설정합니다.

```
virtual void OnSetRollUpTimer();
```

##  <a name="onshowpane"></a>  CPaneFrameWnd::OnShowPane

미니 프레임 창의 창이 숨겨지거나 표시될 때 프레임워크에서 호출됩니다.

```
virtual void OnShowPane(
    CDockablePane* pBar,
    BOOL bShow);
```

### <a name="parameters"></a>매개 변수

*pBar*<br/>
[in] 되는 창 표시 또는 숨겨집니다.

*bShow*<br/>
[in] 창으로 표시 되는 경우 TRUE입니다. 창에는 숨겨진 경우 FALSE입니다.

### <a name="remarks"></a>설명

미니 프레임 창의 창이 표시 하거나 숨길 때 프레임 워크에서 호출 됩니다. 기본 구현은 아무 작업도 수행하지 않습니다.

##  <a name="pin"></a>  CPaneFrameWnd::Pin

```
void Pin(BOOL bPin = TRUE);
```

### <a name="parameters"></a>매개 변수

[in] *bPin*<br/>

### <a name="remarks"></a>설명

##  <a name="panefrompoint"></a>  CPaneFrameWnd::PaneFromPoint

미니 프레임 창 안에 사용자가 제공한 지점을 포함하는 경우 창을 반환합니다.

```
virtual CBasePane* PaneFromPoint(
    CPoint point,
    int nSensitivity,
    BOOL bCheckVisibility);
```

### <a name="parameters"></a>매개 변수

*point*<br/>
[in] 지점을 화면 좌표에서 사용자를 클릭 합니다.

*nSensitivity*<br/>
[in] 이 매개 변수 사용 되지 않습니다.

*bCheckVisibility*<br/>
[in] 표시 창만 반환 되어야 함을;을 지정 하려면 TRUE 그렇지 않으면 FALSE입니다.

### <a name="return-value"></a>반환 값

사용자가 클릭 하 고 창 또는 없습니다 창의 해당 위치에 있는 경우 NULL입니다.

### <a name="remarks"></a>설명

지정된 된 점을 포함 하는 창을 가져오려면이 메서드를 호출 합니다.

##  <a name="redrawall"></a>  CPaneFrameWnd::RedrawAll

모든 미니 프레임 창을 다시 그립니다.

```
static void RedrawAll();
```

### <a name="remarks"></a>설명

이 메서드를 호출 하 여 모든 미니 프레임 창을 업데이트 [CWnd::RedrawWindow](../../mfc/reference/cwnd-class.md#redrawwindow) 각 창에 대 한 합니다.

##  <a name="removenonvalidpanes"></a>  CPaneFrameWnd::RemoveNonValidPanes

잘못된 창을 제거하기 위해 프레임워크에서 호출됩니다.

```
virtual void RemoveNonValidPanes();
```

##  <a name="removepane"></a>  CPaneFrameWnd::RemovePane

미니 프레임 창에서 창을 제거합니다.

```
virtual void RemovePane(
    CBasePane* pWnd,
    BOOL bDestroy = FALSE,
    BOOL bNoDelayedDestroy = FALSE);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
[in] 제거할 창에 대 한 포인터입니다.

*bDestroy*<br/>
[in] 미니 프레임 창을 처리 방식을 지정 합니다. 하는 경우 *bDestroy* 가 TRUE 이면이 메서드 즉시 미니 프레임 창을 소멸 시킵니다. FALSE 인 경우이 메서드를 특정 지연 후 미니 프레임 창을 소멸 시킵니다.

*bNoDelayedDestroy*<br/>
[in] TRUE 이면 지연된 소멸 비활성화 됩니다. FALSE 인 경우 지연 된 소멸 사용 됩니다.

### <a name="remarks"></a>설명

프레임 워크는 특정 지연 후 즉시 또는 미니 프레임 창을 손상 될 수 있습니다. 미니 프레임 창 소멸을 지연 하려는 경우 FALSE를 전달 합니다 *bNoDelayedDestroy* 매개 변수입니다. 지연 된 소멸 프레임 워크 AFX_WM_CHECKEMPTYMINIFRAME 메시지를 처리할 때 발생 합니다.

##  <a name="replacepane"></a>  CPaneFrameWnd::ReplacePane

한 창을 다른 창으로 대체합니다.

```
virtual void ReplacePane(
    CBasePane* pBarOrg,
    CBasePane* pBarReplaceWith);
```

### <a name="parameters"></a>매개 변수

*pBarOrg*<br/>
[in] 원래 창에 대 한 포인터입니다.

*pBarReplaceWith*<br/>
[in] 원래 창을 대체 하는 창에 대 한 포인터입니다.

##  <a name="savestate"></a>  CPaneFrameWnd::SaveState

레지스트리에 창의 상태를 저장합니다.

```
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>매개 변수

*lpszProfileName*<br/>
[in] 프로필 이름입니다.

*uiID*<br/>
[in] 창 ID

### <a name="return-value"></a>반환 값

TRUE 이면 창 상태를 저장 했습니다. 그렇지 않으면 FALSE입니다.

##  <a name="setcaptionbuttons"></a>  CPaneFrameWnd::SetCaptionButtons

캡션 단추를 설정합니다.

```
virtual void SetCaptionButtons(DWORD dwButtons);
```

### <a name="parameters"></a>매개 변수

*dwButtons*<br/>
[in] 다음 값의 비트 OR 조합 합니다.

- AFX_CAPTION_BTN_CLOSE

- AFX_CAPTION_BTN_PIN

- AFX_CAPTION_BTN_MENU

- AFX_CAPTION_BTN_CUSTOMIZE

##  <a name="setdelayshow"></a>  CPaneFrameWnd::SetDelayShow

```
void SetDelayShow(BOOL bDelayShow);
```

### <a name="parameters"></a>매개 변수

[in] *bDelayShow*<br/>

### <a name="remarks"></a>설명

##  <a name="setdockingmanager"></a>  CPaneFrameWnd::SetDockingManager

```
void SetDockingManager(CDockingManager* pManager);
```

### <a name="parameters"></a>매개 변수

[in] *pManager*<br/>

### <a name="remarks"></a>설명

##  <a name="setdockingtimer"></a>  CPaneFrameWnd::SetDockingTimer

도킹 타이머를 설정합니다.

```
void SetDockingTimer(UINT nTimeOut);
```

### <a name="parameters"></a>매개 변수

*nTimeOut*<br/>
[in] 시간 제한 값 (밀리초)입니다.

##  <a name="setdockstate"></a>  CPaneFrameWnd::SetDockState

도킹 상태를 설정합니다.

```
virtual void SetDockState(CDockingManager* pDockManager);
```

### <a name="parameters"></a>매개 변수

*pDockManager*<br/>
[in] 도킹 관리자에 대 한 포인터입니다.

##  <a name="sethotpoint"></a>  CPaneFrameWnd::SetHotPoint

```
void SetHotPoint(CPoint& ptNew);
```

### <a name="parameters"></a>매개 변수

[in] *ptNew*<br/>

### <a name="remarks"></a>설명

##  <a name="setpredockstate"></a>  CPaneFrameWnd::SetPreDockState

사전 도킹 상태를 설정하기 위해 프레임워크에서 호출됩니다.

```
virtual BOOL SetPreDockState(
    AFX_PREDOCK_STATE preDockState,
    CBasePane* pBarToDock = NULL,
    AFX_DOCK_METHOD dockMethod = DM_MOUSE);
```

### <a name="parameters"></a>매개 변수

*preDockState*<br/>
[in] 가능한 값:

- PDS_NOTHING,

- PDS_DOCK_REGULAR,

- PDS_DOCK_TO_TAB

*pBarToDock*<br/>
[in] 도킹 창에 대 한 포인터입니다.

*dockMethod*<br/>
[in] 도킹 메서드입니다. (이 매개 변수가 무시 됩니다.)

### <a name="return-value"></a>반환 값

TRUE 이면 미니 프레임 창을 도킹; 되지 않습니다. 고정 되어 있는 경우 FALSE입니다.

##  <a name="sizetocontent"></a>  CPaneFrameWnd::SizeToContent

미니 프레임 창의 크기를 조정 하는 포함 된 창에 해당 하는 것입니다.

```
virtual void SizeToContent();
```

### <a name="remarks"></a>설명

포함 된 창의 크기를 미니 프레임 창의 크기를 조정 하려면이 메서드를 호출 합니다.

##  <a name="starttearoff"></a>  CPaneFrameWnd::StartTearOff

메뉴를 분리합니다.

```
BOOL StartTearOff(CMFCPopu* pMenu);
```

### <a name="parameters"></a>매개 변수

*pMenu*<br/>
[in] 메뉴에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 TRUE입니다. 그렇지 않으면 FALSE입니다.

##  <a name="storerecentdocksiteinfo"></a>  CPaneFrameWnd::StoreRecentDockSiteInfo

```
virtual void StoreRecentDockSiteInfo(CPane* pBar);
```

### <a name="parameters"></a>매개 변수

[in] *pBar*<br/>

### <a name="remarks"></a>설명

##  <a name="storerecenttabrelatedinfo"></a>  CPaneFrameWnd::StoreRecentTabRelatedInfo

```
virtual void StoreRecentTabRelatedInfo(
    CDockablePane* pDockingBar,
    CDockablePane* pTabbedBar);
```

### <a name="parameters"></a>매개 변수

[in] *pDockingBar*<br/>
[in] *pTabbedBar*<br/>

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)
