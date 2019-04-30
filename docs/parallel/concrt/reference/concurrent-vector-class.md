---
title: concurrent_vector 클래스
ms.date: 11/04/2016
f1_keywords:
- concurrent_vector
- CONCURRENT_VECTOR/concurrency::concurrent_vector
- CONCURRENT_VECTOR/concurrency::concurrent_vector::concurrent_vector
- CONCURRENT_VECTOR/concurrency::concurrent_vector::assign
- CONCURRENT_VECTOR/concurrency::concurrent_vector::at
- CONCURRENT_VECTOR/concurrency::concurrent_vector::back
- CONCURRENT_VECTOR/concurrency::concurrent_vector::begin
- CONCURRENT_VECTOR/concurrency::concurrent_vector::capacity
- CONCURRENT_VECTOR/concurrency::concurrent_vector::cbegin
- CONCURRENT_VECTOR/concurrency::concurrent_vector::cend
- CONCURRENT_VECTOR/concurrency::concurrent_vector::clear
- CONCURRENT_VECTOR/concurrency::concurrent_vector::crbegin
- CONCURRENT_VECTOR/concurrency::concurrent_vector::crend
- CONCURRENT_VECTOR/concurrency::concurrent_vector::empty
- CONCURRENT_VECTOR/concurrency::concurrent_vector::end
- CONCURRENT_VECTOR/concurrency::concurrent_vector::front
- CONCURRENT_VECTOR/concurrency::concurrent_vector::get_allocator
- CONCURRENT_VECTOR/concurrency::concurrent_vector::grow_by
- CONCURRENT_VECTOR/concurrency::concurrent_vector::grow_to_at_least
- CONCURRENT_VECTOR/concurrency::concurrent_vector::max_size
- CONCURRENT_VECTOR/concurrency::concurrent_vector::push_back
- CONCURRENT_VECTOR/concurrency::concurrent_vector::rbegin
- CONCURRENT_VECTOR/concurrency::concurrent_vector::rend
- CONCURRENT_VECTOR/concurrency::concurrent_vector::reserve
- CONCURRENT_VECTOR/concurrency::concurrent_vector::resize
- CONCURRENT_VECTOR/concurrency::concurrent_vector::shrink_to_fit
- CONCURRENT_VECTOR/concurrency::concurrent_vector::size
- CONCURRENT_VECTOR/concurrency::concurrent_vector::swap
helpviewer_keywords:
- concurrent_vector class
ms.assetid: a217b4ac-af2b-4d41-94eb-09a75ee28622
ms.openlocfilehash: 7c2ca35239dfb3ce4c0f710259f54005ff9f3c94
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62224209"
---
# <a name="concurrentvector-class"></a>concurrent_vector 클래스

`concurrent_vector` 클래스는 모든 요소에 대해 임의 액세스를 허용하는 시퀀스 컨테이너 클래스입니다. 동시성으로부터 안전한 추가, 요소 액세스, 반복기 액세스 및 반복기 통과 작업을 사용할 수 있게 합니다.

## <a name="syntax"></a>구문

