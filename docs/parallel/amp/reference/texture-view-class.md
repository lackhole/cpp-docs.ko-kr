---
title: texture_view 클래스
ms.date: 11/04/2016
f1_keywords:
- texture_view
- AMP_GRAPHICS/texture_view
- AMP_GRAPHICS/Concurrency::graphics::texture_view::texture_view
- AMP_GRAPHICS/Concurrency::graphics::texture_view::gather_alpha
- AMP_GRAPHICS/Concurrency::graphics::texture_view::gather_blue
- AMP_GRAPHICS/Concurrency::graphics::texture_view::gather_green
- AMP_GRAPHICS/Concurrency::graphics::texture_view::gather_red
- AMP_GRAPHICS/Concurrency::graphics::texture_view::get
- AMP_GRAPHICS/Concurrency::graphics::texture_view::sample
- AMP_GRAPHICS/Concurrency::graphics::texture_view::set
- AMP_GRAPHICS/Concurrency::graphics::texture_view::value_type
ms.assetid: 6ec2e289-1626-4727-9592-07981cf1d27d
ms.openlocfilehash: 0f2b627afa216f03592fe913afece1a80f5bd5a6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62351523"
---
# <a name="textureview-class"></a>texture_view 클래스

대 한 읽기 및 쓰기 액세스를 제공합니다. `texture_view` 값 형식의 질감을 읽을 수만 사용할 수 있습니다 `int`, `unsigned int`, 또는 `float` 기본 32 비트 bpse가 있습니다. 다른 질감 형식을 알아보려면를 사용 하 여 `texture_view<const value_type, _Rank>`입니다.

## <a name="syntax"></a>구문

```
template<typename value_type,int _Rank>
class texture_view;

template<typename value_type, int _Rank>
class texture_view
   : public details::_Texture_base<value_type, _Rank>;

template<typename value_type, int _Rank>
class texture_view<const value_type, _Rank>
   : public details::_Texture_base<value_type, _Rank>;
```

#### <a name="parameters"></a>매개 변수

*value_type*<br/>
질감 집계에 있는 요소의 형식입니다.

