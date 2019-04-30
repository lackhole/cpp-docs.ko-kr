---
title: CD2DSizeF 클래스
ms.date: 11/04/2016
f1_keywords:
- CD2DSizeF
- AFXRENDERTARGET/CD2DSizeF
- AFXRENDERTARGET/CD2DSizeF::CD2DSizeF
- AFXRENDERTARGET/CD2DSizeF::IsNull
helpviewer_keywords:
- CD2DSizeF [MFC], CD2DSizeF
- CD2DSizeF [MFC], IsNull
ms.assetid: f486a1e1-997d-4286-8cb9-26369dc82055
ms.openlocfilehash: 09ccd8c4ba6bb0c345adb32bcf22686c485d1184
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62396238"
---
# <a name="cd2dsizef-class"></a>CD2DSizeF 클래스

D2D1_SIZE_F에 대 한 래퍼입니다.

## <a name="syntax"></a>구문

```
class CD2DSizeF : public D2D1_SIZE_F;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CD2DSizeF::CD2DSizeF](#cd2dsizef)|오버로드됨. 생성 된 `CD2DSizeF` 에서 개체 `D2D1_SIZE_F` 개체입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CD2DSizeF::IsNull](#isnull)|반환 된 **부울** 식에 유효 하지 않은 데이터 (NULL)이 포함 되어 있는지 여부를 나타내는 값입니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CD2DSizeF::operator CSize](#operator_csize)|변환 `CD2DSizeF` 에 `CSize` 개체입니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`D2D1_SIZE_F`

[CD2DSizeF](../../mfc/reference/cd2dsizef-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxrendertarget.h

##  <a name="cd2dsizef"></a>  CD2DSizeF::CD2DSizeF

CSize 개체에서 CD2DSizeF 개체를 생성합니다.

```
CD2DSizeF(const CSize& size);
CD2DSizeF(const D2D1_SIZE_F& size);
  CD2DSizeF(const D2D1_SIZE_F* size);

CD2DSizeF(
    FLOAT cx = 0.,
    FLOAT cy = 0.);
```

### <a name="parameters"></a>매개 변수

*size*<br/>
원본 크기

*cx*<br/>
원본 너비

*cy*<br/>
원본 높이

##  <a name="isnull"></a>  CD2DSizeF::IsNull

식에 유효 하지 않은 데이터 (Null)이 포함 되어 있는지 여부를 나타내는 부울 값을 반환 합니다.

```
BOOL IsNull() const;
```

### <a name="return-value"></a>반환 값

너비와 높이 비어 있으면 TRUE 그렇지 않으면 FALSE입니다.

##  <a name="operator_csize"></a>  CD2DSizeF::operator CSize

CD2DSizeF CSize 개체로 변환합니다.

```
operator CSize();
```

### <a name="return-value"></a>반환 값

D2D 크기의 현재 값입니다.

## <a name="see-also"></a>참고자료

[클래스](../../mfc/reference/mfc-classes.md)
