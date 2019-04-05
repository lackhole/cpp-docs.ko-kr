---
title: CMFCRibbonProgressBar 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetPos
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRangeMax
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRangeMin
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRegularSize
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::IsInfiniteMode
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::OnDraw
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetInfiniteMode
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetPos
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetRange
helpviewer_keywords:
- CMFCRibbonProgressBar [MFC], CMFCRibbonProgressBar
- CMFCRibbonProgressBar [MFC], GetPos
- CMFCRibbonProgressBar [MFC], GetRangeMax
- CMFCRibbonProgressBar [MFC], GetRangeMin
- CMFCRibbonProgressBar [MFC], GetRegularSize
- CMFCRibbonProgressBar [MFC], IsInfiniteMode
- CMFCRibbonProgressBar [MFC], OnDraw
- CMFCRibbonProgressBar [MFC], SetInfiniteMode
- CMFCRibbonProgressBar [MFC], SetPos
- CMFCRibbonProgressBar [MFC], SetRange
ms.assetid: de3d9f2e-ed59-480e-aa7d-08a33ab36c67
ms.openlocfilehash: 7c16217378cb8825ca4605687770de177e720c1d
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58778171"
---
# <a name="cmfcribbonprogressbar-class"></a>CMFCRibbonProgressBar 클래스

긴 작업의 진행률을 시각적으로 나타내는 컨트롤을 구현합니다.

## <a name="syntax"></a>구문

```
class CMFCRibbonProgressBar : public CMFCRibbonBaseElement
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMFCRibbonProgressBar::CMFCRibbonProgressBar](#cmfcribbonprogressbar)|`CMFCRibbonProgressBar` 개체를 생성하고 초기화합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CMFCRibbonProgressBar::GetPos](#getpos)|현재 진행 상태를 반환합니다.|
|[CMFCRibbonProgressBar::GetRangeMax](#getrangemax)|현재 범위의 최대값을 반환합니다.|
|[CMFCRibbonProgressBar::GetRangeMin](#getrangemin)|현재 범위의 최소값을 반환합니다.|
|[CMFCRibbonProgressBar::GetRegularSize](#getregularsize)|리본 요소의 보통 크기를 반환합니다. (재정의 [cmfcribbonbaseelement:: Getregularsize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|
|[CMFCRibbonProgressBar::IsInfiniteMode](#isinfinitemode)|진행률 표시줄 무한 모드에서 작동 하는지 여부를 지정 합니다.|
|[CMFCRibbonProgressBar::OnDraw](#ondraw)|리본 요소를 그리기 위해 프레임워크에서 호출됩니다. (재정의 [cmfcribbonbaseelement:: Ondraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw).)|
|[CMFCRibbonProgressBar::SetInfiniteMode](#setinfinitemode)|진행률 표시줄 무한 모드로 작동 하도록 설정 합니다.|
|[CMFCRibbonProgressBar::SetPos](#setpos)|현재 진행 상태를 설정합니다.|
|[CMFCRibbonProgressBar::SetRange](#setrange)|최소 및 최대 값을 설정 합니다.|

## <a name="remarks"></a>설명

`CMFCRibbonProgressBar` 두 가지 모드로 작동할 수 있습니다: 일반 및 무한 합니다. 일반 모드에서 진행률 표시줄 왼쪽에서 오른쪽 채워지고 최 댓 값에 도달 하면 중지 됩니다. 무한 모드로 진행률 표시줄은 반복적으로 최소값에서 최 댓 값에 입력 됩니다. 작업이 진행 중에 있지만 완료 시간 알려지지 않은 무한 모드를 사용할 수 있습니다.

## <a name="example"></a>예제

다음 예제에서는 `CMFCRibbonProgressBar` 클래스에서 다양한 메서드를 사용하는 방법을 보여 줍니다. 이 예제에서는 진행률 표시줄에 대 한 최소 및 최대 값을 설정 하 고 진행률 표시줄의 현재 위치를 설정 모드로 작동 하도록 무한 (여기서는 작업의 완료에 알려지지 않은), 진행률 표시줄 설정 방법을 보여 줍니다. 이 코드 조각은의 일부인 합니다 [MS Office 2007 데모 샘플](../../overview/visual-cpp-samples.md)합니다.

[!code-cpp[NVC_MFC_MSOffice2007Demo#11](../../mfc/reference/codesnippet/cpp/cmfcribbonprogressbar-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxRibbonProgressBar.h

##  <a name="cmfcribbonprogressbar"></a>  CMFCRibbonProgressBar::CMFCRibbonProgressBar

생성 하 고 초기화 된 [CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md) 개체입니다.

```
CMFCRibbonProgressBar();

CMFCRibbonProgressBar(
    UINT nID,
    int nWidth = 90,
    int nHeight = 22);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
