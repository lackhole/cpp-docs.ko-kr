---
title: 변형 클래스
ms.date: 04/04/2019
f1_keywords:
- variant/std::variant
- variant/std::variant::emplace
- variant/std::variant::index
- variant/std::variant::valueless_by_exception
helpviewer_keywords:
- variant/std::variant
- variant/std::variant::emplace
- variant/std::variant::index
- variant/std::variant::valueless_by_exception
ms.openlocfilehash: 9bfdf644374a0b825fd0ca02bf4164a766cb42a3
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68269305"
---
# <a name="variant-class"></a>변형 클래스

언제 든 지 변형의 인스턴스에도 해당 대체 형식 중 하나의 값을 보유 하거나 또는 값을 보유 합니다.

## <a name="syntax"></a>구문

```cpp
template <class... Types>
    class variant
```

## <a name="members"></a>멤버

### <a name="constructors"></a>생성자

|||
|-|-|
|[Variant](#variant)|`variant` 형식의 개체를 생성합니다.|

### <a name="functions"></a>함수

|||
|-|-|
|[emplace](#emplace)|새 포함 된 값을 만듭니다.|
|[index](#index)|포함 된 값의 인덱스를 반환합니다.|
|[swap](#swap)||
|[valueless_by_exception](#emplace)|반환 **false** 변형 값을 보유 하는 경우.|

### <a name="operators"></a>연산자

|||
|-|-|
|[operator=](#op_eq)|변형을 다른 변형의 복사본으로 바꿉니다.|

## <a name="emplace"></a> emplace

새 포함 된 값을 만듭니다.

```cpp
template <class T, class... Args>
    T& emplace(Args&&...);
template <class T, class U, class... Args>
    T& emplace(initializer_list<U>, Args&&...);
template <size_t I, class... Args>
    variant_alternative_t<I, variant<Types...>>& emplace(Args&&...);
template <size_t I, class U, class... Args>
    variant_alternative_t<I, variant<Types...>>& emplace(initializer_list<U>, Args&&...);
```

## <a name="index"></a> 인덱스

포함 된 값의 인덱스를 반환합니다.

```cpp
constexpr size_t index() const noexcept;
```

## <a name="variant"></a> Variant

`variant` 형식의 개체를 생성합니다. 소멸자가 포함 됩니다.

```cpp
constexpr variant() noexcept(see below);
variant(const variant&);
variant(variant&&) noexcept(see below);
template <class T>
    constexpr variant(T&&) noexcept(see below);
template <class T, class... Args>
    constexpr explicit variant(in_place_type_t<T>, Args&&...);
template <class T, class U, class... Args>
    constexpr explicit variant(in_place_type_t<T>, initializer_list<U>, Args&&...);
template <size_t I, class... Args>
    constexpr explicit variant(in_place_index_t<I>, Args&&...);
template <size_t I, class U, class... Args>
    constexpr explicit variant(in_place_index_t<I>, initializer_list<U>, Args&&...);

template <class Alloc>
    variant(allocator_arg_t, const Al&);
template <class Alloc>
    variant(allocator_arg_t, const Al&, const variant&);
template <class Alloc>
    variant(allocator_arg_t, const Al&, variant&&);
template <class Alloc, class T>
    variant(allocator_arg_t, const Al&, T&&);
template <class Alloc, class T, class... Args>
    variant(allocator_arg_t, const Al&, in_place_type_t<T>, Args&&...);
template <class Alloc, class T, class U, class... Args>
    variant(allocator_arg_t, const Al&, in_place_type_t<T>, initializer_list<U>, Args&&...);
template <class Alloc, size_t I, class... Args>
    variant(allocator_arg_t, const Al&, in_place_index_t<I>, Args&&...);
template <class Alloc, size_t I, class U, class... Args>
    variant(allocator_arg_t, const Al&, in_place_index_t<I>, initializer_list<U>, Args&&...);

~variant();
```

### <a name="parameters"></a>매개 변수

*Al*\
이 개체에 사용할 할당자 클래스입니다.

## <a name="op_eq"></a> 연산자 =

변형을 다른 변형의 복사본으로 바꿉니다.

```cpp
variant& operator=(const variant&);
variant& operator=(variant&&) noexcept(see below);
template <class T>
    variant& operator=(T&&) noexcept(see below);
```

## <a name="swap"></a> 교환

```cpp
void swap(variant&) noexcept(see below);
```

## <a name="valueless"></a> valueless_by_exception

반환 **false** 변형 값을 보유 하는 경우.

```cpp
constexpr bool valueless_by_exception() const noexcept;
```
