---
title: CSliderCtrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CSliderCtrl
- AFXCMN/CSliderCtrl
- AFXCMN/CSliderCtrl::CSliderCtrl
- AFXCMN/CSliderCtrl::ClearSel
- AFXCMN/CSliderCtrl::ClearTics
- AFXCMN/CSliderCtrl::Create
- AFXCMN/CSliderCtrl::CreateEx
- AFXCMN/CSliderCtrl::GetBuddy
- AFXCMN/CSliderCtrl::GetChannelRect
- AFXCMN/CSliderCtrl::GetLineSize
- AFXCMN/CSliderCtrl::GetNumTics
- AFXCMN/CSliderCtrl::GetPageSize
- AFXCMN/CSliderCtrl::GetPos
- AFXCMN/CSliderCtrl::GetRange
- AFXCMN/CSliderCtrl::GetRangeMax
- AFXCMN/CSliderCtrl::GetRangeMin
- AFXCMN/CSliderCtrl::GetSelection
- AFXCMN/CSliderCtrl::GetThumbLength
- AFXCMN/CSliderCtrl::GetThumbRect
- AFXCMN/CSliderCtrl::GetTic
- AFXCMN/CSliderCtrl::GetTicArray
- AFXCMN/CSliderCtrl::GetTicPos
- AFXCMN/CSliderCtrl::GetToolTips
- AFXCMN/CSliderCtrl::SetBuddy
- AFXCMN/CSliderCtrl::SetLineSize
- AFXCMN/CSliderCtrl::SetPageSize
- AFXCMN/CSliderCtrl::SetPos
- AFXCMN/CSliderCtrl::SetRange
- AFXCMN/CSliderCtrl::SetRangeMax
- AFXCMN/CSliderCtrl::SetRangeMin
- AFXCMN/CSliderCtrl::SetSelection
- AFXCMN/CSliderCtrl::SetThumbLength
- AFXCMN/CSliderCtrl::SetTic
- AFXCMN/CSliderCtrl::SetTicFreq
- AFXCMN/CSliderCtrl::SetTipSide
- AFXCMN/CSliderCtrl::SetToolTips
helpviewer_keywords:
- CSliderCtrl [MFC], CSliderCtrl
- CSliderCtrl [MFC], ClearSel
- CSliderCtrl [MFC], ClearTics
- CSliderCtrl [MFC], Create
- CSliderCtrl [MFC], CreateEx
- CSliderCtrl [MFC], GetBuddy
- CSliderCtrl [MFC], GetChannelRect
- CSliderCtrl [MFC], GetLineSize
- CSliderCtrl [MFC], GetNumTics
- CSliderCtrl [MFC], GetPageSize
- CSliderCtrl [MFC], GetPos
- CSliderCtrl [MFC], GetRange
- CSliderCtrl [MFC], GetRangeMax
- CSliderCtrl [MFC], GetRangeMin
- CSliderCtrl [MFC], GetSelection
- CSliderCtrl [MFC], GetThumbLength
- CSliderCtrl [MFC], GetThumbRect
- CSliderCtrl [MFC], GetTic
- CSliderCtrl [MFC], GetTicArray
- CSliderCtrl [MFC], GetTicPos
- CSliderCtrl [MFC], GetToolTips
- CSliderCtrl [MFC], SetBuddy
- CSliderCtrl [MFC], SetLineSize
- CSliderCtrl [MFC], SetPageSize
- CSliderCtrl [MFC], SetPos
- CSliderCtrl [MFC], SetRange
- CSliderCtrl [MFC], SetRangeMax
- CSliderCtrl [MFC], SetRangeMin
- CSliderCtrl [MFC], SetSelection
- CSliderCtrl [MFC], SetThumbLength
- CSliderCtrl [MFC], SetTic
- CSliderCtrl [MFC], SetTicFreq
- CSliderCtrl [MFC], SetTipSide
- CSliderCtrl [MFC], SetToolTips
ms.assetid: dd12b084-4eda-4550-a810-8f3cfb06b871
ms.openlocfilehash: 4db27112daf65b2c3f477527cd7b4351b91d7f18
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58776637"
---
# <a name="csliderctrl-class"></a>CSliderCtrl 클래스

