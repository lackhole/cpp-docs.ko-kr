---
title: extent 클래스(C++ AMP)
ms.date: 03/27/2019
f1_keywords:
- extent
- AMP/extent
- AMP/Concurrency::extent::extent
- AMP/Concurrency::extent::contains
- AMP/Concurrency::extent::size
- AMP/Concurrency::extent::tile
- AMP/Concurrency::extent::rank Constant
helpviewer_keywords:
- extent structure
ms.assetid: edb5de3d-3935-4dbb-8365-4cc6c4fb0269
ms.openlocfilehash: 46af59708ef3f0d91883c52502bce4d09676ca77
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62181946"
---
# <a name="extent-class-c-amp"></a>extent 클래스(C++ AMP)

벡터를 나타냅니다 *N* 의 범위를 지정 하는 정수 값을 *N*-원점이 0 차원 공간입니다. 벡터의 값은 최하위에서 최하위 순서로 정렬 합니다.

### <a name="syntax"></a>구문

```
template <int _Rank>
class extent;
```

### <a name="parameters"></a>매개 변수

*_Rank*<br/>
순위를 `extent` 개체입니다.

## <a name="requirements"></a>요구 사항

**헤더:** amp.h

**네임스페이스:** 동시성

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[extent 생성자](#ctor)|`extent` 클래스의 새 인스턴스를 초기화합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[contains](#contains)|확인 된 `extent` 개체의 순위를 지정된 합니다.|
|[size](#size)|범위 (요소의 단위)에서 총 선형 크기를 반환합니다.|
|[tile](#tile)|생성 된 `tiled_extent` 지정 된 타일을 사용 하 여 개체 크기를 지정 합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[operator-](#operator_min)|반환 된 새 `extent` 빼는 방식으로 만들어지는 개체는 `index` 해당 되는 요소 `extent` 요소입니다.|
|[operator--](#operator_min_min)|감소의 각 요소는 `extent` 개체입니다.|
|[operator%=](#operator_mod_eq)|각 요소에 모듈러스 (나머지)를 계산 합니다 `extent` 해당 요소를 숫자로 나눌 때 개체입니다.|
|[operator*=](#operator_star_eq)|각 요소를 곱합니다는 `extent` 번호로 개체입니다.|
|[operator/=](#operator_min_eq)|각 요소를 나눕니다는 `extent` 번호로 개체입니다.|
|[extent::operator\[\]](#operator_at)|지정된 된 인덱스에 있는 요소를 반환 합니다.|
|[operator+](#operator_add)|반환 된 새 `extent` 해당 추가 하 여 만든 개체 `index` 고 `extent` 요소입니다.|
|[operator++](#operator_add_add)|각 요소를 증가 시킵니다는 `extent` 개체입니다.|
|[operator+=](#operator_add_eq)|지정된 된 수의 각 요소에 추가 된 `extent` 개체입니다.|
|[operator=](#operator_eq)|다른 콘텐츠를 복사 `extent` 을 여기에 개체입니다.|
|[operator-=](#operator_min_eq)|각 요소에서 지정한 수를 뺍니다는 `extent` 개체입니다.|

### <a name="public-constants"></a>공용 상수

|이름|설명|
|----------|-----------------|
|[rank 상수](#rank_constant)|차수를 가져옵니다는 `extent` 개체입니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`extent`

## <a name="contains"></a> 포함

나타냅니다 여부를 지정 된 [인덱스](index-class.md) '범위' 개체 내에서 값이 포함 됩니다.

### <a name="syntax"></a>구문

```
bool contains(const index<rank>& _Index) const restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Index*<br/>
`index` 테스트할 값입니다.

### <a name="return-value"></a>반환 값

**true** 하는 경우 지정 된 *인덱스* 에 포함 된 값을 `extent` ; 개체이 고, 그렇지 **false**합니다.

##  <a name="ctor"></a> 범위

'범위' 클래스의 새 인스턴스를 초기화합니다.

### <a name="syntax"></a>구문

```
extent() restrict(amp,cpu);
extent(const extent<_Rank>& _Other) restrict(amp,cpu);
explicit extent(int _I) restrict(amp,cpu);
extent(int _I0,  int _I1) restrict(amp,cpu);
extent(int _I0,  int _I1, int _I2) restrict(amp,cpu);
explicit extent(const int _Array[_Rank])restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Array*<br/>
배열을 `_Rank` 새 만드는 데 사용 되는 정수 `extent` 개체입니다.

*_I*<br/>
범위의 길이입니다.

*_I0*<br/>
최대 유효 치수의 길이입니다.

*_I1*<br/>
다음-에-가장 중요 한 차원의 길이입니다.

*_I2*<br/>
최소 유효 치수의 길이입니다.

*_Other*<br/>
`extent` 개체를 새 `extent` 개체를 기반으로 합니다.

## <a name="remarks"></a>설명

매개 변수가 없는 생성자는 `extent` 3의 순위를 가진 개체입니다.

배열을 생성 하는 경우는 `extent` 개체를 배열의 길이의 차수와 일치 해야 합니다는 `extent` 개체입니다.

##  <a name="operator_mod_eq"></a> operator%=

해당 요소를 숫자로 나눌 때의 각 요소에 '범위' 모듈러스 (나머지)를 계산 합니다.

### <a name="syntax"></a>구문

```
extent<_Rank>& operator%=(int _Rhs) restrict(cpu, direct3d);
```

### <a name="parameters"></a>매개 변수

*_Rhs*<br/>
모듈러스를 찾기 위한 숫자입니다.

### <a name="return-value"></a>반환 값

`extent` 개체

##  <a name="operator_star_eq"></a> operator*=

지정된 된 수 만큼 '범위' 개체의 각 요소를 곱합니다.

### <a name="syntax"></a>구문

```
extent<_Rank>& operator*=(int _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Rhs*<br/>
곱할 숫자입니다.

### <a name="return-value"></a>반환 값

`extent` 개체

## <a name="operator_add"></a> operator +

반환 된 새 `extent` 해당 추가 하 여 만든 개체 `index` 고 `extent` 요소입니다.

### <a name="syntax"></a>구문

```
extent<_Rank> operator+(const index<_Rank>& _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Rhs*<br/>
`index` 추가할 요소가 포함 된 개체입니다.

### <a name="return-value"></a>반환 값

새로운 `extent` 개체입니다.

##  <a name="operator_add_add"></a> operator + +

'범위' 개체의 각 요소를 증가 시킵니다.

### <a name="syntax"></a>구문

```
extent<_Rank>& operator++() restrict(amp,cpu);
extent<_Rank> operator++(int)restrict(amp,cpu);
```

### <a name="return-value"></a>반환 값

전위 연산자의 경우에 `extent` 개체 (`*this`). 접미사 연산자의 경우 새 `extent` 개체입니다.

##  <a name="operator_add_eq"></a> operator + =

'범위' 개체의 각 요소에 지정된 된 숫자를 추가합니다.

### <a name="syntax"></a>구문

```
extent<_Rank>& operator+=(const extent<_Rank>& _Rhs) restrict(amp,cpu);
extent<_Rank>& operator+=(const index<_Rank>& _Rhs) restrict(amp,cpu);
extent<_Rank>& operator+=(int _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Rhs*<br/>
번호, 인덱스 또는 범위 추가 합니다.

### <a name="return-value"></a>반환 값

결과 `extent` 개체입니다.

##  <a name="operator_min"></a> 연산자-

새로 만듭니다 `extent` 개체의 지정 된 각 요소를 빼서 `index` 이 해당 요소에서 개체 `extent` 개체입니다.

### <a name="syntax"></a>구문

```
extent<_Rank> operator-(const index<_Rank>& _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Rhs*<br/>
`index` 뺄 요소가 포함 된 개체입니다.

### <a name="return-value"></a>반환 값

새로운 `extent` 개체입니다.

##  <a name="operator_min_min"></a> operator-

감소 '범위' 개체의 각 요소입니다.

### <a name="syntax"></a>구문

```
extent<_Rank>& operator--() restrict(amp,cpu);
extent<_Rank> operator--(int)restrict(amp,cpu);
```

### <a name="return-value"></a>반환 값

전위 연산자의 경우에 `extent` 개체 (`*this`). 접미사 연산자의 경우 새 `extent` 개체입니다.

##  <a name="operator_div_eq"></a> operator / =

지정된 된 수 만큼 '범위' 개체의 각 요소를 나눕니다.

### <a name="syntax"></a>구문

```
extent<_Rank>& operator/=(int _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Rhs*<br/>
나눌 숫자입니다.

### <a name="return-value"></a>반환 값

`extent` 개체

##  <a name="operator_min_eq"></a> -= 연산자

'범위' 개체의 각 요소에서 지정된 된 숫자를 뺍니다.

### <a name="syntax"></a>구문

```
extent<_Rank>& operator-=(const extent<_Rank>& _Rhs) restrict(amp,cpu);
extent<_Rank>& operator-=(const index<_Rank>& _Rhs) restrict(amp,cpu);
extent<_Rank>& operator-=(int _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Rhs*<br/>
뺄 숫자입니다.

### <a name="return-value"></a>반환 값

결과 `extent` 개체입니다.

##  <a name="operator_eq"></a> operator=

다른 '범위' 개체의 내용을 여기로 복사합니다.

### <a name="syntax"></a>구문

```
extent<_Rank>& operator=(const extent<_Rank>& _Other) restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Other*<br/>
`extent` 복사할 개체입니다.

### <a name="return-value"></a>반환 값

이에 대 한 참조 `extent` 개체입니다.

##  <a name="operator_at"></a> extent:: operator \[\]

지정된 된 인덱스에 있는 요소를 반환 합니다.

### <a name="syntax"></a>구문

```
int operator[](unsigned int _Index) const restrict(amp,cpu);
int& operator[](unsigned int _Index) restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Index*<br/>
0에서 1 뺀 순위 까지의 정수입니다.

### <a name="return-value"></a>반환 값

지정된 된 인덱스에 있는 요소입니다.

##  <a name="rank_constant"></a> 순위

'범위' 개체의 차수를 저장 합니다.

### <a name="syntax"></a>구문

```
static const int rank = _Rank;
```

##  <a name="size"></a> 크기

`extent` 개체(요소의 단위에서)의 총 선형 크기 단위를 반환합니다.

### <a name="syntax"></a>구문

```
unsigned int size() const restrict(amp,cpu);
```

## <a name="tile"></a> 타일

지정 된 타일 크기를 사용 하 여 tiled_extent 개체를 생성합니다.

```
template <int _Dim0>
tiled_extent<_Dim0> tile() const ;

template <int _Dim0, int _Dim1>
tiled_extent<_Dim0, _Dim1> tile() const ;

template <int _Dim0, int _Dim1, int _Dim2>
tiled_extent<_Dim0, _Dim1, _Dim2> tile() const ;
```

### <a name="parameters"></a>매개 변수

*_Dim0*<br/>
텍스처 범위의 가장 중요 한 구성 요소입니다.
*_Dim1*<br/>
텍스처 범위의 다음-에-가장 중요 한 구성 요소입니다.
*_Dim2*<br/>
텍스처 범위의 가장 중요 하지 않은 구성 요소입니다.

## <a name="see-also"></a>참고자료

[Concurrency 네임스페이스(C++ AMP)](concurrency-namespace-cpp-amp.md)
