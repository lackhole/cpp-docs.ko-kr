---
title: CDrawingManager 클래스
ms.date: 11/04/2016
f1_keywords:
- CDrawingManager
- AFXDRAWMANAGER/CDrawingManager
- AFXDRAWMANAGER/CDrawingManager::CDrawingManager
- AFXDRAWMANAGER/CDrawingManager::CreateBitmap_32
- AFXDRAWMANAGER/CDrawingManager::DrawAlpha
- AFXDRAWMANAGER/CDrawingManager::DrawRotated
- AFXDRAWMANAGER/CDrawingManager::DrawEllipse
- AFXDRAWMANAGER/CDrawingManager::DrawGradientRing
- AFXDRAWMANAGER/CDrawingManager::DrawRect
- AFXDRAWMANAGER/CDrawingManager::DrawShadow
- AFXDRAWMANAGER/CDrawingManager::Fill4ColorsGradient
- AFXDRAWMANAGER/CDrawingManager::FillGradient
- AFXDRAWMANAGER/CDrawingManager::FillGradient2
- AFXDRAWMANAGER/CDrawingManager::GrayRect
- AFXDRAWMANAGER/CDrawingManager::HighlightRect
- AFXDRAWMANAGER/CDrawingManager::HLStoRGB_ONE
- AFXDRAWMANAGER/CDrawingManager::HLStoRGB_TWO
- AFXDRAWMANAGER/CDrawingManager::HSVtoRGB
- AFXDRAWMANAGER/CDrawingManager::HuetoRGB
- AFXDRAWMANAGER/CDrawingManager::MirrorRect
- AFXDRAWMANAGER/CDrawingManager::PixelAlpha
- AFXDRAWMANAGER/CDrawingManager::PrepareShadowMask
- AFXDRAWMANAGER/CDrawingManager::RGBtoHSL
- AFXDRAWMANAGER/CDrawingManager::RGBtoHSV
- AFXDRAWMANAGER/CDrawingManager::SetAlphaPixel
- AFXDRAWMANAGER/CDrawingManager::SetPixel
- AFXDRAWMANAGER/CDrawingManager::SmartMixColors
helpviewer_keywords:
- CDrawingManager [MFC], CDrawingManager
- CDrawingManager [MFC], CreateBitmap_32
- CDrawingManager [MFC], DrawAlpha
- CDrawingManager [MFC], DrawRotated
- CDrawingManager [MFC], DrawEllipse
- CDrawingManager [MFC], DrawGradientRing
- CDrawingManager [MFC], DrawRect
- CDrawingManager [MFC], DrawShadow
- CDrawingManager [MFC], Fill4ColorsGradient
- CDrawingManager [MFC], FillGradient
- CDrawingManager [MFC], FillGradient2
- CDrawingManager [MFC], GrayRect
- CDrawingManager [MFC], HighlightRect
- CDrawingManager [MFC], HLStoRGB_ONE
- CDrawingManager [MFC], HLStoRGB_TWO
- CDrawingManager [MFC], HSVtoRGB
- CDrawingManager [MFC], HuetoRGB
- CDrawingManager [MFC], MirrorRect
- CDrawingManager [MFC], PixelAlpha
- CDrawingManager [MFC], PrepareShadowMask
- CDrawingManager [MFC], RGBtoHSL
- CDrawingManager [MFC], RGBtoHSV
- CDrawingManager [MFC], SetAlphaPixel
- CDrawingManager [MFC], SetPixel
- CDrawingManager [MFC], SmartMixColors
ms.assetid: 9e4775ca-101b-4aa9-a85a-4d047c701215
ms.openlocfilehash: f14b21c97e5a36d5107e7db526e4153446ae2a01
ms.sourcegitcommit: 90817d9d78fbaed8ffacde63f3add334842e596f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2019
ms.locfileid: "58278537"
---
# <a name="cdrawingmanager-class"></a>CDrawingManager 클래스

`CDrawingManager` 클래스는 복합 그리기 알고리즘을 구현 합니다.

## <a name="syntax"></a>구문

