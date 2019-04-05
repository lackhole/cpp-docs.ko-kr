---
title: CPaneDivider 클래스
ms.date: 11/04/2016
f1_keywords:
- CPaneDivider
- AFXPANEDIVIDER/CPaneDivider
- AFXPANEDIVIDER/CPaneDivider::CPaneDivider
- AFXPANEDIVIDER/CPaneDivider::AddPaneContainer
- AFXPANEDIVIDER/CPaneDivider::AddPane
- AFXPANEDIVIDER/CPaneDivider::AddRecentPane
- AFXPANEDIVIDER/CPaneDivider::CalcExpectedDockedRect
- AFXPANEDIVIDER/CPaneDivider::CalcFixedLayout
- AFXPANEDIVIDER/CPaneDivider::CheckVisibility
- AFXPANEDIVIDER/CPaneDivider::CreateEx
- AFXPANEDIVIDER/CPaneDivider::DoesAllowDynInsertBefore
- AFXPANEDIVIDER/CPaneDivider::DoesContainFloatingPane
- AFXPANEDIVIDER/CPaneDivider::FindPaneContainer
- AFXPANEDIVIDER/CPaneDivider::FindTabbedPane
- AFXPANEDIVIDER/CPaneDivider::GetDefaultWidth
- AFXPANEDIVIDER/CPaneDivider::GetFirstPane
- AFXPANEDIVIDER/CPaneDivider::GetPaneDividerStyle
- AFXPANEDIVIDER/CPaneDivider::GetRootContainerRect
- AFXPANEDIVIDER/CPaneDivider::GetWidth
- AFXPANEDIVIDER/CPaneDivider::Init
- AFXPANEDIVIDER/CPaneDivider::InsertPane
- AFXPANEDIVIDER/CPaneDivider::IsAutoHideMode
- AFXPANEDIVIDER/CPaneDivider::IsDefault
- AFXPANEDIVIDER/CPaneDivider::IsHorizontal
- AFXPANEDIVIDER/CPaneDivider::Move
- AFXPANEDIVIDER/CPaneDivider::NotifyAboutRelease
- AFXPANEDIVIDER/CPaneDivider::OnShowPane
- AFXPANEDIVIDER/CPaneDivider::ReleaseEmptyPaneContainers
- AFXPANEDIVIDER/CPaneDivider::RemovePane
- AFXPANEDIVIDER/CPaneDivider::ReplacePane
- AFXPANEDIVIDER/CPaneDivider::RepositionPanes
- AFXPANEDIVIDER/CPaneDivider::Serialize
- AFXPANEDIVIDER/CPaneDivider::SetAutoHideMode
- AFXPANEDIVIDER/CPaneDivider::SetPaneContainerManager
- AFXPANEDIVIDER/CPaneDivider::ShowWindow
- AFXPANEDIVIDER/CPaneDivider::StoreRecentDockSiteInfo
- AFXPANEDIVIDER/CPaneDivider::StoreRecentTabRelatedInfo
- AFXPANEDIVIDER/CPaneDivider::GetPanes
- AFXPANEDIVIDER/CPaneDivider::GetPaneDividers
- AFXPANEDIVIDER/CPaneDivider::m_nDefaultWidth
- AFXPANEDIVIDER/CPaneDivider::m_pSliderRTC
helpviewer_keywords:
- CPaneDivider [MFC], CPaneDivider
- CPaneDivider [MFC], AddPaneContainer
- CPaneDivider [MFC], AddPane
- CPaneDivider [MFC], AddRecentPane
- CPaneDivider [MFC], CalcExpectedDockedRect
- CPaneDivider [MFC], CalcFixedLayout
- CPaneDivider [MFC], CheckVisibility
- CPaneDivider [MFC], CreateEx
- CPaneDivider [MFC], DoesAllowDynInsertBefore
- CPaneDivider [MFC], DoesContainFloatingPane
- CPaneDivider [MFC], FindPaneContainer
- CPaneDivider [MFC], FindTabbedPane
- CPaneDivider [MFC], GetDefaultWidth
- CPaneDivider [MFC], GetFirstPane
- CPaneDivider [MFC], GetPaneDividerStyle
- CPaneDivider [MFC], GetRootContainerRect
- CPaneDivider [MFC], GetWidth
- CPaneDivider [MFC], Init
- CPaneDivider [MFC], InsertPane
- CPaneDivider [MFC], IsAutoHideMode
- CPaneDivider [MFC], IsDefault
- CPaneDivider [MFC], IsHorizontal
- CPaneDivider [MFC], Move
- CPaneDivider [MFC], NotifyAboutRelease
- CPaneDivider [MFC], OnShowPane
- CPaneDivider [MFC], ReleaseEmptyPaneContainers
- CPaneDivider [MFC], RemovePane
- CPaneDivider [MFC], ReplacePane
- CPaneDivider [MFC], RepositionPanes
- CPaneDivider [MFC], Serialize
- CPaneDivider [MFC], SetAutoHideMode
- CPaneDivider [MFC], SetPaneContainerManager
- CPaneDivider [MFC], ShowWindow
- CPaneDivider [MFC], StoreRecentDockSiteInfo
- CPaneDivider [MFC], StoreRecentTabRelatedInfo
- CPaneDivider [MFC], GetPanes
- CPaneDivider [MFC], GetPaneDividers
- CPaneDivider [MFC], m_nDefaultWidth
- CPaneDivider [MFC], m_pSliderRTC
ms.assetid: 8e828a5d-232f-4127-b8e3-7fa45a7a476e
ms.openlocfilehash: 43cba977d50e161c58d3e240e1282049a415c88d
ms.sourcegitcommit: b72a10a7b12e722fd91a17406b91b270026f763a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/04/2019
ms.locfileid: "58773855"
---
# <a name="cpanedivider-class"></a>CPaneDivider 클래스

