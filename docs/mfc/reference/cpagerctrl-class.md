---
title: CPagerCtrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CPagerCtrl
- AFXCMN/CPagerCtrl
- AFXCMN/CPagerCtrl::CPagerCtrl
- AFXCMN/CPagerCtrl::Create
- AFXCMN/CPagerCtrl::CreateEx
- AFXCMN/CPagerCtrl::ForwardMouse
- AFXCMN/CPagerCtrl::GetBkColor
- AFXCMN/CPagerCtrl::GetBorder
- AFXCMN/CPagerCtrl::GetButtonSize
- AFXCMN/CPagerCtrl::GetButtonState
- AFXCMN/CPagerCtrl::GetDropTarget
- AFXCMN/CPagerCtrl::GetScrollPos
- AFXCMN/CPagerCtrl::IsButtonDepressed
- AFXCMN/CPagerCtrl::IsButtonGrayed
- AFXCMN/CPagerCtrl::IsButtonHot
- AFXCMN/CPagerCtrl::IsButtonInvisible
- AFXCMN/CPagerCtrl::IsButtonNormal
- AFXCMN/CPagerCtrl::RecalcSize
- AFXCMN/CPagerCtrl::SetBkColor
- AFXCMN/CPagerCtrl::SetBorder
- AFXCMN/CPagerCtrl::SetButtonSize
- AFXCMN/CPagerCtrl::SetChild
- AFXCMN/CPagerCtrl::SetScrollPos
helpviewer_keywords:
- CPagerCtrl [MFC], CPagerCtrl
- CPagerCtrl [MFC], Create
- CPagerCtrl [MFC], CreateEx
- CPagerCtrl [MFC], ForwardMouse
- CPagerCtrl [MFC], GetBkColor
- CPagerCtrl [MFC], GetBorder
- CPagerCtrl [MFC], GetButtonSize
- CPagerCtrl [MFC], GetButtonState
- CPagerCtrl [MFC], GetDropTarget
- CPagerCtrl [MFC], GetScrollPos
- CPagerCtrl [MFC], IsButtonDepressed
- CPagerCtrl [MFC], IsButtonGrayed
- CPagerCtrl [MFC], IsButtonHot
- CPagerCtrl [MFC], IsButtonInvisible
- CPagerCtrl [MFC], IsButtonNormal
- CPagerCtrl [MFC], RecalcSize
- CPagerCtrl [MFC], SetBkColor
- CPagerCtrl [MFC], SetBorder
- CPagerCtrl [MFC], SetButtonSize
- CPagerCtrl [MFC], SetChild
- CPagerCtrl [MFC], SetScrollPos
ms.assetid: 65ac58dd-4f5e-4b7e-b15c-e0d435a7e884
ms.openlocfilehash: 648bc17f0f130b831aa619b90ed13ba6be35b4d4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62373247"
---
# <a name="cpagerctrl-class"></a>CPagerCtrl 클래스

`CPagerCtrl` 클래스는 윈도우에 맞지 않는 포함된 창을 보기로 스크롤할 수 있는 Windows 페이저 컨트롤을 래핑합니다.

## <a name="syntax"></a>구문