*_Rank*<br/>
순위는 `texture_view`합니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|이름|설명|
|----------|-----------------|
|`value_type`|질감 집계에 있는 요소의 형식입니다.|
|`coordinates_type`|텍셀을 지정 하는 데 사용 된 좌표 형식 합니다 `texture_view`-즉,는 `short_vector` 의 값 형식을 갖는 연결 된 질감으로 같은 순위를 가지는 `float`합니다.|
|`gather_return_type`|수집 작업에 사용 되는 반환 형식-4 차원, `short_vector` 는 4 개의 동종 색상 구성 요소 포함 샘플링 하는 4 가지 텍셀 값에서 수집 되는 것입니다.|

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[texture_view 생성자](#ctor)|오버로드됨. 생성 된 `texture_view` 인스턴스.|
|[~ texture_view 소멸자](#ctor)|제거 된 `texture_view` 인스턴스.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[gather_alpha](#gather_alpha)|오버로드됨. 지정된 된 샘플링 구성을 사용 하 여 지정된 된 좌표에 질감을 샘플링 하 고 4 개의 샘플링 된 텍셀의 알파 (w) 구성 요소를 반환 합니다.|
|[gather_blue](#gather_blue)|오버로드됨. 지정된 된 샘플링 구성을 사용 하 여 지정된 된 좌표에 질감을 샘플링 하 고 4 개의 샘플링 된 텍셀의 파란색 (z) 구성 요소를 반환 합니다.|
|[gather_green](#gather_green)|오버로드됨. 지정된 된 샘플링 구성을 사용 하 여 지정된 된 좌표에 질감을 샘플링 하 고 4 개의 샘플링 된 텍셀의 녹색 (y) 구성 요소를 반환 합니다.|
|[gather_red](#gather_red)|오버로드됨. 지정된 된 샘플링 구성을 사용 하 여 지정된 된 좌표에 질감을 샘플링 하 고 4 개의 샘플링 된 텍셀의 빨간색 (x) 구성 요소를 반환 합니다.|
|[get](#get)|오버로드됨. 인덱스 별로 요소 값을 가져옵니다.|
|[sample](#sample)|오버로드됨. 지정된 된 샘플링 구성을 사용 하 여 세부 수준을 확인 하 고 지정 된 좌표에 질감을 샘플링 합니다.|
|[set](#set)|인덱스로 요소의 값을 설정합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[operator()](#operator_call)|오버로드됨. 인덱스 별로 요소 값을 가져옵니다.|
|[operator\[\]](#operator_at)|오버로드됨. 인덱스 별로 요소 값을 가져옵니다.|
|[operator=](#operator_eq)|오버로드됨. 대입 연산자입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[value_type](#value_type)|값 형식의 요소는 `texture_view`합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`_Texture_base`

`texture_view`

## <a name="requirements"></a>요구 사항

**헤더:** amp_graphics.h

**Namespace:** concurrency:: graphics

##  <a name="dtor"></a> ~texture_view

제거 된 `texture_view` 인스턴스.

```
~texture_view() restrict(amp, cpu);
```

##  <a name="ctor"></a> texture_view

생성 된 `texture_view` 인스턴스.

```
texture_view(// [1] constructor
    texture<value_type, _Rank>& _Src) restrict(amp);

texture_view(// [2] constructor
    texture<value_type, _Rank>& _Src,
    unsigned int _Mipmap_level = 0) restrict(cpu);

texture_view(// [3] constructor
    const texture<value_type, _Rank>& _Src) restrict(amp);

texture_view(// [4] constructor
    const texture<value_type, _Rank>& _Src,
    unsigned int _Most_detailed_mip,
    unsigned int _Mip_levels) restrict(cpu);

texture_view(// [5] copy constructor
    const texture_view<value_type, _Rank>& _Other) restrict(amp, cpu);

texture_view(// [6] copy constructor
    const texture_view<const value_type, _Rank>& _Other) restrict(amp, cpu);

texture_view(// [7] copy constructor
    const texture_view<const value_type, _Rank>& _Other,
    unsigned int _Most_detailed_mip,
    unsigned int _Mip_levels) restrict(cpu);
```

### <a name="parameters"></a>매개 변수

*_Src*<br/>
[1, 2] 생성자는 `texture` 는 쓰기 가능한 `texture_view` 만들어집니다.

[3, 4] 생성자는 `texture` 기반이 쓰기 불가능 `texture_view` 만들어집니다.

*_Other*<br/>
[5] 복사 생성자 쓰기 가능한 원본 `texture_view`합니다.

[6, 7] 복사 생성자 쓸 수 없는 소스 `texture_view`합니다.

*_Mipmap_level*<br/>
원본에서 특정 밉 맵 레벨 `texture` 는 쓰기 가능한 `texture_view` 에 바인딩합니다. 기본값은 최상위 (가장 자세한) 밉 수준을 나타내는 0입니다.

*_Most_detailed_mip*<br/>
지정 된 기준으로 보기에 대 한 수준 (가장 자세한) 밉 수준 상위 `texture_view` 개체입니다.

*_Mip_levels*<br/>
통해 액세스할 수 있는 mip 맵 수준 수를 `texture_view`입니다.

##  <a name="gather_red"></a> gather_red

지정된 된 샘플링 구성을 사용 하 여 지정된 된 좌표에 질감을 샘플링 하 고 4 개의 샘플링 된 텍셀의 빨간색 (x) 구성 요소를 반환 합니다.

```
const gather_return_type gather_red(
    const sampler& _Sampler,
    const coordinates_type& _Coord) const restrict(amp);

template<
    address_mode _Address_mode = address_clamp
>
const gather_return_type gather_red(
    const coordinates_type& _Coord) const restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_Address_mode*<br/>
사용 하는 주소 모드 샘플에는 `texture_view`합니다. 주소 모드가 모든 차원에 대해 동일 합니다.

*_Sampler*<br/>
사용 하는 샘플러 구성 샘플을 `texture_view`입니다.

*_Coord*<br/>
샘플을 취할 좌표입니다. 좌표 값은 샘플 텍스트 사이 보간 하는 데 사용 됩니다.

### <a name="return-value"></a>반환 값

4의 빨간색 (x) 구성 요소를 포함 하는 4 차원 짧은 벡터 텍셀 값을 샘플링 합니다.

##  <a name="gather_green"></a> gather_green

지정된 된 샘플링 구성을 사용 하 여 지정된 된 좌표에 질감을 샘플링 하 고 4 개의 샘플링 된 텍셀의 녹색 (y) 구성 요소를 반환 합니다.

```
const gather_return_type gather_green(
    const sampler& _Sampler,
    const coordinates_type& _Coord) const restrict(amp);

template<
    address_mode _Address_mode = address_clamp
>
const gather_return_type gather_green(
    const coordinates_type& _Coord) const restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_Address_mode*<br/>
사용 하는 주소 모드 샘플에는 `texture_view`합니다. 주소 모드가 모든 차원에 대해 동일 합니다.

*_Sampler*<br/>
사용 하는 샘플러 구성 샘플을 `texture_view`입니다.

*_Coord*<br/>
샘플을 취할 좌표입니다. 좌표 값은 샘플 텍스트 사이 보간 하는 데 사용 됩니다.

### <a name="return-value"></a>반환 값

4 녹색 (y) 구성 요소를 포함 하는 4 차원 짧은 벡터 텍셀 값을 샘플링 합니다.

##  <a name="gather_blue"></a> gather_blue

지정된 된 샘플링 구성을 사용 하 여 지정된 된 좌표에 질감을 샘플링 하 고 4 개의 샘플링 된 텍셀의 파란색 (z) 구성 요소를 반환 합니다.

```
const gather_return_type gather_blue(
    const sampler& _Sampler,
    const coordinates_type& _Coord) const restrict(amp);

template<
    address_mode _Address_mode = address_clamp
>
const gather_return_type gather_blue(
    const coordinates_type& _Coord) const restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_Address_mode*<br/>
사용 하는 주소 모드 샘플에는 `texture_view`합니다. 주소 모드가 모든 차원에 대해 동일 합니다.

*_Sampler*<br/>
사용 하는 샘플러 구성 샘플을 `texture_view`입니다.

*_Coord*<br/>
샘플을 취할 좌표입니다. 좌표 값은 샘플 텍스트 사이 보간 하는 데 사용 됩니다.

### <a name="return-value"></a>반환 값

4의 빨간색 (x) 구성 요소를 포함 하는 4 차원 짧은 벡터 텍셀 값을 샘플링 합니다.

##  <a name="gather_alpha"></a> gather_alpha

지정된 된 샘플링 구성을 사용 하 여 지정된 된 좌표에 질감을 샘플링 하 고 4 개의 샘플링 된 텍셀의 알파 (w) 구성 요소를 반환 합니다.

```
const gather_return_type gather_alpha(
    const sampler& _Sampler,
    const coordinates_type& _Coord) const restrict(amp);

template<
    address_mode _Address_mode = address_clamp
>
const gather_return_type gather_alpha(
    const coordinates_type& _Coord) const restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_Address_mode*<br/>
사용 하는 주소 모드 샘플에는 `texture_view`합니다. 주소 모드가 모든 차원에 대해 동일 합니다.

*_Sampler*<br/>
사용 하는 샘플러 구성 샘플을 `texture_view`입니다.

*_Coord*<br/>
샘플을 취할 좌표입니다. 좌표 값은 샘플 텍스트 사이 보간 하는 데 사용 됩니다.

### <a name="return-value"></a>반환 값

4 차원 짧은 벡터 알파 (w) 구성 요소 4의 샘플링 텍셀 값을 포함 합니다.

##  <a name="get"></a> get

지정된 된 인덱스에 요소 값을 가져옵니다.

```
const value_type get(
    const index<_Rank>& _Index) const restrict(amp);

value_type get(
    const index<_Rank>& _Index,
    unsigned int _Mip_level = 0) const restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_Index*<br/>
가져오기, 아마도 다중 차원 요소의 인덱스입니다.

*_Mip_level*<br/>
값은 얻게 mip 맵 수준입니다. 기본값 0은 가장 상세한 밉 맵 수준을 나타냅니다.

### <a name="return-value"></a>반환 값

요소의 값입니다.

##  <a name="operator_eq"></a> operator=

지정 된와 동일한 텍스처의 뷰를 할당 `texture_view` 이 `texture_view` 인스턴스.

```
texture_view<value_type, _Rank>& operator= (// [1] copy constructor
    const texture_view<value_type, _Rank>& _Other) restrict(amp, cpu);

texture_view<const value_type, _Rank>& operator= (// [2] copy constructor
    const texture_view<value_type, _Rank>& _Other) restrict(cpu);

texture_view<const value_type, _Rank>& operator= (// [3] copy constructor
    const texture_view<const value_type, _Rank>& _Other) restrict(amp, cpu);
```

### <a name="parameters"></a>매개 변수

*_Other*<br/>
[1, 2] 쓰기 가능한 복사본 생성자 `texture_view` 개체입니다.

[쓰기 불가능 3] 복사 생성자 `texture_view` 개체입니다.

### <a name="return-value"></a>반환 값

이에 대 한 참조 `texture_view` 인스턴스.

##  <a name="operator_at"></a> operator[]

인덱스 별로 요소 값을 반환합니다.

```
const value_type operator[] (const index<_Rank>& _Index) const restrict(amp);

const value_type operator[] (int _I0) const restrict(amp);

value_type operator[] (const index<_Rank>& _Index) const restrict(amp);

value_type operator[] (int _I0) const restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_Index*<br/>
인덱스, 아마도 다중 차원입니다.

*_I0*<br/>
1 차원 인덱스입니다.

### <a name="return-value"></a>반환 값

요소 값으로 인덱싱된 `_Index`합니다.

##  <a name="operator_call"></a> operator()

인덱스 별로 요소 값을 반환합니다.

```
const value_type operator() (
    const index<_Rank>& _Index) const restrict(amp);

const value_type operator() (
    int _I0) const restrict(amp);

const value_type operator() (
    int _I0,   int _I1) const restrict(amp);

const value_type operator() (
    int _I0,
    int _I1,
    int _I2) const restrict(amp);

value_type operator() (
    const index<_Rank>& _Index) const restrict(amp);

value_type operator() (
    int _I0) const restrict(amp);

value_type operator() (
    int _I0,
    int _I1) const restrict(amp);

value_type operator() (
    int _I0,
    int _I1,
    int _I2) const restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_Index*<br/>
인덱스, 아마도 다중 차원입니다.

*_I0*<br/>
인덱스의 가장 중요 한 구성 요소입니다.

*_I1*<br/>
다음-에-가장 중요 한 구성 요소 인덱스입니다.

*_I2*<br/>
인덱스의 가장 중요 한 구성 요소입니다.

### <a name="return-value"></a>반환 값

요소 값으로 인덱싱된 `_Index`합니다.

##  <a name="sample"></a> 샘플

지정된 된 샘플링 구성을 사용 하 여 세부 수준을 확인 하 고 지정 된 좌표에 질감을 샘플링 합니다.

```
value_type sample(
    const sampler& _Sampler,
    const coordinates_type& _Coord,
    float _Level_of_detail = 0.0f) const restrict(amp);

template<
    filter_mode _Filter_mode = filter_linear,
    address_mode _Address_mode = address_clamp
>
value_type sample(
    const coordinates_type& _Coord,
    float _Level_of_detail = 0.0f) const restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_Filter_mode*<br/>
Texture_view에 사용 하는 필터 모드입니다. 필터 모드는 최소화, 극대화, 및 밉 맵 필터에 대 한 동일합니다.

*_Address_mode*<br/>
Texture_view에 사용 하는 주소 모드입니다. 주소 모드가 모든 차원에 대해 동일 합니다.

*_Sampler*<br/>
Texture_view에 사용 하는 샘플러 구성입니다.

*_Coord*<br/>
샘플을 취할 좌표입니다. 좌표 값은 텍셀 값 사이 보간 하는 데 사용 됩니다.

*_Level_of_detail*<br/>
값에서 샘플링할 밉 맵 레벨을 지정 합니다. 소수 값은 두 텍셀 사이 보간 하는 데 사용 됩니다. 세부 기본 수준은 가장 자세한 밉 수준을 나타내는 0입니다.

### <a name="return-value"></a>반환 값

보간된 샘플 값입니다.

##  <a name="set"></a> 설정

지정된 된 값으로 지정된 된 인덱스에 요소 값을 설정합니다.

```
void set(
    const index<_Rank>& _Index,
    const value_type& value) const restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_Index*<br/>
아마도 다중 차원 설정 요소의 인덱스입니다.

*값*<br/>
요소를 설정 값입니다.

##  <a name="value_type"></a> value_type

Texture_view의 요소 값 형식입니다.

```
typedef typename const value_type value_type;
```

## <a name="see-also"></a>참고자료

[Concurrency::graphics 네임스페이스](concurrency-graphics-namespace.md)