더 자세한 내용은 Visual Studio 설치의 **VC\\atlmfc\\src\\mfc** 폴더에 있는 소스 코드를 참조하세요.

`CPaneDivider` 클래스 두 창을 분할 두 그룹 창을 분할 또는 주 프레임 창의 클라이언트 영역에서 창 그룹을 구분 합니다.

## <a name="syntax"></a>구문

```
class CPaneDivider : public CBasePane
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CPaneDivider::CPaneDivider](#cpanedivider)||

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CPaneDivider::AddPaneContainer](#addpanecontainer)||
|[CPaneDivider::AddPane](#addpane)||
|[CPaneDivider::AddRecentPane](#addrecentpane)||
|[CPaneDivider::CalcExpectedDockedRect](#calcexpecteddockedrect)||
|[CPaneDivider::CalcFixedLayout](#calcfixedlayout)|(재정의 [cbasepane:: Calcfixedlayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|
|[CPaneDivider::CheckVisibility](#checkvisibility)||
|[CPaneDivider::CreateEx](#createex)|(재정의 [cbasepane:: Createex](../../mfc/reference/cbasepane-class.md#createex).)|
|[CPaneDivider::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|(재정의 [cbasepane:: Doesallowdyninsertbefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|
|[CPaneDivider::DoesContainFloatingPane](#doescontainfloatingpane)||
|[CPaneDivider::FindPaneContainer](#findpanecontainer)||
|[CPaneDivider::FindTabbedPane](#findtabbedpane)||
|[CPaneDivider::GetDefaultWidth](#getdefaultwidth)||
|[CPaneDivider::GetFirstPane](#getfirstpane)||
|[CPaneDivider::GetPaneDividerStyle](#getpanedividerstyle)||
|[CPaneDivider::GetRootContainerRect](#getrootcontainerrect)||
|[CPaneDivider::GetWidth](#getwidth)||
|[CPaneDivider::Init](#init)||
|[CPaneDivider::InsertPane](#insertpane)||
|[CPaneDivider::IsAutoHideMode](#isautohidemode)|(재정의 [CBasePane::IsAutoHideMode](../../mfc/reference/cbasepane-class.md#isautohidemode).)|
|[CPaneDivider::IsDefault](#isdefault)||
|[CPaneDivider::IsHorizontal](#ishorizontal)|(재정의 [CBasePane::IsHorizontal](../../mfc/reference/cbasepane-class.md#ishorizontal).)|
|[CPaneDivider::Move](#move)||
|[CPaneDivider::NotifyAboutRelease](#notifyaboutrelease)||
|[CPaneDivider::OnShowPane](#onshowpane)||
|[CPaneDivider::ReleaseEmptyPaneContainers](#releaseemptypanecontainers)||
|[CPaneDivider::RemovePane](#removepane)||
|[CPaneDivider::ReplacePane](#replacepane)||
|[CPaneDivider::RepositionPanes](#repositionpanes)||
|[CPaneDivider::Serialize](#serialize)|( `CBasePane::Serialize`을 재정의합니다.)|
|[CPaneDivider::SetAutoHideMode](#setautohidemode)||
|[CPaneDivider::SetPaneContainerManager](#setpanecontainermanager)||
|[CPaneDivider::ShowWindow](#showwindow)||
|[CPaneDivider::StoreRecentDockSiteInfo](#storerecentdocksiteinfo)||
|[CPaneDivider::StoreRecentTabRelatedInfo](#storerecenttabrelatedinfo)||

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CPaneDivider::GetPanes](#getpanes)|창에 있는 목록을 반환 합니다 [CPaneContainer 클래스](../../mfc/reference/cpanecontainer-class.md)합니다. 기본 창 구분선에 대해서만이 메서드를 호출 해야 합니다.|
|[CPaneDivider::GetPaneDividers](#getpanedividers)|에 있는 창 구분선의 목록을 반환 합니다 [CPaneContainer 클래스](../../mfc/reference/cpanecontainer-class.md)합니다. 기본 창 구분선에 대해서만이 메서드를 호출 해야 합니다.|

### <a name="data-members"></a>데이터 멤버

|이름|설명|
|----------|-----------------|
|[CPaneDivider::m_nDefaultWidth](#m_ndefaultwidth)|응용 프로그램의 모든 창 구분선의 픽셀에서의 기본 너비를 지정합니다.|
|[CPaneDivider::m_pSliderRTC](#m_psliderrtc)|에 대 한 런타임 클래스 정보에 대 한 포인터를 보유 한 `CPaneDivider`-파생 개체입니다.|

## <a name="remarks"></a>설명

프레임 워크 만듭니다 `CPaneDivider` 개체를 자동으로 창을 도킹 합니다.

창 구분선의는 다음과 같은 두 종류가 있습니다.

- 기본 창 구분선 창 그룹을 주 프레임 창에의 한 쪽에 도킹 될 때 생성 됩니다. 기본 창 구분선에 대 한 포인터를 보유 합니다 [CPaneContainerManager 클래스](../../mfc/reference/cpanecontainermanager-class.md) 창의 그룹에 대 한 대부분의 작업을 리디렉션합니다 (를 창 크기 조정 등 다른 도킹 창 또는 컨테이너) 컨테이너 관리자에 게 합니다. 각 도킹 창을 해당 기본 창 구분선에 대 한 포인터를 유지 관리합니다.

- 일반 창 구분선만 컨테이너에 두 개의 창이 나눕니다. 자세한 내용은 [CPaneContainer 클래스](../../mfc/reference/cpanecontainer-class.md)합니다.

## <a name="example"></a>예제

다음 예제에서는 `CWorkspaceBar` 개체에서 `CPaneDivider` 개체를 가져오는 방법을 보여 줍니다. 이 코드 조각은의 일부인 합니다 [MDI 탭 데모 샘플](../../overview/visual-cpp-samples.md)합니다.

[!code-cpp[NVC_MFC_MDITabsDemo#5](../../mfc/reference/codesnippet/cpp/cpanedivider-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md) [CPaneDivider](../../mfc/reference/cpanedivider-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxPaneDivider.h

##  <a name="setautohidemode"></a>  CPaneDivider::SetAutoHideMode

```
void SetAutoHideMode(BOOL bMode);
```

### <a name="parameters"></a>매개 변수

[in] *bMode*<br/>

### <a name="remarks"></a>설명

##  <a name="setpanecontainermanager"></a>  CPaneDivider::SetPaneContainerManager

```
void SetPaneContainerManager(CPaneContainerManager* p);
```

### <a name="parameters"></a>매개 변수

[in] *p*<br/>

### <a name="remarks"></a>설명

##  <a name="addpane"></a>  CPaneDivider::AddPane

```
virtual void AddPane(CDockablePane* pBar);
```

### <a name="parameters"></a>매개 변수

[in] *pBar*<br/>

### <a name="remarks"></a>설명

##  <a name="addpanecontainer"></a>  CPaneDivider::AddPaneContainer

```
virtual BOOL AddPaneContainer(
    CPaneContainerManager& barContainerManager,
    BOOL bOuterEdge);