```
template<typename T, class _Ax>
class concurrent_vector: protected details::_Allocator_base<T,
    _Ax>,
private details::_Concurrent_vector_base_v4;
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
벡터에 저장 될 요소의 데이터 형식입니다.

*_Ax*<br/>
할당 및 동시 벡터에 대 한 메모리 할당 취소 하는 방법에 대 한 세부 정보를 캡슐화 하는 저장 된 할당자 개체를 나타내는 형식입니다. 이 인수는 선택 사항이며 기본값은 `allocator<T>`입니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|이름|설명|
|----------|-----------------|
|`allocator_type`|동시 벡터에 대 한 할당자 클래스를 나타내는 형식입니다.|
|`const_iterator`|읽을 수 있는 임의 액세스 반복기를 제공 하는 형식은 `const` 동시 벡터의 요소입니다.|
|`const_pointer`|에 대 한 포인터를 제공 하는 형식은 `const` 동시 벡터의 요소입니다.|
|`const_reference`|에 대 한 참조를 제공 하는 형식에 `const` 읽고 수행 하기 위해 동시 벡터에 저장 된 요소의 `const` 작업 합니다.|
|`const_reverse_iterator`|읽을 수 있는 임의 액세스 반복기를 제공 하는 형식 `const` 동시 벡터의 요소입니다.|
|`difference_type`|동시 벡터 내에서 두 요소 사이의 부호가 있는 거리를 제공 하는 형식입니다.|
|`iterator`|동시 벡터의 모든 요소를 읽을 수 있는 임의 액세스 반복기를 제공 하는 형식입니다. 반복기를 사용 하 여 요소의 수정 동시성 으로부터 안전한 아닙니다.|
|`pointer`|동시 벡터의 요소에에서 대 한 포인터를 제공 하는 형식입니다.|
|`reference`|동시 벡터에 저장 된 요소에 대 한 참조를 제공 하는 형식입니다.|
|`reverse_iterator`|역방향된 동시 벡터에 있는 모든 요소를 읽을 수 있는 임의 액세스 반복기를 제공 하는 형식입니다. 반복기를 사용 하 여 요소의 수정 동시성 으로부터 안전한 아닙니다.|
|`size_type`|동시 벡터의 요소 수를 계산 하는 형식입니다.|
|`value_type`|동시 벡터에 저장 된 데이터 형식을 나타내는 형식입니다.|

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[concurrent_vector](#ctor)|오버로드됨. 동시 벡터를 생성합니다.|
|[~ concurrent_vector 소멸자](#dtor)|모든 요소를 삭제 하 고이 동시 벡터를 제거 합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[assign](#assign)|오버로드됨. 동시 벡터의 요소를 삭제 하 고을 할당 `_N` 복사본 `_Item`, 또는 반복기 범위 지정 된 값 [ `_Begin`, `_End`). 이 메서드는 동시성이 보장 되지 않습니다.|
|[at](#at)|오버로드됨. 동시 벡터의 지정된 된 인덱스에 있는 요소에 대 한 액세스를 제공합니다. 이 메서드는 동시성이 읽기 작업에 대 한 및 보장 하는 값으로 벡터를 증가 하는 동안 `_Index` 동시 벡터 크기 보다 작습니다.|
|[back](#back)|오버로드됨. 참조 또는 반환 `const` 마지막 동시 벡터의 요소를 참조 합니다. 동시 벡터가 비어 있으면 반환 값은 정의 되지 않습니다. 이 메서드는 동시성이 보장 합니다.|
|[begin](#begin)|오버로드됨. 형식의 반복기를 반환 `iterator` 또는 `const_iterator` 동시 벡터의 시작 부분에 있습니다. 이 메서드는 동시성이 보장 합니다.|
|[capacity](#capacity)|동시 벡터가 더 많은 메모리를 할당 하지 않고도 증가할 수 있는 최대 크기를 반환 합니다. 이 메서드는 동시성이 보장 합니다.|
|[cbegin](#cbegin)|형식의 반복기를 반환 `const_iterator` 동시 벡터의 시작 부분에 있습니다. 이 메서드는 동시성이 보장 합니다.|
|[cend](#cend)|형식의 반복기를 반환 `const_iterator` 동시 벡터의 끝에 있습니다. 이 메서드는 동시성이 보장 합니다.|
|[clear](#clear)|동시 벡터의 모든 요소를 지웁니다. 이 메서드는 동시성이 보장 되지 않습니다.|
|[crbegin](#crbegin)|형식의 반복기를 반환 `const_reverse_iterator` 동시 벡터의 시작 부분에 있습니다. 이 메서드는 동시성이 보장 합니다.|
|[crend](#crend)|형식의 반복기를 반환 `const_reverse_iterator` 동시 벡터의 끝에 있습니다. 이 메서드는 동시성이 보장 합니다.|
|[empty](#empty)|테스트 시 동시 벡터가 비어 있으면이 메서드가 호출 됩니다. 이 메서드는 동시성이 보장 합니다.|
|[end](#end)|오버로드됨. 형식의 반복기를 반환 `iterator` 또는 `const_iterator` 동시 벡터의 끝에 있습니다. 이 메서드는 동시성이 보장 합니다.|
|[front](#front)|오버로드됨. 참조 또는 반환 `const` 동시 벡터의 첫 번째 요소에 대 한 참조입니다. 동시 벡터가 비어 있으면 반환 값은 정의 되지 않습니다. 이 메서드는 동시성이 보장 합니다.|
|[get_allocator](#get_allocator)|동시 벡터를 생성 하는 데 사용 되는 할당자 복사본을 반환 합니다. 이 메서드는 동시성이 보장 합니다.|
|[grow_by](#grow_by)|오버로드됨. 이 동시 벡터가 확장 `_Delta` 요소입니다. 이 메서드는 동시성이 보장 합니다.|
|[grow_to_at_least](#grow_to_at_least)|이상까지이 동시 벡터가 확장 `_N` 요소입니다. 이 메서드는 동시성이 보장 합니다.|
|[max_size](#max_size)|동시 벡터 저장할 수 있는 요소의 최대 수를 반환 합니다. 이 메서드는 동시성이 보장 합니다.|
|[push_back](#push_back)|오버로드됨. 동시 벡터의 끝에 지정된 된 항목을 추가합니다. 이 메서드는 동시성이 보장 합니다.|
|[rbegin](#rbegin)|오버로드됨. 형식의 반복기를 반환 `reverse_iterator` 또는 `const_reverse_iterator` 동시 벡터의 시작 부분에 있습니다. 이 메서드는 동시성이 보장 합니다.|
|[rend](#rend)|오버로드됨. 형식의 반복기를 반환 `reverse_iterator` 또는 `const_reverse_iterator` 동시 벡터의 끝에 있습니다. 이 메서드는 동시성이 보장 합니다.|
|[reserve](#reserve)|동시 벡터 크기가 증가할 충분 한 공간이 할당 `_N` 나중에 더 많은 메모리를 할당 하지 않고도 합니다. 이 메서드는 동시성이 보장 되지 않습니다.|
|[resize](#resize)|오버로드됨. 필요에 따라 요소를 추가 또는 삭제를 요청한 크기로 동시 벡터의 크기를 변경 합니다. 이 메서드는 동시성이 보장 되지 않습니다.|
|[shrink_to_fit](#shrink_to_fit)|조각화를 줄이고 메모리 사용을 최적화 하는 동시 벡터의 내부 표현이 압축 합니다. 이 메서드는 동시성이 보장 되지 않습니다.|
|[size](#size)|동시 벡터의 요소 수를 반환합니다. 이 메서드는 동시성이 보장 합니다.|
|[swap](#swap)|두 개의 동시 벡터의 내용을 바꿉니다. 이 메서드는 동시성이 보장 되지 않습니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[operator\[\]](#operator_at)|오버로드됨. 동시 벡터의 지정된 된 인덱스에 있는 요소에 대 한 액세스를 제공합니다. 이 메서드는 동시성이 읽기 작업에 대 한 및 보장 하는 값으로 벡터를 증가 하는 동안 `_Index` 동시 벡터 크기 보다 작습니다.|
|[operator=](#operator_eq)|오버로드됨. 다른 내용을 할당 `concurrent_vector` 여기에 개체입니다. 이 메서드는 동시성이 보장 되지 않습니다.|

## <a name="remarks"></a>설명

대 한 자세한 내용은 합니다 `concurrent_vector` 클래스를 참조 하십시오 [병렬 컨테이너 및 개체](../../../parallel/concrt/parallel-containers-and-objects.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층

`_Concurrent_vector_base_v4`

`_Allocator_base`

`concurrent_vector`

## <a name="requirements"></a>요구 사항

**헤더:** concurrent_vector.h

**네임스페이스:** 동시성

##  <a name="assign"></a> assign

동시 벡터의 요소를 삭제 하 고을 할당 `_N` 복사본 `_Item`, 또는 반복기 범위 지정 된 값 [ `_Begin`, `_End`). 이 메서드는 동시성이 보장 되지 않습니다.

```
void assign(
    size_type _N,
    const_reference _Item);

