---
title: CMFCReBar 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCReBar
- AFXREBAR/CMFCReBar
- AFXREBAR/CMFCReBar::AddBar
- AFXREBAR/CMFCReBar::CalcFixedLayout
- AFXREBAR/CMFCReBar::CanFloat
- AFXREBAR/CMFCReBar::Create
- AFXREBAR/CMFCReBar::EnableDocking
- AFXREBAR/CMFCReBar::GetReBarBandInfoSize
- AFXREBAR/CMFCReBar::GetReBarCtrl
- AFXREBAR/CMFCReBar::OnShowControlBarMenu
- AFXREBAR/CMFCReBar::OnToolHitTest
- AFXREBAR/CMFCReBar::OnUpdateCmdUI
- AFXREBAR/CMFCReBar::SetPaneAlignment
helpviewer_keywords:
- CMFCReBar [MFC], AddBar
- CMFCReBar [MFC], CalcFixedLayout
- CMFCReBar [MFC], CanFloat
- CMFCReBar [MFC], Create
- CMFCReBar [MFC], EnableDocking
- CMFCReBar [MFC], GetReBarBandInfoSize
- CMFCReBar [MFC], GetReBarCtrl
- CMFCReBar [MFC], OnShowControlBarMenu
- CMFCReBar [MFC], OnToolHitTest
- CMFCReBar [MFC], OnUpdateCmdUI
- CMFCReBar [MFC], SetPaneAlignment
ms.assetid: 02a60e29-6224-49c1-9e74-e0a7d9f8d023
ms.openlocfilehash: 7776bf504d502feee8ef51949b8adc8e44f94c8e
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58772295"
---
# <a name="cmfcrebar-class"></a>CMFCReBar 클래스

`CMFCReBar` 개체 레이아웃, 지 속성 및 rebar 컨트롤에 대 한 상태 정보를 제공 하는 컨트롤 막대입니다.
더 자세한 내용은 Visual Studio 설치의 **VC\\atlmfc\\src\\mfc** 폴더에 있는 소스 코드를 참조하세요.
## <a name="syntax"></a>구문

```
class CMFCReBar : public CPane
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMFCReBar::AddBar](#addbar)|Rebar 밴드를 추가합니다.|
|[CMFCReBar::CalcFixedLayout](#calcfixedlayout)|(재정의 [cbasepane:: Calcfixedlayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|
|[CMFCReBar::CanFloat](#canfloat)|(재정의 [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat).)|
|[CMFCReBar::Create](#create)|Rebar 컨트롤을 만들고에 연결 된 `CMFCReBar` 개체입니다.|
|[CMFCReBar::EnableDocking](#enabledocking)|(재정의 [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking).)|
|[CMFCReBar::GetReBarBandInfoSize](#getrebarbandinfosize)||
|[CMFCReBar::GetReBarCtrl](#getrebarctrl)|내부에 직접 액세스할 [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) 공용 컨트롤입니다.|
|[CMFCReBar::OnShowControlBarMenu](#onshowcontrolbarmenu)|(재정의 [cpane:: Onshowcontrolbarmenu](../../mfc/reference/cpane-class.md#onshowcontrolbarmenu).)|
|[CMFCReBar::OnToolHitTest](#ontoolhittest)|(재정의 [CWnd::OnToolHitTest](../../mfc/reference/cwnd-class.md#ontoolhittest).)|
|[CMFCReBar::OnUpdateCmdUI](#onupdatecmdui)|(재정의 [CBasePane::OnUpdateCmdUI](cbasepane-class.md).)|
|[CMFCReBar::SetPaneAlignment](#setpanealignment)|(재정의 [CBasePane::SetPaneAlignment](../../mfc/reference/cbasepane-class.md#setpanealignment).)|

## <a name="remarks"></a>설명

`CMFCReBar` 개체는 다양 한 자식 창 포함할 수 있습니다. 여기에 편집 상자, 도구 모음 및 목록 상자입니다. Rebar를 프로그래밍 방식으로 조정할 수 있습니다 하거나 수동으로 조정할 수 rebar 그리퍼 막대를 드래그 하 여 합니다. 또한 원하는 비트맵 rebar 개체의 배경색을 설정할 수 있습니다.

크기 조정 막대를 도구 모음 개체 비슷하게 작동합니다. Rebar 컨트롤에는 하나 이상의 밴드를 포함할 수 있습니다 하 고 각 밴드에는 그리퍼 막대, 비트맵, 텍스트 레이블 및 자식 창이 포함 될 수 있습니다.

## <a name="example"></a>예제

다음 예제에서는 `CMFCReBar` 클래스에서 다양한 메서드를 사용하는 방법을 보여 줍니다. Rebar 컨트롤을 만들고 밴드를 추가 하는 방법을 보여 줍니다. 밴드는 내부 도구 모음으로 작동합니다. 이 코드 조각은의 일부인 합니다 [Rebar 테스트 샘플](../../overview/visual-cpp-samples.md)합니다.

[!code-cpp[NVC_MFC_RebarTest#1](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_1.h)]
[!code-cpp[NVC_MFC_RebarTest#2](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CMFCReBar](../../mfc/reference/cmfcrebar-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxRebar.h

##  <a name="addbar"></a>  CMFCReBar::AddBar

Rebar 밴드를 추가합니다.

```
BOOL AddBar(
    CWnd* pBar,
    LPCTSTR pszText = NULL,
    CBitmap* pbmp = NULL,
    DWORD dwStyle = RBBS_GRIPPERALWAYS | RBBS_FIXEDBMP);