virtual BOOL AddPaneContainer(
    CDockablePane* pTargetBar,
    CPaneContainerManager& barContainerManager,
    DWORD dwAlignment);
```

### <a name="parameters"></a>매개 변수

[in] *barContainerManager*<br/>
[in] *bOuterEdge*<br/>
[in] *pTargetBar*<br/>
[in] *dwAlignment*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="addrecentpane"></a>  CPaneDivider::AddRecentPane

```
virtual CDockablePane* AddRecentPane(CDockablePane* pBar);
```

### <a name="parameters"></a>매개 변수

[in] *pBar*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="calcexpecteddockedrect"></a>  CPaneDivider::CalcExpectedDockedRect

```
virtual void CalcExpectedDockedRect(
    CWnd* pWndToDock,
    CPoint ptMouse,
    CRect& rectResult,
    BOOL& bDrawTab,
    CDockablePane** ppTargetBar);
```

### <a name="parameters"></a>매개 변수

[in] *pWndToDock*<br/>
[in] *ptMouse*<br/>
[in] *rectResult*<br/>
[in] *bDrawTab*<br/>
[in] *ppTargetBar*<br/>

### <a name="remarks"></a>설명

##  <a name="calcfixedlayout"></a>  CPaneDivider::CalcFixedLayout

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

##  <a name="checkvisibility"></a>  CPaneDivider::CheckVisibility

```
virtual BOOL CheckVisibility();
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="cpanedivider"></a>  CPaneDivider::CPaneDivider

