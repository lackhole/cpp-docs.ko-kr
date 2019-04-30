---
title: CD2DPointU 클래스
ms.date: 11/04/2016
f1_keywords:
- CD2DPointU
- AFXRENDERTARGET/CD2DPointU
- AFXRENDERTARGET/CD2DPointU::CD2DPointU
helpviewer_keywords:
- CD2DPointU [MFC], CD2DPointU
ms.assetid: 04733f96-b6de-4a89-82e3-caad1e8087a9
ms.openlocfilehash: d66793abbb83015891df348eef8384e5c97baf2c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62396316"
---
# <a name="cd2dpointu-class"></a>CD2DPointU 클래스

`D2D1_POINT_2U`의 래퍼입니다.

## <a name="syntax"></a>구문

```
class CD2DPointU : public D2D1_POINT_2U;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CD2DPointU::CD2DPointU](#cd2dpointu)|오버로드됨. 생성 된 `CD2DPointU` 개체에서 `D2D1_POINT_2U` 개체입니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CD2DPointU::operator CPoint](#operator_cpoint)|변환 `CD2DPointU` 에 `CPoint` 개체입니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`D2D1_POINT_2U`

`CD2DPointU`

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget.h

##  <a name="cd2dpointu"></a>  CD2DPointU::CD2DPointU

CPoint 개체에서 CD2DPointU 개체를 생성합니다.

```
CD2DPointU(const CPoint& pt);
CD2DPointU(const D2D1_POINT_2U& pt);
  CD2DPointU(const D2D1_POINT_2U* pt);
CD2DPointU(UINT32 uX = 0, UINT32 uY = 0);
```

### <a name="parameters"></a>매개 변수

*pt*<br/>
원본 지점

*uX*<br/>
원본 X

*uY*<br/>
원본 Y

##  <a name="operator_cpoint"></a>  CD2DPointU::operator CPoint

CD2DPointU CPoint 개체로 변환합니다.

```
operator CPoint();
```

### <a name="return-value"></a>반환 값

D2D 요소의 현재 값입니다.

## <a name="see-also"></a>참고자료

[클래스](../../mfc/reference/mfc-classes.md)
