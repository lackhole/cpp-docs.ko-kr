---
title: CRBMultiMap 클래스
ms.date: 11/04/2016
f1_keywords:
- CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap::CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap::FindFirstWithKey
- ATLCOLL/ATL::CRBMultiMap::GetNextValueWithKey
- ATLCOLL/ATL::CRBMultiMap::GetNextWithKey
- ATLCOLL/ATL::CRBMultiMap::Insert
- ATLCOLL/ATL::CRBMultiMap::RemoveKey
helpviewer_keywords:
- CRBMultiMap class
ms.assetid: 94d3ec0c-3e30-4ab7-a101-d8da4fb8add3
ms.openlocfilehash: 03a9639e8b0b3d11a414e5db0ce874d7ca8f2d45
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62278139"
---
# <a name="crbmultimap-class"></a>CRBMultiMap 클래스

이 클래스는 각 키 빨강-검정 이진 트리를 사용 하 여 둘 이상의 값을 사용 하 여 연결할 수 있게 하는 매핑 구조를 나타냅니다.

## <a name="syntax"></a>구문

```
template<typename K,
         typename V,
         class KTraits = CElementTraits<K>,
         class VTraits = CElementTraits<V>>
class CRBMultiMap : public CRBTree<K, V, KTraits, VTraits>
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

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CRBMultiMap::CRBMultiMap](#crbmultimap)|생성자입니다.|
|[CRBMultiMap::~CRBMultiMap](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CRBMultiMap::FindFirstWithKey](#findfirstwithkey)|지정된 된 키를 사용 하 여 첫 번째 요소의 위치를 찾으려면이 메서드를 호출 합니다.|
|[CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey)|지정된 된 키와 연결 된 값을 가져오려면이 메서드를 호출 하 고 위치 값을 업데이트 합니다.|
|[CRBMultiMap::GetNextWithKey](#getnextwithkey)|지정된 된 키와 연결 된 요소를 가져오려면이 메서드를 호출 하 고 위치 값을 업데이트 합니다.|
|[CRBMultiMap::Insert](#insert)|Map에 요소 쌍을 삽입 하려면이 메서드를 호출 합니다.|
|[CRBMultiMap::RemoveKey](#removekey)|모든 지정된 된 키에 대 한 키/값 요소를 제거 하려면이 메서드를 호출 합니다.|

## <a name="remarks"></a>설명

`CRBMultiMap` 지정된 된 형식의 관리 되는 주요 요소 및 값의 순서 있는 배열 매핑 배열에 지원을 제공 합니다. 와 달리 합니다 [CRBMap](../../atl/reference/crbmap-class.md) 클래스, 각 키 둘 이상의 값을 사용 하 여 연결할 수 있습니다.

이진 트리 (키 및 값 구성) 요소가 저장 되 구조체를 사용 하 여 [CRBMultiMap::Insert](#insert) 메서드. 사용 하 여 요소를 제거할 수 있습니다 합니다 [CRBMultiMap::RemoveKey](#removekey) 메서드를 지정된 된 키와 일치 하는 모든 요소를 삭제 합니다.

트리를 이동 가능 메서드를 사용 하 여 같은 [CRBTree::GetHeadPosition](../../atl/reference/crbtree-class.md#getheadposition)하십시오 [CRBTree::GetNext](../../atl/reference/crbtree-class.md#getnext), 및 [CRBTree::GetNextValue](../../atl/reference/crbtree-class.md#getnextvalue)합니다. 에 액세스 하는 키 당 잠재적으로 여러 값 가능한 사용 하는 [CRBMultiMap::FindFirstWithKey](#findfirstwithkey), [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey), 및 [CRBMultiMap::GetNextWithKey ](#getnextwithkey) 메서드. 예를 참조 하세요 [CRBMultiMap::CRBMultiMap](#crbmultimap) 실제로 예시입니다.

합니다 *KTraits* 하 고 *VTraits* 매개 변수는 복사 하거나 요소를 이동 하는 데 필요한 추가 코드를 포함 traits 클래스입니다.

`CRBMultiMap` 파생 됩니다 [CRBTree](../../atl/reference/crbtree-class.md), 빨강-검정 알고리즘을 사용 하 여 이진 트리를 구현 하는 합니다. 대 안으로 `CRBMultiMap` 하 고 `CRBMap` 에서 제공 하는 합니다 [CAtlMap](../../atl/reference/catlmap-class.md) 클래스. 소수의 요소를 저장 해야 하는 경우 사용을 고려 합니다 [CSimpleMap](../../atl/reference/csimplemap-class.md) 클래스를 대신 합니다.

자세한 내용은 다양 한 컬렉션 클래스 및 해당 기능 및 성능 특성에 대 한 참조 [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CRBTree](../../atl/reference/crbtree-class.md)

`CRBMultiMap`

## <a name="requirements"></a>요구 사항

**헤더:** atlcoll.h

##  <a name="crbmultimap"></a>  CRBMultiMap::CRBMultiMap

생성자입니다.

```
explicit CRBMultiMap(size_t nBlockSize = 10) throw();
```

### <a name="parameters"></a>매개 변수

*nBlockSize*<br/>
블록 크기입니다.

### <a name="remarks"></a>설명

합니다 *nBlockSize* 매개 변수는 새 요소가 필요한 경우 할당 된 메모리 양 측정 한 것입니다. 블록 크기가 클수록 메모리 할당 루틴에 대 한 호출 줄어들지만 더 많은 리소스를 사용 합니다. 기본값을 한 번에 10 요소에 대 한 공간을 할당 됩니다.

기본 클래스에 대 한 설명서를 참조 하세요 [CRBTree](../../atl/reference/crbtree-class.md) 사용할 수 있는 다른 방법에 대 한 정보에 대 한 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_Utilities#85](../../atl/codesnippet/cpp/crbmultimap-class_1.cpp)]

##  <a name="dtor"></a>  CRBMultiMap::~CRBMultiMap

소멸자입니다.

```
~CRBMultiMap() throw();
```

### <a name="remarks"></a>설명

할당 된 리소스를 해제 합니다.

기본 클래스에 대 한 설명서를 참조 하세요 [CRBTree](../../atl/reference/crbtree-class.md) 사용할 수 있는 다른 방법에 대 한 정보에 대 한 합니다.

##  <a name="findfirstwithkey"></a>  CRBMultiMap::FindFirstWithKey

지정된 된 키를 사용 하 여 첫 번째 요소의 위치를 찾으려면이 메서드를 호출 합니다.

```
POSITION FindFirstWithKey(KINARGTYPE key) const throw();
```

### <a name="parameters"></a>매개 변수

*key*<br/>
찾을 요소를 식별 하는 키를 지정 합니다.

### <a name="return-value"></a>반환 값

키가 있으면 NULL이 고, 그렇지 첫 번째 키/값 요소의 위치를 반환 합니다.

### <a name="remarks"></a>설명

키에는 `CRBMultiMap` 하나 이상의 연결 된 값을 가질 수 있습니다. 이 메서드는 해당 특정 키와 연결 된 첫 번째 값 (일 수 있음, 실제로 유일한 값)의 위치 값을 제공 합니다. 반환 되는 위치 값으로 사용할 수 있습니다 [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey) 하거나 [CRBMultiMap::GetNextWithKey](#getnextwithkey) 값을 가져올 위치를 업데이트 하 합니다.

기본 클래스에 대 한 설명서를 참조 하세요 [CRBTree](../../atl/reference/crbtree-class.md) 사용할 수 있는 다른 방법에 대 한 정보에 대 한 합니다.

### <a name="example"></a>예제

예를 참조 하세요 [CRBMultiMap::CRBMultiMap](#crbmultimap)합니다.

##  <a name="getnextvaluewithkey"></a>  CRBMultiMap::GetNextValueWithKey

지정된 된 키와 연결 된 값을 가져오려면이 메서드를 호출 하 고 위치 값을 업데이트 합니다.

```
const V& GetNextValueWithKey(
    POSITION& pos,
    KINARGTYPE key) const throw();
