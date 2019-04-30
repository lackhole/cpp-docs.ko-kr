---
title: CAutoHideDockSite 클래스
ms.date: 11/04/2016
f1_keywords:
- CAutoHideDockSite
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::CanAcceptPane
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::DockPane
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::GetAlignRect
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::RepositionPanes
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::SetOffsetLeft
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::SetOffsetRight
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::UnSetAutoHideMode
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::m_nExtraSpace
helpviewer_keywords:
- CAutoHideDockSite [MFC], CanAcceptPane
- CAutoHideDockSite [MFC], DockPane
- CAutoHideDockSite [MFC], GetAlignRect
- CAutoHideDockSite [MFC], RepositionPanes
- CAutoHideDockSite [MFC], SetOffsetLeft
- CAutoHideDockSite [MFC], SetOffsetRight
- CAutoHideDockSite [MFC], UnSetAutoHideMode
- CAutoHideDockSite [MFC], m_nExtraSpace
ms.assetid: 2a0f6bec-c369-4ab7-977d-564e7946ebad
ms.openlocfilehash: f24827e2dc1f4d1131f5b63aebeb0e2b09bc2281
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388477"
---
# <a name="cautohidedocksite-class"></a>CAutoHideDockSite 클래스

합니다 `CAutoHideDockSite` 확장 합니다 [CDockSite 클래스](../../mfc/reference/cdocksite-class.md) 자동 숨김 도킹 창을 구현 합니다.

## <a name="syntax"></a>구문

```
class CAutoHideDockSite : public CDockSite
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|||
|-|-|
|이름|설명|
|`CAutoHideDockSite::CAutoHideDockSite`|`CAutoHideDockSite` 개체를 생성합니다.|
|`CAutoHideDockSite::~CAutoHideDockSite`|소멸자|

### <a name="public-methods"></a>Public 메서드

|||
|-|-|
|이름|설명|
|`CAutoHideDockSite::AllowShowOnPaneMenu`|나타냅니다 여부는 `CAutoHideDockSite` 창 메뉴에 표시 됩니다.|
|[CAutoHideDockSite::CanAcceptPane](#canacceptpane)|기본 창 개체에서 파생 되었는지 여부를 결정 합니다 [CMFCAutoHideBar 클래스](../../mfc/reference/cmfcautohidebar-class.md)합니다.|
|[CAutoHideDockSite::DockPane](#dockpane)|이 창을 도킹 `CAuotHideDockSite` 개체입니다.|
|[CAutoHideDockSite::GetAlignRect](#getalignrect)|화면 좌표에서 도킹 사이트의 크기를 검색합니다.|
|[CAutoHideDockSite::RepositionPanes](#repositionpanes)|창에서 다시 그립니다는 `CAutoHideDockSite` 전역 여백와 단추 간격입니다.|
|[CAutoHideDockSite::SetOffsetLeft](#setoffsetleft)|도킹 모음의 왼쪽에 여백을 설정 합니다.|
|[CAutoHideDockSite::SetOffsetRight](#setoffsetright)|도킹 모음의 오른쪽에 여백을 설정 합니다.|
|[CAutoHideDockSite::UnSetAutoHideMode](#unsetautohidemode)|호출 [CMFCAutoHideBar::UnSetAutoHideMode](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode) 개체에 대 한는 `CAutoHideDockSite`합니다.|

### <a name="data-members"></a>데이터 멤버

|||
|-|-|
|이름|설명|
|[CAutoHideDockSite::m_nExtraSpace](#m_nextraspace)|도구 모음에서 도킹 모음의 가장자리 사이의 공간 크기를 정의 합니다. 이 작업 영역에서 왼쪽 가장자리나 위쪽 가장자리에 도킹 공간에 대 한 맞춤에 따라 측정 됩니다.|

## <a name="remarks"></a>설명

호출 하는 경우 [CFrameWndEx::EnableAutoHidePanes](../../mfc/reference/cframewndex-class.md#enableautohidepanes), 프레임 워크에서 자동으로 만듭니다는 `CAutoHideDockSite` 개체입니다. 대부분의 경우에는를 인스턴스화하거나이 클래스를 직접 사용 되지 해야 합니다.

도킹 모음의 도킹 창 왼쪽의 왼쪽 사이의 격차를 [CMFCAutoHideButton 클래스](../../mfc/reference/cmfcautohidebutton-class.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CDockSite](../../mfc/reference/cdocksite-class.md)

## <a name="example"></a>예제

다음 예제에서는 검색 하는 방법을 보여 줍니다는 `CAutoHideDockSite` 에서 개체를 `CMFCAutoHideBar` 개체 및 도킹 모음의 왼쪽 및 오른쪽 여백을 설정 하는 방법입니다.

[!code-cpp[NVC_MFC_RibbonApp#29](../../mfc/reference/codesnippet/cpp/cautohidedocksite-class_1.cpp)]

## <a name="requirements"></a>요구 사항

**헤더:** afxautohidedocksite.h

##  <a name="canacceptpane"></a>  CAutoHideDockSite::CanAcceptPane

기본 창 인지 여부를 확인 한 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) 개체 또는에서 파생 된 `CMFCAutoHideBar`합니다.

```
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*pBar*|[in] 프레임 워크를 테스트 하는 기본 창입니다.|

### <a name="return-value"></a>반환 값

TRUE 이면 *pBar* 에서 파생 된 `CMFCAutoHideBar`; FALSE이 고, 그렇지 합니다.

### <a name="remarks"></a>설명

기본 창 개체에서 파생 된 경우 `CMFCAutoHideBar`를 포함할 수 있습니다는 `CAutoHideDockSite`합니다.

##  <a name="dockpane"></a>  CAutoHideDockSite::DockPane

