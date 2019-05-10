---
title: writeonly_texture_view 클래스
ms.date: 11/04/2016
f1_keywords:
- writeonly_texture_view
- AMP_GRAPHICS/writeonly_texture_view
- AMP_GRAPHICS/Concurrency::graphics::writeonly_texture_view
- AMP_GRAPHICS/Concurrency::graphics::writeonly_texture_view::set
- AMP_GRAPHICS/Concurrency::graphics::rank Constant
ms.assetid: 8d117ad3-0a1c-41ae-b29c-7c95fdd4d04d
ms.openlocfilehash: 5244ae5df99b06c77f4eb27317e5829b21fabf24
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405419"
---
# <a name="writeonlytextureview-class"></a>writeonly_texture_view 클래스

질감에 대 한 writeonly 액세스를 제공합니다.

## <a name="syntax"></a>구문

```
template <
    typename value_type,
    int _Rank
>
class writeonly_texture_view;

template <
    typename value_type,
    int _Rank
>
class writeonly_texture_view<value_type, _Rank> : public details::_Texture_base<value_type, _Rank>;
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
|`scalar_type`||
|`value_type`|질감의 요소 형식입니다.|

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[writeonly_texture_view 생성자](#ctor)|`writeonly_texture_view` 클래스의 새 인스턴스를 초기화합니다.|
|[~ writeonly_texture_view 소멸자](#ctor)|제거 된 `writeonly_texture_view` 개체입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[set](#set)|지정된 된 인덱스에 요소 값을 설정합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[operator=](#operator_eq)|복사 된 `writeonly_texture_view` 여기에 개체입니다.|

### <a name="public-constants"></a>공용 상수

|이름|설명|
|----------|-----------------|
|[rank 상수](#rank)|차수를 가져옵니다는 `writeonly_texture_view` 개체입니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`_Texture_base`

`writeonly_texture_view`

## <a name="requirements"></a>요구 사항

**헤더:** amp_graphics.h

**네임스페이스:** Concurrency:: graphics

##  <a name="dtor"></a> ~writeonly_texture_view

제거 된 `writeonly_texture_view` 개체입니다.

```
~writeonly_texture_view() restrict(amp,cpu);
```

##  <a name="operator_eq"></a> operator=

복사 된 `writeonly_texture_view` 여기에 개체입니다.

```
writeonly_texture_view<value_type, _Rank>& operator= (
    const writeonly_texture_view<value_type, _Rank>& _Other) restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Other*<br/>
`writeonly_texture_view` 복사할 개체입니다.

### <a name="return-value"></a>반환 값

이에 대 한 참조 `writeonly_texture_view` 개체입니다.

##  <a name="rank"></a> 순위

차수를 가져옵니다는 `writeonly_texture_view` 개체입니다.

```
static const int rank = _Rank;
```

##  <a name="set"></a> 설정

지정된 된 인덱스에 요소 값을 설정합니다.

```
void set(
    const index<_Rank>& _Index,
    const value_type& value) const restrict(amp);
```

### <a name="parameters"></a>매개 변수

*_Index*<br/>
요소의 인덱스입니다.

*값*<br/>
요소의 새 값입니다.

##  <a name="ctor"></a> writeonly_texture_view

`writeonly_texture_view` 클래스의 새 인스턴스를 초기화합니다.

```
writeonly_texture_view(
    texture<value_type,
    _Rank>& _Src) restrict(amp);

writeonly_texture_view(
    const writeonly_texture_view<value_type,
    _Rank>& _Src) restrict(amp,cpu);
```

### <a name="parameters"></a>매개 변수

*_Rank*<br/>
질감의 순위입니다.

*value_type*<br/>
질감의 요소 형식입니다.

*_Src*<br/>
`writeonly_texture_view`를 만드는 데 사용되는 질감입니다.

## <a name="see-also"></a>참고자료

[Concurrency::graphics 네임스페이스](concurrency-graphics-namespace.md)
