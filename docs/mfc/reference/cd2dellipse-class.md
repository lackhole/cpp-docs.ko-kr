---
title: CD2DEllipse 클래스
ms.date: 08/29/2019
f1_keywords:
- CD2DEllipse
- AFXRENDERTARGET/CD2DEllipse
- AFXRENDERTARGET/CD2DEllipse::CD2DEllipse
helpviewer_keywords:
- CD2DEllipse [MFC], CD2DEllipse
ms.assetid: e9f02f54-acf2-427e-b349-db50cd9a77df
ms.openlocfilehash: 21087682d40dac521cc949a39ef4b1aab23e7d71
ms.sourcegitcommit: e10a5feea193c249ddc5a6faba48e7c6d8784e73
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2019
ms.locfileid: "70177218"
---
# <a name="cd2dellipse-class"></a>CD2DEllipse 클래스

`D2D1_ELLIPSE`의 래퍼입니다.

## <a name="syntax"></a>구문

```
class CD2DEllipse : public D2D1_ELLIPSE;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CD2DEllipse::CD2DEllipse](#cd2dellipse)|오버로드됨. 개체에서 `CD2DEllipse` `D2D1_ELLIPSE` 개체를 생성 합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층

`D2D1_ELLIPSE`

`CD2DEllipse`

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget

##  <a name="cd2dellipse"></a>  CD2DEllipse::CD2DEllipse

CD2DRectF 개체에서 CD2DEllipse 개체를 생성 합니다.

```
CD2DEllipse(const CD2DRectF& rect);
CD2DEllipse(const D2D1_ELLIPSE& ellipse);
CD2DEllipse(const D2D1_ELLIPSE* ellipse);

CD2DEllipse(
    const CD2DPointF& ptCenter,
    const CD2DSizeF& sizeRadius);
```

### <a name="parameters"></a>매개 변수

*rect*<br/>
소스 사각형

*ellipse*<br/>
원본 타원

*ptCenter*<br/>
타원의 중심점입니다.

*sizeRadius*<br/>
타원의 X 반지름 및 Y 반경입니다.

## <a name="see-also"></a>참고자료

[클래스](../../mfc/reference/mfc-classes.md)
