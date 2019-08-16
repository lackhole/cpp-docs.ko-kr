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
ms.openlocfilehash: 434232e8f99bf914b00379db53d4b4a37d24fe36
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502791"
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
|[CReBar::AddBar](#addbar)|크기 조정 막대에 밴드를 추가 합니다.|
|[CReBar::Create](#create)|Rebar 컨트롤을 만들고이를 `CReBar` 개체에 연결 합니다.|
|[CReBar::GetReBarCtrl](#getrebarctrl)|기본 공용 컨트롤에 직접 액세스할 수 있습니다.|

## <a name="remarks"></a>설명

Rebar 개체는 편집 상자, 도구 모음 및 목록 상자를 포함 하 여 다양 한 자식 창, 일반적으로 다른 컨트롤을 포함할 수 있습니다. Rebar 개체는 지정 된 비트맵 위에 자식 창을 표시할 수 있습니다. 응용 프로그램에서 자동 크기 조정 크기를 자동으로 조정할 수 있으며, 사용자는 그리퍼 막대를 클릭 하거나 끌어서 크기 조정 막대를 수동으로 조정할 수 있습니다.

![RebarMenu의 예](../../mfc/reference/media/vc4sc61.gif "RebarMenu의 예")

## <a name="rebar-control"></a>Rebar 컨트롤

Rebar 개체는 toolbar 개체와 비슷하게 동작 합니다. Rebar는 클릭 및 끌기 메커니즘을 사용 하 여 해당 밴드의 크기를 조정 합니다. rebar 컨트롤은 그리퍼 막대, 비트맵, 텍스트 레이블 및 자식 창이 조합된 하나 이상의 밴드를 포함할 수 있습니다. 그러나 밴드는 둘 이상의 자식 창을 포함할 수 없습니다.

`CReBar`는 [Crebarctrl](../../mfc/reference/crebarctrl-class.md) 클래스를 사용 하 여 구현을 제공 합니다. [Getre Ctrl 키](#getrebarctrl) 를 사용 하 여 rebar 컨트롤에 액세스 하 여 컨트롤의 사용자 지정 옵션을 활용할 수 있습니다. Rebar 컨트롤에 대 한 자세한 내용은을 `CReBarCtrl`참조 하십시오. Rebar 컨트롤 사용에 대 한 자세한 내용은 [CReBarCtrl 사용](../../mfc/using-crebarctrl.md)을 참조 하세요.

> [!CAUTION]
>  Rebar 및 rebar 컨트롤 개체는 MFC 컨트롤 막대 도킹을 지원 하지 않습니다. 가 `CRebar::EnableDocking` 호출 되 면 응용 프로그램은를 어설션 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`CReBar`

## <a name="requirements"></a>요구 사항

**헤더:** afxext.h

##  <a name="addbar"></a>  CReBar::AddBar

이 멤버 함수를 호출 하 여 rebar에 밴드를 추가 합니다.

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
Rebar에 삽입할 자식 `CWnd` 창인 개체에 대 한 포인터입니다. 참조 된 개체에는 WS_CHILD가 있어야 합니다.

*lpszText*<br/>
Rebar에 표시할 텍스트를 포함 하는 문자열에 대 한 포인터입니다. 기본값은 NULL입니다. *LpszText* 에 포함 된 텍스트는 자식 창의 일부가 아닙니다. rebar 자체에 있습니다.

*pbmp*<br/>
Rebar 배경에 표시 되 `CBitmap` 는 개체에 대 한 포인터입니다. 기본값은 NULL입니다.

*dwStyle*<br/>
Rebar에 적용할 스타일을 포함 하는 DWORD입니다. 밴드 스타일 `fStyle` 의 전체 목록은 Win32 구조 [re바 밴드 정보](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow) 에서 함수 설명을 참조 하세요.

*clrFore*<br/>
크기 조정 막대의 전경색을 나타내는 COLORREF 값입니다.

*clrBack*<br/>
Rebar의 배경색을 나타내는 COLORREF 값입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CReBarCtrl#1](../../mfc/reference/codesnippet/cpp/crebar-class_1.cpp)]

##  <a name="create"></a>  CReBar::Create

이 멤버 함수를 호출 하 여 rebar를 만듭니다.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = RBS_BANDBORDERS,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS | WS_CLIPCHILDREN | CBRS_TOP,
    UINT nID = AFX_IDW_REBAR);
```

### <a name="parameters"></a>매개 변수

*pParentWnd*<br/>
Windows 창이 상태 `CWnd` 표시줄의 부모 인 개체에 대 한 포인터입니다. 일반적으로 프레임 창입니다.

*dwCtrlStyle*<br/>
Rebar 컨트롤 스타일입니다. 기본적으로 RBS_BANDBORDERS는 좁은 선을 표시 하 여 rebar 컨트롤 내에 인접 한 밴드를 분리 합니다. 스타일 목록은 Windows SDK의 [Rebar 컨트롤 스타일](/windows/win32/Controls/rebar-control-styles) 을 참조 하세요.

*dwStyle*<br/>
Rebar 창 스타일입니다.

*nID*<br/>
Rebar의 자식 창 ID입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

  [CReBar:: AddBar](#addbar)의 예제를 참조 하세요.

##  <a name="getrebarctrl"></a>  CReBar::GetReBarCtrl

이 멤버 함수를 사용 하면 기본 공용 컨트롤에 직접 액세스할 수 있습니다.

```
CReBarCtrl& GetReBarCtrl() const;
```

### <a name="return-value"></a>반환 값

[Cre바 ctrl](../../mfc/reference/crebarctrl-class.md) 개체에 대 한 참조입니다.

### <a name="remarks"></a>설명

이 멤버 함수를 호출 하 여 rebar 사용자 지정에서 Windows rebar 공용 컨트롤의 기능을 활용 합니다. 를 호출 `GetReBarCtrl`하면 멤버 함수 집합을 사용할 수 있도록 `CReBarCtrl` 개체에 대 한 참조 개체를 반환 합니다.

를 사용 `CReBarCtrl` 하 여 rebar를 사용자 지정 하는 방법에 대 한 자세한 내용은 [crebarctrl 사용](../../mfc/using-crebarctrl.md)을 참조 하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CReBarCtrl#2](../../mfc/reference/codesnippet/cpp/crebar-class_2.cpp)]

## <a name="see-also"></a>참고자료

[MFC 샘플 MFCIE](../../overview/visual-cpp-samples.md)<br/>
[CControlBar 클래스](../../mfc/reference/ccontrolbar-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
