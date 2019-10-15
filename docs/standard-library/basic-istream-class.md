---
title: basic_istream 클래스
ms.date: 11/04/2016
f1_keywords:
- istream/std::basic_istream
- istream/std::basic_istream::gcount
- istream/std::basic_istream::get
- istream/std::basic_istream::getline
- 'istream/std::basic_istream::'
- istream/std::basic_istream::peek
- istream/std::basic_istream::putback
- istream/std::basic_istream::read
- istream/std::basic_istream::readsome
- istream/std::basic_istream::seekg
- istream/std::basic_istream::sentry
- istream/std::basic_istream::swap
- istream/std::basic_istream::sync
- istream/std::basic_istream::tellg
- istream/std::basic_istream::unget
helpviewer_keywords:
- std::basic_istream [C++]
- std::basic_istream [C++], gcount
- std::basic_istream [C++], get
- std::basic_istream [C++], getline
- std::basic_istream [C++], OVERWRITE
- std::basic_istream [C++], peek
- std::basic_istream [C++], putback
- std::basic_istream [C++], read
- std::basic_istream [C++], readsome
- std::basic_istream [C++], seekg
- std::basic_istream [C++], sentry
- std::basic_istream [C++], swap
- std::basic_istream [C++], sync
- std::basic_istream [C++], tellg
- std::basic_istream [C++], unget
ms.assetid: c7c27111-de6d-42b4-95a3-a7e65259bf17
ms.openlocfilehash: d1a76e9c639ac56ca693527543ecff5c597456f0
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68452547"
---
# <a name="basic_istream-class"></a>basic_istream 클래스

