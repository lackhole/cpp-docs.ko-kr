---
title: source_link_manager 클래스
ms.date: 11/04/2016
f1_keywords:
- source_link_manager
- AGENTS/concurrency::source_link_manager
- AGENTS/concurrency::source_link_manager::source_link_manager
- AGENTS/concurrency::source_link_manager::add
- AGENTS/concurrency::source_link_manager::begin
- AGENTS/concurrency::source_link_manager::contains
- AGENTS/concurrency::source_link_manager::count
- AGENTS/concurrency::source_link_manager::reference
- AGENTS/concurrency::source_link_manager::register_target_block
- AGENTS/concurrency::source_link_manager::release
- AGENTS/concurrency::source_link_manager::remove
- AGENTS/concurrency::source_link_manager::set_bound
helpviewer_keywords:
- source_link_manager class
ms.assetid: 287487cf-e0fe-4c35-aa3c-24f081d1ddae
ms.openlocfilehash: d4979eaf9065183be646be72cfdd5a94500edf55
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62337585"
---
# <a name="sourcelinkmanager-class"></a>source_link_manager 클래스

`source_link_manager` 개체는 `ISource` 블록에 대한 메시징 블록 네트워크 연결을 관리합니다.

## <a name="syntax"></a>구문

```
template<class _LinkRegistry>
class source_link_manager;
```

#### <a name="parameters"></a>매개 변수

*_LinkRegistry*<br/>
네트워크 링크 레지스트리입니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|이름|설명|
|----------|-----------------|
|`const_pointer`|에 대 한 포인터를 제공 하는 형식에 `const` 요소에는 `source_link_manager` 개체.|
|`const_reference`|에 대 한 참조를 제공 하는 형식을 `const` 에 저장 된 요소는 `source_link_manager` 읽고 const 작업 수행에 대 한 개체입니다.|
|`iterator`|반복기를 제공 하는 형식 읽거나에 있는 모든 요소를 수정할 수는 `source_link_manager` 개체입니다.|
|`type`|으로 관리 되는 링크 레지스트리에서 유형의 `source_link_manager` 개체입니다.|

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[source_link_manager](#ctor)|`source_link_manager` 개체를 생성합니다.|
|[~ source_link_manager 소멸자](#dtor)|제거 된 `source_link_manager` 개체입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[add](#add)|소스 링크를 추가 합니다 `source_link_manager` 개체입니다.|
|[begin](#begin)|첫 번째 요소에 반복기를 반환 합니다 `source_link_manager` 개체입니다.|
|[contains](#contains)|검색 된 `network_link_registry` 이 `source_link_manager` 지정된 된 블록에 대 한 개체입니다.|
|[count](#count)|연결 된 블록의 개수는 `source_link_manager` 개체입니다.|
|[reference](#reference)|에 대 한 참조를 가져옵니다는 `source_link_manager` 개체입니다.|
|[register_target_block](#register_target_block)|이 보유 하는 대상 블록을 등록 `source_link_manager` 개체입니다.|
|[release](#release)|참조를 해제 합니다 `source_link_manager` 개체입니다.|
|[remove](#remove)|링크를 제거 합니다 `source_link_manager` 개체입니다.|
|[set_bound](#set_bound)|이를 추가할 수 있는 소스 링크의 최대 수를 설정 `source_link_manager` 개체입니다.|

## <a name="remarks"></a>설명

현재 소스 블록은 참조를 계산 합니다. 이 래퍼를 `network_link_registry` 링크에 대 한 동시 액세스를 허용 하 고 콜백을 통해 링크를 참조 하는 기능을 제공 하는 개체입니다. 메시지 블록 ( `target_block`s 또는 `propagator_block`s)가 소스 링크에 대 한이 클래스를 사용 해야 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`source_link_manager`

## <a name="requirements"></a>요구 사항

**헤더:** agents.h

**네임스페이스:** 동시성

##  <a name="add"></a> 추가

소스 링크를 추가 합니다 `source_link_manager` 개체입니다.

```
void add(_EType _Link);
```

### <a name="parameters"></a>매개 변수

*_Link*<br/>
추가할 블록에 대 한 포인터입니다.

##  <a name="begin"></a> 시작

첫 번째 요소에 반복기를 반환 합니다 `source_link_manager` 개체입니다.

```
iterator begin();
```

### <a name="return-value"></a>반환 값

첫 번째 요소를 지정 하는 반복기는 `source_link_manager` 개체입니다.

### <a name="remarks"></a>설명

반복기의 최종 상태도 표시 됩니다는 `NULL` 링크 합니다.

##  <a name="contains"></a> 포함

검색 된 `network_link_registry` 이 `source_link_manager` 지정된 된 블록에 대 한 개체입니다.

```
bool contains(_EType _Link);
```

### <a name="parameters"></a>매개 변수

*_Link*<br/>
검색 하는 블록에 대 한 포인터를 `source_link_manager` 개체입니다.

### <a name="return-value"></a>반환 값

**true** 지정된 된 블록 있으면 **false** 그렇지 않은 경우.

##  <a name="count"></a> 개수

연결 된 블록의 개수는 `source_link_manager` 개체입니다.

```
size_t count();
```

### <a name="return-value"></a>반환 값

에 연결 된 블록 수는 `source_link_manager` 개체입니다.

##  <a name="reference"></a> 참조

에 대 한 참조를 가져옵니다는 `source_link_manager` 개체입니다.

```
void reference();
```

##  <a name="register_target_block"></a> register_target_block

이 보유 하는 대상 블록을 등록 `source_link_manager` 개체입니다.

```
void register_target_block(_Inout_ ITarget<typename _Block::source_type>* _PTarget);
```

### <a name="parameters"></a>매개 변수

*_PTarget*<br/>
이 보유 하는 대상 블록 `source_link_manager` 개체입니다.

##  <a name="release"></a> 릴리스

참조를 해제 합니다 `source_link_manager` 개체입니다.

```
void release();
```

##  <a name="remove"></a> 제거

링크를 제거 합니다 `source_link_manager` 개체입니다.

```
bool remove(_EType _Link);
```

### <a name="parameters"></a>매개 변수

*_Link*<br/>
제거 될 경우 블록에 대 한 포인터를 찾을 수 있습니다.

### <a name="return-value"></a>반환 값

**true** 링크를을 찾아 제거 했으면 **false** 그렇지 않은 경우.

##  <a name="set_bound"></a> set_bound

이를 추가할 수 있는 소스 링크의 최대 수를 설정 `source_link_manager` 개체입니다.

```
void set_bound(size_t _MaxLinks);
```

### <a name="parameters"></a>매개 변수

*_MaxLinks*<br/>
링크의 최대 수입니다.

##  <a name="ctor"></a> source_link_manager

`source_link_manager` 개체를 생성합니다.

```
source_link_manager();
```

##  <a name="dtor"></a> ~source_link_manager

제거 된 `source_link_manager` 개체입니다.

```
~source_link_manager();
```

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[single_link_registry 클래스](single-link-registry-class.md)<br/>
[multi_link_registry 클래스](multi-link-registry-class.md)
