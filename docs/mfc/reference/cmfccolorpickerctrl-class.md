---
title: CMFCColorPickerCtrl 클래스
ms.date: 11/19/2018
f1_keywords:
- CMFCColorPickerCtrl
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::CMFCColorPickerCtrl
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetColor
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetHLS
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetHue
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetLuminance
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetSaturation
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SelectCellHexagon
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetColor
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetHLS
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetHue
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetLuminance
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetLuminanceBarWidth
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetOriginalColor
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetPalette
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetSaturation
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetType
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::DrawCursor
helpviewer_keywords:
- CMFCColorPickerCtrl [MFC], CMFCColorPickerCtrl
- CMFCColorPickerCtrl [MFC], GetColor
- CMFCColorPickerCtrl [MFC], GetHLS
- CMFCColorPickerCtrl [MFC], GetHue
- CMFCColorPickerCtrl [MFC], GetLuminance
- CMFCColorPickerCtrl [MFC], GetSaturation
- CMFCColorPickerCtrl [MFC], SelectCellHexagon
- CMFCColorPickerCtrl [MFC], SetColor
- CMFCColorPickerCtrl [MFC], SetHLS
- CMFCColorPickerCtrl [MFC], SetHue
- CMFCColorPickerCtrl [MFC], SetLuminance
- CMFCColorPickerCtrl [MFC], SetLuminanceBarWidth
- CMFCColorPickerCtrl [MFC], SetOriginalColor
- CMFCColorPickerCtrl [MFC], SetPalette
- CMFCColorPickerCtrl [MFC], SetSaturation
- CMFCColorPickerCtrl [MFC], SetType
- CMFCColorPickerCtrl [MFC], DrawCursor
ms.assetid: b9bbd03c-beb0-4b55-9765-9985fd05e5dc
ms.openlocfilehash: 1977717ee590acb63655ba21bfa5eb6bfe7c9bd8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403794"
---
# <a name="cmfccolorpickerctrl-class"></a>CMFCColorPickerCtrl 클래스

`CMFCColorPickerCtrl` 클래스 색을 선택 하는 데 사용 되는 컨트롤에 대 한 기능을 제공 합니다.

## <a name="syntax"></a>구문