이 템플릿 클래스는 문자 특성이 *Tr*([traits_type](../standard-library/basic-ios-class.md#traits_type)이라고도 함) 클래스에 의해 결정되는 `Elem`([char_type](../standard-library/basic-ios-class.md#char_type)이라고도 함) 형식의 요소가 있는 스트림 버퍼에서 요소 및 인코드된 개체의 추출을 제어하는 개체를 설명합니다.

## <a name="syntax"></a>구문

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_istream : virtual public basic_ios<Elem, Tr>
```

## <a name="remarks"></a>설명

[operator>>](#op_gt_gt)를 오버로드하는 대부분의 멤버 함수는 형식이 지정된 입력 함수입니다. 다음 패턴을 따릅니다.

```cpp
iostate state = goodbit;
const sentry ok(*this);

if (ok)
{
    try
    {
        /*extract elements and convert
            accumulate flags in state.
            store a successful conversion*/
    }
    catch (...)
    {
        try
        {
            setstate(badbit);

        }
        catch (...)
        {
        }
        if ((exceptions()& badbit) != 0)
            throw;
    }
}
setstate(state);

return (*this);
```

다른 많은 멤버 함수는 형식이 지정되지 않은 입력 함수입니다. 다음 패턴을 따릅니다.

```cpp
iostate state = goodbit;
count = 0;    // the value returned by gcount
const sentry ok(*this, true);

if (ok)
{
    try
    {
        /* extract elements and deliver
            count extracted elements in count
            accumulate flags in state */
    }
    catch (...)
    {
        try
        {
            setstate(badbit);

        }
        catch (...)
        {
        }
        if ((exceptions()& badbit) != 0)
            throw;
    }
}
setstate(state);
```

두 함수 그룹은 요소를 추출하는 동안 파일 끝에 도달 하는 경우 [setstate](../standard-library/basic-ios-class.md#setstate)(`eofbit`)를 호출합니다.

`basic_istream`< `Elem`, *Tr*> 클래스의 개체는 다음을 저장합니다.

- [basic_ios](../standard-library/basic-ios-class.md)< `Elem`, *Tr*> `.` 클래스의 공용 가상 기준 개체

- 서식이 지정 되지 않은 마지막 입력 작업 (이전 코드에서 `count` 호출)에 대 한 추출 수입니다.

## <a name="example"></a>예제

입력 스트림에 대한 자세한 내용은 [basic_ifstream 클래스](../standard-library/basic-ifstream-class.md)에 대한 예제를 참조하세요.

### <a name="constructors"></a>생성자

|생성자|설명|
|-|-|
|[basic_istream](#basic_istream)|`basic_istream` 형식의 개체를 생성합니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|설명|
|-|-|
|[gcount](#gcount)|서식이 지정되지 않은 마지막 입력 동안 읽은 문자 수를 반환합니다.|
|[get](#get)|입력 스트림에서 하나 이상의 문자를 읽습니다.|
|[getline](#getline)|입력 스트림에서 한 줄을 읽습니다.|
|[ignore](#ignore)|현재 읽기 위치에서 많은 요소를 건너뜁니다.|
|[peek](#peek)|읽을 다음 문자를 반환합니다.|
|[putback](#putback)|지정된 문자를 스트림에 넣습니다.|
|[read](#read)|스트림에서 지정된 개수의 문자를 읽고 배열에 저장합니다.|
|[readsome](#readsome)|버퍼에서 읽기만 합니다.|
|[seekg](#seekg)|스트림에서 읽기 위치를 이동합니다.|
|[sentry](#sentry)|중첩된 클래스는 선언에서 형식이 지정된 입력 함수 및 형식이 지정되지 않은 입력 함수를 구성하는 개체를 설명합니다.|
|[swap](#swap)|이 `basic_istream` 개체를 제공된 `basic_istream` 개체 매개 변수로 교환합니다.|
|[sync](#sync)|스트림과 연결된 입력 디바이스를 스트림 버퍼와 동기화합니다.|
|[tellg](#tellg)|스트림에서 현재 읽기 위치를 보고합니다.|
|[unget](#unget)|가장 최근에 읽은 문자를 다시 스트림에 넣습니다.|

### <a name="operators"></a>연산자

|연산자|설명|
|-|-|
|[operator>>](#op_gt_gt)|입력 스트림에 대해 함수를 호출하거나 입력 스트림에서 형식이 지정된 데이터를 읽습니다.|
|[operator=](#op_eq)|이 개체에 연산자의 오른쪽에 있는 `basic_istream`을 할당합니다. 복사본을 남기지 않는 `rvalue` 참조와 관련된 이동 할당입니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<istream>

**네임스페이스:** std

## <a name="basic_istream"></a>  basic_istream::basic_istream

`basic_istream` 형식의 개체를 생성합니다.

```cpp
explicit basic_istream(
    basic_streambuf<Elem, Tr>* strbuf,
    bool _Isstd = false);

basic_istream(basic_istream&& right);
```

### <a name="parameters"></a>매개 변수

*strbuf*\
[basic_streambuf](../standard-library/basic-streambuf-class.md) 형식의 개체입니다.

*_Isstd*\
표준 스트림 이면 **true** 입니다. 그렇지 않으면 **false**입니다.

*오른쪽*\
복사할 `basic_istream` 개체입니다.

### <a name="remarks"></a>설명

첫 번째 생성자는 [init](../standard-library/basic-ios-class.md#init)(_S `trbuf`)를 호출하여 기본 개체를 초기화합니다. 또한 추출 개수에 0을 저장합니다. 이 추출 개수에 대한 자세한 내용은 [basic_istream Class](../standard-library/basic-istream-class.md) 개요 항목의 설명 섹션을 참조하세요.

두 번째 생성자는 `move( right)`를 호출하여 기본 개체를 초기화합니다. 이 생성자는 또한 추출 개수에 _R `ight.gcount()`를 저장하고, _R `ight`에 대한 추출 개수에 0을 저장합니다.

### <a name="example"></a>예제

입력 스트림에 대한 자세한 내용은 [basic_ifstream::basic_ifstream](../standard-library/basic-ifstream-class.md#basic_ifstream)에 대한 예제를 참조하세요.

## <a name="gcount"></a>  basic_istream::gcount

서식이 지정되지 않은 마지막 입력 동안 읽은 문자 수를 반환합니다.

```cpp
streamsize gcount() const;
```

### <a name="return-value"></a>반환 값

추출 개수입니다.

### <a name="remarks"></a>설명

형식이 지정되지 않은 문자를 읽으려면 [basic_istream::get](#get)을 사용하세요.

### <a name="example"></a>예제

```cpp
// basic_istream_gcount.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   cout << "Type the letter 'a': ";

   ws( cin );
   char c[10];

   cin.get( &c[0],9 );
   cout << c << endl;

   cout << cin.gcount( ) << endl;
}
```

```Input
a
```

```Output
Type the letter 'a': a
1
```

## <a name="get"></a>  basic_istream::get

입력 스트림에서 하나 이상의 문자를 읽습니다.

```cpp
int_type get();

basic_istream<Elem, Tr>& get(Elem& Ch);
basic_istream<Elem, Tr>& get(Elem* str, streamsize count);
basic_istream<Elem, Tr>& get(Elem* str, streamsize count, Elem Delim);

basic_istream<Elem, Tr>& get(basic_streambuf<Elem, Tr>& strbuf);
basic_istream<Elem, Tr>& get(basic_streambuf<Elem, Tr>& strbuf, Elem Delim);
```

### <a name="parameters"></a>매개 변수

*수*\
`strbuf`에서 읽을 문자 수입니다.

*Delim*\
*개수*이전에 발생 한 경우 읽기를 종료 해야 하는 문자입니다.

*문자열*\
쓸 수 있는 문자열입니다.

*Ch*\
가져올 문자입니다.

*strbuf*\
쓸 수 있는 버퍼입니다.

### <a name="return-value"></a>반환 값

매개 변수 없는 형식의 get은 읽은 요소를 정수로서 또는 파일 끝으로서 반환합니다. 나머지 형식은 (* `this`) 스트림을 반환합니다.

### <a name="remarks"></a>설명

형식이 지정되지 않은 이러한 입력 함수 중 첫 번째 함수는 가능한 경우 `rdbuf`-> `sbumpc`를 반환하여 요소를 추출합니다. 아닌 경우 **traits_type::** [eof](../standard-library/char-traits-struct.md#eof)를 반환합니다. 함수가 요소를 추출 하지 않으면 [setstate](../standard-library/basic-ios-class.md#setstate)(`failbit`)를 호출 합니다.

두 번째 함수도 같은 방법으로 [int_type](../standard-library/basic-ios-class.md#int_type) 요소 `meta`를 추출합니다. `meta`가 **traits_type::eof**와 비교 시 같으면 함수는 `setstate`( **failbit**)를 호출합니다. 같지 않으면 `Ch`에 **traits_type::** [to_char_type](../standard-library/char-traits-struct.md#to_char_type)( `meta`)를 저장합니다. 함수는 **\*this**를 반환합니다.

세 번째 함수는 **get**(_ *Str*, `count`, `widen`('\ **n**'))을 반환합니다.

네 번째 함수는 *count* -1 개 요소를 추출 하 여 _ *Str*에서 시작 하는 배열에 저장 합니다. 함수는 항상 추출하여 저장한 요소 뒤에 `char_type`을 저장합니다. 테스트 순서에서 추출은 다음에서 중지됩니다.

- 파일의 끝에 도달하는 경우

- 함수는 *Delim*와 비교 하는 요소를 추출 합니다 .이 경우 요소는 제어 되는 시퀀스로 다시 배치 됩니다.

- 함수는 *count* -1 요소를 추출 합니다.

요소를 추출하지 않는 경우 함수는 `setstate`( **failbit**)를 호출합니다. 어떤 경우든 함수는 **\*this**를 반환합니다.

다섯 번째 함수는 **get**( **strbuf**, `widen`('\ **n**'))을 반환합니다.

여섯 번째 함수는 요소를 추출 하 여 `strbuf`에 삽입 합니다. 추출되지 않은 _ *Delim*과 비교 시 같은 요소에서 또는 파일의 끝에서 추출이 중지됩니다. 또한 삽입이 실패하거나 예외를 throw하면(catch했지만 다시 throw되지 않음) 문제의 요소를 추출하지 않고 중단합니다. 요소를 추출하지 않는 경우 함수는 `setstate`( **failbit**)를 호출합니다. 어떤 경우든 함수는 **\*this**를 반환합니다.

### <a name="example"></a>예제

```cpp
// basic_istream_get.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   char c[10];

   c[0] = cin.get( );
   cin.get( c[1] );
   cin.get( &c[2],3 );
   cin.get( &c[4], 4, '7' );

   cout << c << endl;
}
```

```Output
1111
```

## <a name="getline"></a>  basic_istream::getline

입력 스트림에서 한 줄을 가져옵니다.

```cpp
basic_istream<Elem, Tr>& getline(
    char_type* str,
    streamsize count);

