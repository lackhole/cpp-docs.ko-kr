---
title: CRBTree 클래스
ms.date: 11/04/2016
f1_keywords:
- CRBTree
- ATLCOLL/ATL::CRBTree
- ATLCOLL/ATL::CRBTree::KINARGTYPE
- ATLCOLL/ATL::CRBTree::KOUTARGTYPE
- ATLCOLL/ATL::CRBTree::VINARGTYPE
- ATLCOLL/ATL::CRBTree::VOUTARGTYPE
- ATLCOLL/ATL::CRBTree::FindFirstKeyAfter
- ATLCOLL/ATL::CRBTree::GetAt
- ATLCOLL/ATL::CRBTree::GetCount
- ATLCOLL/ATL::CRBTree::GetHeadPosition
- ATLCOLL/ATL::CRBTree::GetKeyAt
- ATLCOLL/ATL::CRBTree::GetNext
- ATLCOLL/ATL::CRBTree::GetNextAssoc
- ATLCOLL/ATL::CRBTree::GetNextKey
- ATLCOLL/ATL::CRBTree::GetNextValue
- ATLCOLL/ATL::CRBTree::GetPrev
- ATLCOLL/ATL::CRBTree::GetTailPosition
- ATLCOLL/ATL::CRBTree::GetValueAt
- ATLCOLL/ATL::CRBTree::IsEmpty
- ATLCOLL/ATL::CRBTree::RemoveAll
- ATLCOLL/ATL::CRBTree::RemoveAt
- ATLCOLL/ATL::CRBTree::SetValueAt
helpviewer_keywords:
- CRBTree class
ms.assetid: a1b1cb63-38e4-4fc2-bb28-f774d1721760
ms.openlocfilehash: 59416000eecf4be25746d9dedd86ea2af116087a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62278074"
---
# <a name="crbtree-class"></a>CRBTree 클래스

이 클래스를 만들고 빨강-검정 트리를 활용 하는 메서드를 제공 합니다.

## <a name="syntax"></a>구문