template<class _InputIterator>
void assign(_InputIterator _Begin,
    _InputIterator _End);
```

### <a name="parameters"></a>매개 변수

*_InputIterator*<br/>
지정 된 반복기의 형식입니다.

*_N*<br/>
동시 벡터에 복사할 항목의 수입니다.

*_Item*<br/>
동시 벡터를 채우는 데 사용 되는 값에 대 한 참조입니다.

*_Begin*<br/>
소스 범위의 첫 번째 요소는 반복기입니다.

*_End*<br/>
소스 범위의 마지막 요소 하나 다음에 반복기입니다.

### <a name="remarks"></a>설명

`assign` 동시성 안전 하지 않습니다. 다른 스레드가 없을 때 메서드를 호출 동시 벡터에서이 메서드를 호출 해야 합니다.

##  <a name="at"></a> 에서

동시 벡터의 지정된 된 인덱스에 있는 요소에 대 한 액세스를 제공합니다. 이 메서드는 동시성이 읽기 작업에 대 한 및 보장 하는 값으로 벡터를 증가 하는 동안 `_Index` 동시 벡터 크기 보다 작습니다.

```
reference at(size_type _Index);

const_reference at(size_type _Index) const;
```

### <a name="parameters"></a>매개 변수

*_Index*<br/>
검색할 요소의 인덱스입니다.

### <a name="return-value"></a>반환 값

지정된 된 인덱스의 항목에 대 한 참조입니다.

### <a name="remarks"></a>설명

버전의 함수 `at` 반환 하는 비- `const` 참조 요소에 서로 다른 여러 스레드에서 동시에 쓰는 데 사용할 수 없습니다. 다른 동기화 개체를 동시 읽기를 동기화 하 고 동일한 데이터 요소에 작업을 작성 하는 것 같습니다.

메서드에서 throw `out_of_range` 하는 경우 `_Index` 동시 벡터 크기 보다 크거나 같은 경우에 및 `range_error` 인덱스 벡터의 손상 된 부분에 대 한 경우. 벡터 손상 될 수 있습니다 하는 방법에 대 한 내용은 참조 하세요 [병렬 컨테이너 및 개체](../../../parallel/concrt/parallel-containers-and-objects.md)합니다.

##  <a name="back"></a> 뒤로

참조 또는 반환 `const` 마지막 동시 벡터의 요소를 참조 합니다. 동시 벡터가 비어 있으면 반환 값은 정의 되지 않습니다. 이 메서드는 동시성이 보장 합니다.

```
reference back();

