---
title: 위치 클래스
ms.date: 11/04/2016
f1_keywords:
- location
- CONCRT/concurrency::location
- CONCRT/concurrency::location::location
- CONCRT/concurrency::location::current
- CONCRT/concurrency::location::from_numa_node
helpviewer_keywords:
- location class
ms.assetid: c3289f51-5bf1-4dff-a18d-d0dab8e5d9c7
ms.openlocfilehash: 5e90dd3b23b33f6699f2df4ce0df9178f95816b8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62375459"
---
# <a name="location-class"></a>위치 클래스

하드웨어의 실제 위치에 대한 추상화입니다.

## <a name="syntax"></a>구문

```
class location;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[location](#ctor)|오버로드됨. `location` 개체를 생성합니다.|
|[~ location 소멸자](#dtor)|`location` 개체를 제거합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[current](#current)|호출 스레드가 실행 중인 가장 구체적인 장소를 나타내는 `location` 개체를 반환합니다.|
|[from_numa_node](#from_numa_node)|지정된 NUMA 노드를 나타내는 `location` 개체를 반환합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[operator!=](#operator_neq)|두 `location` 개체가 서로 다른 위치를 나타내는지 여부를 확인합니다.|
|[operator=](#operator_eq)|다른 `location` 개체의 내용을 여기에 할당합니다.|
|[연산자==](#operator_eq_eq)|두 결정 `location` 개체는 동일한 위치를 나타냅니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`location`

## <a name="requirements"></a>요구 사항

**헤더:** concrt.h

**네임스페이스:** 동시성

##  <a name="dtor"></a> ~location

`location` 개체를 제거합니다.

```
~location();
```

##  <a name="current"></a> current

호출 스레드가 실행 중인 가장 구체적인 장소를 나타내는 `location` 개체를 반환합니다.

```
static location __cdecl current();
```

### <a name="return-value"></a>반환 값

호출 스레드가 실행 중인 가장 구체적인 장소를 나타내는 위치입니다.

##  <a name="from_numa_node"></a> from_numa_node

지정된 NUMA 노드를 나타내는 `location` 개체를 반환합니다.

```
static location __cdecl from_numa_node(unsigned short _NumaNodeNumber);
```

### <a name="parameters"></a>매개 변수

*_NumaNodeNumber*<br/>
위치를 생성하기 위한 NUMA 노드 번호입니다.

### <a name="return-value"></a>반환 값

`_NumaNodeNumber` 매개 변수로 지정된 NUMA 노드를 나타내는 위치입니다.

##  <a name="ctor"></a> 위치

`location` 개체를 생성합니다.

```
location();

location(
    const location& _Src);

location(
    T _LocationType,
    unsigned int _Id,
    unsigned int _BindingId = 0,
    _Inout_opt_ void* _PBinding = NULL);
```

### <a name="parameters"></a>매개 변수

*_Src*<br/>

*_LocationType*<br/>

*_Id*<br/>

*_BindingId*<br/>

*_PBinding*<br/>
(선택 사항) 바인딩에 대 한 포인터입니다.

### <a name="remarks"></a>설명

기본적으로 생성되는 위치는 시스템 전체를 나타냅니다.

##  <a name="operator_neq"></a> operator!=

두 `location` 개체가 서로 다른 위치를 나타내는지 여부를 확인합니다.

```
bool operator!= (const location& _Rhs) const;
```

### <a name="parameters"></a>매개 변수

*_Rhs*<br/>
피연산자 `location`합니다.

### <a name="return-value"></a>반환 값

**true** 두 위치 다르면 **false** 그렇지 않은 경우.

##  <a name="operator_eq"></a> operator=

다른 `location` 개체의 내용을 여기에 할당합니다.

```
location& operator= (const location& _Rhs);
```

### <a name="parameters"></a>매개 변수

*_Rhs*<br/>
소스 `location` 개체입니다.

### <a name="return-value"></a>반환 값

##  <a name="operator_eq_eq"></a> operator==

두 결정 `location` 개체는 동일한 위치를 나타냅니다.

```
bool operator== (const location& _Rhs) const;
```

### <a name="parameters"></a>매개 변수

*_Rhs*<br/>
피연산자 `location`합니다.

### <a name="return-value"></a>반환 값

**true** 두 위치 동일 하 고 **false** 그렇지 않은 경우.

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)