```
class CDrawingManager : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CDrawingManager::CDrawingManager](#cdrawingmanager)|`CDrawingManager` 개체를 생성합니다.|
|`CDrawingManager::~CDrawingManager`|소멸자|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CDrawingManager::CreateBitmap_32](#createbitmap_32)|응용 프로그램에 직접 쓸 수 있는 32 비트 장치 독립적 비트맵 DIB ()을 만듭니다.|
|[CDrawingManager::DrawAlpha](#drawalpha)|투명 하거나 반투명 픽셀로 있는 비트맵을 표시 합니다.|
|[CDrawingManager::DrawRotated](#drawrotated)|원본-90도에서 지정된 된 사각형 내에서 DC 콘텐츠 회전|
|[CDrawingManager::DrawEllipse](#drawellipse)|제공 된 테두리 및 채우기 색을 사용 하 여 타원을 그립니다.|
|[CDrawingManager::DrawGradientRing](#drawgradientring)|링 그리고 색 그라데이션을 사용 하 여 채웁니다.|
|[CDrawingManager::DrawLine, CDrawingManager::DrawLineA](#drawline_cdrawingmanager__drawlinea)|선을 그립니다.|
|[CDrawingManager::DrawRect](#drawrect)|제공 된 테두리 및 채우기 색을 사용 하 여 사각형을 그립니다.|
|[CDrawingManager::DrawShadow](#drawshadow)|사각형 영역에 대 한 그림자를 그립니다.|
|[CDrawingManager::Fill4ColorsGradient](#fill4colorsgradient)|두 가지 색 그라데이션을 사용 하 여 사각형 영역을 채웁니다.|
|[CDrawingManager::FillGradient](#fillgradient)|지정 된 색 그라데이션을 사용 하 여 사각형 영역을 채웁니다.|
|[CDrawingManager::FillGradient2](#fillgradient2)|지정 된 색 그라데이션을 사용 하 여 사각형 영역을 채웁니다. 그라데이션 중지점의 색 변경의 방향은 지정 됩니다.|
|[CDrawingManager::GrayRect](#grayrect)|지정한 회색 색으로 사각형을 채웁니다.|
|[CDrawingManager::HighlightRect](#highlightrect)|사각형 영역을 강조 표시합니다.|
|[CDrawingManager::HLStoRGB_ONE](#hlstorgb_one)|HLS 표현에서 색을 RGB 표현으로 변환 합니다.|
|[CDrawingManager::HLStoRGB_TWO](#hlstorgb_two)|HLS 표현에서 색을 RGB 표현으로 변환 합니다.|
|[CDrawingManager::HSVtoRGB](#hsvtorgb)|HSV 표현에서 색을 RGB 표현으로 변환 합니다.|
|[CDrawingManager::HuetoRGB](#huetorgb)|빨간색, 녹색 또는 파란색 구성 요소에 색상 값을 변환 하는 도우미 메서드.|
|[CDrawingManager::MirrorRect](#mirrorrect)|사각형 영역을 대칭 이동합니다.|
|[CDrawingManager::PixelAlpha](#pixelalpha)|반투명 픽셀의 최종 색을 결정 하는 도우미 메서드.|
|[CDrawingManager::PrepareShadowMask](#prepareshadowmask)|그림자를 사용할 수 있는 비트맵을 만듭니다.|
|[CDrawingManager::RGBtoHSL](#rgbtohsl)|색을 RGB 표현에서을 HSL 표현으로 변환 합니다.|
|[CDrawingManager::RGBtoHSV](#rgbtohsv)|색을 RGB 표현에서을 HSV 표현으로 변환 합니다.|
|[CDrawingManager::SetAlphaPixel](#setalphapixel)|부분적으로 투명 한 비트맵의 픽셀 색 도우미 메서드.|
|[CDrawingManager::SetPixel](#setpixel)|단일 픽셀 비트맵의 지정된 된 색으로 변경 하는 도우미 메서드.|
|[CDrawingManager::SmartMixColors](#smartmixcolors)|가중치가 적용 된 비율에 따라 두 가지 색을 결합 합니다.|

## <a name="remarks"></a>설명

`CDrawingManager` 클래스 그림자, 색 그라데이션 및 강조 표시 된 사각형을 그리기 위한 함수를 제공 합니다. 또한 알파 혼합 수행합니다. 직접 응용 프로그램의 UI를 변경 하려면이 클래스를 사용할 수 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)<br/>
`CDrawingManager`

## <a name="requirements"></a>요구 사항

**헤더:** afxdrawmanager.h

##  <a name="cdrawingmanager"></a>  CDrawingManager::CDrawingManager

생성 된 [CDrawingManager](../../mfc/reference/cdrawingmanager-class.md) 개체입니다.

```
CDrawingManager(CDC& dc);
```

### <a name="parameters"></a>매개 변수

*dc*<br/>
[in] 장치 컨텍스트에 대 한 참조입니다. `CDrawingManager` 그리기에 대 한이 컨텍스트를 사용 합니다.

##  <a name="createbitmap_32"></a>  CDrawingManager::CreateBitmap_32

응용 프로그램에 직접 쓸 수 있는 32 비트 장치 독립적 비트맵 DIB ()을 만듭니다.

```
static HBITMAP __stdcall CreateBitmap_32(
    const CSize& size,
    void** pBits);

static HBITMAP __stdcall CreateBitmap_32(
    HBITMAP bitmap,
    COLORREF clrTransparent = -1);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*size*|[in] A [CSize](../../atl-mfc-shared/reference/csize-class.md) 비트맵의 크기를 나타내는 매개 변수입니다.|
|*pBits*|[out] DIB의 위치를 수신 하는 데이터 포인터에 비트 값입니다.|
|*bitmap*|원래 비트맵에 대 한 핸들|
|*clrTransparent*|원래 비트맵의 투명 한 색을 지정 하는 RGB 값입니다.|

### <a name="return-value"></a>반환 값

이 메서드가 성공할 경우 새로 만든된 DIB 비트맵에 대 한 핸들 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

DIB 비트맵을 만드는 방법에 대 한 자세한 내용은 참조 하세요. [CreateDIBSection](/windows/desktop/api/wingdi/nf-wingdi-createdibitmap)합니다.

##  <a name="drawalpha"></a>  CDrawingManager::DrawAlpha

투명 하거나 반투명 픽셀로 있는 비트맵을 표시 합니다.

```
void DrawAlpha(
    CDC* pDstDC,
    const CRect& rectDst,
    CDC* pSrcDC,
    const CRect& rectSrc);
```

### <a name="parameters"></a>매개 변수

*pDstDC*<br/>
[in] 대상 장치 컨텍스트에 대 한 포인터입니다.

*rectDst*<br/>
[in] 대상 사각형입니다.

*pSrcDC*<br/>
[in] 원본에 대 한 장치 컨텍스트 포인터입니다.