basic_istream<Elem, Tr>& getline(
    char_type* str,
    streamsize count,
    char_type Delim);
```

### <a name="parameters"></a>매개 변수

*수*\
`strbuf`에서 읽을 문자 수입니다.

*Delim*\
*개수*이전에 발생 한 경우 읽기를 종료 해야 하는 문자입니다.

*문자열*\
쓸 수 있는 문자열입니다.

### <a name="return-value"></a>반환 값

스트림( **\*this**)입니다.

### <a name="remarks"></a>설명

형식이 지정되지 않은 이러한 입력 함수의 첫 번째는 **getline**(_ *Str*, `count`, `widen`(' `\`**n**'))을 반환합니다.

두 번째 함수는 *count* -1 개 요소를 추출 하 여 _ *Str*에서 시작 하는 배열에 저장 합니다. 함수는 항상 추출하여 저장한 요소 뒤에 문자열 종결 문자를 저장합니다. 테스트 순서에서 추출은 다음에서 중지됩니다.

- 파일의 끝에 도달하는 경우

- 함수가 *Delim*과 비교 하는 요소를 추출 하는 경우 (이 경우 요소는 다시 배치 되거나 제어 되는 시퀀스에 추가 되지 않습니다.)

- 함수는 *count* -1 요소를 추출 합니다.

요소가 요소를 추출하지 않거나 *count* -1 요소를 추출하는 경우 [setstate](../standard-library/basic-ios-class.md#setstate)(`failbit`)를 호출합니다. 어떤 경우든 함수는 **\*this**를 반환합니다.

### <a name="example"></a>예제

```cpp
// basic_istream_getline.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   char c[10];

   cin.getline( &c[0], 5, '2' );
   cout << c << endl;
}
```

```Output
121
```

## <a name="ignore"></a>  basic_istream::ignore

현재 읽기 위치에서 많은 요소를 건너뜁니다.

```cpp
basic_istream<Elem, Tr>& ignore(
    streamsize count = 1,
    int_type Delim = traits_type::eof());
