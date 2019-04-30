---
title: CMFCToolTipCtrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCToolTipCtrl
- AFXTOOLTIPCTRL/CMFCToolTipCtrl
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::GetIconSize
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::GetParams
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawBorder
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawDescription
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawIcon
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawLabel
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawSeparator
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnFillBackground
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetDescription
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetFixedWidth
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetHotRibbonButton
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetLocation
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetParams
helpviewer_keywords:
- CMFCToolTipCtrl [MFC], GetIconSize
- CMFCToolTipCtrl [MFC], GetParams
- CMFCToolTipCtrl [MFC], OnDrawBorder
- CMFCToolTipCtrl [MFC], OnDrawDescription
- CMFCToolTipCtrl [MFC], OnDrawIcon
- CMFCToolTipCtrl [MFC], OnDrawLabel
- CMFCToolTipCtrl [MFC], OnDrawSeparator
- CMFCToolTipCtrl [MFC], OnFillBackground
- CMFCToolTipCtrl [MFC], SetDescription
- CMFCToolTipCtrl [MFC], SetFixedWidth
- CMFCToolTipCtrl [MFC], SetHotRibbonButton
- CMFCToolTipCtrl [MFC], SetLocation
- CMFCToolTipCtrl [MFC], SetParams
ms.assetid: 9fbfcfb1-a8ab-417f-ae29-9a9ca85ee58f
ms.openlocfilehash: aaf9d9570906b7886d8ec78575c39db5d62099f7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388308"
---
# <a name="cmfctooltipctrl-class"></a>CMFCToolTipCtrl 클래스

[CToolTipCtrl Class](../../mfc/reference/ctooltipctrl-class.md)를 기반으로 하는 확장된 도구 설명 구현입니다. `CMFCToolTipCtrl` 클래스 기반의 도구 설명은 아이콘, 레이블 및 설명을 표시할 수 있습니다. 그라데이션 채우기, 사용자 지정 텍스트와 테두리 색, 굵은 텍스트, 둥근 모서리 또는 풍선 스타일을 사용하여 시각적인 모양을 사용자 지정할 수 있습니다.

더 자세한 내용은 Visual Studio 설치의 **VC\\atlmfc\\src\\mfc** 폴더에 있는 소스 코드를 참조하세요.

## <a name="syntax"></a>구문

