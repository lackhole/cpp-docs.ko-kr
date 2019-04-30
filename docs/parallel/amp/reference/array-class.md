---
title: array 클래스
ms.date: 11/04/2016
f1_keywords:
- array
- AMP/array
- AMP/Concurrency::array::array
- AMP/Concurrency::array::copy_to
- AMP/Concurrency::array::data
- AMP/Concurrency::array::get_accelerator_view
- AMP/Concurrency::array::get_associated_accelerator_view
- AMP/Concurrency::array::get_cpu_access_type
- AMP/Concurrency::array::get_extent
- AMP/Concurrency::array::reinterpret_as
- AMP/Concurrency::array::section
- AMP/Concurrency::array::view_as
- AMP/Concurrency::array::rank
- AMP/Concurrency::array::accelerator_view
- AMP/Concurrency::array::associated_accelerator_view
- AMP/Concurrency::array::cpu_access_type
- AMP/Concurrency::array::extent
helpviewer_keywords:
- array class
ms.assetid: 0832b6c1-40f0-421d-9104-6b1baa0c63a7
ms.openlocfilehash: 16d18d23c370a8a603ab6150fcee18455ae47c48
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405510"
---
# <a name="array-class"></a>array 클래스

액셀러레이터로 데이터를 이동 하는 데 데이터 컨테이너를 나타냅니다.

## <a name="syntax"></a>구문

```
template <typename value_type, int _Rank>
friend class array;
```

#### <a name="parameters"></a>매개 변수

*value_type*<br/>
데이터의 요소 형식입니다.

