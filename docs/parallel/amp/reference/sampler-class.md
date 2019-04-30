---
title: sampler 클래스
ms.date: 06/28/2018
f1_keywords:
- sampler
- AMP_GRAPHICS/sampler
- AMP_GRAPHICS/concurrency::sampler::graphics::sampler
- AMP_GRAPHICS/concurrency::sampler::graphics::get_address_mode
- AMP_GRAPHICS/concurrency::sampler::graphics::get_border_color
- AMP_GRAPHICS/concurrency::sampler::graphics::get_filter_mode
- AMP_GRAPHICS/concurrency::sampler::graphics::address_mode
- AMP_GRAPHICS/concurrency::sampler::graphics::border_color
- AMP_GRAPHICS/concurrency::sampler::graphics::filter_mode
ms.assetid: 9a6a9807-497d-402d-b092-8c4d86275b80
ms.openlocfilehash: 1a66e4d025a7592b78839dbe5f25f9103da41224
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62352595"
---
# <a name="sampler-class"></a>sampler 클래스

샘플러 클래스는 텍스처 샘플링에 사용 되는 샘플링 구성 정보를 집계 합니다.

## <a name="syntax"></a>구문

```cpp
class sampler;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[샘플러 생성자](#ctor)|오버로드됨. 샘플러 인스턴스를 생성 합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[get_address_mode](#get_address_mode)|반환 된 `address_mode` 샘플러 개체와 연관 된 합니다.|
|[get_border_color](#get_border_color)|샘플러 개체와 연결 된 테두리 색을 반환 합니다.|
|[get_filter_mode](#get_filter_mode)|반환 된 `filter_mode` 샘플러 개체와 연관 된 합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[operator=](#operator_eq)|오버로드됨. 대입 연산자입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[address_mode](#address_mode)|주소 모드를 가져옵니다는 `sampler` 개체입니다.|
|[border_color](#border_color)|테두리 색을 가져옵니다는 `sampler` 개체입니다.|
|[filter_mode](#filter_mode)|필터 모드를 가져옵니다는 `sampler` 개체입니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`sampler`

## <a name="requirements"></a>요구 사항

**헤더:** amp_graphics.h

**Namespace:** concurrency:: graphics

##  <a name="ctor"></a> 샘플러

인스턴스를 생성 합니다 [sampler 클래스](sampler-class.md)합니다.

```cpp
sampler() restrict(cpu);    // [1] default constructor

sampler(                    // [2] constructor
    filter_mode _Filter_mode) restrict(cpu);

sampler(                    // [3] constructor
    address_mode _Address_mode,
    float_4 _Border_color = float_4(0.0f,
    0.0f,
    0.0f,
    0.0f)) restrict(cpu);

sampler(                    // [4] constructor
    filter_mode _Filter_mode,
    address_mode _Address_mode,
    float_4 _Border_color = float_4(0.0f,
    0.0f,
    0.0f,
    0.0f)) restrict(cpu);

sampler(                    // [5] copy constructor
    const sampler& _Other) restrict(amp,
    cpu);

sampler(                    // [6] move constructor
    sampler&& _Other) restrict(amp,
    cpu);
```

### <a name="parameters"></a>매개 변수

*_Filter_mode*<br/>
샘플링에 사용할 필터 모드입니다.

*_Address_mode*<br/>
모든 차원에 대 한 샘플링에 사용할 주소 모드입니다.

*_Border_color*<br/>
주소 모드는 address_border입니다 경우 사용할 테두리 색입니다. 기본값은 `float_4(0.0f, 0.0f, 0.0f, 0.0f)`입니다.

*_Other*<br/>
[5] 복사 생성자는 `sampler` 새 복사할 개체 `sampler` 인스턴스.

[6] 이동 생성자는 `sampler` 개체를 새 이동할 `sampler` 인스턴스.

##  <a name="address_mode"></a> address_mode

주소 모드를 가져옵니다는 `sampler` 개체입니다.

```cpp
__declspec(property(get= get_address_mode)) Concurrency::graphics::address_mode address_mode;
```

##  <a name="border_color"></a> border_color

테두리 색을 가져옵니다는 `sampler` 개체입니다.

```cpp
__declspec(property(get= get_border_color)) Concurrency::graphics::float_4 border_color;
```

##  <a name="filter_mode"></a> filter_mode

필터 모드를 가져옵니다는 `sampler` 개체입니다.

```cpp
__declspec(property(get= get_filter_mode)) Concurrency::graphics::filter_mode filter_mode;
```

##  <a name="get_address_mode"></a> get_address_mode

이 대해 구성 된 필터 모드를 반환 `sampler`합니다.

```cpp
Concurrency::graphics::address_mode get_address_mode() const __GPU;
```

### <a name="return-value"></a>반환 값

샘플러에 구성 된 주소 모드입니다.

##  <a name="get_border_color"></a> get_border_color

이 대해 구성 된 테두리 색을 반환 합니다 `sampler`합니다.

```cpp
Concurrency::graphics::float_4 get_border_color() const restrict(amp, cpu);
```

### <a name="return-value"></a>반환 값

테두리 색이 포함 된 float_4입니다.

##  <a name="get_filter_mode"></a> get_filter_mode

이 대해 구성 된 필터 모드를 반환 `sampler`합니다.

```cpp
Concurrency::graphics::filter_mode get_filter_mode() const restrict(amp, cpu);
```

### <a name="return-value"></a>반환 값

샘플러에 구성 된 필터 모드입니다.

##  <a name="operator_eq"></a> operator=

다른 샘플러 개체의 값을 기존 샘플러에 할당합니다.

```cpp
sampler& operator= (    // [1] copy assignment operator
    const sampler& _Other) restrict(amp, cpu);

sampler& operator= (    // [2] move assignment operator
    sampler&& _Other) restrict(amp, cpu);
```

### <a name="parameters"></a>매개 변수

*_Other*<br/>
[1] 복사 할당 연산자는 `sampler` 이 복사할 개체 `sampler`합니다.

[2] 이동 할당 연산자는 `sampler` 로 이동할 개체 `sampler`합니다.

### <a name="return-value"></a>반환 값

이 샘플러 인스턴스에 대 한 참조입니다.

## <a name="see-also"></a>참고자료

[Concurrency::graphics 네임스페이스](concurrency-graphics-namespace.md)
