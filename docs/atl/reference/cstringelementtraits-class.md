---
title: CStringElementTraits 클래스
ms.date: 11/04/2016
f1_keywords:
- CStringElementTraits
- CSTRINGT/ATL::CStringElementTraits
- CSTRINGT/ATL::CStringElementTraits::INARGTYPE
- CSTRINGT/ATL::CStringElementTraits::OUTARGTYPE
- CSTRINGT/ATL::CStringElementTraits::CompareElements
- CSTRINGT/ATL::CStringElementTraits::CompareElementsOrdered
- CSTRINGT/ATL::CStringElementTraits::CopyElements
- CSTRINGT/ATL::CStringElementTraits::Hash
- CSTRINGT/ATL::CStringElementTraits::RelocateElements
helpviewer_keywords:
- CStringElementTraits class
ms.assetid: 74d7134b-099d-4455-bf91-3e68ccbf95bc
ms.openlocfilehash: 80efd4dbc4ff0541e083ed61bed872d5e69c7a74
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62277450"
---
# <a name="cstringelementtraits-class"></a>CStringElementTraits 클래스

이 클래스는 저장 하는 컬렉션 클래스에 의해 사용 되는 정적 함수를 제공 `CString` 개체입니다.

## <a name="syntax"></a>구문

```
template <typename T>
class CStringElementTraits
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
컬렉션에 저장할 데이터의 형식입니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|이름|설명|
|----------|-----------------|
|[CStringElementTraits::INARGTYPE](#inargtype)|컬렉션 클래스 개체에 요소를 추가 하는 데 데이터 형식입니다.|
|[CStringElementTraits::OUTARGTYPE](#outargtype)|컬렉션 클래스 개체의 요소를 검색에 사용할 데이터 형식입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CStringElementTraits::CompareElements](#compareelements)|(정적) 두 문자열 요소가 같은지를 비교 하려면이 함수를 호출 합니다.|
|[CStringElementTraits::CompareElementsOrdered](#compareelementsordered)|(정적) 두 문자열 요소를 비교 하려면이 함수를 호출 합니다.|
|[CStringElementTraits::CopyElements](#copyelements)|(정적) 복사 하려면이 함수를 호출 `CString` 요소 컬렉션 클래스 개체에 저장 됩니다.|
|[CStringElementTraits::Hash](#hash)|(정적) 지정 된 문자열 요소에 대 한 해시 값을 계산 하려면이 함수를 호출 합니다.|
|[CStringElementTraits::RelocateElements](#relocateelements)|(정적) 위치를 다시 지정 하려면이 함수를 호출 `CString` 요소 컬렉션 클래스 개체에 저장 됩니다.|

## <a name="remarks"></a>설명

이 클래스는 복사, 이동 및 문자열 비교에 대 한 고 해시 값을 만들기 위한 정적 함수를 제공 합니다. 이러한 함수는 문자열 기반 데이터를 저장 하는 컬렉션 클래스를 사용 하는 경우에 유용 합니다. 사용 하 여 [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md) 대/소문자 구분 비교가 필요한 경우. 사용 하 여 [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md) 문자열 개체 참조로 사용 하 여 처리 하려는 경우.

자세한 내용은 [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md)합니다.

## <a name="requirements"></a>요구 사항

**헤더:** cstringt.h

##  <a name="compareelements"></a>  CStringElementTraits::CompareElements

두 문자열 요소가 같은지를 비교 하려면이 정적 함수를 호출 합니다.

```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2);
```

### <a name="parameters"></a>매개 변수

*str1*<br/>
첫 번째 요소는 문자열입니다.

*str2*<br/>
두 번째 요소는 문자열입니다.

### <a name="return-value"></a>반환 값

요소가 같으면 false이 고, 그렇지 true를 반환 합니다.

##  <a name="compareelementsordered"></a>  CStringElementTraits::CompareElementsOrdered

두 문자열 요소를 비교 하려면이 정적 함수를 호출 합니다.

```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2);
```

### <a name="parameters"></a>매개 변수

*str1*<br/>
첫 번째 요소는 문자열입니다.

*str2*<br/>
두 번째 요소는 문자열입니다.

### <a name="return-value"></a>반환 값

< 0, 0이 문자열이 동일한 경우 경우 *str1* 는 보다 작은 *str2*, 또는 > 0 경우 *str1* 보다 크면 *str2*합니다. 합니다 [CStringT::Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare) 메서드는 비교를 수행 하는 데 사용 됩니다.

##  <a name="copyelements"></a>  CStringElementTraits::CopyElements

복사 하려면이 정적 함수를 호출 `CString` 요소 컬렉션 클래스 개체에 저장 됩니다.

```
static void CopyElements(
    T* pDest,
    const T* pSrc,
    size_t nElements);
```

### <a name="parameters"></a>매개 변수

*pDest*<br/>
복사한 데이터를 받을 첫 번째 요소에 대 한 포인터입니다.

*pSrc*<br/>
복사할 첫 번째 요소에 대 한 포인터입니다.

*nElements*<br/>
복사할 요소의 수입니다.

### <a name="remarks"></a>설명

원본 및 대상 요소를 겹치지 않아야 합니다.

##  <a name="hash"></a>  CStringElementTraits::Hash

지정 된 문자열 요소에 대 한 해시 값을 계산 하려면이 정적 함수를 호출 합니다.

```
static ULONG Hash(INARGTYPE str);
```

### <a name="parameters"></a>매개 변수

*str*<br/>
문자열 요소입니다.

### <a name="return-value"></a>반환 값

문자열의 내용을 사용 하 여 계산 된 해시 값을 반환 합니다.

##  <a name="inargtype"></a>  CStringElementTraits::INARGTYPE

컬렉션 클래스 개체에 요소를 추가 하는 데 데이터 형식입니다.

```
typedef T::PCXSTR INARGTYPE;
```

##  <a name="outargtype"></a>  CStringElementTraits::OUTARGTYPE

컬렉션 클래스 개체의 요소를 검색에 사용할 데이터 형식입니다.

```
typedef T& OUTARGTYPE;
```

##  <a name="relocateelements"></a>  CStringElementTraits::RelocateElements

위치를 다시 지정 하려면이 정적 함수를 호출 `CString` 요소 컬렉션 클래스 개체에 저장 됩니다.

```
static void RelocateElements(
    T* pDest,
    T* pSrc,
    size_t nElements);
```

### <a name="parameters"></a>매개 변수

*pDest*<br/>
위치가 변경 된 데이터를 받을 첫 번째 요소에 대 한 포인터입니다.

*pSrc*<br/>
재배치 첫 번째 요소에 대 한 포인터입니다.

*nElements*<br/>
재배치 요소의 수입니다.

### <a name="remarks"></a>설명

이 정적 함수 호출 [memmove](../../c-runtime-library/reference/memmove-wmemmove.md), 대부분의 데이터 형식에 대 한 충분 한 합니다. 이동할 개체를 해당 멤버에 대 한 포인터에 포함 되어이 정적 함수를 재정의 해야 합니다.

## <a name="see-also"></a>참고자료

[CElementTraitsBase 클래스](../../atl/reference/celementtraitsbase-class.md)<br/>
[CStringElementTraitsI 클래스](../../atl/reference/cstringelementtraitsi-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
