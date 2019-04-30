---
title: CReBar 클래스
ms.date: 11/19/2018
f1_keywords:
- CReBar
- AFXEXT/CReBar
- AFXEXT/CReBar::AddBar
- AFXEXT/CReBar::Create
- AFXEXT/CReBar::GetReBarCtrl
helpviewer_keywords:
- CReBar [MFC], AddBar
- CReBar [MFC], Create
- CReBar [MFC], GetReBarCtrl
ms.assetid: c1ad2720-1d33-4106-8e4e-80aa84f93559
ms.openlocfilehash: 5a87f70816e9342c7aa203a53d13699659cebb28
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62372369"
---
# <a name="crebar-class"></a>CReBar 클래스

rebar 컨트롤의 레이아웃, 지속성 및 상태 정보를 제공하는 컨트롤 막대입니다.

## <a name="syntax"></a>구문

```
class CReBar : public CControlBar
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CReBar::AddBar](#addbar)|Rebar 밴드를 추가합니다.|
|[CReBar::Create](#create)|Rebar 컨트롤을 만들고에 연결 된 `CReBar` 개체입니다.|
|[CReBar::GetReBarCtrl](#getrebarctrl)|기본 공용 컨트롤에 직접 액세스할 수 있습니다.|

## <a name="remarks"></a>설명

Rebar 개체는 다양 한 자식 창에 일반적으로 다른 컨트롤 편집 상자, 도구 모음, 목록 상자 등을 포함할 수 있습니다. Rebar 개체는 지정 된 비트맵을 통해 해당 자식 창을 표시할 수 있습니다. 응용 프로그램이 자동으로 크기를 조정 rebar 하거나 수동으로 조정할 수 rebar 그리퍼 막대를 끌거나 클릭 하 여 합니다.

![RebarMenu의 예](../../mfc/reference/media/vc4sc61.gif "RebarMenu의 예")

## <a name="rebar-control"></a>Rebar 컨트롤

크기 조정 막대를 도구 모음 개체 비슷하게 작동합니다. Rebar 밴드의 크기를 조정 하려면 클릭 및 끌어서 메커니즘을 사용 합니다. rebar 컨트롤은 그리퍼 막대, 비트맵, 텍스트 레이블 및 자식 창이 조합된 하나 이상의 밴드를 포함할 수 있습니다. 그러나 밴드는 둘 이상의 자식 창을 포함할 수 없습니다.

`CReBar` 사용 하는 [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) 해당 구현을 제공 하는 클래스입니다. Rebar 컨트롤을 통해 액세스할 수 있습니다 [GetReBarCtrl](#getrebarctrl) 컨트롤의 사용자 지정 옵션을 활용할 수 있습니다. Rebar 컨트롤에 대 한 자세한 내용은 참조 하세요. `CReBarCtrl`합니다. Rebar 컨트롤을 사용 하는 방법에 대 한 자세한 내용은 참조 하십시오 [를 사용 하 여 CReBarCtrl](../../mfc/using-crebarctrl.md)합니다.

> [!CAUTION]
>  Rebar 및 rebar 컨트롤 개체에는 MFC 컨트롤 모음 고정을 지원 하지 않습니다. 경우 `CRebar::EnableDocking` 응용 프로그램에서 assert가 호출 됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`CReBar`

## <a name="requirements"></a>요구 사항

**헤더:** afxext.h

##  <a name="addbar"></a>  CReBar::AddBar

Rebar 밴드를 추가 하려면이 멤버 함수를 호출 합니다.

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
에 대 한 포인터를 `CWnd` 자식 창을 rebar에 삽입할 개체입니다. 참조 된 개체는 WS_CHILD 있어야 합니다.

*lpszText*<br/>
Rebar에 표시할 텍스트를 포함 하는 문자열에 대 한 포인터입니다. 기본적으로 NULL입니다. 에 포함 된 텍스트 *lpszText* 자식 창의의 일부가 아닌 자체 rebar에 있는 것입니다.

*pbmp*<br/>
에 대 한 포인터를 `CBitmap` rebar 백그라운드에 표시 되는 개체입니다. 기본적으로 NULL입니다.

*dwStyle*<br/>
Rebar에 적용할 스타일을 포함 하 DWORD. 참조를 `fStyle` 함수는 Win32 구조의 설명 [REBARBANDINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarbandinfoa) 대역 외 스타일의 목록은 합니다.

*clrFore*<br/>
Rebar의 전경색을 나타내는 COLORREF 값입니다.

*clrBack*<br/>
Rebar의 배경색을 나타내는 COLORREF 값입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CReBarCtrl#1](../../mfc/reference/codesnippet/cpp/crebar-class_1.cpp)]

##  <a name="create"></a>  CReBar::Create

Rebar를 만들려면이 멤버 함수를 호출 합니다.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = RBS_BANDBORDERS,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS | WS_CLIPCHILDREN | CBRS_TOP,
    UINT nID = AFX_IDW_REBAR);
```

### <a name="parameters"></a>매개 변수

*pParentWnd*<br/>
에 대 한 포인터를 `CWnd` 인 Windows 창 상태 표시줄의 부모인 개체입니다. 프레임 창 일반적으로입니다.

*dwCtrlStyle*<br/>
Rebar 컨트롤 스타일입니다. 기본적으로 RBS_BANDBORDERS 좁은 rebar 컨트롤 내에서 인접 한 밴드를 별도 줄을 표시 합니다. 참조 [Rebar 컨트롤 스타일](/windows/desktop/Controls/rebar-control-styles) 스타일의 목록은 Windows SDK에 있습니다.

*dwStyle*<br/>
Rebar 창 스타일입니다.

*nID*<br/>
Rebar의 자식 창 id입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CReBar::AddBar](#addbar)합니다.

##  <a name="getrebarctrl"></a>  CReBar::GetReBarCtrl

이 멤버 함수에는 기본 공용 컨트롤에 직접 액세스할 수 있습니다.

```
CReBarCtrl& GetReBarCtrl() const;
```

### <a name="return-value"></a>반환 값

에 대 한 참조를 [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) 개체입니다.

### <a name="remarks"></a>설명

Rebar에 사용자 지정 Windows rebar 공용 컨트롤의 기능을 활용 하려면이 멤버 함수를 호출 합니다. 호출 하는 경우 `GetReBarCtrl`, 참조 개체를 반환 합니다 `CReBarCtrl` 개체 멤버 함수의 집합 중 하나를 사용할 수 있습니다.

사용에 대 한 자세한 내용은 `CReBarCtrl` 참조에 크기 조정 막대를 사용자 지정 하려면 [CReBarCtrl 사용 하 여](../../mfc/using-crebarctrl.md)입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CReBarCtrl#2](../../mfc/reference/codesnippet/cpp/crebar-class_2.cpp)]

## <a name="see-also"></a>참고자료

[MFC 샘플 MFCIE](../../overview/visual-cpp-samples.md)<br/>
[CControlBar 클래스](../../mfc/reference/ccontrolbar-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
