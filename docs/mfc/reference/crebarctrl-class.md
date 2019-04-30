---
title: CReBarCtrl 클래스
ms.date: 11/19/2018
f1_keywords:
- CReBarCtrl
- AFXCMN/CReBarCtrl
- AFXCMN/CReBarCtrl::CReBarCtrl
- AFXCMN/CReBarCtrl::BeginDrag
- AFXCMN/CReBarCtrl::Create
- AFXCMN/CReBarCtrl::CreateEx
- AFXCMN/CReBarCtrl::DeleteBand
- AFXCMN/CReBarCtrl::DragMove
- AFXCMN/CReBarCtrl::EndDrag
- AFXCMN/CReBarCtrl::GetBandBorders
- AFXCMN/CReBarCtrl::GetBandCount
- AFXCMN/CReBarCtrl::GetBandInfo
- AFXCMN/CReBarCtrl::GetBandMargins
- AFXCMN/CReBarCtrl::GetBarHeight
- AFXCMN/CReBarCtrl::GetBarInfo
- AFXCMN/CReBarCtrl::GetBkColor
- AFXCMN/CReBarCtrl::GetColorScheme
- AFXCMN/CReBarCtrl::GetDropTarget
- AFXCMN/CReBarCtrl::GetExtendedStyle
- AFXCMN/CReBarCtrl::GetImageList
- AFXCMN/CReBarCtrl::GetPalette
- AFXCMN/CReBarCtrl::GetRect
- AFXCMN/CReBarCtrl::GetRowCount
- AFXCMN/CReBarCtrl::GetRowHeight
- AFXCMN/CReBarCtrl::GetTextColor
- AFXCMN/CReBarCtrl::GetToolTips
- AFXCMN/CReBarCtrl::HitTest
- AFXCMN/CReBarCtrl::IDToIndex
- AFXCMN/CReBarCtrl::InsertBand
- AFXCMN/CReBarCtrl::MaximizeBand
- AFXCMN/CReBarCtrl::MinimizeBand
- AFXCMN/CReBarCtrl::MoveBand
- AFXCMN/CReBarCtrl::PushChevron
- AFXCMN/CReBarCtrl::RestoreBand
- AFXCMN/CReBarCtrl::SetBandInfo
- AFXCMN/CReBarCtrl::SetBandWidth
- AFXCMN/CReBarCtrl::SetBarInfo
- AFXCMN/CReBarCtrl::SetBkColor
- AFXCMN/CReBarCtrl::SetColorScheme
- AFXCMN/CReBarCtrl::SetExtendedStyle
- AFXCMN/CReBarCtrl::SetImageList
- AFXCMN/CReBarCtrl::SetOwner
- AFXCMN/CReBarCtrl::SetPalette
- AFXCMN/CReBarCtrl::SetTextColor
- AFXCMN/CReBarCtrl::SetToolTips
- AFXCMN/CReBarCtrl::SetWindowTheme
- AFXCMN/CReBarCtrl::ShowBand
- AFXCMN/CReBarCtrl::SizeToRect
helpviewer_keywords:
- CReBarCtrl [MFC], CReBarCtrl
- CReBarCtrl [MFC], BeginDrag
- CReBarCtrl [MFC], Create
- CReBarCtrl [MFC], CreateEx
- CReBarCtrl [MFC], DeleteBand
- CReBarCtrl [MFC], DragMove
- CReBarCtrl [MFC], EndDrag
- CReBarCtrl [MFC], GetBandBorders
- CReBarCtrl [MFC], GetBandCount
- CReBarCtrl [MFC], GetBandInfo
- CReBarCtrl [MFC], GetBandMargins
- CReBarCtrl [MFC], GetBarHeight
- CReBarCtrl [MFC], GetBarInfo
- CReBarCtrl [MFC], GetBkColor
- CReBarCtrl [MFC], GetColorScheme
- CReBarCtrl [MFC], GetDropTarget
- CReBarCtrl [MFC], GetExtendedStyle
- CReBarCtrl [MFC], GetImageList
- CReBarCtrl [MFC], GetPalette
- CReBarCtrl [MFC], GetRect
- CReBarCtrl [MFC], GetRowCount
- CReBarCtrl [MFC], GetRowHeight
- CReBarCtrl [MFC], GetTextColor
- CReBarCtrl [MFC], GetToolTips
- CReBarCtrl [MFC], HitTest
- CReBarCtrl [MFC], IDToIndex
- CReBarCtrl [MFC], InsertBand
- CReBarCtrl [MFC], MaximizeBand
- CReBarCtrl [MFC], MinimizeBand
- CReBarCtrl [MFC], MoveBand
- CReBarCtrl [MFC], PushChevron
- CReBarCtrl [MFC], RestoreBand
- CReBarCtrl [MFC], SetBandInfo
- CReBarCtrl [MFC], SetBandWidth
- CReBarCtrl [MFC], SetBarInfo
- CReBarCtrl [MFC], SetBkColor
- CReBarCtrl [MFC], SetColorScheme
- CReBarCtrl [MFC], SetExtendedStyle
- CReBarCtrl [MFC], SetImageList
- CReBarCtrl [MFC], SetOwner
- CReBarCtrl [MFC], SetPalette
- CReBarCtrl [MFC], SetTextColor
- CReBarCtrl [MFC], SetToolTips
- CReBarCtrl [MFC], SetWindowTheme
- CReBarCtrl [MFC], ShowBand
- CReBarCtrl [MFC], SizeToRect
ms.assetid: 154570d7-e48c-425d-8c7e-c64542bcb4cc
ms.openlocfilehash: db72dbab14db69f14d7c3d813562ec661df4b424
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62372392"
---
# <a name="crebarctrl-class"></a>CReBarCtrl 클래스

자식 창의 컨테이너인 rebar 컨트롤의 기능을 캡슐화합니다.

## <a name="syntax"></a>구문

