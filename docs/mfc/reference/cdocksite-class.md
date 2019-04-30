---
title: CDockSite Class
ms.date: 10/18/2018
f1_keywords:
- CDockSite
- AFXDOCKSITE/CDockSite
- AFXDOCKSITE/CDockSite::AddRow
- AFXDOCKSITE/CDockSite::AdjustDockingLayout
- AFXDOCKSITE/CDockSite::AdjustLayout
- AFXDOCKSITE/CDockSite::AlignDockSite
- AFXDOCKSITE/CDockSite::CalcFixedLayout
- AFXDOCKSITE/CDockSite::CanAcceptPane
- AFXDOCKSITE/CDockSite::CreateEx
- AFXDOCKSITE/CDockSite::CreateRow
- AFXDOCKSITE/CDockSite::DockPane
- AFXDOCKSITE/CDockSite::DoesAllowDynInsertBefore
- AFXDOCKSITE/CDockSite::FindRowIndex
- AFXDOCKSITE/CDockSite::FixupVirtualRects
- AFXDOCKSITE/CDockSite::GetDockSiteID
- AFXDOCKSITE/CDockSite::GetDockSiteRowsList
- AFXDOCKSITE/CDockSite::IsAccessibilityCompatible
- AFXDOCKSITE/CDockSite::IsDragMode
- AFXDOCKSITE/CDockSite::IsLastRow
- AFXDOCKSITE/CDockSite::IsRectWithinDockSite
- AFXDOCKSITE/CDockSite::IsResizable
- AFXDOCKSITE/CDockSite::MovePane
- AFXDOCKSITE/CDockSite::OnInsertRow
- AFXDOCKSITE/CDockSite::OnRemoveRow
- AFXDOCKSITE/CDockSite::OnResizeRow
- AFXDOCKSITE/CDockSite::OnSetWindowPos
- AFXDOCKSITE/CDockSite::OnShowRow
- AFXDOCKSITE/CDockSite::OnSizeParent
- AFXDOCKSITE/CDockSite::PaneFromPoint
- AFXDOCKSITE/CDockSite::DockPaneLeftOf
- AFXDOCKSITE/CDockSite::FindPaneByID
- AFXDOCKSITE/CDockSite::GetPaneList
- AFXDOCKSITE/CDockSite::RectSideFromPoint
- AFXDOCKSITE/CDockSite::RemovePane
- AFXDOCKSITE/CDockSite::RemoveRow
- AFXDOCKSITE/CDockSite::ReplacePane
- AFXDOCKSITE/CDockSite::RepositionPanes
- AFXDOCKSITE/CDockSite::ResizeDockSite
- AFXDOCKSITE/CDockSite::ResizeRow
- AFXDOCKSITE/CDockSite::ShowPane
- AFXDOCKSITE/CDockSite::ShowRow
- AFXDOCKSITE/CDockSite::SwapRows
helpviewer_keywords:
- CDockSite [MFC], AddRow
- CDockSite [MFC], AdjustDockingLayout
- CDockSite [MFC], AdjustLayout
- CDockSite [MFC], AlignDockSite
- CDockSite [MFC], CalcFixedLayout
- CDockSite [MFC], CanAcceptPane
- CDockSite [MFC], CreateEx
- CDockSite [MFC], CreateRow
- CDockSite [MFC], DockPane
- CDockSite [MFC], DoesAllowDynInsertBefore
- CDockSite [MFC], FindRowIndex
- CDockSite [MFC], FixupVirtualRects
- CDockSite [MFC], GetDockSiteID
- CDockSite [MFC], GetDockSiteRowsList
- CDockSite [MFC], IsAccessibilityCompatible
- CDockSite [MFC], IsDragMode
- CDockSite [MFC], IsLastRow
- CDockSite [MFC], IsRectWithinDockSite
- CDockSite [MFC], IsResizable
- CDockSite [MFC], MovePane
- CDockSite [MFC], OnInsertRow
- CDockSite [MFC], OnRemoveRow
- CDockSite [MFC], OnResizeRow
- CDockSite [MFC], OnSetWindowPos
- CDockSite [MFC], OnShowRow
- CDockSite [MFC], OnSizeParent
- CDockSite [MFC], PaneFromPoint
- CDockSite [MFC], DockPaneLeftOf
- CDockSite [MFC], FindPaneByID
- CDockSite [MFC], GetPaneList
- CDockSite [MFC], RectSideFromPoint
- CDockSite [MFC], RemovePane
- CDockSite [MFC], RemoveRow
- CDockSite [MFC], ReplacePane
- CDockSite [MFC], RepositionPanes
- CDockSite [MFC], ResizeDockSite
- CDockSite [MFC], ResizeRow
- CDockSite [MFC], ShowPane
- CDockSite [MFC], ShowRow
- CDockSite [MFC], SwapRows
ms.assetid: 0fcfff79-5f50-4281-b2de-a55653bbea40
ms.openlocfilehash: ccd1bc115f92e0c2605fe5f587a0567f672c6c09
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391168"
---
# <a name="cdocksite-class"></a>CDockSite Class