```
CPaneDivider();

CPaneDivider(
    BOOL bDefaultSlider,
    CWnd* pParent = NULL);
```

### <a name="parameters"></a>매개 변수

[in] *bDefaultSlider*<br/>
[in] *pParent*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="createex"></a>  CPaneDivider::CreateEx

```
virtual BOOL CreateEx(
    DWORD dwStyleEx,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID,
    CCreateContext* pContext);
```

### <a name="parameters"></a>매개 변수

[in] *dwStyleEx*<br/>
[in] *dwStyle*<br/>
[in] *rect*<br/>
[in] *pParentWnd*<br/>
[in] *nID*<br/>
[in] *pContext*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="doesallowdyninsertbefore"></a>  CPaneDivider::DoesAllowDynInsertBefore

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="doescontainfloatingpane"></a>  CPaneDivider::DoesContainFloatingPane

```
virtual BOOL DoesContainFloatingPane();
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="findpanecontainer"></a>  CPaneDivider::FindPaneContainer

```
CPaneContainer* FindPaneContainer(
    CDockablePane* pBar,
    BOOL& bLeftBar);
```

### <a name="parameters"></a>매개 변수

[in] *pBar*<br/>
[in] *bLeftBar*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="findtabbedpane"></a>  CPaneDivider::FindTabbedPane

```
CDockablePane* FindTabbedPane(UINT nID);
```

### <a name="parameters"></a>매개 변수

[in] *nID*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="getdefaultwidth"></a>  CPaneDivider::GetDefaultWidth

```
static int __stdcall GetDefaultWidth();
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="getfirstpane"></a>  CPaneDivider::GetFirstPane