const_reference back() const;
```

### <a name="return-value"></a>반환 값

참조 또는 `const` 마지막 동시 벡터의 요소를 참조 합니다.

##  <a name="begin"></a> 시작

형식의 반복기를 반환 `iterator` 또는 `const_iterator` 동시 벡터의 시작 부분에 있습니다. 이 메서드는 동시성이 보장 합니다.

```
iterator begin();

const_iterator begin() const;
```

### <a name="return-value"></a>반환 값

형식의 반복기 `iterator` 또는 `const_iterator` 동시 벡터의 시작 부분에 있습니다.

##  <a name="capacity"></a> 용량

동시 벡터가 더 많은 메모리를 할당 하지 않고도 증가할 수 있는 최대 크기를 반환 합니다. 이 메서드는 동시성이 보장 합니다.

```
size_type capacity() const;
```

### <a name="return-value"></a>반환 값

동시 벡터가 더 많은 메모리를 할당하지 않고도 확장할 수 있는 최대 크기입니다.

### <a name="remarks"></a>설명

달리는 C++ 표준 라이브러리 `vector`하면 `concurrent_vector` 개체가 더 많은 메모리를 할당 하는 경우 기존 요소를 이동 하지 않도록 합니다.

##  <a name="cbegin"></a> cbegin

형식의 반복기를 반환 `const_iterator` 동시 벡터의 시작 부분에 있습니다. 이 메서드는 동시성이 보장 합니다.

```
const_iterator cbegin() const;
```

### <a name="return-value"></a>반환 값

반복기 형식의 `const_iterator` 동시 벡터의 시작 부분에 있습니다.

##  <a name="cend"></a> cend

형식의 반복기를 반환 `const_iterator` 동시 벡터의 끝에 있습니다. 이 메서드는 동시성이 보장 합니다.

```
const_iterator cend() const;
```

### <a name="return-value"></a>반환 값

반복기 형식의 `const_iterator` 동시 벡터의 끝에 있습니다.

##  <a name="clear"></a> 지우기

동시 벡터의 모든 요소를 지웁니다. 이 메서드는 동시성이 보장 되지 않습니다.

```
void clear();
```

### <a name="remarks"></a>설명

`clear` 동시성 안전 하지 않습니다. 다른 스레드가 없을 때 메서드를 호출 동시 벡터에서이 메서드를 호출 해야 합니다. `clear` 내부 배열 해제 하지 않습니다. 내부 배열을 확보 하기 위해 함수를 호출 `shrink_to_fit` 후 `clear`합니다.

##  <a name="ctor"></a> concurrent_vector

동시 벡터를 생성합니다.

```
explicit concurrent_vector(
    const allocator_type& _Al = allocator_type());