```
class CMFCColorPickerCtrl : public CButton
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMFCColorPickerCtrl::CMFCColorPickerCtrl](#cmfccolorpickerctrl)|`CMFCColorPickerCtrl` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMFCColorPickerCtrl::GetColor](#getcolor)|사용자가 선택한 색을 검색 합니다.|
|[CMFCColorPickerCtrl::GetHLS](#gethls)|사용자가 선택한 색의 색상, 광도 및 채도 값을 검색 합니다.|
|[CMFCColorPickerCtrl::GetHue](#gethue)|사용자가 선택한 색의 색상 구성 요소를 검색 합니다.|
|[CMFCColorPickerCtrl::GetLuminance](#getluminance)|사용자가 선택한 색의 광도 구성 요소를 검색 합니다.|
|[CMFCColorPickerCtrl::GetSaturation](#getsaturation)|사용자가 선택한 색의 채도 구성 요소를 검색 합니다.|
|[CMFCColorPickerCtrl::SelectCellHexagon](#selectcellhexagon)|지정된 된 RGB 색 구성 요소 또는 지정 된 셀 육각형에 정의 된 색에 현재 색을 설정 합니다.|
|[CMFCColorPickerCtrl::SetColor](#setcolor)|지정된 된 RGB 색 값으로 현재 색을 설정합니다.|
|[CMFCColorPickerCtrl::SetHLS](#sethls)|지정된 된 HLS 색 값으로 현재 색을 설정합니다.|
|[CMFCColorPickerCtrl::SetHue](#sethue)|현재 선택한 색의 색상 구성 요소를 변경합니다.|
|[CMFCColorPickerCtrl::SetLuminance](#setluminance)|현재 선택한 색의 광도 구성 요소를 변경합니다.|
|[CMFCColorPickerCtrl::SetLuminanceBarWidth](#setluminancebarwidth)|색 선택 컨트롤에서 광도 막대의 너비를 설정합니다.|
|[CMFCColorPickerCtrl::SetOriginalColor](#setoriginalcolor)|초기 선택한 색을 설정합니다.|
|[CMFCColorPickerCtrl::SetPalette](#setpalette)|현재 색상표를 설정합니다.|
|[CMFCColorPickerCtrl::SetSaturation](#setsaturation)|현재 선택한 색의 채도 구성 요소를 변경합니다.|
|[CMFCColorPickerCtrl::SetType](#settype)|표시할 색 선택 컨트롤의 형식을 설정 합니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[CMFCColorPickerCtrl::DrawCursor](#drawcursor)|선택한 색을 가리키는 커서 표시 되기 전에 프레임 워크에서 호출 됩니다.|

## <a name="remarks"></a>설명

표준 색 육각 색상표에서 선택 하 고 사용자 지정 색 광도 모음에서 선택한 색은 빨강/녹색/파랑 표기법 또는 hue/satuaration/광도 표기법을 사용 하 여 지정 됩니다.

다음 그림에서는 몇 가지를 보여 주며 `CMFCColorPickerCtrl` 개체입니다.

![CMFCColorPickerCtrl 대화 상자](../../mfc/reference/media/colorpicker.png "CMFCColorPickerCtrl 대화 상자")

`CMFCColorPickerCtrl` 스타일의 두 쌍을 지원 합니다. 16 진수 및 HEX_GREYSCALE 스타일 표준 색 선택에 적합 합니다. 선택과 광도 스타일 사용자 지정 색 선택에 적합 합니다.

통합 하려면 다음 단계를 수행 합니다 `CMFCColorPickerCtrl` 대화 상자에 컨트롤:

1. 사용 하는 경우는 **ClassWizard**, 대화 상자 템플릿의 새 단추 컨트롤을 삽입 (때문에 `CMFCColorPickerCtrl` 클래스에서 상속 됩니다는 `CButton` 클래스).

1. 대화 상자 클래스에 새 단추 컨트롤과 연결 된 멤버 변수를 삽입 합니다. 변수 형식을 변경한 `CButton` 에 `CMFCColorPickerCtrl`입니다.

1. 삽입 된 `WM_INITDIALOG` 대화 상자 클래스에 대 한 메시지 처리기입니다. 처리기에서 유형, 색상표 및 초기 선택한 색을 설정 합니다 `CMFCColorPickerCtrl` 제어 합니다.

## <a name="example"></a>예제

다음 예제에서는 구성 하는 방법에 설명 된 `CMFCColorPickerCtrl` 에서 다양 한 메서드를 사용 하 여 개체를 `CMFCColorPickerCtrl` 클래스입니다. 예제에는 선택 컨트롤의 유형을 설정 하는 방법 및 해당 색, 색상, 광도 및 채도 설정 하는 방법을 보여 줍니다. 일부인 예제는 [새 컨트롤 샘플](../../overview/visual-cpp-samples.md)합니다.

[!code-cpp[NVC_MFC_NewControls#4](../../mfc/reference/codesnippet/cpp/cmfccolorpickerctrl-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#5](../../mfc/reference/codesnippet/cpp/cmfccolorpickerctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCColorPickerCtrl](../../mfc/reference/cmfccolorpickerctrl-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxcolorpickerctrl.h

##  <a name="cmfccolorpickerctrl"></a>  CMFCColorPickerCtrl::CMFCColorPickerCtrl

`CMFCColorPickerCtrl` 개체를 생성합니다.

```
CMFCColorPickerCtrl();
```

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="drawcursor"></a>  CMFCColorPickerCtrl::DrawCursor

선택한 색을 가리키는 커서 표시 되기 전에 프레임 워크에서 호출 됩니다.

```
virtual void DrawCursor(
    CDC* pDC,
    const CRect& rect);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 장치 컨텍스트에 대 한 포인터입니다.

*rect*<br/>
[in] 선택한 색으로 사각형 영역을 지정합니다.

