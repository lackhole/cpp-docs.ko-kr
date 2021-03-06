---
title: codecvt 클래스
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::codecvt
- xlocale/std::codecvt::extern_type
- xlocale/std::codecvt::intern_type
- xlocale/std::codecvt::state_type
- xlocale/std::codecvt::always_noconv
- xlocale/std::codecvt::do_always_noconv
- xlocale/std::codecvt::do_encoding
- xlocale/std::codecvt::do_in
- xlocale/std::codecvt::do_length
- xlocale/std::codecvt::do_max_length
- xlocale/std::codecvt::do_out
- xlocale/std::codecvt::do_unshift
- xlocale/std::codecvt::encoding
- xlocale/std::codecvt::in
- xlocale/std::codecvt::length
- xlocale/std::codecvt::max_length
- xlocale/std::codecvt::out
- xlocale/std::codecvt::unshift
helpviewer_keywords:
- std::codecvt [C++]
- std::codecvt [C++], extern_type
- std::codecvt [C++], intern_type
- std::codecvt [C++], state_type
- std::codecvt [C++], always_noconv
- std::codecvt [C++], do_always_noconv
- std::codecvt [C++], do_encoding
- std::codecvt [C++], do_in
- std::codecvt [C++], do_length
- std::codecvt [C++], do_max_length
- std::codecvt [C++], do_out
- std::codecvt [C++], do_unshift
- std::codecvt [C++], encoding
- std::codecvt [C++], in
- std::codecvt [C++], length
- std::codecvt [C++], max_length
- std::codecvt [C++], out
- std::codecvt [C++], unshift
ms.assetid: 37d3efa1-2b7f-42b6-b04f-7a972c8c2c86
ms.openlocfilehash: 631c3b88be5e2a03798ff6d8e3fb200ad257a8d7
ms.sourcegitcommit: 4b0928a1a497648d0d327579c8262f25ed20d02e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2019
ms.locfileid: "72890183"
---
# <a name="codecvt-class"></a>codecvt 클래스

로캘 패싯으로 사용할 수 있는 개체를 설명 하는 클래스 템플릿입니다. 프로그램 내의 문자를 인코딩하는 데 사용하는 값의 시퀀스와 프로그램 밖의 문자를 인코딩하는 데 사용하는 값 사이의 변환을 제어할 수 있습니다.

## <a name="syntax"></a>구문

```cpp
template <class CharType, class Byte, class StateType>
class codecvt : public locale::facet, codecvt_base;
```

### <a name="parameters"></a>매개 변수

*Chartype* \
문자를 인코딩하기 위해 프로그램 내 사용하는 형식

*바이트* \
프로그램 밖의 문자를 인코딩하는 데 사용되는 형식입니다.

*StateType* \
내부 및 외부 문자 표현 형식 사이의 변환의 중간 상태를 나타내는 데 사용할 수 있는 형식입니다.

## <a name="remarks"></a>주의