concurrent_vector(
    const concurrent_vector& _Vector);

template<class M>
concurrent_vector(
    const concurrent_vector<T,
    M>& _Vector,
    const allocator_type& _Al = allocator_type());

concurrent_vector(
    concurrent_vector&& _Vector);

explicit concurrent_vector(
    size_type _N);

concurrent_vector(
    size_type _N,
    const_reference _Item,
    const allocator_type& _Al = allocator_type());

template<class _InputIterator>
concurrent_vector(_InputIterator _Begin,
    _InputIterator _End,
    const allocator_type& _Al = allocator_type());
```

### <a name="parameters"></a>매개 변수

*M*<br/>
할당자 유형 원본 벡터입니다.

*_InputIterator*<br/>
입력 반복기의 형식입니다.

*_Al*<br/>
이 개체에 사용할 할당자 클래스입니다.

*_Vector*<br/>
요소를 복사해 오거나 이동해 올 소스 `concurrent_vector` 개체입니다.

*_N*<br/>
`concurrent_vector` 개체의 초기 용량입니다.

*_Item*<br/>
생성된 된 개체의 요소 값입니다.

*_Begin*<br/>
복사할 요소의 범위에서 첫 번째 요소의 위치입니다.

*_End*<br/>
복사할 요소의 범위를 벗어난 첫 번째 요소의 위치입니다.

### <a name="remarks"></a>설명

모든 생성자는 할당자 개체를 저장 `_Al` 는 벡터를 초기화 합니다.

첫 번째 생성자는 빈 초기 벡터를 지정 및 할당자 형식을 명시적으로 지정 합니다. 사용할 수 있습니다.

동시 벡터의 복사본을 지정 하는 두 번째 및 세 번째 생성자 `_Vector`합니다.

네 번째 생성자는 동시 벡터 `_Vector`의 이동을 지정합니다.

다섯 번째 생성자는 지정된 된 수의 반복을 지정 ( `_N`) 클래스에 대 한 기본값 요소의 `T`합니다.

여섯 번째 생성자는 반복을 지정 합니다 ( `_N`) 값의 요소 `_Item`합니다.

마지막 생성자는 반복기 범위에서 제공 하는 값을 지정 [ `_Begin`, `_End`).

##  <a name="dtor"></a> ~concurrent_vector

모든 요소를 삭제 하 고이 동시 벡터를 제거 합니다.

```
~concurrent_vector();
```

##  <a name="crbegin"></a> crbegin

형식의 반복기를 반환 `const_reverse_iterator` 동시 벡터의 시작 부분에 있습니다. 이 메서드는 동시성이 보장 합니다.

```
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>반환 값