*_Rank*<br/>
배열의 차수입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[배열 생성자](#ctor)|`array` 클래스의 새 인스턴스를 초기화합니다.|
|[~ array 소멸자](#dtor)|제거 된 `array` 개체입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[copy_to](#copy_to)|배열의 내용을 다른 배열로 복사합니다.|
|[data](#data)|배열의 원시 데이터에 대 한 포인터를 반환합니다.|
|[get_accelerator_view](#get_accelerator_view)|반환 된 [accelerator_view](accelerator-view-class.md) 배열 할당 된 위치를 나타내는 개체입니다. 이 속성은 CPU 에서만 액세스할 수 있습니다.|
|[get_associated_accelerator_view](#get_associated_accelerator_view)|두 번째 가져옵니다 [accelerator_view](accelerator-view-class.md) 인스턴스화하는 스테이징 생성자를 호출할 때 매개 변수로 전달 되는 개체는 `array` 개체입니다.|
|[get_cpu_access_type](#get_cpu_access_type)|반환 된 [access_type](concurrency-namespace-enums-amp.md#access_type) 배열입니다. 이 메서드는 CPU 에서만 액세스할 수 있습니다.|
|[get_extent](#get_extent)|반환 된 [익스텐트](extent-class.md) 개체 배열입니다.|
|[reinterpret_as](#reinterpret_as)|모든 요소를 포함 하는 1 차원 배열을 반환 합니다 `array` 개체입니다.|
|[section](#section)|하위 단원을 반환 합니다 `array` 에 지정 된 origin을 있고, 선택적으로 하는 개체에 지정된 된 범위입니다.|
|[view_as](#view_as)|반환 된 [array_view](array-view-class.md) 에서 생성 된 개체는 `array` 개체.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[operator std::vector&lt;value_type&gt;](#operator_vec)|사용 하 여 `copy(*this, vector)` 변환할 암시적으로 배열 된 std::[벡터](../../../standard-library/vector-class.md) 개체입니다.|
|[operator()](#operator_call)|매개 변수로 지정 된 요소 값을 반환 합니다.|
|[operator\[\]](#operator_at)|지정된 된 인덱스에 있는 요소를 반환 합니다.|
|[operator=](#operator_eq)|지정 된 내용을 복사 `array` 을 여기에 개체입니다.|

### <a name="public-constants"></a>공용 상수

|이름|설명|
|----------|-----------------|
|[rank 상수](#rank)|배열의 차수를 저장합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[accelerator_view](#accelerator_view)|가져옵니다 합니다 [accelerator_view](accelerator-view-class.md) 배열 할당 된 위치를 나타내는 개체입니다. 이 속성은 CPU 에서만 액세스할 수 있습니다.|
|[associated_accelerator_view](#associated_accelerator_view)|두 번째 가져옵니다 [accelerator_view](accelerator-view-class.md) 인스턴스화하는 스테이징 생성자를 호출할 때 매개 변수로 전달 되는 개체는 `array` 개체입니다.|
|[cpu_access_type](#cpu_access_type)|가져옵니다 합니다 [access_type](concurrency-namespace-enums-amp.md#access_type) CPU 배열의 저장소에 액세스 하는 방법을 나타내는입니다.|
|[extent](#extent)|배열의 모양을 정의 하는 범위를 가져옵니다.|

## <a name="remarks"></a>설명

형식 `array<T,N>` 나타냅니다 밀도가 높고 일반적인 (가변 아님) *N*-액셀러레이터 또는 CPU와 같은 특정 위치에 있는 차원 배열입니다. 배열에서 요소의 데이터 형식이 `T`, 대상 액셀러레이터와 호환 되는 형식 이어야 합니다. 하지만 순위 `N`, (의 배열을 정적으로 결정 되며 형식의 일부, 배열의 범위는 런타임에 의해 결정 되며 클래스를 사용 하 여 표현 됩니다 `extent<N>`합니다.

배열 차원 개수에 관계 없이 가질 수 있는 몇 가지 기능에 특수화 되기 `array` 차수가 1, 2 또는 3을 사용 하 여 개체입니다. 차원 인수를 생략 하면 기본값은 1입니다.

배열 데이터는 연속적으로 메모리에 배치 합니다. 최하위 차원에서 차이가 있는 요소는 메모리 내에서 인접해 있습니다.

배열은은 배열이 다른 배열에 복사 하면 전체 복사를 수행 되기 때문에 논리적으로 값 형식으로 간주 됩니다. 두 배열이 동일한 데이터를 가리키지 않습니다.

`array<T,N>` 형식은 여러 시나리오에서 사용 됩니다.

- 액셀러레이터 키에 대 한 계산에 사용할 수 있는 데이터 컨테이너입니다.

- (사용할 수 있는 다른 배열에서 복사) 호스트 CPU에 대 한 메모리를 보유 하는 데이터 컨테이너입니다.

- 로 호스트-장치 복사 시에서 빠른 매개자 역할을 하는 스테이징 개체입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`array`

## <a name="requirements"></a>요구 사항

**헤더:** amp.h

**네임스페이스:** 동시성

##  <a name="dtor"></a> ~array

제거 된 `array` 개체입니다.

```
~array() restrict(cpu);
```

##  <a name="accelerator_view"></a> accelerator_view

가져옵니다 합니다 [accelerator_view](accelerator-view-class.md) 배열 할당 된 위치를 나타내는 개체입니다. 이 속성은 CPU 에서만 액세스할 수 있습니다.

```
__declspec(property(get= get_accelerator_view)) Concurrency::accelerator_view accelerator_view;
```

##  <a name="ctor"></a> 배열

새 인스턴스를 초기화 합니다 [array 클래스](array-class.md)합니다. 에 대 한 기본 생성자가 없는 `array<T,N>`합니다. 모든 생성자는 cpu 에서만 실행 됩니다. 이러한 Direct3D 대상에서는 실행할 수 없습니다.

```
explicit array(
    const Concurrency::extent<_Rank>& _Extent) restrict(cpu);

explicit array(
    int _E0) restrict(cpu);

explicit array(
    int _E0,
    int _E1) restrict(cpu);

explicit array(
    int _E0,
    int _E1,
    int _E2) restrict(cpu);

array(
    const Concurrency::extent<_Rank>& _Extent,
    Concurrency::accelerator_view _Av
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

array(
    int _E0,
    Concurrency::accelerator_view _Av
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

array(
    int _E0,
    int _E1,
    Concurrency::accelerator_view _Av
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

array(
    int _E0,
    int _E1,
    int _E2,
    Concurrency::accelerator_view _Av
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

array(
    const Concurrency::extent<_Rank>& _Extent,
    Concurrency::accelerator_view _Av,
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

array(
    int _E0,
    accelerator_view _Av,
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

array(
    int _E0,
    int _E1,
    Concurrency::accelerator_view _Av,
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

array(
    int _E0,
    int _E1,
    int _E2,
    Concurrency::accelerator_view _Av,
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

template <typename _InputIterator>
array(
    const Concurrency::extent<_Rank>& _Extent,
    _InputIterator _Src_first,
    _InputIterator _Src_last) restrict(cpu);

template <typename _InputIterator>
array(
    const Concurrency::extent<_Rank>& _Extent,
    _InputIterator _Src_first) restrict(cpu);

template <typename _InputIterator>
array(
    int _E0,
    _InputIterator _Src_first,
    _InputIterator _Src_last) restrict(cpu);

template <typename _InputIterator>
array(
    int _E0,
    _InputIterator _Src_first) restrict(cpu);

template <typename _InputIterator>
array(
    int _E0,
    int _E1,
    _InputIterator _Src_first,
    _InputIterator _Src_last) restrict(cpu);

template <typename _InputIterator>
array(
    int _E0,
    int _E1,
    _InputIterator _Src_first) restrict(cpu);

template <typename _InputIterator>
array(
    int _E0,
    int _E1,
    int _E2,
    _InputIterator _Src_first,
    _InputIterator _Src_last) restrict(cpu);

template <typename _InputIterator>
array(
    int _E0,
    int _E1,
    int _E2,
    _InputIterator _Src_first) restrict(cpu);

template <typename _InputIterator>
array(
    const Concurrency::extent<_Rank>& _Extent,
    _InputIterator _Src_first,
    _InputIterator _Src_last,
    Concurrency::accelerator_view _Av
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

template <typename _InputIterator>
array(
    const Concurrency::extent<_Rank>& _Extent,
    _InputIterator _Src_first,
    Concurrency::accelerator_view _Av
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

template <typename _InputIterator>
array(
    int _E0,
    _InputIterator _Src_first,
    _InputIterator _Src_last,
    Concurrency::accelerator_view _Av
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

template <typename _InputIterator>
array(
    int _E0,
    _InputIterator _Src_first,
    Concurrency::accelerator_view _Av
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

template <typename _InputIterator>
array(
    int _E0,
    int _E1,
    _InputIterator _Src_first,
    _InputIterator _Src_last,
    Concurrency::accelerator_view _Av
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

template <typename _InputIterator>
array(
    int _E0,
    int _E1,
    _InputIterator _Src_first,
    Concurrency::accelerator_view _Av
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

template <typename _InputIterator>
array(
    int _E0,
    int _E1,
    int _E2,
    _InputIterator _Src_first,
    _InputIterator _Src_last,
    Concurrency::accelerator_view _Av,
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

template <typename _InputIterator>
array(
    int _E0,
    int _E1,
    int _E2,
    _InputIterator _Src_first,
    Concurrency::accelerator_view _Av
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

template <typename _InputIterator>
array(
    const Concurrency::extent<_Rank>& _Extent,
    _InputIterator _Src_first,
    _InputIterator _Src_last,
    Concurrency::accelerator_view _Av,
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

template <typename _InputIterator>
array(
    const Concurrency::extent<_Rank>& _Extent,
    _InputIterator _Src_first,
    Concurrency::accelerator_view _Av,
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

template <typename _InputIterator>
array(
    int _E0,
    _InputIterator _Src_first,
    _InputIterator _Src_last,
    Concurrency::accelerator_view _Av,
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

template <typename _InputIterator>
array(
    int _E0, _InputIterator _Src_first,
    Concurrency::accelerator_view _Av,
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

template <typename _InputIterator>
array(
    int _E0,
    int _E1, _InputIterator _Src_first, _InputIterator _Src_last,
    Concurrency::accelerator_view _Av,
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

template <typename _InputIterator>
array(
    int _E0,
    int _E1, _InputIterator _Src_first,
    Concurrency::accelerator_view _Av,
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

template <typename _InputIterator>
array(
    int _E0,
    int _E1,
    int _E2, _InputIterator _Src_first, _InputIterator _Src_last,
    Concurrency::accelerator_view _Av,
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

template <typename _InputIterator>
array(
    int _E0,
    int _E1,
    int _E2, _InputIterator _Src_first,
    Concurrency::accelerator_view _Av,
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

explicit array(
    const array_view<const value_type, _Rank>& _Src) restrict(cpu);

array(
    const array_view<const value_type, _Rank>& _Src,
    accelerator_view _Av
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

array(
    const array_view<const value_type, _Rank>& _Src,
    accelerator_view _Av,
    accelerator_view _Associated_Av) restrict(cpu);

array(const array& _Other) restrict(cpu);

array(array&& _Other) restrict(cpu);
```

### <a name="parameters"></a>매개 변수

*_Associated_Av*<br/>
Accelerator_view는 배열의 기본 대상 위치를 지정 합니다.

*_Av*<br/>
[accelerator_view](accelerator-view-class.md) 배열의 위치를 지정 하는 개체입니다.

*_Cpu_access_type*<br/>
원하는 [access_type](concurrency-namespace-enums-amp.md#access_type) CPU에서 배열에 대 한 합니다. 이 매개 변수는 기본값은 `access_type_auto` 은 cpu `access_type` 런타임에 결정 합니다. 실제 CPU `access_type` 배열을 사용 하 여 쿼리할 수 있습니다에 대 한는 `get_cpu_access_type` 메서드.

*_Extent*<br/>
배열의 각 차원의 범위입니다.

*_E0*<br/>
이 섹션의 범위의 가장 중요 한 구성 요소입니다.

*_E1*<br/>
이 섹션의 범위는 다음-에-가장 중요 한 구성 요소입니다.

*_E2*<br/>
이 섹션의 범위의 가장 중요 하지 않은 구성 요소입니다.

*_InputIterator*<br/>
입력된 반복기의 형식입니다.

*_Src*<br/>
복사할 대상 개체입니다.

*_Src_first*<br/>
소스 컨테이너에는 시작 반복기입니다.

*_Src_last*<br/>
소스 컨테이너에 사용 되는 끝 반복기입니다.

*_Other*<br/>
다른 데이터 원본입니다.

*_Rank*<br/>
섹션의 순위입니다.

*value_type*<br/>
복사 된 요소의 데이터 형식입니다.

##  <a name="associated_accelerator_view"></a> associated_accelerator_view

두 번째 가져옵니다 [accelerator_view](accelerator-view-class.md) 인스턴스화하는 스테이징 생성자를 호출할 때 매개 변수로 전달 되는 개체는 `array` 개체입니다.

```
__declspec(property(get= get_associated_accelerator_view)) Concurrency::accelerator_view associated_accelerator_view;
```

##  <a name="copy_to"></a> copy_to

내용을 복사 합니다 `array` 간 `array`합니다.

```
void copy_to(
    array<value_type, _Rank>& _Dest) const ;

void copy_to(
    array_view<value_type, _Rank>& _Dest) const ;
```

### <a name="parameters"></a>매개 변수

*_Dest*<br/>
합니다 [array_view](array-view-class.md) 복사할 개체입니다.

##  <a name="cpu_access_type"></a> cpu_access_type

이 배열에 허용 되는 CPU access_type을 가져옵니다.

```
__declspec(property(get= get_cpu_access_type)) access_type cpu_access_type;
```

##  <a name="data"></a> 데이터

원시 데이터에 대 한 포인터를 반환 합니다 `array`합니다.

```
value_type* data() restrict(amp, cpu);

const value_type* data() const restrict(amp, cpu);
```

### <a name="return-value"></a>반환 값

배열의 원시 데이터에 대 한 포인터입니다.

##  <a name="extent"></a> 범위

가져옵니다 합니다 [익스텐트](extent-class.md) 의 모양을 정의 하는 개체는 `array`합니다.

```
__declspec(property(get= get_extent)) Concurrency::extent<_Rank> extent;
```

##  <a name="get_accelerator_view"></a> get_accelerator_view

반환 합니다 [accelerator_view](accelerator-view-class.md) 위치를 나타내는 개체 위치를 `array` 개체가 할당 되 합니다. 이 속성은 CPU 에서만 액세스할 수 있습니다.

```
Concurrency::accelerator_view get_accelerator_view() const;
```

### <a name="return-value"></a>반환 값

합니다 `accelerator_view` 위치를 나타내는 개체 위치를 `array` 개체가 할당 되 합니다.

##  <a name="get_associated_accelerator_view"></a> get_associated_accelerator_view

두 번째 가져옵니다 [accelerator_view](accelerator-view-class.md) 인스턴스화하는 스테이징 생성자를 호출할 때 매개 변수로 전달 되는 개체는 `array` 개체입니다.

```
Concurrency::accelerator_view get_associated_accelerator_view() const ;
```

### <a name="return-value"></a>반환 값

두 번째 [accelerator_view](accelerator-view-class.md) 스테이징 생성자에 전달 된 개체입니다.

##  <a name="get_cpu_access_type"></a> get_cpu_access_type

이 배열에 허용 되는 CPU access_type을 반환 합니다.

```
access_type get_cpu_access_type() const restrict(cpu);
```

### <a name="return-value"></a>반환 값

##  <a name="get_extent"></a> get_extent

반환 합니다 [익스텐트](extent-class.md) 의 개체는 `array`합니다.

```
Concurrency::extent<_Rank> get_extent() const restrict(amp,cpu);
```

### <a name="return-value"></a>반환 값

합니다 `extent` 의 개체는 `array`합니다.

##  <a name="operator_vec"></a> operator std::vector&lt;value_type&gt;

사용 하 여 `copy(*this, vector)` 배열 std:: vector 개체를 암시적으로 변환할 합니다.

```
operator std::vector<value_type>() const restrict(cpu);
```

### <a name="parameters"></a>매개 변수

*value_type*<br/>
벡터 요소의 데이터 형식입니다.

### <a name="return-value"></a>반환 값

형식의 개체 `vector<T>` 배열에 포함 된 데이터의 복사본이 포함 된 합니다.

##  <a name="operator_call"></a> operator()

매개 변수로 지정 된 요소 값을 반환 합니다.

```
value_type& operator() (const index<_Rank>& _Index) restrict(amp,cpu);

const value_type& operator() (const index<_Rank>& _Index) cons  t restrict(amp,cpu);

value_type& operator() (int _I0, int _I1) restrict(amp,cpu);

const value_type& operator() (int _I0, int _I1) const restrict(amp,cpu)  ;

value_type& operator() (int _I0, int _I1, int _I2) restrict(amp,cpu);

const value_type& operator() (int _I0, int _I1, int _I2) const restrict(amp,cpu);

typename details::_Projection_result_type<value_type,_Rank>::_Result_type operator()(int _I) restrict(amp,cpu);

typename details::_Projection_result_type<value_type,_Rank>::_Const_result_type operator()(int _I) const restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Index*<br/>
요소의 위치입니다.

*_I0*<br/>
이 단원의 원본의의 가장 중요 한 구성 요소입니다.

*_I1*<br/>
이 섹션의 원점을 다음-에-가장 중요 한 구성 요소입니다.

*_I2*<br/>
이 단원의 원본의의 가장 중요 하지 않은 구성 요소입니다.

*_I*<br/>
요소의 위치입니다.

### <a name="return-value"></a>반환 값

매개 변수로 지정 된 요소 값입니다.

##  <a name="operator_at"></a> operator[]

지정된 된 인덱스에 있는 요소를 반환 합니다.

```
value_type& operator[](const index<_Rank>& _Index) restrict(amp,cpu);

const value_type& operator[]
    (const index<_Rank>& _Index) const restrict(amp,cpu);

typename details::_Projection_result_type<value_type,_Rank>::_Result_type operator[](int _i) restrict(amp,cpu);

typename details::_Projection_result_type<value_type,_Rank>::_Const_result_type operator[](int _i) const restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Index*<br/>
인덱스입니다.

*_I*<br/>
인덱스입니다.

### <a name="return-value"></a>반환 값

지정된 된 인덱스에 있는 요소입니다.

##  <a name="operator_eq"></a> operator=

지정 된 내용을 복사 `array` 개체입니다.

```
array& operator= (const array& _Other) restrict(cpu);

array& operator= (array&& _Other) restrict(cpu);

array& operator= (
    const array_view<const value_type, _Rank>& _Src) restrict(cpu);
```

### <a name="parameters"></a>매개 변수

*_Other*<br/>
`array` 복사할 개체입니다.

*_Src*<br/>
`array` 복사할 개체입니다.

### <a name="return-value"></a>반환 값

이에 대 한 참조 `array` 개체입니다.

##  <a name="rank"></a> 순위

차수를 저장 합니다 `array`합니다.

```
static const int rank = _Rank;
```

## <a name="reinterpret_as"></a> reinterpret_as

필요에 따라 소스 배열과 다른 값 형식을 가질 수 있는 1 차원 배열을 통해 배열을 다시 해석 합니다.

### <a name="syntax"></a>구문

```
template <typename _Value_type2>
array_view<_Value_type2,1> reinterpret_as() restrict(amp,cpu);

template <typename _Value_type2>
array_view<const _Value_type2, 1> reinterpret_as() const restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Value_type2*<br/>
반환된 된 데이터의 데이터 형식입니다.

### <a name="return-value"></a>반환 값

Array_view 또는 T에서 ElementType을 1로 감소 n에서 순위 재해석 요소 형식이 배열 기반으로 하는 const array_view 개체입니다.

### <a name="remarks"></a>설명

때때로 다차원 배열을 소스 배열과 다른 값 형식을 사용 하 여 수 있는 선형의 1 차원 배열에는 것 처럼 보려는 것이 유용 합니다. 이렇게 하려면이 메서드를 사용할 수 있습니다.
**주의** 안전 하지 않은 작업이 다른 값 형식을 사용 하 여 배열 개체를 재해석 합니다. 이 기능을 신중 하 게 사용 하는 것이 좋습니다.

코드 예제는 다음과 같습니다.

```cpp
struct RGB { float r; float g; float b; };

array<RGB,3>  a = ...;
array_view<float,1> v = a.reinterpret_as<float>();

assert(v.extent == 3*a.extent);
```

##  <a name="section"></a> 섹션

하위 단원을 반환 합니다 `array` 에 지정 된 origin을 있고, 선택적으로 하는 개체에 지정된 된 범위입니다.

```
array_view<value_type,_Rank> section(
    const Concurrency::index<_Rank>& _Section_origin,
    const Concurrency::extent<_Rank>& _Section_extent) restrict(amp,cpu);

array_view<const value_type,_Rank> section(
    const Concurrency::index<_Rank>& _Section_origin,
    const Concurrency::extent<_Rank>& _Section_extent) const restrict(amp,cpu);

array_view<value_type,_Rank> section(
    const Concurrency::extent<_Rank>& _Ext) restrict(amp,cpu);

array_view<const value_type,_Rank> section(
    const Concurrency::extent<_Rank>& _Ext) const restrict(amp,cpu);

array_view<value_type,_Rank> section(
    const index<_Rank>& _Idx) restrict(amp,cpu);

array_view<const value_type,_Rank> section(
    const index<_Rank>& _Idx) const restrict(amp,cpu);

array_view<value_type,1> section(
    int _I0,
    int _E0) restrict(amp,cpu);

array_view<const value_type,1> section(
    int _I0,
    int _E0) const restrict(amp,cpu);

array_view<value_type,2> section(
    int _I0,
    int _I1,
    int _E0,
    int _E1) restrict(amp,cpu);

array_view<const value_type,2> section(
    int _I0,
    int _I1,
    int _E0,
    int _E1) const restrict(amp,cpu);

array_view<value_type,3> section(
    int _I0,
    int _I1,
    int _I2,
    int _E0,
    int _E1,
    int _E2) restrict(amp,cpu);

array_view<const value_type,3> section(
    int _I0,
    int _I1,
    int _I2,
    int _E0,
    int _E1,
    int _E2) const restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_E0*<br/>
이 섹션의 범위의 가장 중요 한 구성 요소입니다.

*_E1*<br/>
이 섹션의 범위는 다음-에-가장 중요 한 구성 요소입니다.

*_E2*<br/>
이 섹션의 범위의 가장 중요 하지 않은 구성 요소입니다.

*_Ext*<br/>
합니다 [익스텐트](extent-class.md) 섹션의 범위를 지정 하는 개체입니다. 원래 값은 0입니다.

*_Idx*<br/>
합니다 [인덱스](index-class.md) 출처의 위치를 지정 하는 개체입니다. 하위 섹션에는 범위의 나머지입니다.

*_I0*<br/>
이 단원의 원본의의 가장 중요 한 구성 요소입니다.

*_I1*<br/>
이 섹션의 원점을 다음-에-가장 중요 한 구성 요소입니다.

*_I2*<br/>
이 단원의 원본의의 가장 중요 하지 않은 구성 요소입니다.

*_Rank*<br/>
섹션의 순위입니다.

*_Section_extent*<br/>
합니다 [익스텐트](extent-class.md) 섹션의 범위를 지정 하는 개체입니다.

*_Section_origin*<br/>
합니다 [인덱스](index-class.md) 출처의 위치를 지정 하는 개체입니다.

*value_type*<br/>
복사 된 요소의 데이터 형식입니다.

### <a name="return-value"></a>반환 값

하위 단원을 반환 합니다 `array` 에 지정 된 origin을 있고, 선택적으로 하는 개체에 지정된 된 범위입니다. 개체만 합니다 `index` 지정 된 경우 요소에 대 한 인덱스 보다 큰 인덱스가 있는 관련된 된 모눈의 모든 요소를 포함 하는 하위 섹션을 `index` 개체.

##  <a name="view_as"></a> view_as

이 배열을 재해석를 [array_view](array-view-class.md) 다른 순위의 합니다.

```
template <int _New_rank>
array_view<value_type,_New_rank> view_as(
    const Concurrency::extent<_New_rank>& _View_extent) restrict(amp,cpu);

template <int _New_rank>
array_view<const value_type,_New_rank> view_as(
    const Concurrency::extent<_New_rank>& _View_extent) const restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_New_rank*<br/>
순위를 `extent` 개체를 매개 변수로 전달 합니다.

*_View_extent*<br/>
새 생성 하는 데 사용 되는 정도 [array_view](array-view-class.md) 개체입니다.

*value_type*<br/>
두 원본에 있는 요소의 데이터 형식 `array` 개체 및 반환 된 `array_view` 개체입니다.

### <a name="return-value"></a>반환 값

합니다 [array_view](array-view-class.md) 생성 된 개체입니다.

## <a name="see-also"></a>참고자료

[Concurrency 네임스페이스(C++ AMP)](concurrency-namespace-cpp-amp.md)
