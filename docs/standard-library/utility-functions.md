---
title: '&lt;utility&gt; 함수'
ms.date: 11/04/2016
f1_keywords:
- utility/std::exchange
- utility/std::forward
- utility/std::make_pair
- utility/std::move
- utility/std::swap
ms.assetid: b1df38cd-3a59-4098-9c81-83342eb719a4
helpviewer_keywords:
- std::exchange [C++]
- std::forward [C++]
- std::make_pair [C++]
- std::move [C++]
- std::swap [C++]
ms.openlocfilehash: 723b077500b9b741445efcd8574fb26cd53e5fc7
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68246306"
---
# <a name="ltutilitygt-functions"></a>&lt;utility&gt; 함수

## <a name="asconst"></a> as_const

```cpp
template <class T> constexpr add_const_t<T>& as_const(T& t) noexcept;
template <class T> void as_const(const T&&) = delete;
```

### <a name="return-value"></a>반환 값

반환 *T*합니다.

## <a name="declval"></a> declval

```cpp
template <class T> add_rvalue_reference_t<T> declval() noexcept;  // as unevaluated operand
```

## <a name="exchange"></a> exchange

**(C++14)** 개체에 새 값을 할당하고 이전 값을 반환합니다.

```cpp
template <class T, class Other = T>
    T exchange(T& val, Other&& new_val)
```

### <a name="parameters"></a>매개 변수

*val*\
new_val의 값을 받는 개체입니다.

*new_val*\
값이 val로 복사되거나 이동되는 개체입니다.

### <a name="remarks"></a>설명