### <a name="remarks"></a>설명

선택한 색을 가리키는 커서의 모양을 변경 해야 할 경우이 메서드를 재정의 합니다.

##  <a name="getcolor"></a>  CMFCColorPickerCtrl::GetColor

사용자가 선택한 색을 검색 합니다.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>반환 값

선택한 색의 RGB 값입니다.

### <a name="remarks"></a>설명

##  <a name="gethls"></a>  CMFCColorPickerCtrl::GetHLS

사용자가 선택한 색의 색상, 광도 및 채도 값을 검색 합니다.

```
void GetHLS(
    double* hue,
    double* luminance,
    double* saturation);
```

### <a name="parameters"></a>매개 변수

*hue*<br/>
[out] Hue 정보를 수신 하는 double 형식의 변수에 대 한 포인터입니다.

*luminance*<br/>
[out] 광도 정보를 수신 하는 double 형식의 변수에 대 한 포인터입니다.

*saturation*<br/>
[out] 채도 정보를 수신 하는 double 형식의 변수에 대 한 포인터입니다.

### <a name="remarks"></a>설명

##  <a name="gethue"></a>  CMFCColorPickerCtrl::GetHue

사용자가 선택한 색의 색상 구성 요소를 검색 합니다.

```
double GetHue() const;
```

### <a name="return-value"></a>반환 값

선택한 색의 색상 구성 요소입니다.

### <a name="remarks"></a>설명

##  <a name="getluminance"></a>  CMFCColorPickerCtrl::GetLuminance

사용자가 선택한 색의 광도 구성 요소를 검색 합니다.

```
double GetLuminance() const;
```

### <a name="return-value"></a>반환 값

선택한 색의 광도 구성 요소입니다.

### <a name="remarks"></a>설명

##  <a name="getsaturation"></a>  CMFCColorPickerCtrl::GetSaturation

사용자가 선택한 색의 채도 값을 검색 합니다.

```
double GetSaturation() const;
```

### <a name="return-value"></a>반환 값

선택한 색의 채도 구성 요소입니다.

### <a name="remarks"></a>설명

##  <a name="selectcellhexagon"></a>  CMFCColorPickerCtrl::SelectCellHexagon

지정된 된 RGB 색 구성 요소 또는 지정 된 셀 육각형에 정의 된 색에 현재 색을 설정 합니다.

```
void SelectCellHexagon(
    BYTE R,
    BYTE G,
    BYTE B);

BOOL SelectCellHexagon(
    int x,
    int y);
```

### <a name="parameters"></a>매개 변수

*R*<br/>
[in] 빨간색 구성 요소입니다.

*G*<br/>
[in] 녹색 구성 요소입니다.

*B*<br/>
[in] 파란색 구성 요소입니다.

*x*<br/>
[in] 셀 육각형을 가리키는 커서의 x 좌표입니다.

*y*<br/>
[in] 셀 육각형을 가리키는 커서의 y 좌표입니다.

### <a name="return-value"></a>반환 값

이 메서드의 두 번째 오버 로드는 항상 FALSE를 반환합니다.

### <a name="remarks"></a>설명

현재 색의 색 선택 컨트롤에 해당 하는 색이 설정의 첫 번째 오버 로드의 빨강, 녹색 및 파랑 색 구성 요소를 지정 합니다.

이 메서드의 두 번째 오버 로드는 지정 된 커서 위치에 따라 가리키는 셀 육각형의 색으로 현재 색을 설정 합니다.

##  <a name="setcolor"></a>  CMFCColorPickerCtrl::SetColor

지정된 된 RGB 색 값으로 현재 색을 설정합니다.

```
void SetColor(COLORREF Color);
```

### <a name="parameters"></a>매개 변수

*색*<br/>
[in] RGB 색 값입니다.

### <a name="remarks"></a>설명

##  <a name="sethls"></a>  CMFCColorPickerCtrl::SetHLS

지정된 된 HLS 색 값으로 현재 색을 설정합니다.

