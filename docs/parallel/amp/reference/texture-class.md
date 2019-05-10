---
title: texture 클래스
ms.date: 11/04/2016
f1_keywords:
- texture
- AMP_GRAPHICS/texture
- AMP_GRAPHICS/concurrency::graphics::texture::texture
- AMP_GRAPHICS/concurrency::graphics::texture::copy_to
- AMP_GRAPHICS/concurrency::graphics::texture::data
- AMP_GRAPHICS/concurrency::graphics::texture::get
- AMP_GRAPHICS/concurrency::graphics::texture::get_associated_accelerator_view
- AMP_GRAPHICS/concurrency::graphics::texture::get_depth_pitch
- AMP_GRAPHICS/concurrency::graphics::texture::get_row_pitch
- AMP_GRAPHICS/concurrency::graphics::texture::set
- AMP_GRAPHICS/concurrency::graphics::texture::rank
- AMP_GRAPHICS/concurrency::graphics::texture::associated_accelerator_view
- AMP_GRAPHICS/concurrency::graphics::texture::depth_pitch
- AMP_GRAPHICS/concurrency::graphics::texture::row_pitch
ms.assetid: 16e85d4d-e80a-474a-995d-8bf63fbdf34c
ms.openlocfilehash: cfcb65fa23fe4593e7dcf11da3b5da4b1785ce71
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62351536"
---
# <a name="texture-class"></a>texture 클래스

텍스처에 대 한 데이터 집계는 `accelerator_view` 범위 도메인에서 합니다. 범위 도메인에서 각 요소에 대 한 변수 컬렉션입니다. 각 변수는 해당 하는 값 C++ 기본 형식 ( `unsigned int`, `int`를 `float`를 `double`), 스칼라 형식 ( `norm`, 또는 `unorm`), 또는 short 벡터 형식입니다.

## <a name="syntax"></a>구문

```
template <typename value_type,  int _Rank>
class texture;
```

#### <a name="parameters"></a>매개 변수

*value_type*<br/>
질감의 요소 형식입니다.

