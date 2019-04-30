---
title: '&lt;string_view&gt; 연산자'
ms.date: 04/19/2019
f1_keywords:
- xstring/basic_string_view::operator!=
- xstring/basic_string_view::operator&gt;
- xstring/basic_string_view::operator&gt;=
- xstring/basic_string_view::operator&lt;
- xstring/basic_string_view::operator&lt;&lt;
- xstring/basic_string_view::operator&lt;=
- xstring/basic_string_view::operator+
- xstring/basic_string_view::operator==
helpviewer_keywords:
- std::basic_string_view::operator!=
- std::basic_string_view::operator&gt;
- std::basic_string_view::operator&gt;=
- std::basic_string_view::operator&lt;
- std::basic_string_view::operator&lt;&lt;
- std::basic_string_view::operator&lt;=, std::basic_string_view::operator==
ms.openlocfilehash: 1fbb7faf7d6fc92a053c0f4d47575c5c53c7968e
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346921"
---
# <a name="ltstringviewgt-operators"></a>&lt;string_view&gt; 연산자

이러한 연산자를 사용 하 여 두 string_view 개체 또는 string_view 및 다른 문자열 개체나 비교할 (예를 들어 [std:: string](basic-string-class.md), 또는 **char\***) 변환 하는 암시적 변환을 제공 하는 대 한 합니다. 