```
void SetHLS(
    double hue,
    double luminance,
    double saturation,
    BOOL bInvalidate=TRUE);
```

### <a name="parameters"></a>매개 변수

*hue*<br/>
[in] 색상 값입니다.

*luminance*<br/>
[in] 광도 값입니다.

*saturation*<br/>
[in] 채도 값입니다.

*bInvalidate*<br/>
[in] 강제로 창; 새로운 색으로 즉시 업데이트. 그렇지 않으면 FALSE입니다. 기본값은 TRUE입니다.

### <a name="remarks"></a>설명

##  <a name="sethue"></a>  CMFCColorPickerCtrl::SetHue

현재 선택한 색의 색상을 변경합니다.

```
void SetHue(double Hue);
```

### <a name="parameters"></a>매개 변수

*Hue*<br/>
[in] 색상 값입니다.

### <a name="remarks"></a>설명

##  <a name="setluminance"></a>  CMFCColorPickerCtrl::SetLuminance

현재 선택한 색의 광도 변경합니다.

```
void SetLuminance(double Luminance);
```

### <a name="parameters"></a>매개 변수

*광도*<br/>
[in] 광도 값입니다.

### <a name="remarks"></a>설명

##  <a name="setluminancebarwidth"></a>  CMFCColorPickerCtrl::SetLuminanceBarWidth

색 선택 컨트롤에서 광도 막대의 너비를 설정합니다.

```
void SetLuminanceBarWidth(int w);
```

### <a name="parameters"></a>매개 변수

*w*<br/>
[in] 광도 막대의 너비를 픽셀 단위로 지정 합니다.

### <a name="remarks"></a>설명

에 있는 광도 막대의 크기를 조정 하려면이 메서드를 사용 합니다 **사용자 지정** 색 선택 컨트롤의 탭 합니다. 합니다 *w* 광도 막대의 새 너비를 지정 하는 매개 변수입니다. 너비 값에는 3 / 4 클라이언트 영역의 너비를 초과 하는 경우 무시 됩니다.

##  <a name="setoriginalcolor"></a>  CMFCColorPickerCtrl::SetOriginalColor

초기 선택한 색을 설정합니다.

```
void SetOriginalColor(COLORREF ref);
```

### <a name="parameters"></a>매개 변수

*ref*<br/>
[in] RGB 색 값입니다.

### <a name="remarks"></a>설명

색 선택 컨트롤을 초기화할 때이 메서드를 호출 합니다.

##  <a name="setpalette"></a>  CMFCColorPickerCtrl::SetPalette

현재 색상표를 설정합니다.

```
void SetPalette(CPalette* pPalette);
```

### <a name="parameters"></a>매개 변수

*pPalette*<br/>
[in] 색상표를 가리키는 포인터입니다.

### <a name="remarks"></a>설명

색상표 색 선택 컨트롤에서 표시 되는 색 배열을 정의 합니다.

##  <a name="setsaturation"></a>  CMFCColorPickerCtrl::SetSaturation

현재 선택한 색의 채도 변경합니다.

```
void SetSaturation(double Saturation);
```

### <a name="parameters"></a>매개 변수

*채도*<br/>
[in] 채도 값입니다.

### <a name="remarks"></a>설명

##  <a name="settype"></a>  CMFCColorPickerCtrl::SetType

표시할 색 선택 컨트롤의 형식을 설정 합니다.

```
void SetType(COLORTYPE colorType);
```

### <a name="parameters"></a>매개 변수

*colorType*<br/>
[in] 색 선택 컨트롤 형식입니다.

형식에서 정의 된는 `CMFCColorPickerCtrl::COLORTYPE` 열거형입니다. 가능한 유형은 광도 "," 선택 "," HEX "및" HEX_GREYSCALE입니다. 기본 형식은 선택기입니다.

### <a name="remarks"></a>설명

색 선택 컨트롤 형식을 지정 하려면 Windows 컨트롤을 만들기 전에이 메서드를 호출 합니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCColorDialog 클래스](../../mfc/reference/cmfccolordialog-class.md)
