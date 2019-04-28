---
title: CSimpleMap 클래스
ms.date: 11/04/2016
f1_keywords:
- CSimpleMap
- ATLSIMPCOLL/ATL::CSimpleMap
- ATLSIMPCOLL/ATL::CSimpleMap::_ArrayElementType
- ATLSIMPCOLL/ATL::CSimpleMap::_ArrayKeyType
- ATLSIMPCOLL/ATL::CSimpleMap::CSimpleMap
- ATLSIMPCOLL/ATL::CSimpleMap::Add
- ATLSIMPCOLL/ATL::CSimpleMap::FindKey
- ATLSIMPCOLL/ATL::CSimpleMap::FindVal
- ATLSIMPCOLL/ATL::CSimpleMap::GetKeyAt
- ATLSIMPCOLL/ATL::CSimpleMap::GetSize
- ATLSIMPCOLL/ATL::CSimpleMap::GetValueAt
- ATLSIMPCOLL/ATL::CSimpleMap::Lookup
- ATLSIMPCOLL/ATL::CSimpleMap::Remove
- ATLSIMPCOLL/ATL::CSimpleMap::RemoveAll
- ATLSIMPCOLL/ATL::CSimpleMap::RemoveAt
- ATLSIMPCOLL/ATL::CSimpleMap::ReverseLookup
- ATLSIMPCOLL/ATL::CSimpleMap::SetAt
- ATLSIMPCOLL/ATL::CSimpleMap::SetAtIndex
helpviewer_keywords:
- CSimpleMap class
ms.assetid: 61b06eb4-ae73-44b0-a305-0afb5a33e8b1
ms.openlocfilehash: afd9f017bb0fb9a95a0ed4fd135dcbd5ea4ddba2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62277944"
---
# <a name="csimplemap-class"></a>CSimpleMap 클래스

이 클래스는 단순한 매핑 배열에 대 한 지원을 제공합니다.

## <a name="syntax"></a>구문

```
template <class TKey, class TVal, class TEqual = CSimpleMapEqualHelper<TKey, TVal>>
class CSimpleMap
```

#### <a name="parameters"></a>매개 변수

*TKey*<br/>
Key 요소 형식입니다.

*TVal*<br/>
값 요소 형식입니다.

