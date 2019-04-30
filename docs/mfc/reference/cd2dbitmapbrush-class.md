---
title: CD2DBitmapBrush 클래스
ms.date: 11/04/2016
f1_keywords:
- CD2DBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush::CD2DBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush::Attach
- AFXRENDERTARGET/CD2DBitmapBrush::Create
- AFXRENDERTARGET/CD2DBitmapBrush::Destroy
- AFXRENDERTARGET/CD2DBitmapBrush::Detach
- AFXRENDERTARGET/CD2DBitmapBrush::Get
- AFXRENDERTARGET/CD2DBitmapBrush::GetBitmap
- AFXRENDERTARGET/CD2DBitmapBrush::GetExtendModeX
- AFXRENDERTARGET/CD2DBitmapBrush::GetExtendModeY
- AFXRENDERTARGET/CD2DBitmapBrush::GetInterpolationMode
- AFXRENDERTARGET/CD2DBitmapBrush::SetBitmap
- AFXRENDERTARGET/CD2DBitmapBrush::SetExtendModeX
- AFXRENDERTARGET/CD2DBitmapBrush::SetExtendModeY
- AFXRENDERTARGET/CD2DBitmapBrush::SetInterpolationMode
- AFXRENDERTARGET/CD2DBitmapBrush::CommonInit
- AFXRENDERTARGET/CD2DBitmapBrush::m_pBitmap
- AFXRENDERTARGET/CD2DBitmapBrush::m_pBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush::m_pBitmapBrushProperties
helpviewer_keywords:
- CD2DBitmapBrush [MFC], CD2DBitmapBrush
- CD2DBitmapBrush [MFC], Attach
- CD2DBitmapBrush [MFC], Create
- CD2DBitmapBrush [MFC], Destroy
- CD2DBitmapBrush [MFC], Detach
- CD2DBitmapBrush [MFC], Get
- CD2DBitmapBrush [MFC], GetBitmap
- CD2DBitmapBrush [MFC], GetExtendModeX
- CD2DBitmapBrush [MFC], GetExtendModeY
- CD2DBitmapBrush [MFC], GetInterpolationMode
- CD2DBitmapBrush [MFC], SetBitmap
- CD2DBitmapBrush [MFC], SetExtendModeX
- CD2DBitmapBrush [MFC], SetExtendModeY
- CD2DBitmapBrush [MFC], SetInterpolationMode
- CD2DBitmapBrush [MFC], CommonInit
- CD2DBitmapBrush [MFC], m_pBitmap
- CD2DBitmapBrush [MFC], m_pBitmapBrush
- CD2DBitmapBrush [MFC], m_pBitmapBrushProperties
ms.assetid: 46ebbe34-66e0-44c8-af1d-d129e851de5e
ms.openlocfilehash: 1569039db8c1f85d3091282b55d7eda253444deb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405796"
---
# <a name="cd2dbitmapbrush-class"></a>CD2DBitmapBrush 클래스

ID2D1BitmapBrush에 대 한 래퍼입니다.

## <a name="syntax"></a>구문