반복기 형식의 `const_reverse_iterator` 동시 벡터의 시작 부분에 있습니다.

##  <a name="crend"></a> crend

형식의 반복기를 반환 `const_reverse_iterator` 동시 벡터의 끝에 있습니다. 이 메서드는 동시성이 보장 합니다.

```
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>반환 값

반복기 형식의 `const_reverse_iterator` 동시 벡터의 끝에 있습니다.

##  <a name="empty"></a> empty

테스트 시 동시 벡터가 비어 있으면이 메서드가 호출 됩니다. 이 메서드는 동시성이 보장 합니다.

```
bool empty() const;
```

### <a name="return-value"></a>반환 값

**true 이면** 함수가 호출 된 시점 벡터가 비어 있으면 **false** 그렇지 않은 경우.

##  <a name="end"></a> 끝

형식의 반복기를 반환 `iterator` 또는 `const_iterator` 동시 벡터의 끝에 있습니다. 이 메서드는 동시성이 보장 합니다.

```
iterator end();

const_iterator end() const;
```

### <a name="return-value"></a>반환 값

형식의 반복기 `iterator` 또는 `const_iterator` 동시 벡터의 끝에 있습니다.

##  <a name="front"></a> front

참조 또는 반환 `const` 동시 벡터의 첫 번째 요소에 대 한 참조입니다. 동시 벡터가 비어 있으면 반환 값은 정의 되지 않습니다. 이 메서드는 동시성이 보장 합니다.

```
reference front();

const_reference front() const;
```

### <a name="return-value"></a>반환 값

참조 또는 `const` 동시 벡터의 첫 번째 요소에 대 한 참조입니다.

##  <a name="get_allocator"></a> get_allocator

동시 벡터를 생성 하는 데 사용 되는 할당자 복사본을 반환 합니다. 이 메서드는 동시성이 보장 합니다.

```
allocator_type get_allocator() const;
```

### <a name="return-value"></a>반환 값

생성 하는 데 사용 되는 할당자 복사본을 `concurrent_vector` 개체입니다.

##  <a name="grow_by"></a> grow_by

이 동시 벡터가 확장 `_Delta` 요소입니다. 이 메서드는 동시성이 보장 합니다.

```
iterator grow_by(
    size_type _Delta);

iterator grow_by(
    size_type _Delta,
    const_reference _Item);
```

### <a name="parameters"></a>매개 변수

*_Delta*<br/>
개체에 추가할 요소의 수입니다.

*_Item*<br/>
새 요소를 초기화할 값입니다.

### <a name="return-value"></a>반환 값

첫 번째 항목에 대 한 반복기를 추가 합니다.

### <a name="remarks"></a>설명

경우 `_Item` 지정 하지 않으면 새 요소는 기본 생성 합니다.

##  <a name="grow_to_at_least"></a> grow_to_at_least

이상까지이 동시 벡터가 확장 `_N` 요소입니다. 이 메서드는 동시성이 보장 합니다.

```
iterator grow_to_at_least(size_type _N);
```

### <a name="parameters"></a>매개 변수

*_N*<br/>
에 대 한 새 최소 크기는 `concurrent_vector` 개체입니다.

### <a name="return-value"></a>반환 값

추가 된 시퀀스의 시작 부분 또는 인덱스의 요소를 가리키는 반복자 `_N` 요소가 추가 된 경우.

##  <a name="max_size"></a> max_size

동시 벡터 저장할 수 있는 요소의 최대 수를 반환 합니다. 이 메서드는 동시성이 보장 합니다.

```
size_type max_size() const;
```

### <a name="return-value"></a>반환 값

요소의 최대 개수는 `concurrent_vector` 개체가 보유할 수 있습니다.

##  <a name="operator_eq"></a> operator=

다른 내용을 할당 `concurrent_vector` 여기에 개체입니다. 이 메서드는 동시성이 보장 되지 않습니다.

```
concurrent_vector& operator= (
    const concurrent_vector& _Vector);

