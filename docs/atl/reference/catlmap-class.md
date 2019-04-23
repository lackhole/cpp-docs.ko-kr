---
title: CAtlMap 클래스
ms.date: 11/04/2016
f1_keywords:
- CAtlMap
- ATLCOLL/ATL::CAtlMap
- ATLCOLL/ATL::CAtlMap::KINARGTYPE
- ATLCOLL/ATL::CAtlMap::KOUTARGTYPE
- ATLCOLL/ATL::CAtlMap::VINARGTYPE
- ATLCOLL/ATL::CAtlMap::VOUTARGTYPE
- ATLCOLL/ATL::CPair::m_key
- ATLCOLL/ATL::CPair::m_value
- ATLCOLL/ATL::CAtlMap::CAtlMap
- ATLCOLL/ATL::CAtlMap::AssertValid
- ATLCOLL/ATL::CAtlMap::DisableAutoRehash
- ATLCOLL/ATL::CAtlMap::EnableAutoRehash
- ATLCOLL/ATL::CAtlMap::GetAt
- ATLCOLL/ATL::CAtlMap::GetCount
- ATLCOLL/ATL::CAtlMap::GetHashTableSize
- ATLCOLL/ATL::CAtlMap::GetKeyAt
- ATLCOLL/ATL::CAtlMap::GetNext
- ATLCOLL/ATL::CAtlMap::GetNextAssoc
- ATLCOLL/ATL::CAtlMap::GetNextKey
- ATLCOLL/ATL::CAtlMap::GetNextValue
- ATLCOLL/ATL::CAtlMap::GetStartPosition
- ATLCOLL/ATL::CAtlMap::GetValueAt
- ATLCOLL/ATL::CAtlMap::InitHashTable
- ATLCOLL/ATL::CAtlMap::IsEmpty
- ATLCOLL/ATL::CAtlMap::Lookup
- ATLCOLL/ATL::CAtlMap::Rehash
- ATLCOLL/ATL::CAtlMap::RemoveAll
- ATLCOLL/ATL::CAtlMap::RemoveAtPos
- ATLCOLL/ATL::CAtlMap::RemoveKey
- ATLCOLL/ATL::CAtlMap::SetAt
- ATLCOLL/ATL::CAtlMap::SetOptimalLoad
- ATLCOLL/ATL::CAtlMap::SetValueAt
helpviewer_keywords:
- CAtlMap class
ms.assetid: 5e2fe028-8e6d-4686-93df-1433d2080ec3
ms.openlocfilehash: 1821532a4d5a3078202f180273b02945b8d8e4ba
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58774557"
---
# <a name="catlmap-class"></a>CAtlMap 클래스

이 클래스를 만들고 지도 개체를 관리 하기 위한 메서드를 제공 합니다.

## <a name="syntax"></a>구문

```
template <typename K,
          typename V,
          class KTraits = CElementTraits<K>,
          class VTraits = CElementTraits<V>>
class CAtlMap
```

#### <a name="parameters"></a>매개 변수

*K*<br/>
Key 요소 형식입니다.

*V*<br/>
값 요소 형식입니다.

*KTraits*<br/>
복사 하거나 주요 요소를 이동 하는 데 사용 되는 코드입니다. 참조 [CElementTraits 클래스](../../atl/reference/celementtraits-class.md) 대 한 자세한 내용은 합니다.