```
class CD2DBitmapBrush : public CD2DBrush;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CD2DBitmapBrush::CD2DBitmapBrush](#cd2dbitmapbrush)|오버로드됨. 파일에서 CD2DBitmapBrush 개체를 생성합니다.|
|[CD2DBitmapBrush::~CD2DBitmapBrush](#dtor)|소멸자입니다. D2D 비트맵 brush 개체 소멸 될 때 호출 됩니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CD2DBitmapBrush::Attach](#attach)|기존 개체에 대 한 리소스 인터페이스를 연결.|
|[CD2DBitmapBrush::Create](#create)|CD2DBitmapBrush를 만듭니다. (재정의 [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DBitmapBrush::Destroy](#destroy)|CD2DBitmapBrush 개체를 제거합니다. (재정의 [CD2DBrush::Destroy](../../mfc/reference/cd2dbrush-class.md#destroy).)|
|[CD2DBitmapBrush::Detach](#detach)|개체에서 리소스 인터페이스를 분리합니다.|
|[CD2DBitmapBrush::Get](#get)|반환 ID2D1BitmapBrush 인터페이스|
|[CD2DBitmapBrush::GetBitmap](#getbitmap)|이 브러시를 그리는 데 사용 하는 비트맵 소스를 가져옵니다.|
|[CD2DBitmapBrush::GetExtendModeX](#getextendmodex)|브러시가 비트맵을 지 나 확장 되는 영역 가로 바둑판식는 메서드를 가져옵니다.|
|[CD2DBitmapBrush::GetExtendModeY](#getextendmodey)|브러시가 비트맵을 지 나 확장 되는 영역 세로 바둑판식는 메서드를 가져옵니다.|
|[CD2DBitmapBrush::GetInterpolationMode](#getinterpolationmode)|브러시 비트맵은 크기 조정 또는 회전할 때 사용 되는 보간 메서드를 가져옵니다.|
|[CD2DBitmapBrush::SetBitmap](#setbitmap)|이 브러시를 그리는 데 사용 하는 비트맵 소스를 지정 합니다.|
|[CD2DBitmapBrush::SetExtendModeX](#setextendmodex)|브러시가 비트맵을 지 나 확장 되는 영역을 가로로으로 바둑판식으로 표시 되는 방식을 지정 합니다.|
|[CD2DBitmapBrush::SetExtendModeY](#setextendmodey)|브러시가 비트맵을 지 나 확장 되는 영역을 세로로으로 바둑판식으로 표시 되는 방식을 지정 합니다.|
|[CD2DBitmapBrush::SetInterpolationMode](#setinterpolationmode)|브러시 비트맵을 크기 조정 또는 회전 하는 경우 사용 되는 보간 모드를 지정 합니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[CD2DBitmapBrush::CommonInit](#commoninit)|개체를 초기화합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CD2DBitmapBrush::operator ID2D1BitmapBrush*](#operator_id2d1bitmapbrush_star)|반환 ID2D1BitmapBrush 인터페이스|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CD2DBitmapBrush::m_pBitmap](#m_pbitmap)|CD2DBitmap 개체에 대 한 포인터를 저장합니다.|
|[CD2DBitmapBrush::m_pBitmapBrush](#m_pbitmapbrush)|ID2D1BitmapBrush 개체에 대 한 포인터를 저장합니다.|
|[CD2DBitmapBrush::m_pBitmapBrushProperties](#m_pbitmapbrushproperties)|브러시 속성은 비트맵입니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DBrush](../../mfc/reference/cd2dbrush-class.md)

`CD2DBitmapBrush`

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget.h

##  <a name="dtor"></a>  CD2DBitmapBrush::~CD2DBitmapBrush

소멸자입니다. D2D 비트맵 brush 개체 소멸 될 때 호출 됩니다.

```
virtual ~CD2DBitmapBrush();
```

##  <a name="attach"></a>  CD2DBitmapBrush::Attach

기존 개체에 대 한 리소스 인터페이스를 연결.

```
void Attach(ID2D1BitmapBrush* pResource);
```

### <a name="parameters"></a>매개 변수

*pResource*<br/>
기존 리소스 인터페이스입니다. NULL 일 수 없습니다.

##  <a name="cd2dbitmapbrush"></a>  CD2DBitmapBrush::CD2DBitmapBrush

CD2DBitmapBrush 개체를 생성합니다.

```
CD2DBitmapBrush(
    CRenderTarget* pParentTarget,
    D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties = NULL,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);

CD2DBitmapBrush(
    CRenderTarget* pParentTarget,
    UINT uiResID,
    LPCTSTR lpszType = NULL,
    CD2DSizeU sizeDest = CD2DSizeU(0, 0),
    D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties = NULL,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);