```
class CReBarCtrl : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CReBarCtrl::CReBarCtrl](#crebarctrl)|`CReBarCtrl` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CReBarCtrl::BeginDrag](#begindrag)|끌어서 놓기 모드로 rebar 컨트롤을 배치합니다.|
|[CReBarCtrl::Create](#create)|Rebar 컨트롤을 만들고에 연결 된 `CReBarCtrl` 개체입니다.|
|[CReBarCtrl::CreateEx](#createex)|지정 된 Windows 확장된 스타일을 사용 하 여 rebar 컨트롤을 만들고 연결 하는 `CReBarCtrl` 개체입니다.|
|[CReBarCtrl::DeleteBand](#deleteband)|Rebar 컨트롤에서 밴드를 삭제합니다.|
|[CReBarCtrl::DragMove](#dragmove)|Rebar 컨트롤에서 끌어서 위치에 대 한 호출 후 업데이트 `BeginDrag`합니다.|
|[CReBarCtrl::EndDrag](#enddrag)|Rebar 컨트롤의 끌어서 놓기 작업을 종료합니다.|
|[CReBarCtrl::GetBandBorders](#getbandborders)|밴드의 테두리를 검색합니다.|
|[CReBarCtrl::GetBandCount](#getbandcount)|Rebar 컨트롤에서 현재 밴드의 수를 검색합니다.|
|[CReBarCtrl::GetBandInfo](#getbandinfo)|Rebar 컨트롤에서 밴드를 지정된 하는 방법에 대 한 정보를 검색 합니다.|
|[CReBarCtrl::GetBandMargins](#getbandmargins)|밴드의 여백을 검색합니다.|
|[CReBarCtrl::GetBarHeight](#getbarheight)|Rebar 컨트롤의 높이 검색합니다.|
|[CReBarCtrl::GetBarInfo](#getbarinfo)|사용 하 여 이미지 목록과 rebar 컨트롤에 대 한 정보를 검색 합니다.|
|[CReBarCtrl::GetBkColor](#getbkcolor)|Rebar 컨트롤의 기본 배경색을 검색합니다.|
|[CReBarCtrl::GetColorScheme](#getcolorscheme)|검색 된 [COLORSCHEME](/windows/desktop/api/commctrl/ns-commctrl-tagcolorscheme) rebar 컨트롤을 사용 하 여 연결 된 구조입니다.|
|[CReBarCtrl::GetDropTarget](#getdroptarget)|Rebar 컨트롤의 검색 `IDropTarget` 인터페이스 포인터입니다.|
|[CReBarCtrl::GetExtendedStyle](#getextendedstyle)|현재 rebar 컨트롤의 확장된 스타일을 가져옵니다.|
|[CReBarCtrl::GetImageList](#getimagelist)|Rebar 컨트롤에 연결 된 이미지 목록을 검색 합니다.|
|[CReBarCtrl::GetPalette](#getpalette)|Rebar 컨트롤의 현재 색상표를 검색합니다.|
|[CReBarCtrl::GetRect](#getrect)|Rebar 컨트롤에서 밴드를 지정된에 대 한 경계 사각형을 검색합니다.|
|[CReBarCtrl::GetRowCount](#getrowcount)|Rebar 컨트롤에서 밴드 행의 수를 검색 합니다.|
|[CReBarCtrl::GetRowHeight](#getrowheight)|Rebar 컨트롤에서 지정된 된 행의 높이 검색합니다.|
|[CReBarCtrl::GetTextColor](#gettextcolor)|Rebar 컨트롤의 기본 텍스트 색을 검색합니다.|
|[CReBarCtrl::GetToolTips](#gettooltips)|Rebar 컨트롤에 연결 된 모든 도구 설명 컨트롤에 대 한 핸들을 검색 합니다.|
|[CReBarCtrl::HitTest](#hittest)|Rebar 밴드 이때 있으면 화면의 지정 된 시점 rebar 밴드의 부분 인지 확인 합니다.|
|[CReBarCtrl::IDToIndex](#idtoindex)|Rebar 컨트롤에서 밴드 인덱스를 대역 외 식별자 (ID)를 변환합니다.|
|[CReBarCtrl::InsertBand](#insertband)|Rebar 컨트롤에서 새 밴드를 삽입합니다.|
|[CReBarCtrl::MaximizeBand](#maximizeband)|가장 큰 크기로 rebar 컨트롤에서 밴드의 크기를 조정 합니다.|
|[CReBarCtrl::MinimizeBand](#minimizeband)|가장 작은 크기로 rebar 컨트롤에서 밴드의 크기를 조정 합니다.|
|[CReBarCtrl::MoveBand](#moveband)|다른 한 인덱스에서 밴드를 이동합니다.|
|[CReBarCtrl::PushChevron](#pushchevron)|갈매기형 펼침 단추를 프로그래밍 방식으로 푸시합니다.|
|[CReBarCtrl::RestoreBand](#restoreband)|이상적인 크기를 rebar 컨트롤에서 밴드의 크기를 조정 합니다.|
|[CReBarCtrl::SetBandInfo](#setbandinfo)|Rebar 컨트롤에서 기존는 대역 외의 특성을 설정합니다.|
|[CReBarCtrl::SetBandWidth](#setbandwidth)|현재는 rebar 컨트롤에서 지정 된 도킹된 대역의 너비를 설정합니다.|
|[CReBarCtrl::SetBarInfo](#setbarinfo)|Rebar 컨트롤의 특성을 설정합니다.|
|[CReBarCtrl::SetBkColor](#setbkcolor)|Rebar 컨트롤의 기본 배경색을 설정합니다.|
|[CReBarCtrl::SetColorScheme](#setcolorscheme)|Rebar 컨트롤에서 단추에 대 한 색 구성표를 설정합니다.|
|[CReBarCtrl::SetExtendedStyle](#setextendedstyle)|현재 rebar 컨트롤에 대 한 확장된 스타일을 설정합니다.|
|[CReBarCtrl::SetImageList](#setimagelist)|Rebar 컨트롤의 이미지 목록을 설정 합니다.|
|[CReBarCtrl::SetOwner](#setowner)|Rebar 컨트롤의 소유자 창을 설정입니다.|
|[CReBarCtrl::SetPalette](#setpalette)|Rebar 컨트롤의 현재 색상표를 설정합니다.|
|[CReBarCtrl::SetTextColor](#settextcolor)|Rebar 컨트롤의 기본 텍스트 색을 설정합니다.|
|[CReBarCtrl::SetToolTips](#settooltips)|Rebar 컨트롤 도구 설명 컨트롤에 연결합니다.|
|[CReBarCtrl::SetWindowTheme](#setwindowtheme)|Rebar 컨트롤의 비주얼 스타일을 설정합니다.|
|[CReBarCtrl::ShowBand](#showband)|표시 하거나 숨깁니다 rebar 컨트롤에서 밴드를 지정된 합니다.|
|[CReBarCtrl::SizeToRect](#sizetorect)|지정 된 사각형에 rebar 컨트롤에 맞춥니다.|

## <a name="remarks"></a>설명

Rebar 컨트롤 상주 하는 응용 프로그램 크기 조정 막대 밴드를 rebar 컨트롤에 포함 된 자식 창을 할당 합니다. 자식 창에는 일반적으로 다른 일반적인 컨트롤입니다.

Rebar 컨트롤 하나 이상의 밴드를 포함 합니다. 각 밴드에는 그리퍼 막대, 비트맵, 텍스트 레이블 및 자식 창이 조합을 포함할 수 있습니다. 밴드에는 이러한 각 항목 중 하나만 포함할 수 있습니다.

Rebar 컨트롤에는 지정 된 배경 비트맵을 통해 자식 창을 표시할 수 있습니다. RBBS_FIXEDSIZE 스타일을 사용 하는 작업을 제외한 모든 rebar 컨트롤 밴드를 조정할 수 있습니다. Rebar 컨트롤 밴드의 크기를 조정 하거나 위치를 변경 하면 rebar 컨트롤 크기와 해당 대역 외에 할당 된 자식 창의 위치를 관리 합니다. 크기를 조정 하거나 컨트롤 내에서 밴드의 순서를 변경, 클릭 하 고 밴드의 그리퍼 막대를 끌어 옵니다.

다음 그림에서는 3 개의 밴드가 있는 rebar 컨트롤을 보여 줍니다.

- 0 대역 외 플랫, 투명 한 도구 모음 컨트롤을 포함합니다.

- 대역 외 1에는 모두 투명 한 표준 및 투명 한 드롭다운 단추가 포함 됩니다.

- 대역 외 2 콤보 상자 및 표준 단추 4 개를 포함합니다.

   ![Rebar 메뉴 예가](../../mfc/reference/media/vc4scc1.gif "Rebar 메뉴의 예")

## <a name="rebar-control"></a>Rebar 컨트롤

Rebar 컨트롤 지원:

- 이미지를 나열합니다.

- 메시지 처리 합니다.

- 사용자 지정 기능을 그립니다.

- 다양 한 표준 창 스타일 외에도 컨트롤 스타일입니다. 이러한 스타일의 목록은 참조 하세요 [Rebar 컨트롤 스타일](/windows/desktop/Controls/rebar-control-styles) Windows SDK에 있습니다.

자세한 내용은 [를 사용 하 여 CReBarCtrl](../../mfc/using-crebarctrl.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CReBarCtrl`