*_Rank*<br/>
질감의 순위입니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|이름|설명|
|----------|-----------------|
|`scalar_type`|스칼라 형식입니다.|
|`value_type`|값 형식입니다.|

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[질감 생성자](#ctor)|`texture` 클래스의 새 인스턴스를 초기화합니다.|
|[~ texture 소멸자](#ctor)|제거 된 `texture` 개체입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[copy_to](#copy_to)|복사본을 `texture` 전체 복사를 수행 하 여 대상 개체입니다.|
|[data](#data)|이 질감의 원시 데이터에 대 한 CPU 포인터를 반환합니다.|
|[get](#get)|지정된 된 인덱스에 있는 요소의 값을 반환합니다.|
|[get_associated_accelerator_view](#get_associated_accelerator_view)|반환 된 [accelerator_view](accelerator-view-class.md) 복사할이 질감에 대 한 기본 대상입니다.|
|[get_depth_pitch](#get_depth_pitch)|3D 스테이징 텍스처 CPU에서 각 깊이 조각 사이의 바이트 수를 반환 합니다.|
|[get_row_pitch](#get_row_pitch)|2D 또는 3D 스테이징 텍스처에서 CPU의 각 행 사이의 바이트 수를 반환 합니다.|
|[set](#set)|지정된 된 인덱스에 요소 값을 설정합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[operator()](#operator_call)|매개 변수로 지정 된 요소 값을 반환 합니다.|
|[operator\[\]](#operator_at)|지정된 된 인덱스에 있는 요소를 반환 합니다.|
|[operator=](#operator_eq)|지정 된 복사 [질감](texture-class.md) 여기에 개체입니다.|

### <a name="public-constants"></a>공용 상수

|이름|설명|
|----------|-----------------|
|[rank 상수](#rank)|차수를 가져옵니다는 `texture` 개체입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[associated_accelerator_view](#associated_accelerator_view)|가져옵니다 합니다 [accelerator_view](accelerator-view-class.md) 복사할이 질감에 대 한 기본 대상입니다.|
|[depth_pitch](#depth_pitch)|Cpu의 3D 스테이징 텍스처에서 각 깊이 조각 사이의 바이트 수를 가져옵니다.|
|[row_pitch](#row_pitch)|스테이징 텍스처 CPU의 2D 또는 3D의 각 행 사이의 바이트 수를 가져옵니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`_Texture_base`

`texture`

## <a name="requirements"></a>요구 사항

**헤더:** amp_graphics.h

**네임스페이스:** Concurrency:: graphics

##  <a name="dtor"></a> ~texture

제거 된 `texture` 개체입니다.

```
~texture() restrict(cpu);
```

##  <a name="associated_accelerator_view"></a> associated_accelerator_view

가져옵니다 합니다 [accelerator_view](accelerator-view-class.md) 복사할이 질감에 대 한 기본 대상입니다.

```
__declspec(property(get= get_associated_accelerator_view)) Concurrency::accelerator_view associated_accelerator_view;
```

##  <a name="copy_to"></a> copy_to

복사본을 `texture` 전체 복사를 수행 하 여 대상 개체입니다.

```
void copy_to(texture& _Dest) const;
void copy_to(writeonly_texture_view<value_type, _Rank>& _Dest) const;
```

### <a name="parameters"></a>매개 변수

*_Dest*<br/>
복사할 개체입니다.

*_Rank*<br/>
질감의 순위입니다.

*value_type*<br/>
질감의 요소 형식입니다.

##  <a name="data"></a> 데이터

이 질감의 원시 데이터에 대 한 CPU 포인터를 반환합니다.

```
void* data() restrict(cpu);

const void* data() const restrict(cpu);
```

### <a name="return-value"></a>반환 값

질감의 원시 데이터에 대 한 포인터입니다.

##  <a name="depth_pitch"></a> depth_pitch

Cpu의 3D 스테이징 텍스처에서 각 깊이 조각 사이의 바이트 수를 가져옵니다.

```
__declspec(property(get= get_depth_pitch)) unsigned int depth_pitch;
```

##  <a name="get"></a> get

지정된 된 인덱스에 있는 요소의 값을 반환합니다.

```
const value_type get(const index<_Rank>& _Index) const restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_Index*<br/>
요소의 인덱스입니다.

### <a name="return-value"></a>반환 값

지정된 인덱스에 있는 요소의 값입니다.

##  <a name="get_associated_accelerator_view"></a> get_associated_accelerator_view

복사할이 질감에 대 한 기본 대상인 accelerator_view를 반환 합니다.

```
Concurrency::accelerator_view get_associated_accelerator_view() const restrict(cpu);
```

### <a name="return-value"></a>반환 값

합니다 [accelerator_view](accelerator-view-class.md) 복사할이 질감에 대 한 기본 대상입니다.

##  <a name="get_depth_pitch"></a> get_depth_pitch

3D 스테이징 텍스처 CPU에서 각 깊이 조각 사이의 바이트 수를 반환 합니다.

```
unsigned int get_depth_pitch() const restrict(cpu);
```

### <a name="return-value"></a>반환 값

3D 스테이징 텍스처 CPU에서 각 깊이 조각 사이의 바이트 수입니다.

##  <a name="get_row_pitch"></a> get_row_pitch

2 차원 스테이징 질감에서 각 행 사이의 또는 3 차원 스테이징 질감에서 깊이 조각의 각 행 사이의 바이트 수를 반환합니다.

```
unsigned int get_row_pitch() const restrict(cpu);
```

### <a name="return-value"></a>반환 값

2 차원 스테이징 질감에서 각 행 사이의 또는 3 차원 스테이징 질감에서 깊이 조각의 각 행 사이의 바이트 수입니다.

##  <a name="operator_call"></a> operator()

매개 변수로 지정 된 요소 값을 반환 합니다.

```
const value_type operator() (
    const index<_Rank>& _Index) const restrict(amp);

const value_type operator() (
    int _I0) const restrict(amp);

const value_type operator() (
    int _I0,
    int _I1) const restrict(amp);

const value_type operator() (
    int _I0,
    int _I1,
    int _I2) const restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_Index*<br/>
인덱스입니다.

*_I0*<br/>
인덱스의 가장 중요 한 구성 요소입니다.

*_I1*<br/>
다음-에-가장 중요 한 구성 요소 인덱스입니다.

*_I2*<br/>
인덱스의 가장 중요 한 구성 요소입니다.

*_Rank*<br/>
인덱스의 순위입니다.

### <a name="return-value"></a>반환 값

매개 변수로 지정 된 요소 값입니다.

##  <a name="operator_at"></a> operator[]

지정된 된 인덱스에 있는 요소를 반환 합니다.

```
const value_type operator[] (const index<_Rank>& _Index) const restrict(amp);

const value_type operator[] (int _I0) const restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_Index*<br/>
인덱스입니다.

*_I0*<br/>
인덱스입니다.

### <a name="return-value"></a>반환 값

지정된 된 인덱스에 있는 요소입니다.

##  <a name="operator_eq"></a> operator=

지정 된 복사 [질감](texture-class.md) 여기에 개체입니다.

```
texture& operator= (
    const texture& _Other);

texture& operator= (
    texture<value_type, _Rank>&& _Other);
```

### <a name="parameters"></a>매개 변수

*_Other*<br/>
`texture` 복사할 개체입니다.

### <a name="return-value"></a>반환 값

이에 대 한 참조 `texture` 개체입니다.

##  <a name="rank"></a> 순위

차수를 가져옵니다는 `texture` 개체입니다.

```
static const int rank = _Rank;
```

##  <a name="row_pitch"></a> row_pitch

스테이징 텍스처 CPU의 2D 또는 3D의 각 행 사이의 바이트 수를 가져옵니다.

```
__declspec(property(get= get_row_pitch)) unsigned int row_pitch;
```

##  <a name="set"></a> 설정

지정된 된 인덱스에 요소 값을 설정합니다.

```
void set(
    const index<_Rank>& _Index,
    const value_type& value) restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_Index*<br/>
요소의 인덱스입니다.

*_Rank*<br/>
인덱스의 순위입니다.

*값*<br/>
요소의 새 값입니다.

##  <a name="ctor"></a> 질감

`texture` 클래스의 새 인스턴스를 초기화합니다.

```
texture(const Concurrency::extent<_Rank>& _Ext) restrict(cpu);

texture(int _E0) restrict(cpu);

texture(int _E0, int _E1) restrict(cpu);

texture(int _E0, int _E1, int _E2) restrict(cpu);

texture(
    const Concurrency::extent<_Rank>& _Ext,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

texture(
    int _E0,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

texture(
    int _E0,
    int _E1,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

texture(
    int _E0,
    int _E1,
    int _E2,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

template<typename _Input_iterator>
texture(
    const Concurrency::extent<_Rank>& _Ext,
    _Input_iterator _Src_first,
    _Input_iterator _Src_last) restrict(cpu);

template<typename _Input_iterator>
texture(
    int _E0, _Input_iterator _Src_first, _Input_iterator _Src_last) restrict(cpu);

template<typename _Input_iterator>
texture(
    int _E0,
    int _E1,
    _Input_iterator _Src_first,
    _Input_iterator _Src_last) restrict(cpu);

template<typename _Input_iterator>
texture(
    int _E0,
    int _E1,
    int _E2,
    _Input_iterator _Src_first,
    _Input_iterator _Src_last) restrict(cpu);

template<typename _Input_iterator>
texture(
    const Concurrency::extent<_Rank>& _Ext,
    _Input_iterator _Src_first,
    _Input_iterator _Src_last,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

template<typename _Input_iterator>
texture(
    int _E0,
    _Input_iterator _Src_first,
    _Input_iterator _Src_last,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

template<typename _Input_iterator>
texture(
    int _E0,
    int _E1,
    _Input_iterator _Src_first,
    _Input_iterator _Src_last,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

template<typename _Input_iterator>
texture(
    int _E0,
    int _E1,
    int _E2,
    _Input_iterator _Src_first,
    _Input_iterator _Src_last,
    const Concurrency::accelerator_view& _Av) restrict(cpu))  ;

texture(
    int _E0,
    unsigned int _Bits_per_scalar_element) restrict(cpu);

texture(
    int _E0,
    int _E1,
    unsigned int _Bits_per_scalar_element) restrict(cpu);

texture(
    int _E0,
    int _E1,
    int _E2,
    unsigned int _Bits_per_scalar_element) restrict(cpu);

texture(
    const Concurrency::extent<_Rank>& _Ext,
    unsigned int _Bits_per_scalar_element,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

texture(
    int _E0,
    unsigned int _Bits_per_scalar_element,
    const Concurrency::accelerator_view& _Av)  ;

texture(
    int _E0,
    int _E1,
    unsigned int _Bits_per_scalar_element,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

texture(
    int _E0,
    int _E1,
    int _E2,
    unsigned int _Bits_per_scalar_element,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

texture(
    const Concurrency::extent<_Rank>& _Ext,
    _In_ void* _Source,
    unsigned int _Src_byte_size,
    unsigned int _Bits_per_scalar_element) restrict(cpu);

texture(
    int _E0,
    _In_ void* _Source,
    unsigned int _Src_byte_size,
    unsigned int _Bits_per_scalar_element) restrict(cpu);

texture(
    int _E0,
    int _E1,
    _In_ void* _Source,
    unsigned int _Src_byte_size,
    unsigned int _Bits_per_scalar_element) restrict(cpu);

texture(
    int _E0,
    int _E1,
    int _E2,
    _In_ void* _Source,
    unsigned int _Src_byte_size,
    unsigned int _Bits_per_scalar_element) restrict(cpu);

texture(
    const Concurrency::extent<_Rank>& _Ext,
    _In_ void* _Source,
    unsigned int _Src_byte_size,
    unsigned int _Bits_per_scalar_element,
    const Concurrency::accelerator_view& _Av)  ;

texture(
    int _E0,
    _In_ void* _Source,
    unsigned int _Src_byte_size,
    unsigned int _Bits_per_scalar_element,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

texture(
    int _E0,
    int _E1,
    _In_ void* _Source,
    unsigned int _Src_byte_size,
    unsigned int _Bits_per_scalar_element,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

texture(
    int _E0,
    int _E1,
    int _E2,
    _In_ void* _Source,
    unsigned int _Src_byte_size,
    unsigned int _Bits_per_scalar_element,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

texture(
    const texture& _Src,
    const Concurrency::accelerator_view& _Acc_view);

texture(
    texture&& _Other);

texture(
    const Concurrency::extent<_Rank>& _Ext,
    unsigned int _Bits_per_scalar_element,
    const Concurrency::accelerator_view& _Av);

texture(
    const texture& _Src);
```

### <a name="parameters"></a>매개 변수

*_Acc_view*<br/>
합니다 [accelerator_view](accelerator-view-class.md) 텍스처의 위치를 지정 하는 합니다.

*_Av*<br/>
합니다 [accelerator_view](accelerator-view-class.md) 텍스처의 위치를 지정 하는 합니다.

*_Associated_av*<br/>
이 질감의 복사본에 대 한 기본 대상을 지정 하는 accelerator_view입니다.

*_Bits_per_scalar_element*<br/>
텍스처의 기본 스칼라 형식의 각 스칼라 요소당 비트 수입니다. 일반적으로 지원 되는 값은 8, 16, 32 및 64입니다. 0을 지정 된 비트 수가 기본 scalar_type과 같습니다. 64 이중 기반 텍스처에만 유효합니다.

*_Ext*<br/>
텍스처의 각 차원의 범위입니다.

*_E0*<br/>
질감의 가장 중요 한 구성 요소입니다.

*_E1*<br/>
질감의 다음-에-가장 중요 한 구성 요소입니다.

*_E2*<br/>
텍스처 범위의 가장 중요 하지 않은 구성 요소입니다.

*_Input_iterator*<br/>
입력된 반복기의 형식입니다.

*_Mipmap_levels*<br/>
기본 질감의 밉 맵 수준 수입니다. 0을 지정 하는 경우 질감에 mip 맵 수준까지 지정된 된 범위에 대 한 가장 작은 크기의 전체 범위를 해야 합니다.

*_Rank*<br/>
범위의 차수입니다.

*_Source*<br/>
호스트 버퍼에 대 한 포인터입니다.

*_Src*<br/>
복사할 질감입니다.

*_Src_byte_size*<br/>
소스 버퍼의 바이트 수입니다.

*_Src_first*<br/>
소스 컨테이너에는 시작 반복기입니다.

*_Src_last*<br/>
소스 컨테이너에 사용 되는 끝 반복기입니다.

*_Other*<br/>
다른 데이터 원본입니다.

*_Rank*<br/>
섹션의 순위입니다.

## <a name="see-also"></a>참고자료

[Concurrency::graphics 네임스페이스](concurrency-graphics-namespace.md)
