---
title: CMFCToolTipInfo 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCToolTipInfo
- AFXTOOLTIPCTRL/CMFCToolTipInfo
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bBalloonTooltip
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bBoldLabel
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bDrawDescription
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bDrawIcon
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bDrawSeparator
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bRoundedCorners
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bVislManagerTheme
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrBorder
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrFill
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrFillGradient
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrText
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_nGradientAngle
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_nMaxDescrWidth
helpviewer_keywords:
- CMFCToolTipInfo [MFC], m_bBalloonTooltip
- CMFCToolTipInfo [MFC], m_bBoldLabel
- CMFCToolTipInfo [MFC], m_bDrawDescription
- CMFCToolTipInfo [MFC], m_bDrawIcon
- CMFCToolTipInfo [MFC], m_bDrawSeparator
- CMFCToolTipInfo [MFC], m_bRoundedCorners
- CMFCToolTipInfo [MFC], m_bVislManagerTheme
- CMFCToolTipInfo [MFC], m_clrBorder
- CMFCToolTipInfo [MFC], m_clrFill
- CMFCToolTipInfo [MFC], m_clrFillGradient
- CMFCToolTipInfo [MFC], m_clrText
- CMFCToolTipInfo [MFC], m_nGradientAngle
- CMFCToolTipInfo [MFC], m_nMaxDescrWidth
ms.assetid: f9d3d7f8-1f08-4342-a7b2-683860e5d2a5
ms.openlocfilehash: b38c3a62cca376ef7a19a111fe3a34c923983d1b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62338222"
---
# <a name="cmfctooltipinfo-class"></a>CMFCToolTipInfo 클래스

도구 설명의 시각적 모양에 대한 정보를 저장합니다.

## <a name="syntax"></a>구문

