---
title: CControlBar Class
ms.date: 11/04/2016
f1_keywords:
- CControlBar
- AFXEXT/CControlBar
- AFXEXT/CControlBar::CControlBar
- AFXEXT/CControlBar::CalcDynamicLayout
- AFXEXT/CControlBar::CalcFixedLayout
- AFXEXT/CControlBar::CalcInsideRect
- AFXEXT/CControlBar::DoPaint
- AFXEXT/CControlBar::DrawBorders
- AFXEXT/CControlBar::DrawGripper
- AFXEXT/CControlBar::EnableDocking
- AFXEXT/CControlBar::GetBarStyle
- AFXEXT/CControlBar::GetBorders
- AFXEXT/CControlBar::GetCount
- AFXEXT/CControlBar::GetDockingFrame
- AFXEXT/CControlBar::IsFloating
- AFXEXT/CControlBar::OnUpdateCmdUI
- AFXEXT/CControlBar::SetBarStyle
- AFXEXT/CControlBar::SetBorders
- AFXEXT/CControlBar::SetInPlaceOwner
- AFXEXT/CControlBar::m_bAutoDelete
- AFXEXT/CControlBar::m_pInPlaceOwner
helpviewer_keywords:
- CControlBar [MFC], CControlBar
- CControlBar [MFC], CalcDynamicLayout
- CControlBar [MFC], CalcFixedLayout
- CControlBar [MFC], CalcInsideRect
- CControlBar [MFC], DoPaint
- CControlBar [MFC], DrawBorders
- CControlBar [MFC], DrawGripper
- CControlBar [MFC], EnableDocking
- CControlBar [MFC], GetBarStyle
- CControlBar [MFC], GetBorders
- CControlBar [MFC], GetCount
- CControlBar [MFC], GetDockingFrame
- CControlBar [MFC], IsFloating
- CControlBar [MFC], OnUpdateCmdUI
- CControlBar [MFC], SetBarStyle
- CControlBar [MFC], SetBorders
- CControlBar [MFC], SetInPlaceOwner
- CControlBar [MFC], m_bAutoDelete
- CControlBar [MFC], m_pInPlaceOwner
ms.assetid: 4d668c55-9b42-4838-97ac-cf2b3000b82c
ms.openlocfilehash: 41e40b3da7b4a294fe396a9d93f7c6a93593ff95
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62345827"
---
# <a name="ccontrolbar-class"></a>CControlBar Class

컨트롤 막대 클래스에 대 한 기본 클래스 [CStatusBar](../../mfc/reference/cstatusbar-class.md), [CToolBar](../../mfc/reference/ctoolbar-class.md), [CDialogBar](../../mfc/reference/cdialogbar-class.md)하십시오 [CReBar](../../mfc/reference/crebar-class.md), 및 [ COleResizeBar](../../mfc/reference/coleresizebar-class.md)합니다.

## <a name="syntax"></a>구문

```
class CControlBar : public CWnd
```

## <a name="members"></a>멤버

### <a name="protected-constructors"></a>Protected 생성자