```

### <a name="parameters"></a>매개 변수

*수*\
현재 읽기 위치에서 건너뛸 요소의 수입니다.

*Delim*\
Count 이전에 발생 한 경우에서 `ignore` 를 반환 하 고 *Delim* 이후의 모든 요소를 읽을 수 있도록 하는 요소입니다.

### <a name="return-value"></a>반환 값

스트림( **\*this**)입니다.

### <a name="remarks"></a>설명

형식이 지정 되지 않은 입력 함수는 요소 *수를 계산* 하 고 삭제 합니다. 그러나 *count* 가 **numeric_limits\<int >:: max**인 경우에는 임의로 크기가 됩니다. `Ch` 추출은 파일의 끝 이나 요소에서 일찍 중지 되며, **traits_type::** [to_int_type](../standard-library/char-traits-struct.md#to_int_type)( `Ch`)는 *Delim* (추출 됨)와 동일 하 게 비교 됩니다. 함수는 **\*this**를 반환합니다.

### <a name="example"></a>예제

```cpp
// basic_istream_ignore.cpp
// compile with: /EHsc
#include <iostream>
int main( )
{
   using namespace std;
   char chararray[10];
   cout << "Type 'abcdef': ";
   cin.ignore( 5, 'c' );
   cin >> chararray;
   cout << chararray;
}
```

```Output
Type 'abcdef': abcdef
def
```

## <a name="op_gt_gt"></a>  basic\_istream::operator>>

입력 스트림에 대해 함수를 호출하거나 입력 스트림에서 형식이 지정된 데이터를 읽습니다.

```cpp
basic_istream& operator>>(basic_istream& (* Pfn)(basic_istream&));
basic_istream& operator>>(ios_base& (* Pfn)(ios_base&));
basic_istream& operator>>(basic_ios<Elem, Tr>& (* Pfn)(basic_ios<Elem, Tr>&));
basic_istream& operator>>(basic_streambuf<Elem, Tr>* strbuf);
basic_istream& operator>>(bool& val);
basic_istream& operator>>(short& val);
basic_istream& operator>>(unsigned short& val);
basic_istream& operator>>(int& val);
basic_istream& operator>>(unsigned int& val);
basic_istream& operator>>(long& val);
basic_istream& operator>>(unsigned long& val);
basic_istream& operator>>(long long& val);
basic_istream& operator>>(unsigned long long& val);
basic_istream& operator>>(void *& val);
basic_istream& operator>>(float& val);
basic_istream& operator>>(double& val);
basic_istream& operator>>(long double& val);
```

### <a name="parameters"></a>매개 변수

*Pfn*\
함수 포인터입니다.

*strbuf*\
`stream_buf` 형식의 개체입니다.

*짧은*\
스트림에서 읽은 값입니다.

### <a name="return-value"></a>반환 값

스트림( **\*this**)입니다.

### <a name="remarks"></a>설명

Istream \<> 헤더는 여러 전역 추출 연산자도 정의 합니다. 자세한 내용은 [operator>> (\<istream>)](../standard-library/istream-operators.md#op_gt_gt)을 참조하세요.

첫 번째 멤버 함수는 **istr** >> `ws` 형식의 식이 [ws](../standard-library/istream-functions.md#ws)( **istr**)을 호출한 다음 **\*this**를 반환하도록 합니다. 두 번째와 세 번째 함수는 [hex](../standard-library/ios-functions.md#hex)와 같은 기타 조작자가 비슷하게 동작하도록 합니다. 나머지 함수는 형식이 지정된 입력 함수를 구성합니다.

다음 함수는

```cpp
basic_istream& operator>>(
    basic_streambuf<Elem, Tr>* strbuf);