BOOL AddBar(
    CWnd* pBar,
    COLORREF clrFore,
    COLORREF clrBack,
    LPCTSTR pszText = NULL,
    DWORD dwStyle = RBBS_GRIPPERALWAYS);
```

### <a name="parameters"></a>매개 변수

*pBar*<br/>
[out에서] Rebar에 삽입 되는 자식 창에 대 한 포인터입니다. 참조 된 개체에 있어야 합니다 **WS_CHILD** 창 스타일입니다.

*pszText*<br/>
[in] Rebar에 표시할 텍스트를 지정 합니다. 텍스트를 자식 창에 속하지 않습니다. 대신, rebar 자체에 표시 됩니다.

*pbmp*<br/>
[out에서] Rebar 백그라운드에 표시할 비트맵을 지정 합니다.

*dwStyle*<br/>
[in] 밴드에 적용할 스타일을 포함 합니다. 대역 외 스타일의 전체 목록은에 대 한 설명을 참조 하세요 `fStyle` 에 [REBARBANDINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarbandinfoa) Windows SDK 설명서의 구조입니다.

*clrFore*<br/>
[in] Rebar의 전경색을 나타냅니다.

*clrBack*<br/>
[in] Rebar의 배경색을 나타냅니다.

### <a name="return-value"></a>반환 값

밴드 rebar;에 성공적으로 추가 된 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

##  <a name="create"></a>  CMFCReBar::Create

Rebar 컨트롤을 만들고에 연결 합니다 [CMFCReBar](../../mfc/reference/cmfcrebar-class.md) 개체입니다.

```
BOOL Create(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = RBS_BANDBORDERS,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS | WS_CLIPCHILDREN | CBRS_TOP,
    UINT nID = AFX_IDW_REBAR);
```

### <a name="parameters"></a>매개 변수

*pParentWnd*<br/>
[out에서] 이 rebar 컨트롤의 부모 창에 대 한 포인터입니다.

*dwCtrlStyle*<br/>
[in] Rebar 컨트롤의 스타일을 지정합니다. 기본 스타일 값은 **RBS_BANDBORDERS**는 표시 좁힐 선으로 인접 한 rebar 컨트롤 밴드를 구분 합니다. 유효한 스타일의 목록은 참조 하세요 [Rebar 컨트롤 스타일](/windows/desktop/Controls/rebar-control-styles) Windows SDK 설명서의 합니다.

*dwStyle*<br/>
[in] Rebar 컨트롤의 창 스타일입니다. 유효한 스타일의 목록은 참조 하세요 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles)합니다.

*nID*<br/>
[in] Rebar의 자식 창 id입니다.

### <a name="return-value"></a>반환 값

Rebar 성공적으로 만들어진 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

##  <a name="getrebarctrl"></a>  CMFCReBar::GetReBarCtrl

직접 액세스를 제공 `CReBarCtrl` 에 대 한 기본 공용 컨트롤 `CMFCReBar` 개체입니다.

```
CReBarCtrl& GetReBarCtrl() const;
```

### <a name="return-value"></a>반환 값

기본에 대 한 참조 `CReBarCtrl` 개체입니다.

### <a name="remarks"></a>설명

프로그램 크기 조정 막대를 사용자 지정할 때 Windows rebar 공용 컨트롤 기능을 활용 하려면이 메서드를 호출 합니다.

##  <a name="calcfixedlayout"></a>  CMFCReBar::CalcFixedLayout

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

##  <a name="canfloat"></a>  CMFCReBar::CanFloat

```
virtual BOOL CanFloat() const;
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="enabledocking"></a>  CMFCReBar::EnableDocking

```
void EnableDocking(DWORD dwDockStyle);
```

### <a name="parameters"></a>매개 변수

[in] *dwDockStyle*<br/>

### <a name="remarks"></a>설명

##  <a name="getrebarbandinfosize"></a>  CMFCReBar::GetReBarBandInfoSize

```
UINT GetReBarBandInfoSize() const;
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="onshowcontrolbarmenu"></a>  CMFCReBar::OnShowControlBarMenu

```
virtual BOOL OnShowControlBarMenu(CPoint);
```

### <a name="parameters"></a>매개 변수

[in] *CPoint*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="ontoolhittest"></a>  CMFCReBar::OnToolHitTest

```
virtual INT_PTR OnToolHitTest(
    CPoint point,
    TOOLINFO* pTI) const;
```

### <a name="parameters"></a>매개 변수

[in] *point*<br/>
[in] *pTI*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="onupdatecmdui"></a>  CMFCReBar::OnUpdateCmdUI

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler);
```

### <a name="parameters"></a>매개 변수

[in] *pTarget*<br/>
[in] *bDisableIfNoHndler*<br/>

### <a name="remarks"></a>설명

##  <a name="setpanealignment"></a>  CMFCReBar::SetPaneAlignment

```
virtual void SetPaneAlignment(DWORD dwAlignment);
```

### <a name="parameters"></a>매개 변수

[in] *dwAlignment*<br/>

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CReBarCtrl 클래스](../../mfc/reference/crebarctrl-class.md)<br/>
[CPane Class](../../mfc/reference/cpane-class.md)
