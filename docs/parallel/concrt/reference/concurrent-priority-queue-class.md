---
title: concurrent_priority_queue 클래스
ms.date: 11/04/2016
f1_keywords:
- concurrent_priority_queue
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::concurrent_priority_queue
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::clear
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::empty
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::get_allocator
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::push
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::size
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::swap
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::try_pop
helpviewer_keywords:
- concurrent_priority_queue class
ms.assetid: 3e740381-0f4e-41fc-8b66-ad0bb55f17a3
ms.openlocfilehash: 5804675ffdaf6de2e73327103398316566b41627
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160041"
---
# <a name="concurrentpriorityqueue-class"></a>concurrent_priority_queue 클래스

`concurrent_priority_queue` 클래스는 여러 스레드에서 동시에 항목을 푸시 및 팝할 수 있도록 허용하는 컨테이너입니다. 항목은 우선순위에 따라 팝되고, 우선순위는 템플릿 인수로 제공된 함수에 의해 결정됩니다.

## <a name="syntax"></a>구문

```
template <typename T,
    typename _Compare= std::less<T>,
    typename _Ax = std::allocator<T>
>,
    typename _Ax = std::allocator<T>> class concurrent_priority_queue;
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
우선 순위 큐에 저장될 요소의 데이터 형식입니다.

*_Compare*<br/>
우선 순위 큐에서 두 요소 값의 상대적 순서를 결정하기 위해 정렬 키로 두 요소 값을 비교할 수 있는 함수 개체의 형식입니다. 이 인수는 선택 사항이며 기본값은 이진 조건자 `less<T>`입니다.

*_Ax*<br/>
동시 우선 순위 큐의 메모리 할당 및 할당 취소에 대한 세부 정보를 캡슐화하는, 저장된 할당자 개체를 나타내는 형식입니다. 이 인수는 선택 사항이며 기본값은 `allocator<T>`입니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|이름|설명|
|----------|-----------------|
|`allocator_type`|동시 우선 순위 큐의 할당자 클래스를 나타내는 형식입니다.|
|`const_reference`|동시 우선 순위 큐에 저장된 형식의 요소에 대한 const 참조를 나타내는 형식입니다.|
|`reference`|동시 우선 순위 큐에 저장된 형식의 요소에 대한 참조를 나타내는 형식입니다.|
|`size_type`|동시 우선 순위 큐에 있는 요소의 수를 세는 형식입니다.|
|`value_type`|동시 우선 순위 큐에 저장된 데이터 형식을 나타내는 형식입니다.|

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[concurrent_priority_queue](#ctor)|오버로드됨. 동시 우선 순위 큐를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[clear](#clear)|동시 우선 순위의 모든 요소를 지웁니다. 이 메서드는 동시성이 보장 되지 않습니다.|
|[empty](#empty)|이 메서드가 호출될 때 동시 우선 순위 큐가 비어 있는지를 테스트합니다. 이 메서드는 동시성이 보장 합니다.|
|[get_allocator](#get_allocator)|동시 우선 순위 큐를 생성하는 데 사용되는 할당자 복사본을 반환합니다. 이 메서드는 동시성이 보장 합니다.|
|[push](#push)|오버로드됨. 동시 우선 순위 큐에 요소를 추가 합니다. 이 메서드는 동시성이 보장 합니다.|
|[size](#size)|동시 우선 순위 큐에 있는 요소의 수를 반환합니다. 이 메서드는 동시성이 보장 합니다.|
|[swap](#swap)|두 개의 동시 우선 순위 큐의 내용을 바꿉니다. 이 메서드는 동시성이 보장 되지 않습니다.|
|[try_pop](#try_pop)|큐가 비어 있지 않은 경우 큐에서 우선 순위가 가장 높은 요소를 제거하고 반환합니다. 이 메서드는 동시성이 보장 합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[operator=](#operator_eq)|오버로드됨. 다른 내용을 할당 `concurrent_priority_queue` 여기에 개체입니다. 이 메서드는 동시성이 보장 되지 않습니다.|

## <a name="remarks"></a>설명

대 한 자세한 내용은 합니다 `concurrent_priority_queue` 클래스를 참조 하십시오 [병렬 컨테이너 및 개체](../../../parallel/concrt/parallel-containers-and-objects.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층

`concurrent_priority_queue`

## <a name="requirements"></a>요구 사항

**헤더:** concurrent_priority_queue.h

**네임스페이스:** 동시성

##  <a name="clear"></a> 지우기

동시 우선 순위의 모든 요소를 지웁니다. 이 메서드는 동시성이 보장 되지 않습니다.

```
void clear();
```

### <a name="remarks"></a>설명

`clear` 동시성 안전 하지 않습니다. 이 메서드를 호출할 때 다른 스레드가 없는 동시 우선 순위 큐에 메서드를 호출 하는 확인 해야 합니다. `clear` 메모리를 해제 하지 않습니다.

##  <a name="ctor"></a> concurrent_priority_queue

동시 우선 순위 큐를 생성합니다.

```
explicit concurrent_priority_queue(
    const allocator_type& _Al = allocator_type());

explicit concurrent_priority_queue(
    size_type _Init_capacity,
    const allocator_type& _Al = allocator_type());

template<typename _InputIterator>
concurrent_priority_queue(_InputIterator _Begin,
    _InputIterator _End,
    const allocator_type& _Al = allocator_type());