```
class CMFCToolTipInfo
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMFCToolTipInfo::operator=](#operator_eq)||

### <a name="data-members"></a>데이터 멤버

|이름|설명|
|----------|-----------------|
|[CMFCToolTipInfo::m_bBalloonTooltip](#m_bballoontooltip)|도구 설명이 풍선 모양인지 여부를 나타내는 부울 변수입니다.|
|[CMFCToolTipInfo::m_bBoldLabel](#m_bboldlabel)|도구 설명 레이블이 굵은 글꼴로 표시되는지 여부를 나타내는 부울 변수입니다.|
|[CMFCToolTipInfo::m_bDrawDescription](#m_bdrawdescription)|도구 설명이 설명을 포함하는지 여부를 나타내는 부울 변수입니다.|
|[CMFCToolTipInfo::m_bDrawIcon](#m_bdrawicon)|도구 설명이 아이콘을 포함하는지 여부를 나타내는 부울 변수입니다.|
|[CMFCToolTipInfo::m_bDrawSeparator](#m_bdrawseparator)|도구 설명 레이블과 도구 설명 사이에 구분 기호가 표시되는지 여부를 나타내는 부울 변수입니다.|
|[CMFCToolTipInfo::m_bRoundedCorners](#m_broundedcorners)|도구 설명 모서리가 둥근지 여부를 나타내는 부울 변수입니다.|
|[CMFCToolTipInfo::m_bVislManagerTheme](#m_bvislmanagertheme)|시각화 관리자에서 도구 설명의 모양을 제어 해야 하는지 여부를 나타내는 부울 변수 (참조 [CMFCVisualManager 클래스](../../mfc/reference/cmfcvisualmanager-class.md)).|
|[CMFCToolTipInfo::m_clrBorder](#m_clrborder)|도구 설명 테두리 색입니다.|
|[CMFCToolTipInfo::m_clrFill](#m_clrfill)|도구 설명 배경색입니다.|
|[CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient)|도구 설명의 그라데이션 채우기 색입니다.|
|[CMFCToolTipInfo::m_clrText](#m_clrtext)|도구 설명의 텍스트 색입니다.|
|[CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle)|도구 설명의 그라데이션 채우기 각도입니다.|
|[CMFCToolTipInfo::m_nMaxDescrWidth](#m_nmaxdescrwidth)|도구 설명의 가능한 최대 설명 너비(픽셀)입니다.|

## <a name="remarks"></a>설명

사용 하 여 [CMFCToolTipCtrl 클래스](../../mfc/reference/cmfctooltipctrl-class.md)하십시오 `CMFCToolTipInfo`, 및 [CTooltipManager 클래스](../../mfc/reference/ctooltipmanager-class.md) 응용 프로그램에서 사용자 지정된 도구 설명을 구현 하 합니다. 이러한 도구 설명 클래스를 사용 하는 방법의 예제를 참조 합니다 [CMFCToolTipCtrl 클래스](../../mfc/reference/cmfctooltipctrl-class.md) 항목입니다.

## <a name="example"></a>예제

다음 예제에서는 `CMFCToolTipInfo` 클래스에서 다양한 멤버 변수의 값을 설정하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFC_RibbonApp#42](../../mfc/reference/codesnippet/cpp/cmfctooltipinfo-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxtooltipctrl.h

##  <a name="m_bballoontooltip"></a>  CMFCToolTipInfo::m_bBalloonTooltip

모든 도구 설명의 표시 스타일을 지정 합니다.

```
BOOL m_bBalloonTooltip;
```

### <a name="remarks"></a>설명

TRUE 도구 설명이 풍선 스타일을 사용 하는 FALSE를 나타내고, 나타냅니다 사각형 스타일을 사용 하는 도구 설명 합니다.

##  <a name="m_bboldlabel"></a>  CMFCToolTipInfo::m_bBoldLabel

도구 설명 텍스트의 글꼴을 굵게 여부를 지정 합니다.

```
BOOL m_bBoldLabel;
```

### <a name="remarks"></a>설명

이 멤버를 표시 도구 설명 텍스트에 굵게, FALSE 또는 true로 설정 하면 도구 설명 레이블이 굵은 글꼴이 아닌 글꼴을 사용 하 여 표시를 설정 합니다.

##  <a name="m_bdrawdescription"></a>  CMFCToolTipInfo::m_bDrawDescription

각 도구 설명 설명 텍스트를 표시 하는지 여부를 지정 합니다.

```
BOOL m_bDrawDescription;
```

### <a name="remarks"></a>설명

설명, 표시 또는 설명을 숨기려면 FALSE는 true로 설정 하면이 멤버를 설정 합니다. 호출 하 여 도구 설명에는 설명을 지정할 수 있습니다 [CMFCToolTipCtrl::SetDescription](../../mfc/reference/cmfctooltipctrl-class.md#setdescription)

##  <a name="m_bdrawicon"></a>  CMFCToolTipInfo::m_bDrawIcon

모든 도구 설명 아이콘을 표시 하는지 여부를 지정 합니다.

```
BOOL m_bDrawIcon;
```

### <a name="remarks"></a>설명

각 도구 설명에 아이콘을 표시 하려면 TRUE 또는 FALSE 아이콘이 없는 도구 설명을 표시 하려면이 멤버를 설정 합니다.

##  <a name="m_bdrawseparator"></a>  CMFCToolTipInfo::m_bDrawSeparator

각 도구 설명의 레이블과 설명을 사이 구분 기호에 있는지 여부를 지정 합니다.

```
BOOL m_bDrawSeparator;
```

### <a name="remarks"></a>설명

도구 설명의 레이블과 설명 사이 구분 기호를 표시 하려면 TRUE 또는 FALSE 없습니다 구분 기호를 사용 하 여 도구 설명을 표시 하려면이 멤버를 설정 합니다.

##  <a name="m_broundedcorners"></a>  CMFCToolTipInfo::m_bRoundedCorners

모든 도구 설명 모서리가 둥근가 있는지 여부를 지정 합니다.

```
BOOL m_bRoundedCorners;
```

### <a name="remarks"></a>설명

이 멤버를 표시 둥근 모서리 FALSE 또는 도구 설명에 true로 설정 하면 도구 설명에 사각형 모서리를 표시할를 설정 합니다.

##  <a name="m_clrborder"></a>  CMFCToolTipInfo::m_clrBorder

모든 도구 설명에는 테두리의 색을 지정합니다.

```
COLORREF m_clrBorder;
```

##  <a name="m_clrfill"></a>  CMFCToolTipInfo::m_clrFill

도구 설명 배경의 색을 지정합니다.

```
COLORREF m_clrFill;
```

### <a name="remarks"></a>설명

하는 경우 [CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient) 가-1 이면 도구 설명 배경색은 `m_clrFill`합니다. 그렇지 않으면 `m_clrFill` 그라데이션의 시작 색을 지정 하 고 `m_clrFillGradient` 그라데이션의 끝 색을 지정 합니다. [CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle) 그라데이션의 방향을 결정 합니다.

##  <a name="m_clrfillgradient"></a>  CMFCToolTipInfo::m_clrFillGradient

도구 설명에 배경에 그라데이션 효과 대 한 끝 색을 지정합니다.

```
COLORREF m_clrFillGradient;
```

### <a name="remarks"></a>설명

경우 `m_clrFillGradient` 가-1 이면는 그라데이션 없음. 그라데이션 초기 색은에서 지정 하는 고, 그렇지 [CMFCToolTipInfo::m_clrFill](#m_clrfill) 그라데이션 마침 색으로 지정 됩니다 `m_clrFillGradient`합니다. [CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle) 그라데이션의 방향을 결정 합니다.

##  <a name="m_clrtext"></a>  CMFCToolTipInfo::m_clrText

모든 도구 설명의 텍스트 색을 지정합니다.

```
COLORREF m_clrText;
```

##  <a name="m_ngradientangle"></a>  CMFCToolTipInfo::m_nGradientAngle

도구 설명의 배경에 그라데이션을 그릴 각도 지정 합니다.

```
int m_nGradientAngle;
```

### <a name="remarks"></a>설명

`m_nGradientAngle` 각도 (도)를 도구 설명의 배경에 그라데이션 가로에서 오프셋 되는 각도 지정 합니다. 경우 `m_nGradientAngle` 0 인 그라데이션의 왼쪽에서 오른쪽에 그려집니다. 경우 `m_nGradientAngle` 은 1과 360 사이의 그라데이션 회전 시계 방향으로도 해당 숫자입니다. 경우 `m_nGradientAngle` 은-1로, 기본 값이 그라데이션의 위에서 맨 아래에 그려집니다. 이 설정과 동일 `m_nGradientAngle` 90으로 합니다.

[CMFCToolTipInfo::m_clrFill](#m_clrfill) `clrFill` 그라데이션의 시작 색을 지정 하 고 [CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient) `clrFillGradient` 그라데이션의 끝 색을 지정 합니다. 경우 `m_clrFillGradient` 가-1 이면는 그라데이션 없음.

##  <a name="m_nmaxdescrwidth"></a>  CMFCToolTipInfo::m_nMaxDescrWidth

각 도구 설명에 표시 하는 설명의 최대 너비를 지정 합니다. 설명 너비를 지정된 된 값을 초과 하면 텍스트가 래핑됩니다.

```
int m_nMaxDescrWidth;
```

##  <a name="m_bvislmanagertheme"></a>  CMFCToolTipInfo::m_bVislManagerTheme

비주얼 관리자 응용 프로그램의 모든 도구 설명의 모양을 제어 하는지 여부를 지정 합니다.

```
BOOL m_bVislManagerTheme;
```

### <a name="remarks"></a>설명

하는 경우 `m_bVislManagerTheme` 가 TRUE 인 모든 도구 설명 새 요청 [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md) 화면에 표시 하 고 모양을 결정 하는 개체의 값을 사용 하려면 먼저 응용 프로그램의 비주얼 관리자에서. 다른 멤버에 [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md) 무시 됩니다.

##  <a name="operator_eq"></a>  CMFCToolTipInfo::operator=

더 자세한 내용은 Visual Studio 설치의 **VC\\atlmfc\\src\\mfc** 폴더에 있는 소스 코드를 참조하세요.

```
CMFCToolTipInfo& operator=(CMFCToolTipInfo& src);
```

### <a name="parameters"></a>매개 변수

[in] *src*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CTooltipManager 클래스](../../mfc/reference/ctooltipmanager-class.md)<br/>
[CMFCToolTipCtrl 클래스](../../mfc/reference/cmfctooltipctrl-class.md)
