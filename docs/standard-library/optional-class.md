---
title: 선택적 클래스
ms.date: 11/04/2016
f1_keywords:
- optional/std::optional
- optional/std::optional::has_value
- optional/std::optional::reset
- optional/std::optional::value
- optional/std::optional::value_or
helpviewer_keywords:
- optional/std::optional
- optional/std::optional::has_value
- optional/std::optional::reset
- optional/std::optional::value
- optional/std::optional::value_or
ms.assetid: 89a3b805-ab60-4858-b772-5855130c11b1
ms.openlocfilehash: 414b3e608e915ec06dbdf90726151a1c33ea4c60
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68269205"
---
# <a name="optional-class"></a>선택적 클래스

값이 포함 되지 않을 수 있습니다 하거나 않을 수 있는 개체를 설명 합니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
class optional
{
    using value_type = T;
};

template<class T> optional(T) -> optional<T>;
```

## <a name="members"></a>멤버

### <a name="constructors"></a>생성자

|||
|-|-|
|[optional](#optional)|`optional` 형식의 개체를 생성합니다.|

### <a name="functions"></a>함수

|||
|-|-|
|[has_value](#has_value)|반환 **true** 경우 `optional` 값을 포함 합니다.|
|[reset](#reset)|다시 설정 된 `optional`합니다.|
|[value](#value)|평가 `optional` 값입니다.|
|[value_or](#value_or)|평가 `optional` 값입니다.|

### <a name="operators"></a>연산자

|||
|-|-|
|[operator=](#op_eq)|대체는 `optional` 의 다른 복사본으로 `optional`입니다.|
|[operator->](#op_as)|값을 할당할 `optional`합니다.|
|[operator*](#op_mem)|메모리의 참조 `optional`합니다.|
|[operator bool](#op_bool)|부울 반환 `optional` 값입니다.|

### <a name="has_value"></a> has_value

```cpp
constexpr bool has_value() const noexcept;
```

### <a name="optional"></a> 선택 사항

`optional` 형식의 개체를 생성합니다. 소멸자가 포함 됩니다.

```cpp
constexpr optional() noexcept;
constexpr optional(nullopt_t) noexcept;
constexpr optional(const optional&);
constexpr optional(optional&&) noexcept(see below);

template <class... Args>
    constexpr explicit optional(in_place_t, Args&&...);
template <class U, class... Args>
    constexpr explicit optional(in_place_t, initializer_list<U>, Args&&...);
template <class U = T>
    explicit constexpr optional(U&&);
template <class U>
    explicit optional(const optional<U>&);
template <class U>
    explicit optional(optional<U>&&);

~optional();
```

### <a name="op_eq"></a> 연산자 =

대체는 `optional` 의 다른 복사본으로 `optional`입니다.

```cpp
optional& operator=(nullopt_t) noexcept;
optional& operator=(const optional&);
optional& operator=(optional&&) noexcept(see below);

template <class U = T>
    optional& operator=(U&&); template <class U> optional& operator=(const optional<U>&);
template <class U>
    optional& operator=(optional<U>&&); template <class... Args> T& emplace(Args&&...);
template <class U, class... Args>
    T& emplace(initializer_list<U>, Args&&...);
```

### <a name="op_as"></a> operator->

```cpp
constexpr const T* operator->() const;
constexpr T* operator->();
```

### <a name="op_mem"></a> 연산자 *

```cpp
constexpr const T& operator*() const&;
constexpr T& operator*() &;
constexpr T&& operator*() &&;
constexpr const T&& operator*() const&&;
```

### <a name="op_bool"></a> 연산자 bool

```cpp
constexpr explicit operator bool() const noexcept;
```

### <a name="reset"></a> 다시 설정

```cpp
void reset() noexcept;
```

### <a name="value"></a> 값

```cpp
constexpr const T& value() const&;
constexpr T& value() &;
constexpr T&& value() &&;
constexpr const T&& value() const&&;
```

### <a name="value_or"></a> value_or

```cpp
template <class U>
    constexpr T value_or(U&&) const&;
template <class U>
    constexpr T value_or(U&&) &&;
```
