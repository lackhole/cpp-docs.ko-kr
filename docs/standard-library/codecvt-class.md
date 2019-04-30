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
ms.openlocfilehash: be1075da65284ac3f9672a839622b59c8926bfb9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405240"
---
# <a name="codecvt-class"></a>codecvt 클래스

로캘 패싯으로 사용할 수 있는 개체를 설명하는 템플릿 클래스입니다. 프로그램 내의 문자를 인코딩하는 데 사용하는 값의 시퀀스와 프로그램 밖의 문자를 인코딩하는 데 사용하는 값 사이의 변환을 제어할 수 있습니다.

## <a name="syntax"></a>구문

```cpp
template <class CharType, class Byte, class StateType>
class codecvt : public locale::facet, codecvt_base;
```

### <a name="parameters"></a>매개 변수

*CharType*<br/>
문자를 인코딩하기 위해 프로그램 내 사용하는 형식

*Byte*<br/>
프로그램 밖의 문자를 인코딩하는 데 사용되는 형식입니다.

*StateType*<br/>
내부 및 외부 문자 표현 형식 사이의 변환의 중간 상태를 나타내는 데 사용할 수 있는 형식입니다.

## <a name="remarks"></a>설명

로 사용 될 수 있는 개체를 설명 하는 템플릿 클래스는 [로캘 패싯](../standard-library/locale-class.md#facet_class)형식의 값 시퀀스 간의 변환을 제어 하기 위해 *CharType* 형식의 값 시퀀스와 *바이트*. 클래스 *StateType* 변환-및 클래스의 개체를 지정 *StateType* 변환 하는 동안 필요한 상태 정보를 저장 합니다.

내부 인코딩은 표현을 사용 하 여는 문자당 바이트의 고정된 된 수를 사용 하 여 일반적으로 입력 하거나 **char** 종류나 **wchar_t**합니다.

모든 로캘 패싯과 마찬가지로, 고정 개체 `id`에는 초기값 0이 저장되어 있습니다. 저장된 값에 액세스를 처음 시도하면 `id`에 고유한 양수 값이 저장됩니다.

[do_in](#do_in) 및 [do_out](#do_out)의 템플릿 버전은 항상 `codecvt_base::noconv`를 반환합니다.

C++ 표준 라이브러리는 여러 명시적 특수화를 정의합니다.

```cpp
template<>
codecvt<wchar_t, char, mbstate_t>
```

사이 변환 **wchar_t** 하 고 **char** 시퀀스입니다.

```cpp
template<>
codecvt<char16_t, char, mbstate_t>
```

사이 변환 `char16_t` 시퀀스를 u t F-16으로 인코드된 및 **char** 시퀀스를 u t F-8로 인코딩됩니다.

```cpp
template<>
codecvt<char32_t, char, mbstate_t>
```

사이 변환 `char32_t` (u c S-4) UTF-32로 인코딩된 시퀀스 및 **char** 시퀀스를 u t F-8로 인코딩됩니다.

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
|[do_encoding](#do_encoding)|`Byte` 스트림의 인코딩이 상태에 의존하는지 여부, 사용한 `Byte`와 만들어진 `CharType`의 비율이 일정한지 여부를 테스트하고, 그럴 경우, 해당 비율 값을 결정하는 가상 함수입니다.|
|[do_in](#do_in)|내부 `Byte`의 시퀀스를 외부 `CharType`의 시퀀스로 변환하기 위해 호출하는 가상 함수입니다.|
|[do_length](#do_length)|외부 `Byte`의 지정된 시퀀스 중 몇 `Byte`가 몇 개 이하의 내부 `CharType`을 만들고 같은 수의 `Byte`를 반환하는지를 결정하는 가상 함수입니다.|
|[do_max_length](#do_max_length)|하나의 내부 `CharType`을 만드는 데 필요한 외부 바이트의 최대 수를 반환하는 가상 함수입니다.|
|[do_out](#do_out)|내부 `CharType`의 시퀀스를 외부 바이트의 시퀀스로 변환하기 위해 호출하는 가상 함수입니다.|
|[do_unshift](#do_unshift)|`Byte`의 시퀀스에서 마지막 문자를 완료하기 위해 상태 의존 변환에 필요한 `Byte`를 제공하기 위해 호출하는 가상 함수입니다.|
|[encoding](#encoding)|`Byte` 스트림의 인코딩이 상태에 의존하는지 여부, 사용한 `Byte`와 만들어진 `CharType`의 비율이 일정한지 여부를 테스트하고, 그럴 경우, 해당 비율 값을 결정합니다.|
|[in](#in)|`Byte`의 시퀀스의 외부 표현을 `CharType`의 시퀀스의 내부 표현으로 변환합니다.|
|[length](#length)|외부 `Byte`의 지정된 시퀀스 중 몇 `Byte`가 몇 개 이하의 내부 `CharType`을 만들고 같은 수의 `Byte`를 반환하는지를 결정합니다.|
|[max_length](#max_length)|하나의 내부 `Byte`을 만드는 데 필요한 외부 `CharType`의 최대 수를 반환합니다.|
|[out](#out)|내부 `CharType`을 외부 `Byte`의 시퀀스로 변환합니다.|
|[unshift](#unshift)|`Byte`의 시퀀스에서 마지막 문자를 완료하기 위해 상태 의존 변환에 필요한 외부 `Byte`를 제공합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<locale>

**네임스페이스:** std

## <a name="always_noconv"></a>  codecvt::always_noconv

변환을 수행해야 하는지 여부를 테스트합니다.

```cpp
bool always_noconv() const throw();
```

### <a name="return-value"></a>반환 값

변환을 수행하지 않아도 되는 경우 **true**인 부울 값이고, 하나 이상의 변환을 수행해야 하는 경우 **false**인 부울 값입니다.

### <a name="remarks"></a>설명

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
explicit codecvt(size_t _Refs = 0);
```

### <a name="parameters"></a>매개 변수

*_Refs*<br/>
개체에 대한 메모리 관리 형식을 지정하는 데 사용하는 정수값입니다.

### <a name="remarks"></a>설명

에 대 한 가능한 값을 *_Refs* 매개 변수 및 중요성은:

- 0: 개체의 수명은 포함 하는 로캘에 의해 관리 됩니다.

- 1: 개체의 수명은 수동으로 관리 해야 합니다.

- 2: 이러한 값이 정의 되지 않습니다.

생성자는 초기화 해당 `locale::facet` 사용 하 여 기본 개체 **로캘::**[패싯](../standard-library/locale-class.md#facet_class)(`_Refs`).

## <a name="do_always_noconv"></a>  codecvt::do_always_noconv

변환을 수행해야 하는지 여부를 테스트하기 위해 호출하는 가상 함수입니다.

```cpp
virtual bool do_always_noconv() const throw();
```

### <a name="return-value"></a>반환 값

보호 된 가상 구성원 함수가 반환 **true** 경우에만를 호출할 때마다 [do_in](#do_in) 하거나 [do_out](#do_out) 반환 `noconv`합니다.

템플릿 버전은 항상 **true**를 반환합니다.

### <a name="example"></a>예제

`do_always_noconv`를 호출하는 [always_noconv](#always_noconv)에 대한 예제를 참조하세요.

## <a name="do_encoding"></a>  codecvt::do_encoding

여부를 테스트 하는 가상 함수 인코딩의 `Byte` 스트림 상태가 종속 여부의 비율이 `Byte`사용한 및 `CharType`만들어진 상수 이며, 그렇다면 해당 비율 값을 결정 합니다.

```cpp
virtual int do_encoding() const throw();
```

### <a name="return-value"></a>반환 값

보호된 가상 멤버 함수는 다음을 반환합니다.

- -1로, 경우 형식의 시퀀스의 인코딩을 `extern_type` 상태 다릅니다.

- 0: 인코딩에 다양한 길이의 시퀀스가 포함된 경우

- *N*: 인코딩에 *N* 길이의 시퀀스만 포함된 경우

### <a name="example"></a>예제

`do_encoding`을 호출하는 [encoding](#encoding)에 대한 예제를 참조하세요.

## <a name="do_in"></a>  codecvt::do_in

가상 함수 호출 시퀀스를 외부 변환할 `Byte`내부 시퀀스 `CharType`s입니다.

```cpp
virtual result do_in(
    StateType& _State,
    const Byte* first1,
    const Byte* last1,
    const Byte*& next1,
    CharType* first2,
    CharType* last2,
    CharType*& next2,) const;
```

### <a name="parameters"></a>매개 변수

*_State*<br/>
멤버 함수에 대한 호출 사이에 유지되는 변환 상태입니다.

*first1*<br/>
변환할 시퀀스의 시작 부분에 대한 포인터입니다.

*last1*<br/>
변환할 시퀀스의 끝 부분에 대한 포인터입니다.

*next1*<br/>
변환된 시퀀스의 끝 너머에 있는 포인터로, 변환되지 않은 첫 번째 문자에 대한 포인터입니다.

*first2*<br/>
변환된 시퀀스의 시작 부분에 대한 포인터입니다.

*last2*<br/>
변환된 시퀀스의 끝 부분에 대한 포인터입니다.

*next2*<br/>
에 대 한 포인터를 `CharType` 변환 된 마지막 뒤에 오는 `CharType`, 대상 시퀀스의 첫 번째 변경 되지 않은 문자입니다.

### <a name="return-value"></a>반환 값

작업의 성공, 부분적 성공 또는 실패를 나타내는 반환입니다. 함수에서 다음을 반환합니다.

- `codecvt_base::error` 소스 시퀀스의 형식이 잘못 된 경우 다음을 구성 합니다.

- 함수가 변환을 수행하지 않은 경우 `codecvt_base::noconv`

- `codecvt_base::ok` 변환이 성공 합니다.

- `codecvt_base::partial` 소스가 충분 하지 않은 경우 또는 대상 변환이 성공 하기에 충분히 큰 경우.

### <a name="remarks"></a>설명

*_State* 새 소스 시퀀스의 시작 부분에서 초기 변환 상태를 나타내야 합니다. 함수는 성공적인 변환의 현재 상태를 반영하기 위해 필요에 따라 해당 저장 값을 변경합니다. 저장 값은 달리 지정되지 않습니다.

### <a name="example"></a>예제

`do_in`을 호출하는 [in](#in)에 대한 예제를 참조하세요.

## <a name="do_length"></a>  codecvt::do_length

외부 `Byte`의 지정된 시퀀스 중 몇 `Byte`가 몇 개 이하의 내부 `CharType`을 만들고 같은 수의 `Byte`를 반환하는지를 결정하는 가상 함수입니다.

```cpp
virtual int do_length(
    const StateType& _State,
    const Byte* first1,
    const Byte* last1,
    size_t _Len2) const;
```

### <a name="parameters"></a>매개 변수

*_State*<br/>
멤버 함수에 대한 호출 사이에 유지되는 변환 상태입니다.

*first1*<br/>
외부 시퀀스의 시작 부분에 대한 포인터입니다.

*last1*<br/>
외부 시퀀스의 끝 부분에 대한 포인터입니다.

*_Len2*<br/>
최대 `Byte`멤버 함수에 의해 반환 될 수 있는 s입니다.

### <a name="return-value"></a>반환 값

변환 보다 크지 않은 최대 개수를 나타내는 정수입니다 *_Len2*에서 외부 소스 시퀀스로 정의 된 [ `first1`, `last1`).

### <a name="remarks"></a>설명

보호 된 가상 구성원 함수는 효과적으로 호출한 `do_in`( `_State`, `first1`, `last1`를 `next1`를 `_Buf`를 `_Buf`  +  `_Len2`, `next2`) 에대한 *_State* (상태의 복사본)을 몇 가지 버퍼 `_Buf`, 및 포인터 `next1`고 `next2`입니다.

그런 다음 반환 `next2`  -  `buf`합니다. 따라서 변환 보다 크지 않은 최대 개수가 계산 *_Len2*에서 소스 시퀀스로 정의 된 [ `first1`, `last1`).

템플릿 버전은 항상 중 더 작은 값 반환 *last1* - *first1* 하 고 *_Len2*합니다.

### <a name="example"></a>예제

예를 참조 하세요 [길이](#length)를 호출 하는 `do_length`합니다.

## <a name="do_max_length"></a>  codecvt::do_max_length

외부의 최대 수를 반환 하는 가상 함수 `Byte`하나의 내부를 생성 하는 데 필요한 `CharType`합니다.

```cpp
virtual int do_max_length() const throw();
```

### <a name="return-value"></a>반환 값

최대 `Byte`하나를 생성 하는 데 필요한 `CharType`합니다.

### <a name="remarks"></a>설명

보호 된 가상 멤버 함수에서 반환 될 수 있는 최대 허용 값을 반환 [do_length](#do_length)( `first1`합니다 `last1`, 1)의 유효한 임의 값에 대 한 *first1* 하고*last1*합니다.

### <a name="example"></a>예제

`do_max_length`를 호출하는 [max_length](#max_length)에 대한 예제를 참조하세요.

## <a name="do_out"></a>  codecvt::do_out

내부 `CharType`의 시퀀스를 외부 `Byte`의 시퀀스로 변환하기 위해 호출하는 가상 함수입니다.

```cpp
virtual result do_out(
    StateType& _State,
    const CharType* first1,
    const CharType* last1,
    const CharType*& next1,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>매개 변수

*_State*<br/>
멤버 함수에 대한 호출 사이에 유지되는 변환 상태입니다.

*first1*<br/>
변환할 시퀀스의 시작 부분에 대한 포인터입니다.

*last1*<br/>
변환할 시퀀스의 끝 부분에 대한 포인터입니다.

*next1*<br/>
첫 번째에 대 한 포인터에 대 한 참조 된 `CharType`, 마지막 `CharType` 변환 합니다.

*first2*<br/>
변환된 시퀀스의 시작 부분에 대한 포인터입니다.

*last2*<br/>
변환된 시퀀스의 끝 부분에 대한 포인터입니다.

*next2*<br/>
첫 번째에 대 한 포인터에 대 한 참조 된 `Byte`, 마지막 `Byte` 변환 합니다.

### <a name="return-value"></a>반환 값

함수에서 다음을 반환합니다.

- `codecvt_base::error` 소스 시퀀스의 형식이 잘못 된 경우 다음을 구성 합니다.

- 함수가 변환을 수행하지 않은 경우 `codecvt_base::noconv`

- `codecvt_base::ok` 변환이 성공 합니다.

- `codecvt_base::partial` 소스가 충분 하지 않은 경우 또는 대상 변환이 성공 하기에 충분히 큰 경우.

### <a name="remarks"></a>설명

*_State* 새 소스 시퀀스의 시작 부분에서 초기 변환 상태를 나타내야 합니다. 함수는 성공적인 변환의 현재 상태를 반영하기 위해 필요에 따라 해당 저장 값을 변경합니다. 저장 값은 달리 지정되지 않습니다.

### <a name="example"></a>예제

`do_out`을 호출하는 [out](#out)에 대한 예제를 참조하세요.

## <a name="do_unshift"></a>  codecvt::do_unshift

`Byte`의 시퀀스에서 마지막 문자를 완료하기 위해 상태 의존 변환에 필요한 `Byte`를 제공하기 위해 호출하는 가상 함수입니다.

```cpp
virtual result do_unshift(
    StateType& _State,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>매개 변수

*_State*<br/>
멤버 함수에 대한 호출 사이에 유지되는 변환 상태입니다.

*first2*<br/>
대상 범위에서 첫 번째 위치에 대한 포인터입니다.

*last2*<br/>
대상 범위에서 마지막 위치에 대한 포인터입니다.

*next2*<br/>
대상 시퀀스의 변경되지 않은 첫 번째 요소에 대한 포인터입니다.

### <a name="return-value"></a>반환 값

함수에서 다음을 반환합니다.

- `codecvt_base::error` 경우 _ *상태* 잘못 된 상태를 나타냅니다.

- 함수가 변환을 수행하지 않은 경우 `codecvt_base::noconv`

- `codecvt_base::ok` 변환이 성공 하는 경우

- `codecvt_base::partial` 대상은 변환이 성공 하기에 충분히 큰 경우

### <a name="remarks"></a>설명

보호 된 가상 멤버 함수에서 소스 요소를 변환 하려고 `CharType`(0) 내에 저장 하는 대상 시퀀스 [ `first2`를 `last2`)를 종료 요소를 제외 하 고 `Byte`(0). 항상 저장 *next2* 는 대상 시퀀스의 첫 번째 변경 되지 않은 요소에 대 한 포인터입니다.

_*State*는 새 소스 시퀀스의 시작 부분에 있는 초기 변환 상태를 나타내야 합니다. 함수는 성공적인 변환의 현재 상태를 반영하기 위해 필요에 따라 해당 저장 값을 변경합니다. 일반적으로 소스 요소를 변환 `CharType`(0) 현재 상태가 초기 변환 상태로 유지 합니다.

### <a name="example"></a>예제

`do_unshift`를 호출하는 [unshift](#unshift)에 대한 예제를 참조하세요.

## <a name="encoding"></a>  codecvt::encoding

`Byte` 스트림의 인코딩이 상태에 의존하는지 여부, 사용한 `Byte`와 만들어진 `CharType`의 비율이 일정한지 여부를 테스트하고, 그럴 경우, 해당 비율 값을 결정합니다.

```cpp
int encoding() const throw();
```

### <a name="return-value"></a>반환 값

반환 값이 양수 이면 해당 값은 일정 한 수의 경우 `Byte` 생성 하는 데 필요한 문자는 `CharType` 문자입니다.

보호된 가상 멤버 함수는 다음을 반환합니다.

- -1로, 경우 형식의 시퀀스의 인코딩을 `extern_type` 상태 다릅니다.

- 0: 인코딩에 다양한 길이의 시퀀스가 포함된 경우

- *N*: 인코딩에 *N* 길이의 시퀀스만 포함된 경우

### <a name="remarks"></a>설명

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

### <a name="remarks"></a>설명

이 형식은 템플릿 매개 변수 `Byte`의 동의어입니다.

## <a name="in"></a>  codecvt::in

`Byte`의 시퀀스의 외부 표현을 `CharType`의 시퀀스의 내부 표현으로 변환합니다.

```cpp
result in(
    StateType& _State,
    const Byte* first1,
    const Byte* last1,
    const Byte*& next1,
    CharType* first2,
    CharType* last2,
    CharType*& next2,) const;
```

### <a name="parameters"></a>매개 변수

*_State*<br/>
멤버 함수에 대한 호출 사이에 유지되는 변환 상태입니다.

*first1*<br/>
변환할 시퀀스의 시작 부분에 대한 포인터입니다.

*last1*<br/>
변환할 시퀀스의 끝 부분에 대한 포인터입니다.

*next1*<br/>
변환된 시퀀스의 끝 너머에 있는 포인터로, 변환되지 않은 첫 번째 문자에 대한 포인터입니다.

*first2*<br/>
변환된 시퀀스의 시작 부분에 대한 포인터입니다.

*last2*<br/>
변환된 시퀀스의 끝 부분에 대한 포인터입니다.

*next2*<br/>
에 대 한 포인터를 `CharType` 변환 된 마지막 뒤에 오는 `Chartype` 는 대상 시퀀스의 첫 번째 변경 되지 않은 문자입니다.

### <a name="return-value"></a>반환 값

작업의 성공, 부분적 성공 또는 실패를 나타내는 반환입니다. 함수에서 다음을 반환합니다.

- `codecvt_base::error` 소스 시퀀스의 형식이 잘못 된 경우 다음을 구성 합니다.

- 함수가 변환을 수행하지 않은 경우 `codecvt_base::noconv`

- `codecvt_base::ok` 변환이 성공 합니다.

- `codecvt_base::partial` 소스가 충분 하지 않은 경우 또는 대상 변환이 성공 하기에 충분히 큰 경우.

### <a name="remarks"></a>설명

*_State* 새 소스 시퀀스의 시작 부분에서 초기 변환 상태를 나타내야 합니다. 함수는 성공적인 변환의 현재 상태를 반영하기 위해 필요에 따라 해당 저장 값을 변경합니다. 일부 변환 이후 *_State* 변환이 새 문자가 도착할 때 다시 시작할 수 있도록 설정 해야 합니다.

멤버 함수가 [do_in](#do_in)(`_State`, _ *First1,  last1,  next1, First2, _Llast2,  next2*)를 반환합니다.

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

### <a name="remarks"></a>설명

이 형식은 템플릿 매개 변수 `CharType`의 동의어입니다.

## <a name="length"></a>  codecvt::length

외부 `Byte`의 지정된 시퀀스 중 몇 `Byte`가 몇 개 이하의 내부 `CharType`을 만들고 같은 수의 `Byte`를 반환하는지를 결정합니다.

```cpp
int length(
    const StateType& _State,
    const Byte* first1,
    const Byte* last1,
    size_t _Len2) const;
```

### <a name="parameters"></a>매개 변수

*_State*<br/>
멤버 함수에 대한 호출 사이에 유지되는 변환 상태입니다.

*first1*<br/>
외부 시퀀스의 시작 부분에 대한 포인터입니다.

*last1*<br/>
외부 시퀀스의 끝 부분에 대한 포인터입니다.

*_Len2*<br/>
멤버 함수에서 반환할 수 있는 최대 바이트 수입니다.

### <a name="return-value"></a>반환 값

변환 보다 크지 않은 최대 개수를 나타내는 정수입니다 *_Len2*에서 외부 소스 시퀀스로 정의 된 [ `first1`, `last1`).

### <a name="remarks"></a>설명

멤버 함수가 [do_length](#do_length)(*_State,  first1*, `last1`, `_Len2`)를 반환합니다.

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

하나의 내부 `Byte`을 만드는 데 필요한 외부 `CharType`의 최대 수를 반환합니다.

```cpp
int max_length() const throw();
```

### <a name="return-value"></a>반환 값

최대 `Byte`하나를 생성 하는 데 필요한 `CharType`합니다.

### <a name="remarks"></a>설명

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

내부 `CharType`을 외부 `Byte`의 시퀀스로 변환합니다.

```cpp
result out(
    StateType& _State,
    const CharType* first1,
    const CharType* last1,
    const CharType*& next1,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>매개 변수

*_State*<br/>
멤버 함수에 대한 호출 사이에 유지되는 변환 상태입니다.

*first1*<br/>
변환할 시퀀스의 시작 부분에 대한 포인터입니다.

*last1*<br/>
변환할 시퀀스의 끝 부분에 대한 포인터입니다.

*next1*<br/>
첫 번째에 대 한 포인터에 대 한 참조 된 `CharType` 마지막 `CharType` 변환 합니다.

*first2*<br/>
변환된 시퀀스의 시작 부분에 대한 포인터입니다.

*last2*<br/>
변환된 시퀀스의 끝 부분에 대한 포인터입니다.

*next2*<br/>
첫 번째에 대 한 포인터에 대 한 참조 된 `Byte` 마지막으로 변환한 후 `Byte`합니다.

### <a name="return-value"></a>반환 값

멤버 함수는 [do_out](#do_out)(`_State`, `first1`, `last1`, `next1`, `first2`, `last2`, `next2`)를 반환합니다.

### <a name="remarks"></a>설명

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

### <a name="remarks"></a>설명

이 형식은 템플릿 매개 변수 `StateType`의 동의어입니다.

## <a name="unshift"></a>  codecvt::unshift

제공 된 `Byte`시퀀스의 마지막 문자를 완료 하는 데 상태 의존 변환에 필요한 `Byte`s입니다.

```cpp
result unshift(
    StateType& _State,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>매개 변수

*_State*<br/>
멤버 함수에 대한 호출 사이에 유지되는 변환 상태입니다.

*first2*<br/>
대상 범위에서 첫 번째 위치에 대한 포인터입니다.

*last2*<br/>
대상 범위에서 마지막 위치에 대한 포인터입니다.

*next2*<br/>
대상 시퀀스의 변경되지 않은 첫 번째 요소에 대한 포인터입니다.

### <a name="return-value"></a>반환 값

함수에서 다음을 반환합니다.

- `codecvt_base::error` 상태 경우 잘못 된 상태를 나타냅니다.

- 함수가 변환을 수행하지 않은 경우 `codecvt_base::noconv`

- `codecvt_base::ok` 변환이 성공 합니다.

- `codecvt_base::partial` 대상은 변환이 성공 하기에 충분 되지 않습니다.

### <a name="remarks"></a>설명

보호 된 가상 멤버 함수에서 소스 요소를 변환 하려고 `CharType`(0) 내에 저장 하는 대상 시퀀스 [ `first2`를 `last2`)를 종료 요소를 제외 하 고 `Byte`(0). 항상 저장 *next2* 는 대상 시퀀스의 첫 번째 변경 되지 않은 요소에 대 한 포인터입니다.

*_State* 새 소스 시퀀스의 시작 부분에서 초기 변환 상태를 나타내야 합니다. 함수는 성공적인 변환의 현재 상태를 반영하기 위해 필요에 따라 해당 저장 값을 변경합니다. 일반적으로 소스 요소를 변환 `CharType`(0) 현재 상태가 초기 변환 상태로 유지 합니다.

멤버 함수는 [do_unshift](#do_unshift)(`_State`, `first2`, `last2`, `next2`)를 반환합니다.

## <a name="see-also"></a>참고자료

[\<locale>](../standard-library/locale.md)<br/>
[코드 페이지](../c-runtime-library/code-pages.md)<br/>
[로캘 이름, 언어 및 국가/지역 문자열](../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