복합 형식에서 `exchange`는 이동 생성자를 사용할 수 있는 경우 이전 값의 복사를 방지하고, 임시 개체이거나 이동된 경우 새 값의 복사를 방지하며, 사용 가능한 변환 대입 연산자를 통해 모든 형식을 새 값으로 받아들입니다. Exchange 함수는 다른 [std::swap](../standard-library/algorithm-functions.md#swap) 는 왼쪽된 인수가 없거나 이동 오른쪽 인수에 복사 합니다.

### <a name="example"></a>예제

다음 예제에서는 `exchange`을 사용하는 방법을 보여 줍니다. 실제로 `exchange`는 복사하는 데 비용이 많이 드는 큰 개체에서 가장 유용합니다.

```cpp
#include <utility>
#include <iostream>

using namespace std;

struct C
{
   int i;
   //...
};

int main()
{
   // Use brace initialization
   C c1{ 1 };
   C c2{ 2 };
   C result = exchange(c1, c2);
   cout << "The old value of c1 is: " << result.i << endl;
   cout << "The new value of c1 after exchange is: " << c1.i << endl;

   return 0;
}
```

```Output
The old value of c1 is: 1
The new value of c1 after exchange is: 2
```

## <a name="forward"></a> 앞으로

인수가 rvalue 또는 rvalue 참조인 경우 rvalue 참조에 대한 해당 인수를 조건적으로 캐스팅합니다. 그러면 인수의 rvalue 특성이 전달 함수로 복원되어 완벽하게 전달됩니다.

```cpp
template <class Type>    // accepts lvalues
    constexpr Type&& forward(typename remove_reference<Type>::type& Arg) noexcept

template <class Type>    // accepts everything else
    constexpr Type&& forward(typename remove_reference<Type>::type&& Arg) noexcept
```

### <a name="parameters"></a>매개 변수

*형식*\
전달 된 값의 형식을 *Arg*의 형식과 다 수 있음 *Arg*합니다. 일반적으로 전달 함수의 템플릿 인수에 의해 결정됩니다.

*arg*\
캐스팅할 인수입니다.

### <a name="return-value"></a>반환 값

Rvalue 참조를 반환 *Arg* 값을 전달 하는 경우 *Arg* rvalue 또는 rvalue에 대 한 참조를 원래 그렇지 않으면 반환 *Arg* 해당 형식을 수정 하지 않고 있습니다.

### <a name="remarks"></a>설명

`forward`를 호출하려면 명시적 템플릿 인수를 지정해야 합니다.

`forward` 인수를 전달 하지 않습니다. 대신 원래 rvalue 또는 rvalue 참조였던 경우 해당 인수를 rvalue 참조에 조건적으로 캐스팅하면 `forward`를 사용하여 컴파일러에서 전달된 인수의 원래 형식을 알고 오버로드 해결을 수행할 수 있습니다. 전달 함수는 인수의 명백한 형식은 원래 형식과 다를 수 있습니다-예를 들어, rvalue 함수에 인수로 사용 하는 시점과 바인딩되는 매개 변수 이름 이름을 지정 하면 해당 값이 실제로 rvalue로 존재와 lvalue- `forward` 인수의 rvalue 특성을 복원 합니다.

오버 로드 확인을 수행 하는 인수의 원래 값의 rvalue 특성을 복원 하 라고 *완벽 전달*합니다. 완벽한 전달을 사용하면 템플릿 함수에서 참조 형식의 인수를 허용하고 올바른 오버로드 해결을 위해 필요할 때 rvalue 특성을 복원할 수 있습니다. 완벽한 전달을 수행하면 rvalue에 대해 이동 의미 체계를 보존하고 인수의 참조 형식만 다른 함수의 오버로드를 제공하지 않아도 됩니다.

## <a name="from_chars"></a> from_chars

```cpp
from_chars_result from_chars(const char* first, const char* last, see below& value, int base = 10);

from_chars_result from_chars(const char* first, const char* last, float& value, chars_format fmt = chars_format::general); 

from_chars_result from_chars(const char* first, const char* last, double& value, chars_format fmt = chars_format::general); 

from_chars_result from_chars(const char* first, const char* last, long double& value, chars_format fmt = chars_format::general);
```

## <a name="get"></a> get

인덱스 위치 또는 형식을 기준으로 `pair` 개체에서 요소를 가져옵니다.

```cpp
// get reference to element at Index in pair Pr
template <size_t Index, class T1, class T2>
    constexpr tuple_element_t<Index, pair<T1, T2>>&
    get(pair<T1, T2>& Pr) noexcept;

// get reference to element T1 in pair Pr
template <class T1, class T2>
    constexpr T1& get(pair<T1, T2>& Pr) noexcept;

// get reference to element T2 in pair Pr
template <class T2, class T1>
    constexpr T2& get(pair<T1, T2>& Pr) noexcept;

// get const reference to element at Index in pair Pr
template <size_t Index, class T1, class T2>
    constexpr const tuple_element_t<Index, pair<T1, T2>>&
    get(const pair<T1, T2>& Pr) noexcept;

// get const reference to element T1 in pair Pr
template <class T1, class T2>
    constexpr const T1& get(const pair<T1, T2>& Pr) noexcept;

// get const reference to element T2 in pair Pr
template <class T2, class T1>
    constexpr const T2& get(const pair<T1, T2>& Pr) noexcept;

// get rvalue reference to element at Index in pair Pr
template <size_t Index, class T1, class T2>
    constexpr tuple_element_t<Index, pair<T1, T2>>&&
    get(pair<T1, T2>&& Pr) noexcept;

// get rvalue reference to element T1 in pair Pr
template <class T1, class T2>
    constexpr T1&& get(pair<T1, T2>&& Pr) noexcept;

// get rvalue reference to element T2 in pair Pr
template <class T2, class T1>
    constexpr T2&& get(pair<T1, T2>&& Pr) noexcept;
```

### <a name="parameters"></a>매개 변수

*인덱스*\
선택한 요소의 0 기반 인덱스입니다.

*T1*\
첫 번째 pair 요소의 형식입니다.

*T2*\
두 번째 pair 요소의 형식입니다.

*pr*\
선택할 쌍입니다.

### <a name="remarks"></a>설명

각각의 템플릿 함수는 `pair` 인수의 요소에 대한 참조를 반환합니다.

인덱싱된 오버 로드에 대 한 경우 값 *인덱스* 함수를 반환 하는 0 `pr.first` 경우에 값 *인덱스* 함수를 반환 하는 1 `pr.second`합니다. `RI` 형식은 반환된 요소의 형식입니다.

인덱스 매개 변수가 없는 오버 로드에 대해 반환할 요소 형식 인수에 의해 추론 됩니다. 호출 `get<T>(Tuple)` 경우 컴파일러 오류가 생성 됩니다 *pr* 이상 있거나 없는 형식은 T 형식 요소가 두 개

### <a name="example"></a>예제

```cpp
#include <utility>
#include <iostream>
using namespace std;
int main()
{

    typedef pair<int, double> MyPair;

    MyPair c0(9, 3.14);

    // get elements by index
    cout << " " << get<0>(c0);
    cout << " " << get<1>(c0) << endl;

    // get elements by type (C++14)
    MyPair c1(1, 0.27);
    cout << " " << get<int>(c1);
    cout << " " << get<double>(c1) << endl;
}
```

```Output
9 3.14
1 0.27
```

## <a name="index_sequence"></a> index_sequence

```cpp
template<size_t... I>
    using index_sequence = integer_sequence<size_t, I...>;
```

## <a name="index_sequence_for"></a> index_sequence_for

```cpp
template<class... T>
    using index_sequence_for = make_index_sequence<sizeof...(T)>;
```

## <a name="make_index_sequence"></a> make_index_sequence

```cpp
template<size_t N>
    using make_index_sequence = make_integer_sequence<size_t, N>;
```

## <a name="make_integer_sequence"></a> make_integer_sequence

```cpp
template<class T, T N>
    using make_integer_sequence = integer_sequence<T, see below >;
```

## <a name="make_pair"></a> make_pair

`pair` 형식의 개체를 만드는 데 사용할 수 있는 템플릿 함수. 여기서 구성 요소 형식은 매개 변수로 전달된 데이터 형식을 기준으로 자동 선택됩니다.

```cpp
template <class T, class U>
    pair<T, U> make_pair(T& Val1, U& Val2);

template <class T, class U>
    pair<T, U> make_pair(T& Val1, U&& Val2);

template <class T, class U>
    pair<T, U> make_pair(T&& Val1, U& Val2);

template <class T, class U>
    pair<T, U> make_pair(T&& Val1, U&& Val2);
```

### <a name="parameters"></a>매개 변수

*Val1*\
`pair`의 첫 번째 요소를 초기화하는 값

*Val2*\
`pair`의 두 번째 요소를 초기화하는 값

### <a name="return-value"></a>반환 값

생성 된 쌍 개체: `pair` < `T`하십시오`U`> (`Val1`, `Val2`).

### <a name="remarks"></a>설명

`make_pair`는 [reference_wrapper Class](../standard-library/reference-wrapper-class.md) 형식의 개체를 참조 형식으로 변환하고 감소하는 배열 및 함수를 포인터로 변환합니다.

반환된 `pair` 개체에서 `T`은 다음과 같이 결정됩니다.

- 입력 형식 `T`이 `reference_wrapper<X>`인 경우 반환된 형식 `T`은 `X&`입니다.

- 그렇지 않은 경우, 반환된 형식 `T`은 `decay<T>::type`입니다. 하는 경우 [decay 클래스](../standard-library/decay-class.md) 지원 되지 않습니다 반환 되는 형식은 `T` 는 입력된 형식과 동일한 지 `T`합니다.

반환된 형식 `U`는 마찬가지로 입력 형식 `U`에서 결정됩니다.

장점은 `make_pair` 저장 되는 개체의 형식을 컴파일러에 의해 자동으로 결정 되 고 명시적으로 지정할 필요가 없습니다. 와 같은 명시적 템플릿 인수를 사용 하지 마세요 `make_pair<int, int>(1, 2)` 사용 하는 경우 `make_pair` 하기 때문에 자세한 컴파일 오류를 일으킬 수 있는 복잡 한 rvalue 참조 문제를 추가 합니다. 이 예제에서 올바른 구문은 `make_pair(1, 2)`입니다.

`make_pair` 도우미 함수도 입력 매개 변수로 한 쌍이 필요한 함수에 두 값을 전달할 수 있습니다.

### <a name="example"></a>예제

도우미 함수 `make_pair`를 사용하여 쌍을 선언하고 초기화하는 방법을 알아보려면 [pair 구조체](../standard-library/pair-structure.md)를 참조하세요.

## <a name="move"></a> 이동

무조건 인수를 rvalue 참조로 캐스트합니다. 따라서 형식이 이동 가능할 경우 이동 가능하다는 신호를 줍니다.

```cpp
template <class Type>
    constexpr typename remove_reference<Type>::type&& move(Type&& Arg) noexcept;
```

### <a name="parameters"></a>매개 변수

*형식*\
전달 된 인수 형식에서 추론 된 형식 *Arg*참조 축소 규칙과 함께 합니다.

*arg*\
캐스팅할 인수입니다. 하지만 유형의 *Arg* 는 rvalue 참조로 지정 되 `move` 도 lvalue 참조가 rvalue 참조에 바인딩할 수 있으므로 lvalue 인수를 허용 합니다.

### <a name="return-value"></a>반환 값

형식과 상관없이, rvalue 참조로서의 `Arg`는 참조 형식입니다.

### <a name="remarks"></a>설명

템플릿 인수 *형식* 명시적으로 지정할 수 있지만 전달 된 값의 형식에서 추론 해야 사용할 수 없습니다 *Arg*합니다. 유형의 *형식* 참조 축소 규칙에 따라 추가 조정 됩니다.

`move` 해당 인수를 이동 하지 않습니다. 무조건 인수를 캐스트 하 여 대신-lvalue 일 수 있는-에서 전달 된 값을 복사 하는 것이 아니라 있도록 이동할 이후에 컴파일러는 rvalue 참조로 *Arg* 해당 형식이 이동 가능할 경우. 해당 형식이 이동 가능할 아니면 대신 복사 됩니다.

값 전달 *Arg* 이 lvalue-즉, 여기에 이름 또는 해당 주소를 가져올 수 있습니다-이동이 발생 하면 무효화 됩니다. 전달 된 값을 참조 하지 마세요 *Arg* 이름이 나 주소를 이동한 후으로 합니다.

## <a name="moveif"></a> move_if_noexcept

```cpp
template <class T> constexpr conditional_t< !is_nothrow_move_constructible_v<T> && is_copy_constructible_v<T>, const T&, T&&> move_if_noexcept(T& x) noexcept;
```

## <a name="swap"></a> 교환

두 형식의 요소를 교환 하거나 [pair 구조체](../standard-library/pair-structure.md) 개체입니다.

```cpp
template <class T>
    void swap(T& left, T& right) noexcept(see below );
template <class T, size_t N>
    void swap(T (&left)[N], T (&right)[N]) noexcept(is_nothrow_swappable_v<T>);
template <class T, class U>
    void swap(pair<T, U>& left, pair<T, U>& right);
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
개체 형식 또는 형식의 `pair`합니다.

*오른쪽*\
개체 형식 또는 형식의 `pair`합니다.

### <a name="remarks"></a>설명

장점은 `swap` 저장 되는 개체의 형식을 컴파일러에 의해 자동으로 결정 되 고 명시적으로 지정할 필요가 없습니다. 와 같은 명시적 템플릿 인수를 사용 하지 마세요 `swap<int, int>(1, 2)` 사용 하는 경우 `swap` 하기 때문에 자세한 컴파일 오류를 일으킬 수 있는 복잡 한 rvalue 참조 문제를 추가 합니다.

## <a name="to_chars"></a> to_chars

```cpp
to_chars_result to_chars(char* first, char* last, see below value, int base = 10);
to_chars_result to_chars(char* first, char* last, float value); 
to_chars_result to_chars(char* first, char* last, double value); 
to_chars_result to_chars(char* first, char* last, long double value);
to_chars_result to_chars(char* first, char* last, float value, chars_format fmt); 
to_chars_result to_chars(char* first, char* last, double value, chars_format fmt); 
to_chars_result to_chars(char* first, char* last, long double value, chars_format fmt);
to_chars_result to_chars(char* first, char* last, float value, chars_format fmt, int precision); 
to_chars_result to_chars(char* first, char* last, double value, chars_format fmt, int precision); 
to_chars_result to_chars(char* first, char* last, long double value, chars_format fmt, int precision);
```

### <a name="remarks"></a>설명

값 범위를 입력 하 여 문자열로 변환 `[first, last)`여기서 `[first, last)` 유효한 범위를 해야 합니다.