*rectSrc*<br/>
[in] 소스 사각형입니다.

### <a name="remarks"></a>설명

이 메서드가 두 비트맵의 알파 혼합을 수행합니다. 알파 혼합 하는 방법에 대 한 자세한 내용은 참조 하세요. [해 서 AlphaBlend](/windows/desktop/api/wingdi/nf-wingdi-alphablend) Windows SDK에 있습니다.

##  <a name="drawellipse"></a>  CDrawingManager::DrawEllipse

제공 된 테두리 및 채우기 색을 사용 하 여 타원을 그립니다.

```
void DrawEllipse(
    const CRect& rect,
    COLORREF clrFill,
    COLORREF clrLine);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
[in] 타원에 대 한 경계 사각형입니다.

*clrFill*<br/>
[in] 이 메서드는 타원을 채우는 데 사용 된 색입니다.

*clrLine*<br/>
[in] 이 메서드는 타원의 테두리 색입니다.

### <a name="remarks"></a>설명

이 메서드는 두 색은-1로 설정 하는 경우 타원 그리기 없이 반환 합니다. 경계 사각형의 두 차원을 0 이면 타원 그리기 없이 반환 합니다.

##  <a name="drawgradientring"></a>  CDrawingManager::DrawGradientRing

링 그리고 색 그라데이션을 사용 하 여 채웁니다.

```
BOOL DrawGradientRing(
    CRect rect,
    COLORREF colorStart,
    COLORREF colorFinish,
    COLORREF colorBorder,
    int nAngle,
    int nWidth,
    COLORREF clrFace = (COLORREF)-1);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
[in] A [CRect](../../atl-mfc-shared/reference/crect-class.md) 그라데이션 링에 대 한 경계를 지정 하는 매개 변수입니다.

*colorStart*<br/>
[in] 첫 번째 그라데이션 색입니다.

*colorFinish*<br/>
[in] 그라데이션의 마지막 색입니다.

*colorBorder*<br/>
[in] 테두리의 색입니다.

*nAngle*<br/>
[in] 초기 그라데이션 그리기 각도 지정 하는 매개 변수입니다. 이 값은 0에서 360 사이 여야 합니다.

*nWidth*<br/>
[in] 링에 대 한 테두리의 너비입니다.

*clrFace*<br/>
[in] 내부 링의 색입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

정의 된 사각형 *rect* 최소 5 픽셀 너비와 5 픽셀 이어야 합니다.

##  <a name="drawline_cdrawingmanager__drawlinea"></a>  CDrawingManager::DrawLine, CDrawingManager::DrawLineA

선을 그립니다.

```
void DrawLine(
    int x1,
    int y1,
    int x2,
    int y2,
    COLORREF clrLine);

void DrawLineA(
    double x1,
    double y1,
    double x2,
    double y2,
    COLORREF clrLine);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*x1*|[in] 줄 시작 위치 x 좌표입니다.|
|*y1*|[in] 줄 시작 위치 y 좌표입니다.|
|*x2*|[in] 줄이 끝나는 x 좌표입니다.|
|*y2*|[in] 줄이 끝나는 y 좌표입니다.|
|*clrLine*|[in] 선의 색입니다.|

### <a name="remarks"></a>설명

이 메서드가 실패 하는 경우 *clrLine* 가-1입니다.

##  <a name="drawrect"></a>  CDrawingManager::DrawRect

제공 된 테두리 및 채우기 색을 사용 하 여 사각형을 그립니다.

```
void DrawRect(
    const CRect& rect,
    COLORREF clrFill,
    COLORREF clrLine);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
[in] 사각형의 경계입니다.

*clrFill*<br/>
[in] 이 메서드는 사각형을 채우는 데 사용 된 색입니다.

*clrLine*<br/>
[in] 이 메서드는 사각형의 테두리 색입니다.

### <a name="remarks"></a>설명

이 메서드는 두 색을-1로 설정 된 경우 사각형을 그리지 않고 반환 합니다. 사각형의 두 차원을 0 인 경우 반환 합니다.

##  <a name="drawshadow"></a>  CDrawingManager::DrawShadow

사각형 영역에 대 한 그림자를 그립니다.

