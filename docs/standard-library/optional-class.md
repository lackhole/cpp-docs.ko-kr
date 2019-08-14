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
ms.openlocfilehash: f664df6493a7ee20361d49531a930aeb810d3d2a
ms.sourcegitcommit: 16c0392fc8d96e814c3a40b0c5346d7389aeb525
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/12/2019
ms.locfileid: "68957154"
---
# <a name="optional-class"></a>선택적 클래스

템플릿 클래스 `optional<T>` 는 *포함 된 값*이라고 하는 형식의 `T`값을 포함 하거나 포함 하지 않을 수 있는 개체를 설명 합니다.

인스턴스에 `optional<T>` 값이 포함 된 경우 포함 된 값은 형식 `T`에 대해 적절 하 게 정렬 된 `optional` 지역에서 개체의 저장소 내에 할당 됩니다. 가로 `bool`변환 되 면 개체에 값이 `true` `false`포함 되어 있으면이 고, 그렇지 않으면입니다. `optional<T>`

포함 된 개체 형식은 `T` [in_place_t](in-place-t-struct.md) 또는 [nullopt_t](nullopt-t-structure.md)이 아니어야 합니다. `T`*소멸 가능한*이어야 합니다. 즉, 해당 소멸자는 소유 된 모든 리소스를 회수 해야 하며 예외를 throw 하지 않을 수 있습니다.

