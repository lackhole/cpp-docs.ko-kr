---
title: basic_string_view 클래스
ms.date: 04/20/2019
f1_keywords:
- xstring/std::basic_string_view
- xstring/std::basic_string_view::allocator_type
- xstring/std::basic_string_view::const_iterator
- xstring/std::basic_string_view::const_pointer
- xstring/std::basic_string_view::const_reference
- xstring/std::basic_string_view::const_reverse_iterator
- xstring/std::basic_string_view::difference_type
- xstring/std::basic_string_view::iterator
- xstring/std::basic_string_view::npos
- xstring/std::basic_string_view::pointer
- xstring/std::basic_string_view::reference
- xstring/std::basic_string_view::reverse_iterator
- xstring/std::basic_string_view::size_type
- xstring/std::basic_string_view::traits_type
- xstring/std::basic_string_view::value_type
- xstring/std::basic_string_view::append
- xstring/std::basic_string_view::assign
- xstring/std::basic_string_view::at
- xstring/std::basic_string_view::back
- xstring/std::basic_string_view::begin
- xstring/std::basic_string_view::c_str
- xstring/std::basic_string_view::capacity
- xstring/std::basic_string_view::cbegin
- xstring/std::basic_string_view::cend
- xstring/std::basic_string_view::clear
- xstring/std::basic_string_view::compare
- xstring/std::basic_string_view::copy
- xstring/std::basic_string_view::_Copy_s
- xstring/std::basic_string_view::crbegin
- xstring/std::basic_string_view::crend
- xstring/std::basic_string_view::data
- xstring/std::basic_string_view::empty
- xstring/std::basic_string_view::end
- xstring/std::basic_string_view::erase
- xstring/std::basic_string_view::find
- xstring/std::basic_string_view::find_first_not_of
- xstring/std::basic_string_view::find_first_of
- xstring/std::basic_string_view::find_last_not_of
- xstring/std::basic_string_view::find_last_of
- xstring/std::basic_string_view::front
- xstring/std::basic_string_view::get_allocator
- xstring/std::basic_string_view::insert
- xstring/std::basic_string_view::length
- xstring/std::basic_string_view::max_size
- xstring/std::basic_string_view::pop_back
- xstring/std::basic_string_view::push_back
- xstring/std::basic_string_view::rbegin
- xstring/std::basic_string_view::rend
- xstring/std::basic_string_view::remove_prefix
- xstring/std::basic_string_view::remove_suffix
- xstring/std::basic_string_view::replace
- xstring/std::basic_string_view::reserve
- xstring/std::basic_string_view::resize
- xstring/std::basic_string_view::rfind
- xstring/std::basic_string_view::shrink_to_fit
- xstring/std::basic_string_view::size
- xstring/std::basic_string_view::substr
- xstring/std::basic_string_view::swap
helpviewer_keywords:
- std::basic_string_view
- std::basic_string_view, allocator_type
- std::basic_string_view, const_iterator
- std::basic_string_view, const_pointer
- std::basic_string_view, const_reference
- std::basic_string_view, const_reverse_iterator
- std::basic_string_view, difference_type
- std::basic_string_view, iterator
- std::basic_string_view, npos
- std::basic_string_view, pointer
- std::basic_string_view, reference
- std::basic_string_view, reverse_iterator
- std::basic_string_view, size_type
- std::basic_string_view, traits_type
- std::basic_string_view, value_type
- std::basic_string_view, append
- std::basic_string_view, assign
- std::basic_string_view, at
- std::basic_string_view, back
- std::basic_string_view, begin
- std::basic_string_view, c_str
- std::basic_string_view, capacity
- std::basic_string_view, cbegin
- std::basic_string_view, cend
- std::basic_string_view, clear
- std::basic_string_view, compare
- std::basic_string_view, copy
- std::basic_string_view, crbegin
- std::basic_string_view, crend
- std::basic_string_view, data
- std::basic_string_view, empty
- std::basic_string_view, end
- std::basic_string_view, erase
- std::basic_string_view, find
- std::basic_string_view, find_first_not_of
- std::basic_string_view, find_first_of
- std::basic_string_view, find_last_not_of
- std::basic_string_view, find_last_of
- std::basic_string_view, front
- std::basic_string_view, get_allocator
- std::basic_string_view, insert
- std::basic_string_view, length
- std::basic_string_view, max_size
- std::basic_string_view, pop_back
- std::basic_string_view, push_back
- std::basic_string_view, rbegin
- std::basic_string_view, rend
- std::basic_string_view, remove_prefix
- std::basic_string_view, remove_suffix
- std::basic_string_view, replace
- std::basic_string_view, reserve
- std::basic_string_view, resize
- std::basic_string_view, rfind
- std::basic_string_view, shrink_to_fit
- std::basic_string_view, size
- std::basic_string_view, substr
- std::basic_string_view, swap
ms.assetid: a9c3e0a2-39bf-4c8a-b093-9abe30839591
ms.openlocfilehash: 0ac5e3d528881f7b1caa0a1dcdae0161a6777e57
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346941"
---
# <a name="basicstringview-class"></a>basic_string_view 클래스

클래스 템플릿 `basic_string_view<charT>` c++17에서 다양 한 허용 하는 함수에 대 한 안전 하 고 효율적인 방식으로 이러한 형식에서 템플릿 화할 수 하지 않아도 함수 없이 관련 없는 문자열 형식으로 사용할 추가 되었습니다. 시퀀스의 문자 수를 지정 하는 길이 문자 데이터의 연속 시퀀스를 소유 되지 않은 포인터를 보유 하는 클래스입니다. 가정이 없는 시퀀스의 null로 끝나는 인지 여부와 관련 하 여 수행 됩니다.