```

_ *Strbuf* 가 null 포인터가 아닌 경우 요소를 추출 하 고 *Strbuf*에 삽입 합니다. 추출은 파일의 끝에서 중지됩니다. 또한 삽입이 실패하거나 예외를 throw하면(catch했지만 다시 throw되지 않음) 문제의 요소를 추출하지 않고 중단합니다. 함수가 요소를 추출 하지 않으면 [setstate](../standard-library/basic-ios-class.md#setstate)(`failbit`)를 호출 합니다. 어떤 경우든 함수는 **\*this**를 반환합니다.

다음 함수는

```cpp
basic_istream& operator>>(bool& val);
```

필드를 추출하고 다음을 호출하여 부울 값으로 변환합니다. [use_facet](../standard-library/basic-filebuf-class.md#open) < `num_get`\< **Elem**, **InIt**>( [getloc](../standard-library/ios-base-class.md#getloc)). [get](../standard-library/ios-base-class.md#getloc)( **InIt**( [rdbuf](../standard-library/basic-ios-class.md#rdbuf)), `Init`(0), **\*this**, `getloc`, `val`). 여기서 **InIt**는 [istreambuf_iterator](../standard-library/istreambuf-iterator-class.md)\< **Elem**, **Tr**>로 정의됩니다. 함수는 **\*this**를 반환합니다.

다음 함수는

```cpp
basic_istream& operator>>(short& val);
basic_istream& operator>>(unsigned short& val);
basic_istream& operator>>(int& val);
basic_istream& operator>>(unsigned int& val);
basic_istream& operator>>(long& val);
basic_istream& operator>>(unsigned long& val);
basic_istream& operator>>(long long& val);
basic_istream& operator>>(unsigned long long& val);
basic_istream& operator>>(void *& val);
```

각각 필드를 추출하고 다음을 호출하여 숫자 값으로 변환합니다. `use_facet`< `num_get`\< **Elem**, **InIt**>( `getloc`). [get](#get)( **InIt**( `rdbuf`), `Init`(0), **\*this**, `getloc`, `val`). 여기서 **InIt** 는 `istreambuf_iterator` **Elem**, **Tr**>로 `val` \< 정의 되며 필요에 따라 **long**, **unsigned long**또는 **void** <strong>\*</strong> 형식입니다.

변환 된 값을의 `val`형식으로 나타낼 수 없는 경우 함수는 [setstate](../standard-library/basic-ios-class.md#setstate)(`failbit`)를 호출 합니다. 어떤 경우든 함수는 **\*this**를 반환합니다.

다음 함수는

```cpp
basic_istream& operator>>(float& val);
basic_istream& operator>>(double& val);
basic_istream& operator>>(long double& val);
```

각각 필드를 추출하고 다음을 호출하여 숫자 값으로 변환합니다. `use_facet`< `num_get`\< **Elem**, **InIt**>( `getloc`). **get**( **InIt**( `rdbuf`), `Init`(0), **\*this**, `getloc`, `val`). \< `istreambuf_iterator` `val` 여기서는 Elem, Tr >로 정의 되며 필요에 따라 double 또는 long double 형식을 갖습니다. `InIt`

변환된 값을 `val`의 형식으로 나타낼 수 없는 경우 함수는 `setstate`( **failbit**)를 호출합니다. 어떤 경우든 함수는 **\*this**를 반환합니다.

### <a name="example"></a>예제

```cpp
// istream_basic_istream_op_is.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;

ios_base& hex2( ios_base& ib )
{
   ib.unsetf( ios_base::dec );
   ib.setf( ios_base::hex );
   return ib;
}

basic_istream<char, char_traits<char> >& somefunc(basic_istream<char, char_traits<char> > &i)
{
   if ( i == cin )
   {
      cerr << "i is cin" << endl;
   }
   return i;
}

