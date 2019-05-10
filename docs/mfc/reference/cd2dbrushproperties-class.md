---
title: CD2DBrushProperties 클래스
ms.date: 11/04/2016
f1_keywords:
- CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties::CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties::CommonInit
helpviewer_keywords:
- CD2DBrushProperties [MFC], CD2DBrushProperties
- CD2DBrushProperties [MFC], CommonInit
ms.assetid: c77d717f-0a16-4d74-b2ce-0ae1766ed6f9
ms.openlocfilehash: 5ca791af658ee719b2e6d6ea78f82e23a66edc98
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62253734"
---
# <a name="cd2dbrushproperties-class"></a>CD2DBrushProperties 클래스

`D2D1_BRUSH_PROPERTIES`의 래퍼입니다.

## <a name="syntax"></a>구문

```
class CD2DBrushProperties : public D2D1_BRUSH_PROPERTIES;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CD2DBrushProperties::CD2DBrushProperties](#cd2dbrushproperties)|오버로드됨. 만듭니다는 `CD2D_BRUSH_PROPERTIES` 구조|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[CD2DBrushProperties::CommonInit](#commoninit)|개체를 초기화합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`D2D1_BRUSH_PROPERTIES`

`CD2DBrushProperties`

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget.h

##  <a name="cd2dbrushproperties"></a>  CD2DBrushProperties::CD2DBrushProperties

CD2D_BRUSH_PROPERTIES 구조를 만듭니다.

```
CD2DBrushProperties();
CD2DBrushProperties(FLOAT _opacity);

CD2DBrushProperties(
    D2D1_MATRIX_3X2_F _transform,
    FLOAT _opacity = 1.);
```

### <a name="parameters"></a>매개 변수

*_opacity*<br/>
기본 불투명도 브러시입니다. 기본값은 1.0입니다.

*_transform*<br/>
브러시에 적용할 변환

##  <a name="commoninit"></a>  CD2DBrushProperties::CommonInit

개체를 초기화합니다.

```
void CommonInit();
```

## <a name="see-also"></a>참고자료

[클래스](../../mfc/reference/mfc-classes.md)