```
class CPagerCtrl : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CPagerCtrl::CPagerCtrl](#cpagerctrl)|`CPagerCtrl` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CPagerCtrl::Create](#create)|지정 된 스타일을 사용 하 여 pager 컨트롤을 만들고 현재 연결 `CPagerCtrl` 개체입니다.|
|[CPagerCtrl::CreateEx](#createex)|지정 된 확장된 스타일을 사용 하 여 pager 컨트롤을 만들고 현재 연결 `CPagerCtrl` 개체입니다.|
|[CPagerCtrl::ForwardMouse](#forwardmouse)|전달을 사용 하지 않도록 설정 하거나 [WM_MOUSEMOVE](/windows/desktop/inputdev/wm-mousemove) 현재 페이저 컨트롤에 포함 된 창에는 메시지입니다.|
|[CPagerCtrl::GetBkColor](#getbkcolor)|현재 페이저 컨트롤의 배경색을 검색합니다.|
|[CPagerCtrl::GetBorder](#getborder)|현재 페이저 컨트롤의 테두리 크기를 검색 합니다.|
|[CPagerCtrl::GetButtonSize](#getbuttonsize)|현재 페이저 컨트롤의 단추 크기를 검색합니다.|
|[CPagerCtrl::GetButtonState](#getbuttonstate)|현재 페이저 컨트롤에서 지정 된 단추의 상태를 검색합니다.|
|[CPagerCtrl::GetDropTarget](#getdroptarget)|검색 된 [IDropTarget](/windows/desktop/api/oleidl/nn-oleidl-idroptarget) 현재 페이저 컨트롤에 대 한 인터페이스입니다.|
|[CPagerCtrl::GetScrollPos](#getscrollpos)|현재 페이저 컨트롤의 스크롤 위치를 검색합니다.|
|[CPagerCtrl::IsButtonDepressed](#isbuttondepressed)|현재 페이저 컨트롤의 지정 된 단추 인지 여부를 나타냅니다 `pressed` 상태입니다.|
|[CPagerCtrl::IsButtonGrayed](#isbuttongrayed)|현재 페이저 컨트롤의 지정 된 단추 인지 여부를 나타냅니다 `grayed` 상태입니다.|
|[CPagerCtrl::IsButtonHot](#isbuttonhot)|현재 페이저 컨트롤의 지정 된 단추 인지 여부를 나타냅니다 `hot` 상태입니다.|
|[CPagerCtrl::IsButtonInvisible](#isbuttoninvisible)|현재 페이저 컨트롤의 지정 된 단추 인지 여부를 나타냅니다 `invisible` 상태입니다.|
|[CPagerCtrl::IsButtonNormal](#isbuttonnormal)|현재 페이저 컨트롤의 지정 된 단추 인지 여부를 나타냅니다 `normal` 상태입니다.|
|[CPagerCtrl::RecalcSize](#recalcsize)|현재 페이저 컨트롤이 포함 된 창의 크기를 다시 계산 해야 합니다.|
|[CPagerCtrl::SetBkColor](#setbkcolor)|현재 페이저 컨트롤의 배경색을 설정합니다.|
|[CPagerCtrl::SetBorder](#setborder)|현재 페이저 컨트롤의 테두리 크기를 설정합니다.|
|[CPagerCtrl::SetButtonSize](#setbuttonsize)|현재 페이저 컨트롤의 단추 크기를 설정합니다.|
|[CPagerCtrl::SetChild](#setchild)|현재 페이저 컨트롤에 포함 된 창을 설정입니다.|
|[CPagerCtrl::SetScrollPos](#setscrollpos)|현재 페이저 컨트롤의 스크롤 위치를 설정 합니다.|

## <a name="remarks"></a>설명

Pager 컨트롤에 포함 된 기간 보다 크고 선형 이며 포함 된 창을 보기로 스크롤할 수 있습니다 다른 창에 있는 창입니다. 페이저 컨트롤 압력도 해당 범위 내에서 포함 된 창을 스크롤할 때를 자동으로 사라집니다는 두 개의 스크롤 단추 표시 되 고 그렇지 않으면 다시 나타납니다. 가로 또는 세로 방향으로 스크롤 하는 페이저 컨트롤을 만들 수 있습니다.

예를 들어, 응용 프로그램에 해당 항목이 모두 표시 하기에 충분 하지 않은 도구 모음, 페이저 컨트롤에 도구 모음을 할당할 수 있습니다 및 사용자가 왼쪽 또는 오른쪽의 모든 항목에 액세스 하려면 도구 모음을 스크롤할 수 있게 됩니다. Microsoft Internet Explorer 버전 4.0 (commctrl.dll 버전 4.71) 페이저 컨트롤을 소개합니다.

합니다 `CPagerCtrl` 에서 파생 된 클래스를 [CWnd](../../mfc/reference/cwnd-class.md) 클래스입니다. 자세한 내용 및 pager 컨트롤의 예시를 참조 하세요 [페이저 컨트롤](/windows/desktop/Controls/pager-controls)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CPagerCtrl`

## <a name="requirements"></a>요구 사항

**헤더:** afxcmn.h

##  <a name="cpagerctrl"></a>  CPagerCtrl::CPagerCtrl

`CPagerCtrl` 개체를 생성합니다.

```
CPagerCtrl();
```

### <a name="remarks"></a>설명