클래스 `optional` 는 c + + 17의 새로운 클래스입니다.

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
| **생성자 및 소멸자** | |
|[optional](#optional) | `optional` 형식의 개체를 생성합니다. |
|[~ 선택 사항](#optional-destructor) | 형식의 `optional`개체를 소멸 시킵니다. |
| **할당** | |
| [operator=](#op_eq) | 를 `optional` 다른`optional`의 복사본으로 바꿉니다. |
| [emplace](#op_eq) | 지정 된 인수를 사용 하 여 포함 된 값을 초기화 합니다. |
| **Swap** | |
| [swap](#swap) | 포함 된 값 이나 빈 상태를 다른 `optional`값으로 바꿉니다. |
| **관찰자** | |
| [has_value](#has_value) | `optional` 개체에 값이 포함 되어 있는지 여부를 반환 합니다. |
| [value](#value) | 포함 된 값을 반환 합니다. |
| [value_or](#value_or) | 포함 된 값을 반환 하거나, 값이 없는 경우 대체 값을 반환 합니다. |
| [operator->](#op_as) | `optional` 개체의 포함 된 값을 참조 합니다. |
| [operator*](#op_mem) | `optional` 개체의 포함 된 값을 참조 합니다. |
| [operator bool](#op_bool) | `optional` 개체에 값이 포함 되어 있는지 여부를 반환 합니다. |
| **한정자** | |
| [reset](#reset) | 포함 된 `optional` 값을 삭제 하 여를 다시 설정 합니다. |

## <a name="has_value"></a>has_value

```cpp
constexpr bool has_value() const noexcept;
```

## <a name="optional"></a>선택적 생성자

`optional` 형식의 개체를 생성합니다.

```cpp
constexpr optional() noexcept;
constexpr optional(nullopt_t nullopt) noexcept;
constexpr optional(const optional& rhs);
constexpr optional(optional&& rhs) noexcept;

template <class... Args>
constexpr explicit optional(in_place_t, Args&&... args);

template <class U, class... Args>
constexpr explicit optional(in_place_t, initializer_list<U> i_list, Args&&... args);

template <class U = T>
explicit constexpr optional(U&& rhs);

template <class U>
explicit optional(const optional<U>& rhs);

template <class U>
explicit optional(optional<U>&& rhs);
```

### <a name="parameters"></a>매개 변수

*rhs*\
`optional` 복사 하거나 이동할에서 포함 된 값을 생성할입니다.

*i_list*\
포함 된 값을 생성할 이니셜라이저 목록입니다.

*args*\
포함 된 값을 생성 하는 인수 목록입니다.

### <a name="remarks"></a>설명

`constexpr optional() noexcept;`
`constexpr optional(nullopt_t nullopt) noexcept;`이러한 생성자는 값 `optional` 을 포함 하지 않는을 생성 합니다.

`constexpr optional(const optional& rhs);`Copy 생성자는 인수의 포함 된 값에서 포함 된 값을 초기화 합니다. 가 true가 `is_copy_constructible_v<T>` 아니면 **삭제** 된 것으로 정의 되 고가 true 인 `is_trivially_copy_constructible_v<T>` 경우 trivial입니다.

`constexpr optional(optional&& rhs) noexcept;`이동 생성자는 인수의 포함 된 값에서 이동 하 여 포함 된 값을 초기화 합니다. 이 true 인 경우를 제외 `is_move_constructible_v<T>` 하 고는 오버 로드 확인에 참여 하지 않으며,가 true 인 경우 `is_trivially_move_constructible_v<T>` trivial입니다.

`template <class... Args> constexpr explicit optional(in_place_t, Args&&... args);`직접 인수 `std::forward<Args>(args)`를 사용 하는 경우에 포함 된 값을 초기화 합니다. 이 생성자는 `constexpr` 사용 된생성자`T` 가 인 경우입니다 `constexpr`. 가 true가 아닌 경우 `is_constructible_v<T, Args...>` 오버 로드 확인에 참여 하지 않습니다.

`template <class U, class... Args> constexpr explicit optional(in_place_t, initializer_list<U> i_list, Args&&... args);`직접 인수 `i_list, std::forward<Args>(args)`를 사용 하는 경우에 포함 된 값을 초기화 합니다. 이 생성자는 `constexpr` 사용 된생성자`T` 가 인 경우입니다 `constexpr`. 가 true가 아닌 경우 `is_constructible_v<T, initializer_list<U>&, Args&&...>` 오버 로드 확인에 참여 하지 않습니다.

`template <class U = T> explicit constexpr optional(U&& rhs);`를 사용 하 `std::forward<U>(v)`는 경우에는 포함 된 값을 직접 초기화 합니다. 이 생성자는 `constexpr` 사용 된생성자`T` 가 인 경우입니다 `constexpr`. 이 true이 고 `is_constructible_v<T, U&&>` `is_same_v<remove_cvref_t<U>, in_place_t>` 및 `is_same_v<remove_cvref_t<U>, optional>` 가 false가 아닌 경우 오버 로드 확인에 참여 하지 않습니다.

`template <class U> explicit optional(const optional<U>& rhs);`*Rhs* 에 값이 포함 된 경우 직접 인수의 포함 된 값에서 포함 된 값을 초기화 합니다. `is_constructible_v<T, const U&>` 가 true `is_constructible_v<T, const optional<U>&&>` `is_constructible_v<T, optional<U>&>` 가아니면`is_convertible_v<const optional<U>&&, T>` ,,,,,, 및가 모두 false 인 경우를 제외 하 고는 오버 로드 확인에 참여 하지 않습니다. `is_constructible_v<T, optional<U>&&>` `is_constructible_v<T, const optional<U>&>` `is_convertible_v<optional<U>&, T>` `is_convertible_v<optional<U>&&, T>` `is_convertible_v<const optional<U>&, T>`

`template <class U> explicit optional(optional<U>&& rhs);`*Rhs* 에 값이 포함 된 경우를 사용 하 `std::move(*rhs)`는 것 처럼 직접 포함 된 값을 초기화 합니다. `is_constructible_v<T, U&&>` 가 true `is_constructible_v<T, const optional<U>&&>` `is_constructible_v<T, optional<U>&>` 가아니면`is_convertible_v<const optional<U>&&, T>` ,,,,,, 및가 모두 false 인 경우를 제외 하 고는 오버 로드 확인에 참여 하지 않습니다. `is_constructible_v<T, optional<U>&&>` `is_constructible_v<T, const optional<U>&>` `is_convertible_v<optional<U>&, T>` `is_convertible_v<optional<U>&&, T>` `is_convertible_v<const optional<U>&, T>`

## <a name="optional-destructor"></a>~ 선택적 소멸자

소멸자를 호출 하 여 일반적으로 소멸 가능한 포함 된 값 (있는 경우)을 모두 소멸 합니다.

```cpp
~optional();
```

### <a name="remarks"></a>설명

가 `T` 일반적으로 소멸 가능한 `optional<T>` 이면도 일반적으로 소멸 가능한입니다.

## <a name="op_eq"></a>연산자 =

의 `optional` 포함 된 값을 복사 하거나 다른 포함 된 값에서 다른 `optional` 위치로 바꿉니다.

```cpp
optional& operator=(nullopt_t) noexcept;
optional& operator=(const optional& rhs);
optional& operator=(optional&&) noexcept( /* see below */ );

template <class U = T>
    optional& operator=(U&&);

template <class U>
optional& operator=(const optional<U>&);

template <class U>
    optional& operator=(optional<U>&&);

template <class... Args>
T& emplace(Args&&...);

template <class U, class... Args>
T& emplace(initializer_list<U>, Args&&...);
```

## <a name="op_as"></a>연산자->

`optional` 개체의 포함 된 값을 역참조 합니다.

```cpp
constexpr const T* operator->() const;
constexpr T* operator->();
```

## <a name="op_mem"></a>연산자

`optional` 개체의 포함 된 값을 역참조 합니다.

```cpp
constexpr const T& operator*() const&;
constexpr T& operator*() &;
constexpr T&& operator*() &&;
constexpr const T&& operator*() const&&;
```

## <a name="op_bool"></a>연산자 bool

`optional` 개체에 포함 된 값이 있는지 여부를 보고 합니다.

```cpp
constexpr explicit operator bool() const noexcept;
```

## <a name="reset"></a>다시 설정

효과적으로는 포함 된 개체 (있는 경우)의 소멸자를 호출 하 고이를 초기화 되지 않은 상태로 설정 합니다.

```cpp
void reset() noexcept;
```

## <a name="swap"></a>스왑을

```cpp
template<class T>
void swap(optional<T>&, optional<T>&) noexcept;
```

## <a name="value"></a>기본값

```cpp
constexpr const T& value() const&;
constexpr T& value() &;
constexpr T&& value() &&;
constexpr const T&& value() const&&;
```

## <a name="value_or"></a>value_or

```cpp
template <class U>
    constexpr T value_or(U&&) const&;
template <class U>
    constexpr T value_or(U&&) &&;
```

## <a name="see-also"></a>참고자료

[\<선택적 >](optional.md)