*VTraits*<br/>
값 요소 이동 하거나 복사 하는 데 사용 되는 코드입니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|이름|설명|
|----------|-----------------|
|[CAtlMap::KINARGTYPE](#kinargtype)|키를 입력 인수로 전달 될 때 사용 되는 형식|
|[CAtlMap::KOUTARGTYPE](#koutargtype)|키 출력 인수로 반환 될 때 사용 되는 형식입니다.|
|[CAtlMap::VINARGTYPE](#vinargtype)|값 입력 인수로 전달 될 때 사용 되는 형식입니다.|
|[CAtlMap::VOUTARGTYPE](#voutargtype)|값을 출력 인수로 전달 될 때 사용 되는 형식입니다.|

### <a name="public-classes"></a>public 클래스

|이름|설명|
|----------|-----------------|
|[CAtlMap::CPair 클래스](#cpair_class)|키 및 값 요소를 포함 하는 클래스입니다.|

### <a name="cpair-data-members"></a>CPair 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CPair::m_key](#m_key)|키 요소에 저장 하는 데이터 멤버입니다.|
|[CPair::m_value](#m_value)|Value 요소 저장 데이터 멤버입니다.|

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CAtlMap::CAtlMap](#catlmap)|생성자입니다.|
|[CAtlMap::~CAtlMap](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CAtlMap::AssertValid](#assertvalid)|경우 어설션이 발생할이 메서드를 호출 합니다 `CAtlMap` 올바르지 않습니다.|
|[CAtlMap::DisableAutoRehash](#disableautorehash)|자동 해싱하여 사용 하지 않도록 설정 하려면이 메서드는 `CAtlMap` 개체입니다.|
|[CAtlMap::EnableAutoRehash](#enableautorehash)|자동 해싱하여 사용 하도록 설정 하려면이 메서드를 호출 합니다 `CAtlMap` 개체입니다.|
|[CAtlMap::GetAt](#getat)|맵에서 지정된 된 위치에 있는 요소를 반환 하려면이 메서드를 호출 합니다.|
|[CAtlMap::GetCount](#getcount)|Map의 요소 수를 검색 하려면이 메서드를 호출 합니다.|
|[CAtlMap::GetHashTableSize](#gethashtablesize)|지도의 해시 테이블에서 bin의 수를 확인 하려면이 메서드를 호출 합니다.|
|[CAtlMap::GetKeyAt](#getkeyat)|지정된 된 위치에 저장 된 키를 검색 하려면이 메서드는 `CAtlMap` 개체입니다.|
|[CAtlMap::GetNext](#getnext)|쌍에 저장 된 다음 요소에 대 한 포인터를 가져오려면이 메서드를 호출 합니다 `CAtlMap` 개체입니다.|
|[CAtlMap::GetNextAssoc](#getnextassoc)|반복에 대 한 다음 요소를 가져옵니다.|
|[CAtlMap::GetNextKey](#getnextkey)|다음 키를 검색 하려면이 메서드는 `CAtlMap` 개체입니다.|
|[CAtlMap::GetNextValue](#getnextvalue)|다음 값을 가져오려면이 메서드를 호출 합니다 `CAtlMap` 개체입니다.|
|[CAtlMap::GetStartPosition](#getstartposition)|맵 반복을 시작 하려면이 메서드를 호출 합니다.|
|[CAtlMap::GetValueAt](#getvalueat)|지정 된 위치에 저장 된 값을 검색 하려면이 메서드는 `CAtlMap` 개체입니다.|
|[CAtlMap::InitHashTable](#inithashtable)|해시 테이블을 초기화 하려면이 메서드를 호출 합니다.|
|[CAtlMap::IsEmpty](#isempty)|이 메서드는 빈 map 개체에 대 한 테스트를 호출 합니다.|
|[CAtlMap::Lookup](#lookup)|키 또는 값을 조회 하려면이 메서드는 `CAtlMap` 개체입니다.|
|[CAtlMap::Rehash](#rehash)|Rehash 하려면이 메서드는 `CAtlMap` 개체입니다.|
|[CAtlMap::RemoveAll](#removeall)|모든 요소를 제거 하려면이 메서드는 `CAtlMap` 개체입니다.|
|[CAtlMap::RemoveAtPos](#removeatpos)|지정된 된 위치에 있는 요소를 제거 하려면이 메서드를 호출 합니다 `CAtlMap` 개체입니다.|
|[CAtlMap::RemoveKey](#removekey)|요소를 제거 하려면이 메서드를 호출 합니다 `CAtlMap` 키를 지정 된 개체입니다.|
|[CAtlMap::SetAt](#setat)|Map에 요소 쌍을 삽입 하려면이 메서드를 호출 합니다.|
|[CAtlMap::SetOptimalLoad](#setoptimalload)|최적의 부하를 설정 하려면이 메서드를 호출 합니다 `CAtlMap` 개체입니다.|
|[CAtlMap::SetValueAt](#setvalueat)|지정 된 위치에 저장 된 값을 변경 하려면이 메서드를 호출 합니다 `CAtlMap` 개체입니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CAtlMap::operator\[\]](catlmap-class.md#operator_at)|새 요소를 추가 하거나이 대체 합니다 `CAtlMap`합니다.|

## <a name="remarks"></a>설명

`CAtlMap` 관리 키 요소와 연결 된 값의 순서가 지정 되지 않은 배열을 지정 된 형식의 매핑 배열의 지원을 제공 합니다. (키 및 값 구성) 하는 요소는 많은 양의 데이터를 효율적으로 저장 하 고 검색할 수 있도록 해싱 알고리즘을 사용 하 여 저장 됩니다.

합니다 *KTraits* 하 고 *VTraits* 매개 변수는 복사 하거나 요소를 이동 하는 데 필요한 추가 코드를 포함 traits 클래스입니다.

대 안으로 `CAtlMap` 에서 제공 합니다 [CRBMap](../../atl/reference/crbmap-class.md) 클래스입니다. `CRBMap` 또한 키/값 쌍을 저장 하지만 다양 한 성능 특성을 나타냅니다. 키를 삭제 하거나 항목을 삽입 하는 데 걸리는 시간을 키 조회는 `CRBMap` 주문의 개체가 *log(n)* 여기서 *n* 요소입니다. 에 대 한 `CAtlMap`, 이러한 모든 작업 일반적으로 상수 시간이 걸릴 최악의 시나리오 주문의 수 있긴 *n*합니다. 일반적인 경우에 따라서 `CAtlMap` 더 빠릅니다.

또 다른 차이점 `CRBMap` 고 `CAtlMap` 저장된 요소를 통해 반복 하는 경우에 잘 드러납니다. 에 `CRBMap`, 정렬된 된 순서 대로 방문 하는 요소입니다. 에 `CAtlMap`, 요소는 정렬 되지 않는 및 순서 없이 유추할 수 있습니다.

적은 수의 요소를 저장 해야 하는 경우 사용을 고려 합니다 [CSimpleMap](../../atl/reference/csimplemap-class.md) 클래스를 대신 합니다.

자세한 내용은 [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md)합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlcoll.h

##  <a name="assertvalid"></a>  CAtlMap::AssertValid

경우 어설션이 발생할이 메서드를 호출 합니다 `CAtlMap` 개체가 잘못 되었습니다.

```
void AssertValid() const;
```

### <a name="remarks"></a>설명

디버그 빌드에서이 메서드를 ASSERT 경우 발생 합니다 `CAtlMap` 개체가 잘못 되었습니다.

### <a name="example"></a>예제

예를 참조 하세요 [CAtlMap::CAtlMap](#catlmap)합니다.

##  <a name="catlmap"></a>  CAtlMap::CAtlMap

생성자입니다.

```
CAtlMap(
    UINT nBins = 17,
    float fOptimalLoad = 0.75f,
    float fLoThreshold = 0.25f,
    float fHiThreshold = 2.25f,
    UINT nBlockSize = 10) throw ();
```

### <a name="parameters"></a>매개 변수

*nBins*<br/>
저장 된 요소에 대 한 포인터를 제공 하는 bin의 수입니다. Bin에 대 한 설명은이 항목의 뒷부분에 나오는 설명을 참조 하세요.

*fOptimalLoad*<br/>
최적의 부하 비율입니다.

*fLoThreshold*<br/>
부하 비율에 대 한 임계값입니다.

*fHiThreshold*<br/>
부하 비율에 대 한 상한 임계값입니다.

*nBlockSize*<br/>
블록 크기입니다.

### <a name="remarks"></a>설명

`CAtlMap` 첫 번째 키에 해시 알고리즘을 사용 하 여 인덱스를 만들어 모든 저장 된 요소를 참조 합니다. 이 인덱스는 저장 된 요소에 대 한 포인터를 포함 하는 "bin"를 참조 합니다. 휴지통에 이미 사용 중인 경우 후속 요소에 액세스 하는 연결 목록 만들어집니다. 올바른 요소에 직접 액세스 하는 보다 느립니다 목록을 트래버스 하며 따라서 맵 구조 성능에 대 한 저장소 요구 사항이 균형을 유지 합니다. 기본 매개 변수는 대부분의 경우에서 좋은 결과 제공 하도록 선택 되어 있습니다.

부하는 map 개체에 저장 된 요소의 수는 bin의 수의 비율이입니다. 맵 구조를 다시 계산할 때 합니다 *fOptimalLoad* 필요한 bin의 수를 계산 하려면 매개 변수 값이 사용 됩니다. 사용 하 여이 값을 변경할 수 있습니다 합니다 [CAtlMap::SetOptimalLoad](#setoptimalload) 메서드.

합니다 *fLoThreshold* 매개 변수는 로드 비율을 하기 전에 연결할 수 있는 더 낮은 값 `CAtlMap` 맵의 최적의 크기를 다시 계산 됩니다.

*fHiThreshold* 매개 변수는 로드 비율을 하기 전에 연결할 수 있는 상한 값을 `CAtlMap` 개체에는 map의 최적 크기 다시 계산 됩니다.

이 다시 계산 프로세스 (해싱하여 라고 함)는 기본적으로 사용 됩니다. 많은 양의 데이터가 한 번에 호출을 입력 하는 경우 아마도이 프로세스를 사용 하지 않으려는 경우 합니다 [CAtlMap::DisableAutoRehash](#disableautorehash) 메서드. 사용 하 여 다시 활성화 합니다 [CAtlMap::EnableAutoRehash](#enableautorehash) 메서드.

합니다 *nBlockSize* 매개 변수는 새 요소가 필요한 경우 할당 된 메모리 양 측정 한 것입니다. 블록 크기가 클수록 메모리 할당 루틴에 대 한 호출 줄어들지만 더 많은 리소스를 사용 합니다.

호출 하 여 해시 테이블을 초기화 해야 하는 모든 데이터를 저장할 수 있습니다, 전에 [CAtlMap::InitHashTable](#inithashtable)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#72](../../atl/codesnippet/cpp/catlmap-class_1.cpp)]

##  <a name="dtor"></a>  CAtlMap::~CAtlMap

소멸자입니다.

```
~CAtlMap() throw();
```

### <a name="remarks"></a>설명

할당 된 리소스를 해제 합니다.

##  <a name="cpair_class"></a>  CAtlMap::CPair 클래스

키 및 값 요소를 포함 하는 클래스입니다.

```
class CPair : public __POSITION
```

### <a name="remarks"></a>설명

이 클래스는 메서드를 사용한 [CAtlMap::GetNext](#getnext) 하 고 [CAtlMap::Lookup](#lookup) 매핑 구조에 저장 된 키 및 값 요소에 액세스 하려면.

##  <a name="disableautorehash"></a>  CAtlMap::DisableAutoRehash

자동 해싱하여 사용 하지 않도록 설정 하려면이 메서드는 `CAtlMap` 개체입니다.

```
void DisableAutoRehash() throw();
```

### <a name="remarks"></a>설명

자동 해싱하여 사용 하는 경우 (기본적으로 상태)는 해시 테이블에서 데이터 저장소 수가 자동으로 다시 계산 됩니다 (배열에 저장 된 요소의 수는 bin의 수의 비율)에 값 로드 최대값 또는 최소값 값을 초과 하는 경우 맵이 만들어진 시점에 지정 합니다.

`DisableAutoRehash` 가장 유용한 경우 한 번에 많은 수의 요소를 지도에 추가 됩니다. 제한을 초과 하는 때마다 rehashing 프로세스를 트리거하기, 대신 것이 효율적으로 호출할 `DisableAutoRehash`요소를 추가 하 고 마지막으로 호출 [CAtlMap::EnableAutoRehash](#enableautorehash)합니다.

##  <a name="enableautorehash"></a>  CAtlMap::EnableAutoRehash

자동 해싱하여 사용 하도록 설정 하려면이 메서드를 호출 합니다 `CAtlMap` 개체입니다.

```
void EnableAutoRehash() throw();
```

### <a name="remarks"></a>설명

자동 해싱하여 사용 하는 경우 (기본적으로 상태)는 해시 테이블에서 데이터 저장소 수가 자동으로 다시 계산 됩니다 (배열에 저장 된 요소의 수는 bin의 수의 비율)에 값 로드 최대값 또는 최소값 값을 초과 하는 경우 지도 만들 때에 지정 합니다.

`EnableAutoRefresh` 호출한 후에 가장 자주 [CAtlMap::DisableAutoRehash](#disableautorehash)합니다.

##  <a name="getat"></a>  CAtlMap::GetAt

맵에서 지정된 된 위치에 있는 요소를 반환 하려면이 메서드를 호출 합니다.

```
void GetAt(
    POSITION pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;

CPair* GetAt(POSITION& pos) throw();
```

### <a name="parameters"></a>매개 변수

*pos*<br/>
에 대 한 이전 호출에서 반환 되는 위치 카운터 [CAtlMap::GetNextAssoc](#getnextassoc) 하거나 [CAtlMap::GetStartPosition](#getstartposition)합니다.

*key*<br/>
템플릿 매개 변수 맵의 키의 형식을 지정 합니다.

*값*<br/>
템플릿 매개 변수 맵의 값의 형식을 지정 합니다.

### <a name="return-value"></a>반환 값

현재 map에 저장 된 키/값 요소의 쌍에 대 한 포인터를 반환 합니다.

### <a name="remarks"></a>설명

디버그 빌드에서 어설션 오류가 발생 하는 경우 *pos* NULL과 같습니다.

##  <a name="getcount"></a>  CAtlMap::GetCount

Map의 요소 수를 검색 하려면이 메서드를 호출 합니다.

```
size_t GetCount() const throw();
```

### <a name="return-value"></a>반환 값

Map 개체의 요소 수를 반환합니다. 단일 요소는 키/값 쌍입니다.

### <a name="example"></a>예제

예를 참조 하세요 [CAtlMap::CAtlMap](#catlmap)합니다.

##  <a name="gethashtablesize"></a>  CAtlMap::GetHashTableSize

지도의 해시 테이블에서 bin의 수를 확인 하려면이 메서드를 호출 합니다.

```
UINT GetHashTableSize() const throw();
```

### <a name="return-value"></a>반환 값

해시 테이블의 bin의 수를 반환합니다. 참조 [CAtlMap::CAtlMap](#catlmap) 설명 합니다.

##  <a name="getkeyat"></a>  CAtlMap::GetKeyAt

지정된 된 위치에 저장 된 키를 검색 하려면이 메서드는 `CAtlMap` 개체입니다.

```
const K& GetKeyAt(POSITION pos) const throw();
```

### <a name="parameters"></a>매개 변수

*pos*<br/>
에 대 한 이전 호출에서 반환 되는 위치 카운터 [CAtlMap::GetNextAssoc](#getnextassoc) 하거나 [CAtlMap::GetStartPosition](#getstartposition)합니다.

### <a name="return-value"></a>반환 값

지정된 된 위치에 저장 된 키에 대 한 참조를 반환 합니다 `CAtlMap` 개체입니다.

### <a name="example"></a>예제

예를 참조 하세요 [CAtlMap::CAtlMap](#catlmap)합니다.

##  <a name="getnext"></a>  CAtlMap::GetNext

쌍에 저장 된 다음 요소에 대 한 포인터를 가져오려면이 메서드를 호출 합니다 `CAtlMap` 개체입니다.

```
CPair* GetNext(POSITION& pos) throw();
const CPair* GetNext(POSITION& pos) const throw();
```

### <a name="parameters"></a>매개 변수

*pos*<br/>
에 대 한 이전 호출에서 반환 되는 위치 카운터 [CAtlMap::GetNextAssoc](#getnextassoc) 하거나 [CAtlMap::GetStartPosition](#getstartposition)합니다.

### <a name="return-value"></a>반환 값

Map에 저장 된 키/값 요소의 다음 쌍에 대 한 포인터를 반환 합니다. 합니다 *pos* 위치 카운터는 각 호출 후 업데이트 됩니다. 검색된 된 요소 맵에서 마지막 이면 *pos* NULL로 설정 됩니다.

##  <a name="getnextassoc"></a>  CAtlMap::GetNextAssoc

반복에 대 한 다음 요소를 가져옵니다.

```
void GetNextAssoc(
    POSITION& pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;
```

### <a name="parameters"></a>매개 변수

*pos*<br/>
에 대 한 이전 호출에서 반환 되는 위치 카운터 [CAtlMap::GetNextAssoc](#getnextassoc) 하거나 [CAtlMap::GetStartPosition](#getstartposition)합니다.

*key*<br/>
템플릿 매개 변수 맵의 키의 형식을 지정 합니다.

*값*<br/>
템플릿 매개 변수 맵의 값의 형식을 지정 합니다.

### <a name="remarks"></a>설명

합니다 *pos* 위치 카운터는 각 호출 후 업데이트 됩니다. 검색된 된 요소 맵에서 마지막 이면 *pos* NULL로 설정 됩니다.

##  <a name="getnextkey"></a>  CAtlMap::GetNextKey

다음 키를 검색 하려면이 메서드는 `CAtlMap` 개체입니다.

```
const K& GetNextKey(POSITION& pos) const throw();
```

### <a name="parameters"></a>매개 변수

*pos*<br/>
에 대 한 이전 호출에서 반환 되는 위치 카운터 [CAtlMap::GetNextAssoc](#getnextassoc) 하거나 [CAtlMap::GetStartPosition](#getstartposition)합니다.

### <a name="return-value"></a>반환 값

맵에서 다음 키에 대 한 참조를 반환합니다.

### <a name="remarks"></a>설명

현재 위치 카운터를 업데이트 *pos*합니다. 지도에 엔트리를 더 이상 없으면 위치 카운터가 NULL로 설정 됩니다.

##  <a name="getnextvalue"></a>  CAtlMap::GetNextValue

다음 값을 가져오려면이 메서드를 호출 합니다 `CAtlMap` 개체입니다.

```
V& GetNextValue(POSITION& pos) throw();
const V& GetNextValue(POSITION& pos) const throw();
```

### <a name="parameters"></a>매개 변수

*pos*<br/>
에 대 한 이전 호출에서 반환 되는 위치 카운터 [CAtlMap::GetNextAssoc](#getnextassoc) 하거나 [CAtlMap::GetStartPosition](#getstartposition)합니다.

### <a name="return-value"></a>반환 값

맵에서 다음 값에 대 한 참조를 반환합니다.

### <a name="remarks"></a>설명

현재 위치 카운터를 업데이트 *pos*합니다. 지도에 엔트리를 더 이상 없으면 위치 카운터가 NULL로 설정 됩니다.

### <a name="example"></a>예제

예를 참조 하세요 [CAtlMap::CAtlMap](#catlmap)합니다.

##  <a name="getstartposition"></a>  CAtlMap::GetStartPosition

맵 반복을 시작 하려면이 메서드를 호출 합니다.

```
POSITION GetStartPosition() const throw();
```

### <a name="return-value"></a>반환 값

Map이 비어 있으면 반환은 시작 위치 또는 NULL을 반환 합니다.

### <a name="remarks"></a>설명

호출 된 위치를 반환 하 여 맵 반복을 시작 하려면이 메서드는 값을 전달할 수는 `GetNextAssoc` 메서드.

> [!NOTE]
>  반복 시퀀스를 예측할 수 없는 경우

### <a name="example"></a>예제

예를 참조 하세요 [CAtlMap::CAtlMap](#catlmap)합니다.

##  <a name="getvalueat"></a>  CAtlMap::GetValueAt

지정 된 위치에 저장 된 값을 검색 하려면이 메서드는 `CAtlMap` 개체입니다.

```
V& GetValueAt(POSITION pos) throw();
const V& GetValueAt(POSITION pos) const throw();
```

### <a name="parameters"></a>매개 변수

*pos*<br/>
에 대 한 이전 호출에서 반환 되는 위치 카운터 [CAtlMap::GetNextAssoc](#getnextassoc) 하거나 [CAtlMap::GetStartPosition](#getstartposition)합니다.

### <a name="return-value"></a>반환 값

지정된 된 위치에 저장 된 값에 대 한 참조를 반환 합니다 `CAtlMap` 개체입니다.

##  <a name="inithashtable"></a>  CAtlMap::InitHashTable

해시 테이블을 초기화 하려면이 메서드를 호출 합니다.

```
bool InitHashTable(
    UINT nBins,
    bool bAllocNow = true);
```

### <a name="parameters"></a>매개 변수

*nBins*<br/>
해시 테이블에서 사용 하는 bin의 수입니다. 참조 [CAtlMap::CAtlMap](#catlmap) 설명 합니다.

*bAllocNow*<br/>
메모리를 할당 해야 하는 경우 플래그 나타냅니다.

### <a name="return-value"></a>반환 값

성공적인 초기화에 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

`InitHashTable` 요소는 해시 테이블에 저장 되기 전에 호출 해야 합니다.  이 메서드를 명시적으로 호출 하지 않으면, 호출 됩니다 자동으로 하면 요소가 지정 된 bin 개수를 사용 하 여 추가 되어 처음으로 `CAtlMap` 생성자입니다.  지정 된 새 bin 개수를 사용 하 여 지도 초기화이 고, 그렇지 합니다 *nBins* 매개 변수입니다.

경우는 *bAllocNow* 매개 변수가 false 인, 해시 테이블에 필요한 메모리는 필요한 먼저 될 때까지 할당 되지 것입니다. 이 지도 사용할 경우 특정 경우에 유용할 수 있습니다.

### <a name="example"></a>예제

예를 참조 하세요 [CAtlMap::CAtlMap](#catlmap)합니다.

##  <a name="isempty"></a>  CAtlMap::IsEmpty

이 메서드는 빈 map 개체에 대 한 테스트를 호출 합니다.

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>반환 값

지도 경우 비어 있는 경우 FALSE이 고, 그렇지 TRUE를 반환 합니다.

##  <a name="kinargtype"></a>  CAtlMap::KINARGTYPE

키를 입력 인수로 전달 될 때 사용 되는 형식입니다.

```
typedef KTraits::INARGTYPE KINARGTYPE;
```

##  <a name="koutargtype"></a>  CAtlMap::KOUTARGTYPE

키 출력 인수로 반환 될 때 사용 되는 형식입니다.

```
typedef KTraits::OUTARGTYPE KOUTARGTYPE;
```

##  <a name="lookup"></a>  CAtlMap::Lookup

키 또는 값을 조회 하려면이 메서드는 `CAtlMap` 개체입니다.

```
bool Lookup(KINARGTYPE key, VOUTARGTYPE value) const;
const CPair* Lookup(KINARGTYPE key) const throw();
CPair* Lookup(KINARGTYPE key) throw();
```

### <a name="parameters"></a>매개 변수

*key*<br/>
조회 요소를 식별 하는 키를 지정 합니다.

*값*<br/>
조회 값을 수신 하는 변수입니다.

### <a name="return-value"></a>반환 값

메서드의 첫 번째 형태는 키 발견 되 면 true, 그렇지 않으면 false를 반환 합니다. 두 번째 및 세 번째 폼에 대 한 포인터를 반환 된 [CPair](#cpair_class) 사용할 수 있는 위치로 대 한 호출 [CAtlMap::GetNext](#getnext) 등.

### <a name="remarks"></a>설명

`Lookup` 해시 알고리즘을를 사용 하 여 신속 하 게 정확 하 게 제공된 된 키 매개 변수와 일치 하는 키가 포함 된 지도 요소를 찾습니다.

##  <a name="operator_at"></a>  CAtlMap::operator \[\]

새 요소를 추가 하거나이 대체 합니다 `CAtlMap`합니다.

```
V& operator[](kinargtype key) throw();
```

### <a name="parameters"></a>매개 변수

*key*<br/>
키를 추가 하거나 바꿀 요소입니다.

### <a name="return-value"></a>반환 값

지정된 된 키와 연결 된 값에 대 한 참조를 반환 합니다.

### <a name="example"></a>예제

키가 이미 있는 경우 요소가 바뀝니다. 키가 없으면 새 요소가 추가 됩니다. 예를 참조 하세요 [CAtlMap::CAtlMap](#catlmap)합니다.

##  <a name="rehash"></a>  CAtlMap::Rehash

Rehash 하려면이 메서드는 `CAtlMap` 개체입니다.

```
void Rehash(UINT nBins = 0);
```

### <a name="parameters"></a>매개 변수

*nBins*<br/>
새 해시 테이블에서 사용 하는 bin 수입니다. 참조 [CAtlMap::CAtlMap](#catlmap) 설명 합니다.

### <a name="remarks"></a>설명

하는 경우 *nBins* 가 0 이면 `CAtlMap` 된 데이터베이스 맵 및 최적의 부하 설정의 요소 수에 따라 적절 한 수를 계산 합니다. 일반적으로 rehashing 프로세스는 자동으로 경우에 [CAtlMap::DisableAutoRehash](#disableautorehash) 되었습니다 호출이 메서드는 필요한 크기를 조정 수행 됩니다.

##  <a name="removeall"></a>  CAtlMap::RemoveAll

모든 요소를 제거 하려면이 메서드는 `CAtlMap` 개체입니다.

```
void RemoveAll() throw();
```

### <a name="remarks"></a>설명

지웁니다는 `CAtlMap` 개체에 요소를 저장 하는 데 사용 된 메모리를 해제 합니다.

##  <a name="removeatpos"></a>  CAtlMap::RemoveAtPos

지정된 된 위치에 있는 요소를 제거 하려면이 메서드를 호출 합니다 `CAtlMap` 개체입니다.

```
void RemoveAtPos(POSITION pos) throw();
```

### <a name="parameters"></a>매개 변수

*pos*<br/>
에 대 한 이전 호출에서 반환 되는 위치 카운터 [CAtlMap::GetNextAssoc](#getnextassoc) 하거나 [CAtlMap::GetStartPosition](#getstartposition)합니다.

### <a name="remarks"></a>설명

지정된 된 위치에 저장 된 키/값 쌍을 제거 합니다. 요소를 저장 하는 데 메모리 해제 됩니다. 참조 하는 위치 *pos* 무효화 되 고 맵의 다른 요소의 위치 유효한 반드시 수행 하는 동안 동일한 순서를 유지 합니다.

##  <a name="removekey"></a>  CAtlMap::RemoveKey

요소를 제거 하려면이 메서드를 호출 합니다 `CAtlMap` 키를 지정 된 개체입니다.

```
bool RemoveKey(KINARGTYPE key) throw();
```

### <a name="parameters"></a>매개 변수

*key*<br/>
제거 하려는 키에 해당 하는 요소 쌍입니다.

### <a name="return-value"></a>반환 값

키가 발견 및 제거, 실패 시 FALSE 경우 TRUE를 반환 합니다.

### <a name="example"></a>예제

예를 참조 하세요 [CAtlMap::CAtlMap](#catlmap)합니다.

##  <a name="setat"></a>  CAtlMap::SetAt

Map에 요소 쌍을 삽입 하려면이 메서드를 호출 합니다.

```
POSITION SetAt(
    KINARGTYPE key,
    VINARGTYPE value);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
추가할 키 값을 `CAtlMap` 개체입니다.

*값*<br/>
에 추가할 값을 `CAtlMap` 개체입니다.

### <a name="return-value"></a>반환 값

에 있는 키/값 요소 쌍의 위치를 반환 합니다 `CAtlMap` 개체입니다.

### <a name="remarks"></a>설명

`SetAt` 일치 하는 키가 있을 경우 기존 요소를 바꿉니다. 키가 없는 경우 새 키/값 쌍이 생성 됩니다.

##  <a name="setoptimalload"></a>  CAtlMap::SetOptimalLoad

최적의 부하를 설정 하려면이 메서드를 호출 합니다 `CAtlMap` 개체입니다.

```
void SetOptimalLoad(
    float fOptimalLoad,
    float fLoThreshold,
    float fHiThreshold,
    bool bRehashNow = false);
```

### <a name="parameters"></a>매개 변수

*fOptimalLoad*<br/>
최적의 부하 비율입니다.

*fLoThreshold*<br/>
부하 비율에 대 한 임계값입니다.

*fHiThreshold*<br/>
부하 비율에 대 한 상한 임계값입니다.

*bRehashNow*<br/>
해시 테이블을 다시 계산 해야 하는 경우를 나타내는 플래그입니다.

### <a name="remarks"></a>설명

최적의 부하 값을 다시 정의 `CAtlMap` 개체입니다. 참조 [CAtlMap::CAtlMap](#catlmap) 여러 매개 변수에 대 한 내용은 합니다. 하는 경우 *bRehashNow* 가 true 이면 요소 수는 최소 및 최대 값을 외부를 해시 테이블을 다시 계산 됩니다.

##  <a name="setvalueat"></a>  CAtlMap::SetValueAt

지정 된 위치에 저장 된 값을 변경 하려면이 메서드를 호출 합니다 `CAtlMap` 개체입니다.

```
void SetValueAt(
    POSITION pos,
    VINARGTYPE value);
```

### <a name="parameters"></a>매개 변수

*pos*<br/>
에 대 한 이전 호출에서 반환 되는 위치 카운터 [CAtlMap::GetNextAssoc](#getnextassoc) 하거나 [CAtlMap::GetStartPosition](#getstartposition)합니다.

*값*<br/>
에 추가할 값을 `CAtlMap` 개체입니다.

### <a name="remarks"></a>설명

지정된 된 위치에 저장 된 값 요소를 변경 합니다 `CAtlMap` 개체입니다.

##  <a name="vinargtype"></a>  CAtlMap::VINARGTYPE

값 입력 인수로 전달 될 때 사용 되는 형식입니다.

```
typedef VTraits::INARGTYPE VINARGTYPE;
```

##  <a name="voutargtype"></a>  CAtlMap::VOUTARGTYPE

값을 출력 인수로 전달 될 때 사용 되는 형식입니다.

```
typedef VTraits::OUTARGTYPE VOUTARGTYPE;
```

##  <a name="m_key"></a>  CAtlMap::CPair::m_key

키 요소에 저장 하는 데이터 멤버입니다.

```
const K m_key;
```

### <a name="parameters"></a>매개 변수

*K*<br/>
Key 요소 형식입니다.

##  <a name="m_value"></a>  CAtlMap::CPair::m_value

Value 요소 저장 데이터 멤버입니다.

```
V  m_value;
```

### <a name="parameters"></a>매개 변수

*V*<br/>
값 요소 형식입니다.

## <a name="see-also"></a>참고자료

[움직이는 텍스트 샘플](../../overview/visual-cpp-samples.md)<br/>
[UpdatePV 샘플](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