int main( )
{
   int i = 0;
   cin >> somefunc;
   cin >> i;
   cout << i << endl;
   cin >> hex2;
   cin >> i;
   cout << i << endl;
}
```

## <a name="op_eq"></a>  basic_istream::operator=

이 개체에 연산자의 오른쪽에 있는 `basic_istream`을 할당합니다. 복사본을 남기지 않는 `rvalue` 참조와 관련된 이동 할당입니다.

```cpp
basic_istream& operator=(basic_istream&& right);
```

### <a name="parameters"></a>매개 변수

*오른쪽*\
`basic_ifstream` 개체에 대한 `rvalue` 참조입니다.

### <a name="return-value"></a>반환 값

*this를 반환합니다.

### <a name="remarks"></a>설명

멤버 연산자는 swap `( right)`를 호출합니다.

## <a name="peek"></a>  basic_istream::peek

읽을 다음 문자를 반환합니다.

```cpp
int_type peek();
```

### <a name="return-value"></a>반환 값

읽을 다음 문자입니다.

### <a name="remarks"></a>설명

형식이 지정되지 않은 입력 함수는 가능한 경우 `rdbuf` -> [sgetc](../standard-library/basic-streambuf-class.md#sgetc)를 반환하여 요소를 추출합니다. 아닌 경우 **traits_type::** [eof](../standard-library/char-traits-struct.md#eof)를 반환합니다.

### <a name="example"></a>예제

```cpp
// basic_istream_peek.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   char c[10], c2;
   cout << "Type 'abcde': ";

   c2 = cin.peek( );
   cin.getline( &c[0], 9 );

   cout << c2 << " " << c << endl;
}
```

```Input
abcde
```

```Output
Type 'abcde': abcde
a abcde
```

## <a name="putback"></a>  basic_istream::putback

지정된 문자를 스트림에 넣습니다.

```cpp
basic_istream<Elem, Tr>& putback(
    char_type Ch);
```

### <a name="parameters"></a>매개 변수

*Ch*\
스트림에 다시 배치할 문자입니다.

### <a name="return-value"></a>반환 값

스트림( **\*this**)입니다.

### <a name="remarks"></a>설명

형식이 지정 되지 않은 [입력 함수](../standard-library/basic-istream-class.md) 는 [rdbuf](../standard-library/basic-ios-class.md#rdbuf)`->`[sputbackc](../standard-library/basic-streambuf-class.md#sputbackc)를 호출 하는 것 처럼 가능한 경우 *Ch*를 다시 배치 합니다. Rdbuf `sputbackc` 가 null 포인터 이거나에 대 한 호출이 **traits_type::** [eof](../standard-library/char-traits-struct.md#eof)를 반환 하면 함수는 [setstate](../standard-library/basic-ios-class.md#setstate)(`badbit`)를 호출 합니다. 어떤 경우든 함수는 **\*this**를 반환합니다.

### <a name="example"></a>예제

```cpp
// basic_istream_putback.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   char c[10], c2, c3;

   c2 = cin.get( );
   c3 = cin.get( );
   cin.putback( c2 );
   cin.getline( &c[0], 9 );
   cout << c << endl;
}
```

```Output
qwq
```

## <a name="read"></a>  basic_istream::read

스트림에서 지정된 개수의 문자를 읽고 배열에 저장합니다.

이 메서드는 전달된 값이 정확한지 확인하기 위해 호출자를 사용하므로 보안상 위험할 수 있습니다.

```cpp
basic_istream<Elem, Tr>& read(
    char_type* str,
    streamsize count);
```

### <a name="parameters"></a>매개 변수

*문자열*\
문자를 읽을 배열입니다.

*수*\
읽을 문자 수입니다.

### <a name="return-value"></a>반환 값

스트림( `*this`)입니다.

### <a name="remarks"></a>설명

형식이 지정 되지 않은 입력 함수는 요소 *수를 계산* 하 여 _ `Str`에서 시작 하는 배열에 저장 합니다. 추출은 파일의 끝에서 일찍 중지 되며,이 경우 함수는 [setstate](../standard-library/basic-ios-class.md#setstate)(`failbit`)를 호출 합니다. 어떤 경우든 `*this`를 반환합니다.

### <a name="example"></a>예제

```cpp
// basic_istream_read.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main()
{
    char c[10];
    int count = 5;

    cout << "Type 'abcde': ";

    // Note: cin::read is potentially unsafe, consider
    // using cin::_Read_s instead.
    cin.read(&c[0], count);
    c[count] = 0;

    cout << c << endl;
}
```

```Input
abcde
```

```Output
Type 'abcde': abcde
abcde
```

## <a name="readsome"></a>  basic_istream::readsome

지정한 개수의 문자 값을 읽습니다.

이 메서드는 전달된 값이 정확한지 확인하기 위해 호출자를 사용하므로 보안상 위험할 수 있습니다.

```cpp
streamsize readsome(
    char_type* str,
    streamsize count);
