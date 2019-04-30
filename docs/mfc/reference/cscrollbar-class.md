---
title: CScrollBar 클래스
ms.date: 11/04/2016
f1_keywords:
- CScrollBar
- AFXWIN/CScrollBar
- AFXWIN/CScrollBar::CScrollBar
- AFXWIN/CScrollBar::Create
- AFXWIN/CScrollBar::EnableScrollBar
- AFXWIN/CScrollBar::GetScrollBarInfo
- AFXWIN/CScrollBar::GetScrollInfo
- AFXWIN/CScrollBar::GetScrollLimit
- AFXWIN/CScrollBar::GetScrollPos
- AFXWIN/CScrollBar::GetScrollRange
- AFXWIN/CScrollBar::SetScrollInfo
- AFXWIN/CScrollBar::SetScrollPos
- AFXWIN/CScrollBar::SetScrollRange
- AFXWIN/CScrollBar::ShowScrollBar
helpviewer_keywords:
- CScrollBar [MFC], CScrollBar
- CScrollBar [MFC], Create
- CScrollBar [MFC], EnableScrollBar
- CScrollBar [MFC], GetScrollBarInfo
- CScrollBar [MFC], GetScrollInfo
- CScrollBar [MFC], GetScrollLimit
- CScrollBar [MFC], GetScrollPos
- CScrollBar [MFC], GetScrollRange
- CScrollBar [MFC], SetScrollInfo
- CScrollBar [MFC], SetScrollPos
- CScrollBar [MFC], SetScrollRange
- CScrollBar [MFC], ShowScrollBar
ms.assetid: f3735ca5-73ea-46dc-918b-4d824c9fe47f
ms.openlocfilehash: d677d72b7e758fcdaa7df0e2918e9bbec3e18ee9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62324235"
---
# <a name="cscrollbar-class"></a>CScrollBar 클래스