표준 라이브러리 요소 형식을 기반으로 하는 여러 특수화를 정의 합니다.

-  `string_view`
-  `wstring_view`
-  `u16string_view`
-  `u32string_view`

이 문서에서는 "string_view" 란 일반적으로 이러한 typedefs 중 하나를 말합니다.

string_view 문자열 데이터를 읽는 데 필요한 최소 공통 인터페이스를 설명 합니다. 기본 데이터에 대 한 const 제공 복사본 없습니다 (제외 하 고는 `copy` 함수). 데이터 수도 있고 다른 위치에 있는 null 값 ('\0')를 포함할 수 없습니다. string_view는 개체의 수명 기간 동안 제어할 수 없습니다. 호출자의 기본 문자열 데이터가 유효한 지 확인 합니다.

형식 string_view의 매개 변수를 받아들이는 함수입니다 템플릿으로, 함수 또는 문자열 형식의 특정 하위 집합에는 제하지 없이, 모든 문자열 형식 유형과 함께 작동 하도록 만들 수 있습니다. 유일한 요구 사항인 string_view를 문자열 형식에서 암시적 변환이 존재 합니다. 모든 표준 문자열 형식은 동일한 요소 유형이 포함 된 string_view 암시적으로 변환할 수 있습니다. 즉, 한 `std::string` 으로 변환 될 수는 `string_view` 없습니다를 `wstring_view`.

다음 예제는 비템플릿 함수를 보여 줍니다 `f` 형식의 매개 변수를 사용 하는 `wstring_view`합니다. 형식의 인수를 사용 하 여 호출할 수 있습니다 `std::wstring`하십시오 `wchar_t*`, 및 `winrt::hstring`합니다.

```cpp
// compile with: /std:c++17
// string_view that uses elements of wchar_t
void f(wstring_view);

// pass a std::wstring:
const std::wstring& s { L"Hello" };
f(s);

// pass a C-style null-terminated string (string_view is not null-terminated):
const wchar_t* ns = L"Hello";
f(ns);

// pass a C-style character array of len characters (excluding null terminator):
const wchar_t* cs { L"Hello" };
size_t len { 5 };
f({cs,len});

// pass a WinRT string
winrt::hstring hs { L"Hello" };
f(hs);
```

## <a name="syntax"></a>구문

```cpp
template <class CharType, class Traits = char_traits<CharType>>
class basic_string_view;
```

### <a name="parameters"></a>매개 변수