||||
|-|-|-|
|[operator!=](#op_neq)|[operator&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|
|[operator&lt;](#op_lt)|[operator&lt;&lt;](#op_lt_lt)|[operator&lt;=](#op_lt_eq)|
|[연산자==](#op_eq_eq)|[operator""sv](#op_sv)|

## <a name="op_neq"></a> operator!=

연산자의 좌변에 있는 개체가 우변에 있는 개체와 같지 않은지 테스트합니다.

```cpp
template <class CharType, class Traits>
bool operator!=(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator!=(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator!=(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>매개 변수

*left*<br/>
형식의 개체 또는 모든 변환할 수 있는 문자열 형식을 `basic_string_view` 비교 합니다.

*right*<br/>
형식의 개체 또는 모든 변환할 수 있는 문자열 형식을 `basic_string_view` 비교 합니다.

### <a name="return-value"></a>반환 값

**true 이면** 연산자의 좌 변에 있는 개체가 없는 경우 사전순으로 오른쪽에 있는 개체와 같지 않으면 **false**합니다.

### <a name="remarks"></a>설명

암시적 변환이 있어야 *convertible_string_type* 반대쪽 string_view에 있습니다. 

비교 기반을 쌍으로 문자 시퀀스의 사전순으로 비교 합니다. 요소 수가 같고 요소가 모두 같은 두 개체가 같습니다. 그렇지 않으면 목록은 같지 않은 것입니다.

## <a name="op_eq_eq"></a> operator==

연산자의 좌변에 있는 개체가 우변에 있는 개체와 같은지 테스트합니다.

```cpp
template <class CharType, class Traits>
bool operator==(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator==(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator==(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>매개 변수

*left*<br/>
형식의 개체 또는 모든 변환할 수 있는 문자열 형식을 `basic_string_view` 비교 합니다.

*right*<br/>
형식의 개체 또는 모든 변환할 수 있는 문자열 형식을 `basic_string_view` 비교 합니다.

### <a name="return-value"></a>반환 값

**true 이면** 어휘가 우변에 있는 개체와 같지 않으면 연산자의 좌 변에 있는 개체가 있으면 **false**합니다.

### <a name="remarks"></a>설명

암시적 변환이 있어야 *convertible_string_type* 반대쪽 string_view에 있습니다. 

비교 기반을 쌍으로 문자 시퀀스의 사전순으로 비교 합니다. 요소 수가 같고 요소가 모두 같은 두 개체가 같습니다.


## <a name="op_lt"></a> 연산자&lt;

연산자의 좌 변에 있는 개체가 오른쪽 sidestring_view에 개체 보다 작은지 여부를 테스트
```cpp
template <class CharType, class Traits>
bool operator<(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator<(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator<(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>매개 변수

*left*<br/>
형식의 개체 또는 모든 변환할 수 있는 문자열 형식을 `basic_string_view` 비교 합니다.

*right*<br/>
형식의 개체 또는 모든 변환할 수 있는 문자열 형식을 `basic_string_view` 비교 합니다.

### <a name="return-value"></a>반환 값

**true 이면** 연산자의 좌 변에 있는 개체가 우변; 개체 보다 사전 순으로 작은 경우이 고, 그렇지 **false**합니다.

### <a name="remarks"></a>설명

암시적 변환이 있어야 *convertible_string_type* 반대쪽 string_view에 있습니다. 

비교 기반을 쌍으로 문자 시퀀스의 사전순으로 비교 합니다. 같지 않은 첫 번째 문자 쌍 발생 하면 해당 비교 결과가 반환 됩니다. 같지 않은 문자가 발견 되 면 하나의 시퀀스가 더 짧으면 하지만 짧은 시퀀스가 작습니다 보다 깁니다. 즉, "고양이"을 사용 하면 고양이 보다 작습니다.

### <a name="example"></a>예제

```cpp
#include <string>
#include <string_view>

using namespace std;

int main()
{
    string_view sv1 { "ABA" };
    string_view sv2{ "ABAC" };
    string_view sv3{ "ABAD" };
    string_view sv4{ "ABACE" };

    bool result = sv2 > sv1; // true
    result = sv3 > sv2; // true
    result = sv3 != sv1; // true
    result = sv4 < sv3; // true because `C` < `D`
}
```

## <a name="op_lt_eq"></a> 연산자&lt;=

연산자의 좌변에 있는 개체가 우변에 있는 개체보다 작거나 같은지 테스트합니다.

```cpp
template <class CharType, class Traits>
bool operator<=(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator<=(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator<=(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>매개 변수

*left*<br/>
형식의 개체 또는 모든 변환할 수 있는 문자열 형식을 `basic_string_view` 비교 합니다.

*right*<br/>
형식의 개체 또는 모든 변환할 수 있는 문자열 형식을 `basic_string_view` 비교 합니다.

### <a name="return-value"></a>반환 값

**true 이면** 연산자의 좌 변에 있는 개체가 사전 순으로 작은 보다 또는 오른쪽에 있는 개체와 같으면이 고 그렇지 않으면 **false**합니다.

### <a name="remarks"></a>설명

참조 [연산자&lt;](#op_lt)합니다.

## <a name="op_lt_lt"></a> 연산자&lt;&lt;

string_view 출력 스트림에 씁니다.

```cpp
template <class CharType, class Traits>
inline basic_ostream<CharType, Traits>& operator<<(
    basic_ostream<CharType, Traits>& Ostr, const basic_string_view<CharType, Traits> Str);
```

### <a name="parameters"></a>매개 변수

*Ostr*<br/>
에 기록 되는 출력 스트림.

*Str*<br/>
출력 스트림에 입력할 string_view 합니다.

### <a name="return-value"></a>반환 값

에 기록 되는 출력 스트림.

### <a name="remarks"></a>설명

이 연산자를 사용 하 여 사용 하 여 예를 들어 출력 스트림으로 string_view의 콘텐츠를 삽입할 [std:: cout](iostream.md#cout)합니다.

## <a name="op_gt"></a> 연산자&gt;

연산자의 좌변에 있는 개체가 우변에 있는 개체보다 큰지 테스트합니다.

```cpp
template <class CharType, class Traits>
bool operator>(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator>(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator>(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>매개 변수

*left*<br/>
형식의 개체 또는 모든 변환할 수 있는 문자열 형식을 `basic_string_view` 비교 합니다.

*right*<br/>
형식의 개체 또는 모든 변환할 수 있는 문자열 형식을 `basic_string_view` 비교 합니다.

### <a name="return-value"></a>반환 값

**true 이면** 어휘가 우변 string_view 개체 보다 크면이 고 그렇지 않으면 연산자의 좌 변에 있는 개체가 있으면 **false**합니다.

### <a name="remarks"></a>설명

참조 [연산자&lt;](#op_lt)합니다.

## <a name="op_gt_eq"></a> 연산자&gt;=

연산자의 좌변에 있는 개체가 우변에 있는 개체보다 크거나 같은지 테스트합니다.

```cpp
template <class CharType, class Traits>
bool operator>=(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator>=(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator>=(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>매개 변수

*left*<br/>
형식의 개체 또는 모든 변환할 수 있는 문자열 형식을 `basic_string_view` 비교 합니다.

*right*<br/>
형식의 개체 또는 모든 변환할 수 있는 문자열 형식을 `basic_string_view` 비교 합니다.

### <a name="return-value"></a>반환 값

**true 이면** 사전순으로 보다 큰 또는 오른쪽에 있는 개체와 같으면이 고 그렇지 않으면 연산자의 좌 변에 있는 개체가 있으면 **false**합니다.

### <a name="remarks"></a>설명

참조 [연산자&lt;](#op_lt)합니다.

## <a name="op_sv"></a> 연산자"" sv (string_view 리터럴)

문자열 리터럴에서 string_view를 생성합니다. 사용 하려면 네임 스페이스 `std::literals::string_view_literals`합니다. 

### <a name="example"></a>예제

```cpp

using namespace std;
using namespace literals::string_view_literals;

    string_view sv{ "Hello"sv };
    wstring_view wsv{ L"Hello"sv };
    u16string_view sv16{ u"Hello"sv };
    u32string_view sv32{ U"Hello"sv };
```

## <a name="see-also"></a>참고자료

[\<string_view>](../standard-library/string-view.md)<br/>
