---
title: tiled_extent 클래스
ms.date: 11/04/2016
f1_keywords:
- tiled_extent
- AMP/tiled_extent
- AMP/Concurrency::tiled_extent::tiled_extent
- AMP/Concurrency::tiled_extent::get_tile_extent
- AMP/Concurrency::tiled_extent::pad
- AMP/Concurrency::tiled_extent::truncate
- AMP/Concurrency::tiled_extent::tile_dim0
- AMP/Concurrency::tiled_extent::tile_dim1
- AMP/Concurrency::tiled_extent::tile_dim2
- AMP/Concurrency::tiled_extent::tile_extent
ms.assetid: 671ecaf8-c7b0-4ac8-bbdc-e30bd92da7c0
ms.openlocfilehash: 51e7696b8103e81d42beec0987a49f26fe041643
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62352283"
---
# <a name="tiledextent-class"></a>tiled_extent 클래스

A `tiled_extent` 개체는 `extent` 익스텐트 공간 1, 2 또는 3 차원 타일로 세분 하는 1 ~ 3 차원 개체입니다.

### <a name="syntax"></a>구문

```
template <
    int _Dim0,
    int _Dim1,
    int _Dim2
>
class tiled_extent : public Concurrency::extent<3>;

template <
    int _Dim0,
    int _Dim1
>
class tiled_extent<_Dim0, _Dim1, 0> : public Concurrency::extent<2>;

template <
    int _Dim0
>
class tiled_extent<_Dim0, 0, 0> : public Concurrency::extent<1>;
```

### <a name="parameters"></a>매개 변수

*_Dim0*<br/>
최대 유효 치수의 길이입니다.

*_Dim1*<br/>
다음 최대 유효 치수의 길이입니다.

*_Dim2*<br/>
최소 유효 치수의 길이입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[tiled_extent 생성자](#ctor)|`tiled_extent` 클래스의 새 인스턴스를 초기화합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[get_tile_extent](#get_tile_extent)|반환을 `extent` 개체의 값을 캡처하는 합니다 `tiled_extent` 템플릿 인수 `_Dim0`, `_Dim1`, 및 `_Dim2`합니다.|
|[pad](#pad)|반환 된 새 `tiled_extent` 익스텐트를 사용 하 여 개체 타일 크기에 따라 균등 하 게 나눌 수를 조정 합니다.|
|[truncate](#truncate)|반환 된 새 `tiled_extent` 타일 크기에 따라 균등 하 게 나눌 수를 조정 된 익스텐트를 사용 하 여 개체입니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[operator=](#operator_eq)|지정 된 내용을 복사 `tiled_index` 을 여기에 개체입니다.|

### <a name="public-constants"></a>공용 상수

|이름|설명|
|----------|-----------------|
|[tile_dim0 Constant](#tile_dim0)|최대 유효 치수의 길이 저장 합니다.|
|[tile_dim1 Constant](#tile_dim1)|다음 최대 유효 치수의 길이 저장 합니다.|
|[tile_dim2 Constant](#tile_dim2)|최소 유효 치수의 길이 저장 합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[tile_extent](#tile_extent)|가져옵니다는 `extent` 의 값을 캡처하는 개체를 `tiled_extent` 템플릿 인수 `_Dim0`, `_Dim1`, 및 `_Dim2`.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`extent`

`tiled_extent`

## <a name="requirements"></a>요구 사항

**헤더:** amp.h

**네임스페이스:** 동시성

## <a name="ctor"> </a>  tiled_extent 생성자

`tiled_extent` 클래스의 새 인스턴스를 초기화합니다.

### <a name="syntax"></a>구문

```
tiled_extent();

tiled_extent(
    const Concurrency::extent<rank>& _Other );

tiled_extent(
    const tiled_extent& _Other );
```

### <a name="parameters"></a>매개 변수

*_Other*<br/>
합니다 `extent` 또는 `tiled_extent` 복사할 개체입니다.

## <a name="get_tile_extent"> </a>  get_tile_extent

반환을 `extent` 개체의 값을 캡처하는 합니다 `tiled_extent` 템플릿 인수 `_Dim0`, `_Dim1`, 및 `_Dim2`합니다.

### <a name="syntax"></a>구문

```
Concurrency::extent<rank> get_tile_extent() const restrict(amp,cpu);
```

### <a name="return-value"></a>반환 값

`extent` 개체의 크기를 캡처하는 `tiled_extent` 인스턴스.

## <a name="pad"> </a>  pad

반환 된 새 `tiled_extent` 익스텐트를 사용 하 여 개체 타일 크기에 따라 균등 하 게 나눌 수를 조정 합니다.

### <a name="syntax"></a>구문

```
tiled_extent pad() const;
```

### <a name="return-value"></a>반환 값

새 `tiled_extent` 값 개체입니다.
## <a name="truncate"> </a>  truncate

반환 된 새 `tiled_extent` 타일 크기에 따라 균등 하 게 나눌 수를 조정 된 익스텐트를 사용 하 여 개체입니다.

### <a name="syntax"></a>구문

```
tiled_extent truncate() const;
```

### <a name="return-value"></a>반환 값

반환 된 새 `tiled_extent` 타일 크기에 따라 균등 하 게 나눌 수를 조정 된 익스텐트를 사용 하 여 개체입니다.

## <a name="operator_eq"> </a>  operator=

지정 된 내용을 복사 `tiled_index` 을 여기에 개체입니다.

### <a name="syntax"></a>구문

```
tiled_extent&  operator= (
    const tiled_extent& _Other ) restrict (amp, cpu);
```

### <a name="parameters"></a>매개 변수

*_Other*<br/>
`tiled_index` 복사할 개체입니다.

### <a name="return-value"></a>반환 값

이에 대 한 참조 `tiled_index` 인스턴스.

## <a name="tile_dim0"> </a>  tile_dim0

최대 유효 치수의 길이 저장 합니다.

### <a name="syntax"></a>구문

```
static const int tile_dim0 = _Dim0;
```

## <a name="tile_dim1"> </a>  tile_dim1

다음 최대 유효 치수의 길이 저장 합니다.

### <a name="syntax"></a>구문

```
static const int tile_dim1 = _Dim1;
```

## <a name="tile_dim2"> </a>  tile_dim2

최소 유효 치수의 길이 저장 합니다.

### <a name="syntax"></a>구문

```
static const int tile_dim2 = _Dim2;
```

## <a name="tile_extent"> </a>  tile_extent
  가져옵니다는 `extent` 의 값을 캡처하는 개체를 `tiled_extent` 템플릿 인수 `_Dim0`, `_Dim1`, 및 `_Dim2`.

### <a name="syntax"></a>구문

```
__declspec(property(get= get_tile_extent)) Concurrency::extent<rank> tile_extent;
```

## <a name="see-also"></a>참고자료

[Concurrency 네임스페이스(C++ AMP)](concurrency-namespace-cpp-amp.md)