Windows 스크롤 막대 컨트롤의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CScrollBar : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CScrollBar::CScrollBar](#cscrollbar)|`CScrollBar` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CScrollBar::Create](#create)|Windows 스크롤 막대를 만들고 연결 하는 `CScrollBar` 개체입니다.|
|[CScrollBar::EnableScrollBar](#enablescrollbar)|스크롤 막대의 화살표 하나 또는 둘 다를 사용하거나 사용하지 않도록 설정합니다.|
|[CScrollBar::GetScrollBarInfo](#getscrollbarinfo)|스크롤 막대를 사용 하는 방법에 대 한 정보를 검색 한 `SCROLLBARINFO` 구조입니다.|
|[CScrollBar::GetScrollInfo](#getscrollinfo)|스크롤 막대에 대 한 정보를 검색합니다.|
|[CScrollBar::GetScrollLimit](#getscrolllimit)|스크롤 막대의 한계를 검색합니다.|
|[CScrollBar::GetScrollPos](#getscrollpos)|스크롤 상자의 현재 위치를 검색합니다.|
|[CScrollBar::GetScrollRange](#getscrollrange)|지정 된 스크롤 막대에 대 한 현재 최소 및 최대 스크롤 막대 위치를 검색합니다.|
|[CScrollBar::SetScrollInfo](#setscrollinfo)|스크롤 막대에 대한 정보를 설정합니다.|
|[CScrollBar::SetScrollPos](#setscrollpos)|스크롤 상자의 현재 위치를 설정합니다.|
|[CScrollBar::SetScrollRange](#setscrollrange)|지정된 스크롤 막대에 대한 최소 및 최대 위치 값을 설정합니다.|
|[CScrollBar::ShowScrollBar](#showscrollbar)|표시 하거나 스크롤 막대를 숨깁니다.|

## <a name="remarks"></a>설명

두 단계에서 스크롤 막대 컨트롤을 만듭니다. 먼저 생성자를 호출 `CScrollBar` 생성 하는 `CScrollBar` 개체를 만든 다음 호출 합니다 [만들기](#create) Windows 스크롤 막대 컨트롤을 만들고 연결 하는 멤버 함수는 `CScrollBar` 개체입니다.

만드는 경우는 `CScrollBar` (대화 상자 리소스의 경우)를 통해 대화 상자 내에서 개체를 `CScrollBar` 사용자 대화 상자를 닫을 때 자동으로 제거 됩니다.

만드는 경우는 `CScrollBar` 창 내에서 개체 삭제 해야 합니다.

만드는 경우는 `CScrollBar` 개체 스택에 자동으로 제거 됩니다. 만드는 경우는 `CScrollBar` 를 사용 하 여 힙에 있는 개체에는 **새** 를 호출 해야 함수를 **삭제** 개체에서 사용자가 Windows 스크롤 막대를 종료 하는 경우 삭제를 합니다.

메모리를 할당 하는 경우는 `CScrollBar` 개체를 재정의 합니다 `CScrollBar` 소멸자는 할당을 삭제 합니다.

사용에 대 한 관련된 정보에 대 한 `CScrollBar`를 참조 하세요 [컨트롤](../../mfc/controls-mfc.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CScrollBar`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

##  <a name="create"></a>  CScrollBar::Create

Windows 스크롤 막대를 만들고 연결 하는 `CScrollBar` 개체입니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
지정 된 스크롤 막대 스타일. 어떤 조합도 적용할 [스크롤 막대 스타일](../../mfc/reference/styles-used-by-mfc.md#scroll-bar-styles) 스크롤 막대를 합니다.

*rect*<br/>
스크롤 막대의 크기와 위치를 지정합니다. 일 수를 `RECT` 구조 또는 `CRect` 개체입니다.

*pParentWnd*<br/>
스크롤을 지정 합니다 모음의 부모 창에 일반적으로 `CDialog` 개체입니다. NULL이 아니어야 합니다.

*nID*<br/>
스크롤 막대의 컨트롤 id입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

생성 된 `CScrollBar` 두 단계에서 개체입니다. 먼저 생성 하는 생성자를 호출 합니다 `CScrollBar` 개체; 호출 `Create`, 생성 되 고 관련된 Windows 스크롤 막대를 초기화 하 고에 연결 합니다 `CScrollBar` 개체.

다음 적용 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles) 스크롤 막대에:

- WS_CHILD 항상

- WS_VISIBLE 일반적으로

- WS_DISABLED 거의

- 그룹 컨트롤에 WS_GROUP

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CScrollBar#1](../../mfc/reference/codesnippet/cpp/cscrollbar-class_1.cpp)]

##  <a name="cscrollbar"></a>  CScrollBar::CScrollBar

`CScrollBar` 개체를 생성합니다.

```
CScrollBar();
```

### <a name="remarks"></a>설명

개체를 생성 한 후 호출 하 여 `Create` 멤버 함수를 만들고 Windows 스크롤 막대를 초기화 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CScrollBar#2](../../mfc/reference/codesnippet/cpp/cscrollbar-class_2.h)]

##  <a name="enablescrollbar"></a>  CScrollBar::EnableScrollBar

스크롤 막대의 화살표 하나 또는 둘 다를 사용하거나 사용하지 않도록 설정합니다.

```
BOOL EnableScrollBar(UINT nArrowFlags = ESB_ENABLE_BOTH);
```

### <a name="parameters"></a>매개 변수

*nArrowFlags*<br/>
화살표는 설정 또는 해제와 스크롤 화살표를 설정 또는 해제 여부를 지정 합니다. 이 매개 변수는 다음 값 중 하나일 수 있습니다.

- ESB_ENABLE_BOTH는 스크롤 막대의 화살표를 둘 다를 수 있습니다.

- ESB_DISABLE_LTUP 가로 스크롤 막대의 왼쪽된 화살표 또는 세로 스크롤 막대의 위쪽 화살표 사용 하지 않도록 설정 합니다.

- ESB_DISABLE_RTDN 가로 스크롤 막대의 오른쪽 화살표 또는 아래쪽 화살표의 세로 스크롤 막대를 사용 하지 않도록 설정 합니다.

- ESB_DISABLE_BOTH는 스크롤 막대의 화살표 모두 사용 하지 않도록 설정 합니다.

### <a name="return-value"></a>반환 값

화살표를; 지정 된 대로 사용 하는 경우 0이 아닌 값 화살표는 이미 요청 된 상태 또는 오류가 발생 했음을 나타내는 그렇지 않으면 0입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CScrollBar::SetScrollRange](#setscrollrange)합니다.

##  <a name="getscrollbarinfo"></a>  CScrollBar::GetScrollBarInfo

`SCROLLBARINFO` 구조체에서 스크롤 막대에 대해 유지 관리하는 정보를 검색합니다.

```
BOOL GetScrollBarInfo(PSCROLLBARINFO pScrollInfo) const;
```

### <a name="parameters"></a>매개 변수

*pScrollInfo*<br/>
에 대 한 포인터를 [SCROLLBARINFO](/windows/desktop/api/winuser/ns-winuser-tagscrollbarinfo) 구조입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

이 멤버 함수는의 기능을 에뮬레이션 합니다 [SBM_SCROLLBARINFO](/windows/desktop/Controls/sbm-getscrollbarinfo) Windows SDK에 설명 된 대로 메시지입니다.

##  <a name="getscrollinfo"></a>  CScrollBar::GetScrollInfo

`SCROLLINFO` 구조체에서 스크롤 막대에 대해 유지 관리하는 정보를 검색합니다.

```
BOOL GetScrollInfo(
    LPSCROLLINFO lpScrollInfo,
    UINT nMask = SIF_ALL);
```

### <a name="parameters"></a>매개 변수

*lpScrollInfo*<br/>
에 대 한 포인터를 [SCROLLINFO](/windows/desktop/api/winuser/ns-winuser-tagscrollinfo) 구조입니다. 이 구조에 대 한 자세한 내용은 Windows SDK를 참조 하세요.

*nMask*<br/>
검색할 스크롤 막대 매개 변수를 지정 합니다. SIF_ALL, 일반적인 사용량 SIF_PAGE, SIF_POS, SIF_TRACKPOS, 및 SIF_RANGE 조합을 지정합니다. 참조 `SCROLLINFO` nMask 값에 대 한 자세한 내용은 합니다.

### <a name="return-value"></a>반환 값

메시지가 검색 된 값을 반환은 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

`GetScrollInfo` 32 비트 스크롤 위치를 사용 하도록 응용 프로그램을 사용 하도록 설정 합니다.

합니다 [SCROLLINFO](/windows/desktop/api/winuser/ns-winuser-tagscrollinfo) 구조에 스크롤 막대를 최소 및 최대 스크롤 위치, 페이지 크기 및 스크롤 상자 (엄지 단추)의 위치를 포함 하는 방법에 대 한 정보가 들어 있습니다. 참조 된 `SCROLLINFO` 구조 기본값을 변경 하는 방법에 대 한 자세한 내용은 Windows SDK의 구조 항목입니다.

MFC Windows 메시지 처리기 스크롤 막대 위치를 나타내는 [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) 하 고 [CWnd::OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll)만 16 비트 위치 데이터를 제공 합니다. `GetScrollInfo` 및 `SetScrollInfo` 스크롤 막대의 위치 데이터의 32 비트를 제공 합니다. 응용 프로그램을 호출할 수 있습니다 따라서 `GetScrollInfo` 중 하나를 처리 하는 동안 `CWnd::OnHScroll` 또는 `CWnd::OnVScroll` 32 비트 스크롤 막대 위치 데이터를 가져오려고 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll)합니다.

##  <a name="getscrolllimit"></a>  CScrollBar::GetScrollLimit

최대 스크롤 스크롤 막대의 위치를 검색 합니다.

```
int GetScrollLimit();
```

### <a name="return-value"></a>반환 값

성공할 경우 스크롤 막대의 최대 위치 지정 그렇지 않으면 0입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll)합니다.

##  <a name="getscrollpos"></a>  CScrollBar::GetScrollPos

스크롤 상자의 현재 위치를 검색합니다.

```
int GetScrollPos() const;
```

### <a name="return-value"></a>반환 값

성공할 경우 스크롤 상자의 현재 위치를 지정 합니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

현재 위치가 현재 스크롤 범위에 의존 하는 상대 값을 보여 줍니다. 예를 들어, 스크롤 범위는 100-200 개 사이인 경우 스크롤 상자 막대는 현재 위치는 150입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll)합니다.

##  <a name="getscrollrange"></a>  CScrollBar::GetScrollRange

지정 된 스크롤 막대에 대 한 현재 최소 및 최대 스크롤 막대 위치를 지정 된 위치에 복사 *lpMinPos* 하 고 *lpMaxPos*합니다.

```
void GetScrollRange(
    LPINT lpMinPos,
    LPINT lpMaxPos) const;
```

### <a name="parameters"></a>매개 변수

*lpMinPos*<br/>
최소 위치를 수신 하는 정수 변수를 가리킵니다.

*lpMaxPos*<br/>
최대 위치를 수신 하는 정수 변수를 가리킵니다.

### <a name="remarks"></a>설명

스크롤 막대 컨트롤에 대 한 기본 범위는 빈 (두 값은 0 임).

### <a name="example"></a>예제

  예를 참조 하세요 [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll)합니다.

##  <a name="setscrollinfo"></a>  CScrollBar::SetScrollInfo

정보를 설정 합니다 `SCROLLINFO` 스크롤 막대에 대 한 구조를 유지 관리 합니다.

```
BOOL SetScrollInfo(
    LPSCROLLINFO lpScrollInfo,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>매개 변수

*lpScrollInfo*<br/>
에 대 한 포인터를 [SCROLLINFO](/windows/desktop/api/winuser/ns-winuser-tagscrollinfo) 구조입니다.

*bRedraw*<br/>
새 정보를 반영 하도록 스크롤 막대를 그려야 하는지 여부를 지정 합니다. 하는 경우 *bRedraw* 가 TRUE 인 스크롤 막대를 다시 그려집니다. FALSE 인 경우 다시 그려지지 않습니다. 스크롤 막대는 기본적으로 다시 그려집니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE이 반환이 됩니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

에 필요한 값을 제공 해야 합니다 `SCROLLINFO` 플래그 값을 포함 하 여 매개 변수를 구성 합니다.

`SCROLLINFO` 구조에 스크롤 막대를 최소 및 최대 스크롤 위치, 페이지 크기 및 스크롤 상자 (엄지 단추)의 위치를 포함 하는 방법에 대 한 정보가 들어 있습니다. 참조 된 [SCROLLINFO](/windows/desktop/api/winuser/ns-winuser-tagscrollinfo) 구조 기본값을 변경 하는 방법에 대 한 자세한 내용은 Windows SDK의 구조 항목입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CScrollBar#3](../../mfc/reference/codesnippet/cpp/cscrollbar-class_3.cpp)]

##  <a name="setscrollpos"></a>  CScrollBar::SetScrollPos

스크롤 상자의 현재 위치에 지정 된 설정 *nPos* 및 지정 하는 경우 새 위치를 반영 하도록 스크롤 막대를 다시 그립니다.

```
int SetScrollPos(
    int nPos,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>매개 변수

*nPos*<br/>
스크롤 상자에 대 한 새 위치를 지정합니다. 스크롤 범위 내 여야 합니다.

*bRedraw*<br/>
새 위치를 반영 하도록 스크롤 막대를 그려야 하는지 여부를 지정 합니다. 하는 경우 *bRedraw* 가 TRUE 인 스크롤 막대를 다시 그려집니다. FALSE 인 경우 다시 그려지지 않습니다. 스크롤 막대는 기본적으로 다시 그려집니다.

### <a name="return-value"></a>반환 값

성공할 경우 스크롤 상자의 이전 위치를 지정 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

설정할 *bRedraw* FALSE로 때마다 스크롤 막대에 그릴 짧은 간격 내에서 두 번 다시 그릴 스크롤 막대 것을 방지 하려면 다른 함수를 이후에 호출 하 여 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CScrollBar::SetScrollRange](#setscrollrange)합니다.

##  <a name="setscrollrange"></a>  CScrollBar::SetScrollRange

지정된 스크롤 막대에 대한 최소 및 최대 위치 값을 설정합니다.

```
void SetScrollRange(
    int nMinPos,
    int nMaxPos,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>매개 변수

*nMinPos*<br/>
최소 스크롤 위치를 지정 합니다.

*nMaxPos*<br/>
최대 스크롤 위치를 지정 합니다.

*bRedraw*<br/>
변경 내용을 반영 하도록 스크롤 막대를 그려야 하는지 여부를 지정 합니다. 하는 경우 *bRedraw* 가 TRUE 인 스크롤 막대를 다시 그릴; FALSE 이면이 그려집니다. 기본적으로 두는 것이 그려집니다.

### <a name="remarks"></a>설명

설정할 *nMinPos* 하 고 *nMaxPos* 표준 스크롤 막대를 숨기려면 0입니다.

스크롤 막대 알림 메시지를 처리 하는 동안 스크롤 막대를 숨기려면이 함수를 호출 하지 마세요.

호출 하는 경우 `SetScrollRange` 에 대 한 호출 바로 뒤에 오는 `SetScrollPos` 멤버 함수를 설정 *bRedraw* 에서 `SetScrollPos` 을 두 번 다시 그려지는에서 스크롤 막대를 제한 합니다.

지정 된 값의 차이 *nMinPos* 하 고 *nMaxPos* 32,767 보다 크지 않아야 합니다. 스크롤 막대 컨트롤에 대 한 기본 범위는 빈 (둘 다 *nMinPos* 하 고 *nMaxPos* 0).

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CScrollBar#4](../../mfc/reference/codesnippet/cpp/cscrollbar-class_4.cpp)]

##  <a name="showscrollbar"></a>  CScrollBar::ShowScrollBar

표시 하거나 스크롤 막대를 숨깁니다.

```
void ShowScrollBar(BOOL bShow = TRUE);
```

### <a name="parameters"></a>매개 변수

*bShow*<br/>
스크롤 막대 표시 되는지 또는 숨겨지는지 여부를 지정 합니다. 이 매개 변수가 TRUE 이면 스크롤 막대가 표시 됩니다. 그렇지 않으면이 숨겨집니다.

### <a name="remarks"></a>설명

응용 프로그램에서 스크롤 막대 알림 메시지를 처리 하는 동안 스크롤 막대를 숨기려면이 함수를 호출 하지 않습니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CScrollBar::Create](#create)합니다.

## <a name="see-also"></a>참고자료

[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[CButton 클래스](../../mfc/reference/cbutton-class.md)<br/>
[CComboBox 클래스](../../mfc/reference/ccombobox-class.md)<br/>
[CEdit Class](../../mfc/reference/cedit-class.md)<br/>
[CListBox 클래스](../../mfc/reference/clistbox-class.md)<br/>
[CStatic 클래스](../../mfc/reference/cstatic-class.md)<br/>
[CDialog 클래스](../../mfc/reference/cdialog-class.md)