|이름|설명|
|----------|-----------------|
|[CControlBar::CControlBar](#ccontrolbar)|`CControlBar` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CControlBar::CalcDynamicLayout](#calcdynamiclayout)|으로 동적 컨트롤 막대의 크기를 반환 하는 [CSize](../../atl-mfc-shared/reference/csize-class.md) 개체입니다.|
|[CControlBar::CalcFixedLayout](#calcfixedlayout)|으로 컨트롤 막대의 크기를 반환 하는 [CSize](../../atl-mfc-shared/reference/csize-class.md) 개체입니다.|
|[CControlBar::CalcInsideRect](#calcinsiderect)|컨트롤 막대 영역;의 현재 크기를 반환합니다. 테두리를 포함합니다.|
|[CControlBar::DoPaint](#dopaint)|컨트롤 막대의 그리퍼 고 테두리를 렌더링합니다.|
|[CControlBar::DrawBorders](#drawborders)|컨트롤 막대의 테두리를 렌더링합니다.|
|[CControlBar::DrawGripper](#drawgripper)|컨트롤 막대의 위치 조정 막대를 렌더링합니다.|
|[CControlBar::EnableDocking](#enabledocking)|도킹 하거나 부동 컨트롤 막대를 허용 합니다.|
|[CControlBar::GetBarStyle](#getbarstyle)|컨트롤 막대 스타일 설정을 검색합니다.|
|[CControlBar::GetBorders](#getborders)|컨트롤 막대의 테두리 값을 검색 합니다.|
|[CControlBar::GetCount](#getcount)|컨트롤 막대에서 비 HWND 요소 수를 반환합니다.|
|[CControlBar::GetDockingFrame](#getdockingframe)|컨트롤 막대 도킹 프레임에 대 한 포인터를 반환 합니다.|
|[CControlBar::IsFloating](#isfloating)|컨트롤 막대에 부동 컨트롤 막대 이면 0이 아닌 값을 반환 합니다.|
|[CControlBar::OnUpdateCmdUI](#onupdatecmdui)|명령 UI 처리기를 호출합니다.|
|[CControlBar::SetBarStyle](#setbarstyle)|컨트롤 막대 스타일 설정을 수정합니다.|
|[CControlBar::SetBorders](#setborders)|컨트롤 막대의 테두리 값을 설정 합니다.|
|[CControlBar::SetInPlaceOwner](#setinplaceowner)|컨트롤 막대의 위치에서 소유자를 변경 합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CControlBar::m_bAutoDelete](#m_bautodelete)|0이 아니면는 `CControlBar` Windows 컨트롤 막대 소멸 될 때 개체가 삭제 됩니다.|
|[CControlBar::m_pInPlaceOwner](#m_pinplaceowner)|컨트롤 막대의 내부 소유자입니다.|

## <a name="remarks"></a>설명

컨트롤 막대에는 프레임 창 오른쪽 또는 왼쪽에 맞춰진 일반적으로 창입니다. 자식 항목 HWND 기반 컨트롤을 생성 하 고 Windows 메시지에 응답 하는 windows, 또는 windows가 아닌 응용 프로그램 코드 또는 프레임 워크 코드에서 관리 되는 비 HWND 기반 항목을 포함할 수 있습니다. 목록 상자 및 편집 컨트롤은 예 HWND 기반 컨트롤이입니다. 상태 표시줄 창 및 비트맵 단추는 예 HWND 기반 컨트롤입니다.

컨트롤 막대 windows는 일반적으로 부모 프레임 창의 자식 창 이며 일반적으로 프레임 창의 MDI 클라이언트 또는 클라이언트 보기는 형제입니다. `CControlBar` 개체 부모 창의 클라이언트 사각형에 대 한 정보를 사용 하 여 자체의 위치입니다. 그런 다음 부모 창의 클라이언트 영역에서 공간 할당 되지 않은 유지에 대 한 부모 창을 알려줍니다.

에 대 한 자세한 `CControlBar`를 참조 하세요.

- [컨트롤 막대](../../mfc/control-bars.md)

- [Technical Note 31: 컨트롤 막대](../../mfc/tn031-control-bars.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CControlBar`

## <a name="requirements"></a>요구 사항

**헤더:** afxext.h

##  <a name="calcdynamiclayout"></a>  CControlBar::CalcDynamicLayout

프레임 워크의 동적 도구 모음 크기를 계산 하려면이 멤버 함수를 호출 합니다.

```
virtual CSize CalcDynamicLayout(
    int nLength,
    DWORD nMode);
```

### <a name="parameters"></a>매개 변수

*nLength*<br/>
컨트롤 막대를 가로 또는 세로에 따라 요청 된 차원의 *dwMode*합니다.

*nMode*<br/>
동적 컨트롤 막대의 너비와 높이 확인 하려면 다음 미리 정의 된 플래그를 사용 됩니다. 비트 OR를 사용 하 여 (&#124;) 플래그를 조합 하는 연산자입니다.

|레이아웃 모드 플래그|의미|
|-----------------------|-------------------|
|LM_STRETCH|컨트롤 막대 프레임의 크기를 위해 늘여 야 하는지 여부를 나타냅니다. 막대는 도킹 모음 (도킹에 대 한 사용할 수 없음) 없는 경우 설정 합니다. 설정 되지 않았습니다 도킹 하거나 부동 막대 때 (도킹에 대 한 사용 가능). 설정 LM_STRETCH 무시 *nLength* LM_HORZ 상태를 기반으로 차원을 반환 합니다. LM_STRETCH 유사 하 게 작동 합니다 *bStretch* 에 사용 되는 매개 변수 [CalcFixedLayout](#calcfixedlayout);를 확장 하 고 방향 간의 관계에 대 한 자세한 내용은 해당 멤버 함수를 참조 하세요.|
|LM_HORZ|막대를 가로 또는 세로 방향 인지를 나타냅니다. 막대를 가로 방향의 이며 방향은 세로 이면 설정 되지 않은 경우 설정 합니다. LM_HORZ 유사 하 게 작동 합니다 *bHorz* 에 사용 되는 매개 변수 [CalcFixedLayout](#calcfixedlayout);를 확장 하 고 방향 간의 관계에 대 한 자세한 내용은 해당 멤버 함수를 참조 하세요.|
|LM_MRUWIDTH|가장 최근에 동적 너비를 사용 합니다. 무시 *nLength* 매개 변수는 저장 된 사용 하 여 가장 최근에 사용 된 너비입니다.|
|LM_HORZDOCK|가로 크기를 도킹 합니다. 무시 *nLength* 매개 변수 최대 너비를 사용 하 여 동적 크기를 반환 합니다.|
|LM_VERTDOCK|세로 크기를 도킹 합니다. 무시 *nLength* 매개 변수 최대 높이 사용 하 여 동적 크기를 반환 합니다.|
|LM_LENGTHY|설정 하는 경우 *nLength* 너비가 아닌 높이 (Y 방향)을 나타냅니다.|
|LM_COMMIT|LM_MRUWIDTH 부동 컨트롤 막대의 현재 너비 다시 설정합니다.|

### <a name="return-value"></a>반환 값

컨트롤 막대, 픽셀에서의 크기를 [CSize](../../atl-mfc-shared/reference/csize-class.md) 개체입니다.

### <a name="remarks"></a>설명

파생 클래스에서 직접 동적 레이아웃을 제공 하려면이 멤버 함수를 재정의 `CControlBar`합니다. 파생 된 MFC 클래스 `CControlBar`와 같은 [CToolbar](../../mfc/reference/ctoolbar-class.md)이 멤버 함수를 재정의 하 고 고유한 구현을 제공 합니다.

##  <a name="calcfixedlayout"></a>  CControlBar::CalcFixedLayout

컨트롤 막대의 가로 크기를 계산 하려면이 멤버 함수를 호출 합니다.

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>매개 변수

*bStretch*<br/>
막대 프레임의 크기를 위해 늘여 야 하는지 여부를 나타냅니다. 합니다 *bStretch* 매개 변수는 0이 아닌 막대는 도킹 모음 (도킹에 대 한 사용할 수 없음) 아니며 있을 경우 0이 도킹 또는 부동 (도킹에 대 한 사용 가능) 하는 경우.

*bHorz*<br/>
막대를 가로 또는 세로 방향 인지를 나타냅니다. 합니다 *bHorz* 0이 아닌 경우 막대를 가로 방향 및 세로 방향인 경우 0입니다.

### <a name="return-value"></a>반환 값

컨트롤 막대, 픽셀에서의 크기를 `CSize` 개체입니다.

### <a name="remarks"></a>설명

도구 모음 등의 컨트롤 막대를 가로 방향으로 확장할 수 또는 세로 방향으로 단추를 수용 하기 위해 컨트롤 막대에 포함 합니다.

하는 경우 *bStretch* 가 TRUE 인 확장에서 제공 하는 방향에 따라 차원 *bHorz*합니다. 즉, 하는 경우 *bHorz* 은 FALSE 컨트롤 막대에 세로로 확장 됩니다. 하는 경우 *bStretch* 은 FALSE 늘이기 발생 합니다. 다음 표에서 가능한 순열 및 결과 컨트롤 막대 스타일의 *bStretch* 하 고 *bHorz*합니다.

|bStretch|bHorz|늘이기|방향|도킹/Not 도킹|
|--------------|-----------|----------------|-----------------|--------------------------|
|TRUE|TRUE|가로 늘이기|가로로 조정|도킹 하지|
|TRUE|FALSE|세로 늘이기|세로 방향|도킹 하지|
|FALSE|TRUE|사용 가능한 확장 하지 않는|가로로 조정|도킹|
|FALSE|FALSE|사용 가능한 확장 하지 않는|세로 방향|도킹|

##  <a name="calcinsiderect"></a>  CControlBar::CalcInsideRect

프레임 워크는 컨트롤 막대의 클라이언트 영역을 계산 하려면이 함수를 호출 합니다.

```
virtual void CalcInsideRect(
    CRect& rect,
    BOOL bHorz) const;
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
컨트롤 막대;의 현재 크기를 포함합니다. 테두리를 포함합니다.

*bHorz*<br/>
막대를 가로 또는 세로 방향 인지를 나타냅니다. 합니다 *bHorz* 0이 아닌 경우 막대를 가로 방향 및 세로 방향인 경우 0입니다.

### <a name="remarks"></a>설명

컨트롤 막대가 칠 해지기 전에이 함수가 호출 됩니다.

테두리 및 컨트롤 막대의 그리퍼 막대의 렌더링을 사용자 지정 하려면이 함수를 재정의 합니다.

##  <a name="ccontrolbar"></a>  CControlBar::CControlBar

`CControlBar` 개체를 생성합니다.

```
CControlBar();
```

##  <a name="dopaint"></a>  CControlBar::DoPaint

테두리 및 컨트롤 막대의 그리퍼 막대를 렌더링 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual void DoPaint(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
테두리 및 컨트롤 막대의 그리퍼 렌더링에 사용 되는 장치 컨텍스트를 가리킵니다.

### <a name="remarks"></a>설명

컨트롤 막대 그리기 동작을 사용자 지정 하려면이 함수를 재정의 합니다.

다른 사용자 지정 메서드를 재정의 하는 것은 `DrawBorders` 및 `DrawGripper` 함수 및 테두리 및 위치 조정 막대에 대 한 사용자 지정 그리기 코드를 추가 합니다. 기본적으로 이러한 메서드를 호출 하므로 `DoPaint` 메서드를 재정의 하는 `DoPaint` 필요 하지 않습니다.

##  <a name="drawborders"></a>  CControlBar::DrawBorders

컨트롤 막대의 테두리를 렌더링 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual void DrawBorders(
    CDC* pDC,
    CRect& rect);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
컨트롤 막대의 테두리를 렌더링 하는 데 사용할 장치 컨텍스트를 가리킵니다.

*rect*<br/>
`CRect` 컨트롤 막대의 크기를 포함 하는 개체입니다.

### <a name="remarks"></a>설명

컨트롤 막대 테두리의 모양을 사용자 지정 하려면이 함수를 재정의 합니다.

##  <a name="drawgripper"></a>  CControlBar::DrawGripper

컨트롤 막대의 그리퍼 렌더링 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual void DrawGripper(
    CDC* pDC,
    const CRect& rect);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
컨트롤 막대 위치 조정 막대를 렌더링 하는 데 사용할 장치 컨텍스트를 가리킵니다.

*rect*<br/>
`CRect` 컨트롤 막대 위치 조정 막대의 크기를 포함 하는 개체입니다.

### <a name="remarks"></a>설명

컨트롤 막대 위치 조정 막대의 모양을 사용자 지정 하려면이 함수를 재정의 합니다.

##  <a name="enabledocking"></a>  CControlBar::EnableDocking

도킹 컨트롤 막대를 사용 하도록 설정 하려면이 함수를 호출 합니다.

```
void EnableDocking(DWORD dwDockStyle);
```

### <a name="parameters"></a>매개 변수

*dwDockStyle*<br/>
지원 되는 경우 컨트롤 막대에 도킹을 지원 하는지 여부와는 컨트롤 막대에 도킹할 수, 해당 부모 창 측면을 지정 합니다. 다음 중 하나 이상의 수 있습니다.

- CBRS_ALIGN_TOP 클라이언트 영역의 위쪽에 도킹 수 있습니다.

- CBRS_ALIGN_BOTTOM 클라이언트 영역의 맨 아래에서 도킹 수 있습니다.

- CBRS_ALIGN_LEFT 클라이언트 영역의 왼쪽에 도킹할 수 있습니다.

- CBRS_ALIGN_RIGHT 클라이언트 영역 오른쪽에 도킹할 수 있습니다.

- CBRS_ALIGN_ANY 클라이언트 영역의 한쪽에 도킹 수 있습니다.

- CBRS_FLOAT_MULTI 여러 컨트롤 막대를 단일 미니 프레임 창에서 이동할 수 있습니다.

0 인 경우 (즉, 나타내는 플래그가 없습니다) 컨트롤 막대에 도킹 되지 됩니다.

### <a name="remarks"></a>설명

지정 된 면 대상 프레임 창에서 도킹 가능한 면 중 하 나와 일치 해야 합니다 또는 컨트롤 막대 프레임 창으로 도킹 될 수 없습니다.

##  <a name="getbarstyle"></a>  CControlBar::GetBarStyle

결정이 함수를 호출 **CBRS_** (컨트롤 막대 스타일) 설정을 컨트롤 막대에 대 한 현재 설정 되어 있습니다.

```
DWORD GetBarStyle();
```

### <a name="return-value"></a>반환 값

현재 **CBRS_** 컨트롤 막대에 대 한 (컨트롤 막대 스타일) 설정 합니다. 참조 [CControlBar::SetBarStyle](#setbarstyle) 사용 가능한 스타일의 목록은 합니다.

### <a name="remarks"></a>설명

처리 하지 않습니다 **WS_** (창 스타일) 스타일입니다.

##  <a name="getborders"></a>  CControlBar::GetBorders

컨트롤 막대 테두리의 현재 값을 반환합니다.

```
CRect GetBorders() const;
```

### <a name="return-value"></a>반환 값

`CRect` 컨트롤 막대 개체의 각 측면의 현재 너비 (픽셀)를 포함 하는 개체입니다. 예를 들어, 값을 *왼쪽* 멤버의 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체, 왼쪽 테두리의 너비입니다.

##  <a name="getcount"></a>  CControlBar::GetCount

에 비 HWND 항목의 수를 반환 합니다 `CControlBar` 개체입니다.

```
int GetCount() const;
```

### <a name="return-value"></a>반환 값

HWND가 아닌 항목에 대 한 수의 `CControlBar` 개체입니다. 이 함수에 대 한 0을 반환 합니다.는 [CDialogBar](../../mfc/reference/cdialogbar-class.md) 개체입니다.

### <a name="remarks"></a>설명

파생된 된 개체에 따라 달라 집니다 항목의 형식: 창을 [CStatusBar](../../mfc/reference/cstatusbar-class.md) 개체 및 단추에 대 한 구분 기호 [CToolBar](../../mfc/reference/ctoolbar-class.md) 개체입니다.

##  <a name="getdockingframe"></a>  CControlBar::GetDockingFrame

컨트롤 막대에 도킹 되는 현재 프레임 창에 대 한 포인터를 가져오려면이 함수를 호출 합니다.

```
CFrameWnd* GetDockingFrame() const;
```

### <a name="return-value"></a>반환 값

성공할 경우 프레임 창에 대 한 포인터 그렇지 않으면 NULL입니다.

경우 (즉, 하는 경우 컨트롤 막대에는 부동) 컨트롤 막대 프레임 창에 잠기지 않은,이 함수는 해당 부모에 대 한 포인터를 반환 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)합니다.

### <a name="remarks"></a>설명

도킹 가능한 컨트롤 막대에 대 한 자세한 내용은 참조 하세요. [CControlBar::EnableDocking](#enabledocking) 하 고 [CFrameWnd::DockControlBar](../../mfc/reference/cframewnd-class.md#dockcontrolbar)합니다.

##  <a name="isfloating"></a>  CControlBar::IsFloating

부동 또는 도킹 컨트롤 막대 인지 여부를 확인 하려면이 멤버 함수를 호출 합니다.

```
BOOL IsFloating() const;
```

### <a name="return-value"></a>반환 값

컨트롤 막대; 부동 창인 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

부동으로 도킹 컨트롤 막대에서의 상태를 변경 하려면 호출 [CFrameWnd::FloatControlBar](../../mfc/reference/cframewnd-class.md#floatcontrolbar)합니다.

##  <a name="m_bautodelete"></a>  CControlBar::m_bAutoDelete

0이 아니면는 `CControlBar` Windows 컨트롤 막대 소멸 될 때 개체가 삭제 됩니다.

```
BOOL m_bAutoDelete;
```

### <a name="remarks"></a>설명

*m_bAutoDelete* BOOL 형식의 공용 변수입니다.

컨트롤 막대 개체는 일반적으로 프레임 창 개체에 포함 됩니다. 이 예에서 *m_bAutoDelete* 0 이므로 프레임 창을 소멸 될 때 포함 된 컨트롤 막대 개체를 삭제 합니다.

0이 아닌 값으로 할당 하는 경우이 변수를 설정를 `CControlBar` 힙에에 개체를 호출 하지 않으려는 **삭제**합니다.

##  <a name="m_pinplaceowner"></a>  CControlBar::m_pInPlaceOwner

컨트롤 막대의 내부 소유자입니다.

```
CWnd* m_pInPlaceOwner;
```

##  <a name="onupdatecmdui"></a>  CControlBar::OnUpdateCmdUI

이 멤버 함수는 도구 모음 또는 상태 표시줄의 상태를 업데이트 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler) = 0;
```

### <a name="parameters"></a>매개 변수

*pTarget*<br/>
응용 프로그램의 주 프레임 창을 가리킵니다. 이 포인터 업데이트 메시지 라우팅에 사용 됩니다.

*bDisableIfNoHndler*<br/>
업데이트 처리기가 컨트롤을 사용 하지 않도록 설정으로 자동으로 표시할지 여부를 나타내는 플래그입니다.

### <a name="remarks"></a>설명

개별 단추 또는 창을 업데이트 하려면 메시지 맵에 ON_UPDATE_COMMAND_UI 매크로 사용 하 여 업데이트 처리기를 적절 하 게 설정 합니다. 참조 [ON_UPDATE_COMMAND_UI](message-map-macros-mfc.md#on_update_command_ui) 이 매크로 사용 하는 방법에 대 한 자세한 내용은 합니다.

`OnUpdateCmdUI` 응용 프로그램이 유휴 상태일 때 프레임 워크에서 호출 됩니다. 업데이트할 수 있는 프레임 창을 해제 해야 합니다 자식 창에 적어도 직접 표시 프레임 창. `OnUpdateCmdUI` 고급 재정의할 수 있습니다.

##  <a name="setbarstyle"></a>  CControlBar::SetBarStyle

원하는 설정 하려면이 함수를 호출 **CBRS_** 컨트롤 막대에 대 한 스타일입니다.

```
void SetBarStyle(DWORD dwStyle);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
컨트롤 막대에 대 한 원하는 스타일입니다. 다음 중 하나 이상의 수 있습니다.

- CBRS_ALIGN_TOP은 프레임 창의 클라이언트 영역의 위쪽에 도킹 컨트롤 막대를 허용 합니다.

- CBRS_ALIGN_BOTTOM은 프레임 창의 클라이언트 영역의 아래쪽에 도킹 컨트롤 막대를 허용 합니다.

- CBRS_ALIGN_LEFT은 프레임 창의 클라이언트 영역의 왼쪽에 도킹 컨트롤 막대를 허용 합니다.

- CBRS_ALIGN_RIGHT은 프레임 창의 클라이언트 영역의 왼쪽에서 오른쪽으로 도킹 컨트롤 막대를 허용 합니다.

- CBRS_ALIGN_ANY는 컨트롤 막대를 프레임 창의 클라이언트 영역에서 원하는 쪽에 도킹 될 수 있습니다.

- CBRS_BORDER_TOP 테두리 막대 때 볼 수는 컨트롤의 위쪽 가장자리에 그려지는를 하면 됩니다.

- CBRS_BORDER_BOTTOM 때 볼 수는 표시줄 컨트롤의 아래쪽 가장자리에 그려질 테두리를 하면 됩니다.

- CBRS_BORDER_LEFT 때 볼 수는 표시줄 컨트롤의 왼쪽된 가장자리에 그려질 테두리를 하면 됩니다.

- CBRS_BORDER_RIGHT 때 볼 수는 표시줄 컨트롤의 오른쪽 가장자리에 그려질 테두리를 하면 됩니다.

- CBRS_FLOAT_MULTI 여러 컨트롤 막대를 단일 미니 프레임 창에서 이동할 수 있습니다.

- 컨트롤 막대에 대해 표시할 도구 설명을 CBRS_TOOLTIPS 발생 합니다.

- CBRS_FLYBY 하면 도구 설명으로 동시에 업데이트할 텍스트를 메시지입니다.

- CBRS_GRIPPER 하면 위치 조정 막대를에서 밴드에 사용한 것과 비슷한를 `CReBar` 개체에 대해 그릴 `CControlBar`-클래스를 파생 합니다.

### <a name="remarks"></a>설명

영향을 주지 않습니다 합니다 **WS_** (창 스타일) 설정 합니다.

##  <a name="setborders"></a>  CControlBar::SetBorders

컨트롤 막대의 테두리의 크기를 설정 하려면이 함수를 호출 합니다.

```
void SetBorders(
    int cxLeft = 0,
    int cyTop = 0,
    int cxRight = 0,
    int cyBottom = 0);

void SetBorders(LPCRECT lpRect);
```

### <a name="parameters"></a>매개 변수

*cxLeft*<br/>
컨트롤 막대의 왼쪽된 테두리의 너비 (픽셀)입니다.

*cyTop*<br/>
컨트롤 막대의 위쪽 테두리의 높이 (픽셀)입니다.

*cxRight*<br/>
컨트롤 막대의 오른쪽 테두리의 너비 (픽셀)입니다.

*cyBottom*<br/>
컨트롤 막대의 아래쪽 테두리의 높이 (픽셀)입니다.

*lpRect*<br/>
에 대 한 포인터를 [CRect](../../atl-mfc-shared/reference/crect-class.md) 컨트롤 막대 개체의 각 테두리의 현재 너비 (픽셀)를 포함 하는 개체입니다.

### <a name="example"></a>예제

다음 코드 예제에서는 2 픽셀로 5 픽셀은 컨트롤 막대의 테두리 위쪽 및 아래쪽 및 왼쪽 및 오른쪽 테두리를 설정합니다.

[!code-cpp[NVC_MFCControlLadenDialog#61](../../mfc/codesnippet/cpp/ccontrolbar-class_1.cpp)]

##  <a name="setinplaceowner"></a>  CControlBar::SetInPlaceOwner

컨트롤 막대의 위치에서 소유자를 변경 합니다.

```
void SetInPlaceOwner(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
`CWnd` 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고자료

[MFC 샘플 CTRLBARS](../../overview/visual-cpp-samples.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CToolBar 클래스](../../mfc/reference/ctoolbar-class.md)<br/>
[CDialogBar 클래스](../../mfc/reference/cdialogbar-class.md)<br/>
[CStatusBar 클래스](../../mfc/reference/cstatusbar-class.md)<br/>
[CReBar 클래스](../../mfc/reference/crebar-class.md)
