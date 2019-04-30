---
title: network_link_registry 클래스
ms.date: 11/04/2016
f1_keywords:
- network_link_registry
- AGENTS/concurrency::network_link_registry
- AGENTS/concurrency::network_link_registry::add
- AGENTS/concurrency::network_link_registry::begin
- AGENTS/concurrency::network_link_registry::contains
- AGENTS/concurrency::network_link_registry::count
- AGENTS/concurrency::network_link_registry::remove
helpviewer_keywords:
- network_link_registry class
ms.assetid: 3e7b4097-09f1-4252-964e-b15b8f7f7fc6
ms.openlocfilehash: 2537ed857651b5210b104a270b3d827246b8339a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385234"
---
# <a name="networklinkregistry-class"></a>network_link_registry 클래스

`network_link_registry` 추상 기본 클래스는 소스 및 대상 블록 간의 연결을 관리합니다.

## <a name="syntax"></a>구문

```
template<class _Block>
class network_link_registry;
```

#### <a name="parameters"></a>매개 변수

*_Block*<br/>
블록 데이터 형식에 저장 되는 `network_link_registry`합니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|이름|설명|
|----------|-----------------|
|`const_pointer`|에 대 한 포인터를 제공 하는 형식에 `const` 요소에는 `network_link_registry` 개체.|
|`const_reference`|에 대 한 참조를 제공 하는 형식을 `const` 에 저장 된 요소는 `network_link_registry` 읽고 const 작업 수행에 대 한 개체입니다.|
|`iterator`|반복기를 제공 하는 형식 읽거나에 있는 모든 요소를 수정할 수는 `network_link_registry` 개체입니다.|
|`type`|에 저장 된 블록 형식을 나타내는 형식입니다는 `network_link_registry` 개체입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[add](#add)|파생된 클래스에서 재정의 되 면 추가에 대 한 링크는 `network_link_registry` 개체입니다.|
|[begin](#begin)|파생된 클래스에서 재정의 되 면 첫 번째 요소에 반복기를 반환 합니다 `network_link_registry` 개체입니다.|
|[contains](#contains)|파생된 클래스에서 재정의 되 면 검색 된 `network_link_registry` 지정된 된 블록에 대 한 개체입니다.|
|[count](#count)|파생된 클래스에서 재정의 되 면에 있는 항목의 수를 반환 합니다 `network_link_registry` 개체입니다.|
|[remove](#remove)|파생된 클래스에서 재정의 되 면에서 지정된 된 블록을 제거 합니다 `network_link_registry` 개체입니다.|

## <a name="remarks"></a>설명

`network link registry` 동시 액세스에 대 한 안전 하지 않습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`network_link_registry`

## <a name="requirements"></a>요구 사항

**헤더:** agents.h

**네임스페이스:** 동시성

##  <a name="add"></a> 추가

파생된 클래스에서 재정의 되 면 추가에 대 한 링크는 `network_link_registry` 개체입니다.

```
virtual void add(_EType _Link) = 0;
```

### <a name="parameters"></a>매개 변수

*_Link*<br/>
추가할 블록에 대 한 포인터입니다.

##  <a name="begin"></a> 시작

파생된 클래스에서 재정의 되 면 첫 번째 요소에 반복기를 반환 합니다 `network_link_registry` 개체입니다.

```
virtual iterator begin() = 0;
```

### <a name="return-value"></a>반환 값

첫 번째 요소를 지정 하는 반복기는 `network_link_registry` 개체입니다.

### <a name="remarks"></a>설명

반복기의 최종 상태도 표시 됩니다는 `NULL` 링크 합니다.

##  <a name="contains"></a> 포함

파생된 클래스에서 재정의 되 면 검색 된 `network_link_registry` 지정된 된 블록에 대 한 개체입니다.

```
virtual bool contains(_EType _Link) = 0;
```

### <a name="parameters"></a>매개 변수

*_Link*<br/>
검색 되는 블록에 대 한 포인터를 `network_link_registry` 개체입니다.

### <a name="return-value"></a>반환 값

**true** 블록이 없으면 **false** 그렇지 않은 경우.

##  <a name="count"></a> 개수

파생된 클래스에서 재정의 되 면에 있는 항목의 수를 반환 합니다 `network_link_registry` 개체입니다.

```
virtual size_t count() = 0;
```

### <a name="return-value"></a>반환 값

항목 수를 `network_link_registry` 개체입니다.

##  <a name="remove"></a> 제거

파생된 클래스에서 재정의 되 면에서 지정된 된 블록을 제거 합니다 `network_link_registry` 개체입니다.

```
virtual bool remove(_EType _Link) = 0;
```

### <a name="parameters"></a>매개 변수

*_Link*<br/>
제거 될 경우 블록에 대 한 포인터를 찾을 수 있습니다.

### <a name="return-value"></a>반환 값

**true** 링크를을 찾아 제거 했으면 **false** 그렇지 않은 경우.

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[single_link_registry 클래스](single-link-registry-class.md)<br/>
[multi_link_registry 클래스](multi-link-registry-class.md)