concurrent_priority_queue(
    const concurrent_priority_queue& _Src);

concurrent_priority_queue(
    const concurrent_priority_queue& _Src,
    const allocator_type& _Al);

concurrent_priority_queue(
    concurrent_priority_queue&& _Src);

concurrent_priority_queue(
    concurrent_priority_queue&& _Src,
    const allocator_type& _Al);
```

### <a name="parameters"></a>매개 변수

*_InputIterator*<br/>
입력 반복기의 형식입니다.

*_Al*<br/>
이 개체에 사용할 할당자 클래스입니다.

*_Init_capacity*<br/>
`concurrent_priority_queue` 개체의 초기 용량입니다.

*_Begin*<br/>
복사할 요소의 범위에서 첫 번째 요소의 위치입니다.

*_End*<br/>
복사할 요소의 범위를 벗어나는 첫 번째 요소의 위치입니다.

*_Src*<br/>
요소를 복사해 오거나 이동해 올 소스 `concurrent_priority_queue` 개체입니다.

### <a name="remarks"></a>설명

모든 생성자는 할당자 개체를 저장 `_Al` 우선 순위 큐를 초기화 합니다.

첫 번째 생성자는 빈 초기 우선 순위 큐를 지정 하 고 필요에 따라 할당자를 지정 합니다.

초기 용량을 사용 하 여 우선 순위 큐를 지정 하는 두 번째 생성자는 `_Init_capacity` 할당자를 선택적으로 지정 합니다.

반복기 범위에서 제공 하는 값을 지정 하는 세 번째 생성자는 [ `_Begin`, `_End`) 하 고 필요에 따라 할당자를 지정 합니다.

네 번째와 다섯 번째 생성자는 우선 순위 큐의 복사본을 지정 `_Src`합니다.

여섯 번째와 일곱 번째 생성자는 우선 순위 큐의 이동을 지정 `_Src`합니다.

##  <a name="empty"></a> empty

이 메서드가 호출될 때 동시 우선 순위 큐가 비어 있는지를 테스트합니다. 이 메서드는 동시성이 보장 합니다.

```
bool empty() const;
```

### <a name="return-value"></a>반환 값

**true 이면** 함수를 호출 하는 순간에 우선 순위 큐가 비어 있으면 **false** 그렇지 않은 경우.

##  <a name="get_allocator"></a> get_allocator

동시 우선 순위 큐를 생성하는 데 사용되는 할당자 복사본을 반환합니다. 이 메서드는 동시성이 보장 합니다.

```
allocator_type get_allocator() const;
```

### <a name="return-value"></a>반환 값

생성 하는 데 사용 되는 할당자 복사본을 `concurrent_priority_queue` 개체입니다.

##  <a name="operator_eq"></a> operator=

다른 내용을 할당 `concurrent_priority_queue` 여기에 개체입니다. 이 메서드는 동시성이 보장 되지 않습니다.

```
concurrent_priority_queue& operator= (const concurrent_priority_queue& _Src);

concurrent_priority_queue& operator= (concurrent_priority_queue&& _Src);
```

### <a name="parameters"></a>매개 변수

*_Src*<br/>
소스 `concurrent_priority_queue` 개체입니다.

### <a name="return-value"></a>반환 값

이에 대 한 참조 `concurrent_priority_queue` 개체입니다.

##  <a name="push"></a> push

동시 우선 순위 큐에 요소를 추가 합니다. 이 메서드는 동시성이 보장 합니다.

```
void push(const value_type& _Elem);

void push(value_type&& _Elem);
```

### <a name="parameters"></a>매개 변수

*_Elem*<br/>
동시 우선 순위 큐에 추가할 요소입니다.

##  <a name="size"></a> 크기

동시 우선 순위 큐에 있는 요소의 수를 반환합니다. 이 메서드는 동시성이 보장 합니다.

```
size_type size() const;
```

### <a name="return-value"></a>반환 값

이 요소 수가 `concurrent_priority_queue` 개체입니다.

### <a name="remarks"></a>설명

반환 되는 크기는 함수를 호출 하 여 추가 된 모든 요소를 포함 하도록 보장 됩니다 `push`합니다. 그러나 보류 중인 동시 작업의 결과 반영 하지 않을 수 있습니다.

##  <a name="swap"></a> swap

두 개의 동시 우선 순위 큐의 내용을 바꿉니다. 이 메서드는 동시성이 보장 되지 않습니다.

```
void swap(concurrent_priority_queue& _Queue);
```

### <a name="parameters"></a>매개 변수

*_Queue*<br/>
`concurrent_priority_queue` 개체를 사용 하 여 콘텐츠를 교환 합니다.

##  <a name="try_pop"></a> try_pop

큐가 비어 있지 않은 경우 큐에서 우선 순위가 가장 높은 요소를 제거하고 반환합니다. 이 메서드는 동시성이 보장 합니다.

```
bool try_pop(reference _Elem);
```

### <a name="parameters"></a>매개 변수

*_Elem*<br/>
큐가 비어 있지 않은 경우 가장 높은 우선 순위 요소를 사용 하 여 채울 수 있는 변수에 대 한 참조입니다.

### <a name="return-value"></a>반환 값

**true 이면** 값을 팝 하는 경우 **false** 그렇지 않은 경우.

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[병렬 컨테이너 및 개체](../../../parallel/concrt/parallel-containers-and-objects.md)
