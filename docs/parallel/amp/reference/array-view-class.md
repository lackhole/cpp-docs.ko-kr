---
title: array_view 클래스
ms.date: 11/04/2016
f1_keywords:
- array_view
- AMP/array_view
- AMP/Concurrency::array_view::array_view
- AMP/Concurrency::array_view::copy_to
- AMP/Concurrency::array_view::data
- AMP/Concurrency::array_view::discard_data
- AMP/Concurrency::array_view::get_extent
- AMP/Concurrency::array_view::get_ref
- AMP/Concurrency::array_view::get_source_accelerator_view
- AMP/Concurrency::array_view::refresh
- AMP/Concurrency::array_view::reinterpret_as
- AMP/Concurrency::array_view::section
- AMP/Concurrency::array_view::synchronize
- AMP/Concurrency::array_view::synchronize_async
- AMP/Concurrency::array_view::synchronize_to
- AMP/Concurrency::array_view::synchronize_to_async
- AMP/Concurrency::array_view::view_as
- AMP/Concurrency::array_view::rank
- AMP/Concurrency::array_view::extent
- AMP/Concurrency::array_view::source_accelerator_view
- AMP/Concurrency::array_view::value_type
helpviewer_keywords:
- array_view class
ms.assetid: 7e7ec9bc-05a2-4372-b05d-752b50006c5a
ms.openlocfilehash: e73639ffd11e08edb2fdb03471f2c6c88730f02d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405562"
---
# <a name="arrayview-class"></a>array_view 클래스

다른 컨테이너에 저장 된 데이터에 대 한 N 차원 뷰를 나타냅니다.

## <a name="syntax"></a>구문

```
template <
    typename value_type,
    int _Rank = 1
>
class array_view : public _Array_view_base<_Rank, sizeof(value_type)/sizeof(int)>;

template <
    typename value_type,
    int _Rank
>
class array_view<const value_type, _Rank> : public _Array_view_base<_Rank, sizeof(value_type)/sizeof(int)>;
```

#### <a name="parameters"></a>매개 변수

*value_type*<br/>
데이터 형식의 요소에는 `array_view` 개체입니다.

