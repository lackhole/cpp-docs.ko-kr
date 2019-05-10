---
title: tiled_index 클래스
ms.date: 03/27/2019
f1_keywords:
- tiled_index
- AMP/tiled_index
- AMP/Concurrency::tiled_index::tiled_index
- AMP/Concurrency::tiled_index::get_tile_extent
- AMP/Concurrency::tiled_index::barrier
- AMP/Concurrency::tiled_index::global
- AMP/Concurrency::tiled_index::local
- AMP/Concurrency::tiled_index::rank
- AMP/Concurrency::tiled_index::tile
- AMP/Concurrency::tiled_index::tile_dim0
- AMP/Concurrency::tiled_index::tile_dim1
- AMP/Concurrency::tiled_index::tile_dim2
- AMP/Concurrency::tiled_index::tile_origin
- AMP/Concurrency::tiled_index::tile_extent
helpviewer_keywords:
- tiled_index class
ms.assetid: 0ce2ae26-f1bb-4436-b473-a9e1b619bb38
ms.openlocfilehash: dd8b6d7a0e174c88ad229da2d08a9ec8a11fb0aa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62352192"
---
# <a name="tiledindex-class"></a>tiled_index 클래스

인덱스를 제공 된 [tiled_extent](tiled-extent-class.md) 개체입니다. 이 클래스는 로컬 타일 원본에 상대적인 및 전역 원본과 요소에 액세스 하는 속성에 있습니다. 바둑판식된 공간에 대 한 자세한 내용은 참조 하세요. [를 사용 하 여 타일](../../../parallel/amp/using-tiles.md)합니다.

## <a name="syntax"></a>구문

```
template <
    int _Dim0,
    int _Dim1 = 0,
    int _Dim2 = 0
>
class tiled_index : public _Tiled_index_base<3>;

template <
    int _Dim0,
    int _Dim1
>
class tiled_index<_Dim0, _Dim1, 0> : public _Tiled_index_base<2>;

template <
    int _Dim0
>
class tiled_index<_Dim0, 0, 0> : public _Tiled_index_base<1>;
```