클래스 템플릿은 *Chartype* 형식의 값 시퀀스와 *Byte*형식의 값 시퀀스 간의 변환을 제어 하기 위해 [로캘 패싯](../standard-library/locale-class.md#facet_class)으로 사용할 수 있는 개체를 설명 합니다. *StateType* 클래스는 변환에 대 한 특징을, *StateType* 클래스의 개체는 변환 중에 필요한 상태 정보를 저장 합니다.

내부 인코딩은 문자 당 고정 바이트 수를 포함 하는 표현 (일반적으로 **char** 또는 type **wchar_t**)을 사용 합니다.

모든 로캘 패싯과 마찬가지로, 고정 개체 `id`에는 초기값 0이 저장되어 있습니다. 저장된 값에 액세스를 처음 시도하면 `id`에 고유한 양수 값이 저장됩니다.

[do_in](#do_in) 및 [do_out](#do_out)의 템플릿 버전은 항상 `codecvt_base::noconv`를 반환합니다.

C++ 표준 라이브러리는 여러 명시적 특수화를 정의합니다.

```cpp
template<>
codecvt<wchar_t, char, mbstate_t>
```

**wchar_t** 와 **char** 시퀀스 간을 변환 합니다.

```cpp
template<>
codecvt<char16_t, char, mbstate_t>
```

u t f-16으로 인코딩된 `char16_t` 시퀀스와 u t f-8로 인코딩된 **문자** 시퀀스로 변환 합니다.

```cpp
template<>
codecvt<char32_t, char, mbstate_t>
```

u t f-32 (UCS-4)로 인코딩된 `char32_t` 시퀀스와 u t f-8로 인코딩된 **문자** 시퀀스로 변환 합니다.

### <a name="constructors"></a>생성자

|생성자|설명|
|-|-|
|[codecvt](#codecvt)|변환을 처리할 로캘 패싯으로 사용할 `codecvt` 클래스 개체의 생성자입니다.|

### <a name="typedefs"></a>형식 정의

|형식 이름|설명|
|-|-|
|[extern_type](#extern_type)|외부 표현에 사용되는 문자 형식입니다.|
|[intern_type](#intern_type)|내부 표현에 사용되는 문자 형식입니다.|
|[state_type](#state_type)|내부 및 외부 표현 사이의 변환 중간 상태를 나타내는 데 사용하는 문자 형식입니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|설명|
|-|-|
|[always_noconv](#always_noconv)|변환을 수행해야 하는지 여부를 테스트합니다.|
|[do_always_noconv](#do_always_noconv)|변환을 수행해야 하는지 여부를 테스트하기 위해 호출하는 가상 함수입니다.|
|[do_encoding](#do_encoding)|`Byte` 스트림의 인코딩이 상태에 의존 하는지 여부, 사용 된 `Byte` 값과 생성 된 `CharType` 값 사이의 비율이 일정 한지 여부를 테스트 하 고, 그럴 경우 해당 비율 값을 결정 하는 가상 함수입니다.|
|[do_in](#do_in)|내부 `Byte` 값의 시퀀스를 외부 `CharType` 값의 시퀀스로 변환 하기 위해 호출 하는 가상 함수입니다.|
|[do_length](#do_length)|외부 `Byte` 값의 지정 된 시퀀스에서 `Byte` 값의 개수를 결정 하는 가상 함수는 지정 된 수의 내부 `CharType` 값 보다 많이 생성 되 고 `Byte` 값의 수를 반환 합니다.|
|[do_max_length](#do_max_length)|하나의 내부 `CharType`을 만드는 데 필요한 외부 바이트의 최대 수를 반환하는 가상 함수입니다.|
|[do_out](#do_out)|내부 `CharType` 값의 시퀀스를 외부 바이트 시퀀스로 변환 하기 위해 호출 하는 가상 함수입니다.|
|[do_unshift](#do_unshift)|`Byte` 값 시퀀스에서 마지막 문자를 완료 하기 위해 상태 의존 변환에 필요한 `Byte` 값을 제공 하기 위해 호출 하는 가상 함수입니다.|
|[encoding](#encoding)|`Byte` 스트림의 인코딩이 상태에 의존 하는지 여부, 사용 된 `Byte` 값과 생성 된 `CharType` 값 사이의 비율이 일정 한지 여부를 테스트 하 고, 해당 비율 값을 결정 합니다.|
|[in](#in)|`Byte` 값 시퀀스의 외부 표현을 `CharType` 값 시퀀스의 내부 표현으로 변환 합니다.|
|[length](#length)|외부 `Byte` 값의 지정 된 시퀀스에서 지정 된 개수의 내부 `CharType` 값 보다 많은 `Byte` 값이 생성 되 고 해당 `Byte` 값 수를 반환 하는 값을 결정 합니다.|
|[max_length](#max_length)|내부 `CharType`하나를 생성 하는 데 필요한 외부 `Byte` 값의 최대 수를 반환 합니다.|
|[out](#out)|내부 `CharType` 값의 시퀀스를 외부 `Byte` 값의 시퀀스로 변환 합니다.|
|[unshift](#unshift)|`Byte` 값 시퀀스에서 마지막 문자를 완료 하기 위해 상태 의존 변환에 필요한 외부 `Byte` 값을 제공 합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<locale>

**네임스페이스:** std

## <a name="always_noconv"></a>  codecvt::always_noconv

변환을 수행 해야 하는지 여부를 테스트 합니다.

```cpp
bool always_noconv() const throw();
```

### <a name="return-value"></a>반환 값

변환을 수행 하지 않아도 되는 경우 **true** 인 부울 값입니다. 하나 이상의 작업을 수행 해야 하는 경우 **false** 입니다.

### <a name="remarks"></a>주의

멤버 함수는 [do_always_noconv](#do_always_noconv)를 반환합니다.

### <a name="example"></a>예제

```cpp
// codecvt_always_noconv.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   bool result1 = use_facet<codecvt<char, char, mbstate_t> >
      ( loc ).always_noconv( );

   if ( result1 )
      cout << "No conversion is needed." << endl;
   else
      cout << "At least one conversion is required." << endl;

   bool result2 = use_facet<codecvt<wchar_t, char, mbstate_t> >
      ( loc ).always_noconv( );

   if ( result2 )
      cout << "No conversion is needed." << endl;
   else
      cout << "At least one conversion is required." << endl;
}
```

```Output
No conversion is needed.
At least one conversion is required.
```

## <a name="codecvt"></a>  codecvt::codecvt

변환을 처리할 로캘 패싯으로 사용하는 codecvt 클래스 개체의 생성자입니다.

```cpp
explicit codecvt(size_t refs = 0);
```

### <a name="parameters"></a>매개 변수

*refs* \
개체에 대한 메모리 관리 형식을 지정하는 데 사용하는 정수값입니다.

### <a name="remarks"></a>주의

*Refs* 매개 변수에 사용할 수 있는 값은 다음과 같습니다.

- 0: 개체를 포함하는 로캘에 의해 개체의 수명이 관리됩니다.

- 1: 개체의 수명을 수동으로 관리해야 합니다.

- 2: 이러한 값은 정의 되지 않습니다.

생성자는 [locale:: facet](../standard-library/locale-class.md#facet_class)`(refs)`를 사용 하 여 `locale::facet` 기본 개체를 초기화 합니다.

## <a name="do_always_noconv"></a>  codecvt::do_always_noconv

변환을 수행 해야 하는지 여부를 테스트 하기 위해 호출 하는 가상 함수입니다.

```cpp
virtual bool do_always_noconv() const throw();
```

### <a name="return-value"></a>반환 값

[Do_in](#do_in) 또는 [do_out](#do_out) 에 대 한 모든 호출이 `noconv`반환 하는 경우에만 보호 된 가상 멤버 함수에서 **true** 를 반환 합니다.

템플릿 버전은 항상 **true**를 반환합니다.

### <a name="example"></a>예제

`do_always_noconv`를 호출하는 [always_noconv](#always_noconv)에 대한 예제를 참조하세요.

## <a name="do_encoding"></a>  codecvt::do_encoding

`Byte` 스트림의 인코딩이 상태에 의존 하는지 여부, 사용 된 `Byte` 값과 생성 된 `CharType` 값 사이의 비율이 일정 한지 여부를 테스트 하는 가상 함수입니다. 해당 비율 값을 결정 합니다.

```cpp
virtual int do_encoding() const throw();
```

### <a name="return-value"></a>반환 값

보호된 가상 멤버 함수는 다음을 반환합니다.

- `extern_type` 형식의 시퀀스 인코딩이 상태에 종속 되는 경우-1입니다.

- 0: 인코딩에 다양한 길이의 시퀀스가 포함된 경우

- *N*: 인코딩에 *N* 길이의 시퀀스만 포함된 경우

### <a name="example"></a>예제

`do_encoding`을 호출하는 [encoding](#encoding)에 대한 예제를 참조하세요.

## <a name="do_in"></a>  codecvt::do_in

외부 `Byte` 값의 시퀀스를 내부 `CharType` 값의 시퀀스로 변환 하기 위해 호출 하는 가상 함수입니다.

```cpp
virtual result do_in(
    StateType& state,
    const Byte* first1,
    const Byte* last1,
    const Byte*& next1,
    CharType* first2,
    CharType* last2,
    CharType*& next2,) const;
```

### <a name="parameters"></a>매개 변수

*상태* \
멤버 함수에 대한 호출 사이에 유지되는 변환 상태입니다.

*first1* \
변환할 시퀀스의 시작 부분에 대한 포인터입니다.

*last1* \
변환할 시퀀스의 끝 부분에 대한 포인터입니다.

*next1* \
변환된 시퀀스의 끝 너머에 있는 포인터로, 변환되지 않은 첫 번째 문자에 대한 포인터입니다.

*first2* \
변환된 시퀀스의 시작 부분에 대한 포인터입니다.

*last2* \
변환된 시퀀스의 끝 부분에 대한 포인터입니다.

*next2* \
마지막으로 변환 된 `CharType` 뒤에 오는 `CharType`에 대 한 포인터로, 대상 시퀀스의 변경 되지 않은 첫 번째 문자에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

작업의 성공, 부분적 성공 또는 실패를 나타내는 반환입니다. 함수에서 다음을 반환합니다.

- 소스 시퀀스의 형식이 잘못 된 경우 `codecvt_base::error` 합니다.

- 함수가 변환을 수행하지 않은 경우 `codecvt_base::noconv`

- 변환이 성공 하면 `codecvt_base::ok` 합니다.

- 소스가 충분 하지 않거나 대상이 충분히 크지 않아 변환에 성공 하는 경우 `codecvt_base::partial` 합니다.

### <a name="remarks"></a>주의

*상태* 는 새 소스 시퀀스의 시작 부분에 있는 초기 변환 상태를 나타내야 합니다. 함수는 성공적인 변환의 현재 상태를 반영하기 위해 필요에 따라 해당 저장 값을 변경합니다. 저장 값은 달리 지정되지 않습니다.

### <a name="example"></a>예제

`do_in`을 호출하는 [in](#in)에 대한 예제를 참조하세요.

## <a name="do_length"></a>  codecvt::do_length

외부 `Byte` 값의 지정 된 시퀀스에서 `Byte` 값의 개수를 결정 하는 가상 함수는 지정 된 수의 내부 `CharType` 값 보다 많이 생성 되 고 `Byte` 값의 수를 반환 합니다.

```cpp
virtual int do_length(
    const StateType& state,
    const Byte* first1,
    const Byte* last1,
    size_t len2) const;
```

### <a name="parameters"></a>매개 변수

*상태* \
멤버 함수에 대한 호출 사이에 유지되는 변환 상태입니다.

*first1* \
외부 시퀀스의 시작 부분에 대한 포인터입니다.

*last1* \
외부 시퀀스의 끝 부분에 대한 포인터입니다.

*len2*\
멤버 함수에서 반환할 수 있는 `Byte` 값의 최대 개수입니다.

### <a name="return-value"></a>반환 값

[`first1`, `last1`)에서 외부 소스 시퀀스에 의해 정의 된 *len2*보다 크지 않은 최대 변환 수를 나타내는 정수입니다.

### <a name="remarks"></a>주의

보호 된 가상 멤버 함수는 *상태* (상태 복사본), 일부 버퍼 `buf`및 포인터 `next1` 및 `next2`에 대 한 `do_in( state, first1, last1, next1, buf, buf + len2, next2)`를 효과적으로 호출 합니다.

그런 다음  -  `buf` `next2` 반환 합니다. 따라서 [`first1`, `last1`)의 원본 시퀀스에 정의 된 *len2*보다 크지 않은 최대 변환 수를 계산 합니다.

템플릿 버전은 항상 *last1* - *first1* 및 *len2*중 작은 값을 반환 합니다.

### <a name="example"></a>예제

`do_length`를 호출 하는 [length](#length)의 예제를 참조 하세요.

## <a name="do_max_length"></a>  codecvt::do_max_length

내부 `CharType`하나를 생성 하는 데 필요한 외부 `Byte` 값의 최대 개수를 반환 하는 가상 함수입니다.

```cpp
virtual int do_max_length() const throw();
```

### <a name="return-value"></a>반환 값

하나 `CharType`을 생성 하는 데 필요한 `Byte` 값의 최대 수입니다.

### <a name="remarks"></a>주의

보호 된 가상 멤버 함수는 *first1* 및 *last1*의 임의의 유효한 값에 대해 [do_length](#do_length)`( first1, last1, 1)`에서 반환 될 수 있는 최대 허용 값을 반환 합니다.

### <a name="example"></a>예제

`do_max_length`를 호출하는 [max_length](#max_length)에 대한 예제를 참조하세요.

## <a name="do_out"></a>  codecvt::do_out

내부 `CharType` 값의 시퀀스를 외부 `Byte` 값의 시퀀스로 변환 하기 위해 호출 하는 가상 함수입니다.

```cpp
virtual result do_out(
    StateType& state,
    const CharType* first1,
    const CharType* last1,
    const CharType*& next1,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>매개 변수

*상태* \
멤버 함수에 대한 호출 사이에 유지되는 변환 상태입니다.

*first1* \
변환할 시퀀스의 시작 부분에 대한 포인터입니다.

*last1* \
변환할 시퀀스의 끝 부분에 대한 포인터입니다.

*next1* \
마지막 `CharType` 변환 된 후 변환 되지 않은 첫 번째 `CharType`에 대 한 포인터를 참조 합니다.

*first2* \
변환된 시퀀스의 시작 부분에 대한 포인터입니다.

*last2* \
변환된 시퀀스의 끝 부분에 대한 포인터입니다.

*next2* \
마지막 `Byte` 변환 된 후 변환 되지 않은 첫 번째 `Byte`에 대 한 포인터를 참조 합니다.

### <a name="return-value"></a>반환 값

함수에서 다음을 반환합니다.

- 소스 시퀀스의 형식이 잘못 된 경우 `codecvt_base::error` 합니다.

- 함수가 변환을 수행하지 않은 경우 `codecvt_base::noconv`

- 변환이 성공 하면 `codecvt_base::ok` 합니다.

- 소스가 충분 하지 않거나 변환이 성공 하기에 충분 하지 않은 경우 `codecvt_base::partial` 합니다.

### <a name="remarks"></a>주의

*상태* 는 새 소스 시퀀스의 시작 부분에 있는 초기 변환 상태를 나타내야 합니다. 함수는 성공적인 변환의 현재 상태를 반영하기 위해 필요에 따라 해당 저장 값을 변경합니다. 저장 값은 달리 지정되지 않습니다.

### <a name="example"></a>예제

`do_out`을 호출하는 [out](#out)에 대한 예제를 참조하세요.

## <a name="do_unshift"></a>  codecvt::do_unshift

`Byte` 값 시퀀스에서 마지막 문자를 완료 하기 위해 상태 의존 변환에 필요한 `Byte` 값을 제공 하기 위해 호출 하는 가상 함수입니다.

```cpp
virtual result do_unshift(
    StateType& state,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>매개 변수

*상태* \
멤버 함수에 대한 호출 사이에 유지되는 변환 상태입니다.

*first2* \
대상 범위에서 첫 번째 위치에 대한 포인터입니다.

*last2* \
대상 범위에서 마지막 위치에 대한 포인터입니다.

*next2* \
대상 시퀀스의 변경되지 않은 첫 번째 요소에 대한 포인터입니다.

### <a name="return-value"></a>반환 값

함수에서 다음을 반환합니다.

- *상태가* 잘못 된 상태를 나타내는 경우 `codecvt_base::error`

- 함수가 변환을 수행하지 않은 경우 `codecvt_base::noconv`

- 변환에 성공 하는 경우 `codecvt_base::ok`

- 변환이 성공 하기에는 대상이 충분히 크지 않은 경우 `codecvt_base::partial` 합니다.

### <a name="remarks"></a>주의

보호 된 가상 멤버 함수는 종료 요소 `Byte`(0)를 제외 하 고 원본 요소 `CharType`(0)을 [`first2`, `last2`) 내에 저장 하는 대상 시퀀스로 변환 하려고 합니다. 항상 *next2* 에 대상 시퀀스의 변경 되지 않은 첫 번째 요소에 대 한 포인터를 저장 합니다.

_*State*는 새 소스 시퀀스의 시작 부분에 있는 초기 변환 상태를 나타내야 합니다. 함수는 성공적인 변환의 현재 상태를 반영하기 위해 필요에 따라 해당 저장 값을 변경합니다. 일반적으로 소스 요소 `CharType` (0)을 변환 하면 초기 변환 상태에서 현재 상태를 유지 합니다.

### <a name="example"></a>예제

`do_unshift`를 호출하는 [unshift](#unshift)에 대한 예제를 참조하세요.

## <a name="encoding"></a>  codecvt::encoding

`Byte` 스트림의 인코딩이 상태에 의존 하는지 여부, 사용 된 `Byte` 값과 생성 된 `CharType` 값 사이의 비율이 일정 한지 여부를 테스트 하 고, 해당 비율 값을 결정 합니다.

```cpp
int encoding() const throw();
```

### <a name="return-value"></a>반환 값

반환 값이 양수 이면이 값은 `CharType` 문자를 생성 하는 데 필요한 `Byte` 문자의 상수 수입니다.

보호된 가상 멤버 함수는 다음을 반환합니다.

- `extern_type` 형식의 시퀀스 인코딩이 상태에 종속 되는 경우-1입니다.

- 0: 인코딩에 다양한 길이의 시퀀스가 포함된 경우

- *N*: 인코딩에 *N* 길이의 시퀀스만 포함된 경우

### <a name="remarks"></a>주의

멤버 함수는 [do_encoding](#do_encoding)을 반환합니다.

### <a name="example"></a>예제

```cpp
// codecvt_encoding.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   int result1 = use_facet<codecvt<char, char, mbstate_t> > ( loc ).encoding ( );
   cout << result1 << endl;
   result1 = use_facet<codecvt<wchar_t, char, mbstate_t> > ( loc ).encoding( );
   cout << result1 << endl;
   result1 = use_facet<codecvt<char, wchar_t, mbstate_t> > ( loc ).encoding( );
   cout << result1 << endl;
}
```

```Output
1
1
1
```

## <a name="extern_type"></a>  codecvt::extern_type

외부 표현에 사용되는 문자 형식입니다.

```cpp
typedef Byte extern_type;
```

### <a name="remarks"></a>주의

이 형식은 템플릿 매개 변수 `Byte`의 동의어입니다.

## <a name="in"></a>  codecvt::in

`Byte` 값 시퀀스의 외부 표현을 `CharType` 값 시퀀스의 내부 표현으로 변환 합니다.

```cpp
result in(
    StateType& state,
    const Byte* first1,
    const Byte* last1,
    const Byte*& next1,
    CharType* first2,
    CharType* last2,
    CharType*& next2,) const;
```

### <a name="parameters"></a>매개 변수

*상태* \
멤버 함수에 대한 호출 사이에 유지되는 변환 상태입니다.

*first1* \
변환할 시퀀스의 시작 부분에 대한 포인터입니다.

*last1* \
변환할 시퀀스의 끝 부분에 대한 포인터입니다.

*next1* \
변환된 시퀀스의 끝 너머에 있는 포인터로, 변환되지 않은 첫 번째 문자에 대한 포인터입니다.

*first2* \
변환된 시퀀스의 시작 부분에 대한 포인터입니다.

*last2* \
변환된 시퀀스의 끝 부분에 대한 포인터입니다.

*next2* \
대상 시퀀스의 변경 되지 않은 첫 번째 문자로 `Chartype` 마지막으로 변환 된 후에 제공 되는 `CharType`에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

작업의 성공, 부분적 성공 또는 실패를 나타내는 반환입니다. 함수에서 다음을 반환합니다.

- 소스 시퀀스의 형식이 잘못 된 경우 `codecvt_base::error` 합니다.

- 함수가 변환을 수행하지 않은 경우 `codecvt_base::noconv`

- 변환이 성공 하면 `codecvt_base::ok` 합니다.

- 소스가 충분 하지 않거나 변환이 성공 하기에 충분 하지 않은 경우 `codecvt_base::partial` 합니다.

### <a name="remarks"></a>주의

*상태* 는 새 소스 시퀀스의 시작 부분에 있는 초기 변환 상태를 나타내야 합니다. 함수는 성공적인 변환의 현재 상태를 반영하기 위해 필요에 따라 해당 저장 값을 변경합니다. 부분 변환 후에는 새 문자가 도착할 때 변환을 다시 시작할 수 있도록 *상태* 를로 설정 해야 합니다.

멤버 함수는 [do_in](#do_in)`( state, first1,  last1,  next1, first2, last2,  next2)`을 반환 합니다.

### <a name="example"></a>예제

```cpp
// codecvt_in.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
using namespace std;
#define LEN 90
int main( )
{
   char* pszExt = "This is the string to be converted!";
   wchar_t pwszInt [LEN+1];
   memset(&pwszInt[0], 0, (sizeof(wchar_t))*(LEN+1));
   const char* pszNext;
   wchar_t* pwszNext;
   mbstate_t state = {0};
   locale loc("C");//English_Britain");//German_Germany
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >
     ( loc ).in( state,
          pszExt, &pszExt[strlen(pszExt)], pszNext,
          pwszInt, &pwszInt[strlen(pszExt)], pwszNext );
   pwszInt[strlen(pszExt)] = 0;
   wcout << ( (res!=codecvt_base::error)  L"It worked! " : L"It didn't work! " )
   << L"The converted string is:\n ["
   << &pwszInt[0]
   << L"]" << endl;
   exit(-1);
}
```

```Output
It worked! The converted string is:
[This is the string to be converted!]
```

## <a name="intern_type"></a>  codecvt::intern_type

내부 표현에 사용되는 문자 형식입니다.

```cpp
typedef CharType intern_type;
```

### <a name="remarks"></a>주의

이 형식은 템플릿 매개 변수 `CharType`의 동의어입니다.

## <a name="length"></a>  codecvt::length

외부 `Byte` 값의 지정 된 시퀀스에서 지정 된 개수의 내부 `CharType` 값 보다 많은 `Byte` 값이 생성 되 고 해당 `Byte` 값 수를 반환 하는 값을 결정 합니다.

```cpp
int length(
    const StateType& state,
    const Byte* first1,
    const Byte* last1,
    size_t len2) const;
```

### <a name="parameters"></a>매개 변수

*상태* \
멤버 함수에 대한 호출 사이에 유지되는 변환 상태입니다.

*first1* \
외부 시퀀스의 시작 부분에 대한 포인터입니다.

*last1* \
외부 시퀀스의 끝 부분에 대한 포인터입니다.

*len2*\
멤버 함수에서 반환할 수 있는 최대 바이트 수입니다.

### <a name="return-value"></a>반환 값

[`first1`, `last1`)에서 외부 소스 시퀀스에 의해 정의 된 *len2*보다 크지 않은 최대 변환 수를 나타내는 정수입니다.

### <a name="remarks"></a>주의

멤버 함수는 [do_length](#do_length)`( state, first1, last1, len2)`을 반환 합니다.

### <a name="example"></a>예제

```cpp
// codecvt_length.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
using namespace std;
#define LEN 90
int main( )
{
   char* pszExt = "This is the string whose length is to be measured!";
   mbstate_t state = {0};
   locale loc("C");//English_Britain");//German_Germany
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >
     ( loc ).length( state,
          pszExt, &pszExt[strlen(pszExt)], LEN );
   cout << "The length of the string is: ";
   wcout << res;
   cout << "." << endl;
   exit(-1);
}
```

```Output
The length of the string is: 50.
```

## <a name="max_length"></a>  codecvt::max_length

내부 `CharType`하나를 생성 하는 데 필요한 외부 `Byte` 값의 최대 수를 반환 합니다.

```cpp
int max_length() const throw();
```

### <a name="return-value"></a>반환 값

하나 `CharType`을 생성 하는 데 필요한 `Byte` 값의 최대 수입니다.

### <a name="remarks"></a>주의

멤버 함수는 [do_max_length](#do_max_length)를 반환합니다.

### <a name="example"></a>예제

```cpp
// codecvt_max_length.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc( "C");//English_Britain" );//German_Germany
   int res = use_facet<codecvt<char, char, mbstate_t> >
     ( loc ).max_length( );
   wcout << res << endl;
}
```

```Output
1
```

## <a name="out"></a>  codecvt::out

내부 `CharType` 값의 시퀀스를 외부 `Byte` 값의 시퀀스로 변환 합니다.

```cpp
result out(
    StateType& state,
    const CharType* first1,
    const CharType* last1,
    const CharType*& next1,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>매개 변수

*상태* \
멤버 함수에 대한 호출 사이에 유지되는 변환 상태입니다.

*first1* \
변환할 시퀀스의 시작 부분에 대한 포인터입니다.

*last1* \
변환할 시퀀스의 끝 부분에 대한 포인터입니다.

*next1* \
마지막 `CharType` 변환 된 후 `CharType` 변환 되지 않은 첫 번째의 포인터에 대 한 참조입니다.

*first2* \
변환된 시퀀스의 시작 부분에 대한 포인터입니다.

*last2* \
변환된 시퀀스의 끝 부분에 대한 포인터입니다.

*next2* \
마지막으로 변환 된 `Byte` 후 `Byte` 변환 되지 않은 첫 번째에 대 한 포인터에 대 한 참조입니다.

### <a name="return-value"></a>반환 값

멤버 함수는 [do_out](#do_out)`( state, first1, last1, next1, first2, last2, next2)`을 반환 합니다.

### <a name="remarks"></a>주의

자세한 내용은 [codecvt::do_out](#do_out)을 참조하세요.

### <a name="example"></a>예제

```cpp
// codecvt_out.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
#include <wchar.h>
using namespace std;
#define LEN 90
int main( )
{
   char pszExt[LEN+1];
   wchar_t *pwszInt = L"This is the wchar_t string to be converted.";
   memset( &pszExt[0], 0, ( sizeof( char ) )*( LEN+1 ) );
   char* pszNext;
   const wchar_t* pwszNext;
   mbstate_t state;
   locale loc("C");//English_Britain");//German_Germany
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >
      ( loc ).out( state,
      pwszInt, &pwszInt[wcslen( pwszInt )], pwszNext ,
      pszExt, &pszExt[wcslen( pwszInt )], pszNext );
   pszExt[wcslen( pwszInt )] = 0;
   cout << ( ( res!=codecvt_base::error )  "It worked: " : "It didn't work: " )
   << "The converted string is:\n ["
   << &pszExt[0]
   << "]" << endl;
}
```

```Output
It worked: The converted string is:
[This is the wchar_t string to be converted.]
```

## <a name="state_type"></a>  codecvt::state_type

내부 및 외부 표현 사이의 변환 중간 상태를 나타내는 데 사용하는 문자 형식입니다.

```cpp
typedef StateType state_type;
```

### <a name="remarks"></a>주의

이 형식은 템플릿 매개 변수 `StateType`의 동의어입니다.

## <a name="unshift"></a>  codecvt::unshift

`Byte` 값 시퀀스에서 마지막 문자를 완료 하기 위해 상태 의존 변환에 필요한 `Byte` 값을 제공 합니다.

```cpp
result unshift(
    StateType& state,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>매개 변수

*상태* \
멤버 함수에 대한 호출 사이에 유지되는 변환 상태입니다.

*first2* \
대상 범위에서 첫 번째 위치에 대한 포인터입니다.

*last2* \
대상 범위에서 마지막 위치에 대한 포인터입니다.

*next2* \
대상 시퀀스의 변경되지 않은 첫 번째 요소에 대한 포인터입니다.

### <a name="return-value"></a>반환 값

함수에서 다음을 반환합니다.

- 상태가 잘못 된 상태를 나타내는 경우 `codecvt_base::error` 합니다.

- 함수가 변환을 수행하지 않은 경우 `codecvt_base::noconv`

- 변환이 성공 하면 `codecvt_base::ok` 합니다.

- 변환이 성공 하기에는 대상이 충분히 크지 않은 경우 `codecvt_base::partial` 합니다.

### <a name="remarks"></a>주의

보호 된 가상 멤버 함수는 종료 요소 `Byte`(0)를 제외 하 고 원본 요소 `CharType`(0)을 [`first2`, `last2`) 내에 저장 하는 대상 시퀀스로 변환 하려고 합니다. 항상 *next2* 에 대상 시퀀스의 변경 되지 않은 첫 번째 요소에 대 한 포인터를 저장 합니다.

*상태* 는 새 소스 시퀀스의 시작 부분에 있는 초기 변환 상태를 나타내야 합니다. 함수는 성공적인 변환의 현재 상태를 반영하기 위해 필요에 따라 해당 저장 값을 변경합니다. 일반적으로 소스 요소 `CharType` (0)을 변환 하면 초기 변환 상태에서 현재 상태를 유지 합니다.

멤버 함수는 [do_unshift](#do_unshift)`( state, first2, last2, next2 )`을 반환 합니다.

## <a name="see-also"></a>참조

[\<locale>](../standard-library/locale.md)\
[코드 페이지](../c-runtime-library/code-pages.md)\
[로캘 이름, 언어 및 국가/지역 문자열](../c-runtime-library/locale-names-languages-and-country-region-strings.md)\
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)
