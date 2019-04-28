---
title: CD2DLinearGradientBrush 클래스
ms.date: 11/04/2016
f1_keywords:
- CD2DLinearGradientBrush
- AFXRENDERTARGET/CD2DLinearGradientBrush
- AFXRENDERTARGET/CD2DLinearGradientBrush::CD2DLinearGradientBrush
- AFXRENDERTARGET/CD2DLinearGradientBrush::Attach
- AFXRENDERTARGET/CD2DLinearGradientBrush::Create
- AFXRENDERTARGET/CD2DLinearGradientBrush::Destroy
- AFXRENDERTARGET/CD2DLinearGradientBrush::Detach
- AFXRENDERTARGET/CD2DLinearGradientBrush::Get
- AFXRENDERTARGET/CD2DLinearGradientBrush::GetEndPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::GetStartPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::SetEndPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::SetStartPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::m_LinearGradientBrushProperties
- AFXRENDERTARGET/CD2DLinearGradientBrush::m_pLinearGradientBrush
helpviewer_keywords:
- CD2DLinearGradientBrush [MFC], CD2DLinearGradientBrush
- CD2DLinearGradientBrush [MFC], Attach
- CD2DLinearGradientBrush [MFC], Create
- CD2DLinearGradientBrush [MFC], Destroy
- CD2DLinearGradientBrush [MFC], Detach
- CD2DLinearGradientBrush [MFC], Get
- CD2DLinearGradientBrush [MFC], GetEndPoint
- CD2DLinearGradientBrush [MFC], GetStartPoint
- CD2DLinearGradientBrush [MFC], SetEndPoint
- CD2DLinearGradientBrush [MFC], SetStartPoint
- CD2DLinearGradientBrush [MFC], m_LinearGradientBrushProperties
- CD2DLinearGradientBrush [MFC], m_pLinearGradientBrush
ms.assetid: d4be9ff9-0ea8-45e6-9b8d-f3bc5673cbac
ms.openlocfilehash: d86235893d1f238f4cba9c927fad17f29060e591
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62348629"
---
# <a name="cd2dlineargradientbrush-class"></a>CD2DLinearGradientBrush 클래스

ID2D1LinearGradientBrush에 대 한 래퍼입니다.

## <a name="syntax"></a>구문

