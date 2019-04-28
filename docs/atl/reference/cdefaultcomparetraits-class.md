---
title: CDefaultCompareTraits 클래스
ms.date: 11/04/2016
f1_keywords:
- CDefaultCompareTraits
- ATLCOLL/ATL::CDefaultCompareTraits
- ATLCOLL/ATL::CDefaultCompareTraits::CompareElements
- ATLCOLL/ATL::CDefaultCompareTraits::CompareElementsOrdered
helpviewer_keywords:
- CDefaultCompareTraits class
ms.assetid: a17e2740-e7b4-48f2-aeb7-c80ce84b63f7
ms.openlocfilehash: c5f4ab3737838af11501c4a0f2037b57087939c9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62245922"
---
# <a name="cdefaultcomparetraits-class"></a>CDefaultCompareTraits 클래스

이 클래스는 기본 요소 비교 함수를 제공 합니다.

## <a name="syntax"></a>구문

```
template<typename T>
class CDefaultCompareTraits
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
컬렉션에 저장할 데이터의 형식입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CDefaultCompareTraits::CompareElements](#compareelements)|(정적) 두 요소가 같은지를 비교 하려면이 함수를 호출 합니다.|
|[CDefaultCompareTraits::CompareElementsOrdered](#compareelementsordered)|(정적) 크고 작은 요소를 확인 하려면이 함수를 호출 합니다.|

## <a name="remarks"></a>설명

이 클래스에는 컬렉션 클래스 개체에 저장 된 요소를 비교 하기 위한 두 가지 정적 함수가 포함 됩니다. 이 클래스에서 사용 되는 [CDefaultElementTraits 클래스](../../atl/reference/cdefaultelementtraits-class.md)합니다.

자세한 내용은 [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md)합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlcoll.h

##  <a name="compareelements"></a>  CDefaultCompareTraits::CompareElements

두 요소가 같은지를 비교 하려면이 함수를 호출 합니다.

```
static bool CompareElements(const T& element1, const T& element2);
```

### <a name="parameters"></a>매개 변수

*element1*<br/>
첫 번째 요소입니다.

*element2*<br/>
두 번째 요소입니다.

### <a name="return-value"></a>반환 값

요소가 같으면 false이 고, 그렇지 true를 반환 합니다.

### <a name="remarks"></a>설명

이 함수의 기본 구현은 같음 (**==**) 연산자. 단순 데이터 형식 이외의 개체에 대 한이 함수를 재정의할 수 해야 합니다.

##  <a name="compareelementsordered"></a>  CDefaultCompareTraits::CompareElementsOrdered

크고 작은 요소를 확인 하려면이 함수를 호출 합니다.

```
static int CompareElementsOrdered(const T& element1, const T& element2);
```

### <a name="parameters"></a>매개 변수

*element1*<br/>
첫 번째 요소입니다.

*element2*<br/>
두 번째 요소입니다.

### <a name="return-value"></a>반환 값

다음 테이블을 기반으로 하는 정수를 반환 합니다.

|조건|반환 값|
|---------------|------------------|
|*element1* < *element2*|<0|
|*element1* == *element2*|0|
|*element1* > *element2*|>0|

### <a name="remarks"></a>설명

기본 구현은이 함수를 사용 합니다 **==** 를 **\<**, 및 **>** 연산자입니다. 단순 데이터 형식 이외의 개체에 대 한이 함수를 재정의할 수 해야 합니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)