Windows의 공용 슬라이더 컨트롤의 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CSliderCtrl : public CWnd
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CSliderCtrl::CSliderCtrl](#csliderctrl)|`CSliderCtrl` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CSliderCtrl::ClearSel](#clearsel)|슬라이더 컨트롤에서 현재 선택 영역을 지웁니다.|
|[CSliderCtrl::ClearTics](#cleartics)|슬라이더 컨트롤에서 현재 눈금 표시를 제거합니다.|
|[CSliderCtrl::Create](#create)|슬라이더 컨트롤을 만들고 연결 하는 `CSliderCtrl` 개체입니다.|
|[CSliderCtrl::CreateEx](#createex)|지정 된 Windows 확장된 스타일을 사용 하 여 슬라이더 컨트롤을 만들고 연결 하는 `CSliderCtrl` 개체입니다.|
|[CSliderCtrl::GetBuddy](#getbuddy)|지정된 된 위치에 있는 슬라이더 컨트롤 버디 창에 대 한 핸들을 검색합니다.|
|[CSliderCtrl::GetChannelRect](#getchannelrect)|슬라이더 컨트롤 채널의 크기를 검색합니다.|
|[CSliderCtrl::GetLineSize](#getlinesize)|슬라이더 컨트롤의 선 크기를 검색합니다.|
|[CSliderCtrl::GetNumTics](#getnumtics)|슬라이더 컨트롤에 있는 눈금 표시의 수를 검색 합니다.|
|[CSliderCtrl::GetPageSize](#getpagesize)|슬라이더 컨트롤의 페이지 크기를 검색합니다.|
|[CSliderCtrl::GetPos](#getpos)|슬라이더의 현재 위치를 검색합니다.|
|[CSliderCtrl::GetRange](#getrange)|슬라이더에 대 한 최소 및 최대 위치를 검색합니다.|
|[CSliderCtrl::GetRangeMax](#getrangemax)|최대 슬라이더의 위치를 검색합니다.|
|[CSliderCtrl::GetRangeMin](#getrangemin)|최소 슬라이더의 위치를 검색합니다.|
|[CSliderCtrl::GetSelection](#getselection)|현재 선택 영역의 범위를 검색합니다.|
|[CSliderCtrl::GetThumbLength](#getthumblength)|현재 trackbar 컨트롤에서 슬라이더의 길이 검색 합니다.|
|[CSliderCtrl::GetThumbRect](#getthumbrect)|슬라이더 컨트롤의 thumb의 크기를 검색합니다.|
|[CSliderCtrl::GetTic](#gettic)|지정 된 눈금 표시의 위치를 검색 합니다.|
|[CSliderCtrl::GetTicArray](#getticarray)|슬라이더 컨트롤에 대 한 눈금 표시 위치 배열을 검색합니다.|
|[CSliderCtrl::GetTicPos](#getticpos)|클라이언트 좌표로 지정된 눈금 표시의 위치를 검색 합니다.|
|[CSliderCtrl::GetToolTips](#gettooltips)|있는 경우 슬라이더 컨트롤에 할당 된 도구 설명 컨트롤에 대 한 핸들을 검색 합니다.|
|[CSliderCtrl::SetBuddy](#setbuddy)|슬라이더 컨트롤의 버디 창으로 창을 할당합니다.|
|[CSliderCtrl::SetLineSize](#setlinesize)|슬라이더 컨트롤의 선 크기를 설정합니다.|
|[CSliderCtrl::SetPageSize](#setpagesize)|슬라이더 컨트롤의 페이지 크기를 설정합니다.|
|[CSliderCtrl::SetPos](#setpos)|슬라이더의 현재 위치를 설정합니다.|
|[CSliderCtrl::SetRange](#setrange)|슬라이더에 대 한 최소 및 최대 위치를 설정합니다.|
|[CSliderCtrl::SetRangeMax](#setrangemax)|최대 슬라이더의 위치를 설정합니다.|
|[CSliderCtrl::SetRangeMin](#setrangemin)|최소 슬라이더의 위치를 설정합니다.|
|[CSliderCtrl::SetSelection](#setselection)|현재 선택 영역의 범위를 설정합니다.|
|[CSliderCtrl::SetThumbLength](#setthumblength)|현재 trackbar 컨트롤에서 슬라이더의 길이 설정합니다.|
|[CSliderCtrl::SetTic](#settic)|지정 된 눈금 표시의 위치를 설정 합니다.|
|[CSliderCtrl::SetTicFreq](#setticfreq)|슬라이더 컨트롤 증가 당 표시 눈금의 빈도 설정합니다.|
|[CSliderCtrl::SetTipSide](#settipside)|위치 trackbar 컨트롤에서 도구 설명 컨트롤을 사용 합니다.|
|[CSliderCtrl::SetToolTips](#settooltips)|슬라이더 컨트롤에 도구 설명 컨트롤을 할당합니다.|

## <a name="remarks"></a>설명

"Slider 컨트롤" (trackbar)은 슬라이더 및 선택적 눈금 표시를 포함 하는 창입니다. 이동할 때 슬라이더에 마우스 또는 방향 키를 사용 하 여, 컨트롤에 변경 내용을 나타내는 알림 메시지를 보냅니다.

슬라이더 컨트롤을 범위에서 불연속 값 또는 연속 값의 집합을 선택할 때 유용 합니다. 예를 들어, 사용자 지정된 눈금 표시를 슬라이더를 이동 하 여 키보드 반복 속도 설정 하도록 허용 하는 슬라이더 컨트롤을 사용할 수 있습니다.

이 컨트롤 (및 따라서는 `CSliderCtrl` 클래스) 이상 Windows 95/98 및 Windows NT 버전 3.51에서 실행 중인 프로그램에만 사용할 수 있습니다.

슬라이더를 만들 때 지정 하는 단위로 이동 합니다. 예를 들어, 슬라이더를 5 개 범위 있어야 함을 지정 하는 경우 슬라이더 수만 자리를 차지 6: 슬라이더 컨트롤을 범위에서 각 증가값에 대해 하나의 위치 왼쪽 위치입니다. 일반적으로 이러한 각 위치는 눈금으로 식별 됩니다.

생성자를 사용 하 여 슬라이더를 만들면 하며 `Create` 멤버 함수 `CSliderCtrl`합니다. 슬라이더 컨트롤을 만든 경우의 멤버 함수를 사용할 수 있습니다 `CSliderCtrl` 다양 한 속성을 변경 합니다. 슬라이더에 대한 최소 및 최대 위치 설정, 눈금 표시 그리기, 선택 범위 설정 및 슬라이더 위치 조정을 변경할 수 있습니다.

사용 하 여 대 한 자세한 내용은 `CSliderCtrl`를 참조 하세요 [컨트롤](../../mfc/controls-mfc.md) 하 고 [CSliderCtrl 사용 하 여](../../mfc/using-csliderctrl.md).

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CSliderCtrl`

## <a name="requirements"></a>요구 사항

**헤더:** afxcmn.h

##  <a name="clearsel"></a>  CSliderCtrl::ClearSel

슬라이더 컨트롤에서 현재 선택 영역을 지웁니다.

```
void ClearSel(BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>매개 변수

*bRedraw*<br/>
플래그를 다시 그립니다. 슬라이더 선택이 취소 되 면 다시 그리면이 매개 변수가 TRUE 인 경우 그렇지 않은 경우 슬라이더는 다시 그려지지 않습니다.

##  <a name="cleartics"></a>  CSliderCtrl::ClearTics

슬라이더 컨트롤에서 현재 눈금 표시를 제거합니다.

```
void ClearTics(BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>매개 변수

*bRedraw*<br/>
플래그를 다시 그립니다. 눈금 표시의 선택을 취소; 후 슬라이더를 다시 그릴이 매개 변수가 TRUE 인 경우 그렇지 않은 경우 슬라이더는 다시 그려지지 않습니다.

##  <a name="create"></a>  CSliderCtrl::Create

슬라이더 컨트롤을 만들고 연결 하는 `CSliderCtrl` 개체입니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

*dwStyle*<br/>
슬라이더 컨트롤의 스타일을 지정합니다. 어떤 조합도 적용할 [슬라이더 컨트롤 스타일](/windows/desktop/Controls/trackbar-control-styles)컨트롤에 Windows SDK에서 설명 합니다.

*rect*<br/>
슬라이더 컨트롤의 크기와 위치를 지정합니다. 수 있습니다는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](/previous-versions/dd162897\(v=vs.85\)) 구조입니다.

*pParentWnd*<br/>
일반적으로 슬라이더 컨트롤의 부모 창 지정을 `CDialog`입니다. NULL이 아니어야 합니다.

*nID*<br/>
슬라이더 컨트롤의 ID를 지정합니다.

### <a name="return-value"></a>반환 값

초기화에 성공 하면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

생성 된 `CSliderCtrl` 두 단계에서. 먼저 생성자를 호출 하 고 호출 `Create`, 슬라이더 컨트롤을 만들고 연결 하는 `CSliderCtrl` 개체입니다.

에 설정 된 값에 따라 *dwStyle*, 슬라이더 컨트롤을 세로 또는 가로 방향 중 하나를 가질 수 있습니다. 어느 쪽에 눈금 표시가 있을 수 있습니다 또는 둘 다 양쪽 모두 합니다. 연속 값의 범위를 지정 하려면 데도 수 있습니다.

확장된 창 스타일 슬라이더 컨트롤에 적용할 호출 [CreateEx](#createex) 대신 `Create`합니다.

##  <a name="createex"></a>  CSliderCtrl::CreateEx

컨트롤 (자식 창)을 만들고 사용 하 여 연결 된 `CSliderCtrl` 개체입니다.

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
슬라이더 컨트롤의 스타일을 지정합니다. 어떤 조합도 적용할 [슬라이더 컨트롤 스타일](/windows/desktop/Controls/trackbar-control-styles)컨트롤에 Windows SDK에서 설명 합니다.

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

##  <a name="csliderctrl"></a>  CSliderCtrl::CSliderCtrl

`CSliderCtrl` 개체를 생성합니다.

```
CSliderCtrl();
```

##  <a name="getbuddy"></a>  CSliderCtrl::GetBuddy

지정된 된 위치에 있는 슬라이더 컨트롤 버디 창에 대 한 핸들을 검색합니다.

```
CWnd* GetBuddy(BOOL fLocation = TRUE) const;
```

### <a name="parameters"></a>매개 변수

*fLocation*<br/>
검색할 두 개의 버디 창 핸들을 나타내는 부울 값입니다. 다음 값 중 하나입니다.

- TRUE 버디 슬라이더의 왼쪽에 대 한 핸들을 검색합니다. 슬라이더 컨트롤 TBS_VERT 스타일에서는 메시지를 슬라이더 위에 버디를 검색 합니다.

- FALSE 버디 슬라이더의 오른쪽에 대 한 핸들을 검색합니다. 슬라이더 컨트롤 TBS_VERT 스타일에서는 메시지 슬라이더 아래로 버디를 검색 합니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 [CWnd](../../mfc/reference/cwnd-class.md) 개체에서 지정 된 위치의 버디 창입니다 *fLocation*, 해당 위치에 있는 버디 창 없는 경우 null입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [TBM_GETBUDDY](/windows/desktop/Controls/tbm-getbuddy)Windows SDK에 설명 된 대로 합니다. 슬라이더 컨트롤 스타일에 대 한 참조 [Trackbar 컨트롤 스타일](/windows/desktop/Controls/trackbar-control-styles) Windows SDK에 있습니다.

##  <a name="getchannelrect"></a>  CSliderCtrl::GetChannelRect

슬라이더 컨트롤의 채널에 대 한 경계 사각형의 위치와 크기를 검색합니다.

```
void GetChannelRect(LPRECT lprc) const;
```

### <a name="parameters"></a>매개 변수

*lprc*<br/>
에 대 한 포인터를 [CRect](../../atl-mfc-shared/reference/crect-class.md) 함수가 반환할 때 채널의 위치와 크기를 포함 하는 개체의 경계 사각형입니다.

### <a name="remarks"></a>설명

채널을 통해 슬라이더를 이동 하 고 범위를 선택 하는 경우 강조 표시를 포함 하는 영역입니다.

##  <a name="getlinesize"></a>  CSliderCtrl::GetLineSize

슬라이더 컨트롤에 대 한 라인의 크기를 검색합니다.

```
int GetLineSize() const;
```

### <a name="return-value"></a>반환 값

슬라이더 컨트롤에 대 한 줄의 크기입니다.

### <a name="remarks"></a>설명

줄 크기를 TB_LINEUP 및 TB_LINEDOWN 알림에 대 한 슬라이더를 이동 하는 영향을 줍니다. 줄 크기에 대 한 기본값은 1입니다.

##  <a name="getnumtics"></a>  CSliderCtrl::GetNumTics

슬라이더 컨트롤에 있는 눈금 표시의 수를 검색 합니다.

```
UINT GetNumTics() const;
```

### <a name="return-value"></a>반환 값

슬라이더 컨트롤의 눈금 표시의 수입니다.

##  <a name="getpagesize"></a>  CSliderCtrl::GetPageSize

슬라이더 컨트롤에 대 한 페이지의 크기를 검색합니다.

```
int GetPageSize() const;
```

### <a name="return-value"></a>반환 값

슬라이더 컨트롤에 대 한 페이지의 크기입니다.

### <a name="remarks"></a>설명

페이지 크기 TB_PAGEUP 및 TB_PAGEDOWN 알림에 대 한 슬라이더를 이동 하는 영향을 줍니다.

##  <a name="getpos"></a>  CSliderCtrl::GetPos

슬라이더 컨트롤에 있는 슬라이더의 현재 위치를 검색합니다.

```
int GetPos() const;
```

### <a name="return-value"></a>반환 값

현재 위치입니다.

##  <a name="getrange"></a>  CSliderCtrl::GetRange

슬라이더 컨트롤에 있는 슬라이더에 대 한 최대 및 최소 위치를 검색합니다.

```
void GetRange(
    int& nMin,
    int& nMax) const;
```

### <a name="parameters"></a>매개 변수

*nMin*<br/>
최소 위치를 수신 하는 정수에 대 한 참조입니다.

*nMax*<br/>
최대 위치를 수신 하는 정수에 대 한 참조입니다.

### <a name="remarks"></a>설명

이 함수에서 참조 하는 정수 값을 복사 *nMin* 하 고 *최대*합니다.

##  <a name="getrangemax"></a>  CSliderCtrl::GetRangeMax

슬라이더 컨트롤에 있는 슬라이더에 대 한 최대 위치를 검색합니다.

```
int GetRangeMax() const;
```

### <a name="return-value"></a>반환 값

컨트롤의 최대 위치입니다.

##  <a name="getrangemin"></a>  CSliderCtrl::GetRangeMin

슬라이더 컨트롤에 있는 슬라이더에 대 한 최소 위치를 검색 합니다.

```
int GetRangeMin() const;
```

### <a name="return-value"></a>반환 값

컨트롤의 최소 위치입니다.

##  <a name="getselection"></a>  CSliderCtrl::GetSelection

슬라이더 컨트롤에서 현재 선택 영역의 시작 및 끝 위치를 검색합니다.

```
void GetSelection(
    int& nMin,
    int& nMax) const;
```

### <a name="parameters"></a>매개 변수

*nMin*<br/>
현재 선택 영역의 시작 위치를 수신 하는 정수에 대 한 참조입니다.

*nMax*<br/>
현재 선택 영역의 끝 위치를 수신 하는 정수에 대 한 참조입니다.

##  <a name="getthumblength"></a>  CSliderCtrl::GetThumbLength

현재 trackbar 컨트롤에서 슬라이더의 길이 검색 합니다.

```
int GetThumbLength() const;
```

### <a name="return-value"></a>반환 값

픽셀에서 슬라이더의 길이입니다.

### <a name="remarks"></a>설명

이 메서드는 전송 된 [TBM_GETTHUMBLENGTH](/windows/desktop/Controls/tbm-getthumblength) Windows SDK에 설명 된 메시지입니다.

##  <a name="getthumbrect"></a>  CSliderCtrl::GetThumbRect

슬라이더 컨트롤에 있는 슬라이더 (엄지 단추)에 대 한 경계 사각형의 위치와 크기를 검색합니다.

```
void GetThumbRect(LPRECT lprc) const;
```

### <a name="parameters"></a>매개 변수

*lprc*<br/>
에 대 한 포인터를 `CRect` 함수가 반환할 때 슬라이더에 대 한 경계 사각형을 포함 하는 개체입니다.

##  <a name="gettic"></a>  CSliderCtrl::GetTic

슬라이더 컨트롤에 있는 눈금 표시의 위치를 검색 합니다.

```
int GetTic(int nTic) const;
```

### <a name="parameters"></a>매개 변수

*nTic*<br/>
눈금 표시를 식별 하는 0부터 시작 인덱스입니다.

### <a name="return-value"></a>반환 값

위치 지정된 눈금 표시 또는-1 이면 *nTic* 유효한 인덱스를 지정 하지 않습니다.

##  <a name="getticarray"></a>  CSliderCtrl::GetTicArray

슬라이더 컨트롤에 대 한 눈금 표시의 위치를 포함 하는 배열의 주소를 검색 합니다.

```
DWORD* GetTicArray() const;
```

### <a name="return-value"></a>반환 값

주소 슬라이더 컨트롤에 대 한 눈금 표시 위치를 포함 하는 배열입니다.

##  <a name="getticpos"></a>  CSliderCtrl::GetTicPos

슬라이더 컨트롤에 있는 눈금 표시의 현재 실제 위치를 검색합니다.

```
int GetTicPos(int nTic) const;
```

### <a name="parameters"></a>매개 변수

*nTic*<br/>
눈금 표시를 식별 하는 0부터 시작 인덱스입니다.

### <a name="return-value"></a>반환 값

실제 위치를 클라이언트 좌표로 지정된 눈금 표시 또는-1 이면 *nTic* 유효한 인덱스를 지정 하지 않습니다.

##  <a name="gettooltips"></a>  CSliderCtrl::GetToolTips

있는 경우 슬라이더 컨트롤에 할당 된 도구 설명 컨트롤에 대 한 핸들을 검색 합니다.

```
CToolTipCtrl* GetToolTips() const;
```

### <a name="return-value"></a>반환 값

에 대 한 포인터를 [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) 개체 또는 도구 설명을 사용 하지 않는 경우 NULL입니다. 슬라이더 컨트롤 TBS_TOOLTIPS 스타일을 사용 하지 않는 경우 반환 값은 NULL입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [TBM_GETTOOLTIPS](/windows/desktop/Controls/tbm-gettooltips)Windows SDK에 설명 된 대로 합니다. 이 멤버 함수를 반환 하는 참고를 `CToolTipCtrl` 컨트롤에 대 한 핸들 대신 개체입니다.

슬라이더 컨트롤 스타일에 대 한 참조 [Trackbar 컨트롤 스타일](/windows/desktop/Controls/trackbar-control-styles) Windows SDK에 있습니다.

##  <a name="setbuddy"></a>  CSliderCtrl::SetBuddy

슬라이더 컨트롤의 버디 창으로 창을 할당합니다.

```
CWnd* SetBuddy(
    CWnd* pWndBuddy,
    BOOL fLocation = TRUE);
```

### <a name="parameters"></a>매개 변수

*pWndBuddy*<br/>
에 대 한 포인터를 `CWnd` 슬라이더 컨트롤의 버디로 설정 될 개체입니다.

*fLocation*<br/>
버디 창에 표시할 위치를 지정 하는 값입니다. 이 값 중 하나일 수 있습니다.

- TRUE 버디가 나타납니다 왼쪽 트랙 표시줄의 트랙 표시줄 컨트롤에서 TBS_HORZ 스타일을 사용 하는 경우. 트랙 표시줄 TBS_VERT 스타일에서는 버디 trackbar 컨트롤 위에 나타납니다.

- FALSE 버디가 나타납니다 오른쪽 트랙 표시줄의 트랙 표시줄 컨트롤에서 TBS_HORZ 스타일을 사용 하는 경우. 트랙 표시줄 TBS_VERT 스타일에서는 버디 trackbar 컨트롤 아래 표시 됩니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 [CWnd](../../mfc/reference/cwnd-class.md) 이전에 해당 위치에 있는 슬라이더 컨트롤에 할당 된 개체입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [TBM_SETBUDDY](/windows/desktop/Controls/tbm-setbuddy)Windows SDK에 설명 된 대로 합니다. 이 멤버 함수에 대 한 포인터는 `CWnd` 해당 반환 값 및 매개 변수 모두에 대 한 창 핸들 보다는 개체입니다.

슬라이더 컨트롤 스타일에 대 한 참조 [Trackbar 컨트롤 스타일](/windows/desktop/Controls/trackbar-control-styles) Windows SDK에 있습니다.

##  <a name="setlinesize"></a>  CSliderCtrl::SetLineSize

슬라이더 컨트롤에 대 한 라인의 크기를 설정합니다.

```
int SetLineSize(int nSize);
```

### <a name="parameters"></a>매개 변수

*nSize*<br/>
슬라이더 컨트롤의 새 줄 크기입니다.

### <a name="return-value"></a>반환 값

이전 줄 크기입니다.

### <a name="remarks"></a>설명

줄 크기를 TB_LINEUP 및 TB_LINEDOWN 알림에 대 한 슬라이더를 이동 하는 영향을 줍니다.

##  <a name="setpagesize"></a>  CSliderCtrl::SetPageSize

슬라이더 컨트롤에 대 한 페이지의 크기를 설정합니다.

```
int SetPageSize(int nSize);
```

### <a name="parameters"></a>매개 변수

*nSize*<br/>
슬라이더 컨트롤의 새 페이지 크기입니다.

### <a name="return-value"></a>반환 값

이전 페이지 크기입니다.

### <a name="remarks"></a>설명

페이지 크기 TB_PAGEUP 및 TB_PAGEDOWN 알림에 대 한 슬라이더를 이동 하는 영향을 줍니다.

##  <a name="setpos"></a>  CSliderCtrl::SetPos

슬라이더 컨트롤에 있는 슬라이더의 현재 위치를 설정합니다.

```
void SetPos(int nPos);
```

### <a name="parameters"></a>매개 변수

*nPos*<br/>
새 슬라이더 위치를 지정합니다.

##  <a name="setrange"></a>  CSliderCtrl::SetRange

슬라이더 컨트롤에 있는 슬라이더의 범위 (최소 및 최대 위치)를 설정 합니다.

```
void SetRange(
    int nMin,
    int nMax,
    BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>매개 변수

*nMin*<br/>
최소 슬라이더 위치입니다.

*nMax*<br/>
최대 슬라이더 위치입니다.

*bRedraw*<br/>
다시 그리기 플래그입니다. 범위도; 후 슬라이더를 다시 그릴이 매개 변수가 TRUE 인 경우 그렇지 않은 경우 슬라이더는 다시 그려지지 않습니다.

##  <a name="setrangemax"></a>  CSliderCtrl::SetRangeMax

슬라이더 컨트롤에 있는 슬라이더에 대 한 최대 범위를 설정합니다.

```
void SetRangeMax(
    int nMax,
    BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>매개 변수

*nMax*<br/>
최대 슬라이더 위치입니다.

*bRedraw*<br/>
다시 그리기 플래그입니다. 범위도; 후 슬라이더를 다시 그릴이 매개 변수가 TRUE 인 경우 그렇지 않은 경우 슬라이더는 다시 그려지지 않습니다.

##  <a name="setrangemin"></a>  CSliderCtrl::SetRangeMin

슬라이더 컨트롤에 있는 슬라이더에 대 한 최소 범위를 설정합니다.

```
void SetRangeMin(
    int nMin,
    BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>매개 변수

*nMin*<br/>
최소 슬라이더 위치입니다.

*bRedraw*<br/>
다시 그리기 플래그입니다. 범위도; 후 슬라이더를 다시 그릴이 매개 변수가 TRUE 인 경우 그렇지 않은 경우 슬라이더는 다시 그려지지 않습니다.

##  <a name="setselection"></a>  CSliderCtrl::SetSelection

슬라이더 컨트롤에서 현재 선택 영역의 시작 및 끝 위치를 설정합니다.

```
void SetSelection(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>매개 변수

*nMin*<br/>
슬라이더의 시작 위치입니다.

*nMax*<br/>
슬라이더에 대 한 끝 위치입니다.

##  <a name="setthumblength"></a>  CSliderCtrl::SetThumbLength

현재 trackbar 컨트롤에서 슬라이더의 길이 설정합니다.

```
void SetThumbLength(int nLength);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*nLength*|[in] 픽셀에서 슬라이더의 길이입니다.|

### <a name="remarks"></a>설명

Trackbar 컨트롤을 설정할 수는이 메서드에 필요 [TBS_FIXEDLENGTH](/windows/desktop/Controls/trackbar-control-styles) 스타일입니다.

이 메서드는 전송 된 [TBM_SETTHUMBLENGTH](/windows/desktop/Controls/tbm-setthumblength) Windows SDK에 설명 된 메시지입니다.

### <a name="example"></a>예제

다음 코드 예제에서는 변수를 정의 `m_sliderCtrl`, 즉 현재 trackbar 컨트롤에 액세스 하는 데 사용 합니다. 이 예제에서는 변수를 정의 `thumbLength`, 즉 trackbar 컨트롤의 thumb 구성 요소의 기본 길이 저장 하는 데 사용 합니다. 이러한 변수는 다음 예제에서 사용 됩니다.

[!code-cpp[NVC_MFC_CSliderCtrl_s1#1](../../mfc/reference/codesnippet/cpp/csliderctrl-class_1.h)]

### <a name="example"></a>예제

다음 코드 예제에서는 해당 기본 길이 두 번 trackbar 컨트롤의 스크롤 상자 구성 요소를 설정합니다.

[!code-cpp[NVC_MFC_CSliderCtrl_s1#2](../../mfc/reference/codesnippet/cpp/csliderctrl-class_2.cpp)]

##  <a name="settic"></a>  CSliderCtrl::SetTic

슬라이더 컨트롤에 있는 눈금 표시의 위치를 설정합니다.

```
BOOL SetTic(int nTic);
```

### <a name="parameters"></a>매개 변수

*nTic*<br/>
눈금 표시의 위치입니다. 이 매개 변수는 양수 값을 지정 해야 합니다.

### <a name="return-value"></a>반환 값

눈금 표시 설정 되어; 경우 0이 아닌 값 그렇지 않으면 0입니다.

##  <a name="setticfreq"></a>  CSliderCtrl::SetTicFreq

빈도 눈금 표시에에서 표시 되는 슬라이더를 설정 합니다.

```
void SetTicFreq(int nFreq);
```

### <a name="parameters"></a>매개 변수

*nFreq*<br/>
눈금 표시의 빈도입니다.

### <a name="remarks"></a>설명

예를 들어, 빈도 2로 설정 하는 경우 슬라이더의 범위에서 모든 다른 증가 대 한 눈금 표시 됩니다. 빈도 1에 대 한 기본 설정은 (즉, 범위에서 모든 증분 연관 된 눈금 표시).

이 함수를 사용 하 여 TBS_AUTOTICKS 스타일으로 컨트롤을 만들어야 합니다. 자세한 내용은 [CSliderCtrl::Create](#create)합니다.

##  <a name="settipside"></a>  CSliderCtrl::SetTipSide

위치 trackbar 컨트롤에서 도구 설명 컨트롤을 사용 합니다.

```
int SetTipSide(int nLocation);
```

### <a name="parameters"></a>매개 변수

*n 위치*<br/>
도구 설명 컨트롤을 표시할 위치를 나타내는 값입니다. 가능한 값 목록을 Win32 메시지를 참조 하세요 [TBM_SETTIPSIDE](/windows/desktop/Controls/tbm-settipside)Windows SDK에 설명 된 대로 합니다.

### <a name="return-value"></a>반환 값

도구 설명 컨트롤의 이전 위치를 나타내는 값입니다. 반환 값 같음의 가능한 값 중 하나 *n 위치*합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Windows SDK에 설명 된 대로 TBM_SETTIPSIDE, Win32 메시지의 동작을 구현 합니다. TBS_TOOLTIPS 스타일을 사용 하는 슬라이더 컨트롤에 도구 설명을 표시 합니다. 슬라이더 컨트롤 스타일에 대 한 참조 [Trackbar 컨트롤 스타일](/windows/desktop/Controls/trackbar-control-styles) Windows SDK에 있습니다.

##  <a name="settooltips"></a>  CSliderCtrl::SetToolTips

슬라이더 컨트롤에 도구 설명 컨트롤을 할당합니다.

```
void SetToolTips(CToolTipCtrl* pWndTip);
```

### <a name="parameters"></a>매개 변수

*pWndTip*<br/>
에 대 한 포인터를 [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) 슬라이더 컨트롤을 사용 하는 도구 설명을 포함 하는 개체입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 Win32 메시지의 동작을 구현 [TBM_SETTOOLTIPS](/windows/desktop/Controls/tbm-settooltips)Windows SDK에 설명 된 대로 합니다. 슬라이더 컨트롤을 TBS_TOOLTIPS 스타일을 사용 하 여 만들어질 때 슬라이더의 현재 위치를 표시, 슬라이더 옆에 표시 되는 기본 도구 설명 컨트롤을 만듭니다. 슬라이더 컨트롤 스타일에 대 한 참조 [Trackbar 컨트롤 스타일](/windows/desktop/Controls/trackbar-control-styles) Windows SDK에 있습니다.

## <a name="see-also"></a>참고자료

[MFC 샘플 CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[CWnd 클래스](../../mfc/reference/cwnd-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CProgressCtrl 클래스](../../mfc/reference/cprogressctrl-class.md)