```
const CBasePane* GetFirstPane() const;
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="getpanedividers"></a>  CPaneDivider::GetPaneDividers

에 있는 창 구분선의 목록을 반환 합니다 [CPaneContainer 클래스](../../mfc/reference/cpanecontainer-class.md)합니다. 기본 창 구분선에 대해서만이 메서드를 호출 해야 합니다.

```
void GetPaneDividers(CObList& lstSliders);
```

### <a name="parameters"></a>매개 변수

*lstSliders*<br/>
[out] 창 컨테이너에 있는 창 구분선의 목록을 포함 합니다.

### <a name="remarks"></a>설명

기본 창 구분선만에 대 한이 메서드를 호출 해야 합니다. 기본 창 구분선 구분선 전체 창 컨테이너의 크기를 조정 하는 경우

##  <a name="getpanedividerstyle"></a>  CPaneDivider::GetPaneDividerStyle

```
DWORD GetPaneDividerStyle() const;
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="getpanes"></a>  CPaneDivider::GetPanes

창에 있는 목록을 반환 합니다 [CPaneContainer 클래스](../../mfc/reference/cpanecontainer-class.md)합니다. 기본 창 구분선 검색에이 메서드를 호출 해야 합니다.

```
void GetPanes(CObList& lstBars);
```

### <a name="parameters"></a>매개 변수

*lstBars*<br/>
[out] 창 컨테이너에 있는 창의 목록에 포함 되어 있습니다.

### <a name="remarks"></a>설명

기본 창 구분선만에 대 한이 메서드를 호출 해야 합니다. 기본 창 구분선 구분선 전체 창 컨테이너의 크기를 조정 하는 경우

##  <a name="getrootcontainerrect"></a>  CPaneDivider::GetRootContainerRect

```
CRect GetRootContainerRect();
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="getwidth"></a>  CPaneDivider::GetWidth

```
int GetWidth() const;
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="init"></a>  CPaneDivider::Init

```
void Init(
    BOOL bDefaultSlider = FALSE,
    CWnd* pParent = NULL);
```

### <a name="parameters"></a>매개 변수

[in] *bDefaultSlider*<br/>
[in] *pParent*<br/>

### <a name="remarks"></a>설명

##  <a name="insertpane"></a>  CPaneDivider::InsertPane

```
virtual BOOL InsertPane(
    CDockablePane* pBarToInsert,
    CDockablePane* pTargetBar,
    DWORD dwAlignment,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>매개 변수

[in] *pBarToInsert*<br/>
[in] *pTargetBar*<br/>
[in] *dwAlignment*<br/>
[in] *lpRect*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="isautohidemode"></a>  CPaneDivider::IsAutoHideMode

```
BOOL IsAutoHideMode() const;
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="isdefault"></a>  CPaneDivider::IsDefault

```
BOOL IsDefault() const;
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="ishorizontal"></a>  CPaneDivider::IsHorizontal

```
BOOL IsHorizontal() const;
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="m_ndefaultwidth"></a>  CPaneDivider::m_nDefaultWidth

응용 프로그램의 모든 창 구분선의 픽셀에서의 기본 너비를 지정합니다.

```
AFX_IMPORT_DATA static int m_nDefaultWidth;
```

##  <a name="move"></a>  CPaneDivider::Move

```
virtual void Move(
    CPoint& ptOffset,
    BOOL bAdjustLayout = TRUE);
```

### <a name="parameters"></a>매개 변수