template<class M>
concurrent_vector& operator= (
    const concurrent_vector<T, M>& _Vector);

concurrent_vector& operator= (
    concurrent_vector&& _Vector);
```

### <a name="parameters"></a>매개 변수

*M*<br/>
할당자 유형 원본 벡터입니다.

*_Vector*<br/>
소스 `concurrent_vector` 개체입니다.

### <a name="return-value"></a>반환 값

이에 대 한 참조 `concurrent_vector` 개체입니다.

##  <a name="operator_at"></a> operator[]

동시 벡터의 지정된 된 인덱스에 있는 요소에 대 한 액세스를 제공합니다. 이 메서드는 동시성이 읽기 작업에 대 한 및 보장 하는 값으로 벡터를 증가 하는 동안 `_Index` 동시 벡터 크기 보다 작습니다.

```
reference operator[](size_type _index);

const_reference operator[](size_type _index) const;
```

### <a name="parameters"></a>매개 변수

*_Index*<br/>
검색할 요소의 인덱스입니다.

### <a name="return-value"></a>반환 값

지정된 된 인덱스의 항목에 대 한 참조입니다.

### <a name="remarks"></a>설명

버전 `operator []` 반환 하는 비- `const` 참조 요소에 서로 다른 여러 스레드에서 동시에 쓰는 데 사용할 수 없습니다. 다른 동기화 개체를 동시 읽기를 동기화 하 고 동일한 데이터 요소에 작업을 작성 하는 것 같습니다.

없는 범위 검사를 수행 하는 되도록 `_Index` 동시 벡터로 인덱스가 잘못 되었습니다.

##  <a name="push_back"></a> push_back

동시 벡터의 끝에 지정된 된 항목을 추가합니다. 이 메서드는 동시성이 보장 합니다.

```
iterator push_back(const_reference _Item);

iterator push_back(T&& _Item);
```

### <a name="parameters"></a>매개 변수

*_Item*<br/>
추가할 값입니다.

### <a name="return-value"></a>반환 값

반복기 항목을 추가 합니다.

##  <a name="rbegin"></a> rbegin

형식의 반복기를 반환 `reverse_iterator` 또는 `const_reverse_iterator` 동시 벡터의 시작 부분에 있습니다. 이 메서드는 동시성이 보장 합니다.

```
reverse_iterator rbegin();

const_reverse_iterator rbegin() const;
```

### <a name="return-value"></a>반환 값

형식의 반복기 `reverse_iterator` 또는 `const_reverse_iterator` 동시 벡터의 시작 부분에 있습니다.

##  <a name="rend"></a> rend

형식의 반복기를 반환 `reverse_iterator` 또는 `const_reverse_iterator` 동시 벡터의 끝에 있습니다. 이 메서드는 동시성이 보장 합니다.

```
reverse_iterator rend();

