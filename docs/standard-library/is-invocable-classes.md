---
title: is_invocable, is_invocable_r, is_nothrow_invocable is_nothrow_invocable_r 클래스
ms.date: 02/21/2019
f1_keywords:
- type_traits/std::is_invocable
- type_traits/std::is_invocable_r
- type_traits/std::is_nothrow_invocable
- type_traits/std::is_nothrow_invocable_r
helpviewer_keywords:
- is_invocable class
- is_invocable
- is_invocable_r class
- is_invocable_r
- is_nothrow_invocable class
- is_nothrow_invocable
- is_nothrow_invocable_r class
- is_nothrow_invocable_r
ms.openlocfilehash: bb5e75a897029ded2e00e491d93d2df41a3e115b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62336233"
---
# <a name="isinvocable-isinvocabler-isnothrowinvocable-isnothrowinvocabler-classes"></a>is_invocable, is_invocable_r, is_nothrow_invocable is_nothrow_invocable_r 클래스

이러한 템플릿은 형식 지정된 된 인수 형식과 사용 하 여 호출 수를 결정 합니다. `is_invocable_r` 및 `is_nothrow_invocable_r` 도 호출의 결과 특정 형식으로 변환할 수 인지를 확인 합니다. `is_nothrow_invocable` 및 `is_nothrow_invocable_r` 결정 하는 경우 호출 것으로 알려진 예외를 throw 합니다. C + + 17에 추가 합니다.

## <a name="syntax"></a>구문

```cpp
template <class Callable, class... Args>
struct is_invocable;

template <class Convertible, class Callable, class... Args>
struct is_invocable_r;

template <class Callable, class... Args>
struct is_nothrow_invocable;

template <class Convertible, class Callable, class... Args>
struct is_nothrow_invocable_r;

// Helper templates
template <class Callable, class... Args>
inline constexpr bool is_invocable_v =
    std::is_invocable<Callable, Args...>::value;

template <class Convertible, class Callable, class... Args>
inline constexpr bool is_invocable_r_v =
    std::is_invocable_r<Convertible, Callable, Args...>::value;

template <class Callable, class... Args>
inline constexpr bool is_nothrow_invocable_v =
    std::is_nothrow_invocable<Callable, Args...>::value;

template <class Convertible, class Callable, class... Args>
inline constexpr bool is_nothrow_invocable_r_v =
    std::is_nothrow_invocable_r<Convertible, Callable, Args...>::value;
```

### <a name="parameters"></a>매개 변수

*호출 가능*<br/>
쿼리할 호출 가능 형식입니다.

*Args*<br/>
쿼리 인수 형식입니다.

*로 변환할 수 있는*<br/>
형식 결과의 *Callable* 변환할 수 있어야 합니다.

## <a name="remarks"></a>설명

합니다 `is_invocable` 형식 조건자 형태인 경우 true 호출 가능 형식 *Callable* 인수를 사용 하 여 호출할 수 있습니다 *Args* 확인 되지 않은 컨텍스트에서 합니다.

합니다 `is_invocable_r` 형식 조건자 형태인 경우 true 호출 가능 형식 *Callable* 인수를 사용 하 여 호출할 수 있습니다 *Args* 생성 한 결과 형식을 변환할 수 있는 확인 되지 않은 컨텍스트에서  *로 변환할 수 있는*합니다.

합니다 `is_nothrow_invocable` 형식 조건자 형태인 경우 true 호출 가능 형식 *Callable* 인수를 사용 하 여 호출할 수 있습니다 *Args* 에 확인 되지 않은 컨텍스트를 이러한 호출에서 예외가 throw 라고 합니다.

합니다 `is_nothrow_invocable_r` 형식 조건자 형태인 경우 true 호출 가능 형식 *Callable* 인수를 사용 하 여 호출할 수 있습니다 *Args* 생성 한 결과 형식을 변환할 수 있는 확인 되지 않은 컨텍스트에서  *로 변환할 수 있는*, 이러한 호출에서 예외가 throw 라고 하 고 있습니다.

각 유형의 *로 변환할 수 있는*, *Callable*, 및 매개 변수 팩의 유형에 *Args* 완전 한 형식, 범위를 알 수 없는, 배열 또는 cv 정규화 여야합니다**void**합니다. 그렇지 않으면 조건자의 동작이 정의 되지 않습니다.

## <a name="example"></a>예제

```cpp
// std__type_traits__is_invocable.cpp
// compile using: cl /EHsc /std:c++17 std__type_traits__is_invocable.cpp
#include <type_traits>

auto test1(int) noexcept -> int (*)()
{
    return nullptr;
}

auto test2(int) -> int (*)()
{
    return nullptr;
}

int main()
{
    static_assert( std::is_invocable<decltype(test1), short>::value );

    static_assert( std::is_invocable_r<int(*)(), decltype(test1), int>::value ); 
    static_assert( std::is_invocable_r<long(*)(), decltype(test1), int>::value ); // fails

    static_assert( std::is_nothrow_invocable<decltype(test1), int>::value );
    static_assert( std::is_nothrow_invocable<decltype(test2), int>::value ); // fails

    static_assert( std::is_nothrow_invocable_r<int(*)(), decltype(test1), int>::value );
    static_assert( std::is_nothrow_invocable_r<int(*)(), decltype(test2), int>::value ); // fails
}
```

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
[invoke](functional-functions.md#invoke)<br/>