[in] 리본 진행률 표시줄에 대 한 명령 ID를 지정합니다.

*nWidth*<br/>
[in] 리본 진행률 표시줄의 픽셀에서 너비를 지정 합니다.

*nHeight*<br/>
[in] 리본 진행률 표시줄의 픽셀에서 높이 지정합니다.

##  <a name="getpos"></a>  CMFCRibbonProgressBar::GetPos

진행률 표시줄의 현재 위치를 반환 합니다.

```
int GetPos () const;
```

### <a name="return-value"></a>반환 값

진행률 표시줄의 현재 위치를 나타내는 값입니다.

### <a name="remarks"></a>설명

설정 범위에서 지정 된 범위 내에 있어야 합니다.는 [CMFCRibbonProgressBar::SetRange](#setrange) 메서드.

##  <a name="getrangemax"></a>  CMFCRibbonProgressBar::GetRangeMax

진행률 표시줄의 현재 반환 최 댓 값입니다.

```
int GetRangeMax() const;
```

### <a name="return-value"></a>반환 값

현재 범위의 최대값입니다.

### <a name="remarks"></a>설명

##  <a name="getrangemin"></a>  CMFCRibbonProgressBar::GetRangeMin

진행률 표시줄의 현재 반환 합니다. 최소 범위 값입니다.

```
int GetRangeMin() const;
```

### <a name="return-value"></a>반환 값

현재 범위의 최소값입니다.

##  <a name="getregularsize"></a>  CMFCRibbonProgressBar::GetRegularSize

더 자세한 내용은 Visual Studio 설치의 **VC\\atlmfc\\src\\mfc** 폴더에 있는 소스 코드를 참조하세요.

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

[in] *pDC*<br/>

### <a name="return-value"></a>반환 값

### <a name="remarks"></a>설명

##  <a name="isinfinitemode"></a>  CMFCRibbonProgressBar::IsInfiniteMode

진행률 표시줄 무한 모드에서 작동 하는지 여부를 지정 합니다.

```
BOOL IsInfiniteMode() const;
```

### <a name="return-value"></a>반환 값

진행률 표시줄 무한 모드에 있으면 TRUE 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

무한 모드에서 진행률 표시줄을 채웁니다 반복적으로 최소값에서 최대값입니다. 작업이 진행 중에 있지만 완료 시간 알려지지 않은 무한 모드를 사용할 수 있습니다.

##  <a name="ondraw"></a>  CMFCRibbonProgressBar::OnDraw

더 자세한 내용은 Visual Studio 설치의 **VC\\atlmfc\\src\\mfc** 폴더에 있는 소스 코드를 참조하세요.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>매개 변수

[in] *pDC*<br/>

### <a name="remarks"></a>설명

##  <a name="setinfinitemode"></a>  CMFCRibbonProgressBar::SetInfiniteMode

진행률 표시줄 무한 모드로 작동 하도록 설정 합니다.

```
void SetInfiniteMode(BOOL bSet = TRUE);
```

### <a name="parameters"></a>매개 변수

*bSet*<br/>
[in] 진행률 표시줄 무한 모드 인지를 지정. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

일반적으로 진행률 표시줄 무한 모드인 경우 작업이 진행 중인 되었지만 완료 시간 알려지지 않은 사용자 지정 되어 있습니다. 따라서 진행률 표시줄이 반복적으로 최소값에서 최대값입니다.

##  <a name="setpos"></a>  CMFCRibbonProgressBar::SetPos

진행률 표시줄의 현재 위치를 설정합니다.

```
void SetPos(
    int nPos,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>매개 변수

*nPos*<br/>
[in] 진행률 표시줄에 설정 된 위치를 지정 합니다.

*bRedraw*<br/>
[in] 진행률 표시줄을 그려야 하는지 여부를 지정 합니다.

### <a name="remarks"></a>설명

설정 범위에서 지정 된 범위 내에 있어야 합니다.는 [CMFCRibbonProgressBar::SetRange](#setrange) 메서드.

##  <a name="setrange"></a>  CMFCRibbonProgressBar::SetRange

진행률 표시줄에 대 한 최소 및 최대 값을 설정합니다.

```
void SetRange(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>매개 변수

*nMin*<br/>
[in] 범위의 최소값을 지정 합니다.

*nMax*<br/>
[in] 범위의 최대값을 지정 합니다.

### <a name="remarks"></a>설명

최소값 및 최대값을 설정 하 여 진행률 표시줄의 범위를 정의 하려면이 메서드를 사용 합니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonBaseElement 클래스](../../mfc/reference/cmfcribbonbaseelement-class.md)<br/>
[CMFCRibbonBar 클래스](../../mfc/reference/cmfcribbonbar-class.md)