```

### <a name="parameters"></a>매개 변수

*문자열*\
`readsome`이 읽은 문자를 저장하는 배열입니다.

*수*\
읽을 문자 수입니다.

### <a name="return-value"></a>반환 값

실제로 읽은 문자 수 [gcount](#gcount)입니다.

### <a name="remarks"></a>설명

이 형식이 지정 되지 않은 입력 함수는 입력 스트림에서 요소 *수를 계산* 하 여 배열 *str*에 저장 합니다.

이 함수는 입력을 기다리지 않고, 읽을 수 있는 데이터는 무엇이든 읽습니다.

### <a name="example"></a>예제

```cpp
// basic_istream_readsome.cpp
// compile with: /EHsc /W3
#include <iostream>
using namespace std;

int main( )
{
   char c[10];
   int count = 5;

   cout << "Type 'abcdefgh': ";

   // cin.read blocks until user types input.
   // Note: cin::read is potentially unsafe, consider
   // using cin::_Read_s instead.
   cin.read(&c[0], 2);

   // Note: cin::readsome is potentially unsafe, consider
   // using cin::_Readsome_s instead.
   int n = cin.readsome(&c[0], count);  // C4996
   c[n] = 0;
   cout << n << " characters read" << endl;
   cout << c << endl;
}
```

## <a name="seekg"></a>  basic_istream::seekg

스트림에서 읽기 위치를 이동합니다.

```cpp
basic_istream<Elem, Tr>& seekg(pos_type pos);