CD2DBitmapBrush(
    CRenderTarget* pParentTarget,
    LPCTSTR lpszImagePath,
    CD2DSizeU sizeDest = CD2DSizeU(0, 0),
    D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties = NULL,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>매개 변수

*pParentTarget*<br/>
렌더링 대상에 대 한 포인터입니다.

*pBitmapBrushProperties*<br/>
확장 모드 및 비트맵 브러시의 보간 모드에 대 한 포인터입니다.

*pBrushProperties*<br/>
불투명도 및 브러시의 변환에 대 한 포인터입니다.

*bAutoDestroy*<br/>
개체 소유자 (pParentTarget)에 의해 소멸 되는 것을 나타냅니다.

*uiResID*<br/>
리소스의 리소스 ID.

*lpszType*<br/>
리소스 형식이 포함 된 null로 끝나는 문자열에 대 한 포인터입니다.

*sizeDest*<br/>
비트맵의 대상 크기입니다.

*lpszImagePath*<br/>
파일의 이름을 포함 하는 null로 끝나는 문자열에 대 한 포인터입니다.

##  <a name="commoninit"></a>  CD2DBitmapBrush::CommonInit

개체를 초기화합니다.

```
void CommonInit(D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties);
```

### <a name="parameters"></a>매개 변수

*pBitmapBrushProperties*<br/>
비트맵 브러시 속성에 대 한 포인터입니다.

##  <a name="create"></a>  CD2DBitmapBrush::Create

CD2DBitmapBrush를 만듭니다.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>매개 변수

*pRenderTarget*<br/>
렌더링 대상에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

메서드가 성공 하면 S_OK를 반환 합니다. 그렇지 않으면 HRESULT 오류 코드를 반환합니다.

##  <a name="destroy"></a>  CD2DBitmapBrush::Destroy

CD2DBitmapBrush 개체를 제거합니다.

```
virtual void Destroy();
```

##  <a name="detach"></a>  CD2DBitmapBrush::Detach

개체에서 리소스 인터페이스를 분리합니다.

```
ID2D1BitmapBrush* Detach();
```

### <a name="return-value"></a>반환 값

분리 된 리소스 인터페이스에 대 한 포인터입니다.

##  <a name="get"></a>  CD2DBitmapBrush::Get

반환 ID2D1BitmapBrush 인터페이스

```
ID2D1BitmapBrush* Get();
```

### <a name="return-value"></a>반환 값

ID2D1BitmapBrush 인터페이스 또는 개체가 아직 초기화 되지 않은 경우 NULL 포인터입니다.

##  <a name="getbitmap"></a>  CD2DBitmapBrush::GetBitmap

이 브러시를 그리는 데 사용 하는 비트맵 소스를 가져옵니다.

```
CD2DBitmap* GetBitmap();
```

### <a name="return-value"></a>반환 값

CD2DBitmap 개체 또는 NULL 개체가 아직 초기화 되지 않은 경우에 대 한 포인터입니다.

##  <a name="getextendmodex"></a>  CD2DBitmapBrush::GetExtendModeX

브러시가 비트맵을 지 나 확장 되는 영역 가로 바둑판식는 메서드를 가져옵니다.

```
D2D1_EXTEND_MODE GetExtendModeX() const;
```

### <a name="return-value"></a>반환 값

브러시가 비트맵을 지 나 확장 되는 영역을 가로로으로 바둑판식으로 표시 되는 방식을 지정 하는 값

##  <a name="getextendmodey"></a>  CD2DBitmapBrush::GetExtendModeY

브러시가 비트맵을 지 나 확장 되는 영역 세로 바둑판식는 메서드를 가져옵니다.

```
D2D1_EXTEND_MODE GetExtendModeY() const;
```

### <a name="return-value"></a>반환 값

브러시가 비트맵을 지 나 확장 되는 영역을 세로로으로 바둑판식으로 표시 되는 방식을 지정 하는 값

##  <a name="getinterpolationmode"></a>  CD2DBitmapBrush::GetInterpolationMode

브러시 비트맵은 크기 조정 또는 회전할 때 사용 되는 보간 메서드를 가져옵니다.

```
D2D1_BITMAP_INTERPOLATION_MODE GetInterpolationMode() const;
```

### <a name="return-value"></a>반환 값

브러시 비트맵은 크기 조정 또는 회전할 때 사용 되는 보간 방법

##  <a name="m_pbitmap"></a>  CD2DBitmapBrush::m_pBitmap

CD2DBitmap 개체에 대 한 포인터를 저장합니다.

```
CD2DBitmap* m_pBitmap;
```

##  <a name="m_pbitmapbrush"></a>  CD2DBitmapBrush::m_pBitmapBrush

ID2D1BitmapBrush 개체에 대 한 포인터를 저장합니다.

```
ID2D1BitmapBrush* m_pBitmapBrush;
```

##  <a name="m_pbitmapbrushproperties"></a>  CD2DBitmapBrush::m_pBitmapBrushProperties

브러시 속성은 비트맵입니다.

```
D2D1_BITMAP_BRUSH_PROPERTIES* m_pBitmapBrushProperties;
```

##  <a name="operator_id2d1bitmapbrush_star"></a>  CD2DBitmapBrush::operator ID2D1BitmapBrush*

반환 ID2D1BitmapBrush 인터페이스

```
operator ID2D1BitmapBrush*();
```

### <a name="return-value"></a>반환 값

ID2D1BitmapBrush 인터페이스 또는 개체가 아직 초기화 되지 않은 경우 NULL 포인터입니다.

##  <a name="setbitmap"></a>  CD2DBitmapBrush::SetBitmap

이 브러시를 그리는 데 사용 하는 비트맵 소스를 지정 합니다.

```
void SetBitmap(CD2DBitmap* pBitmap);
```

### <a name="parameters"></a>매개 변수

*pBitmap*<br/>
브러시에 사용 되는 비트맵 소스

##  <a name="setextendmodex"></a>  CD2DBitmapBrush::SetExtendModeX

브러시가 비트맵을 지 나 확장 되는 영역을 가로로으로 바둑판식으로 표시 되는 방식을 지정 합니다.

```
void SetExtendModeX(D2D1_EXTEND_MODE extendModeX);
```

### <a name="parameters"></a>매개 변수

*extendModeX*<br/>
브러시가 비트맵을 지 나 확장 되는 영역을 가로로으로 바둑판식으로 표시 되는 방식을 지정 하는 값

##  <a name="setextendmodey"></a>  CD2DBitmapBrush::SetExtendModeY

브러시가 비트맵을 지 나 확장 되는 영역을 세로로으로 바둑판식으로 표시 되는 방식을 지정 합니다.

```
void SetExtendModeY(D2D1_EXTEND_MODE extendModeY);
```

### <a name="parameters"></a>매개 변수

*extendModeY*<br/>
브러시가 비트맵을 지 나 확장 되는 영역을 세로로으로 바둑판식으로 표시 되는 방식을 지정 하는 값

##  <a name="setinterpolationmode"></a>  CD2DBitmapBrush::SetInterpolationMode

브러시 비트맵을 크기 조정 또는 회전 하는 경우 사용 되는 보간 모드를 지정 합니다.

```
void SetInterpolationMode(D2D1_BITMAP_INTERPOLATION_MODE interpolationMode);
```

### <a name="parameters"></a>매개 변수

*interpolationMode*<br/>
브러시 비트맵을 크기 조정 또는 회전 하는 경우 사용 되는 보간 모드

## <a name="see-also"></a>참고자료

[클래스](../../mfc/reference/mfc-classes.md)