const_reverse_iterator rend() const;
```

### <a name="return-value"></a>반환 값

형식의 반복기 `reverse_iterator` 또는 `const_reverse_iterator` 동시 벡터의 끝에 있습니다.

##  <a name="reserve"></a> 예약

동시 벡터 크기가 증가할 충분 한 공간이 할당 `_N` 나중에 더 많은 메모리를 할당 하지 않고도 합니다. 이 메서드는 동시성이 보장 되지 않습니다.

```
void reserve(size_type _N);
```

### <a name="parameters"></a>매개 변수

*_N*<br/>
에 대 한 공간을 예약 요소의 수입니다.

### <a name="remarks"></a>설명

`reserve` 동시성 안전 하지 않습니다. 다른 스레드가 없을 때 메서드를 호출 동시 벡터에서이 메서드를 호출 해야 합니다. 메서드가 반환 된 후 동시 벡터의 용량을 요청된 된 예약 보다 클 수 있습니다.

##  <a name="resize"></a> 크기 조정

필요에 따라 요소를 추가 또는 삭제를 요청한 크기로 동시 벡터의 크기를 변경 합니다. 이 메서드는 동시성이 보장 되지 않습니다.

```
void resize(
    size_type _N);

void resize(
    size_type _N,
    const T& val);
```

### <a name="parameters"></a>매개 변수

*_N*<br/>
동시 벡터의 새 크기입니다.

*val*<br/>
새 크기가 원래 크기보다 크면 새 요소의 값이 벡터에 추가됩니다. 값을 생략 하는 경우 새 개체의 형식에 대 한 기본 값을 할당 됩니다.

### <a name="remarks"></a>설명

컨테이너의 크기가 요청된 된 크기 보다 작은 경우 요청된 된 크기에 도달할 때까지 벡터에 요소가 추가 됩니다. 컨테이너의 크기가 요청된 된 크기 보다 큰 경우 컨테이너 크기에 도달할 때까지 컨테이너의 끝에 가장 가까운 요소가 삭제 됩니다 `_N`합니다. 컨테이너의 현재 크기와 요청된 크기가 동일하면 아무런 작업도 실행되지 않습니다.

`resize` 없는 경우 동시성 안전 다른 스레드가 없을 때 메서드를 호출 동시 벡터에서이 메서드를 호출 해야 합니다.

##  <a name="shrink_to_fit"></a> shrink_to_fit

조각화를 줄이고 메모리 사용을 최적화 하는 동시 벡터의 내부 표현이 압축 합니다. 이 메서드는 동시성이 보장 되지 않습니다.

```
void shrink_to_fit();
```

### <a name="remarks"></a>설명

이 메서드는 내부적으로 다시 할당 메모리 이동 요소, 모든 반복기를 무효화 합니다. `shrink_to_fit` 동시성 안전 하지 않습니다. 다른 스레드가 없을 때 메서드를 호출 동시 벡터에서이 함수를 호출 해야 합니다.

##  <a name="size"></a> 크기

동시 벡터의 요소 수를 반환합니다. 이 메서드는 동시성이 보장 합니다.

```
size_type size() const;
```

### <a name="return-value"></a>반환 값

이 요소 수가 `concurrent_vector` 개체입니다.

### <a name="remarks"></a>설명

반환 되는 크기는 함수를 호출 하 여 추가 된 모든 요소를 포함 하도록 보장 됩니다 `push_back`, 또는이 메서드를 호출 하기 전에 완료 된 작업을 확장 합니다. 그러나 할당 되는 요소를 포함할 수도 있습니다 하지만 여전히 증가 방법 중 하나에 대 한 동시 호출 하 여 생성 합니다.

##  <a name="swap"></a> swap

두 개의 동시 벡터의 내용을 바꿉니다. 이 메서드는 동시성이 보장 되지 않습니다.

```
void swap(concurrent_vector& _Vector);
```

### <a name="parameters"></a>매개 변수

*_Vector*<br/>
`concurrent_vector` 개체를 사용 하 여 콘텐츠를 교환 합니다.

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[병렬 컨테이너 및 개체](../../../parallel/concrt/parallel-containers-and-objects.md)