V& GetNextValueWithKey(
    POSITION& pos,
    KINARGTYPE key) throw();
```

### <a name="parameters"></a>매개 변수

*pos*<br/>
에 대 한 호출을 사용 하 여 얻은 위치 값을 [CRBMultiMap::FindFirstWithKey](#findfirstwithkey) 또는 [CRBMultiMap::GetNextWithKey](#getnextwithkey)에 대 한 이전 호출 또는 `GetNextValueWithKey`합니다.

*key*<br/>
찾을 요소를 식별 하는 키를 지정 합니다.

### <a name="return-value"></a>반환 값

지정된 된 키와 연결 된 요소 쌍을 반환 합니다.

### <a name="remarks"></a>설명

위치 값을 키에 연결 된 다음 값을 가리키도록 업데이트 됩니다. 값이 더 이상 없으면 위치 값이 NULL로 설정 됩니다.

기본 클래스에 대 한 설명서를 참조 하세요 [CRBTree](../../atl/reference/crbtree-class.md) 사용할 수 있는 다른 방법에 대 한 정보에 대 한 합니다.

### <a name="example"></a>예제

예를 참조 하세요 [CRBMultiMap::CRBMultiMap](#crbmultimap)합니다.

##  <a name="getnextwithkey"></a>  CRBMultiMap::GetNextWithKey

지정된 된 키와 연결 된 요소를 가져오려면이 메서드를 호출 하 고 위치 값을 업데이트 합니다.

```
const CPair* GetNextWithKey(
    POSITION& pos,
    KINARGTYPE key) const throw();