*TEqual*<br/>
형식의 요소에 대 한 같음 테스트를 정의 하는 특성 (trait) 개체 `T`합니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|이름|설명|
|----------|-----------------|
|[CSimpleMap::_ArrayElementType](#_arrayelementtype)|값 형식에 대 한 Typedef입니다.|
|[CSimpleMap::_ArrayKeyType](#_arraykeytype)|키 형식에 대 한 Typedef입니다.|

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CSimpleMap::CSimpleMap](#csimplemap)|생성자입니다.|
|[CSimpleMap::~CSimpleMap](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CSimpleMap::Add](#add)|맵 배열에 키와 연결 된 값을 추가합니다.|
|[CSimpleMap::FindKey](#findkey)|특정 키를 찾습니다.|
|[CSimpleMap::FindVal](#findval)|특정 값을 찾습니다.|
|[CSimpleMap::GetKeyAt](#getkeyat)|지정된 된 키를 검색합니다.|
|[CSimpleMap::GetSize](#getsize)|매핑 배열의 항목 수를 반환합니다.|
|[CSimpleMap::GetValueAt](#getvalueat)|지정된 된 값을 검색합니다.|
|[CSimpleMap::Lookup](#lookup)|지정된 된 키와 연결 된 값을 반환 합니다.|
|[CSimpleMap::Remove](#remove)|키와 일치 하는 값을 제거 합니다.|
|[CSimpleMap::RemoveAll](#removeall)|모든 키와 값을 제거합니다.|
|[CSimpleMap::RemoveAt](#removeat)|특정 키와 일치 하는 값을 제거합니다.|
|[CSimpleMap::ReverseLookup](#reverselookup)|지정된 된 값을 사용 하 여 연결 된 키를 반환 합니다.|
|[CSimpleMap::SetAt](#setat)|지정된 된 키와 연결 된 값을 설정 합니다.|
|[CSimpleMap::SetAtIndex](#setatindex)|특정 키와 값을 설정 합니다.|

## <a name="remarks"></a>설명

`CSimpleMap` 지정 된 형식의 단순한 매핑 배열에 대 한 지원을 제공 `T`, 주요 요소 및 연결 된 값의 순서가 지정 되지 않은 배열을 관리 합니다.

매개 변수 `TEqual` 형식의 두 요소에 대 한 같음 함수를 정의 하는 수단을 제공 `T`합니다. 클래스를 만들어 비슷합니다 [CSimpleMapEqualHelper](../../atl/reference/csimplemapequalhelper-class.md), 지정 된 배열에 대 한 같음 테스트의 동작을 변경 하는 것이 가능 합니다. 예를 들어, 포인터 배열을 처리할 때 포인터 참조 값에 따라으로 같음을 정의에 유용할 수 있습니다. 기본 구현은 활용 **operator==()** 합니다.

둘 다 `CSimpleMap` 하 고 [CSimpleArray](../../atl/reference/csimplearray-class.md) 릴리스는 이전 ATL 사용 하 여 호환성 및에서 제공 하는 완전 하 고 효율적인 컬렉션 구현을 제공 됩니다 [CAtlArray](../../atl/reference/catlarray-class.md) 하고[ CAtlMap](../../atl/reference/catlmap-class.md)합니다.

ATL 및 MFC에서 다른 맵 컬렉션과 달리이 클래스는 간단한 배열을 사용 하 여 구현 됩니다 및 조회 검색 선형 검색을 요구 합니다. `CAtlMap` 배열에는 많은 수의 요소를 포함 하는 경우 사용 해야 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlsimpcoll.h

## <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#91](../../atl/codesnippet/cpp/csimplemap-class_1.cpp)]

##  <a name="add"></a>  CSimpleMap::Add

맵 배열에 키와 연결 된 값을 추가합니다.

```
BOOL Add(const TKey& key, const TVal& val);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
키입니다.

*val*<br/>
연결 된 값입니다.

### <a name="return-value"></a>반환 값

경우 키와 값을 된 추가 했습니다.이 고, FALSE 그렇지 않은 경우 TRUE를 반환 합니다.

### <a name="remarks"></a>설명

각 키 / 값 쌍 원인 매핑을 배열 해제 되어 다시 할당, 각각에 대 한 데이터는 항상 연속적으로 저장을 보장 하기 위해 메모리를 추가 합니다. 즉, 두 번째 주요 요소 항상 바로 뒤에 오는 첫 번째 키 요소 메모리 등.

##  <a name="_arrayelementtype"></a>  CSimpleMap::_ArrayElementType

키 형식에 대 한 typedef입니다.

```
typedef TVal _ArrayElementType;
```

##  <a name="_arraykeytype"></a>  CSimpleMap::_ArrayKeyType

값 형식에 대 한 typedef입니다.

```
typedef TKey _ArrayKeyType;
```

##  <a name="csimplemap"></a>  CSimpleMap::CSimpleMap

생성자입니다.

```
CSimpleMap();
```

### <a name="remarks"></a>설명

데이터 멤버를 초기화합니다.

##  <a name="dtor"></a>  CSimpleMap::~CSimpleMap

소멸자입니다.

```
~CSimpleMap();
```

### <a name="remarks"></a>설명

할당 된 모든 리소스를 해제합니다.

##  <a name="findkey"></a>  CSimpleMap::FindKey

특정 키를 찾습니다.

```
int FindKey(const TKey& key) const;
```

### <a name="parameters"></a>매개 변수

*key*<br/>
검색할 키입니다.

### <a name="return-value"></a>반환 값

그렇지 않으면 찾을 경우 키의 인덱스를 반환 합니다-1을 반환 합니다.

##  <a name="findval"></a>  CSimpleMap::FindVal

특정 값을 찾습니다.

```
int FindVal(const TVal& val) const;
```

### <a name="parameters"></a>매개 변수

*val*<br/>
검색할 값입니다.

### <a name="return-value"></a>반환 값

반환 값의 인덱스 이며 그렇지 않으면-1을 반환 합니다.

##  <a name="getkeyat"></a>  CSimpleMap::GetKeyAt

지정된 된 인덱스에 키를 검색합니다.

```
TKey& GetKeyAt(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
반환할 키의 인덱스입니다.

### <a name="return-value"></a>반환 값

참조 하는 키를 반환 *nIndex*합니다.

### <a name="remarks"></a>설명

전달 된 인덱스가 *nIndex* 의미 있는 반환 값에 대해 유효 해야 합니다.

##  <a name="getsize"></a>  CSimpleMap::GetSize

매핑 배열의 항목 수를 반환합니다.

```
int GetSize() const;
```

### <a name="return-value"></a>반환 값

매핑 배열의 (키와 값은 하나의 항목) 항목의 수를 반환 합니다.

##  <a name="getvalueat"></a>  CSimpleMap::GetValueAt

특정 인덱스의 값을 검색합니다.

```
TVal& GetValueAt(int nIndex) const;
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
반환할 값의 인덱스입니다.

### <a name="return-value"></a>반환 값

참조 하는 값 반환 *nIndex*합니다.

### <a name="remarks"></a>설명

전달 된 인덱스가 *nIndex* 의미 있는 반환 값에 대해 유효 해야 합니다.

##  <a name="lookup"></a>  CSimpleMap::Lookup

지정된 된 키와 연결 된 값을 반환 합니다.

```
TVal Lookup(const TKey& key) const;
```

### <a name="parameters"></a>매개 변수

*key*<br/>
키입니다.

### <a name="return-value"></a>반환 값

연결된 된 값을 반환합니다. NULL, 일치 하는 키가 없으면 반환 됩니다.

##  <a name="remove"></a>  CSimpleMap::Remove

키와 일치 하는 값을 제거 합니다.

```
BOOL Remove(const TKey& key);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
키입니다.

### <a name="return-value"></a>반환 값

경우 키 및 값이 일치 된 제거 했습니다.이 고, FALSE 그렇지 않은 경우 TRUE를 반환 합니다.

##  <a name="removeall"></a>  CSimpleMap::RemoveAll

모든 키와 값을 제거합니다.

```
void RemoveAll();
```

### <a name="remarks"></a>설명

매핑 배열 개체에서 모든 키와 값을 제거합니다.

##  <a name="removeat"></a>  CSimpleMap::RemoveAt

키와 지정된 된 인덱스에 연관 된 값을 제거 합니다.

```
BOOL RemoveAt(int nIndex);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
키 및 제거 하려면 연결 된 값의 인덱스입니다.

### <a name="return-value"></a>반환 값

없으면 TRUE 성공 하면 FALSE 잘못 된 인덱스가 지정 된 인덱스입니다.

##  <a name="reverselookup"></a>  CSimpleMap::ReverseLookup

지정된 된 값을 사용 하 여 연결 된 키를 반환 합니다.

```
TKey ReverseLookup(const TVal& val) const;
```

### <a name="parameters"></a>매개 변수

*val*<br/>
값입니다.

### <a name="return-value"></a>반환 값

연결 된 키를 반환합니다. NULL, 일치 하는 키가 없으면 반환 됩니다.

##  <a name="setat"></a>  CSimpleMap::SetAt

지정된 된 키와 연결 된 값을 설정 합니다.

```
BOOL SetAt(const TKey& key, const TVal& val);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
키입니다.

*val*<br/>
할당할 새 값입니다.

### <a name="return-value"></a>반환 값

키를 찾을 수와 그렇지 않은 경우 값이 FALSE로 설정 했습니다. 변경 된 경우 TRUE를 반환 합니다.

##  <a name="setatindex"></a>  CSimpleMap::SetAtIndex

지정된 된 인덱스에서 키와 값을 설정합니다.

```
BOOL SetAtIndex(
    int nIndex,
    const TKey& key,
    const TVal& val);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
키와 값을 변경 하려면 연결을 참조 하는 인덱스입니다.

*key*<br/>
새 키입니다.

*val*<br/>
새 값입니다.

### <a name="return-value"></a>반환 값

경우 TRUE를 반환 성공적이 고 FALSE 인덱스가 잘못 되었습니다.

### <a name="remarks"></a>설명

키와 가리키는 값을 업데이트 *nIndex*합니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)