더 자세한 내용은 Visual Studio 설치의 **VC\\atlmfc\\src\\mfc** 폴더에 있는 소스 코드를 참조하세요.

[CPane Class](../../mfc/reference/cpane-class.md) 에서 파생되는 창을 행 집합으로 배열하기 위한 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CDockSite: public CBasePane
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CDockSite::AddRow](#addrow)||
|[CDockSite::AdjustDockingLayout](#adjustdockinglayout)|(재정의 [cbasepane:: Adjustdockinglayout](../../mfc/reference/cbasepane-class.md#adjustdockinglayout).)|
|[CDockSite::AdjustLayout](#adjustlayout)|(재정의 [cbasepane:: Adjustlayout](../../mfc/reference/cbasepane-class.md#adjustlayout).)|
|[CDockSite::AlignDockSite](#aligndocksite)||
|[CDockSite::CalcFixedLayout](#calcfixedlayout)|(재정의 [cbasepane:: Calcfixedlayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|
|[CDockSite::CanAcceptPane](#canacceptpane)|(재정의 [cbasepane:: Canacceptpane](../../mfc/reference/cbasepane-class.md#canacceptpane).)|
|[CDockSite::CreateEx](#createex)|(재정의 [cbasepane:: Createex](../../mfc/reference/cbasepane-class.md#createex).)|
|[CDockSite::CreateRow](#createrow)||
|[CDockSite::DockPane](#dockpane)|(재정의 [cbasepane:: Dockpane](../../mfc/reference/cbasepane-class.md#dockpane).)|
|[CDockSite::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|(재정의 [cbasepane:: Doesallowdyninsertbefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|
|[CDockSite::FindRowIndex](#findrowindex)||
|[CDockSite::FixupVirtualRects](#fixupvirtualrects)||
|[CDockSite::GetDockSiteID](#getdocksiteid)||
|[CDockSite::GetDockSiteRowsList](#getdocksiterowslist)||
|[CDockSite::IsAccessibilityCompatible](#isaccessibilitycompatible)|( `CBasePane::IsAccessibilityCompatible`을 재정의합니다.)|
|[CDockSite::IsDragMode](#isdragmode)||
|[CDockSite::IsLastRow](#islastrow)||
|[CDockSite::IsRectWithinDockSite](#isrectwithindocksite)||
|[CDockSite::IsResizable](#isresizable)|(재정의 [cbasepane:: Isresizable](../../mfc/reference/cbasepane-class.md#isresizable).)|
|[CDockSite::MovePane](#movepane)||
|[CDockSite::OnInsertRow](#oninsertrow)||
|[CDockSite::OnRemoveRow](#onremoverow)||
|[CDockSite::OnResizeRow](#onresizerow)||
|[CDockSite::OnSetWindowPos](#onsetwindowpos)||
|[CDockSite::OnShowRow](#onshowrow)||
|[CDockSite::OnSizeParent](#onsizeparent)||
|[CDockSite::PaneFromPoint](#panefrompoint)|주어진 매개 변수로 지정된 지점에서 도킹 사이트에 도킹된 창을 반환합니다.|
|[CDockSite::DockPaneLeftOf](#dockpaneleftof)|창을 다른 창의 왼쪽에 도킹합니다.|
|[CDockSite::FindPaneByID](#findpanebyid)|지정된 ID로 식별되는 창을 반환합니다.|
|[CDockSite::GetPaneList](#getpanelist)|도킹 사이트에 도킹된 창 목록을 반환합니다.|
|[CDockSite::RectSideFromPoint](#rectsidefrompoint)||
|[CDockSite::RemovePane](#removepane)||
|[CDockSite::RemoveRow](#removerow)||
|[CDockSite::ReplacePane](#replacepane)||
|[CDockSite::RepositionPanes](#repositionpanes)||
|[CDockSite::ResizeDockSite](#resizedocksite)||
|[CDockSite::ResizeRow](#resizerow)||
|[CDockSite::ShowPane](#showpane)|창을 표시합니다.|
|[CDockSite::ShowRow](#showrow)||
|[CDockSite::SwapRows](#swaprows)||

## <a name="remarks"></a>설명

프레임 워크를 만듭니다 `CDockSite` 개체를 호출 하는 경우 자동으로 [CFrameWndEx::EnableDocking](../../mfc/reference/cframewndex-class.md#enabledocking)합니다. 도킹 사이트 창은 주 프레임 창에서 클라이언트 영역의 가장자리에 배치됩니다.

일반적으로 수행할 필요가 없습니다 때문에 도킹 사이트에서 제공 하는 서비스 호출 [CFrameWndEx 클래스](../../mfc/reference/cframewndex-class.md) 이러한 서비스를 처리 합니다.

## <a name="example"></a>예제

다음 예제에서는 `CDockSite` 클래스의 개체를 만드는 방법을 보여 줍니다.

[!code-cpp[NVC_MFC_RibbonApp#27](../../mfc/reference/codesnippet/cpp/cdocksite-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md) [CDockSite](../../mfc/reference/cdocksite-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxDockSite.h

##  <a name="addrow"></a>  CDockSite::AddRow

```
CDockingPanesRow* AddRow(
    POSITION pos,
    int nHeight);
```

### <a name="parameters"></a>매개 변수

[in] *pos*<br/>

[in] *nHeight*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="adjustdockinglayout"></a>  CDockSite::AdjustDockingLayout

```
virtual void AdjustDockingLayout();
```

### <a name="remarks"></a>설명

##  <a name="adjustlayout"></a>  CDockSite::AdjustLayout

```
virtual void AdjustLayout();
```

### <a name="remarks"></a>설명

##  <a name="aligndocksite"></a>  CDockSite::AlignDockSite

```
void AlignDockSite(
    const CRect& rectToAlignBy,
    CRect& rectResult,
    BOOL bMoveImmediately);
```

### <a name="parameters"></a>매개 변수

[in] *rectToAlignBy*<br/>

[in] *rectResult*<br/>

[in] *bMoveImmediately*<br/>

### <a name="remarks"></a>설명

##  <a name="calcfixedlayout"></a>  CDockSite::CalcFixedLayout

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>매개 변수

[in] *bStretch*<br/>

[in] *bHorz*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="canacceptpane"></a>  CDockSite::CanAcceptPane

```
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;
```

### <a name="parameters"></a>매개 변수

[in] *pBar*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="createex"></a>  CDockSite::CreateEx

```
virtual BOOL CreateEx(
    DWORD dwStyleEx,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    DWORD dwControlBarStyle,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>매개 변수

[in] *dwStyleEx*<br/>

[in] *dwStyle*<br/>

[in] *rect*<br/>

[in] *pParentWnd*<br/>

[in] *dwControlBarStyle*<br/>

[in] *pContext*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="createrow"></a>  CDockSite::CreateRow

```
virtual CDockingPanesRow* CreateRow(
    CDockSite* pParentDockBar,
    int nOffset,
    int nRowHeight);
```

### <a name="parameters"></a>매개 변수

[in] *pParentDockBar*<br/>

[in] *nOffset*<br/>

[in] *nRowHeight*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="dockpane"></a>  CDockSite::DockPane

```
virtual void DockPane(
    CPane* pWnd,
    AFX_DOCK_METHOD dockMethod,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>매개 변수

[in] *pWnd*<br/>

[in] *dockMethod*<br/>

[in] *lpRect*<br/>

### <a name="remarks"></a>설명

##  <a name="dockpaneleftof"></a>  CDockSite::DockPaneLeftOf

창을 다른 창의 왼쪽에 도킹합니다.

```
virtual BOOL DockPaneLeftOf(
    CPane* pBarToDock,
    CPane* pTargetBar);
```

### <a name="parameters"></a>매개 변수

*pBarToDock*<br/>
[out에서] 왼쪽에 도킹 창에 대 한 포인터 *pTargetBar*합니다.

*pTargetBar*<br/>
[out에서] 대상 창에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

창이 도킹 되어 있는 했으면 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

##  <a name="doesallowdyninsertbefore"></a>  CDockSite::DoesAllowDynInsertBefore

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="findpanebyid"></a>  CDockSite::FindPaneByID

지정된 된 ID 사용 하 여 창을 반환 합니다.

```
CPane* FindPaneByID(UINT nID);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
[in] 찾을 창의 명령 ID입니다.

### <a name="return-value"></a>반환 값

창 없는 경우 NULL을 지정 된 명령 ID를 사용 하 여 창에 대 한 포인터입니다.

### <a name="remarks"></a>설명

##  <a name="findrowindex"></a>  CDockSite::FindRowIndex

```
int FindRowIndex(CDockingPanesRow* pRow);
```

### <a name="parameters"></a>매개 변수

[in] *pRow*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="fixupvirtualrects"></a>  CDockSite::FixupVirtualRects

```
virtual void FixupVirtualRects();
```

### <a name="remarks"></a>설명

##  <a name="getdocksiteid"></a>  CDockSite::GetDockSiteID

```
virtual UINT GetDockSiteID() const;
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="getdocksiterowslist"></a>  CDockSite::GetDockSiteRowsList

```
const CObList& GetDockSiteRowsList() const;
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="getpanelist"></a>  CDockSite::GetPaneList

도킹 사이트에 도킹 된 창 목록을 반환 합니다.

```
const CObList& GetPaneList() const;
```

### <a name="return-value"></a>반환 값

에 대 한 읽기 전용 참조 창의 목록에서 도킹 모음의 현재 도킹 합니다.

##  <a name="isaccessibilitycompatible"></a>  CDockSite::IsAccessibilityCompatible

```
virtual BOOL IsAccessibilityCompatible();
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="isdragmode"></a>  CDockSite::IsDragMode

```
virtual BOOL IsDragMode() const;
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="islastrow"></a>  CDockSite::IsLastRow

```
bool IsLastRow(CDockingPanesRow* pRow) const;
```

### <a name="parameters"></a>매개 변수

[in] *pRow*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="isrectwithindocksite"></a>  CDockSite::IsRectWithinDockSite

```
BOOL IsRectWithinDockSite(
    CRect rect,
    CPoint& ptDelta);
```

### <a name="parameters"></a>매개 변수

[in] *rect*<br/>

[in] *ptDelta*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="isresizable"></a>  CDockSite::IsResizable

```
virtual BOOL IsResizable() const;
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="movepane"></a>  CDockSite::MovePane

```
virtual BOOL MovePane(
    CPane* pWnd,
    UINT nFlags,
    CPoint ptOffset);
```

### <a name="parameters"></a>매개 변수

[in] *pWnd*<br/>

[in] *nFlags*<br/>

[in] *ptOffset*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="oninsertrow"></a>  CDockSite::OnInsertRow

```
virtual void OnInsertRow(POSITION pos);
```

### <a name="parameters"></a>매개 변수

[in] *pos*<br/>

### <a name="remarks"></a>설명

##  <a name="onremoverow"></a>  CDockSite::OnRemoveRow

```
virtual void OnRemoveRow(
    POSITION pos,
    BOOL bByShow = FALSE);
```

### <a name="parameters"></a>매개 변수

[in] *pos*<br/>

[in] *bByShow*<br/>

### <a name="remarks"></a>설명

##  <a name="onresizerow"></a>  CDockSite::OnResizeRow

```
virtual int OnResizeRow(
    CDockingPanesRow* pRowToResize,
    int nOffset);
```

### <a name="parameters"></a>매개 변수

[in] *pRowToResize*<br/>

[in] *nOffset*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="onsizeparent"></a>  CDockSite::OnSizeParent

```
virtual void OnSizeParent(
    CRect& rectAvailable,
    UINT nSide,
    BOOL bExpand,
    int nOffset);
```

### <a name="parameters"></a>매개 변수

[in] *rectAvailable*<br/>

[in] *nSide*<br/>

[in] *bExpand*<br/>

[in] *nOffset*<br/>

### <a name="remarks"></a>설명

##  <a name="onsetwindowpos"></a>  CDockSite::OnSetWindowPos

```
virtual BOOL OnSetWindowPos(
    const CWnd* pWndInsertAfter,
    const CRect& rectWnd,
    UINT nFlags);
```

### <a name="parameters"></a>매개 변수

[in] *pWndInsertAfter*<br/>

[in] *rectWnd*<br/>

[in] *nFlags*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="onshowrow"></a>  CDockSite::OnShowRow

```
virtual void OnShowRow(
    POSITION pos,
    BOOL bShow);
```

### <a name="parameters"></a>매개 변수

[in] *pos*<br/>

[in] *bShow*<br/>

### <a name="remarks"></a>설명

##  <a name="panefrompoint"></a>  CDockSite::PaneFromPoint

주어진 매개 변수로 지정된 지점에서 도킹 사이트에 도킹된 창을 반환합니다.

```
virtual CPane* PaneFromPoint(CPoint pt);
```

### <a name="parameters"></a>매개 변수

*pt*<br/>
[in] 시점, 검색할 창에 대 한 화면 좌표입니다.

### <a name="return-value"></a>반환 값

창 없는 지정된 된 지점에 있는 경우 NULL을 지정 된 위치에 있는 창에 대 한 포인터입니다.

### <a name="remarks"></a>설명

##  <a name="rectsidefrompoint"></a>  CDockSite::RectSideFromPoint

```
static int __stdcall RectSideFromPoint(
    const CRect& rect,
    const CPoint& point);
```

### <a name="parameters"></a>매개 변수

[in] *rect*<br/>

[in] *point*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="removepane"></a>  CDockSite::RemovePane

```
virtual void RemovePane(
    CPane* pWnd,
    AFX_DOCK_METHOD dockMethod);
```

### <a name="parameters"></a>매개 변수

[in] *pWnd*<br/>

[in] *dockMethod*<br/>

### <a name="remarks"></a>설명

##  <a name="removerow"></a>  CDockSite::RemoveRow

```
void RemoveRow(CDockingPanesRow* pRow);
```

### <a name="parameters"></a>매개 변수

[in] *pRow*<br/>

### <a name="remarks"></a>설명

##  <a name="replacepane"></a>  CDockSite::ReplacePane

```
BOOL ReplacePane(
    CPane* pOldBar,
    CPane* pNewBar);
```

### <a name="parameters"></a>매개 변수

[in] *pOldBar*<br/>

[in] *pNewBar*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="repositionpanes"></a>  CDockSite::RepositionPanes

```
virtual void RepositionPanes(CRect& rectNewClientArea);
```

### <a name="parameters"></a>매개 변수

[in] *rectNewClientArea*<br/>

### <a name="remarks"></a>설명

##  <a name="resizedocksite"></a>  CDockSite::ResizeDockSite

```
void ResizeDockSite(
    int nNewWidth,
    int nNewHeight);
```

### <a name="parameters"></a>매개 변수

[in] *nNewWidth*<br/>

[in] *nNewHeight*<br/>

### <a name="remarks"></a>설명

##  <a name="resizerow"></a>  CDockSite::ResizeRow

```
int ResizeRow(
    CDockingPanesRow* pRow,
    int nNewSize,
    BOOL bAdjustLayout = TRUE);
```

### <a name="parameters"></a>매개 변수

[in] *pRow*<br/>

[in] *nNewSize*<br/>

[in] *bAdjustLayout*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="showpane"></a>  CDockSite::ShowPane

창을 표시합니다.

```
virtual BOOL ShowPane(
    CBasePane* pBar,
    BOOL bShow,
    BOOL bDelay,
    BOOL bActivate);
```

### <a name="parameters"></a>매개 변수

*pBar*<br/>
[out에서] 표시 하거나 숨길 수의 창에 대 한 포인터입니다.

*bShow*<br/>
[in] 창에 표시할; 임을 지정. 창에 표시 되지 않도록 임을 지정 하려면 FALSE입니다.

*bDelay*<br/>
[in] 창 레이아웃 창으로 표시 되 후까지 지연 돼야 하는지 지정. 그렇지 않으면 FALSE입니다.

*bActivate*<br/>
[in] 이 매개 변수 사용 되지 않습니다.

### <a name="return-value"></a>반환 값

창에 성공적으로 숨기 거 나 표시할지를 하는 경우 TRUE입니다. FALSE 이면 지정한 창이 도킹 사이트에 속하지 않습니다.

### <a name="remarks"></a>설명

표시 하거나 숨기려면 도킹된 창에이 메서드를 호출 합니다. 일반적으로 호출할 필요가 없습니다 `CDockSite::ShowPane` 를 직접 부모 프레임 창에서 또는 기본 창에서 호출 되었습니다.

##  <a name="showrow"></a>  CDockSite::ShowRow

```
void ShowRow(
    CDockingPanesRow* pRow,
    BOOL bShow,
    BOOL bAdjustLayout);
```

### <a name="parameters"></a>매개 변수

[in] *pRow*<br/>

[in] *bShow*<br/>

[in] *bAdjustLayout*<br/>

### <a name="remarks"></a>설명

##  <a name="swaprows"></a>  CDockSite::SwapRows

```
void SwapRows(
    CDockingPanesRow* pFirstRow,
    CDockingPanesRow* pSecondRow);
```

### <a name="parameters"></a>매개 변수

[in] *pFirstRow*<br/>

[in] *pSecondRow*<br/>

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CBasePane 클래스](../../mfc/reference/cbasepane-class.md)