*CharType*<br/>
string_view에 저장 되는 문자 형식입니다. C++ 표준 라이브러리에서는이 템플릿의 특수화에 대 한 다음 형식 정의 제공 합니다.
- [string_view](../standard-library/string-view-typedefs.md#string_view) 형식의 요소에 대해 **char**
- [wstring_view](../standard-library/string-view-typedefs.md#wstring_view), for **wchar_t**
- [u16string_view](../standard-library/string-view-typedefs.md#u16string_view) 에 대 한 **char16_t**
- [u32string_view](../standard-library/string-view-typedefs.md#u32string_view) 에 대 한 **char32_t**합니다.

*특성*<br/>
기본값으로 [char_traits](char-traits-struct.md)<*CharType*>.

### <a name="constructors"></a>생성자

|생성자|설명|
|-|-|
|[basic_string_view](#basic_string_view)|C 스타일 문자 배열 또는 일부 다른 문자열 개체의 데이터의 일부나 전부를 가리킵니다. 그렇지 않으면 비어 있는 string_view를 생성 합니다.|

### <a name="typedefs"></a>형식 정의

|형식 이름|설명|
|-|-|
|**const_iterator**|읽을 수 있는 임의 액세스 반복기 **const** 요소입니다.|
|**const_pointer**|`using const_pointer = const value_type*;`|
|**const_reference**|`using const_reference = const value_type&;`|
|**const_reverse_iterator**|`using const_reverse_iterator = std::reverse_iterator<const_iterator>;`|
|**difference_type**|`using difference_type = ptrdiff_t;`|
|**iterator**|`using iterator = const_iterator;`|
|**npos**|`static constexpr size_type npos = size_type(-1);`|
|**pointer**|`using pointer = value_type*;`|
|**reference**|`using reference = value_type&;`|
|**reverse_iterator**|`using reverse_iterator = const_reverse_iterator;`|
|**size_type**|`using size_type = size_t;`|
|**traits_type**|`using traits_type = Traits;`|
|**value_type**|`using value_type = CharType;`|

### <a name="member-operators"></a>멤버 연산자

|연산자|설명|
|-|-|
|[operator=](#op_eq)|다른 string_view에 string_view 또는 변환할 수 있는 문자열 개체를 할당합니다.|
|[operator\[\]](#op_at)|지정한 인덱스의 요소를 반환합니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|설명|
|-|-|
|[at](#at)|지정된 된 위치에 있는 요소를 const_reference를 반환합니다.|
|[back](#back)|마지막 요소에는 const_reference를 반환합니다.|
|[begin](#begin)|첫 번째 요소 주소를 지정 하는 const 반복기를 반환 합니다. (string_views는 변경할 수 없습니다.)|
|[cbegin](#cbegin)|동일 [시작](#begin)합니다.|
|[cend](#cend)|요소를 지난 요소를 가리키는 const 반복기를 반환 합니다.|
|[copy](#copy)|최대 지정한 개수의 문자를 원본 string_view의 인덱싱된 위치에서는 대상 문자 배열로 복사 합니다. (권장 되지 않습니다. _Copy_s 대신 사용 합니다.)|
|[_Copy_s](#_copy_s)|보안 CRT 복사본 함수입니다.|
|[compare](#compare)|동일한 경우 또는 다른 보다 사전 순으로 작은 경우를 확인 하려면 지정한 string_view 사용 하 여 string_view를 비교 합니다.|
|[crbegin](#crbegin)|동일 [rbegin](#rbegin)합니다.|
|[crend](#crend)|동일 [rend](#rend)합니다.|
|[data](#data)|문자 시퀀스를 소유 되지 않은 원시 포인터를 반환합니다.|
|[empty](#empty)|string_view에 문자가 있는지 테스트 합니다.|
|[end](#end)|동일 [cend](#cend)합니다.|
|[find](#find)|지정된 된 문자 시퀀스와 일치 하는 부분 문자열의 첫 번째 앞으로 검색 합니다.|
|[find_first_not_of](#find_first_not_of)|지정 된 string_view 또는 변환할 수 있는 문자열 개체의 요소가 아닌 첫 번째 문자를 검색 합니다.|
|[find_first_of](#find_first_of)|지정 된 string_view 또는 변환할 수 있는 문자열 개체의 모든 요소와 일치 하는 첫 번째 문자를 검색 합니다.|
|[find_last_not_of](#find_last_not_of)|지정한 string_view 또는 변환할 수 있는 문자열 개체의 요소가 아닌 마지막 문자를 검색 합니다.|
|[find_last_of](#find_last_of)|마지막 문자는 지정 된 string_view 또는 변환할 수 있는 문자열 개체의 요소를 검색 합니다.|
|[front](#front)|첫 번째 요소는 const_reference를 반환합니다.|
|[length](#length)|현재 요소 수를 반환합니다.|
|[max_size](#max_size)|문자는 string_view 수의 최대 수를 반환 합니다.|
|[rbegin](#rbegin)|역방향된 string_view 첫 번째 요소를 해결 하는 const 반복기를 반환 합니다.|
|[remove_prefix](#remove_prefix)|요소의 지정된 된 수 만큼 앞으로 포인터를 이동합니다.|
|[remove_suffix](#remove_suffix)|에서 시작 하는 요소의 지정된 된 수 만큼 뷰의 크기를 줄입니다.|
|[rend](#rend)|역방향된 string_view에 요소를 지난 요소를 가리키는 const 반복기를 반환 합니다.|
|[rfind](#rfind)|지정된 된 문자 시퀀스와 일치 하는 부분 문자열의 첫 번째 역방향에서을 string_view를 검색 합니다.|
|[size](#size)|현재 요소 수를 반환합니다.|
|[substr](#substr)|지정된 된 인덱스부터 지정 된 길이의 부분 문자열을 반환 합니다.|
|[swap](#swap)|두 string_views의 내용을 교환 합니다.|

## <a name="remarks"></a>설명

함수는 [max_size](#max_size) 요소보다 긴 시퀀스를 생성하라는 요청을 받으면 [length_error](../standard-library/length-error-class.md) 형식의 개체를 throw하여 길이 오류를 보고합니다.

## <a name="requirements"></a>요구 사항

[/std: c + + 17](../build/reference/std-specify-language-standard-version.md) 이상

**헤더:** \<string_view >

**네임스페이스:** std

## <a name="at"></a>  basic_string_view::at

지정된 된 0 기반 인덱스에 해당 하는 const_reference를 반환합니다.

```cpp
constexpr const_reference at(size_type offset) const;
```

### <a name="parameters"></a>매개 변수

*offset*<br/>
참조 되는 요소의 인덱스입니다.

### <a name="return-value"></a>반환 값

매개 변수 인덱스로 지정 된 위치에 해당 하는 const_reference 합니다.

### <a name="remarks"></a>설명

첫 번째 요소에 0부터 시작 하 고 다음 요소부터 연속적으로 양의 정수로 있도록 길이의 string_view *n* 에 *n*번째 요소의 인덱스 번호 *n-* 1입니다. **언제** 와 달리 잘못 된 인덱스에 대 한 예외를 throw [연산자\[\]](#op_at)합니다. 

좋습니다 일반적으로 **언제** 같은 순서에 대 한 `std::vector` string_view 사용 되지 않아야 하 고 합니다. 시퀀스에 전달 되는 잘못 된 인덱스에 검색 하 고 개발 하는 동안 고정 해야 하는 논리 오류입니다. 프로그램 아니면 반드시 특정 해당 인덱스는 유효 해야 테스트, 없습니다 at()를 호출 하 고 부주의 프로그래밍에 대 한 예외를 사용 합니다.

참조 [basic_string_view::operator\[ \] ](#op_at) 자세한 내용은 합니다.

### <a name="example"></a>예제

```cpp
// basic_string_view_at.cpp
// compile with: /EHsc
#include <string_view>
#include <iostream>

int main()
{
    using namespace std;

    const string_view  str1("Hello world");
    string_view::const_reference refStr2 = str1.at(8); // 'r'
}
```

## <a name="back"></a>  basic_string_view::back

마지막 요소에는 const_reference를 반환합니다.

```cpp
constexpr const_reference back() const;
```

### <a name="return-value"></a>반환 값

string_view의 마지막 요소에는 const_reference 합니다.

### <a name="remarks"></a>설명

string_view가 비어 있으면 예외가 throw 됩니다.

한다는 점에 주의 string_view 수정 된 후, 예를 들어 호출 하 여 `remove_suffix`,이 함수에서 반환한 요소는 더 이상 기본 데이터의 마지막 요소입니다.

### <a name="example"></a>예제

C 문자열 리터럴에로 생성 된 string_view 종결 null이 포함 되지 않습니다 및 따라서 다음 예와에서 `back` 없습니다 '\0' 및 'p'를 반환 합니다.

```cpp
char c[] = "Help"; // char[5]
string_view sv{ c };
cout << sv.size(); // size() == 4
cout << sv.back() << endl; // p 
```

포함 된 null은 다른 문자로 처리 됩니다.

```cpp
string_view e = "embedded\0nulls"sv;
cout << boolalpha << (e.back() == 's'); // true
```

## <a name="basic_string_view"></a>  basic_string_view::basic_string_view

string_view를 생성합니다.

```cpp
constexpr basic_string_view() noexcept;
constexpr basic_string_view(const basic_string_view&) noexcept = default;
constexpr basic_string_view(const charT* str);
constexpr basic_string_view(const charT* str, size_type len);
```

### <a name="parameters"></a>매개 변수

*str*<br/>
문자 값에 대 한 포인터입니다.

*len*<br/>
보기에 포함 되는 문자의 수입니다.

## <a name="remarks"></a>설명

차트 * 매개 변수를 사용 하 여 생성자는 입력이 null로 종료 되지만 종료 null을 string_view에 포함 되지 않습니다 가정 합니다.

또한 리터럴에 string_view를 생성할 수 있습니다. 참조 [연산자 "" sv](string-view-operators.md#op_sv)합니다.

## <a name="begin"></a>  basic_string_view::begin

동일 [cbegin](#cbegin)합니다.

```cpp
constexpr const_iterator begin() const noexcept;
```

### <a name="return-value"></a>반환 값
첫 번째 요소 주소를 지정 하는 const_iterator를 반환 합니다.

## <a name="cbegin"></a>  basic_string_view::cbegin

범위에서 첫 번째 요소를 해결 하는 const_iterator를 반환 합니다.

```cpp
constexpr const_iterator cbegin() const noexcept;
```

### <a name="return-value"></a>반환 값

A **상수** 범위 또는 빈 범위의 끝 바로 다음 위치 중 첫 번째 요소를 가리키는 임의 액세스 반복기 (빈 범위의 경우 `cbegin() == cend()`).

## <a name="cend"></a>  basic_string_view::cend

범위에서 마지막 요소 바로 다음 위치를 해결 하는 const_iterator를 반환 합니다.

```cpp
constexpr const_iterator cend() const noexcept;
```

### <a name="return-value"></a>반환 값

A **const** 범위의 끝 바로 다음을 가리키는 임의 액세스 반복기입니다.

### <a name="remarks"></a>설명

`cend`에서 반환한 값은 역참조되지 않아야 합니다.

## <a name="compare"></a> basic_string_view::compare

두 개체가 같은지 또는 다른 보다 사전 순으로 작은 경우를 확인 하려면 지정한 string_view (또는 변환할 수 있는 문자열 형식)를 사용 하 여 대/소문자 구분 비교를 수행 합니다. 합니다 [ \<string_view > 연산자](string-view-operators.md) 비교를 수행 하려면이 멤버 함수를 사용 합니다.

```cpp
constexpr int compare(basic_string_view strv) const noexcept;
constexpr int compare(size_type pos, size_type num, basic_string_view strv) const;
constexpr int compare(size_type pos, size_type num, basic_string_view strv, size_type offset, size_type num2) const;
constexpr int compare(const charT* ptr) const;
constexpr int compare(size_type pos, size_type num, const charT* ptr) const;
constexpr int compare(size_type pos, size_type num, const charT* ptr, size_type num2) const;
```

### <a name="parameters"></a>매개 변수

*strv*<br/>
이 string_view 비교할는 string_view 합니다.

*pos*<br/>
비교가 시작 되는이 string_view의 인덱스입니다.

*num*<br/>
비교할이 string_view 문자의 최대 수입니다.

*num2*<br/>
문자 수가 최대 *strv* 비교 합니다.

*offset*<br/>
인덱스 *strv* 비교 시작 되는 합니다.

*ptr*<br/>
이 string_view 비교할 C 문자열입니다.

### <a name="return-value"></a>반환 값

이 string_view 경우 음수 값 보다 작거나 *strv* 하거나 *ptr*경우 두 문자 시퀀스를 같은 이나 양수 값이이 string_view 보다 큰 경우에 0 *strv*나 *ptr*합니다.

### <a name="remarks"></a>설명

`compare` 멤버 함수에는 전체 또는 일부의 각 문자 시퀀스의 대/소문자 구분 비교를 수행 합니다. 

### <a name="example"></a>예제

```cpp
// basic_string_view_compare.cpp
// compile with: /EHsc
#include <string_view>
#include <iostream>
#include <string>

using namespace std;

string to_alpha(int result)
{
   if (result < 0) return " less than ";
   else if (result == 0) return " equal to ";
   else return " greater than ";
}

int main()
{
   // The first member function compares
   // two string_views
   string_view sv_A("CAB");
   string_view sv_B("CAB");
   cout << "sv_A is " << sv_A << endl;
   cout << "sv_B is " << sv_B << endl;
   int comp1 = sv_A.compare(sv_B);
   cout << "sv_A is" << to_alpha(comp1) << "sv_B.\n";

   // The second member function compares part of
   // an operand string_view to another string_view
   string_view sv_C("AACAB");
   string_view sv_D("CAB");
   cout << "sv_C is: " << sv_C << endl;
   cout << "sv_D is: " << sv_D << endl;
   int comp2a = sv_C.compare(2, 3, sv_D);
   cout << "The last three characters of sv_C are" 
       << to_alpha(comp2a) << "sv_D.\n";

   int comp2b = sv_C.compare(0, 3, sv_D);
   cout << "The first three characters of sv_C are" 
       << to_alpha(comp2b) << "sv_D.\n";

   // The third member function compares part of
   // an operand string_view to part of another string_view
   string_view sv_E("AACAB");
   string_view sv_F("DCABD");
   cout << "sv_E: " << sv_E << endl;
   cout << "sv_F is: " << sv_F << endl;
   int comp3a = sv_E.compare(2, 3, sv_F, 1, 3);
   cout << "The three characters from position 2 of sv_E are"
       << to_alpha(comp3a) 
       << "the 3 characters of sv_F from position 1.\n";

   // The fourth member function compares
   // an operand string_view to a C string
   string_view sv_G("ABC");
   const char* cs_A = "DEF";
   cout << "sv_G is: " << sv_G << endl;
   cout << "cs_A is: " << cs_A << endl;
   int comp4a = sv_G.compare(cs_A);
   cout << "sv_G is" << to_alpha(comp4a) << "cs_A.\n";

   // The fifth member function compares part of
   // an operand string_view to a C string
   string_view sv_H("AACAB");
   const char* cs_B = "CAB";
   cout << "sv_H is: " << sv_H << endl;
   cout << "cs_B is: " << cs_B << endl;
   int comp5a = sv_H.compare(2, 3, cs_B);
   cout << "The last three characters of sv_H are"
      << to_alpha(comp5a) << "cs_B.\n";

   // The sixth member function compares part of
   // an operand string_view to part of an equal length of
   // a C string
   string_view sv_I("AACAB");
   const char* cs_C = "ACAB";
   cout << "sv_I is: " << sv_I << endl;
   cout << "cs_C: " << cs_C << endl;
   int comp6a = sv_I.compare(1, 3, cs_C, 3);
   cout << "The 3 characters from position 1 of sv_I are"
      << to_alpha(comp6a) << "the first 3 characters of cs_C.\n";
}
```

```Output
sv_A is CAB
sv_B is CAB
sv_A is equal to sv_B.
sv_C is: AACAB
sv_D is: CAB
The last three characters of sv_C are equal to sv_D.
The first three characters of sv_C are less than sv_D.
sv_E: AACAB
sv_F is: DCABD
The three characters from position 2 of sv_E are equal to the 3 characters of sv_F from position 1.
sv_G is: ABC
cs_A is: DEF
sv_G is less than cs_A.
sv_H is: AACAB
cs_B is: CAB
The last three characters of sv_H are equal to cs_B.
sv_I is: AACAB
cs_C: ACAB
The 3 characters from position 1 of sv_I are equal to the first 3 characters of cs_C.
```

## <a name="copy"></a>  basic_string_view::copy

최대 지정한 개수의 문자를 원본 string_view의 인덱싱된 위치에서는 대상 문자 배열로 복사 합니다. 보안 함수를 사용 하는 것이 좋습니다 [basic_string_view::_Copy_s](#_copy_s) 대신 합니다.

```cpp
size_type copy(charT* ptr, size_type count, size_type offset = 0) const;
```

### <a name="parameters"></a>매개 변수

*ptr*<br/>
요소를 복사할 대상 문자 배열입니다.

*count*<br/>
복사할 최대 원본 string_view에서 문자의 수입니다.

*offset*<br/>
복사 되는 원본 string_view 시작 위치입니다.

### <a name="return-value"></a>반환 값

실제로 복사된 문자 수입니다.

### <a name="remarks"></a>설명

Null 문자는 복사본의 끝에 추가되지 않습니다.

## <a name="_copy_s"></a>  basic_string_view::_Copy_s

보안 CRT 복사본 함수 대신 사용할 [복사](#copy)합니다.

```cpp
size_type _Copy_s(
    value_type* dest,
    size_type dest_size,
    size_type count,
    size_type _Off = 0) const;
```

### <a name="parameters"></a>매개 변수

*dest*<br/>
요소를 복사할 대상 문자 배열입니다.

*dest_size*<br/>
크기인 *dest*합니다.

_ *개수* 복사할 최대 소스 문자열에서 문자의 수입니다.

*_Off*<br/>
복사본을 만들 원본 문자열의 시작 위치입니다.

### <a name="return-value"></a>반환 값

실제로 복사된 문자 수입니다.

### <a name="remarks"></a>설명

Null 문자는 복사본의 끝에 추가되지 않습니다.

 자세한 내용은 [c-runtime-library/security-features-in-the-crt](../c-runtime-library/security-features-in-the-crt.md)합니다.

## <a name="crbegin"></a>  basic_string_view::crbegin

역방향된 string_view 첫 번째 요소를 다루는 const_reverse_iterator를 반환 합니다.

```cpp
constexpr const_reverse_iterator crbegin() const noexcept;
```

### <a name="return-value"></a>반환 값

역방향된 string_view 첫 번째 요소를 다루는 const_reverse_iterator 합니다. 

## <a name="crend"></a>  basic_string_view::crend

동일 [rend](#rend)합니다. 

```cpp
constexpr const_reverse_iterator crend() const noexcept;
```

### <a name="return-value"></a>반환 값

역방향된 string_view의 끝을 지난 하나 다루는 const_reverse_iterator를 반환 합니다.

## <a name="data"></a>  basic_string_view::data

string_view를 생성 하는 데 사용 된 개체의 const 문자 시퀀스를 소유 되지 않은 원시 포인터를 반환 합니다.

```cpp
constexpr value_type *data() const noexcept;
```

### <a name="return-value"></a>반환 값

포인터-에-const 문자 시퀀스의 첫 번째 요소입니다.

### <a name="remarks"></a>설명

포인터에는 문자를 수정할 수 없습니다.

String_view 문자 시퀀스로 반드시 null로 끝나는 아닙니다. 반환 형식은 `data` null 문자가 추가 하기 때문에 유효한 C 문자열이 아닙니다. Null 문자 '\0' 형식 string_view 개체에서는 특별 한 의미가 없으며 및 다른 문자와 마찬가지로 string_view 개체의 일부가 될 수 있습니다.

## <a name="empty"></a>  basic_string_view::empty

string_view에 문자가 있는지 테스트 합니다.

```cpp
constexpr bool empty() const noexcept;
```

### <a name="return-value"></a>반환 값

**true** string_view 개체에 없는 문자를 포함 하는 경우 **false** 문자를 하나 이상 있는 경우.

### <a name="remarks"></a>설명

멤버 함수는 동일 [크기](#size)() = = 0.

## <a name="end"></a>  basic_string_view::end

요소를 지난 요소를 가리키는 임의 액세스 const_iterator를 반환 합니다.

```cpp
constexpr const_iterator end() const noexcept;
```

### <a name="return-value"></a>반환 값

요소를 지난 요소를 가리키는 임의 액세스 const_iterator를 반환 합니다.

### <a name="remarks"></a>설명

`end` const_iterator를 해당 string_view의 끝에 도달 했는지 여부를 테스트 하는 데 사용 됩니다. `end`에서 반환한 값은 역참조되지 않아야 합니다.

## <a name="find"></a>  basic_string_view::find

문자 또는 지정 된 문자 시퀀스와 일치 하는 부분 문자열의 첫 번째 앞으로 string_view를 검색 합니다.

```cpp
constexpr size_type find(basic_string_view str, size_type offset = 0) const noexcept;
constexpr size_type find(charT chVal, size_type offset = 0) const noexcept;
constexpr size_type find(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find(const charT* ptr, size_type offset = 0) const;
```

### <a name="parameters"></a>매개 변수

*str*<br/>
멤버 함수는 검색할 string_view 합니다.

*chVal*<br/>
멤버 함수가 검색할 문자 값입니다.

*offset*<br/>
검색이 시작 되는 인덱스입니다.

*ptr*<br/>
멤버 함수는 검색할 C 문자열입니다.

*count*<br/>
문자 수가 *ptr*, 첫 번째 문자에서 앞으로 계산 합니다.

### <a name="return-value"></a>반환 값

성공하면 검색되는 부분 문자열의 첫 문자 인덱스이고, 그렇지 않으면 `npos`입니다.

## <a name="find_first_not_of"></a>  basic_string_view::find_first_not_of

지정 된 string_view 또는 변환할 수 있는 문자열 개체의 요소가 아닌 첫 번째 문자를 검색 합니다.

```cpp
constexpr size_type find_first_not_of(basic_string_view str, size_type offset = 0) const noexcept;
constexpr size_type find_first_not_of(charT chVal, size_type offset = 0) const noexcept;
constexpr size_type find_first_not_of(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find_first_not_of(const charT* ptr, size_type offset = 0) const;
```

### <a name="parameters"></a>매개 변수

*str*<br/>
멤버 함수는 검색할 string_view 합니다.

*chVal*<br/>
멤버 함수가 검색할 문자 값입니다.

*offset*<br/>
검색이 시작 되는 인덱스입니다.

*ptr*<br/>
멤버 함수는 검색할 C 문자열입니다.

*count*<br/>
멤버 함수는 검색할 C 문자열에서 첫 번째 문자를 앞으로 계산 된 문자 수입니다.

### <a name="return-value"></a>반환 값

성공하면 검색되는 부분 문자열의 첫 문자 인덱스이고, 그렇지 않으면 `npos`입니다.

## <a name="find_first_of"></a>  basic_string_view::find_first_of

지정 된 string_view의 모든 요소와 일치 하는 첫 번째 문자를 검색 합니다.

```cpp
constexpr size_type find_first_of(basic_string_view str, size_type offset = 0) const noexcept;
constexpr size_type find_first_of(charT chVal, size_type offset = 0) const noexcept;
constexpr size_type find_first_of(const charT* str, size_type offset, size_type count) const;
constexpr size_type find_first_of(const charT* str, size_type offset = 0) const;
```

### <a name="parameters"></a>매개 변수

*chVal*<br/>
멤버 함수가 검색할 문자 값입니다.

*offset*<br/>
검색이 시작 되는 인덱스입니다.

*ptr*<br/>
멤버 함수는 검색할 C 문자열입니다.

*count*<br/>
멤버 함수는 검색할 C 문자열에서 첫 번째 문자를 앞으로 계산 된 문자 수입니다.

*str*<br/>
멤버 함수는 검색할 string_view 합니다.

### <a name="return-value"></a>반환 값

성공하면 검색되는 부분 문자열의 첫 문자 인덱스이고, 그렇지 않으면 `npos`입니다.

## <a name="find_last_not_of"></a>  basic_string_view::find_last_not_of

지정 된 string_view의 요소가 아닌 마지막 문자를 검색 합니다.

```cpp
constexpr size_type find_last_not_of(basic_string_view str, size_type offset = npos) const noexcept;
constexpr size_type find_last_not_of(charT chVal, size_type offset = npos) const noexcept;
constexpr size_type find_last_not_of(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find_last_not_of(const charT* ptr, size_type offset = npos) const;
```

### <a name="parameters"></a>매개 변수

*str*<br/>
멤버 함수는 검색할 string_view 합니다.

*chVal*<br/>
멤버 함수가 검색할 문자 값입니다.

*offset*<br/>
검색이 완료 되는 인덱스입니다.

*ptr*<br/>
멤버 함수는 검색할 C 문자열입니다.

*count*<br/>
첫 번째 문자를 앞으로 계산 된 문자 수가 *ptr*합니다.

### <a name="return-value"></a>반환 값

성공하면 검색되는 부분 문자열의 첫 문자 인덱스이고, 그렇지 않으면 `string_view::npos`입니다.

## <a name="find_last_of"></a>  basic_string_view::find_last_of

지정 된 string_view의 모든 요소와 일치 하는 마지막 문자를 검색 합니다.

```cpp
constexpr size_type find_last_of(basic_string_view str, size_type offset = npos) const noexcept;
constexpr size_type find_last_of(charT chVal, size_type offset = npos) const noexcept;
constexpr size_type find_last_of(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find_last_of(const charT* ptr, size_type offset = npos) const;
```

### <a name="parameters"></a>매개 변수

*str*<br/>
멤버 함수는 검색할 string_view 합니다.

*chVal*<br/>
멤버 함수가 검색할 문자 값입니다.

*offset*<br/>
검색이 완료 되는 인덱스입니다.

*ptr*<br/>
멤버 함수는 검색할 C 문자열입니다.

*count*<br/>
멤버 함수는 검색할 C 문자열에서 첫 번째 문자를 앞으로 계산 된 문자 수입니다.

### <a name="return-value"></a>반환 값

성공 시 검색되는 부분 문자열의 마지막 문자 인덱스이고, 그렇지 않으면 `npos`입니다.

## <a name="front"></a>  basic_string_view::front

첫 번째 요소는 const_reference를 반환합니다.

```cpp
constexpr const_reference front() const;
```

### <a name="return-value"></a>반환 값

첫 번째 요소는 const_reference 합니다.

### <a name="remarks"></a>설명

string_view가 비어 있으면 예외가 throw 됩니다.

## <a name="length"></a> basic_string_view::length

현재 요소 수를 반환합니다.

```cpp
constexpr size_type length() const noexcept;
```

### <a name="remarks"></a>설명

멤버 함수는 [size](#size)와 동일합니다.

## <a name="max_size"></a>  basic_string_view::max_size

문자는 string_view 수의 최대 수를 반환 합니다.

```cpp
constexpr size_type max_size() const noexcept;
```

### <a name="return-value"></a>반환 값

최대 string_view 문자를 포함할 수 있습니다.

### <a name="remarks"></a>설명

형식의 예외가 [length_error](../standard-library/length-error-class.md) 작업을 보다 길이가 더 긴 string_view를 생성 하는 경우 throw 되 `max_size()`합니다.

## <a name="op_eq"></a>  basic_string_view::operator=

다른 string_view에 string_view 또는 변환할 수 있는 문자열 개체를 할당합니다.

```cpp
constexpr basic_string_view& operator=(const basic_string_view&) noexcept = default;
```
### <a name="example"></a>예제

```cpp
   string_view s = "Hello";
   string_view s2 = s;
```
## <a name="op_at"></a>  basic_string_view::operator[]

지정된 된 인덱스를 사용 하 여 문자 const_reference를 제공합니다.

```cpp
constexpr const_reference operator[](size_type offset) const;
```

### <a name="parameters"></a>매개 변수

*offset*<br/>
참조 되는 요소의 인덱스입니다.

### <a name="return-value"></a>반환 값

매개 변수 인덱스로 지정 된 위치에 해당 하는 const_reference 합니다.

### <a name="remarks"></a>설명

첫 번째 요소에는 인덱스가 0 및 다음 요소부터 연속적으로 양의 정수로 있도록 길이의 string_view *n* 에 *n*번째 요소의 인덱스 번호 *n* -1입니다.

`operator[]` 멤버 함수 보다 빠릅니다 [에서](#at) 는 string_view의 요소에 대 한 읽기 액세스를 제공 합니다.

`operator[]` 인수로 전달 된 인덱스가 유효한 지 여부를 확인 하지 않습니다. 잘못 된 인덱스가 전달 `operator[]` 정의 되지 않은 동작이 발생 합니다.

내부 문자열 데이터를 수정 하거나 소유 하는 개체에 의해 삭제 하는 경우 반환 되는 참조를 무효화 될 수 있습니다.

사용 하 여 컴파일하면 [ \_반복기\_디버그\_수준](../standard-library/iterator-debug-level.md) 1 또는 2로는 런타임 오류가 발생 합니다 string_view의 범위를 벗어난 요소에 액세스 하려는 경우. 자세한 내용은 [Checked Iterators](../standard-library/checked-iterators.md)을 참조하세요.

## <a name="rbegin"></a>  basic_string_view::rbegin

역방향된 string_view의 첫 번째 요소에 대해 const 반복기를 반환합니다.

```cpp
constexpr const_reverse_iterator rbegin() const noexcept;
```

### <a name="return-value"></a>반환 값

것이 무엇 인지 해당 역방향이 해제 된 string_view에서 마지막 요소의 주소를 지정 하는 역방향된 string_view, 첫 번째 요소에는 임의 액세스 반복기를 반환 합니다.

### <a name="remarks"></a>설명

`rbegin` 역방향된 string_view 사용 됩니다 것 처럼 [시작](#begin) string_view를 함께 사용 됩니다. `rbegin` 반복을 이전 버전과 초기화를 사용할 수 있습니다.

## <a name="remove_prefix"></a> basic_string_view::remove_prefix

요소의 지정된 된 수 만큼 앞으로 포인터를 이동합니다.

```cpp
constexpr void remove_prefix(size_type n);
```

### <a name="remarks"></a>설명

변경 하지 않고 기본 데이터를 유지 합니다. N 개 요소에서 string_view 포인터를 앞으로 이동 하 고 개인 설정 `size` 크기-n 데이터 멤버입니다.

## <a name="remove_suffix"></a> basic_string_view::remove_suffix

에서 시작 하는 요소의 지정된 된 수 만큼 뷰의 크기를 줄입니다.

```cpp
constexpr void remove_suffix(size_type n);
```

### <a name="remarks"></a>설명

기본 데이터 및 포인터를 그대로 둡니다. 개인 설정 `size` 크기-n 데이터 멤버입니다.

## <a name="rend"></a>  basic_string_view::rend

역방향된 string_view에 요소를 지난 요소를 가리키는 const 반복기를 반환 합니다.

```cpp
constexpr reverse_iterator rend() const noexcept;
```

### <a name="return-value"></a>반환 값

const 역방향 역방향된 string_view에서 마지막 요소 하나 다음을 가리키는 임의 액세스 반복기입니다.

### <a name="remarks"></a>설명

`rend` 역방향된 string_view 사용 됩니다 것 처럼 [최종](#end) string_view를 함께 사용 됩니다. `rend` 역방향 반복기를 해당 string_view의 끝에 도달 하는지 여부를 테스트할 수 있습니다. `rend`에서 반환한 값은 역참조되지 않아야 합니다.

## <a name="rfind"></a>  basic_string_view::rfind

지정된 된 문자 시퀀스와 일치 하는 부분 문자열에 대 한 역방향을 string_view를 검색 합니다.

```cpp
constexpr size_type rfind(basic_string_view str, size_type offset = npos) const noexcept;
constexpr size_type rfind(charT chVal, size_type offset = npos) const noexcept;
constexpr size_type rfind(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type rfind(const charT* ptr, size_type offset = npos) const;
```

### <a name="parameters"></a>매개 변수

*chVal*<br/>
멤버 함수가 검색할 문자 값입니다.

*offset*<br/>
검색이 시작 되는 인덱스입니다.

*ptr*<br/>
멤버 함수는 검색할 C 문자열입니다.

*count*<br/>
멤버 함수는 검색할 C 문자열에서 첫 번째 문자를 앞으로 계산 된 문자 수입니다.

*str*<br/>
멤버 함수는 검색할 string_view 합니다.

### <a name="return-value"></a>반환 값

성공할 경우 부분 문자열의 첫 번째 문자의 인덱스 그렇지 않으면 `npos`합니다.

## <a name="size"></a>  basic_string_view::size

string_view에서 요소 수를 반환합니다.

```cpp
constexpr size_type size() const noexcept;
```

### <a name="return-value"></a>반환 값

길이 string_view입니다.

### <a name="remarks"></a>설명

string_view 길이 예를 들어 하 여 수정할 수 `remove_prefix` 고 `remove_suffix`입니다. 내부 문자열 데이터를 수정 하지 않습니다는 string_view 크기 이므로 없습니다 반드시 기본 데이터의 크기입니다.

## <a name="substr"></a>  basic_string_view::substr

지정된 된 위치에서 (최대) 지정 된 개수의 문자를 나타내는 string_view를 반환 합니다.

```cpp
constexpr basic_string_view substr(size_type offset = 0, size_type count = npos) const;
```

### <a name="parameters"></a>매개 변수

*offset*<br/>
복사를 수행 된, 기본값은 0 사용 하 여 위치에 있는 요소를 배치 하는 인덱스입니다.

*count*<br/>
있는 경우는 부분 문자열에 포함할 문자의 수입니다.

### <a name="return-value"></a>반환 값

지정된 된 하위 시퀀스의 요소를 나타내는 string_view 개체입니다.

## <a name="swap"></a>  basic_string_view::swap

두 string_views, 즉 기본 문자열 데이터 크기 값을 포인터를 교환합니다.

```cpp
constexpr void swap(basic_string_view& sv) noexcept;
```

### <a name="parameters"></a>매개 변수

*sv*<br/>
원본 string_view를 대상 string_view의와 교환할 포인터와 크기 값이 포함 됩니다.

## <a name="see-also"></a>참고자료

[\<string_view>](../standard-library/string-view.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