```
BOOL DrawShadow(
    CRect rect,
    int nDepth,
    int iMinBrightness = 100,
    int iMaxBrightness = 50,
    CBitmap* pBmpSaveBottom = NULL,
    CBitmap* pBmpSaveRight = NULL,
    COLORREF clrBase = (COLORREF)-1,
    BOOL bRightShadow = TRUE);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
[in] 응용 프로그램에서 사각형 영역입니다. 그리기 관리자를이 영역 아래에 있는 그림자를 그립니다.

*nDepth*<br/>
[in] 그림자의 높이 너비입니다.

*iMinBrightness*<br/>
[in] 그림자의 최소 밝기입니다.

*iMaxBrightness*<br/>
[in] 그림자의 최대 밝기입니다.

*pBmpSaveBottom*<br/>
[in] 그림자의 아래 부분에 대 한 이미지가 포함 된 비트맵에 대 한 포인터입니다.

*pBmpSaveRight*<br/>
[in] 사각형의 오른쪽에 그린 그림자에 대 한 이미지가 포함 된 비트맵에 대 한 포인터입니다.

*clrBase*<br/>
[in] 그림자의 색입니다.

*bRightShadow*<br/>
[in] 그림자를 그리는 방법을 나타내는 부울 매개 변수입니다. 하는 경우 *bRightShadow* 됩니다 `TRUE`, `DrawShadow` 사각형의 오른쪽에 그림자를 그립니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

매개 변수를 사용 하 여 아래쪽 및 오른쪽 그림자에 대 한 두 개의 유효한 비트맵을 제공할 수 있습니다 *pBmpSaveBottom* 하 고 *pBmpSaveRight*합니다. 이러한 경우 [CBitmap](../../mfc/reference/cbitmap-class.md) 개체에 연결 된 GDI 개체 `DrawShadow` 그림자도 이러한 비트맵을 사용 합니다. 경우는 `CBitmap` 매개 변수에 연결 된 GDI 개체에 없는 `DrawShadow` 매개 변수를 비트맵에 연결 하 고 그림자를 그립니다. 에 대 한 호출 이후 `DrawShadow`에 이러한 비트맵 그리기 프로세스 속도 제공할 수 있습니다. 에 대 한 자세한 내용은 합니다 `CBitmap` 클래스 및 GDI 개체를 참조 하세요 [그래픽 개체](../../mfc/graphic-objects.md)합니다.

이러한 매개 변수 중 하나에 해당 하는 경우 `NULL`, `DrawShadow` 는 자동으로 그림자를 그립니다.

설정 하는 경우 *bRightShadow* FALSE로 그림자를 그릴 사각형 영역의 왼쪽 아래 하 합니다.

### <a name="example"></a>예제

다음 예제에서는 사용 하는 방법에 설명 합니다 `DrawShadow` 메서드는 `CDrawingManager` 클래스입니다. 이 코드 조각은의 일부인 합니다 [Prop 시트 데모 샘플](../../visual-cpp-samples.md)합니다.

[!code-cpp[NVC_MFC_PropSheetDemo#1](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_1.cpp)]

##  <a name="fill4colorsgradient"></a>  CDrawingManager::Fill4ColorsGradient

두 가지 색 그라데이션을 사용 하 여 사각형 영역을 채웁니다.

```
void Fill4ColorsGradient(
    CRect rect,
    COLORREF colorStart1,
    COLORREF colorFinish1,
    COLORREF colorStart2,
    COLORREF colorFinish2,
    BOOL bHorz = TRUE,
    int nPercentage = 50);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
[in] 채울 사각형입니다.

*colorStart1*<br/>
[in] 첫 번째 색 그라데이션에 대 한 초기 색입니다.

*colorFinish1*<br/>
[in] 첫 번째 색 그라데이션의 마지막 색입니다.

*colorStart2*<br/>
[in] 두 번째 색 그라데이션에 대 한 초기 색입니다.

*colorFinish2*<br/>
[in] 한 두 번째 색 그라데이션의 마지막 색입니다.

*bHorz*<br/>
[in] 나타내는 부울 매개 변수 여부 `Fill4ColorsGradient` 가로 또는 세로 그라데이션 색입니다. True 이면 가로 그라데이션이 나타냅니다.

*nPercentage*<br/>
[in] 0-100 까지의 정수입니다. 이 값은 첫 번째 색 그라데이션을 사용 하 여 채울 사각형의 백분율을 나타냅니다.

### <a name="remarks"></a>설명

