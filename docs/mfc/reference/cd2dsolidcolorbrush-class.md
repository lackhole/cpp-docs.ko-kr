---
title: CD2DSolidColorBrush 클래스
ms.date: 03/27/2019
f1_keywords:
- CD2DSolidColorBrush
- AFXRENDERTARGET/CD2DSolidColorBrush
- AFXRENDERTARGET/CD2DSolidColorBrush::CD2DSolidColorBrush
- AFXRENDERTARGET/CD2DSolidColorBrush::Attach
- AFXRENDERTARGET/CD2DSolidColorBrush::Create
- AFXRENDERTARGET/CD2DSolidColorBrush::Destroy
- AFXRENDERTARGET/CD2DSolidColorBrush::Detach
- AFXRENDERTARGET/CD2DSolidColorBrush::Get
- AFXRENDERTARGET/CD2DSolidColorBrush::GetColor
- AFXRENDERTARGET/CD2DSolidColorBrush::SetColor
- AFXRENDERTARGET/CD2DSolidColorBrush::m_colorSolid
- AFXRENDERTARGET/CD2DSolidColorBrush::m_pSolidColorBrush
helpviewer_keywords:
- CD2DSolidColorBrush [MFC], CD2DSolidColorBrush
- CD2DSolidColorBrush [MFC], Attach
- CD2DSolidColorBrush [MFC], Create
- CD2DSolidColorBrush [MFC], Destroy
- CD2DSolidColorBrush [MFC], Detach
- CD2DSolidColorBrush [MFC], Get
- CD2DSolidColorBrush [MFC], GetColor
- CD2DSolidColorBrush [MFC], SetColor
- CD2DSolidColorBrush [MFC], m_colorSolid
- CD2DSolidColorBrush [MFC], m_pSolidColorBrush
ms.assetid: d4506637-acce-4f74-8a9b-f0a45571a735
ms.openlocfilehash: f225198193443c11d0294010a5fb71858514c81e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62396225"
---
# <a name="cd2dsolidcolorbrush-class"></a>CD2DSolidColorBrush 클래스

ID2D1SolidColorBrush에 대 한 래퍼입니다.

## <a name="syntax"></a>구문

```
class CD2DSolidColorBrush : public CD2DBrush;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CD2DSolidColorBrush::CD2DSolidColorBrush](#cd2dsolidcolorbrush)|오버로드됨. CD2DSolidColorBrush 개체를 생성합니다.|
|[CD2DSolidColorBrush::~CD2DSolidColorBrush](#_dtorcd2dsolidcolorbrush)|소멸자입니다. D2D 단색 브러시 개체 소멸 될 때 호출 됩니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CD2DSolidColorBrush::Attach](#attach)|기존 개체에 대 한 리소스 인터페이스를 연결.|
|[CD2DSolidColorBrush::Create](#create)|CD2DSolidColorBrush를 만듭니다. (재정의 [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DSolidColorBrush::Destroy](#destroy)|CD2DSolidColorBrush 개체를 제거합니다. (재정의 [CD2DBrush::Destroy](../../mfc/reference/cd2dbrush-class.md#destroy).)|
|[CD2DSolidColorBrush::Detach](#detach)|개체에서 리소스 인터페이스를 분리합니다.|
|[CD2DSolidColorBrush::Get](#get)|반환 ID2D1SolidColorBrush 인터페이스|
|[CD2DSolidColorBrush::GetColor](#getcolor)|단색 브러시의 색을 검색|
|[CD2DSolidColorBrush::SetColor](#setcolor)|이 단색 브러시의 색을 지정|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CD2DSolidColorBrush::operator ID2D1SolidColorBrush*](#operator_id2d1solidcolorbrush_star)|반환 ID2D1SolidColorBrush 인터페이스|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CD2DSolidColorBrush::m_colorSolid](#m_colorsolid)|단색 브러시입니다.|
|[CD2DSolidColorBrush::m_pSolidColorBrush](#m_psolidcolorbrush)|ID2D1SolidColorBrush 개체에 대 한 포인터를 저장합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DBrush](../../mfc/reference/cd2dbrush-class.md)

[CD2DSolidColorBrush](../../mfc/reference/cd2dsolidcolorbrush-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget.h

##  <a name="_dtorcd2dsolidcolorbrush"></a>  CD2DSolidColorBrush::~CD2DSolidColorBrush

소멸자입니다. D2D 단색 브러시 개체 소멸 될 때 호출 됩니다.

```
virtual ~CD2DSolidColorBrush();
```

##  <a name="attach"></a>  CD2DSolidColorBrush::Attach

기존 개체에 대 한 리소스 인터페이스를 연결.

```
void Attach(ID2D1SolidColorBrush* pResource);
```

### <a name="parameters"></a>매개 변수

*pResource*<br/>
기존 리소스 인터페이스입니다. NULL 일 수 없습니다.

##  <a name="cd2dsolidcolorbrush"></a>  CD2DSolidColorBrush::CD2DSolidColorBrush

CD2DSolidColorBrush 개체를 생성합니다.

```
CD2DSolidColorBrush(
    CRenderTarget* pParentTarget,
    D2D1_COLOR_F color,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);