basic_istream<Elem, Tr>& seekg(off_type off, ios_base::seekdir way);
```

### <a name="parameters"></a>매개 변수

*pos*\
읽기 포인터를 이동할 절대 위치입니다.

*해제*\
읽기 포인터를 기준으로 이동 하는 오프셋 *입니다.*

*방식은*\
[ios_base::seekdir](../standard-library/ios-base-class.md#seekdir) 열거형 중 하나입니다.

### <a name="return-value"></a>반환 값

스트림( **\*this**)입니다.

### <a name="remarks"></a>설명

첫 번째 멤버 함수는 절대 검색을 수행하고 두 번째 멤버 함수는 상대 검색을 수행합니다.

> [!NOTE]
> 표준 C++는 텍스트 파일에서 상대 검색을 지원하지 않으므로 두 번째 멤버 함수를 텍스트 파일과 함께 사용하지 마세요.

[Fail](../standard-library/basic-ios-class.md#fail) 이 false 이면 첫 번째 멤버 함수는 일부`pos_type`임시 개체`newpos`에 대해 **newpos** = [rdbuf](../standard-library/basic-ios-class.md#rdbuf) -> [pubseekpos](../standard-library/basic-streambuf-class.md#pubseekpos)(`pos`)를 호출합니다. 가 `fail` false 인 경우 두 번째 함수는 **newpos** = **rdbuf** -> [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff)( `off`, `way`)를 호출 합니다. 어떤 경우 든 `off_type`() **newpos** = = ( `off_type`) (-1) (위치 지정 작업 실패) 이면 함수는를 호출 `istr`합니다. [setstate](../standard-library/basic-ios-class.md#setstate) (`failbit`). 두 함수 모두 **\*this**를 반환합니다.

[fail](../standard-library/basic-ios-class.md#fail)이 true인 경우 멤버 함수는 아무 작업도 수행하지 않습니다.

### <a name="example"></a>예제

```cpp
// basic_istream_seekg.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main ( )
{
   using namespace std;
   ifstream file;
   char c, c1;

   file.open( "basic_istream_seekg.txt" );
   file.seekg(2);   // seek to position 2
   file >> c;
   cout << c << endl;
}
```

## <a name="sentry"></a>  basic_istream::sentry

중첩된 클래스는 선언에서 형식이 지정된 입력 함수 및 형식이 지정되지 않은 입력 함수를 구성하는 개체를 설명합니다.

class sentry { public: explicit sentry( basic_istream\<Elem, Tr>& _Istr, bool _Noskip = false); operator bool() const; };

### <a name="remarks"></a>설명

`_Istr.`[good](../standard-library/basic-ios-class.md#good)이 true인 경우 생성자는

- `_Istr`. [tie](../standard-library/basic-ios-class.md#tie) -> [flush](../standard-library/basic-ostream-class.md#flush)를 호출합니다(`_Istr`. `tie`가 null 포인터가 아닌 경우).

- `_Istr`인 경우 실제로 [ws](../standard-library/istream-functions.md#ws)( `_Istr`)을 호출합니다. ([flags](../standard-library/ios-base-class.md#flags) **&** [skipws](../standard-library/ios-functions.md#skipws)가 0이 아닌 경우).

이러한 준비 작업 후 `_Istr`. `good`가 false 이면 생성자가를 `_Istr`호출 합니다. [setstate](../standard-library/basic-ios-class.md#setstate) (`failbit`). 어떤 경우든 생성자는 `_Istr`. `good`에서 `status`. 를 `operator bool` 나중에 호출 하면이 저장 된 값이 전달 됩니다.

## <a name="swap"></a>  basic_istream::swap

두 `basic_istream` 개체의 내용을 교환합니다.

```cpp
void swap(basic_istream& right);
```

### <a name="parameters"></a>매개 변수

*오른쪽*\
`basic_istream` 개체에 대한 lvalue 참조입니다.

### <a name="remarks"></a>설명

멤버 함수는 [basic_ios:: swap](../standard-library/basic-ios-class.md#swap)`(right)`를 호출합니다. 또한 추출 개수를 *오른쪽*의 추출 개수로 교환 합니다.

## <a name="sync"></a>  basic_istream::sync

스트림과 연결된 입력 디바이스를 스트림 버퍼와 동기화합니다.

```cpp
int sync();
```

### <a name="return-value"></a>반환 값

[rdbuf](../standard-library/basic-ios-class.md#rdbuf)가 null 포인터인 경우 함수는 -1을 반환하고, 아닌 경우 `rdbuf` -> [pubsync](../standard-library/basic-streambuf-class.md#pubsync)를 호출합니다. -1을 반환 하는 경우 함수는 [setstate](../standard-library/basic-ios-class.md#setstate)(`badbit`)를 호출 하 고-1을 반환 합니다. 아닌 경우 함수는 0을 반환합니다.

## <a name="tellg"></a>  basic_istream::tellg

스트림에서 현재 읽기 위치를 보고합니다.

```cpp
pos_type tellg();
```

### <a name="return-value"></a>반환 값

스트림 내의 현재 위치입니다.

### <a name="remarks"></a>설명

[fail](../standard-library/basic-ios-class.md#fail)이 false인 경우 멤버 함수는 [rdbuf](../standard-library/basic-ios-class.md#rdbuf) -> [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff)(0, `cur`, **in**)을 반환합니다. 아닌 경우 `pos_type`(-1)을 반환합니다.

### <a name="example"></a>예제

```cpp
// basic_istream_tellg.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main()
{
    using namespace std;
    ifstream file;
    char c;
    streamoff i;

    file.open("basic_istream_tellg.txt");
    i = file.tellg();
    file >> c;
    cout << c << " " << i << endl;

    i = file.tellg();
    file >> c;
    cout << c << " " << i << endl;
}
```

## <a name="unget"></a>  basic_istream::unget

가장 최근에 읽은 문자를 다시 스트림에 넣습니다.

```cpp
basic_istream<Elem, Tr>& unget();
```

### <a name="return-value"></a>반환 값

스트림( **\*this**)입니다.

### <a name="remarks"></a>설명

가능한 경우 [형식이 지정되지 않은 입력 함수](../standard-library/basic-istream-class.md)는 `rdbuf` -> [sungetc](../standard-library/basic-streambuf-class.md#sungetc)를 호출하는 것처럼 이전 요소를 스트림에 다시 배치합니다. [Rdbuf](../standard-library/basic-ios-class.md#rdbuf) 가 null 포인터 이거나에 대 `sungetc` 한 호출이 **traits_type::** [eof](../standard-library/basic-ios-class.md#eof)를 반환 하면 함수는 [setstate](../standard-library/basic-ios-class.md#setstate)(`badbit`)를 호출 합니다. 어떤 경우든 함수는 **\*this**를 반환합니다.

`unget`이 실패할 수 있는 방법에 대한 자세한 내용은 [basic_streambuf::sungetc](../standard-library/basic-streambuf-class.md#sungetc)를 참조하세요.

### <a name="example"></a>예제

```cpp
// basic_istream_unget.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   char c[10], c2;

   cout << "Type 'abc': ";
   c2 = cin.get( );
   cin.unget( );
   cin.getline( &c[0], 9 );
   cout << c << endl;
}
```

```Input
abc
```

```Output
Type 'abc': abc
abc
```

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream 프로그래밍](../standard-library/iostream-programming.md)\
[iostreams 규칙](../standard-library/iostreams-conventions.md)