사용 하 여는 [CPagerCtrl::Create](#create) 또는 [CPagerCtrl::CreateEx](#createex) 페이징 컨트롤 만들기에 연결 하는 메서드를 `CPagerCtrl` 개체입니다.

##  <a name="create"></a>  CPagerCtrl::Create

지정 된 스타일을 사용 하 여 pager 컨트롤을 만들고 현재 연결 `CPagerCtrl` 개체입니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*dwStyle*|[in] 비트 조합 (OR) [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles) 하 고 [페이저 컨트롤 스타일](/windows/desktop/Controls/pager-control-styles) 컨트롤을 적용할 수 있습니다.|
|*rect*|[in] 에 대 한 참조를 [RECT](/previous-versions/dd162897\(v=vs.85\)) 클라이언트 좌표로 나타낸에서 컨트롤의 크기와 위치를 포함 하는 구조입니다.|
|*pParentWnd*|[in] 에 대 한 포인터를 [CWnd](../../mfc/reference/cwnd-class.md) 개체 컨트롤의 부모 창입니다. 이 매개 변수는 NULL 일 수 없습니다.|
|*nID*|[in] 컨트롤의 ID입니다.|

### <a name="return-value"></a>반환 값

이 메서드는 성공 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

Pager 컨트롤을 만들려면 선언를 `CPagerCtrl` 변수를 호출 합니다 [CPagerCtrl::Create](#create) 또는 [CPagerCtrl::CreateEx](#createex) 메서드는 변수를 합니다.

### <a name="example"></a>예제

다음 예제에서는 페이저 컨트롤을 만들고 다음 사용 합니다 [CPagerCtrl::SetChild](#setchild) 페이저 컨트롤을 사용 하 여 매우 긴 단추 컨트롤을 연결 하는 방법입니다. 이 예제에서는 다음 사용 합니다 [CPagerCtrl::SetButtonSize](#setbuttonsize) 20 픽셀 pager 컨트롤의 높이 설정 하는 방법 및 [CPagerCtrl::SetBorder](#setborder) 1 픽셀 테두리 두께 설정 하는 방법입니다.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

##  <a name="createex"></a>  CPagerCtrl::CreateEx

지정 된 확장된 스타일을 사용 하 여 pager 컨트롤을 만들고 현재 연결 `CPagerCtrl` 개체입니다.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*dwExStyle*|[in] 컨트롤에 적용 될 확장된 스타일의 비트 조합입니다. 자세한 내용은 참조는 *dwExStyle* 의 매개 변수를 [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) 함수입니다.|
|*dwStyle*|[in] 비트 조합 (OR) [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles) 하 고 [페이저 컨트롤 스타일](/windows/desktop/Controls/pager-control-styles) 컨트롤을 적용할 수 있습니다.|
|*rect*|[in] 에 대 한 참조를 [RECT](/previous-versions/dd162897\(v=vs.85\)) 클라이언트 좌표로 나타낸에서 컨트롤의 크기와 위치를 포함 하는 구조입니다.|
|*pParentWnd*|[in] 에 대 한 포인터를 [CWnd](../../mfc/reference/cwnd-class.md) 개체 컨트롤의 부모 창입니다. 이 매개 변수는 NULL 일 수 없습니다.|
|*nID*|[in] 컨트롤의 ID입니다.|

### <a name="return-value"></a>반환 값

이 메서드는 성공 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

Pager 컨트롤을 만들려면 선언를 `CPagerCtrl` 변수를 호출 합니다 [CPagerCtrl::Create](#create) 또는 [CPagerCtrl::CreateEx](#createex) 메서드는 변수를 합니다.

##  <a name="forwardmouse"></a>  CPagerCtrl::ForwardMouse

전달을 사용 하지 않도록 설정 하거나 [WM_MOUSEMOVE](/windows/desktop/inputdev/wm-mousemove) 현재 페이저 컨트롤에 포함 된 창에는 메시지입니다.

```
void ForwardMouse(BOOL bForward);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*bForward*|[in] 마우스 메시지를 전달 하지 정방향 마우스 메시지 또는 FALSE true로 설정 하면.|

### <a name="remarks"></a>설명

이 메서드는 전송 된 [PGM_FORWARDMOUSE](/windows/desktop/Controls/pgm-forwardmouse) Windows SDK에 설명 된 메시지입니다.

##  <a name="getborder"></a>  CPagerCtrl::GetBorder

현재 페이저 컨트롤의 테두리 크기를 검색 합니다.

```
int GetBorder() const;
```

### <a name="return-value"></a>반환 값

현재 테두리 크기를 픽셀 단위로 지정 합니다.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [PGM_GETBORDER](/windows/desktop/Controls/pgm-getborder) Windows SDK에 설명 된 메시지입니다.

### <a name="example"></a>예제

다음 예제에서는 합니다 [CPagerCtrl::GetBorder](#getborder) 페이저 컨트롤의 테두리의 두께 검색 하는 방법입니다.

[!code-cpp[NVC_MFC_CSplitButton_s2#5](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_2.cpp)]

##  <a name="getbkcolor"></a>  CPagerCtrl::GetBkColor

현재 페이저 컨트롤의 배경색을 검색합니다.

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>반환 값

A [COLORREF](/windows/desktop/gdi/colorref) pager 컨트롤의 현재 배경색을 포함 하는 값입니다.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [PGM_GETBKCOLOR](/windows/desktop/Controls/pgm-getbkcolor) Windows SDK에 설명 된 메시지입니다.

### <a name="example"></a>예제

다음 예제에서는 합니다 [CPagerCtrl::SetBkColor](#setbkcolor) 빨강으로 pager 컨트롤의 배경색을 설정 하는 방법 및 [CPagerCtrl::GetBkColor](#getbkcolor) 변경 되었는지는 확인 하는 방법입니다.

[!code-cpp[NVC_MFC_CSplitButton_s2#4](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_3.cpp)]

##  <a name="getbuttonsize"></a>  CPagerCtrl::GetButtonSize

현재 페이저 컨트롤의 단추 크기를 검색합니다.

```
int GetButtonSize() const;
```

### <a name="return-value"></a>반환 값

현재 단추 크기를 픽셀 단위로 지정 합니다.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [PGM_GETBUTTONSIZE](/windows/desktop/Controls/pgm-getbuttonsize) Windows SDK에 설명 된 메시지입니다.

페이저 컨트롤 PGS_HORZ 스타일 있으면 단추 크기의 페이저 단추 너비를 확인 하 고 페이저 컨트롤 PGS_VERT 스타일 있으면 단추 크기의 페이저 단추 높이 결정 하는 키를 누릅니다. 자세한 내용은 [페이저 컨트롤 스타일](/windows/desktop/Controls/pager-control-styles)합니다.

##  <a name="getbuttonstate"></a>  CPagerCtrl::GetButtonState

현재 페이저 컨트롤에서 지정 된 스크롤 단추의 상태를 검색합니다.

```
DWORD GetButtonState(int iButton) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*iButton*|[in] 상태를 검색할 단추를 나타냅니다. PGS_HORZ 페이저 컨트롤의 스타일을 사용 하는 경우 왼쪽된 단추와 PGB_BOTTOMORRIGHT PGB_TOPORLEFT 오른쪽 단추를 지정 합니다. PGS_VERT 페이저 컨트롤의 스타일을 사용 하는 경우 아래쪽 단추에 대 한 PGB_TOPORLEFT PGB_BOTTOMORRIGHT 위쪽 단추를 지정 합니다. 자세한 내용은 [페이저 컨트롤 스타일](/windows/desktop/Controls/pager-control-styles)합니다.|

### <a name="return-value"></a>반환 값

지정 된 단추의 상태를 *iButton* 매개 변수입니다. 상태가는 PGF_INVISIBLE, PGF_NORMAL, PGF_GRAYED, PGF_DEPRESSED, 또는 PGF_HOT입니다. 자세한 내용은 반환 값 섹션을 참조 합니다 [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) 메시지입니다.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) Windows SDK에 설명 된 메시지입니다.

##  <a name="getdroptarget"></a>  CPagerCtrl::GetDropTarget

검색 된 [IDropTarget](/windows/desktop/api/oleidl/nn-oleidl-idroptarget) 현재 페이저 컨트롤에 대 한 인터페이스입니다.

```
IDropTarget* GetDropTarget() const;
```

### <a name="return-value"></a>반환 값

에 대 한 포인터를 `IDropTarget` 현재 페이저 컨트롤에 대 한 인터페이스입니다.

### <a name="remarks"></a>설명

`IDropTarget` 구현 하는 인터페이스 중 하나는 응용 프로그램에서 끌어서 놓기 작업을 지원 합니다.

이 메서드는 전송 된 [PGM_GETDROPTARGET](/windows/desktop/Controls/pgm-getdroptarget) Windows SDK에 설명 된 메시지입니다. 이 메서드의 호출자가 호출을 `Release` 의 멤버는 [IDropTarget](/windows/desktop/api/oleidl/nn-oleidl-idroptarget) 인터페이스를 더 이상 필요 없는 경우 인터페이스.

##  <a name="getscrollpos"></a>  CPagerCtrl::GetScrollPos

현재 페이저 컨트롤의 스크롤 위치를 검색합니다.

```
int GetScrollPos() const;
```

### <a name="return-value"></a>반환 값

현재 스크롤 위치를 픽셀 단위로 지정 합니다.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [PGM_GETPOS](/windows/desktop/Controls/pgm-getpos) Windows SDK에 설명 된 메시지입니다.

### <a name="example"></a>예제

다음 예제에서는 합니다 [CPagerCtrl::GetScrollPos](#getscrollpos) pager 컨트롤의 현재 스크롤 위치를 검색 하는 방법입니다. 페이저 컨트롤을 0으로 왼쪽에 있는 위치에 이미 스크롤되지 않는 경우이 예제에서는 사용 된 [CPagerCtrl::SetScrollPos](#setscrollpos) 스크롤 위치를 0으로 설정 하는 방법입니다.

[!code-cpp[NVC_MFC_CSplitButton_s2#7](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_4.cpp)]

##  <a name="isbuttondepressed"></a>  CPagerCtrl::IsButtonDepressed

현재 페이저 컨트롤의 지정 된 스크롤 단추를 누름된 상태 인지 여부를 나타냅니다.

```
BOOL IsButtonDepressed(int iButton) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*iButton*|[in] 상태를 검색할 단추를 나타냅니다. PGS_HORZ 페이저 컨트롤의 스타일을 사용 하는 경우 왼쪽된 단추와 PGB_BOTTOMORRIGHT PGB_TOPORLEFT 오른쪽 단추를 지정 합니다. PGS_VERT 페이저 컨트롤의 스타일을 사용 하는 경우 아래쪽 단추에 대 한 PGB_TOPORLEFT PGB_BOTTOMORRIGHT 위쪽 단추를 지정 합니다. 자세한 내용은 [페이저 컨트롤 스타일](/windows/desktop/Controls/pager-control-styles)합니다.|

### <a name="return-value"></a>반환 값

지정한 단추 누름된 상태에 있으면 TRUE 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) Windows SDK에 설명 된 메시지입니다. 그런 다음 반환 되는 상태 PGF_DEPRESSED 인지 테스트 합니다. 자세한 내용은 반환 값 섹션을 참조 합니다 [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) 메시지입니다.

##  <a name="isbuttongrayed"></a>  CPagerCtrl::IsButtonGrayed

현재 페이저 컨트롤의 지정 된 스크롤 단추를 회색으로 표시 된 상태 인지 여부를 나타냅니다.

```
BOOL IsButtonGrayed(int iButton) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*iButton*|[in] 상태를 검색할 단추를 나타냅니다. PGS_HORZ 페이저 컨트롤의 스타일을 사용 하는 경우 왼쪽된 단추와 PGB_BOTTOMORRIGHT PGB_TOPORLEFT 오른쪽 단추를 지정 합니다. PGS_VERT 페이저 컨트롤의 스타일을 사용 하는 경우 아래쪽 단추에 대 한 PGB_TOPORLEFT PGB_BOTTOMORRIGHT 위쪽 단추를 지정 합니다. 자세한 내용은 [페이저 컨트롤 스타일](/windows/desktop/Controls/pager-control-styles)합니다.|

### <a name="return-value"></a>반환 값

지정한 단추가 회색으로 표시 상태에 있으면 TRUE 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) Windows SDK에 설명 된 메시지입니다. 그런 다음 반환 되는 상태 PGF_GRAYED 인지 테스트 합니다. 자세한 내용은 반환 값 섹션을 참조 합니다 [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) 메시지입니다.

##  <a name="isbuttonhot"></a>  CPagerCtrl::IsButtonHot

현재 페이저 컨트롤의 지정 된 스크롤 단추를 활성 상태 인지 여부를 나타냅니다.

```
BOOL IsButtonHot(int iButton) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*iButton*|[in] 상태를 검색할 단추를 나타냅니다. PGS_HORZ 페이저 컨트롤의 스타일을 사용 하는 경우 왼쪽된 단추와 PGB_BOTTOMORRIGHT PGB_TOPORLEFT 오른쪽 단추를 지정 합니다. PGS_VERT 페이저 컨트롤의 스타일을 사용 하는 경우 아래쪽 단추에 대 한 PGB_TOPORLEFT PGB_BOTTOMORRIGHT 위쪽 단추를 지정 합니다. 자세한 내용은 [페이저 컨트롤 스타일](/windows/desktop/Controls/pager-control-styles)합니다.|

### <a name="return-value"></a>반환 값

활성 상태의; 지정 된 단추가 있는 경우 TRUE 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) Windows SDK에 설명 된 메시지입니다. 그런 다음 반환 되는 상태 PGF_HOT 인지 테스트 합니다. 자세한 내용은 반환 값 섹션을 참조 합니다 [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) 메시지입니다.

##  <a name="isbuttoninvisible"></a>  CPagerCtrl::IsButtonInvisible

현재 페이저 컨트롤의 지정 된 스크롤 단추를 보이지 않는 상태 인지 여부를 나타냅니다.

```
BOOL IsButtonInvisible(int iButton) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*iButton*|[in] 상태를 검색할 단추를 나타냅니다. PGS_HORZ 페이저 컨트롤의 스타일을 사용 하는 경우 왼쪽된 단추와 PGB_BOTTOMORRIGHT PGB_TOPORLEFT 오른쪽 단추를 지정 합니다. PGS_VERT 페이저 컨트롤의 스타일을 사용 하는 경우 아래쪽 단추에 대 한 PGB_TOPORLEFT PGB_BOTTOMORRIGHT 위쪽 단추를 지정 합니다. 자세한 내용은 [페이저 컨트롤 스타일](/windows/desktop/Controls/pager-control-styles)합니다.|

### <a name="return-value"></a>반환 값

지정한 단추가 보이지 않는 상태에 있으면 TRUE 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

Windows에서는 추가 단추를 클릭 하면 상태로 만들 수 없습니다 포함 된 창의 자세히 보기로 때문에 포함된 된 창의 해당 먼 정도 스크롤될 때 특정 방향으로 스크롤 단추를 숨깁니다.

이 메서드는 전송 된 [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) Windows SDK에 설명 된 메시지입니다. 그런 다음 반환 되는 상태 PGF_INVISIBLE 인지 테스트 합니다. 자세한 내용은 반환 값 섹션을 참조 합니다 [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) 메시지입니다.

### <a name="example"></a>예제

다음 예제에서는 합니다 [CPagerCtrl::IsButtonInvisible](#isbuttoninvisible) pager 컨트롤의 왼쪽 및 오른쪽 스크롤 단추를 표시 하는지 여부를 결정 하는 방법입니다.

[!code-cpp[NVC_MFC_CSplitButton_s2#6](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_5.cpp)]

##  <a name="isbuttonnormal"></a>  CPagerCtrl::IsButtonNormal

현재 페이저 컨트롤의 지정 된 스크롤 단추를 정상 상태 인지 여부를 나타냅니다.

```
BOOL IsButtonNormal(int iButton) const;
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*iButton*|[in] 상태를 검색할 단추를 나타냅니다. PGS_HORZ 페이저 컨트롤의 스타일을 사용 하는 경우 왼쪽된 단추와 PGB_BOTTOMORRIGHT PGB_TOPORLEFT 오른쪽 단추를 지정 합니다. PGS_VERT 페이저 컨트롤의 스타일을 사용 하는 경우 아래쪽 단추에 대 한 PGB_TOPORLEFT PGB_BOTTOMORRIGHT 위쪽 단추를 지정 합니다. 자세한 내용은 [페이저 컨트롤 스타일](/windows/desktop/Controls/pager-control-styles)합니다.|

### <a name="return-value"></a>반환 값

표준 상태의; 지정 된 단추가 있는 경우 TRUE 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) Windows SDK에 설명 된 메시지입니다. 그런 다음 반환 되는 상태 PGF_NORMAL 인지 테스트 합니다. 자세한 내용은 반환 값 섹션을 참조 합니다 [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) 메시지입니다.

##  <a name="recalcsize"></a>  CPagerCtrl::RecalcSize

현재 페이저 컨트롤이 포함 된 창의 크기를 다시 계산 해야 합니다.

```
void RecalcSize();
```

### <a name="remarks"></a>설명

이 메서드는 전송 된 [PGM_RECALCSIZE](/windows/desktop/Controls/pgm-recalcsize) Windows SDK에 설명 된 메시지입니다. 따라서 페이저 컨트롤 보냅니다 합니다 [PGN_CALCSIZE](/windows/desktop/Controls/pgn-calcsize) 포함 된 창의 스크롤 가능한 크기를 가져오려면 알림.

### <a name="example"></a>예제

다음 예제에서는 합니다 [CPagerCtrl::RecalcSize](#recalcsize) 크기 다시 계산을 현재 페이저 컨트롤을 요청 하는 방법입니다.

[!code-cpp[NVC_MFC_CSplitButton_s2#3](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_6.cpp)]

### <a name="example"></a>예제

다음 예제에서는 [리플렉션 메시지](../../mfc/tn062-message-reflection-for-windows-controls.md) 계산을 수행 하는 컨트롤의 부모 대화 하도록 하는 대신 자체 크기 다시 계산 하도록 페이저 컨트롤을 사용 하도록 설정 합니다. 예제에서는 파생를 `MyPagerCtrl` 에서 클래스를 [CPagerCtrl 클래스](../../mfc/reference/cpagerctrl-class.md), 메시지 맵을 사용 하 여 연결 합니다 [PGN_CALCSIZE](/windows/desktop/Controls/pgn-calcsize) 알림을 `OnCalcsize` 알림 처리기입니다. 이 예제에서는 알림 처리기 고정된 값으로 pager 컨트롤의 높이 너비를 설정합니다.

[!code-cpp[NVC_MFC_CSplitButton_s2#8](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_7.cpp)]

##  <a name="setbkcolor"></a>  CPagerCtrl::SetBkColor

현재 페이저 컨트롤의 배경색을 설정합니다.

```
COLORREF SetBkColor(COLORREF clrBk);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*clrBk*|[in] A [COLORREF](/windows/desktop/gdi/colorref) pager 컨트롤의 새 배경 색을 포함 하는 값입니다.|

### <a name="return-value"></a>반환 값

A [COLORREF](/windows/desktop/gdi/colorref) pager 컨트롤의 이전 배경색을 포함 하는 값입니다.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [PGM_SETBKCOLOR](/windows/desktop/Controls/pgm-setbkcolor) Windows SDK에 설명 된 메시지입니다.

### <a name="example"></a>예제

다음 예제에서는 합니다 [CPagerCtrl::SetBkColor](#setbkcolor) 빨강으로 pager 컨트롤의 배경색을 설정 하는 방법 및 [CPagerCtrl::GetBkColor](#getbkcolor) 변경 되었는지는 확인 하는 방법입니다.

[!code-cpp[NVC_MFC_CSplitButton_s2#4](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_3.cpp)]

##  <a name="setborder"></a>  CPagerCtrl::SetBorder

현재 페이저 컨트롤의 테두리 크기를 설정합니다.

```
int SetBorder(int iBorder);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*iBorder*|[in] 새 테두리 크기를 픽셀 단위로 지정 합니다. 경우는 *iBorder* 매개 변수가 음수 이면 테두리 크기를 0으로 설정 됩니다.|

### <a name="return-value"></a>반환 값

이전 테두리 두께 픽셀 단위로 지정 합니다.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [PGM_SETBORDER](/windows/desktop/Controls/pgm-setborder) Windows SDK에 설명 된 메시지입니다.

### <a name="example"></a>예제

다음 예제에서는 페이저 컨트롤을 만들고 다음 사용 합니다 [CPagerCtrl::SetChild](#setchild) 페이저 컨트롤을 사용 하 여 매우 긴 단추 컨트롤을 연결 하는 방법입니다. 이 예제에서는 다음 사용 합니다 [CPagerCtrl::SetButtonSize](#setbuttonsize) 20 픽셀 pager 컨트롤의 높이 설정 하는 방법 및 [CPagerCtrl::SetBorder](#setborder) 1 픽셀 테두리 두께 설정 하는 방법입니다.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

##  <a name="setbuttonsize"></a>  CPagerCtrl::SetButtonSize

현재 페이저 컨트롤의 단추 크기를 설정합니다.

```
int SetButtonSize(int iButtonSize);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*iButtonSize*|[in] 새 단추 크기를 픽셀 단위로 지정 합니다.|

### <a name="return-value"></a>반환 값

이전 단추 크기를 픽셀 단위로 지정 합니다.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [PGM_SETBUTTONSIZE](/windows/desktop/Controls/pgm-setpos) Windows SDK에 설명 된 메시지입니다.

페이저 컨트롤 PGS_HORZ 스타일 있으면 단추 크기의 페이저 단추 너비를 확인 하 고 페이저 컨트롤 PGS_VERT 스타일 있으면 단추 크기의 페이저 단추 높이 결정 하는 키를 누릅니다. 기본 단추 크기는 3 / 4 스크롤 막대의 너비 및 최소 단추 크기는 12 픽셀입니다. 자세한 내용은 [페이저 컨트롤 스타일](/windows/desktop/Controls/pager-control-styles)합니다.

### <a name="example"></a>예제

다음 예제에서는 페이저 컨트롤을 만들고 다음 사용 합니다 [CPagerCtrl::SetChild](#setchild) 페이저 컨트롤을 사용 하 여 매우 긴 단추 컨트롤을 연결 하는 방법입니다. 이 예제에서는 다음 사용 합니다 [CPagerCtrl::SetButtonSize](#setbuttonsize) 20 픽셀 pager 컨트롤의 높이 설정 하는 방법 및 [CPagerCtrl::SetBorder](#setborder) 1 픽셀 테두리 두께 설정 하는 방법입니다.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

##  <a name="setchild"></a>  CPagerCtrl::SetChild

현재 페이저 컨트롤에 포함 된 창을 설정입니다.

```
void SetChild(HWND hwndChild);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*hwndChild*|[in] 처리 창에 포함 되어야 합니다.|

### <a name="remarks"></a>설명

이 메서드는 전송 된 [PGM_SETCHILD](/windows/desktop/Controls/pgm-setchild) Windows SDK에 설명 된 메시지입니다.

이 메서드는 포함된 된 창의;의 부모를 변경 하지 않습니다. 만 스크롤에 대 한 페이저 컨트롤에 대 한 창 핸들을 할당합니다. 대부분의 경우 포함된 된 창의 pager 컨트롤의 자식 창이 됩니다.

### <a name="example"></a>예제

다음 예제에서는 페이저 컨트롤을 만들고 다음 사용 합니다 [CPagerCtrl::SetChild](#setchild) 페이저 컨트롤을 사용 하 여 매우 긴 단추 컨트롤을 연결 하는 방법입니다. 이 예제에서는 다음 사용 합니다 [CPagerCtrl::SetButtonSize](#setbuttonsize) 20 픽셀 pager 컨트롤의 높이 설정 하는 방법 및 [CPagerCtrl::SetBorder](#setborder) 1 픽셀 테두리 두께 설정 하는 방법입니다.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

##  <a name="setscrollpos"></a>  CPagerCtrl::SetScrollPos

현재 페이저 컨트롤의 스크롤 위치를 설정 합니다.

```
void SetScrollPos(int iPos);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*iPos*|[in] 새 스크롤 위치를 픽셀 단위로 지정 합니다.|

### <a name="remarks"></a>설명

이 메서드는 전송 된 [PGM_SETPOS](/windows/desktop/Controls/pgm-setpos) Windows SDK에 설명 된 메시지입니다.

## <a name="see-also"></a>참고자료

[CPagerCtrl 클래스](../../mfc/reference/cpagerctrl-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[페이저 컨트롤](/windows/desktop/Controls/pager-controls)