## <a name="requirements"></a>요구 사항

**헤더:** afxcmn.h

##  <a name="begindrag"></a>  CReBarCtrl::BeginDrag

Win32 메시지의 동작을 구현 [RB_BEGINDRAG](/windows/desktop/Controls/rb-begindrag)Windows SDK에 설명 된 대로 합니다.

```
void BeginDrag(
    UINT uBand,
    DWORD dwPos = (DWORD)-1);
```

### <a name="parameters"></a>매개 변수

*uBand*<br/>
끌어서 놓기 작업이 영향을 주는 밴드의 0부터 시작 인덱스입니다.

*dwPos*<br/>
시작을 포함 하는 DWORD 값 마우스 좌표입니다. 가로 좌표는 LOWORD 안에 및 세로 좌표는 HIWORD에 포함 됩니다. Rebar 컨트롤에 마지막으로 호출 하는 컨트롤의 스레드는 마우스의 위치가 사용 됩니다 (DWORD)-1을 전달 하면 `GetMessage` 또는 `PeekMessage`합니다.

##  <a name="create"></a>  CReBarCtrl::Create

Rebar 컨트롤을 만들고에 연결 된 `CReBarCtrl` 개체입니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
컨트롤에 적용 되는 rebar 컨트롤 스타일의 조합을 지정 합니다. 참조 [Rebar 컨트롤 스타일](/windows/desktop/Controls/rebar-control-styles) 지원 되는 스타일의 목록은 Windows SDK에 있습니다.

*rect*<br/>
에 대 한 참조를 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](/previous-versions/dd162897\(v=vs.85\)) rebar 컨트롤의 크기와 위치는 구조입니다.

*pParentWnd*<br/>
에 대 한 포인터를 [CWnd](../../mfc/reference/cwnd-class.md) 개체 rebar 컨트롤의 부모 창입니다. NULL이 아니어야 합니다.

*nID*<br/>
Rebar 컨트롤의 컨트롤 ID를 지정 합니다.

### <a name="return-value"></a>반환 값

개체가 성공적으로 만들어진 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

2 단계를 거쳐에서 rebar 컨트롤을 만듭니다.