CD2DSolidColorBrush(
    CRenderTarget* pParentTarget,
    COLORREF color,
    int nAlpha = 255,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>매개 변수

*pParentTarget*<br/>
렌더링 대상에 대 한 포인터입니다.

*color*<br/>
브러시의 색의 빨강, 녹색, 파랑 및 알파 값입니다.

*pBrushProperties*<br/>
불투명도 및 브러시의 변환에 대 한 포인터입니다.

*bAutoDestroy*<br/>
개체 소유자 (pParentTarget)에 의해 소멸 되는 것을 나타냅니다.

*nAlpha*<br/>
브러시의 색의 불투명도입니다.

##  <a name="create"></a>  CD2DSolidColorBrush::Create

CD2DSolidColorBrush를 만듭니다.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>매개 변수

*pRenderTarget*<br/>
렌더링 대상에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 HRESULT 오류 코드를 반환합니다.

##  <a name="destroy"></a>  CD2DSolidColorBrush::Destroy

CD2DSolidColorBrush 개체를 제거합니다.

```
virtual void Destroy();
```

##  <a name="detach"></a>  CD2DSolidColorBrush::Detach

개체에서 리소스 인터페이스를 분리합니다.

```
ID2D1SolidColorBrush* Detach();
```

### <a name="return-value"></a>반환 값

분리 된 리소스 인터페이스에 대 한 포인터입니다.

##  <a name="get"></a>  CD2DSolidColorBrush::Get

반환 ID2D1SolidColorBrush 인터페이스

```
ID2D1SolidColorBrush* Get();
```

### <a name="return-value"></a>반환 값

ID2D1SolidColorBrush 인터페이스 또는 개체가 아직 초기화 되지 않은 경우 NULL 포인터입니다.

##  <a name="getcolor"></a>  CD2DSolidColorBrush::GetColor

단색 브러시의 색을 검색

```
D2D1_COLOR_F GetColor() const;
```

### <a name="return-value"></a>반환 값

이 단색 브러시의 색

##  <a name="m_colorsolid"></a>  CD2DSolidColorBrush::m_colorSolid

단색 브러시입니다.

```
D2D1_COLOR_F m_colorSolid;
```

##  <a name="m_psolidcolorbrush"></a>  CD2DSolidColorBrush::m_pSolidColorBrush

ID2D1SolidColorBrush 개체에 대 한 포인터를 저장합니다.

```
ID2D1SolidColorBrush* m_pSolidColorBrush;
```

##  <a name="operator_id2d1solidcolorbrush_star"></a>  CD2DSolidColorBrush::operator ID2D1SolidColorBrush*

반환 ID2D1SolidColorBrush 인터페이스

```
operator ID2D1SolidColorBrush*();
```

### <a name="return-value"></a>반환 값

ID2D1SolidColorBrush 인터페이스 또는 개체가 아직 초기화 되지 않은 경우 NULL 포인터입니다.

##  <a name="setcolor"></a>  CD2DSolidColorBrush::SetColor

이 단색 브러시의 색을 지정

```
void SetColor(D2D1_COLOR_F color);
```

### <a name="parameters"></a>매개 변수

*color*<br/>
이 단색 브러시의 색

## <a name="see-also"></a>참고자료

[클래스](../../mfc/reference/mfc-classes.md)