[in] *ptOffset*<br/>
[in] *bAdjustLayout*<br/>

### <a name="remarks"></a>설명

##  <a name="m_psliderrtc"></a>  CPaneDivider::m_pSliderRTC

에 대 한 런타임 클래스 정보에 대 한 포인터를 보유 한 `CPaneDivider`-파생 개체입니다.

```
AFX_IMPORT_DATA static CRuntimeClass* m_pSliderRTC;
```

### <a name="remarks"></a>설명

사용자 지정 창 구분선을 만든 경우이 멤버 변수를 설정 합니다. 이렇게 하면 창을 그릴 때 프로그램 창 구분선을 만들기 위해 프레임 워크.

### <a name="example"></a>예제

다음 예제에서는 설정 하는 방법의 `m_pSliderRTC` 멤버 변수:

```
class CMySplitter : public CPaneDivider
{
...
};

CPaneDivider::m_pSliderRTC = RUNTIME_CLASS(CMySpliter);
```

##  <a name="notifyaboutrelease"></a>  CPaneDivider::NotifyAboutRelease

```
virtual void NotifyAboutRelease();
```

### <a name="remarks"></a>설명

##  <a name="onshowpane"></a>  CPaneDivider::OnShowPane

```
virtual void OnShowPane(
    CDockablePane* pBar,
    BOOL bShow);
```

### <a name="parameters"></a>매개 변수

[in] *pBar*<br/>
[in] *bShow*<br/>

### <a name="remarks"></a>설명

##  <a name="releaseemptypanecontainers"></a>  CPaneDivider::ReleaseEmptyPaneContainers

```
void ReleaseEmptyPaneContainers();
```

### <a name="remarks"></a>설명

##  <a name="removepane"></a>  CPaneDivider::RemovePane

```
virtual void RemovePane(CDockablePane* pBar);
```

### <a name="parameters"></a>매개 변수

[in] *pBar*<br/>

### <a name="remarks"></a>설명

##  <a name="replacepane"></a>  CPaneDivider::ReplacePane

```
virtual BOOL ReplacePane(
    CDockablePane* pBarToReplace,
    CDockablePane* pBarToReplaceWith);
```

### <a name="parameters"></a>매개 변수

[in] *pBarToReplace*<br/>
[in] *pBarToReplaceWith*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="repositionpanes"></a>  CPaneDivider::RepositionPanes

```
virtual void RepositionPanes(
    CRect& rectNew,
    HDWP& hdwp);
```

### <a name="parameters"></a>매개 변수

[in] *rectNew*<br/>
[in] *hdwp*<br/>

### <a name="remarks"></a>설명

##  <a name="serialize"></a>  CPaneDivider::Serialize

```
void Serialize(CArchive& ar);
```

### <a name="parameters"></a>매개 변수

[in] *ar*<br/>

### <a name="remarks"></a>설명

##  <a name="showwindow"></a>  CPaneDivider::ShowWindow

```
void ShowWindow(int nCmdShow);
```

### <a name="parameters"></a>매개 변수

[in] *nCmdShow*<br/>

### <a name="remarks"></a>설명

##  <a name="storerecentdocksiteinfo"></a>  CPaneDivider::StoreRecentDockSiteInfo

```
void StoreRecentDockSiteInfo(CDockablePane* pBar);
```

### <a name="parameters"></a>매개 변수

[in] *pBar*<br/>

### <a name="remarks"></a>설명

##  <a name="storerecenttabrelatedinfo"></a>  CPaneDivider::StoreRecentTabRelatedInfo

```
void StoreRecentTabRelatedInfo(
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
[CPaneContainerManager 클래스](../../mfc/reference/cpanecontainermanager-class.md)<br/>
[CPaneContainer 클래스](../../mfc/reference/cpanecontainer-class.md)<br/>
[CDockingManager 클래스](../../mfc/reference/cdockingmanager-class.md)<br/>
[CBasePane 클래스](../../mfc/reference/cbasepane-class.md)