이 창을 도킹 [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md) 개체입니다.

```
virtual void DockPane(
    CPane* pWnd,
    AFX_DOCK_METHOD dockMethod,
    LPRECT lpRect = NULL);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*pWnd*|[in] 프레임 워크 도킹 된 창입니다.|
|*dockMethod*|[in] 창에 대 한 옵션을 도킹 합니다.|
|*lpRect*|[in] 도킹 된 창에 대 한 경계를 지정 하는 사각형입니다.|

### <a name="remarks"></a>설명

기본 구현에서는 매개 변수를 사용 하지 않습니다 *dockMethod*, 나중에 사용할 수 있는 제공 됩니다.

하는 경우 *lpRect* 가 null 인 경우 프레임 워크는 창 도킹 사이트의 기본 위치에 배치 합니다. 도킹 사이트 가로 이면 왼쪽에 도킹 사이트의 기본 위치는입니다. 그렇지 않으면 기본 위치는 도킹 사이트의 맨 위에 있는 합니다.

##  <a name="getalignrect"></a>  CAutoHideDockSite::GetAlignRect

화면 좌표에서 도킹 사이트의 크기를 검색합니다.

```
void GetAlignRect(CRect& rect) const;
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*rect*|[in] 사각형에 대 한 참조입니다. 메서드는이 사각형에 도킹 사이트의 크기를 저장합니다.|

### <a name="remarks"></a>설명

사각형은 포함 되지 않습니다 있도록 오프셋 여백 조정 됩니다.

##  <a name="m_nextraspace"></a>  CAutoHideDockSite::m_nExtraSpace

가장자리 사이의 공간 크기를 [CAutoHideDockSite 클래스](../../mfc/reference/cautohidedocksite-class.md) 하며 [CMFCAutoHideBar 클래스](../../mfc/reference/cmfcautohidebar-class.md) 개체입니다.

```
static int m_nExtraSpace;
```

### <a name="remarks"></a>설명

경우는 `CMFCAutoHideBar` 아래에서 도킹 될는 `CAutoHideDockSite`, 전체 도킹 사이트를 차지 하지 해야 합니다. 이 전역 변수 컨트롤의 왼쪽 가장자리나 위쪽 테두리 사이의 추가 공백 합니다 `CMFCAutoHideBar` 및 해당 `CAutoHideDockSite` 가장자리입니다. 위쪽 또는 왼쪽 가장자리에서 사용 되는지 여부는 현재 맞춤에 따라 달라 집니다.

##  <a name="setoffsetleft"></a>  CAutoHideDockSite::SetOffsetLeft

도킹 모음의 왼쪽에 여백을 설정 합니다.

```
void SetOffsetLeft(int nOffset);
```

### <a name="parameters"></a>매개 변수

*nOffset*<br/>
[in] 새 오프셋입니다.

### <a name="remarks"></a>설명

[CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) 개체를 정적으로 배치 된 `CAutoHideDockSite` 개체입니다. 즉, 사용자의 위치를 수동으로 변경할 수 없습니다는 `CMFCAutoHideBar` 개체입니다. 합니다 `SetOffsetLeft` 메서드 맨 왼쪽의 왼쪽 사이의 간격을 제어 `CMFCAutoHideBar` 및 좌 변의 `CAutoHideDockSite`합니다.

##  <a name="setoffsetright"></a>  CAutoHideDockSite::SetOffsetRight

도킹 모음의 오른쪽에 여백을 설정 합니다.

```
void SetOffsetRight(int nOffset);
```

### <a name="parameters"></a>매개 변수

*nOffset*<br/>
[in] 새 오프셋입니다.

### <a name="remarks"></a>설명

[CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) 개체를 정적으로 배치 된 `CAutoHideDockSite` 개체입니다. 즉, 사용자의 위치를 수동으로 변경할 수 없습니다는 `CMFCAutoHideBar` 개체입니다. 합니다 `SetOffsetRight` 메서드 맨 오른쪽의 오른쪽 사이의 간격을 제어 `CMFCAutoHideBar` 및 오른쪽에 있는 `CAutoHideDockSite`합니다.

##  <a name="repositionpanes"></a>  CAutoHideDockSite::RepositionPanes

창을 다시 그립니다 합니다 [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md)합니다.

```
virtual void RepositionPanes(CRect& rectNewClientArea);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*rectNewClientArea*|[in] 예약 된 값입니다.|

### <a name="remarks"></a>설명

기본 구현에서는 사용 하지 않습니다 *rectNewClientArea*합니다. 전역 도구 모음 여백 및 단추 간격을 사용 하 여 창을 다시 그립니다.

##  <a name="unsetautohidemode"></a>  CAutoHideDockSite::UnSetAutoHideMode

호출 [CMFCAutoHideBar::UnSetAutoHideMode](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode) 도킹 사이트 개체에 대 한 합니다.

```
void UnSetAutoHideMode(CMFCAutoHideBar* pAutoHideToolbar);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*pAutoHideToolbar*|[in] 에 대 한 포인터를 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) 개체 창에는 `CAutoHideDockSite`합니다.|

### <a name="remarks"></a>설명

이 메서드를 포함 하는 행에 대 한 검색 *pAutoHideToolbar*합니다. 호출한 `CMFCAutoHideBar.UnSetAutoHideMode` 모든는 `CMFCAutoHideBar` 해당 행에 있는 개체입니다. 경우 *pAutoHideToolbar* 찾을 수 없습니다 또는 NULL 이면이 메서드를 호출 `CMFCAutoHideBar.UnSetAutoHideMode` 모든는 `CMFCAutoHideBar` 에서 개체를 `CAutoHideDockSite`입니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CDockSite Class](../../mfc/reference/cdocksite-class.md)
