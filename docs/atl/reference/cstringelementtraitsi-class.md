---
title: CStringElementTraitsI 클래스
ms.date: 11/04/2016
f1_keywords:
- CStringElementTraitsI
- ATLCOLL/ATL::CStringElementTraitsI
- ATLCOLL/ATL::CStringElementTraitsI::INARGTYPE
- ATLCOLL/ATL::CStringElementTraitsI::OUTARGTYPE
- ATLCOLL/ATL::CStringElementTraitsI::CompareElements
- ATLCOLL/ATL::CStringElementTraitsI::CompareElementsOrdered
- ATLCOLL/ATL::CStringElementTraitsI::Hash
helpviewer_keywords:
- CStringElementTraitsI class
ms.assetid: c23f92b1-91e5-400f-96ed-258b02622b7a
ms.openlocfilehash: 77357aa2be326ebebaaf5a8614faaf88a0c3c06b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62277437"
---
# <a name="cstringelementtraitsi-class"></a>CStringElementTraitsI 클래스

이 클래스는 컬렉션 클래스 개체에 저장 된 문자열에 관련 된 정적 함수를 제공 합니다. 비슷합니다 [CStringElementTraits](../../atl/reference/cstringelementtraits-class.md), 하지만 대/소문자 구분 비교를 수행 합니다.

## <a name="syntax"></a>구문

```
template <typename T, class CharTraits = CDefaultCharTraits<T ::XCHAR>>
class CStringElementTraitsI : public CElementTraitsBase<T>
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
컬렉션에 저장할 데이터의 형식입니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|이름|설명|
|----------|-----------------|
|[CStringElementTraitsI::INARGTYPE](#inargtype)|컬렉션 클래스 개체에 요소를 추가 하는 데 데이터 형식입니다.|
|[CStringElementTraitsI::OUTARGTYPE](#outargtype)|컬렉션 클래스 개체의 요소를 검색에 사용할 데이터 형식입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CStringElementTraitsI::CompareElements](#compareelements)|대/소문자 차이가 무시 하 고, 동등 여부에 대 한 두 개의 문자열 요소를 비교 하려면이 정적 함수를 호출 합니다.|
|[CStringElementTraitsI::CompareElementsOrdered](#compareelementsordered)|대/소문자 차이가 무시 하 고 두 문자열 요소를 비교 하려면이 정적 함수를 호출 합니다.|
|[CStringElementTraitsI::Hash](#hash)|지정 된 문자열 요소에 대 한 해시 값을 계산 하려면이 정적 함수를 호출 합니다.|

## <a name="remarks"></a>설명

이 클래스는 문자열을 비교 하 고 해시 값을 만들기 위한 정적 함수를 제공 합니다. 이러한 함수는 문자열 기반 데이터를 저장 하는 컬렉션 클래스를 사용 하는 경우에 유용 합니다. 사용 하 여 [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md) 사용 하 여 처리할 수 참조로 문자열 개체의 경우.

자세한 내용은 [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

`CStringElementTraitsI`

## <a name="requirements"></a>요구 사항

**헤더:** atlcoll.h

##  <a name="compareelements"></a>  CStringElementTraitsI::CompareElements

대/소문자 차이가 무시 하 고, 동등 여부에 대 한 두 개의 문자열 요소를 비교 하려면이 정적 함수를 호출 합니다.

```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2) throw();
```

### <a name="parameters"></a>매개 변수

*str1*<br/>
첫 번째 요소는 문자열입니다.

*str2*<br/>
두 번째 요소는 문자열입니다.

### <a name="return-value"></a>반환 값

요소가 같으면 false이 고, 그렇지 true를 반환 합니다.

### <a name="remarks"></a>설명

비교는 대/소문자 구분 합니다.

##  <a name="compareelementsordered"></a>  CStringElementTraitsI::CompareElementsOrdered

대/소문자 차이가 무시 하 고 두 문자열 요소를 비교 하려면이 정적 함수를 호출 합니다.

```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2) throw();
```

### <a name="parameters"></a>매개 변수

*str1*<br/>
첫 번째 요소는 문자열입니다.

*str2*<br/>
두 번째 요소는 문자열입니다.

### <a name="return-value"></a>반환 값

< 0, 0이 문자열이 동일한 경우 경우 *str1* 는 보다 작은 *str2*, 또는 > 0 경우 *str1* 보다 크면 *str2*합니다. 합니다 [CStringT::Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare) 메서드는 비교를 수행 하는 데 사용 됩니다.

### <a name="remarks"></a>설명

비교는 대/소문자 구분 합니다.

##  <a name="hash"></a>  CStringElementTraitsI::Hash

지정 된 문자열 요소에 대 한 해시 값을 계산 하려면이 정적 함수를 호출 합니다.

```
static ULONG Hash(INARGTYPE str) throw();
```

### <a name="parameters"></a>매개 변수

*str*<br/>
문자열 요소입니다.

### <a name="return-value"></a>반환 값

문자열의 내용을 사용 하 여 계산 된 해시 값을 반환 합니다.

##  <a name="inargtype"></a>  CStringElementTraitsI::INARGTYPE

컬렉션 클래스 개체에 요소를 추가 하는 데 데이터 형식입니다.

```
typedef T::PCXSTR INARGTYPE;
```

##  <a name="outargtype"></a>  CStringElementTraitsI::OUTARGTYPE

컬렉션 클래스 개체의 요소를 검색에 사용할 데이터 형식입니다.

```
typedef T& OUTARGTYPE;
```

## <a name="see-also"></a>참고자료

[CElementTraitsBase 클래스](../../atl/reference/celementtraitsbase-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[CStringElementTraits 클래스](../../atl/reference/cstringelementtraits-class.md)