서로 위에 있는 또는 서로 값에 따라 다음 중 하나는 두 색 그라데이션을 사용 하 여 사각형 가득 차면 *bHorz*합니다. 각 색 그라데이션 메서드를 사용 하 여 독립적으로 계산 됩니다 [CDrawingManager::FillGradient](#fillgradient)합니다.

이 메서드는 경우 어설션 오류를 생성 *nPercentage* 가 0 보다 작거나 100 보다 합니다.

##  <a name="fillgradient"></a>  CDrawingManager::FillGradient

지정 된 색 그라데이션을 사용 하 여 사각형 영역을 채웁니다.

```
void FillGradient(
    CRect rect,
    COLORREF colorStart,
    COLORREF colorFinish,
    BOOL bHorz = TRUE,
    int nStartFlatPercentage = 0,
    int nEndFlatPercentage = 0);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
[in] 채울 사각형 영역입니다.

*colorStart*<br/>
[in] 첫 번째 그라데이션 색입니다.

*colorFinish*<br/>
[in] 그라데이션의 마지막 색입니다.

*bHorz*<br/>
[in] 부울 매개 변수를 지정 하 여부를 `FillGradient` 가로 또는 세로 그라데이션을 그리는 해야 합니다.

*nStartFlatPercentage*<br/>
[in] 사각형의 백분율입니다 `FillGradient` 채웁니다 *colorStart* 그라데이션의 시작 하기 전에 합니다.

*nEndFlatPercentage*<br/>
[in] 사각형의 백분율입니다 `FillGradient` 채웁니다 *colorFinish* 그라데이션의 완료 된 후입니다.

### <a name="example"></a>예제

다음 예제에서는 사용 하는 방법에 설명 합니다 `FillGradient` 메서드는 `CDrawingManager` 클래스입니다. 이 코드 조각은의 일부인 합니다 [MS Office 2007 데모 샘플](../../visual-cpp-samples.md)합니다.

[!code-cpp[NVC_MFC_MSOffice2007Demo#12](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_2.cpp)]

##  <a name="fillgradient2"></a>  CDrawingManager::FillGradient2

지정 된 색 그라데이션을 사용 하 여 사각형 영역을 채웁니다.

```
void FillGradient2 (
    CRect rect,
    COLORREF colorStart,
    COLORREF colorFinish,
    int nAngle = 0);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
[in] 채울 사각형 영역입니다.

*colorStart*<br/>
[in] 그라데이션의 첫 번째 색입니다.

*colorFinish*<br/>
[in] 그라데이션의 마지막 색입니다.

*nAngle*<br/>
[in] 0과 360 사이의 정수입니다. 이 매개 변수는 색 그라데이션의 방향을 지정 합니다.

### <a name="remarks"></a>설명

사용 하 여 *nAngle* 색 그라데이션의 방향을 지정 합니다. 색 그라데이션의 방향을 지정 하는 경우 또한 지정할 색 그라데이션의 시작 되는 위치입니다. 값이 0에 대 한 *nAngle* 그라데이션의 사각형의 위쪽에서 시작을 나타냅니다. 로 *nAngle* 증가 하면 시작 되는 위치 그라데이션의 각도에 따라 시계 반대 방향에서 이동에 대 한 합니다.

### <a name="example"></a>예제

다음 예제에서는 사용 하는 방법에 설명 합니다 `FillGradient2` 메서드는 `CDrawingManager` 클래스입니다. 이 코드 조각은의 일부인 합니다 [새 컨트롤 샘플](../../visual-cpp-samples.md)합니다.

[!code-cpp[NVC_MFC_NewControls#37](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_3.cpp)]

##  <a name="grayrect"></a>  CDrawingManager::GrayRect

지정한 회색 색으로 사각형을 채웁니다.

```
BOOL GrayRect(
    CRect rect,
    int nPercentage = -1,
    COLORREF clrTransparent = (COLORREF)-1,
    COLORREF clrDisabled = (COLORREF)-1);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
[in] 채울 사각형 영역입니다.

*nPercentage*<br/>
[in] 사각형에 회색의 비율입니다.

*clrTransparent*<br/>
[in] 투명 한 색입니다.

*clrDisabled*<br/>
[in] 색 채도 취소에 대 한 경우이 메서드를 사용 하 *nPercentage* -1로 설정 됩니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

매개 변수의 *nPercentage*, 값이 낮을수록 더 어두운 색을 나타냅니다.

에 대 한 최대값 *nPercentage* 는 200 개입니다. 200 보다 큰 값에는 사각형의 모양을 변경 되지 않습니다. 이 메서드는 값이-1 이면 *clrDisabled* 사각형의 채도 제한 합니다.

##  <a name="highlightrect"></a>  CDrawingManager::HighlightRect

사각형 영역을 강조 표시합니다.

```
BOOL HighlightRect(
    CRect rect,
    int nPercentage = -1,
    COLORREF clrTransparent = (COLORREF)-1,
    int nTolerance = 0,
    COLORREF clrBlend = (COLORREF)-1);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
[in] 강조 표시 하는 사각형 영역입니다.

*nPercentage*<br/>
[in] 투명도 강조 표시 해야 여부를 나타내는 백분율입니다.

*clrTransparent*<br/>
[in] 투명 한 색입니다.

*nTolerance*<br/>
[in] 색 허용 오차를 나타내는 0과 255 사이의 정수입니다.

*clrBlend*<br/>
[in] 혼합에 대 한 기본 색입니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

하는 경우 *nPercentage* 0에서 99 사이의 `HighlightRect` 알파 혼합 알고리즘을 사용 합니다. 알파 혼합 하는 방법에 대 한 자세한 내용은 참조 하십시오 [알파 혼합 선 및 채우기](/dotnet/framework/winforms/advanced/alpha-blending-lines-and-fills)합니다. 하는 경우 *nPercentage* 가-1 이면이 메서드는 기본 강조 표시 수준을 사용 합니다. 하는 경우 *nPercentage* 100 이면이 메서드는 아무 작업도 수행 하지 하 고 TRUE를 반환 합니다.

매개 변수를 사용 하는 메서드 *nTolerance* 사각형 영역을 강조 표시 여부를 결정 합니다. 사각형을 응용 프로그램의 배경색 간의 차이 강조 표시 및 *clrTransparent* 이어야 합니다 미만 *nTolerance* (빨강, 녹색 및 파랑)에 각 색의 구성 요소에서.

##  <a name="hlstorgb_one"></a>  CDrawingManager::HLStoRGB_ONE

HLS 표현에서 색을 RGB 표현으로 변환 합니다.

```
static COLORREF __stdcall HLStoRGB_ONE(
    double H,
    double L,
    double S);
```

### <a name="parameters"></a>매개 변수

*H*<br/>
[in] 0과 1 사이의 숫자 색에 대 한 색상을 나타냅니다.

*L*<br/>
[in] 0과 1 사이의 숫자는 색의 명도 나타냅니다.

*S*<br/>
[in] 0과 1 사이의 숫자 색 채도 나타냅니다.

### <a name="return-value"></a>반환 값

제공 된 HLS 색의 RGB 표현입니다.

### <a name="remarks"></a>설명

HSV (색상, 채도 및 값), (색상, 채도 및 명도), HSL 또는 RGB (빨강, 녹색 및 파랑) 색을 나타낼 수 있습니다. 색의 다양 한 표현에 대 한 자세한 내용은 참조 하세요. [Color](/windows/desktop/uxguide/vis-color)합니다.

이 메서드는 `CDrawingManager::HLStoRGB_TWO` 메서드가 동일한 작업을 수행 하지만 서로 다른 값이 필요 합니다 *H* 매개 변수입니다. 이 메서드에서 *H* 원의 비율입니다. 에 `CDrawingManager::HLStoRGB_TWO` 메서드를 *H* 가 값 0을 모두 나타내는 빨간색부터 360 사이입니다. 예를 들어 `HLStoRGB_ONE`에 대 한 0.25 *H* 사용 하 여 90 값과 동일 `HLStoRGB_TWO`.

##  <a name="hlstorgb_two"></a>  CDrawingManager::HLStoRGB_TWO

HLS 표현에서 색을 RGB 표현으로 변환 합니다.

```
static COLORREF __stdcall HLStoRGB_TWO(
    double H,
    double L,
    double S);
```

### <a name="parameters"></a>매개 변수

*H*<br/>
[in] 색에 대 한 색상을 나타내는 0과 360 사이의 수입니다.

*L*<br/>
[in] 0과 1 사이의 숫자는 색의 명도 나타냅니다.

*S*<br/>
[in] 0과 1 사이의 숫자 색 채도 나타냅니다.

### <a name="return-value"></a>반환 값

제공 된 HLS 색의 RGB 표현입니다.

### <a name="remarks"></a>설명

HSV (색상, 채도 및 값), (색상, 채도 및 명도), HSL 또는 RGB (빨강, 녹색 및 파랑) 색을 나타낼 수 있습니다. 색의 다양 한 표현에 대 한 자세한 내용은 참조 하세요. [Color](/windows/desktop/uxguide/vis-color)합니다.

이 메서드는 [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one) 메서드가 동일한 작업을 수행 하지만 서로 다른 값이 필요 합니다 *H* 매개 변수입니다. 이 메서드에서 *H* 가 값 0을 모두 나타내는 빨간색부터 360 사이입니다. 에 [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one) 메서드를 *H* 원의 비율입니다. 예를 들어 `HLStoRGB_ONE`에 대 한 0.25 *H* 사용 하 여 90 값과 동일 `HLStoRGB_TWO`.

##  <a name="hsvtorgb"></a>  CDrawingManager::HSVtoRGB

HSV 표현에서 색을 RGB 표현으로 변환 합니다.

```
static COLORREF __stdcall HSVtoRGB(
    double H,
    double S,
    double V);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*H*|[in] 색에 대 한 색상을 나타내는 0과 360 사이의 수입니다.|
|*S*|[in] 0과 1 사이의 숫자 색 채도 나타냅니다.|
|*V*|[in] 0과 1 사이의 숫자 색에 대 한 값을 나타냅니다.|

### <a name="return-value"></a>반환 값

제공 된 HSV 색의 RGB 표현입니다.

### <a name="remarks"></a>설명

HSV (색상, 채도 및 값), (색상, 채도 및 명도), HSL 또는 RGB (빨강, 녹색 및 파랑) 색을 나타낼 수 있습니다. 색의 다양 한 표현에 대 한 자세한 내용은 참조 하세요. [Color](/windows/desktop/uxguide/vis-color)합니다.

##  <a name="huetorgb"></a>  CDrawingManager::HuetoRGB

빨간색, 녹색 또는 파란색 구성 요소에 색상 값을 변환합니다.

```
static double __stdcall HuetoRGB(
    double m1,
    double m2,
    double h);

static BYTE __stdcall HueToRGB(
    float rm1,
    float rm2,
    float rh);
```

### <a name="parameters"></a>매개 변수

*m1*<br/>
[in] 설명을 참조 하세요.

*m2*<br/>
[in] 설명을 참조 하세요.

*h*<br/>
[in] 설명을 참조 하세요.

*rm1*<br/>
[in] 설명을 참조 하세요.

*rm2*<br/>
[in] 설명을 참조 하세요.

*rh*<br/>
[in] 설명을 참조 하세요.

### <a name="return-value"></a>반환 값

제공 된 색상에 대 한 개별 빨간색, 녹색 또는 파란색 구성 합니다.

### <a name="remarks"></a>설명

이 메서드는 도우미 메서드는는 `CDrawingManager` 클래스 HSV 또는 HSL 표현에 있는 색의 개별 빨강, 녹색 및 파랑 구성 요소를 계산 하는 데 사용 합니다. 이 메서드는 프로그래머에 의해 직접 호출 될 설계 되지는 않았습니다. 입력된 매개 변수는 변환 알고리즘에 의존 하는 값입니다.

HSV 또는 HSL 색을 RGB 표현으로 변환 하려면 다음 방법 중 하나를 호출 합니다.

- [CDrawingManager::HSVtoRGB](#hsvtorgb)

- [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one)

- [CDrawingManager::HLStoRGB_TWO](#hlstorgb_two)

##  <a name="mirrorrect"></a>  CDrawingManager::MirrorRect

사각형 영역을 대칭 이동합니다.

```
void MirrorRect(
    CRect rect,
    BOOL bHorz = TRUE);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
[in] 대칭으로 배열할지 영역의 경계 사각형입니다.

*bHorz*<br/>
[in] 사각형을 가로 또는 세로로 대칭 이동 하는지 여부를 나타내는 부울 매개 변수입니다.

### <a name="remarks"></a>설명

이 메서드는 소유한 장치 컨텍스트의 모든 영역을 전환할 수는 `CDrawingManager` 클래스입니다. 하는 경우 *bHorz* 가 TRUE로 설정 된이 메서드 좌우 대칭 이동 하는 영역입니다. 그렇지 않으면 해당 상하 대칭 이동 영역입니다.

##  <a name="pixelalpha"></a>  CDrawingManager::PixelAlpha

반투명 픽셀의 최종 색을 계산합니다.

```
static COLORREF __stdcall PixelAlpha(
    COLORREF srcPixel,
    int percent);

static COLORREF __stdcall PixelAlpha(
    COLORREF srcPixel,
    double percentR,
    double percentG,
    double percentB);

static COLORREF __stdcall PixelAlpha(
    COLORREF srcPixel,
    COLORREF dstPixel,
    int percent);
```

### <a name="parameters"></a>매개 변수

*srcPixel*<br/>
[in] 픽셀의 초기 색입니다.

*percent*<br/>
[in] 투명도의 백분율을 나타내는 0과 100 사이의 숫자입니다. 값이 100 초기 색이 완전히 투명 하 게 나타냅니다.

*percentR*<br/>
[in] 투명도 빨강 구성 요소에 대 한 백분율을 나타내는 0과 100 사이의 숫자입니다.

*percentG*<br/>
[in] 녹색 구성 요소에 대 한 투명도의 백분율을 나타내는 0과 100 사이의 숫자입니다.

*percentB*<br/>
[in] 파랑 구성 요소에 대 한 투명도의 백분율을 나타내는 0과 100 사이의 숫자입니다.

*dstPixel*<br/>
[in] 픽셀에 대 한 기본 색입니다.

### <a name="return-value"></a>반환 값

반투명 픽셀의 최종 색입니다.

### <a name="remarks"></a>설명

반투명 비트맵 색 지정에 대 한 도우미 클래스 이며 프로그래머가가 직접 호출 하도록 설계 되지 않았습니다.

버전의 있는 메서드를 사용 하는 경우 *dstPixel*, 최종 색의 조합입니다 *dstPixel* 하 고 *srcPixel*합니다. 합니다 *srcPixel* 색은 부분적으로 투명 한 색의 기본 색 위로 *dstPixel*합니다.

##  <a name="prepareshadowmask"></a>  CDrawingManager::PrepareShadowMask

그림자를 사용할 수 있는 비트맵을 만듭니다.

```
static HBITMAP __stdcall PrepareShadowMask (
    int nDepth,
    COLORREF clrBase,
    int iMinBrightness = 0,
    int iMaxBrightness = 100);
```

### <a name="parameters"></a>매개 변수

*nDepth*<br/>
[in] 그림자의 높이 너비입니다.

*clrBase*<br/>
[in] 그림자의 색입니다.

*iMinBrightness*<br/>
[in] 그림자의 최소 밝기입니다.

*iMaxBrightness*<br/>
[in] 그림자의 최대 밝기입니다.

### <a name="return-value"></a>반환 값

이 메서드는 성공 하는 경우 만든된 비트맵에 대 한 핸들 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

하는 경우 *nDepth* 는이 메서드는 0으로 설정 종료 하 고 NULL을 반환 합니다. 하는 경우 *nDepth* 3 보다 작은 경우 그림자의 높이 너비를 3 픽셀로 설정 됩니다.

##  <a name="rgbtohsl"></a>  CDrawingManager::RGBtoHSL

색상, 채도 및 밝기 (HSL) 표현을 색을 빨간색, 녹색 및 파란색 (RGB) 표현에서 변환합니다.

```
static void __stdcall RGBtoHSL(
    COLORREF rgb,
    double* H,
    double* S,
    double* L);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*rgb*|[in] RGB 값의 색입니다.|
|*H*|[out] 메서드는 색의 색상을 저장 하는 위치 하는 double 값을 포인터입니다.|
|*S*|[out] 메서드는 색의 채도 저장 하는 위치 하는 double 값을 포인터입니다.|
|*L*|[out] 메서드는 색의 명도 저장 하는 위치 하는 double 값을 포인터입니다.|

### <a name="remarks"></a>설명

HSV (색상, 채도 및 값), (색상, 채도 및 명도), HSL 또는 RGB (빨강, 녹색 및 파랑) 색을 나타낼 수 있습니다. 색의 다양 한 표현에 대 한 자세한 내용은 참조 하세요. [Color](/windows/desktop/uxguide/vis-color)합니다.

반환된 된 값에 대 한 *H* 0-1 위치 0과 1을 모두 나타내며 빨간색 분수로 표시 됩니다. 반환된 값은 *S* 하 고 *L* 는 0과 1 사이의 숫자입니다.

##  <a name="rgbtohsv"></a>  CDrawingManager::RGBtoHSV

색을 RGB 표현에서을 HSV 표현으로 변환 합니다.

```
static void __stdcall RGBtoHSV(
    COLORREF rgb,
    double* H,
    double* S,
    double* V);
```

### <a name="parameters"></a>매개 변수

*rgb*<br/>
[in] 색 RGB 표현에서 변환입니다.

*H*<br/>
[out] 이 메서드는 색에 대 한 결과 색상을 저장 하는 double 값을 포인터입니다.

*S*<br/>
[out] 이 메서드는 색 채도 결과 저장 하는 double 값을 포인터입니다.

*V*<br/>
[out] 이 메서드는 색에 대 한 결과 값을 저장 하는 위치 하는 double 값을 포인터입니다.

### <a name="remarks"></a>설명

HSV (색상, 채도 및 값), (색상, 채도 및 명도), HSL 또는 RGB (빨강, 녹색 및 파랑) 색을 나타낼 수 있습니다. 색의 다양 한 표현에 대 한 자세한 내용은 참조 하세요. [Color](/windows/desktop/uxguide/vis-color)합니다.

반환된 된 값에 대 한 *H* 는 0과 360 사이의 숫자 0과 360 모두 여기서 red를 나타냅니다. 반환 값 *S* 하 고 *V* 는 0과 1 사이의 숫자입니다.

##  <a name="setalphapixel"></a>  CDrawingManager::SetAlphaPixel

비트맵에서 투명 한 픽셀을 색입니다.

```
static void __stdcall SetAlphaPixel(
    COLORREF* pBits,
    CRect rect,
    int x,
    int y,
    int percent,
    int iShadowSize,
    COLORREF clrBase = (COLORREF)-1,
    BOOL bIsRight = TRUE);
```

### <a name="parameters"></a>매개 변수

*pBits*<br/>
[in] 비트맵 비트 값 포인터입니다.

*rect*<br/>
[in] 응용 프로그램에서 사각형 영역입니다. 그리기 관리자는이 영역의 오른쪽 및 아래에 있는 그림자를 그립니다.

*x*<br/>
[in] 픽셀 색에 가로 좌표입니다.

*y*<br/>
[in] 색 픽셀에 세로 좌표입니다.

*percent*<br/>
[in] 백분율 투명도입니다.

*iShadowSize*<br/>
[in] 그림자의 높이 너비입니다.

*clrBase*<br/>
[in] 그림자의 색입니다.

*bIsRight*<br/>
[in] 픽셀 색을 나타내는 부울 매개 변수입니다. 자세한 내용은 설명 부분을 참조하세요.

### <a name="remarks"></a>설명

이 메서드는 사용 되는 도우미 메서드를 [CDrawingManager::DrawShadow](#drawshadow) 메서드. 그림자를 그릴 경우 호출 하는 것이 좋습니다 `CDrawingManager::DrawShadow` 대신 합니다.

하는 경우 *bIsRight* 가 TRUE로 설정 된 색상을 픽셀 측정 됩니다 *x* 의 오른쪽 가장자리에서 픽셀 *rect*합니다. FALSE 인 경우 픽셀 색을 측정 *x* 의 왼쪽된 가장자리에서 픽셀 *rect*합니다.

##  <a name="setpixel"></a>  CDrawingManager::SetPixel

단일 픽셀 비트맵의 지정된 된 색을 변경합니다.

```
static void __stdcall SetPixel(
    COLORREF* pBits,
    int cx,
    int cy,
    int x,
    int y,
    COLORREF color);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*pBits*|[in] 비트맵의 비트 값 포인터입니다.|
|*cx*|[in] 비트맵의 총 너비입니다.|
|*cy*|[in] 비트맵의 전체 높이입니다.|
|*x*|[in] 변경 비트맵의 픽셀의 x 좌표입니다.|
|*y*|[in] 변경 비트맵의 픽셀의 y 좌표입니다.|
|*color*|[in] 제공 된 좌표에서 식별 된 픽셀에 대 한 새 색입니다.|

##  <a name="smartmixcolors"></a>  CDrawingManager::SmartMixColors

가중치가 적용 된 비율에 따라 두 가지 색을 결합 합니다.

```
static COLORREF __stdcall SmartMixColors(
    COLORREF color1,
    COLORREF color2,
    double dblLumRatio = 1.,
    int k1 = 1,
    int k2 = 1);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*color1*|[in] 첫 번째 색 혼합입니다.|
|*color2*|[in] 두 번째 색 혼합입니다.|
|*dblLumRatio*|[in] 새 색의 명도 비율입니다. `SmartMixColors` 최종 색을 결정 하기 전에이 비율에 따라 혼합된 색의 명도 곱합니다.|
|*k1*|[in] 첫 번째 색에 대 한 가중치가 적용 된 비율입니다.|
|*k2*|[in] 두 번째 색에 대 한 가중치가 적용 된 비율입니다.|

### <a name="return-value"></a>반환 값

제공 된 색의 가중치가 적용 된 혼합을 나타내는 색입니다.

### <a name="remarks"></a>설명

오류가 있는 경우이 메서드는 실패 *k1* 하거나 *k2* 가 0 보다 작습니다. 메서드가 반환 하는 경우 0으로 설정 되어 이러한 매개 변수 모두를 `RGB(0, 0, 0)`입니다.

가중치가 적용 된 비율을 다음 수식으로 계산 됩니다. (color1 \* k1 + color2 \* k2) /(k1 + k2) 합니다. 가중치가 적용 된 비율을 결정 메서드 혼합된 색의 광도 계산 합니다. 곱합니다 여 명도 *dblLumRatio*합니다. 값 1.0 보다 큰 경우 메서드는 혼합된 색의 명도 새 값으로 설정 합니다. 그렇지 않으면 명도 1.0으로 설정 됩니다.

##  <a name="drawrotated"></a>  CDrawingManager::DrawRotated

지정된 된 사각형 내에서 DC 콘텐츠 원본으로 90도 회전 합니다.

```
void DrawRotated(
    CRect rectDest,
    CDC& dcSrc,
    BOOL bClockWise);
```

### <a name="parameters"></a>매개 변수

*rectDest*<br/>
대상 사각형입니다.

*dcSrc*<br/>
원본 장치 컨텍스트입니다.

*bClockWise*<br/>
TRUE 이면 + 90도 회전 합니다. FALSE-90도 회전을 나타냅니다.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)