1. 호출 [CReBarCtrl](#crebarctrl) 생성 하는 `CReBarCtrl` 개체입니다.

1. Windows rebar 컨트롤을 만들고에 연결 하는이 멤버 함수를 호출 합니다 `CReBarCtrl` 개체입니다.

호출 하는 경우 `Create`, 공용 컨트롤 초기화 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CReBarCtrl#3](../../mfc/reference/codesnippet/cpp/crebarctrl-class_1.cpp)]

##  <a name="createex"></a>  CReBarCtrl::CreateEx

컨트롤 (자식 창)을 만들고 사용 하 여 연결 된 `CReBarCtrl` 개체입니다.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwExStyle*<br/>
만들려는 컨트롤의 확장된 스타일을 지정 합니다. 확장 된 Windows 스타일의 목록은 참조 하세요. 합니다 *dwExStyle* 에 대 한 매개 변수 [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) Windows SDK의 합니다.

*dwStyle*<br/>
컨트롤에 적용 되는 rebar 컨트롤 스타일의 조합을 지정 합니다. 지원 되는 스타일의 목록은 참조 하세요 [Rebar 컨트롤 스타일](/windows/desktop/Controls/rebar-control-styles) Windows SDK에 있습니다.

*rect*<br/>
에 대 한 참조를 [RECT](/previous-versions/dd162897\(v=vs.85\)) 크기와의 클라이언트 좌표에서 만든 창의 위치를 설명 하는 구조 *pParentWnd*합니다.

*pParentWnd*<br/>
컨트롤의 부모 창에 대 한 포인터입니다.

*nID*<br/>
컨트롤의 자식 창 id입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

사용 하 여 `CreateEx` of [Create](#create) Windows 확장된 스타일 앞으로 지정 된 Windows 확장된 스타일을 적용할 **WS_EX_** 합니다.

##  <a name="crebarctrl"></a>  CReBarCtrl::CReBarCtrl

`CReBarCtrl` 개체를 만듭니다.

```
CReBarCtrl();
```

### <a name="example"></a>예제

  예를 참조 하세요 [CReBarCtrl::Create](#create)합니다.

##  <a name="deleteband"></a>  CReBarCtrl::DeleteBand

Win32 메시지의 동작을 구현 [RB_DELETEBAND](/windows/desktop/Controls/rb-deleteband)Windows SDK에 설명 된 대로 합니다.

```
BOOL DeleteBand(UINT uBand);
```

### <a name="parameters"></a>매개 변수

*uBand*<br/>
삭제할 밴드의 0부터 시작 인덱스입니다.

### <a name="return-value"></a>반환 값

밴드 성공적으로 삭제 하는 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CReBarCtrl#4](../../mfc/reference/codesnippet/cpp/crebarctrl-class_2.cpp)]

##  <a name="dragmove"></a>  CReBarCtrl::DragMove

Win32 메시지의 동작을 구현 [RB_DRAGMOVE](/windows/desktop/Controls/rb-dragmove)Windows SDK에 설명 된 대로 합니다.

```
void DragMove(DWORD dwPos = (DWORD)-1);
```

### <a name="parameters"></a>매개 변수

*dwPos*<br/>
새 마우스 좌표를 포함 하는 DWORD 값입니다. 가로 좌표는 LOWORD 안에 및 세로 좌표는 HIWORD에 포함 됩니다. Rebar 컨트롤에 마지막으로 호출 하는 컨트롤의 스레드는 마우스의 위치가 사용 됩니다 (DWORD)-1을 전달 하면 `GetMessage` 또는 `PeekMessage`합니다.

##  <a name="enddrag"></a>  CReBarCtrl::EndDrag

Win32 메시지의 동작을 구현 [RB_ENDDRAG](/windows/desktop/Controls/rb-enddrag)Windows SDK에 설명 된 대로 합니다.

```
void EndDrag();
```

##  <a name="getbandborders"></a>  CReBarCtrl::GetBandBorders

Win32 메시지의 동작을 구현 [RB_GETBANDBORDERS](/windows/desktop/Controls/rb-getbandborders)Windows SDK에 설명 된 대로 합니다.

```
void GetBandBorders(
    UINT uBand,
    LPRECT prc) const;
```

### <a name="parameters"></a>매개 변수

*uBand*<br/>
테두리를 검색 하는 대역 외의 0부터 시작 인덱스입니다.

*prc*<br/>
에 대 한 포인터를 [RECT](/previous-versions/dd162897\(v=vs.85\)) 대역 외 테두리 받을 구조입니다. Rebar 컨트롤 RBS_BANDBORDERS 스타일에이 구조의 각 멤버의 픽셀 대역 외에서의 해당 쪽에 테두리를 구성 하는 수를 받게 됩니다. Rebar 컨트롤 RBS_BANDBORDERS 스타일에 없는 경우이 구조체의 왼쪽된 멤버에만 유효한 정보를 받습니다. Rebar 컨트롤 스타일에 대 한 참조 [Rebar 컨트롤 스타일](/windows/desktop/Controls/rebar-control-styles) Windows SDK에 있습니다.

##  <a name="getbandcount"></a>  CReBarCtrl::GetBandCount

Win32 메시지의 동작을 구현 [RB_GETBANDCOUNT](/windows/desktop/Controls/rb-getbandcount)Windows SDK에 설명 된 대로 합니다.

```
UINT GetBandCount() const;
```

### <a name="return-value"></a>반환 값

컨트롤에 할당 되는 밴드의 수입니다.

##  <a name="getbandinfo"></a>  CReBarCtrl::GetBandInfo

Win32 메시지의 동작을 구현 [RB_GETBANDINFO](/windows/desktop/Controls/rb-getbandinfo) Windows SDK에 설명 된 대로 합니다.

```
BOOL GetBandInfo(
    UINT uBand,
    REBARBANDINFO* prbbi) const;
```

### <a name="parameters"></a>매개 변수

*uBand*<br/>
정보를 검색할 수 밴드의 0부터 시작 인덱스입니다.

*prbbi*<br/>
에 대 한 포인터를 [REBARBANDINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarbandinfoa) 구조 대역 외 정보를 얻습니다. 설정 해야 합니다는 `cbSize` 이 구조체의 멤버 `sizeof(REBARBANDINFO)` 설정의 `fMask` 이 메시지를 보내기 전에 검색 하려는 항목에는 멤버입니다.

### <a name="return-value"></a>반환 값

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

##  <a name="getbandmargins"></a>  CReBarCtrl::GetBandMargins

밴드의 여백을 검색합니다.

```
void GetBandMargins(PMARGINS pMargins);
```

### <a name="parameters"></a>매개 변수

*pMargins*<br/>
에 대 한 포인터를 [여백](/windows/desktop/api/uxtheme/ns-uxtheme-_margins)구조는 정보를 받게 됩니다.

### <a name="remarks"></a>설명

이 멤버 함수는의 기능을 에뮬레이션 합니다 [RB_GETBANDMARGINS](/windows/desktop/Controls/rb-getbandmargins) Windows SDK에 설명 된 대로 메시지입니다.

##  <a name="getbarheight"></a>  CReBarCtrl::GetBarHeight

Rebar 막대의 높이 검색합니다.

```
UINT GetBarHeight() const;
```

### <a name="return-value"></a>반환 값

컨트롤의 픽셀에서 높이 나타내는 값입니다.

##  <a name="getbarinfo"></a>  CReBarCtrl::GetBarInfo

Win32 메시지의 동작을 구현 [RB_GETBARINFO](/windows/desktop/Controls/rb-getbarinfo)Windows SDK에 설명 된 대로 합니다.

```
BOOL GetBarInfo(REBARINFO* prbi) const;
```

### <a name="parameters"></a>매개 변수

*prbi*<br/>
에 대 한 포인터를 [REBARINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarinfo) rebar 컨트롤 정보를 받는 구조체입니다. 설정 해야 합니다 *cbSize* 이 구조의 멤버 `sizeof(REBARINFO)` 이 메시지를 보내기 전에 합니다.

### <a name="return-value"></a>반환 값

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

##  <a name="getbkcolor"></a>  CReBarCtrl::GetBkColor

Win32 메시지의 동작을 구현 [RB_GETBKCOLOR](/windows/desktop/Controls/rb-getbkcolor)Windows SDK에 설명 된 대로 합니다.

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>반환 값

현재 기본 배경색을 나타내는 COLORREF 값입니다.

##  <a name="getcolorscheme"></a>  CReBarCtrl::GetColorScheme

검색 된 [COLORSCHEME](/windows/desktop/api/commctrl/ns-commctrl-tagcolorscheme) rebar 컨트롤에 대 한 구조입니다.

```
BOOL GetColorScheme(COLORSCHEME* lpcs);
```

### <a name="parameters"></a>매개 변수

*lpcs*<br/>
에 대 한 포인터를 [COLORSCHEME](/windows/desktop/api/commctrl/ns-commctrl-tagcolorscheme) Windows SDK에 설명 된 대로 구조체입니다.

### <a name="return-value"></a>반환 값

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

`COLORSCHEME` 단추 강조 표시 색 및 단추 그림자 색 구조에 포함 되어 있습니다.

##  <a name="getdroptarget"></a>  CReBarCtrl::GetDropTarget

Win32 메시지의 동작을 구현 [RB_GETDROPTARGET](/windows/desktop/Controls/rb-getdroptarget)Windows SDK에 설명 된 대로 합니다.

```
IDropTarget* GetDropTarget() const;
```

### <a name="return-value"></a>반환 값

에 대 한 포인터를 [IDropTarget](/windows/desktop/api/oleidl/nn-oleidl-idroptarget) 인터페이스입니다.

##  <a name="getextendedstyle"></a>  CReBarCtrl::GetExtendedStyle

현재 rebar 컨트롤의 확장된 스타일을 가져옵니다.

```
DWORD GetExtendedStyle() const;
```

### <a name="return-value"></a>반환 값

확장된 스타일 플래그의 비트 조합 (OR)입니다. 가능한 플래그는 RBS_EX_SPLITTER 및 RBS_EX_TRANSPARENT입니다. 자세한 내용은 참조는 *dwMask* 의 매개 변수를 [CReBarCtrl::SetExtendedStyle](#setextendedstyle) 메서드.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [RB_GETEXTENDEDSTYLE](/windows/desktop/Controls/rb-dragmove) Windows SDK에 설명 된 메시지입니다.

##  <a name="getimagelist"></a>  CReBarCtrl::GetImageList

가져옵니다는 `CImageList` rebar 컨트롤에 연결 된 개체입니다.

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>반환 값

에 대 한 포인터를 [CImageList](../../mfc/reference/cimagelist-class.md) 개체입니다. 이미지 목록이 없는 컨트롤에 대해 설정 된 경우 NULL을 반환 합니다.

### <a name="remarks"></a>설명

이 멤버 함수에 저장 된 크기와 마스크 정보를 사용 합니다 [REBARINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarinfo) Windows SDK에 설명 된 대로 구조체입니다.

##  <a name="getpalette"></a>  CReBarCtrl::GetPalette

Rebar 컨트롤의 현재 색상표를 검색합니다.

```
CPalette* GetPalette() const;
```

### <a name="return-value"></a>반환 값

에 대 한 포인터를 [CPalette](../../mfc/reference/cpalette-class.md) rebar 컨트롤의 현재 색상표를 지정 하는 개체입니다.

### <a name="remarks"></a>설명

이 멤버 함수를 사용 하는 참고를 `CPalette` 는 HPALETTE 보다는 해당 반환 값으로는 개체입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CReBarCtrl#5](../../mfc/reference/codesnippet/cpp/crebarctrl-class_3.cpp)]

##  <a name="getrect"></a>  CReBarCtrl::GetRect

Win32 메시지의 동작을 구현 [RB_GETRECT](/windows/desktop/Controls/rb-getrect)Windows SDK에 설명 된 대로 합니다.

```
BOOL GetRect(
    UINT uBand,
    LPRECT prc) const;
```

### <a name="parameters"></a>매개 변수

*uBand*<br/>
Rebar 컨트롤에서 밴드의 0부터 시작 인덱스입니다.

*prc*<br/>
에 대 한 포인터를 [RECT](/previous-versions/dd162897\(v=vs.85\)) 구조는 rebar 밴드의 경계를 받게 됩니다.

### <a name="return-value"></a>반환 값

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CReBarCtrl#6](../../mfc/reference/codesnippet/cpp/crebarctrl-class_4.cpp)]

##  <a name="getrowcount"></a>  CReBarCtrl::GetRowCount

Win32 메시지의 동작을 구현 [RB_GETROWCOUNT](/windows/desktop/Controls/rb-getrowcount)Windows SDK에 설명 된 대로 합니다.

```
UINT GetRowCount() const;
```

### <a name="return-value"></a>반환 값

컨트롤에서 밴드 행의 수를 나타내는 UINT 값입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CReBarCtrl#7](../../mfc/reference/codesnippet/cpp/crebarctrl-class_5.cpp)]

##  <a name="getrowheight"></a>  CReBarCtrl::GetRowHeight

Win32 메시지의 동작을 구현 [RB_GETROWHEIGHT](/windows/desktop/Controls/rb-getrowheight)Windows SDK에 설명 된 대로 합니다.

```
UINT GetRowHeight(UINT uRow) const;
```

### <a name="parameters"></a>매개 변수

*uRow*<br/>
검색할 높이가 갖게 되는 대역 외의 0부터 시작 인덱스입니다.

### <a name="return-value"></a>반환 값

행 높이 픽셀 단위로 나타내는 UINT 값입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CReBarCtrl#8](../../mfc/reference/codesnippet/cpp/crebarctrl-class_6.cpp)]

##  <a name="gettextcolor"></a>  CReBarCtrl::GetTextColor

Win32 메시지의 동작을 구현 [RB_GETTEXTCOLOR](/windows/desktop/Controls/rb-gettextcolor)Windows SDK에 설명 된 대로 합니다.

```
COLORREF GetTextColor() const;
```

### <a name="return-value"></a>반환 값

현재 기본 텍스트 색을 나타내는 COLORREF 값입니다.

##  <a name="gettooltips"></a>  CReBarCtrl::GetToolTips

Win32 메시지의 동작을 구현 [RB_GETTOOLTIPS](/windows/desktop/Controls/rb-gettooltips)Windows SDK에 설명 된 대로 합니다.

```
CToolTipCtrl* GetToolTips() const;
```

### <a name="return-value"></a>반환 값

에 대 한 포인터를 [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) 개체입니다.

### <a name="remarks"></a>설명

MFC 구현 `GetToolTips` 에 대 한 포인터를 반환 합니다.는 `CToolTipCtrl`, HWND 대신 합니다.

##  <a name="hittest"></a>  CReBarCtrl::HitTest

Win32 메시지의 동작을 구현 [RB_HITTEST](/windows/desktop/Controls/rb-hittest)Windows SDK에 설명 된 대로 합니다.

```
int HitTest(RBHITTESTINFO* prbht);
```

### <a name="parameters"></a>매개 변수

*prbht*<br/>
에 대 한 포인터를 [RBHITTESTINFO](/windows/desktop/api/commctrl/ns-commctrl-_rb_hittestinfo) 구조입니다. 메시지를 보내기 전에 `pt` 클라이언트 좌표에서 테스트할 수는 지점으로이 구조체의 멤버를 초기화 합니다.

### <a name="return-value"></a>반환 값

지정된 된 지점 또는 지점에 없는 rebar 밴드 되었으면-1에서 밴드의 0부터 시작 하는 인덱스입니다.

##  <a name="idtoindex"></a>  CReBarCtrl::IDToIndex

Win32 메시지의 동작을 구현 [RB_IDTOINDEX](https://msdn.microsoft.com/library/windows/desktop/bb774496)Windows SDK에 설명 된 대로 합니다.

```
int IDToIndex(UINT uBandID) const;
```

### <a name="parameters"></a>매개 변수

*uBandID*<br/>
전달 된 지정된 된 밴드의 응용 프로그램 정의 식별자를 `wID` 의 멤버는 [REBARBANDINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarbandinfoa) 밴드를 삽입할 때 구조체입니다.

### <a name="return-value"></a>반환 값

성공 하면 0부터 시작 밴드 인덱스 또는 그렇지 않으면-1입니다. 중복 밴드 인덱스 존재 하는 경우 첫 번째 반환 됩니다.

##  <a name="insertband"></a>  CReBarCtrl::InsertBand

Win32 메시지의 동작을 구현 [RB_INSERTBAND](/windows/desktop/Controls/rb-insertband)Windows SDK에 설명 된 대로 합니다.

```
BOOL InsertBand(
    UINT uIndex,
    REBARBANDINFO* prbbi);
```

### <a name="parameters"></a>매개 변수

*uIndex*<br/>
밴드를 삽입할 위치의 인덱스 0부터 시작 합니다. 이 매개 변수를-1로 설정한 경우 컨트롤 마지막 위치에 새 밴드를 추가 합니다.

*prbbi*<br/>
에 대 한 포인터를 [REBARBANDINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarbandinfoa) 삽입할 밴드를 정의 하는 구조입니다. 설정 해야 합니다 *cbSize* 이 구조의 멤버 `sizeof(REBARBANDINFO)` 이 함수를 호출 하기 전에 합니다.

### <a name="return-value"></a>반환 값

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CReBarCtrl#9](../../mfc/reference/codesnippet/cpp/crebarctrl-class_7.cpp)]

##  <a name="maximizeband"></a>  CReBarCtrl::MaximizeBand

가장 큰 크기로 rebar 컨트롤에서 밴드의 크기를 조정 합니다.

```
void MaximizeBand(UINT uBand);
```

### <a name="parameters"></a>매개 변수

*uBand*<br/>
최대화 밴드의 0부터 시작 인덱스입니다.

### <a name="remarks"></a>설명

Win32 메시지의 동작을 구현 [RB_MAXIMIZEBAND](/windows/desktop/Controls/rb-maximizeband) 사용 하 여 `fIdeal` Windows SDK에 설명 된 대로 0으로 설정 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CReBarCtrl#10](../../mfc/reference/codesnippet/cpp/crebarctrl-class_8.cpp)]

##  <a name="minimizeband"></a>  CReBarCtrl::MinimizeBand

가장 작은 크기로 rebar 컨트롤에서 밴드의 크기를 조정 합니다.

```
void MinimizeBand(UINT uBand);
```

### <a name="parameters"></a>매개 변수

*uBand*<br/>
밴드를 최소화할 수의 0부터 시작 인덱스입니다.

### <a name="remarks"></a>설명

Win32 메시지의 동작을 구현 [RB_MINIMIZEBAND](/windows/desktop/Controls/rb-minimizeband)Windows SDK에 설명 된 대로 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CReBarCtrl#11](../../mfc/reference/codesnippet/cpp/crebarctrl-class_9.cpp)]

##  <a name="moveband"></a>  CReBarCtrl::MoveBand

Win32 메시지의 동작을 구현 [RB_MOVEBAND](/windows/desktop/Controls/rb-moveband)Windows SDK에 설명 된 대로 합니다.

```
BOOL MoveBand(
    UINT uFrom,
    UINT uTo);
```

### <a name="parameters"></a>매개 변수

*uFrom*<br/>
이동할 밴드의 0부터 시작 인덱스입니다.

*uTo*<br/>
새 밴드 위치의 0부터 시작 인덱스입니다. 이 매개 변수 값은 하지 밴드에서 1을 뺀 수보다 커야 합니다. 밴드의 번호를 가져오려면, 호출 [GetBandCount](#getbandcount)합니다.

### <a name="return-value"></a>반환 값

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

##  <a name="pushchevron"></a>  CReBarCtrl::PushChevron

Win32 메시지의 동작을 구현 [RB_PUSHCHEVRON](/windows/desktop/Controls/rb-pushchevron)Windows SDK에 설명 된 대로 합니다.

```
void PushChevron(
    UINT uBand,
    LPARAM lAppValue);
```

### <a name="parameters"></a>매개 변수

*uBand*<br/>
푸시할 수 있는 펼침 단추는 대역 외의 0부터 시작 인덱스입니다.

*lAppValue*<br/>
응용 프로그램에 32 비트 값으로 정의 합니다. 참조 *lAppValue* 에 [RB_PUSHCHEVRON](/windows/desktop/Controls/rb-pushchevron) Windows SDK에 있습니다.

##  <a name="restoreband"></a>  CReBarCtrl::RestoreBand

이상적인 크기를 rebar 컨트롤에서 밴드의 크기를 조정 합니다.

```
void RestoreBand(UINT uBand);
```

### <a name="parameters"></a>매개 변수

*uBand*<br/>
최대화 밴드의 0부터 시작 인덱스입니다.

### <a name="remarks"></a>설명

Win32 메시지의 동작을 구현 [RB_MAXIMIZEBAND](/windows/desktop/Controls/rb-maximizeband) 사용 하 여 `fIdeal` Windows SDK에 설명 된 대로 1로 설정 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CReBarCtrl#12](../../mfc/reference/codesnippet/cpp/crebarctrl-class_10.cpp)]

##  <a name="setbandinfo"></a>  CReBarCtrl::SetBandInfo

Win32 메시지의 동작을 구현 [RB_SETBANDINFO](/windows/desktop/Controls/rb-setbandinfo)Windows SDK에 설명 된 대로 합니다.

```
BOOL SetBandInfo(
    UINT uBand,
    REBARBANDINFO* prbbi);
```

### <a name="parameters"></a>매개 변수

*uBand*<br/>
새 설정을 수신 하려면 대역 외의 0부터 시작 인덱스입니다.

*prbbi*<br/>
에 대 한 포인터를 [REBARBANDINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarbandinfoa) 삽입할 밴드를 정의 하는 구조입니다. 설정 해야 합니다 `cbSize` 이 구조의 멤버 `sizeof(REBARBANDINFO)` 이 메시지를 보내기 전에 합니다.

### <a name="return-value"></a>반환 값

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CReBarCtrl#13](../../mfc/reference/codesnippet/cpp/crebarctrl-class_11.cpp)]

##  <a name="setbandwidth"></a>  CReBarCtrl::SetBandWidth

현재는 rebar 컨트롤에서 지정 된 도킹된 대역의 너비를 설정합니다.

```
BOOL SetBandWidth(
    UINT uBand,
    int cxWidth);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*uBand*|[in] Rebar 밴드의 0부터 시작 인덱스입니다.|
|*cxWidth*|[in] 새 너비 (픽셀 단위)는 rebar 밴드입니다.|

### <a name="return-value"></a>반환 값

메서드가 성공 하면 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [RB_SETBANDWIDTH](/windows/desktop/Controls/rb-setbandwidth) Windows SDK에 설명 된 메시지입니다.

### <a name="example"></a>예제

다음 코드 예제에서는 변수를 정의 `m_rebar`, 즉 현재 rebar 컨트롤에 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.

[!code-cpp[NVC_MFC_CReBarCtrl_s1#1](../../mfc/reference/codesnippet/cpp/crebarctrl-class_12.h)]

### <a name="example"></a>예제

다음 코드 예제에서는 각 rebar 밴드 동일한 너비를 설정 합니다.

[!code-cpp[NVC_MFC_CReBarCtrl_s1#2](../../mfc/reference/codesnippet/cpp/crebarctrl-class_13.cpp)]

##  <a name="setbarinfo"></a>  CReBarCtrl::SetBarInfo

Win32 메시지의 동작을 구현 [RB_SETBARINFO](/windows/desktop/Controls/rb-setbarinfo)Windows SDK에 설명 된 대로 합니다.

```
BOOL SetBarInfo(REBARINFO* prbi);
```

### <a name="parameters"></a>매개 변수

*prbi*<br/>
에 대 한 포인터를 [REBARINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarinfo) 설정 정보가 포함 된 구조체입니다. 설정 해야 합니다 `cbSize` 멤버를이 구조의 `sizeof(REBARINFO)` 이 메시지를 보내기 전에

### <a name="return-value"></a>반환 값

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CReBarCtrl#14](../../mfc/reference/codesnippet/cpp/crebarctrl-class_14.cpp)]

##  <a name="setbkcolor"></a>  CReBarCtrl::SetBkColor

Win32 메시지의 동작을 구현 [RB_SETBKCOLOR](/windows/desktop/Controls/rb-setbkcolor)Windows SDK에 설명 된 대로 합니다.

```
COLORREF SetBkColor(COLORREF clr);
```

### <a name="parameters"></a>매개 변수

*clr*<br/>
새 기본 배경색을 나타내는 COLORREF 값입니다.

### <a name="return-value"></a>반환 값

A [COLORREF](/windows/desktop/gdi/colorref) 이전 기본 배경색을 나타내는 값입니다.

### <a name="remarks"></a>설명

배경색을 설정 하는 경우 및 기본값을 설정 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.

##  <a name="setcolorscheme"></a>  CReBarCtrl::SetColorScheme

Rebar 컨트롤에서 단추에 대 한 색 구성표를 설정합니다.

```
void SetColorScheme(const COLORSCHEME* lpcs);
```

### <a name="parameters"></a>매개 변수

*lpcs*<br/>
에 대 한 포인터를 [COLORSCHEME](/windows/desktop/api/commctrl/ns-commctrl-tagcolorscheme) Windows SDK에 설명 된 대로 구조체입니다.

### <a name="remarks"></a>설명

`COLORSCHEME` 단추 강조 표시 색과 단추 그림자 색 구조에 포함 되어 있습니다.

##  <a name="setextendedstyle"></a>  CReBarCtrl::SetExtendedStyle

현재 rebar 컨트롤에 대 한 확장된 스타일을 설정합니다.

```
DWORD SetExtendedStyle(
    DWORD dwMask,
    DWORD dwStyleEx);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*dwMask*|[in] 에 플래그를 지정 하는 플래그의 비트 조합 (OR)는 *dwStyleEx* 매개 변수가 적용 됩니다. 다음 값 중 하나 이상을 사용 합니다.<br /><br /> RBS_EX_SPLITTER: 기본적으로 표시 분할자 아래에 가로 모드에서 및 오른쪽에 세로 모드에서.<br /><br /> RBS_EX_TRANSPARENT: 앞으로 [WM_ERASEBKGND](/windows/desktop/winmsg/wm-erasebkgnd) 부모 창에는 메시지입니다.|
|*dwStyleEx*|[in] 적용할 스타일을 지정 하는 플래그의 비트 조합 (OR)입니다. 스타일을 설정 하려면에서 사용 되는 동일한 플래그를 지정 합니다 *dwMask* 매개 변수입니다. 스타일을 재설정 하려면 이진 0을 지정 합니다.|

### <a name="return-value"></a>반환 값

이전 확장된 스타일입니다.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [RB_SETEXTENDEDSTYLE](/windows/desktop/Controls/rb-setextendedstyle) Windows SDK에 설명 된 메시지입니다.

##  <a name="setimagelist"></a>  CReBarCtrl::SetImageList

이미지 목록과 rebar 컨트롤에 할당합니다.

```
BOOL SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>매개 변수

*pImageList*<br/>
에 대 한 포인터를 [CImageList](../../mfc/reference/cimagelist-class.md) rebar 컨트롤에 할당할 이미지 목록을 포함 하는 개체입니다.

### <a name="return-value"></a>반환 값

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

##  <a name="setowner"></a>  CReBarCtrl::SetOwner

Win32 메시지의 동작을 구현 [RB_SETPARENT](/windows/desktop/Controls/rb-setparent)Windows SDK에 설명 된 대로 합니다.

```
CWnd* SetOwner(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
에 대 한 포인터를 `CWnd` rebar 컨트롤의 소유자로 설정할 개체입니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 [CWnd](../../mfc/reference/cwnd-class.md) rebar 컨트롤의 현재 소유자 인 개체입니다.

### <a name="remarks"></a>설명

이 멤버 함수에 대 한 포인터는 `CWnd` windows를 처리 하는 것이 아니라 rebar 컨트롤의 선택 하 고 현재 소유자에 대 한 개체입니다.

> [!NOTE]
>  이 멤버 함수는 컨트롤이 만들어진 때 설정 된 실제 부모를 변경 하지 않습니다. 대신 지정한 창에 알림 메시지를 보냅니다.

##  <a name="setpalette"></a>  CReBarCtrl::SetPalette

Win32 메시지의 동작을 구현 [RB_SETPALETTE](/windows/desktop/Controls/rb-setpalette)Windows SDK에 설명 된 대로 합니다.

```
CPalette* SetPalette(HPALETTE hPal);
```

### <a name="parameters"></a>매개 변수

*hPal*<br/>
Rebar 컨트롤에서 사용할 새 색상표를 지정 하는 HPALETTE 합니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 [CPalette](../../mfc/reference/cpalette-class.md) rebar 컨트롤의 이전 색상표를 지정 하는 개체입니다.

### <a name="remarks"></a>설명

이 멤버 함수를 사용 하는 참고를 `CPalette` 는 HPALETTE 보다는 해당 반환 값으로는 개체입니다.

##  <a name="settextcolor"></a>  CReBarCtrl::SetTextColor

Win32 메시지의 동작을 구현 [RB_SETTEXTCOLOR](/windows/desktop/Controls/rb-settextcolor)Windows SDK에 설명 된 대로 합니다.

```
COLORREF SetTextColor(COLORREF clr);
```

### <a name="parameters"></a>매개 변수

*clr*<br/>
새 텍스트를 나타내는 COLORREF 값 색은 `CReBarCtrl` 개체입니다.

### <a name="return-value"></a>반환 값

합니다 [COLORREF](/windows/desktop/gdi/colorref) 관련 된 이전 텍스트 색을 나타내는 값을 `CReBarCtrl` 개체입니다.

### <a name="remarks"></a>설명

Rebar 컨트롤에서 텍스트 색을 유연 하 게 제공 됩니다.

##  <a name="settooltips"></a>  CReBarCtrl::SetToolTips

Rebar 컨트롤 도구 설명 컨트롤에 연결합니다.

```
void SetToolTips(CToolTipCtrl* pToolTip);
```

### <a name="parameters"></a>매개 변수

*pToolTip*<br/>
에 대 한 포인터를 [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) 개체

### <a name="remarks"></a>설명

파기 해야 합니다는 `CToolTipCtrl` 되어 완료 되 면 개체입니다.

##  <a name="setwindowtheme"></a>  CReBarCtrl::SetWindowTheme

Rebar 컨트롤의 비주얼 스타일을 설정합니다.

```
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

### <a name="parameters"></a>매개 변수

*pszSubAppName*<br/>
Rebar 비주얼 스타일 집합을 포함 하는 유니코드 문자열 포인터입니다.

### <a name="return-value"></a>반환 값

반환 값은 사용 되지 않습니다.

### <a name="remarks"></a>설명

이 멤버 함수는의 기능을 에뮬레이션 합니다 [RB_SETWINDOWTHEME](/windows/desktop/Controls/rb-setwindowtheme) Windows SDK에 설명 된 대로 메시지입니다.

##  <a name="showband"></a>  CReBarCtrl::ShowBand

Win32 메시지의 동작을 구현 [RB_SHOWBAND](/windows/desktop/Controls/rb-showband)Windows SDK에 설명 된 대로 합니다.

```
BOOL ShowBand(
    UINT uBand,
    BOOL fShow = TRUE);
```

### <a name="parameters"></a>매개 변수

*uBand*<br/>
Rebar 컨트롤에서 밴드의 0부터 시작 인덱스입니다.

*fShow*<br/>
밴드를 표시 하거나 숨길 해야 하는 경우를 나타냅니다. 이 값이 TRUE 이면 밴드 표시 됩니다. 그렇지 않으면 밴드가 숨겨집니다.

### <a name="return-value"></a>반환 값

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

##  <a name="sizetorect"></a>  CReBarCtrl::SizeToRect

Win32 메시지의 동작을 구현 [RB_SIZETORECT](/windows/desktop/Controls/rb-sizetorect)Windows SDK에 설명 된 대로 합니다.

```
BOOL SizeToRect(CRect& rect);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
에 대 한 참조를 [CRect](../../atl-mfc-shared/reference/crect-class.md) rebar 컨트롤 크기를 조정 하는 사각형을 지정 하는 개체입니다.

### <a name="return-value"></a>반환 값

성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수를 사용 하는 참고를 `CRect` 개체를 매개 변수로 대신 `RECT` 구조입니다.

## <a name="see-also"></a>참고자료

[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
