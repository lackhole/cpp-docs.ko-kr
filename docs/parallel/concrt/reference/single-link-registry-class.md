---
title: single_link_registry 클래스
ms.date: 11/04/2016
f1_keywords:
- single_link_registry
- AGENTS/concurrency::single_link_registry
- AGENTS/concurrency::single_link_registry::single_link_registry
- AGENTS/concurrency::single_link_registry::add
- AGENTS/concurrency::single_link_registry::begin
- AGENTS/concurrency::single_link_registry::contains
- AGENTS/concurrency::single_link_registry::count
- AGENTS/concurrency::single_link_registry::remove
helpviewer_keywords:
- single_link_registry class
ms.assetid: 09540a4e-c34e-4ff9-af49-21b8612b6ab3
ms.openlocfilehash: 20032f393964c8919d2c1a49ec8545400cd9e392
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160074"
---
# <a name="singlelinkregistry-class"></a>single_link_registry 클래스

`single_link_registry` 개체는 단일 소스 또는 대상 블록만 관리하는 `network_link_registry`입니다.

## <a name="syntax"></a>구문

```
template<class _Block>
class single_link_registry : public network_link_registry<_Block>;
```

#### <a name="parameters"></a>매개 변수

*_Block*<br/>
블록 데이터 형식에 저장 되는 `single_link_registry` 개체입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[single_link_registry](#ctor)|`single_link_registry` 개체를 생성합니다.|
|[~ single_link_registry 소멸자](#dtor)|제거 된 `single_link_registry` 개체입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[add](#add)|에 대 한 링크를 추가 합니다 `single_link_registry` 개체입니다. (재정의 [network_link_registry:: add](network-link-registry-class.md#add).)|
|[begin](#begin)|첫 번째 요소에 반복기를 반환 합니다 `single_link_registry` 개체입니다. (재정의 [network_link_registry:: begin](network-link-registry-class.md#begin).)|
|[contains](#contains)|검색 된 `single_link_registry` 지정된 된 블록에 대 한 개체입니다. (재정의 [network_link_registry:: contains](network-link-registry-class.md#contains).)|
|[count](#count)|에 있는 항목의 개수는 `single_link_registry` 개체입니다. (재정의 [network_link_registry:: count](network-link-registry-class.md#count).)|
|[remove](#remove)|링크를 제거 합니다 `single_link_registry` 개체입니다. (재정의 [network_link_registry:: remove](network-link-registry-class.md#remove).)|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[network_link_registry](network-link-registry-class.md)

`single_link_registry`

## <a name="requirements"></a>요구 사항

**헤더:** agents.h

**네임스페이스:** 동시성

##  <a name="add"></a> 추가

에 대 한 링크를 추가 합니다 `single_link_registry` 개체입니다.

```
virtual void add(_EType _Link);
```

### <a name="parameters"></a>매개 변수

*_Link*<br/>
추가할 블록에 대 한 포인터입니다.

### <a name="remarks"></a>설명

메서드에서 throw를 [invalid_link_target](invalid-link-target-class.md) 이미 있으면 링크가이 레지스트리의 예외입니다.

##  <a name="begin"></a> 시작

첫 번째 요소에 반복기를 반환 합니다 `single_link_registry` 개체입니다.

```
virtual iterator begin();
```

### <a name="return-value"></a>반환 값

첫 번째 요소를 지정 하는 반복기는 `single_link_registry` 개체입니다.

### <a name="remarks"></a>설명

최종 상태에서 표시 되는 `NULL` 링크 합니다.

##  <a name="contains"></a> 포함

검색 된 `single_link_registry` 지정된 된 블록에 대 한 개체입니다.

```
virtual bool contains(_EType _Link);
```

### <a name="parameters"></a>매개 변수

*_Link*<br/>
검색 하는 블록에 대 한 포인터를 `single_link_registry` 개체입니다.

### <a name="return-value"></a>반환 값

**true** 링크를 찾을 수 있으면 **false** 그렇지 않은 경우.

##  <a name="count"></a> 개수

에 있는 항목의 개수는 `single_link_registry` 개체입니다.

```
virtual size_t count();
```

### <a name="return-value"></a>반환 값

항목 수를 `single_link_registry` 개체입니다.

##  <a name="remove"></a> 제거

링크를 제거 합니다 `single_link_registry` 개체입니다.

```
virtual bool remove(_EType _Link);
```

### <a name="parameters"></a>매개 변수

*_Link*<br/>
제거 될 경우 블록에 대 한 포인터를 찾을 수 있습니다.

### <a name="return-value"></a>반환 값

**true** 링크를을 찾아 제거 했으면 **false** 그렇지 않은 경우.

##  <a name="ctor"></a> single_link_registry

`single_link_registry` 개체를 생성합니다.

```
single_link_registry();
```

##  <a name="dtor"></a> ~single_link_registry

제거 된 `single_link_registry` 개체입니다.

```
virtual ~single_link_registry();
```

### <a name="remarks"></a>설명

메서드에서 throw를 [invalid_operation](invalid-operation-class.md) 링크를 제거 하기 전에 메서드를 호출 하는 예외입니다.

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[multi_link_registry 클래스](multi-link-registry-class.md)
