---
title: '&lt;tuple&gt; 함수'
ms.date: 11/04/2016
f1_keywords:
- tuple/std::get
- tuple/std::make_tuple
- tuple/std::tie
ms.assetid: bc6be38f-5258-4c14-b81b-63caa335fd44
helpviewer_keywords:
- std::get [C++]
- std::make_tuple [C++]
- std::tie [C++]
- std::get [C++]
- std::make_tuple [C++]
- std::tie [C++]
ms.openlocfilehash: 93c11a89f7cdfa3949be2d97e401fad199a17d97
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62278972"
---
# <a name="lttuplegt-functions"></a>&lt;tuple&gt; 함수

||||
|-|-|-|
|[get](#get)|[make_tuple](#make_tuple)|[tie](#tie)|

## <a name="get"></a>  get

인덱스 또는 형식(C++14)을 기준으로 `tuple` 개체에서 요소를 가져옵니다.

```cpp
// by index:
// get reference to Index element of tuple
template <size_t Index, class... Types>
   constexpr tuple_element_t<Index, tuple<Types...>>& get(tuple<Types...>& Tuple) noexcept;

// get const reference to Index element of tuple
template <size_t Index, class... Types>
   constexpr const tuple_element_t<Index, tuple<Types...>>& get(const tuple<Types...>& Tuple) noexcept;

// get rvalue reference to Index element of tuple
template <size_t Index, class... Types>
   constexpr tuple_element_t<Index, tuple<Types...>>&& get(tuple<Types...>&& Tuple) noexcept;

// (C++14) by type:
// get reference to T element of tuple
template <class T, class... Types>
   constexpr T& get(tuple<Types...>& Tuple) noexcept;

// get const reference to T element of tuple
template <class T, class... Types>
   constexpr const T& get(const tuple<Types...>& Tuple) noexcept;

// get rvalue reference to T element of tuple
template <class T, class... Types>
   constexpr T&& get(tuple<Types...>&& Tuple) noexcept;
```

### <a name="parameters"></a>매개 변수

*Index*<br/>
가져올 요소의 인덱스입니다.

*유형*<br/>
튜플에서 선언된 형식의 시퀀스로, 선언 순서대로 나열됩니다.

*T*<br/>
가져올 요소의 형식입니다.

*Tuple*<br/>
임의의 수의 요소가 포함된 std::tuple입니다.

### <a name="remarks"></a>설명

인덱스에 있는 값에 대 한 참조를 반환 하는 템플릿 함수 *인덱스*, 또는 형식의 *T* 에 `tuple` 개체입니다.

`get<T>(Tuple)` 을 호출할 때 튜플에 T 형식의 요소가 두 개 이상 있거나 없는 경우 컴파일러 오류가 생성됩니다.

### <a name="example"></a>예제

```cpp
#include <tuple>
#include <iostream>
#include <string>

using namespace std;

int main() {
    tuple<int, double, string> tup(0, 1.42, "Call me Tuple");

    // get elements by index
    cout << " " << get<0>(tup);
    cout << " " << get<1>(tup);
    cout << " " << get<2>(tup) << endl;

    // get elements by type
    cout << " " << get<int>(tup);
    cout << " " << get<double>(tup);
    cout << " " << get<string>(tup) << endl;
}
```

```Output
0 1.42 Call me Tuple
0 1.42 Call me Tuple
```

## <a name="make_tuple"></a>  make_tuple

요소 값에서 `tuple`을 만듭니다.

```cpp
template <class T1, class T2, ..., class TN>
   tuple<V1, V2, ..., VN> make_tuple(const T1& t1, const T2& t2, ..., const TN& tN);
```

### <a name="parameters"></a>매개 변수

*TN*<br/>
Nth 함수 매개 변수의 형식입니다.

*tN*<br/>
Nth 함수 매개 변수의 값입니다.

### <a name="remarks"></a>설명

템플릿 함수는 `tuple<V1, V2, ..., VN>(t1, t2, ..., tN)`을 반환합니다. 여기서 각 `Vi` 형식은 해당하는 `Ti` 형식이 `cv` `reference_wrapper<X>`이면 `X&`이고 그렇지 않으면 `Ti`입니다.

`make_tuple`의 장점 하나는 저장되는 개체 형식이 컴파일러에서 자동으로 저장되며 명시적으로 지정하지 않아도 된다는 점입니다. `make_tuple<int, int>(1, 2)`를 사용할 경우 불필요하게 장황해지고 컴파일 문제의 원인이 될 수 있는 복잡한 rvalue 참조 문제만 더해지므로 `make_tuple` 등의 명시적 템플릿 인수를 사용하지 마십시오.

### <a name="example"></a>예제

```cpp
// std__tuple__make_tuple.cpp
// compile by using: /EHsc
#include <tuple>
#include <iostream>

typedef std::tuple<int, double, int, double> Mytuple;
int main() {
    Mytuple c0(0, 1, 2, 3);

// display contents " 0 1 2 3"
    std::cout << std::get<0>(c0) << " ";
    std::cout << std::get<1>(c0) << " ";
    std::cout << std::get<2>(c0) << " ";
    std::cout << std::get<3>(c0) << std::endl;

    c0 = std::make_tuple(4, 5, 6, 7);

// display contents " 4 5 6 7"
    std::cout << std::get<0>(c0) << " ";
    std::cout << std::get<1>(c0) << " ";
    std::cout << std::get<2>(c0) << " ";
    std::cout << std::get<3>(c0) << std::endl;

    return (0);
}
```

```Output
0 1 2 3
4 5 6 7
```

## <a name="tie"></a>  tie

요소 선언에서 `tuple`을 만듭니다.

```cpp
template <class T1, class T2, ..., class TN>
tuple<T1&, T2&, ..., TN&> tie(T1& t1, T2& t2, ..., TN& tN);
```

### <a name="parameters"></a>매개 변수

*TN*<br/>
N번째 튜플 요소의 기본 형식입니다.

### <a name="remarks"></a>설명

템플릿 함수가 `tuple<T1&, T2&, ..., TN&>(t1, t2, ..., tN)`을 반환합니다.

### <a name="example"></a>예제

```cpp
// std__tuple__tie.cpp
// compile with: /EHsc
#include <tuple>
#include <iostream>

typedef std::tuple<int, double, int, double> Mytuple;
int main() {
    Mytuple c0(0, 1, 2, 3);

// display contents " 0 1 2 3"
    std::cout << " " << std::get<0>(c0);
    std::cout << " " << std::get<1>(c0);
    std::cout << " " << std::get<2>(c0);
    std::cout << " " << std::get<3>(c0);
    std::cout << std::endl;

    int v4 = 4;
    double v5 = 5;
    int v6 = 6;
    double v7 = 7;
    std::tie(v4, v5, v6, v7) = c0;

// display contents " 0 1 2 3"
    std::cout << " " << v4;
    std::cout << " " << v5;
    std::cout << " " << v6;
    std::cout << " " << v7;
    std::cout << std::endl;

    return (0);
}
```

```Output
0 1 2 3
0 1 2 3
```

## <a name="see-also"></a>참고자료

[\<tuple>](../standard-library/tuple.md)<br/>