```
class CMFCToolTipCtrl : public CToolTipCtrl
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|`CMFCToolTipCtrl::CMFCToolTipCtrl`|기본 생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMFCToolTipCtrl::GetIconSize](#geticonsize)|도구 설명에 아이콘 크기를 반환합니다.|
|[CMFCToolTipCtrl::GetParams](#getparams)|도구 설명의 표시 설정을 반환합니다.|
|[CMFCToolTipCtrl::OnDrawBorder](#ondrawborder)|도구 설명의 테두리를 그립니다.|
|[CMFCToolTipCtrl::OnDrawDescription](#ondrawdescription)||
|[CMFCToolTipCtrl::OnDrawIcon](#ondrawicon)|도구 설명에 아이콘을 표시합니다.|
|[CMFCToolTipCtrl::OnDrawLabel](#ondrawlabel)|도구 설명의 레이블을 그리거나 레이블의 크기를 계산합니다.|
|[CMFCToolTipCtrl::OnDrawSeparator](#ondrawseparator)|도구 설명에서 레이블과 설명 사이에 구분 기호를 그립니다.|
|[CMFCToolTipCtrl::OnFillBackground](#onfillbackground)|도구 설명 배경을 채웁니다.|
|[CMFCToolTipCtrl::SetDescription](#setdescription)|도구 설명에 표시할 설명을 설정합니다.|
|[CMFCToolTipCtrl::SetFixedWidth](#setfixedwidth)||
|[CMFCToolTipCtrl::SetHotRibbonButton](#sethotribbonbutton)||
|[CMFCToolTipCtrl::SetLocation](#setlocation)||
|[CMFCToolTipCtrl::SetParams](#setparams)|`CMFCToolTipInfo` 개체를 사용하여 도구 설명의 시각적 모양을 지정합니다.|

## <a name="remarks"></a>설명

사용 하 여 `CMFCToolTipCtrl`, `CMFCToolTipInfo`, 및 [CTooltipManager 클래스](../../mfc/reference/ctooltipmanager-class.md) 응용 프로그램에서 사용자 지정된 도구 설명을 구현 하는 개체입니다.

예를 들어 풍선 스타일의 도구 설명을 사용하려면 다음 단계를 수행합니다.

1. 사용 된 [CWinAppEx 클래스](../../mfc/reference/cwinappex-class.md) 응용 프로그램에서 도구 설명 관리자를 초기화 하는 방법입니다.

2. `CMFCToolTipInfo` 구조체를 만들어 원하는 시각적 스타일을 지정합니다.

```
CMFCToolTipInfo params;
    params.m_bBoldLabel = FALSE;
    params.m_bDrawDescription = FALSE;
    params.m_bDrawIcon = FALSE;
    params.m_bRoundedCorners = TRUE;
    params.m_bDrawSeparator = FALSE;
    if (m_bCustomColors)
{
    params.m_clrFill = RGB (255,
    255,
    255);

    params.m_clrFillGradient = RGB (228,
    228,
    240);

    params.m_clrText = RGB (61,
    83,
    80);

    params.m_clrBorder = RGB (144,
    149,
    168);

}
```
3. 사용 된 [ctooltipmanager:: Settooltipparams](../../mfc/reference/ctooltipmanager-class.md#settooltipparams) 에 정의 된 스타일을 사용 하 여 응용 프로그램에서 모든 도구 설명에 대 한 시각적 스타일을 설정 하는 방법의 `CMFCToolTipInfo` 개체:

```
theApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,
    RUNTIME_CLASS (CMFCToolTipCtrl), &params);
```
`CMFCToolTipCtrl`에서 새 클래스를 파생시켜 도구 설명 동작과 렌더링을 제어할 수도 있습니다. 새 도구 설명 컨트롤 클래스를 지정하려면 `CTooltipManager::SetTooltipParams` 메서드를 사용합니다.

```
myApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,
    RUNTIME_CLASS (CMyToolTipCtrl))
```
기본 도구 설명 컨트롤 클래스를 복원하고 도구 설명 모양을 기본 상태로 다시 설정하려면 `SetTooltipParams`의 런타임 클래스 및 도구 설명 정보 매개 변수에 NULL을 지정합니다.

```
theApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,
    NULL,
    NULL);
```

## <a name="example"></a>예제

다음 예제에서는 `CMFCToolTipCtrl` 개체를 생성하고, 도구 설명에 표시되는 설명을 설정하고, 도구 설명 컨트롤의 너비를 설정하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFC_RibbonApp#41](../../mfc/reference/codesnippet/cpp/cmfctooltipctrl-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md)

[CMFCToolTipCtrl](../../mfc/reference/cmfctooltipctrl-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxtooltipctrl.h

##  <a name="cmfctooltipctrl"></a>  CMFCToolTipCtrl::CMFCToolTipCtrl

```
CMFCToolTipCtrl(CMFCToolTipInfo* pParams = NULL);
```

### <a name="parameters"></a>매개 변수

[in] *pParams*<br/>

### <a name="remarks"></a>설명

##  <a name="geticonsize"></a>  CMFCToolTipCtrl::GetIconSize

도구 설명에 아이콘 크기를 반환합니다.

```
virtual CSize GetIconSize();
```

### <a name="return-value"></a>반환 값

픽셀에서 아이콘의 크기입니다.

##  <a name="getparams"></a>  CMFCToolTipCtrl::GetParams

도구 설명의 표시 설정을 반환합니다.

```
const CMFCToolTipInfo& GetParams() const;
```

### <a name="return-value"></a>반환 값

에 저장 되는 현재 도구 설명 표시 설정 된 [CMFCToolTipInfo 클래스](../../mfc/reference/cmfctooltipinfo-class.md) 개체입니다.

##  <a name="ondrawborder"></a>  CMFCToolTipCtrl::OnDrawBorder

도구 설명의 테두리를 그립니다.

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect rect,
    COLORREF clrLine);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 장치 컨텍스트에 대 한 포인터입니다.

*rect*<br/>
[in] 도구 설명의 경계 사각형입니다.

*clrLine*<br/>
[in] 테두리 색입니다.

### <a name="remarks"></a>설명

도구 설명 테두리의 모양을 사용자 지정 파생된 클래스에서이 메서드를 재정의 합니다.

##  <a name="ondrawdescription"></a>  CMFCToolTipCtrl::OnDrawDescription

```
virtual CSize OnDrawDescription(
    CDC* pDC,
    CRect rect,
    BOOL bCalcOnly);