CPair* GetNextWithKey(
    POSITION& pos,
    KINARGTYPE key) throw();
```

### <a name="parameters"></a>매개 변수

*pos*<br/>
에 대 한 호출을 사용 하 여 얻은 위치 값을 [CRBMultiMap::FindFirstWithKey](#findfirstwithkey) 또는 [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey)에 대 한 이전 호출 또는 `GetNextWithKey`합니다.

*key*<br/>
찾을 요소를 식별 하는 키를 지정 합니다.

### <a name="return-value"></a>반환 값

다음 반환 [CRBTree::CPair 클래스](crbtree-class.md#cpair_class) 지정된 된 키와 연결 된 요소입니다.

### <a name="remarks"></a>설명

위치 값을 키에 연결 된 다음 값을 가리키도록 업데이트 됩니다. 값이 더 이상 없으면 위치 값이 NULL로 설정 됩니다.

기본 클래스에 대 한 설명서를 참조 하세요 [CRBTree](../../atl/reference/crbtree-class.md) 사용할 수 있는 다른 방법에 대 한 정보에 대 한 합니다.

##  <a name="insert"></a>  CRBMultiMap::Insert

Map에 요소 쌍을 삽입 하려면이 메서드를 호출 합니다.

```
POSITION Insert(KINARGTYPE key, VINARGTYPE value) throw(...);
```

### <a name="parameters"></a>매개 변수

*key*<br/>
추가할 키 값을 `CRBMultiMap` 개체입니다.

*값*<br/>
에 추가할 값을 `CRBMultiMap` 와 연결 된 개체 *키*합니다.

### <a name="return-value"></a>반환 값

에 있는 키/값 요소 쌍의 위치를 반환 합니다 `CRBMultiMap` 개체입니다.

### <a name="remarks"></a>설명

기본 클래스에 대 한 설명서를 참조 하세요 [CRBTree](../../atl/reference/crbtree-class.md) 사용할 수 있는 다른 방법에 대 한 정보에 대 한 합니다.

### <a name="example"></a>예제

예를 참조 하세요 [CRBMultiMap::CRBMultiMap](#crbmultimap)합니다.

##  <a name="removekey"></a>  CRBMultiMap::RemoveKey

모든 지정된 된 키에 대 한 키/값 요소를 제거 하려면이 메서드를 호출 합니다.

```
size_t RemoveKey(KINARGTYPE key) throw();
```

### <a name="parameters"></a>매개 변수

*key*<br/>
삭제할 대상 요소를 식별 하는 키를 지정 합니다.

### <a name="return-value"></a>반환 값

지정된 된 키와 연결 된 값의 개수를 반환 합니다.

### <a name="remarks"></a>설명

`RemoveKey` 일치 하는 키가 있는 키/값 요소의 모든 삭제 *키*합니다.

기본 클래스에 대 한 설명서를 참조 하세요 [CRBTree](../../atl/reference/crbtree-class.md) 사용할 수 있는 다른 방법에 대 한 정보에 대 한 합니다.

### <a name="example"></a>예제

예를 참조 하세요 [CRBMultiMap::CRBMultiMap](#crbmultimap)합니다.

## <a name="see-also"></a>참고자료

[CRBTree 클래스](../../atl/reference/crbtree-class.md)<br/>
[CAtlMap 클래스](../../atl/reference/catlmap-class.md)<br/>
[CRBMap 클래스](../../atl/reference/crbmap-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