```
class CD2DLinearGradientBrush : public CD2DGradientBrush;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CD2DLinearGradientBrush::CD2DLinearGradientBrush](#cd2dlineargradientbrush)|CD2DLinearGradientBrush 개체를 생성합니다.|
|[CD2DLinearGradientBrush::~CD2DLinearGradientBrush](#_dtorcd2dlineargradientbrush)|소멸자입니다. D2D 선형 그라데이션 브러시 개체 소멸 될 때 호출 됩니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CD2DLinearGradientBrush::Attach](#attach)|기존 개체에 대 한 리소스 인터페이스를 연결.|
|[CD2DLinearGradientBrush::Create](#create)|CD2DLinearGradientBrush를 만듭니다. (재정의 [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DLinearGradientBrush::Destroy](#destroy)|CD2DLinearGradientBrush 개체를 제거합니다. (재정의 [CD2DGradientBrush::Destroy](../../mfc/reference/cd2dgradientbrush-class.md#destroy).)|
|[CD2DLinearGradientBrush::Detach](#detach)|개체에서 리소스 인터페이스를 분리합니다.|
|[CD2DLinearGradientBrush::Get](#get)|반환 ID2D1LinearGradientBrush 인터페이스|
|[CD2DLinearGradientBrush::GetEndPoint](#getendpoint)|선형 그라데이션의 끝 좌표를 검색합니다.|
|[CD2DLinearGradientBrush::GetStartPoint](#getstartpoint)|선형 그라데이션의 시작 좌표를 검색합니다.|
|[CD2DLinearGradientBrush::SetEndPoint](#setendpoint)|브러시의 좌표 공간에서 선형 그라데이션의 끝 좌표를 설정합니다.|
|[CD2DLinearGradientBrush::SetStartPoint](#setstartpoint)|브러시의 좌표 공간에서 선형 그라데이션의 시작 좌표를 설정합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CD2DLinearGradientBrush::operator ID2D1LinearGradientBrush*](#operator_id2d1lineargradientbrush_star)|반환 ID2D1LinearGradientBrush 인터페이스|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CD2DLinearGradientBrush::m_LinearGradientBrushProperties](#m_lineargradientbrushproperties)|그라데이션의 시작점과 끝점이 고 시작 합니다.|
|[CD2DLinearGradientBrush::m_pLinearGradientBrush](#m_plineargradientbrush)|ID2D1LinearGradientBrush 포인터입니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DBrush](../../mfc/reference/cd2dbrush-class.md)

[CD2DGradientBrush](../../mfc/reference/cd2dgradientbrush-class.md)

`CD2DLinearGradientBrush`

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget.h

##  <a name="_dtorcd2dlineargradientbrush"></a>  CD2DLinearGradientBrush::~CD2DLinearGradientBrush

소멸자입니다. D2D 선형 그라데이션 브러시 개체 소멸 될 때 호출 됩니다.

```
virtual ~CD2DLinearGradientBrush();
```

##  <a name="attach"></a>  CD2DLinearGradientBrush::Attach

기존 개체에 대 한 리소스 인터페이스를 연결.

```
void Attach(ID2D1LinearGradientBrush* pResource);
```

### <a name="parameters"></a>매개 변수

*pResource*<br/>
기존 리소스 인터페이스입니다. NULL 일 수 없습니다.

##  <a name="cd2dlineargradientbrush"></a>  CD2DLinearGradientBrush::CD2DLinearGradientBrush

CD2DLinearGradientBrush 개체를 생성합니다.

```
CD2DLinearGradientBrush(
    CRenderTarget* pParentTarget,
    const D2D1_GRADIENT_STOP* gradientStops,
    UINT gradientStopsCount,
    D2D1_LINEAR_GRADIENT_BRUSH_PROPERTIES LinearGradientBrushProperties,
    D2D1_GAMMA colorInterpolationGamma = D2D1_GAMMA_2_2,
    D2D1_EXTEND_MODE extendMode = D2D1_EXTEND_MODE_CLAMP,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>매개 변수

*pParentTarget*<br/>
렌더링 대상에 대 한 포인터입니다.

*gradientStops*<br/>
D2D1_GRADIENT_STOP 구조의 배열에 대 한 포인터입니다.

*gradientStopsCount*<br/>
GradientStops 배열의 그라데이션 중지점의 수를 지정 하는 1 보다 크거나 같은 값입니다.

*LinearGradientBrushProperties*<br/>
그라데이션의 시작점과 끝점이 고 시작 합니다.

*colorInterpolationGamma*<br/>
그라데이션 중지점 사이 보간을 수행 되는 색 공간입니다.

*extendMode*<br/>
[0, 1]의 표준화 된 범위 밖에 그라데이션의 동작입니다.

*pBrushProperties*<br/>
불투명도 및 브러시의 변환에 대 한 포인터입니다.

*bAutoDestroy*<br/>
개체 소유자 (pParentTarget)에 의해 소멸 되는 것을 나타냅니다.

##  <a name="create"></a>  CD2DLinearGradientBrush::Create

CD2DLinearGradientBrush를 만듭니다.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>매개 변수

*pRenderTarget*<br/>
렌더링 대상에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 HRESULT 오류 코드를 반환합니다.

##  <a name="destroy"></a>  CD2DLinearGradientBrush::Destroy

CD2DLinearGradientBrush 개체를 제거합니다.

```
virtual void Destroy();
```

##  <a name="detach"></a>  CD2DLinearGradientBrush::Detach

개체에서 리소스 인터페이스를 분리합니다.

```
ID2D1LinearGradientBrush* Detach();
```

### <a name="return-value"></a>반환 값

분리 된 리소스 인터페이스에 대 한 포인터입니다.

##  <a name="get"></a>  CD2DLinearGradientBrush::Get

반환 ID2D1LinearGradientBrush 인터페이스

```
ID2D1LinearGradientBrush* Get();
```

### <a name="return-value"></a>반환 값

ID2D1LinearGradientBrush 인터페이스 또는 개체가 아직 초기화 되지 않은 경우 NULL 포인터입니다.

##  <a name="getendpoint"></a>  CD2DLinearGradientBrush::GetEndPoint

선형 그라데이션의 끝 좌표를 검색합니다.

```
CD2DPointF GetEndPoint() const;
```

### <a name="return-value"></a>반환 값

브러시의 좌표 공간에서 선형 그라데이션의 끝 2 차원 좌표

##  <a name="getstartpoint"></a>  CD2DLinearGradientBrush::GetStartPoint

선형 그라데이션의 시작 좌표를 검색합니다.

```
CD2DPointF GetStartPoint() const;
```

### <a name="return-value"></a>반환 값

브러시의 좌표 공간에서 선형 그라데이션의 시작 2 차원 좌표

##  <a name="m_lineargradientbrushproperties"></a>  CD2DLinearGradientBrush::m_LinearGradientBrushProperties

그라데이션의 시작점과 끝점이 고 시작 합니다.

```
D2D1_LINEAR_GRADIENT_BRUSH_PROPERTIES m_LinearGradientBrushProperties;
```

##  <a name="m_plineargradientbrush"></a>  CD2DLinearGradientBrush::m_pLinearGradientBrush

ID2D1LinearGradientBrush 포인터입니다.

```
ID2D1LinearGradientBrush* m_pLinearGradientBrush;
```

##  <a name="operator_id2d1lineargradientbrush_star"></a>  CD2DLinearGradientBrush::operator ID2D1LinearGradientBrush*

반환 ID2D1LinearGradientBrush 인터페이스

```
operator ID2D1LinearGradientBrush*();
```

### <a name="return-value"></a>반환 값

ID2D1LinearGradientBrush 인터페이스 또는 개체가 아직 초기화 되지 않은 경우 NULL 포인터입니다.

##  <a name="setendpoint"></a>  CD2DLinearGradientBrush::SetEndPoint

브러시의 좌표 공간에서 선형 그라데이션의 끝 좌표를 설정합니다.

```
void SetEndPoint(CD2DPointF point);
```

### <a name="parameters"></a>매개 변수

*point*<br/>
브러시의 좌표 공간에서 선형 그라데이션의 끝 2 차원 좌표

##  <a name="setstartpoint"></a>  CD2DLinearGradientBrush::SetStartPoint

브러시의 좌표 공간에서 선형 그라데이션의 시작 좌표를 설정합니다.

```
void SetStartPoint(CD2DPointF point);
```

### <a name="parameters"></a>매개 변수

*point*<br/>
브러시의 좌표 공간에서 선형 그라데이션의 시작 2 차원 좌표

## <a name="see-also"></a>참고자료

[클래스](../../mfc/reference/mfc-classes.md)