#### <a name="parameters"></a>매개 변수

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
|[tiled_index 생성자](#ctor)|`tile_index` 클래스의 새 인스턴스를 초기화합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[get_tile_extent](#tiled_index__get_tile_extent)|반환을 [익스텐트](extent-class.md) 의 값을 가진 개체를 `tiled_index` 템플릿 인수 `_Dim0`, `_Dim1`, 및 `_Dim2`합니다.|

### <a name="public-constants"></a>공용 상수

|이름|설명|
|----------|-----------------|
|[barrier 상수](#tiled_index__barrier)|저장소를 [tile_barrier](tile-barrier-class.md) 스레드의 현재 타일에 장애물을 나타내는 개체입니다.|
|||
|[전역 상수](#tiled_index__global)|저장소를 [인덱스](index-class.md) 모눈 개체의 전역 인덱스를 나타내는 차수 1, 2 또는 3의 개체입니다.|
|[지역 상수](#tiled_index__local)|저장소를 `index` 의 현재 타일의 상대를 나타내는 차수 1, 2 또는 3 인덱스의 개체를 [tiled_extent](tiled-extent-class.md) 개체입니다.|
|[rank 상수](#tiled_index__rank)|차수를 저장 합니다 `tiled_index` 개체입니다.|
|[tile 상수](#tiled_index__tile)|저장소를 `index` 차수 1, 2 또는 3의 현재 타일의 좌표를 나타내는 개체를 `tiled_extent` 개체입니다.|
|[tile_dim0 Constant](#tiled_index__tile_dim0)|최대 유효 치수의 길이 저장 합니다.|
|[tile_dim1 Constant](#tiled_index__tile_dim1)|다음 최대 유효 치수의 길이 저장 합니다.|
|[tile_dim2 Constant](#tiled_index__tile_dim2)|최소 유효 치수의 길이 저장 합니다.|
|[tile_origin Constant](#tiled_index__tile_origin)|저장소를 `index` 개체의 현재 타일의 원점의 전역를 나타내는 차수 1, 2 또는 3 좌표는 `tiled_extent` 개체입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[tile_extent](#tile_extent)|가져옵니다는 [익스텐트](extent-class.md) 의 값을 가진 개체를 `tiled_index` 템플릿 인수 `tiled_index` 템플릿 인수 `_Dim0`, `_Dim1`, 및 `_Dim2`합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`_Tiled_index_base`

`tiled_index`

## <a name="requirements"></a>요구 사항

**헤더:** amp.h

**네임스페이스:** 동시성

## <a name="ctor"></a>  tiled_index 생성자

`tiled_index` 클래스의 새 인스턴스를 초기화합니다.

## <a name="syntax"></a>구문

```
tiled_index(
    const index<rank>& _Global,
    const index<rank>& _Local,
    const index<rank>& _Tile,
    const index<rank>& _Tile_origin,
    const tile_barrier& _Barrier ) restrict(amp,cpu);

tiled_index(
    const tiled_index& _Other ) restrict(amp,cpu);
```

#### <a name="parameters"></a>매개 변수

*_Global*<br/>
전역 [인덱스](index-class.md) 생성 된 `tiled_index`합니다.

*_Local*<br/>
로컬 [인덱스](index-class.md) 생성 된 `tiled_index`

*_Tile*<br/>
타일 [인덱스](index-class.md) 생성 된 `tiled_index`

*_Tile_origin*<br/>
타일 원본 [인덱스](index-class.md) 생성 된 `tiled_index`

*_Barrier*<br/>
합니다 [tile_barrier](tile-barrier-class.md) 생성 된 개체 `tiled_index`합니다.

*_Other*<br/>
합니다 `tile_index` 복사할 개체를 생성 된 `tiled_index`합니다.

## <a name="overloads"></a>Overloads

|||
|-|-|
|이름|설명|
|`tiled_index(const index<rank>& _Global, const index<rank>& _Local, const index<rank>& _Tile, const index<rank>& _Tile_origin, const tile_barrier& _Barrier restrict(amp,cpu);`|새 인스턴스를 초기화 합니다 `tile_index` 전역 좌표의 타일 및 로컬 좌표의 타일의 상대 위치를 인덱스에서 클래스입니다. 합니다 `_Global` 고 `_Tile_origin` 매개 변수에서 계산 됩니다.|
|`tiled_index(    const tiled_index& _Other) restrict(amp,cpu);`|새 인스턴스를 초기화 합니다 `tile_index` 지정 된 복사 하 여 클래스 `tiled_index` 개체입니다.|

## <a name="tiled_index__get_tile_extent"></a>  get_tile_extent

반환을 [익스텐트](extent-class.md) 의 값을 가진 개체를 `tiled_index` 템플릿 인수 `_Dim0`, `_Dim1`, 및 `_Dim2`합니다.

## <a name="syntax"></a>구문

```
extent<rank> get_tile_extent()restrict(amp,cpu);
```

## <a name="return-value"></a>반환 값

`extent` 템플릿 인수 `tiled_index`, `_Dim0` 및 `_Dim1`의 값을 가진 `_Dim2` 개체입니다.

## <a name="tiled_index__barrier"></a>  barrier

저장소를 [tile_barrier](tile-barrier-class.md) 스레드의 현재 타일에 장애물을 나타내는 개체입니다.

## <a name="syntax"></a>구문

```
const tile_barrier barrier;
```

## <a name="tiled_index__global"></a>  global

저장소를 [인덱스](index-class.md) 개체는 개체의 전역 인덱스를 나타내는 차수 1, 2 또는 3입니다.

## <a name="syntax"></a>구문

```
const index<rank> global;
```

## <a name="tiled_index__local"></a>  local

저장소를 [인덱스](index-class.md) 의 현재 타일의 상대를 나타내는 차수 1, 2 또는 3 인덱스의 개체를 [tiled_extent](tiled-extent-class.md) 개체입니다.

## <a name="syntax"></a>구문

```
const index<rank> local;
```

## <a name="tiled_index__rank"></a>  rank

차수를 저장 합니다 `tiled_index` 개체입니다.

## <a name="syntax"></a>구문

```
static const int rank = _Rank;
```

## <a name="tiled_index__tile"></a>  tile

저장소를 [인덱스](index-class.md) 차수 1, 2 또는 3의 현재 타일의 좌표를 나타내는 개체를 [tiled_extent](tiled-extent-class.md) 개체입니다.

## <a name="syntax"></a>구문

```
const index<rank> tile;
```

## <a name="tiled_index__tile_dim0"></a>  tile_dim0

최대 유효 치수의 길이 저장 합니다.

## <a name="syntax"></a>구문

```
static const int tile_dim0 = _Dim0;
```

## <a name="tiled_index__tile_dim1"></a>  tile_dim1

다음 최대 유효 치수의 길이 저장 합니다.

## <a name="syntax"></a>구문

```
static const int tile_dim1 = _Dim1;
```

## <a name="tiled_index__tile_dim2"></a>  tile_dim2

최소 유효 치수의 길이 저장 합니다.

## <a name="syntax"></a>구문

```
static const int tile_dim2 = _Dim2;
```

## <a name="tiled_index__tile_origin"></a>  tile_origin

저장소를 [인덱스](index-class.md) 개체의 현재 타일의 원점의 전역를 나타내는 차수 1, 2 또는 3 좌표를 [tiled_extent](tiled-extent-class.md) 개체입니다.

## <a name="syntax"></a>구문

```
const index<rank> tile_origin
```

## <a name="tile_extent"></a>  tile_extent
  가져옵니다는 [익스텐트](extent-class.md) 의 값을 가진 개체를 `tiled_index` 템플릿 인수 `tiled_index` 템플릿 인수 `_Dim0`, `_Dim1`, 및 `_Dim2`합니다.

## <a name="syntax"></a>구문

```
__declspec(property(get= get_tile_extent)) extent<rank> tile_extent;
```

## <a name="see-also"></a>참고자료

[Concurrency 네임스페이스(C++ AMP)](concurrency-namespace-cpp-amp.md)