```
template <typename K,
          typename V,
          class KTraits = CElementTraits<K>,
          class VTraits = CElementTraits<V>>
class CRBTree
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
|[CRBTree::KINARGTYPE](#kinargtype)|키를 입력 인수로 전달 될 때 사용 되는 형식입니다.|
|[CRBTree::KOUTARGTYPE](#koutargtype)|키 출력 인수로 반환 될 때 사용 되는 형식입니다.|
|[CRBTree::VINARGTYPE](#vinargtype)|값 입력 인수로 전달 될 때 사용 되는 형식입니다.|
|[CRBTree::VOUTARGTYPE](#voutargtype)|값을 출력 인수로 전달 될 때 사용 되는 형식입니다.|

### <a name="public-classes"></a>public 클래스

|이름|설명|
|----------|-----------------|
|[CRBTree::CPair 클래스](#cpair_class)|키 및 값 요소를 포함 하는 클래스입니다.|

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CRBTree::~CRBTree](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CRBTree::FindFirstKeyAfter](#findfirstkeyafter)|다음 사용 가능한 키를 사용 하는 요소의 위치를 찾으려면이 메서드를 호출 합니다.|
|[CRBTree::GetAt](#getat)|트리에서 지정된 된 위치에 요소를 가져오려면이 메서드를 호출 합니다.|
|[CRBTree::GetCount](#getcount)|트리에서 요소 수를 가져오려면이 메서드를 호출 합니다.|
|[CRBTree::GetHeadPosition](#getheadposition)|트리의 헤드에 있는 요소에 대 한 위치 값을 가져오려면이 메서드를 호출 합니다.|
|[CRBTree::GetKeyAt](#getkeyat)|트리에서 지정된 된 위치에서 키를 가져오려면이 메서드를 호출 합니다.|
|[CRBTree::GetNext](#getnext)|에 저장 된 요소에 대 한 포인터를 가져오려면이 메서드를 호출 합니다 `CRBTree` 개체 및 위치를 다음 요소로 이동 합니다.|
|[CRBTree::GetNextAssoc](#getnextassoc)|키와 맵에 저장 된 요소의 값을 가져오려면이 메서드를 호출 하 고 위치를 다음 요소로 이동 합니다.|
|[CRBTree::GetNextKey](#getnextkey)|트리에서 저장 된 요소의 키를 가져오려면이 메서드를 호출 하 고 위치를 다음 요소로 이동 합니다.|
|[CRBTree::GetNextValue](#getnextvalue)|트리에서 저장 된 요소 값을 가져오려면이 메서드를 호출 하 고 위치를 다음 요소로 이동 합니다.|
|[CRBTree::GetPrev](#getprev)|에 저장 된 요소에 대 한 포인터를 가져오려면이 메서드를 호출 합니다 `CRBTree` 개체를 다음 위치를 이전 요소로 업데이트 합니다.|
|[CRBTree::GetTailPosition](#gettailposition)|트리 끝부분에 있는 요소에 대 한 위치 값을 가져오려면이 메서드를 호출 합니다.|
|[CRBTree::GetValueAt](#getvalueat)|지정 된 위치에 저장 된 값을 검색 하려면이 메서드는 `CRBTree` 개체입니다.|
|[CRBTree::IsEmpty](#isempty)|이 메서드는 빈 트리 개체에 대 한 테스트를 호출 합니다.|
|[CRBTree::RemoveAll](#removeall)|모든 요소를 제거 하려면이 메서드는 `CRBTree` 개체입니다.|
|[CRBTree::RemoveAt](#removeat)|지정된 된 위치에 있는 요소를 제거 하려면이 메서드를 호출 합니다 `CRBTree` 개체입니다.|
|[CRBTree::SetValueAt](#setvalueat)|지정 된 위치에 저장 된 값을 변경 하려면이 메서드를 호출 합니다 `CRBTree` 개체입니다.|

## <a name="remarks"></a>설명

빨강-검정 트리는 추가 사용 하는 이진 검색 트리 하 게 유지 되도록 노드당 정보의 비트 "균형 조정"는, 트리 높이 지나치게 커질 및 성능에 영향을 하지 않습니다.

이 템플릿 클래스는에서 사용할 설계 되었습니다 [CRBMap](../../atl/reference/crbmap-class.md) 하 고 [CRBMultiMap](../../atl/reference/crbmultimap-class.md)합니다. 이러한 파생된 클래스를 구성 하는 메서드는 대량의 제공한 `CRBTree`합니다.

자세한 내용은 다양 한 컬렉션 클래스 및 해당 기능 및 성능 특성에 대 한 참조 [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md)합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlcoll.h

##  <a name="cpair_class"></a>  CRBTree::CPair 클래스

키 및 값 요소를 포함 하는 클래스입니다.

```
class CPair : public __POSITION
```

### <a name="remarks"></a>설명

이 클래스는 메서드에서 사용 됩니다 [CRBTree::GetAt](#getat)를 [CRBTree::GetNext](#getnext), 및 [CRBTree::GetPrev](#getprev) 트리 구조에 저장 된 키 및 값 요소에 액세스 해야 합니다.

멤버는 다음과 같습니다.

|||
|-|-|
|`m_key`|키 요소에 저장 하는 데이터 멤버입니다.|
|`m_value`|Value 요소 저장 데이터 멤버입니다.|

##  <a name="dtor"></a>  CRBTree::~CRBTree

소멸자입니다.

```
~CRBTree() throw();
```

### <a name="remarks"></a>설명

할당 된 리소스를 해제 합니다. 호출 [CRBTree::RemoveAll](#removeall) 모든 요소를 삭제 합니다.

##  <a name="findfirstkeyafter"></a>  CRBTree::FindFirstKeyAfter

다음 사용 가능한 키를 사용 하는 요소의 위치를 찾으려면이 메서드를 호출 합니다.

```
POSITION FindFirstKeyAfter(KINARGTYPE key) const throw();
```

### <a name="parameters"></a>매개 변수

*key*<br/>
키 값입니다.

### <a name="return-value"></a>반환 값

다음 사용 가능한 키를 사용 하는 요소의 위치 값을 반환 합니다. 요소가 더 이상 없으면 NULL이 반환 됩니다.

### <a name="remarks"></a>설명

이 메서드를 사용 하면 트리를 이동할 위치 값을 미리 계산 하지 않고 쉽게 합니다.

##  <a name="getat"></a>  CRBTree::GetAt

트리에서 지정된 된 위치에 요소를 가져오려면이 메서드를 호출 합니다.

```
CPair* GetAt(POSITION pos) throw();
const CPair* GetAt(POSITION pos) const throw();
void GetAt(POSITION pos, KOUTARGTYPE key, VOUTARGTYPE value) const;
```

### <a name="parameters"></a>매개 변수

*pos*<br/>
위치 값입니다.

*key*<br/>
키를 받는 변수입니다.

*값*<br/>
변수 값을 받습니다.입니다.

### <a name="return-value"></a>반환 값

처음 두 형식에 대 한 포인터를 반환 된 [CPair](#cpair_class)합니다. 세 번째 폼에는 키와 지정된 된 위치에 대 한 값을 가져옵니다.

### <a name="remarks"></a>설명

위치 값을 확인할 수 있습니다 이전에 메서드를 호출 하 여 같은 [CRBTree::GetHeadPosition](#getheadposition) 하거나 [CRBTree::GetTailPosition](#gettailposition)합니다.

디버그 빌드에서 어설션 오류가 발생 하는 경우 *pos* NULL과 같습니다.

##  <a name="getcount"></a>  CRBTree::GetCount

트리에서 요소 수를 가져오려면이 메서드를 호출 합니다.

```
size_t GetCount() const throw();
```

### <a name="return-value"></a>반환 값

(각 키/값 쌍 하나 이상의 요소가)에 저장 된 요소의 트리를 반환 합니다.

##  <a name="getheadposition"></a>  CRBTree::GetHeadPosition

트리의 헤드에 있는 요소에 대 한 위치 값을 가져오려면이 메서드를 호출 합니다.

```
POSITION GetHeadPosition() const throw();
```

### <a name="return-value"></a>반환 값

트리의 헤드에 있는 요소에 대 한 위치 값을 반환 합니다.

### <a name="remarks"></a>설명

반환 된 값 `GetHeadPosition` 와 같은 메서드와 함께 사용할 수 있습니다 [CRBTree::GetKeyAt](#getkeyat) 또는 [CRBTree::GetNext](#getnext) 트리를 탐색 하 여 값을 검색 합니다.

##  <a name="getkeyat"></a>  CRBTree::GetKeyAt

트리에서 지정된 된 위치에서 키를 가져오려면이 메서드를 호출 합니다.

```
const K& GetKeyAt(POSITION pos) const throw();
```

### <a name="parameters"></a>매개 변수

*pos*<br/>
위치 값입니다.

### <a name="return-value"></a>반환 값

위치에 저장 된 키를 반환 합니다 *pos* 트리에서 합니다.

### <a name="remarks"></a>설명

하는 경우 *pos* 를 올바른 위치 값이 아닌 결과 예측할 수 없습니다. 디버그 빌드에서 어설션 오류가 발생 하는 경우 *pos* NULL과 같습니다.

##  <a name="getnext"></a>  CRBTree::GetNext

에 저장 된 요소에 대 한 포인터를 가져오려면이 메서드를 호출 합니다 `CRBTree` 개체 및 위치를 다음 요소로 이동 합니다.

```
const CPair* GetNext(POSITION& pos) const throw();
CPair* GetNext(POSITION& pos) throw();
```

### <a name="parameters"></a>매개 변수

*pos*<br/>
위치 카운터를 같은 메서드에 대 한 이전 호출에서 반환한 [CRBTree::GetHeadPosition](#getheadposition) 하거나 [CRBTree::FindFirstKeyAfter](#findfirstkeyafter)합니다.

### <a name="return-value"></a>반환 값

다음에 대 한 포인터를 반환 [CPair](#cpair_class) 트리에서 값입니다.

### <a name="remarks"></a>설명

합니다 *pos* 위치 카운터는 각 호출 후 업데이트 됩니다. 검색된 된 요소 트리에서 마지막 이면 *pos* NULL로 설정 됩니다.

##  <a name="getnextassoc"></a>  CRBTree::GetNextAssoc

키와 맵에 저장 된 요소의 값을 가져오려면이 메서드를 호출 하 고 위치를 다음 요소로 이동 합니다.

```
void GetNextAssoc(
    POSITION& pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;
```

### <a name="parameters"></a>매개 변수

*pos*<br/>
위치 카운터를 같은 메서드에 대 한 이전 호출에서 반환한 [CRBTree::GetHeadPosition](#getheadposition) 하거나 [CRBTree::FindFirstKeyAfter](#findfirstkeyafter)합니다.

*key*<br/>
템플릿 매개 변수를 트리의 키의 형식을 지정 합니다.

*값*<br/>
템플릿 매개 변수를 트리의 값의 형식을 지정 합니다.

### <a name="remarks"></a>설명

합니다 *pos* 위치 카운터는 각 호출 후 업데이트 됩니다. 검색된 된 요소 트리에서 마지막 이면 *pos* NULL로 설정 됩니다.

##  <a name="getnextkey"></a>  CRBTree::GetNextKey

트리에서 저장 된 요소의 키를 가져오려면이 메서드를 호출 하 고 위치를 다음 요소로 이동 합니다.

```
const K& GetNextKey(POSITION& pos) const throw();
```

### <a name="parameters"></a>매개 변수

*pos*<br/>
위치 카운터를 같은 메서드에 대 한 이전 호출에서 반환한 [CRBTree::GetHeadPosition](#getheadposition) 하거나 [CRBTree::FindFirstKeyAfter](#findfirstkeyafter)합니다.

### <a name="return-value"></a>반환 값

트리에서 다음 키에 대 한 참조를 반환합니다.

### <a name="remarks"></a>설명

현재 위치 카운터를 업데이트 *pos*합니다. 트리에서 엔트리를 더 이상 없으면 위치 카운터가 NULL로 설정 됩니다.

##  <a name="getnextvalue"></a>  CRBTree::GetNextValue

트리에서 저장 된 요소 값을 가져오려면이 메서드를 호출 하 고 위치를 다음 요소로 이동 합니다.

```
const V& GetNextValue(POSITION& pos) const throw();
V& GetNextValue(POSITION& pos) throw();
```

### <a name="parameters"></a>매개 변수

*pos*<br/>
위치 카운터를 같은 메서드에 대 한 이전 호출에서 반환한 [CRBTree::GetHeadPosition](#getheadposition) 하거나 [CRBTree::FindFirstKeyAfter](#findfirstkeyafter)합니다.

### <a name="return-value"></a>반환 값

트리에서 다음 값에 대 한 참조를 반환합니다.

### <a name="remarks"></a>설명

현재 위치 카운터를 업데이트 *pos*합니다. 트리에서 엔트리를 더 이상 없으면 위치 카운터가 NULL로 설정 됩니다.

##  <a name="getprev"></a>  CRBTree::GetPrev

에 저장 된 요소에 대 한 포인터를 가져오려면이 메서드를 호출 합니다 `CRBTree` 개체를 다음 위치를 이전 요소로 업데이트 합니다.

```
const CPair* GetPrev(POSITION& pos) const throw();
CPair* GetPrev(POSITION& pos) throw();
```

### <a name="parameters"></a>매개 변수

*pos*<br/>
위치 카운터를 같은 메서드에 대 한 이전 호출에서 반환한 [CRBTree::GetHeadPosition](#getheadposition) 하거나 [CRBTree::FindFirstKeyAfter](#findfirstkeyafter)합니다.

### <a name="return-value"></a>반환 값

이전에 대 한 포인터를 반환 [CPair](#cpair_class) 트리에서 저장 된 값입니다.

### <a name="remarks"></a>설명

현재 위치 카운터를 업데이트 *pos*합니다. 트리에서 엔트리를 더 이상 없으면 위치 카운터가 NULL로 설정 됩니다.

##  <a name="gettailposition"></a>  CRBTree::GetTailPosition

트리 끝부분에 있는 요소에 대 한 위치 값을 가져오려면이 메서드를 호출 합니다.

```
POSITION GetTailPosition() const throw();
```

### <a name="return-value"></a>반환 값

트리 끝부분에 있는 요소에 대 한 위치 값을 반환 합니다.

### <a name="remarks"></a>설명

반환 된 값 `GetTailPosition` 와 같은 메서드와 함께 사용할 수 있습니다 [CRBTree::GetKeyAt](#getkeyat) 또는 [CRBTree::GetPrev](#getprev) 트리를 탐색 하 여 값을 검색 합니다.

##  <a name="getvalueat"></a>  CRBTree::GetValueAt

지정 된 위치에 저장 된 값을 검색 하려면이 메서드는 `CRBTree` 개체입니다.

```
const V& GetValueAt(POSITION pos) const throw();
V& GetValueAt(POSITION pos) throw();
```

### <a name="parameters"></a>매개 변수

*pos*<br/>
위치 카운터를 같은 메서드에 대 한 이전 호출에서 반환한 [CRBTree::GetHeadPosition](#getheadposition) 하거나 [CRBTree::FindFirstKeyAfter](#findfirstkeyafter)합니다.

### <a name="return-value"></a>반환 값

지정된 된 위치에 저장 된 값에 대 한 참조를 반환 합니다 `CRBTree` 개체입니다.

##  <a name="isempty"></a>  CRBTree::IsEmpty

이 메서드는 빈 트리 개체에 대 한 테스트를 호출 합니다.

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>반환 값

트리의 경우 비어 있는 경우 FALSE이 고, 그렇지 TRUE를 반환 합니다.

##  <a name="kinargtype"></a>  CRBTree::KINARGTYPE

키를 입력 인수로 전달 될 때 사용 되는 형식입니다.

```
typedef KTraits::INARGTYPE KINARGTYPE;
```

##  <a name="koutargtype"></a>  CRBTree::KOUTARGTYPE

키 출력 인수로 반환 될 때 사용 되는 형식입니다.

```
typedef KTraits::OUTARGTYPE KOUTARGTYPE;
```

##  <a name="removeall"></a>  CRBTree::RemoveAll

모든 요소를 제거 하려면이 메서드는 `CRBTree` 개체입니다.

```
void RemoveAll() throw();
```

### <a name="remarks"></a>설명

지웁니다는 `CRBTree` 개체에 요소를 저장 하는 데 사용 된 메모리를 해제 합니다.

##  <a name="removeat"></a>  CRBTree::RemoveAt

지정된 된 위치에 있는 요소를 제거 하려면이 메서드를 호출 합니다 `CRBTree` 개체입니다.

```
void RemoveAt(POSITION pos) throw();
```

### <a name="parameters"></a>매개 변수

*pos*<br/>
위치 카운터를 같은 메서드에 대 한 이전 호출에서 반환한 [CRBTree::GetHeadPosition](#getheadposition) 하거나 [CRBTree::FindFirstKeyAfter](#findfirstkeyafter)합니다.

### <a name="remarks"></a>설명

지정된 된 위치에 저장 된 키/값 쌍을 제거 합니다. 요소를 저장 하는 데 메모리 해제 됩니다. 참조 하는 위치 *pos* 무효화 되 고 트리의 다른 요소의 위치 반드시 수행 하는 유효한 상태로 유지 하면서 동일한 순서를 유지 합니다.

##  <a name="setvalueat"></a>  CRBTree::SetValueAt

지정 된 위치에 저장 된 값을 변경 하려면이 메서드를 호출 합니다 `CRBTree` 개체입니다.

```
void SetValueAt(POSITION pos, VINARGTYPE value);
```

### <a name="parameters"></a>매개 변수

*pos*<br/>
위치 카운터를 같은 메서드에 대 한 이전 호출에서 반환한 [CRBTree::GetHeadPosition](#getheadposition) 하거나 [CRBTree::FindFirstKeyAfter](#findfirstkeyafter)합니다.

*값*<br/>
에 추가할 값을 `CRBTree` 개체입니다.

### <a name="remarks"></a>설명

지정된 된 위치에 저장 된 값 요소를 변경 합니다 `CRBTree` 개체입니다.

##  <a name="vinargtype"></a>  CRBTree::VINARGTYPE

값 입력 인수로 전달 될 때 사용 되는 형식입니다.

```
typedef VTraits::INARGTYPE VINARGTYPE;
```

##  <a name="voutargtype"></a>  CRBTree::VOUTARGTYPE

값을 출력 인수로 전달 될 때 사용 되는 형식입니다.

```
typedef VTraits::OUTARGTYPE VOUTARGTYPE;
```

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)
