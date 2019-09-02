---
title: CD2DPointU 클래스
ms.date: 08/29/2019
f1_keywords:
- CD2DPointU
- AFXRENDERTARGET/CD2DPointU
- AFXRENDERTARGET/CD2DPointU::CD2DPointU
helpviewer_keywords:
- CD2DPointU [MFC], CD2DPointU
ms.assetid: 04733f96-b6de-4a89-82e3-caad1e8087a9
ms.openlocfilehash: 6289d33aa0672d1ee423d91b11527dccfc868da7
ms.sourcegitcommit: e10a5feea193c249ddc5a6faba48e7c6d8784e73
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2019
ms.locfileid: "70177170"
---
# <a name="cd2dpointu-class"></a>CD2DPointU 클래스

`D2D1_POINT_2U`의 래퍼입니다.

## <a name="syntax"></a>구문

```
class CD2DPointU : public D2D1_POINT_2U;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|Description|
|----------|-----------------|
|[CD2DPointU::CD2DPointU](#cd2dpointu)|오버로드됨. `CD2DPointU` 개체`D2D1_POINT_2U` 개체에서을 생성 합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|Description|
|----------|-----------------|
|[CD2DPointU::operator CPoint](#operator_cpoint)|개체로 변환 `CD2DPointU`합니다. `CPoint`|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`D2D1_POINT_2U`

`CD2DPointU`

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget

##  <a name="cd2dpointu"></a>  CD2DPointU::CD2DPointU

CPoint 개체에서 CD2DPointU 개체를 생성 합니다.

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

CD2DPointU를 CPoint 개체로 변환 합니다.

```
operator CPoint();
```

### <a name="return-value"></a>반환 값

D2D 지점의 현재 값입니다.

## <a name="see-also"></a>참고자료

[클래스](../../mfc/reference/mfc-classes.md)