```

### <a name="parameters"></a>매개 변수

[in] *pDC*<br/>
[in] *rect*<br/>
[in] *bCalcOnly*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="ondrawicon"></a>  CMFCToolTipCtrl::OnDrawIcon

도구 설명에 아이콘을 표시합니다.

```
virtual BOOL OnDrawIcon(
    CDC* pDC,
    CRect rectImage);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 장치 컨텍스트에 대 한 포인터입니다.

*rectImage*<br/>
[in] 아이콘의 좌표입니다.

### <a name="return-value"></a>반환 값

아이콘을 그린 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

사용자 지정 아이콘을 표시 하려면 파생된 클래스에서이 메서드를 재정의 합니다. 재정의 해야 [CMFCToolTipCtrl::GetIconSize](#geticonsize) 도구 설명 텍스트 및 설명의 레이아웃을 올바르게 계산에 사용할 수 있도록 합니다.

##  <a name="ondrawlabel"></a>  CMFCToolTipCtrl::OnDrawLabel

도구 설명의 레이블을 그리거나 레이블의 크기를 계산합니다.

```
virtual CSize OnDrawLabel(
    CDC* pDC,
    CRect rect,
    BOOL bCalcOnly);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 장치 컨텍스트에 대 한 포인터입니다.

*rect*<br/>
[in] 레이블 영역의 경계 사각형입니다.

*bCalcOnly*<br/>
[in] True 이면 레이블을 그려지지 않습니다.

### <a name="return-value"></a>반환 값

픽셀에서 레이블의 크기입니다.

### <a name="remarks"></a>설명

도구 설명 레이블의 모양을 사용자 지정 하려는 경우에 파생된 클래스에서이 메서드를 재정의 합니다.

##  <a name="ondrawseparator"></a>  CMFCToolTipCtrl::OnDrawSeparator

도구 설명에서 레이블과 설명 사이에 구분 기호를 그립니다.

```
virtual void OnDrawSeparator(
    CDC* pDC,
    int x1,
    int x2,
    int y);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 장치 컨텍스트에 대 한 포인터입니다.

*x1*<br/>
[in] 가로 좌표 구분선의 왼쪽된 끝입니다.

*x2*<br/>
[in] 가로 좌표는 오른쪽 끝 구분 기호입니다.

*Y*<br/>
[in] 세로 좌표는 구분 기호입니다.

### <a name="remarks"></a>설명

기본 구현은 지점에서 하는 선을 그려 (x1, y) 지점 (x2, y).

구분 기호의 표시를 사용자 지정 파생된 클래스에서이 메서드를 재정의 합니다.

##  <a name="onfillbackground"></a>  CMFCToolTipCtrl::OnFillBackground

도구 설명 배경을 채웁니다.

```
virtual void OnFillBackground(
    CDC* pDC,
    CRect rect,
    COLORREF& clrText,
    COLORREF& clrLine);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
[in] 장치 컨텍스트에 대 한 포인터입니다.

*rect*<br/>
[in] 채울 영역을의 경계 사각형을 지정 합니다.

*clrText*<br/>
[in] 도구 설명 전경색입니다.

*clrLine*<br/>
[in] 레이블 및 설명 간의 구분 기호 선과 테두리의 색입니다.

### <a name="remarks"></a>설명

기본 구현으로 지정 된 사각형이 채워집니다 *rect* 색 또는 가장 최근 호출에 의해 지정 된 패턴을 사용 하 여 [CMFCToolTipCtrl::SetParams](#setparams)합니다.

도구 설명의 모양을 사용자 지정 하려는 경우에 파생된 클래스에서이 메서드를 재정의 합니다.

##  <a name="setdescription"></a>  CMFCToolTipCtrl::SetDescription

도구 설명에 표시할 설명을 설정합니다.

```
virtual void SetDescription(const CString strDesrciption);
```

### <a name="parameters"></a>매개 변수

*strDesrciption*<br/>
[in] 설명 텍스트입니다.

### <a name="remarks"></a>설명

설명 텍스트는 구분 기호에서 도구 설명에 표시 됩니다.

##  <a name="setfixedwidth"></a>  CMFCToolTipCtrl::SetFixedWidth

```
void SetFixedWidth(
    int nWidthRegular,
    int nWidthLargeImage);
```

### <a name="parameters"></a>매개 변수

[in] *nWidthRegular*<br/>
[in] *nWidthLargeImage*<br/>

### <a name="remarks"></a>설명

##  <a name="sethotribbonbutton"></a>  CMFCToolTipCtrl::SetHotRibbonButton

```
void SetHotRibbonButton(CMFCRibbonButton* pRibbonButton);
```

### <a name="parameters"></a>매개 변수

[in] *pRibbonButton*<br/>

### <a name="remarks"></a>설명

##  <a name="setlocation"></a>  CMFCToolTipCtrl::SetLocation

```
void SetLocation(CPoint pt);
```

### <a name="parameters"></a>매개 변수

[in] *pt*<br/>

### <a name="remarks"></a>설명

##  <a name="setparams"></a>  CMFCToolTipCtrl::SetParams

도구 설명의 시각적 모양을 사용 하 여 지정 된 [CMFCToolTipInfo 클래스](../../mfc/reference/cmfctooltipinfo-class.md) 개체입니다.

```
void SetParams(CMFCToolTipInfo* pParams);
```

### <a name="parameters"></a>매개 변수

*pParams*<br/>
[in] 에 대 한 포인터를 [CMFCToolTipInfo 클래스](../../mfc/reference/cmfctooltipinfo-class.md) 표시 매개 변수를 포함 하는 개체입니다.

### <a name="remarks"></a>설명

도구 설명이 표시 됩니다, 색을 사용 하 여 그리기는 비주얼 스타일을 때마다 *pParams* 지정 합니다. 변수의 *pParams* 보호 된 멤버에 저장 됩니다 `m_Params`를 재정의 하는 파생된 클래스에서 액세스할 수 있는 [CMFCToolTipCtrl::OnDrawBorder](#ondrawborder), [CMFCToolTipCtrl: : OnDrawIcon](#ondrawicon)하십시오 [CMFCToolTipCtrl::OnDrawLabel](#ondrawlabel)를 [CMFCToolTipCtrl::OnDrawSeparator](#ondrawseparator), 또는 [CMFCToolTipCtrl::OnFillBackground](#onfillbackground)지정 된 모양을 유지할 수 있습니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CToolTipCtrl Class](../../mfc/reference/ctooltipctrl-class.md)<br/>
[CTooltipManager 클래스](../../mfc/reference/ctooltipmanager-class.md)<br/>
[CMFCToolTipInfo 클래스](../../mfc/reference/cmfctooltipinfo-class.md)<br/>
[CWinAppEx 클래스](../../mfc/reference/cwinappex-class.md)