*_Rank*<br/>
순위를 `array_view` 개체입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[array_view 생성자](#ctor)|`array_view` 클래스의 새 인스턴스를 초기화합니다. 에 대 한 기본 생성자가 없는 `array<T,N>`합니다. 모든 생성자는 cpu 에서만 실행 되도록 제한 되며 Direct3D 대상에서 실행할 수 없습니다.|
|[~ array_view 소멸자](#ctor)|제거 된 `array_view` 개체입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[copy_to](#copy_to)|내용을 복사 합니다 `array_view` 개체를 호출 하 여 지정 된 대상 `copy(*this, dest)`합니다.|
|[data](#data)|원시 데이터에 대 한 포인터를 반환 합니다 `array_view`합니다.|
|[discard_data](#discard_data)|이 뷰 내부의 현재 데이터를 삭제 합니다.|
|[get_extent](#get_extent)|Array_view 개체의 범위 개체를 반환합니다.|
|[get_ref](#get_ref)|인덱싱된 요소에 대 한 참조를 반환합니다.|
|[get_source_accelerator_view](#get_source_accelerator_view)|반환 합니다 [accelerator_view](accelerator-view-class.md) 여기서의 데이터 소스는 `array_view` 위치한 합니다.|
|[refresh](#refresh)|알립니다 합니다 `array_view` 외부에서 수정 되었으며의 바운드 메모리는 개체는 `array_view` 인터페이스입니다. 이 메서드를 호출 오래 된 모든 캐시 된 정보를 렌더링합니다.|
|[reinterpret_as](#reinterpret_as)|모든 요소를 포함 하는 1 차원 배열을 반환 합니다 `array_view` 개체입니다.|
|[section](#section)|하위 단원을 반환 합니다 `array_view` 에 지정 된 origin을 있고, 선택적으로 하는 개체에 지정된 된 범위입니다.|
|[synchronize](#synchronize)|에 만들어진 모든 수정을 동기화는 `array_view` 해당 원본 데이터 개체입니다.|
|[synchronize_async](#synchronize_async)|에 대 한 모든 수정을 비동기적으로 동기화 된 `array_view` 해당 원본 데이터 개체입니다.|
|[synchronize_to](#synchronize_to)|에 만들어진 모든 수정을 동기화 합니다 `array_view` 지정 된 개체 [accelerator_view](accelerator-view-class.md)합니다.|
|[synchronize_to_async](#synchronize_to_async)|에 대 한 모든 수정을 비동기적으로 동기화 합니다 `array_view` 지정 된 개체 [accelerator_view](accelerator-view-class.md)합니다.|
|[view_as](#view_as)|생성 된 `array_view` 이 사용 하 여 다른 순위의 개체 `array_view` 개체의 데이터입니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[operator()](#operator_call)|매개 변수 또는 매개 변수에서 지정 된 요소의 값을 반환 합니다.|
|[operator\[\]](#operator_at)|매개 변수로 지정 된 요소를 반환 합니다.|
|[operator=](#operator_eq)|지정 된 내용을 복사 `array_view` 을 여기에 개체입니다.|

### <a name="public-constants"></a>공용 상수

|이름|설명|
|----------|-----------------|
|[rank 상수](#rank)|차수를 저장 합니다 `array_view` 개체입니다.|

### <a name="data-members"></a>데이터 멤버

|이름|설명|
|----------|-----------------|
|[extent](#extent)|`extent` 개체의 모양을 정의하는 `array_view` 개체를 가져옵니다.|
|[source_accelerator_view](#source_accelerator_view)|가져옵니다 합니다 [accelerator_view](accelerator-view-class.md) 여기서의 데이터 소스는 `array_view` 위치한|
|[value_type](#value_type)|값 형식의 `array_view` 및 바인딩된 배열의 합니다.|

## <a name="remarks"></a>설명

`array_view` 클래스에 포함 된 데이터에 대 한 보기를 나타냅니다는 [배열](array-class.md) 개체나의 하위 섹션을 `array` 개체입니다.

액세스할 수는 `array_view` 있는 원본 데이터 (로컬) 또는 다른 가속기 나 일관성 도메인에 개체 (원격). 개체를 원격으로 액세스 하는 경우 뷰 복사 되어 필요에 따라 캐시 됩니다. 자동 캐싱의 효과 제외 하 고 `array_view` 개체에는 비슷한 성능 프로필을 `array` 개체입니다. 뷰를 통해 데이터에 액세스할 때 성능이 약간 저하가 있습니다.

세 가지 원격 사용 시나리오가 있습니다.

- 시스템 메모리 포인터에 대 한 뷰를 통해 전달 되는 [parallel_for_each](../../../parallel/concrt/reference/concurrency-namespace-functions.md#parallel_for_each) 액셀러레이터를 호출 하 고 가속기에서 액세스 합니다.

- 액셀러레이터 키에 위치한 배열에 뷰를 통해 전달 되는 `parallel_for_each` 다른 가속기를 호출 하 고 액세스 됩니다.

- Cpu 액셀러레이터에 위치한 배열에 뷰를 액세스 합니다.

이러한 시나리오 중 하나로, 참조 된 뷰를 복사할 런타임에서 원격 위치에 대 한 호출에 의해 수정 하는 경우는 `array_view` 개체, 로컬 위치로 다시 복사 됩니다. 런타임 변경 내용 복사 프로세스를 최적화할 수 있으며, 변경 된 요소만 복사 될 수 있습니다 또는 변경 되지 않은 부분도 복사할 수 있습니다. 겹치는 `array_view` 하나의 데이터 원본 개체는 원격 위치에서 참조 무결성을 유지 보장 되지 않습니다.

동일한 데이터 원본에 대 한 다중 스레드 액세스를 동기화 해야 합니다.

런타임에 데이터의 캐시에 대 한 다음과 같은 보장 `array_view` 개체:

- 모든 적절히 동기화 된 액세스는 `array` 개체 및 `array_view` 프로그램 순서로 개체에 대해 준수 직렬 발생-전 관계입니다.

- 겹치는 모든 적절히 동기화 된 액세스 `array_view` 단일 같은 가속기 개체 `array` 개체를 통해 별칭을 지정 하는 `array` 개체입니다. 총 유도 발생-전 프로그램 순서를 따르는 관계입니다. 캐싱이 없습니다. 경우는 `array_view` 다른 액셀러레이터에서 실행 하는 개체, 액세스 순서는 정의 경쟁 조건이 생성 되지 않습니다.

만들 때를 `array_view` 시스템 메모리에 대 한 포인터를 사용 하 여 뷰를 변경 해야 `array_view` 통해서만 개체는 `array_view` 포인터입니다. 또는 호출 해야 합니다 `refresh()` 중 하나에 `array_view` 기본 네이티브 메모리가 통하지 않고 직접 변경 된 경우 시스템 포인터에 연결 된 개체는 `array_view` 개체입니다.

두 동작 모두에 게 알리는 `array_view` 기본 네이티브 메모리가 변경 되었음을 액셀러레이터에 있는 모든 복사본은 오래 된는 개체입니다. 다음이 지침을 따르는 경우 포인터 기반 보기는 데이터 병렬 배열의 보기에 제공 된 동일 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`_Array_view_shape`

`_Array_view_base`

`array_view`

## <a name="requirements"></a>요구 사항

**헤더:** amp.h

**네임스페이스:** 동시성

##  <a name="dtor"></a> ~array_view

제거 된 `array_view` 개체입니다.

```
~array_view()restrict(amp,cpu);
```

##  <a name="ctor"></a> array_view

`array_view` 클래스의 새 인스턴스를 초기화합니다.

```
array_view(
    array<value_type, _Rank>& _Src)restrict(amp,cpu);

array_view(
    const array_view& _Other)restrict(amp,cpu);

explicit array_view(
    const Concurrency::extent<_Rank>& _Extent) restrict(cpu);

template <
    typename _Container
>
array_view(
    const Concurrency::extent<_Rank>& _Extent,
    _Container& _Src) restrict(cpu);

array_view(
    const Concurrency::extent<_Rank>& _Extent,
    value_type* _Src)restrict(amp,cpu);

explicit array_view(
    int _E0) restrict(cpu);

template <
    typename _Container
>
explicit array_view(
    _Container& _Src,
    typename std::enable_if<details::_Is_container<_Container>::type::value, void **>::type = 0) restrict(cpu);

template <
    typename _Container
>
explicit array_view(
    int _E0,
    _Container& _Src) restrict(cpu);

explicit array_view(
    int _E0,
    int _E1) __CPU_ONLY;

template <
    typename _Container
>
explicit array_view(
    int _E0,
    int _E1,
    _Container& _Src) restrict(cpu);

explicit array_view(
    int _E0,
    int _E1,
    int _E2) __CPU_ONLY;

template <
    typename _Container
>
explicit array_view(
    int _E0,
    int _E1,
    int _E2,
    _Container& _Src);

explicit array_view(
    int _E0,
    _In_ value_type* _Src)restrict(amp,cpu);

template <
    typename _Arr_type,
    int _Size
>
explicit array_view(
    _In_ _Arr_type (& _Src) [_Size]) restrict(amp,cpu);

explicit array_view(
    int _E0,
    int _E1,
    _In_ value_type* _Src)restrict(amp,cpu);

explicit array_view(
    int _E0,
    int _E1,
    int _E2,
    _In_ value_type* _Src)restrict(amp,cpu);

array_view(
    const array<value_type, _Rank>& _Src)restrict(amp,cpu);

array_view(
    const array_view<value_type, _Rank>& _Src)restrict(amp,cpu);

array_view(
    const array_view<const value_type, _Rank>& _Src)restrict(amp,cpu);

template <
    typename _Container
>
array_view(
    const Concurrency::extent<_Rank>& _Extent,
    const _Container& _Src) restrict(cpu);

template <
    typename _Container
>
explicit array_view(
    const _Container& _Src,
    typename std::enable_if<details::_Is_container<_Container>::type::value, void **>::type = 0) restrict(cpu);

array_view(
    const Concurrency::extent<_Rank>& _Extent,
    const value_type* _Src)restrict(amp,cpu);

template <
    typename _Arr_type,
    int _Size
>
explicit array_view(
    const _In_ _Arr_type (& _Src) [_Size]) restrict(amp,cpu);

template <
    typename _Container
>
array_view(
    int _E0,
    const _Container& _Src);

template <
    typename _Container
>
array_view(
    int _E0,
    int _E1,
    const _Container& _Src);

template <
    typename _Container
>
array_view(
    int _E0,
    int _E1,
    int _E2,
    const _Container& _Src);

array_view(
    int _E0,
    const value_type* _Src)restrict(amp,cpu);

array_view(
    int _E0,
    int _E1,
    const value_type* _Src) restrict(amp,cpu);

array_view(
    int _E0,
    int _E1,
    int _E2,
    const value_type* _Src) restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Arr_type*<br/>
데이터가 제공 되는 C 스타일 배열의 요소 형식입니다.

*_Container*<br/>
지 원하는 선형 컨테이너를 지정 해야 하는 템플릿 인수 `data()` 및 `size()` 멤버입니다.

*_E0*<br/>
이 섹션의 범위의 가장 중요 한 구성 요소입니다.

*_E1*<br/>
이 섹션의 범위는 다음-에-가장 중요 한 구성 요소입니다.

*_E2*<br/>
이 섹션의 범위의 가장 중요 하지 않은 구성 요소입니다.

*_Extent*<br/>
이 각 차원의 범위 `array_view`합니다.

*_Other*<br/>
형식의 개체 `array_view<T,N>` 새 초기화 하는 `array_view`합니다.

*_Size*<br/>
데이터가 제공 되는 C 스타일 배열의 크기입니다.

*_Src*<br/>
새 배열에 복사 될 원본 데이터에 대 한 포인터입니다.

##  <a name="copy_to"></a> copy_to

내용을 복사 합니다 `array_view` 개체를 호출 하 여 지정 된 대상 개체 `copy(*this, dest)`합니다.

```
void copy_to(
    array<value_type, _Rank>& _Dest) const;

void copy_to(
    array_view<value_type, _Rank>& _Dest) const;
```

### <a name="parameters"></a>매개 변수

*_Dest*<br/>
복사할 개체입니다.

##  <a name="data"></a> 데이터

원시 데이터에 대 한 포인터를 반환 합니다 `array_view`합니다.

```
value_type* data() const restrict(amp,
    cpu);

const value_type* data() const restrict(amp,
    cpu);
```

### <a name="return-value"></a>반환 값

`array_view`의 원시 데이터에 대한 포인터입니다.

##  <a name="discard_data"></a> discard_data

이 뷰 내부의 현재 데이터를 삭제 합니다. 이 대상 뷰의 현재 콘텐츠를 복사 하지 않으려면에 사용 된 런타임 최적화 힌트 `accelerator_view` 에 액세스 하는 것을 기존 콘텐츠가 필요 하지 않은 경우 해당 사용을 권장 합니다. 이 메서드는 restrict (amp) 컨텍스트에서 사용할 경우 no-op

```
void discard_data() const restrict(cpu);
```

##  <a name="extent"></a> 범위

`extent` 개체의 모양을 정의하는 `array_view` 개체를 가져옵니다.

```
__declspec(property(get= get_extent)) Concurrency::extent<_Rank> extent;
```

##  <a name="get_extent"></a> get_extent

반환 합니다 [익스텐트](extent-class.md) 의 개체는 `array_view` 개체입니다.

```
Concurrency::extent<_Rank> get_extent() const restrict(cpu, amp);
```

### <a name="return-value"></a>반환 값

`extent` 개체의 `array_view` 개체입니다.

##  <a name="get_ref"></a> get_ref

_Index로 인덱싱된 요소에 대 한 참조를 가져옵니다. 위한 기타 인덱싱 연산자 CPU의 array_view 액세스, 달리이 메서드 동기화 되지 않습니다 암시적으로 cpu이 array_view의이 콘텐츠입니다. 원격 위치에서 array_view에 액세스 하거나이 array_view를 포함 하는 복사 작업 수행 후 사용자는이 메서드를 호출 하기 전에 array_view를 CPU에 명시적으로 동기화 해야 합니다. 이렇게 하지 않으면 정의 되지 않은 동작이 발생 합니다.

```
value_type& get_ref(
    const index<_Rank>& _Index) const restrict(amp, cpu);
```

### <a name="parameters"></a>매개 변수

*_Index*<br/>
인덱스입니다.

### <a name="return-value"></a>반환 값

_Index로 인덱싱된 요소에 대 한 참조

##  <a name="get_source_accelerator_view"></a> get_source_accelerator_view

Array_view의 데이터 소스가 위치한 accelerator_view를 반환 합니다. 이 API는 runtime_exception을 throw array_view에 데이터 원본을 찾을 수 없는 경우

```
accelerator_view get_source_accelerator_view() const;
```

### <a name="return-value"></a>반환 값

##  <a name="operator_call"></a> operator()

매개 변수 또는 매개 변수에서 지정 된 요소의 값을 반환 합니다.

```
value_type& operator() (
    const index<_Rank>& _Index) const restrict(amp,cpu);

typename details::_Projection_result_type<value_type,_Rank>::_Result_type operator() (
    int _I) const restrict(amp,cpu);

value_type& operator() (
    int _I0,
    int _I1) const restrict(amp,cpu);

value_type& operator() (
    int _I0,
    int _I1,
    int _I2) const restrict(amp,cpu);

typename details::_Projection_result_type<value_type,_Rank>::_Const_result_type operator() (
    int _I) const restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Index*<br/>
요소의 위치입니다.

*_I0*<br/>
첫 번째 차원의 인덱스입니다.

*_I1*<br/>
두 번째 차원의 인덱스입니다.

*_I2*<br/>
세 번째 차원의 인덱스입니다.

*_I*<br/>
요소의 위치입니다.

### <a name="return-value"></a>반환 값

매개 변수 또는 매개 변수에서 지정 된 요소의 값입니다.

##  <a name="operator_at"></a> operator[]

매개 변수로 지정 된 요소를 반환 합니다.

```
typename details::_Projection_result_type<value_type,_Rank>::_Const_result_type operator[] (
    int _I) const restrict(amp,cpu);

value_type& operator[] (
    const index<_Rank>& _Index) const restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Index*<br/>
인덱스입니다.

*_I*<br/>
인덱스입니다.

### <a name="return-value"></a>반환 값

인덱스에 있는 요소의 값 또는 `array_view` 가장 중요 한 차원에 투영 합니다.

##  <a name="operator_eq"></a> operator=

지정 된 내용을 복사 `array_view` 여기에 개체입니다.

```
array_view& operator= (
    const array_view& _Other) restrict(amp,cpu);

array_view& operator= (
    const array_view<value_type, _Rank>& _Other) restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Other*<br/>
`array_view` 복사할 개체입니다.

### <a name="return-value"></a>반환 값

이에 대 한 참조 `array_view` 개체입니다.

##  <a name="rank"></a> 순위

차수를 저장 합니다 `array_view` 개체입니다.

```
static const int rank = _Rank;
```

##  <a name="refresh"></a> 새로 고침

알립니다 합니다 `array_view` 외부에서 수정 되었으며의 바운드 메모리는 개체는 `array_view` 인터페이스입니다. 이 메서드를 호출 오래 된 모든 캐시 된 정보를 렌더링합니다.

```
void refresh() const restrict(cpu);
```

## <a name="reinterpret_as"></a> reinterpret_as

옵션으로 소스 배열 보기 보다는 다른 값 형식을 가질 수는 1 차원 배열 통해 array_view를 재해석 합니다.

### <a name="syntax"></a>구문

```
template <
    typename _Value_type2
>
array_view< _Value_type2, _Rank> reinterpret_as() const restrict(amp,cpu);

template <
    typename _Value_type2
>
array_view<const _Value_type2, _Rank> reinterpret_as() const restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Value_type2*<br/>
데이터 형식의 새 `array_view` 개체입니다.

### <a name="return-value"></a>반환 값

`array_view` 개체 또는 const `array_view` 이 기반으로 하는 개체 `array_view`에서 변환 된 요소 형식이 `T` 에 `_Value_type2`, 순위에서 줄이고 *N* 1로.

### <a name="remarks"></a>설명

때때로 다차원 배열을 소스 배열과 다른 값 형식을 가질 수 있는 선형의 1 차원 배열에 보려면는 것이 유용 합니다. 이렇게 할 수는 `array_view` 이 메서드를 사용 하 여 합니다.

**경고** Reinterpeting array_view 개체가 다른 값 형식을 사용 하 여 잠재적으로 안전 하지 않은 작업입니다. 이 기능은 주의 해 서 사용 해야 합니다.

예를 들면 다음과 같습니다.

```cpp
struct RGB { float r; float g; float b; };

array<RGB,3>  a = ...;
array_view<float,1> v = a.reinterpret_as<float>();

assert(v.extent == 3*a.extent);
```

##  <a name="section"></a> 섹션

하위 단원을 반환 합니다 `array_view` 에 지정 된 origin을 있고, 선택적으로 하는 개체에 지정된 된 범위입니다.

```
array_view section(
    const Concurrency::index<_Rank>& _Section_origin,
    const Concurrency::extent<_Rank>& _Section_extent) const restrict(amp,cpu);

array_view section(
    const Concurrency::index<_Rank>& _Idx) const restrict(amp,cpu);

array_view section(
    const Concurrency::extent<_Rank>& _Ext) const restrict(amp,cpu);

array_view section(
    int _I0,
    int _E0) const restrict(amp,cpu);

array_view section(
    int _I0,
    int _I1,
    int _E0,
    int _E1) const restrict(amp,cpu);

array_view section(
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

### <a name="return-value"></a>반환 값

하위 섹션은 `array_view` 에 지정 된 origin을 있고, 선택적으로 하는 개체에 지정된 된 범위입니다. 개체만 합니다 `index` 개체가 지정 된 경우 요소에 대 한 인덱스 보다 큰 인덱스가 있는 관련 된 범위의 모든 요소를 포함 하는 하위 섹션을 `index` 개체.

##  <a name="source_accelerator_view"></a> source_accelerator_view

이 array_view가 연결 된 소스 accelerator_view를 가져옵니다.

```
__declspec(property(get= get_source_accelerator_view)) accelerator_view source_accelerator_view;
```

##  <a name="synchronize"></a> 동기화

에 만들어진 모든 수정을 동기화는 `array_view` 해당 원본 데이터 개체입니다.

```
void synchronize(access_type _Access_type = access_type_read) const restrict(cpu);

void synchronize() const restrict(cpu);
```

### <a name="parameters"></a>매개 변수

*_Access_type*<br/>
원하는 [access_type](concurrency-namespace-enums-amp.md#access_type) 대상 [accelerator_view](accelerator-view-class.md)합니다. 이 매개 변수는 기본값은 `access_type_read`합니다.

##  <a name="synchronize_async"></a> synchronize_async

에 대 한 모든 수정을 비동기적으로 동기화 된 `array_view` 해당 원본 데이터 개체입니다.

```
concurrency::completion_future synchronize_async(access_type _Access_type = access_type_read) const restrict(cpu);

concurrency::completion_future synchronize_async() const restrict(cpu);
```

### <a name="parameters"></a>매개 변수

*_Access_type*<br/>
원하는 [access_type](concurrency-namespace-enums-amp.md#access_type) 대상 [accelerator_view](accelerator-view-class.md)합니다. 이 매개 변수는 기본값은 `access_type_read`합니다.

### <a name="return-value"></a>반환 값

작업이 완료 되기를 대기 하는 미래입니다.

##  <a name="synchronize_to"></a> synchronize_to

지정된 된 accelerator_view에이 array_view에 만들어진 모든 수정을 동기화 합니다.

```
void synchronize_to(
    const accelerator_view& _Accl_view,
    access_type _Access_type = access_type_read) const restrict(cpu);

void synchronize_to(
    const accelerator_view& _Accl_view) const restrict(cpu);
```

### <a name="parameters"></a>매개 변수

*_Accl_view*<br/>
동기화 할 대상 accelerator_view입니다.

*_Access_type*<br/>
대상 accelerator_view에서 원하는 액세스 형식입니다. 이 매개 변수는 기본값은 access_type_read입니다.

##  <a name="synchronize_to_async"></a> synchronize_to_async

지정된 된 accelerator_view에이 array_view에 만들어진 모든 수정을 비동기적으로 동기화 합니다.

```
concurrency::completion_future synchronize_to_async(
    const accelerator_view& _Accl_view,
    access_type _Access_type = access_type_read) const restrict(cpu);

concurrency::completion_future synchronize_to_async(
    const accelerator_view& _Accl_view) const restrict(cpu);
```

### <a name="parameters"></a>매개 변수

*_Accl_view*<br/>
동기화 할 대상 accelerator_view입니다.

*_Access_type*<br/>
대상 accelerator_view에서 원하는 액세스 형식입니다. 이 매개 변수는 기본값은 access_type_read입니다.

### <a name="return-value"></a>반환 값

작업이 완료 되기를 대기 하는 미래입니다.

##  <a name="value_type"></a> value_type

Array_view 및 바인딩된 배열의 값 형식입니다.

```
typedef typenamevalue_type value_type;
```

##  <a name="view_as"></a> view_as

이 재해석 `array_view` 으로 `array_view` 다른 순위의 합니다.

```
template <
    int _New_rank
>
array_view<value_type,_New_rank> view_as(
    const Concurrency::extent<_New_rank>& _View_extent) const restrict(amp,cpu);

template <
    int _New_rank
>
array_view<const value_type,_New_rank> view_as(
    const Concurrency::extent<_New_rank> _View_extent) const restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_New_rank*<br/>
새 순위 `array_view` 개체입니다.

*_View_extent*<br/>
모양 변경 `extent`합니다.

*value_type*<br/>
두 원본에 있는 요소의 데이터 형식 [배열](array-class.md) 개체 및 반환 된 `array_view` 개체입니다.

### <a name="return-value"></a>반환 값

`array_view` 생성 된 개체입니다.

## <a name="see-also"></a>참고자료

[Concurrency 네임스페이스(C++ AMP)](concurrency-namespace-cpp-amp.md)
