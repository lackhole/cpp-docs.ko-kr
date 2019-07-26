---
title: basic_ostream 클래스
ms.date: 03/27/2019
f1_keywords:
- ostream/std::basic_ostream
- ostream/std::basic_ostream::flush
- ostream/std::basic_ostream::put
- ostream/std::basic_ostream::seekp
- ostream/std::basic_ostream::sentry
- ostream/std::basic_ostream::swap
- ostream/std::basic_ostream::tellp
- ostream/std::basic_ostream::write
helpviewer_keywords:
- std::basic_ostream [C++]
- std::basic_ostream [C++], flush
- std::basic_ostream [C++], put
- std::basic_ostream [C++], seekp
- std::basic_ostream [C++], sentry
- std::basic_ostream [C++], swap
- std::basic_ostream [C++], tellp
- std::basic_ostream [C++], write
ms.assetid: 5baadc65-b662-4fab-8c9f-94457c58cda1
ms.openlocfilehash: 8715ae4816be9c8f1453b243d1c8d3574d8c97cf
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457862"
---
# <a name="basicostream-class"></a>basic_ostream 클래스

이 템플릿 클래스는 문자 특성이 클래스 `Elem` `Tr`에 의해 결정 되는 형식의 요소를 사용 하 여 스트림 버퍼에 요소 및 인코드된 개체 삽입을 제어 하는 개체를 설명 합니다 ( [char_type](../standard-library/basic-ios-class.md#char_type)라고도 함). [traits_type](../standard-library/basic-ios-class.md#traits_type)이라고 합니다.

## <a name="syntax"></a>구문

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_ostream : virtual public basic_ios<Elem, Tr>
```

### <a name="parameters"></a>매개 변수

*E*\
`char_type`

*비교한*\
문자 `traits_type`입니다.

## <a name="remarks"></a>설명

[operator<<](#basic_ostream_operator_lt_lt)를 오버로드하는 대부분의 멤버 함수는 형식이 지정된 출력 함수입니다. 다음 패턴을 따릅니다.

```cpp
iostate state = goodbit;
const sentry ok(*this);

if (ok)
{try
{<convert and insert elements
    accumulate flags in state> }
    catch (...)
{try
{setstate(badbit);

}
    catch (...)
{}
    if ((exceptions()& badbit) != 0)
    throw; }}
width(0);
// Except for operator<<(Elem)
setstate(state);

return (*this);
```

다른 두 멤버 함수는 형식이 지정되지 않은 출력 함수입니다. 다음 패턴을 따릅니다.

```cpp
iostate state = goodbit;
const sentry ok(*this);

if (!ok)
    state |= badbit;
else
{try
{<obtain and insert elements
    accumulate flags in state> }
    catch (...)
{try
{setstate(badbit);

}
    catch (...)
{}
    if ((exceptions()& badbit) != 0)
    throw; }}
setstate(state);

return (*this);
```

두 함수 그룹은 요소를 삽입 하는 동안 오류가 발생 하는 경우 [setstate](../standard-library/basic-ios-class.md#setstate)(**badbit**)를 호출 합니다.

basic_istream\< **Elem**, **Tr**> 클래스의 개체는 [basic_ios](../standard-library/basic-ios-class.md) **\<Elem**, **Tr>** 클래스의 가상 공용 기준 개체만 저장합니다.

## <a name="example"></a>예제

출력 스트림에 대한 자세한 내용은 [basic_ofstream 클래스](../standard-library/basic-ofstream-class.md)에 대한 예제를 참조하세요.

### <a name="constructors"></a>생성자

|생성자|설명|
|-|-|
|[basic_ostream](#basic_ostream)|`basic_ostream` 개체를 생성합니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|Description|
|-|-|
|[flush](#flush)|버퍼를 플러시합니다.|
|[put](#put)|스트림에 문자를 넣습니다.|
|[seekp](#seekp)|출력 스트림 내의 위치를 다시 설정합니다.|
|[sentry](#sentry)|중첩 클래스는 선언에서 형식이 지정된 출력 함수 및 형식이 지정되지 않은 출력 함수를 구성하는 개체를 설명합니다.|
|[swap](#swap)|이 `basic_ostream` 개체의 값을 제공된 `basic_ostream` 개체의 값으로 교환합니다.|
|[tellp](#tellp)|출력 스트림 내의 위치를 보고합니다.|
|[write](#write)|스트림에 문자를 넣습니다.|

### <a name="operators"></a>연산자

|연산자|설명|
|-|-|
|[operator=](#op_eq)|제공된 `basic_ostream` 개체 매개 변수의 값을 이 개체에 할당합니다.|
|[operator<<](#basic_ostream_operator_lt_lt)|스트림에 씁니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<ostream>

**네임스페이스:** std

## <a name="basic_ostream"></a>  basic_ostream::basic_ostream

`basic_ostream` 개체를 생성합니다.

```cpp
explicit basic_ostream(
    basic_streambuf<Elem, Tr>* strbuf,
    bool _Isstd = false);

basic_ostream(basic_ostream&& right);
```

### <a name="parameters"></a>매개 변수

*strbuf*\
[basic_streambuf](../standard-library/basic-streambuf-class.md) 형식의 개체입니다.

*_Isstd*\
표준 스트림 이면 **true** 입니다. 그렇지 않으면 **false**입니다.

*오른쪽*\
`basic_ostream` 형식의 개체에 대한 rvalue 참조입니다.

### <a name="remarks"></a>설명

첫 번째 생성자는 [init](../standard-library/basic-ios-class.md#init)(`strbuf`)를 호출하여 기본 개체를 초기화합니다. 두 번째 생성자는 [basic_ios::move](../standard-library/basic-ios-class.md#move)`(right)`를 호출하여 기본 개체를 초기화합니다.

### <a name="example"></a>예제

출력 스트림에 대한 자세한 내용은 [basic_ofstream::basic_ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream)에 대한 예제를 참조하세요.

## <a name="flush"></a>  basic_ostream::flush

버퍼를 플러시합니다.

```cpp
basic_ostream<Elem, Tr>& flush();
```

### <a name="return-value"></a>반환 값

Basic_ostream 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

[rdbuf](../standard-library/basic-ios-class.md#rdbuf)가 null 포인터가 아닌 경우 함수는 **rdbuf->** [pubsync](../standard-library/basic-streambuf-class.md#pubsync)를 호출합니다. -1이 반환되는 경우 함수는 [setstate](../standard-library/basic-ios-class.md#setstate)(**badbit**)를 호출합니다. 그런 다음 **\*this**를 반환합니다.

### <a name="example"></a>예제

```cpp
// basic_ostream_flush.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout << "test";
   cout.flush();
}
```

```Output
test
```

## <a name="basic_ostream_operator_lt_lt"></a>  basic_ostream::operator&lt;&lt;

스트림에 씁니다.

```cpp
basic_ostream<Elem, Tr>& operator<<(
    basic_ostream<Elem, Tr>& (* Pfn)(basic_ostream<Elem, Tr>&));

basic_ostream<Elem, Tr>& operator<<(
    ios_base& (* Pfn)(ios_base&));

basic_ostream<Elem, Tr>& operator<<(
    basic_ios<Elem, Tr>& (* Pfn)(basic_ios<Elem, Tr>&));

basic_ostream<Elem, Tr>& operator<<(basic_streambuf<Elem, Tr>* strbuf);
basic_ostream<Elem, Tr>& operator<<(bool val);
basic_ostream<Elem, Tr>& operator<<(short val);
basic_ostream<Elem, Tr>& operator<<(unsigned short val);
basic_ostream<Elem, Tr>& operator<<(int __w64  val);
basic_ostream<Elem, Tr>& operator<<(unsigned int __w64  val);
basic_ostream<Elem, Tr>& operator<<(long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long __w64  val);
basic_ostream<Elem, Tr>& operator<<(long long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long long val);
basic_ostream<Elem, Tr>& operator<<(float val);
basic_ostream<Elem, Tr>& operator<<(double val);
basic_ostream<Elem, Tr>& operator<<(long double val);
basic_ostream<Elem, Tr>& operator<<(const void* val);
```

### <a name="parameters"></a>매개 변수

*Pfn*\
함수 포인터입니다.

*strbuf*\
`stream_buf` 개체에 대한 포인터입니다.

*짧은*\
스트림에 기록할 요소입니다.

### <a name="return-value"></a>반환 값

Basic_ostream 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

Ostream > 헤더는 또한 여러 전역 삽입 연산자를 \<정의 합니다. 자세한 내용은 [operator < <](../standard-library/ostream-operators.md#op_lt_lt)를 참조 하세요.

첫 번째 멤버 함수 `ostr << endl` 는 폼의 식이 [endl](../standard-library/ostream-functions.md#endl) **(ostr)** 을 호출 하 고  **\*this**를 반환 하는지 확인 합니다. 두 번째와 세 번째 함수는 [hex](../standard-library/ios-functions.md#hex)와 같은 기타 조작자가 비슷하게 동작하도록 합니다. 나머지 함수는 모두 형식이 지정된 출력 함수입니다.

다음 함수는

```cpp
basic_ostream<Elem, Tr>& operator<<(basic_streambuf<Elem, Tr>* strbuf);
```

strbuf가 null 포인터가 *아닌 경우* *strbuf*에서 요소를 추출 하 여 삽입 합니다. 추출은 파일의 끝에서 또는 추출이 예외를 throw하는 경우(다시 throw됨) 중지됩니다. 또한 삽입이 실패하면 문제의 요소를 추출하지 않은 채 중단됩니다. 함수가 요소를 삽입하지 않거나 추출이 예외를 throw하면 함수는 [setstate](../standard-library/basic-ios-class.md#setstate)(**failbit**)를 호출합니다. 어떤 경우든 함수는 **\*this**를 반환합니다.

다음 함수는

```cpp
basic_ostream<Elem, Tr>& operator<<(bool val);
```

부울 `_Val` 필드로 변환 하 고 [use_facet](../standard-library/basic-filebuf-class.md#open) **< num_put\<Elem, OutIt >** `(`[getloc](../standard-library/ios-base-class.md#getloc))를 호출 하 여 삽입 합니다. [put](#put)(**OutIt**([rdbuf](../standard-library/basic-ios-class.md#rdbuf)), **\*this**, `getloc`, **val**). 여기서는 ostreambuf_iterator [Elem,](../standard-library/ostreambuf-iterator-class.md)Tr >로 정의 됩니다. **\<** `OutIt` 함수는 **\*this**를 반환합니다.

다음 함수는

```cpp
basic_ostream<Elem, Tr>& operator<<(short val);
basic_ostream<Elem, Tr>& operator<<(unsigned short val);
basic_ostream<Elem, Tr>& operator<<(int val);
basic_ostream<Elem, Tr>& operator<<(unsigned int __w64  val);
basic_ostream<Elem, Tr>& operator<<(long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long val);
basic_ostream<Elem, Tr>& operator<<(long long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long long val);
basic_ostream<Elem, Tr>& operator<<(const void* val);
```

각각 *val* 을 숫자 필드로 변환 하 고 **use_facet < num_put\<Elem, OutIt >** (`getloc`)를 호출 하 여 삽입 합니다. **put**(**OutIt**(`rdbuf`), **\*this**, `getloc`, **val**). 여기서 **OutIt**는 **ostreambuf_iterator\<Elem, Tr>** 로 정의됩니다. 함수는 **\*this**를 반환합니다.

다음 함수는

```cpp
basic_ostream<Elem, Tr>& operator<<(float val);
basic_ostream<Elem, Tr>& operator<<(double val);
basic_ostream<Elem, Tr>& operator<<(long double val);
```

각각 *val* 을 숫자 필드로 변환 하 고 **use_facet\<< num_put Elem, OutIt >** (`getloc`)를 호출 하 여 삽입**합니다. put**(`rdbuf`**OutIt**(),  **\*this**, `getloc`, **val**). 여기서 **OutIt**는 **ostreambuf_iterator\<Elem, Tr>** 로 정의됩니다. 함수는 **\*this**를 반환합니다.

### <a name="example"></a>예제

```cpp
// basic_ostream_op_write.cpp
// compile with: /EHsc
#include <iostream>
#include <string.h>

using namespace std;

ios_base& hex2( ios_base& ib )
{
   ib.unsetf( ios_base::dec );
   ib.setf( ios_base::hex );
   return ib;
}

basic_ostream<char, char_traits<char> >& somefunc(basic_ostream<char, char_traits<char> > &i)
{
    if (i == cout)
    {
        i << "i is cout" << endl;
    }
    return i;
}

class CTxtStreambuf : public basic_streambuf< char, char_traits< char > >
{
public:
    CTxtStreambuf(char *_pszText)
    {
        pszText = _pszText;
        setg(pszText, pszText, pszText + strlen(pszText));
    };
    char *pszText;
};

int main()
{
    cout << somefunc;
    cout << 21 << endl;

    hex2(cout);
    cout << 21 << endl;

    CTxtStreambuf f("text in streambuf");
    cout << &f << endl;
}
```

## <a name="op_eq"></a>  basic_ostream::operator=

제공된 `basic_ostream` 개체 매개 변수의 값을 이 개체에 할당합니다.

```cpp
basic_ostream& operator=(basic_ostream&& right);
```

### <a name="parameters"></a>매개 변수

*오른쪽*\
`basic_ostream` 개체에 대한 `rvalue` 참조입니다.

### <a name="remarks"></a>설명

멤버 연산자는 swap `(right)`를 호출합니다.

## <a name="put"></a>  basic_ostream::put

스트림에 문자를 넣습니다.

```cpp
basic_ostream<Elem, Tr>& put(char_type _Ch);
```

### <a name="parameters"></a>매개 변수

*_Ch*\
단일 문자입니다.

### <a name="return-value"></a>반환 값

Basic_ostream 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

형식이 지정 되지 않은 출력 함수는 *_Ch*요소를 삽입 합니다. 그런 다음 **\*this**를 반환합니다.

### <a name="example"></a>예제

```cpp
// basic_ostream_put.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout.put( 'v' );
   cout << endl;
   wcout.put( L'l' );
}
```

```Output
v
l
```

## <a name="seekp"></a>  basic_ostream::seekp

출력 스트림 내의 위치를 다시 설정합니다.

```cpp
basic_ostream<Elem, Tr>& seekp(pos_type _Pos);

basic_ostream<Elem, Tr>& seekp(off_type _Off, ios_base::seekdir _Way);
```

### <a name="parameters"></a>매개 변수

*_Pos*\
스트림 내의 위치입니다.

*_Off*\
방향에 상대적인 오프셋입니다 *(_w)* .

*_ 방식*\
[ios_base::seekdir](../standard-library/ios-base-class.md#seekdir) 열거형 중 하나입니다.

### <a name="return-value"></a>반환 값

Basic_ostream 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

[Fail](../standard-library/basic-ios-class.md#fail) 이 **false**이면 첫 번째 멤버 함수는 일부 `pos_type` 임시 `newpos`개체에 대해 **newpos =** [rdbuf](../standard-library/basic-ios-class.md#rdbuf) **->** [pubseekpos](../standard-library/basic-streambuf-class.md#pubseekpos)( *_pos*)를 호출 합니다. 가 `fail` false 인 경우 두 번째 함수는 **newpos = rdbuf->** [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff)( *_off, _off*)를 호출 합니다. 어떤 경우든 (`off_type`)**newpos ==** (`off_type`)(-1)(배치 작업 실패)이면 함수는 **istr.** [setstate](../standard-library/basic-ios-class.md#setstate)(**failbit**)를 호출합니다. 두 함수 모두 **\*this**를 반환합니다.

### <a name="example"></a>예제

```cpp
// basic_ostream_seekp.cpp
// compile with: /EHsc
#include <fstream>
#include <iostream>

int main()
{
    using namespace std;
    ofstream x("basic_ostream_seekp.txt");
    streamoff i = x.tellp();
    cout << i << endl;
    x << "testing";
    i = x.tellp();
    cout << i << endl;
    x.seekp(2);   // Put char in third char position in file
    x << " ";

    x.seekp(2, ios::end);   // Put char two after end of file
    x << "z";
}
```

```Output
0
7
```

## <a name="sentry"></a>  basic_ostream::sentry

중첩 클래스는 선언에서 형식이 지정된 출력 함수 및 형식이 지정되지 않은 출력 함수를 구성하는 개체를 설명합니다.

class sentry { public: explicit sentry(basic_ostream\<Elem, Tr>& _Ostr); operator bool() const; ~sentry(); };

### <a name="remarks"></a>설명

중첩 클래스는 선언에서 형식이 지정된 출력 함수 및 형식이 지정되지 않은 출력 함수를 구성하는 개체를 설명합니다. **ostr.** [good](../standard-library/basic-ios-class.md#good)이 **true**이고 **ostr.** [tie](../standard-library/basic-ios-class.md#tie)가 null 포인터가 아니면 생성자는 **ostr.tie->** [flush](#flush)를 호출합니다. 그런 다음 생성자는 `ostr.good` 에서 `status`반환 된 값을 저장 합니다. 를 `operator bool` 나중에 호출 하면이 저장 된 값이 전달 됩니다.

`uncaught_exception`이 **false**를 반환하고 [flags](../standard-library/ios-base-class.md#flags) **&** [unitbuf](../standard-library/ios-functions.md#unitbuf)가 0이 아니면 소멸자는 [flush](#flush)를 호출합니다.

## <a name="swap"></a>  basic_ostream::swap

이 `basic_ostream` 개체의 값을 제공된 `basic_ostream`의 값으로 교환합니다.

```cpp
void swap(basic_ostream& right);
```

### <a name="parameters"></a>매개 변수

*오른쪽*\
`basic_ostream` 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

멤버 함수는 [basic_ios:: swap](../standard-library/basic-ios-class.md#swap) `(right)` 을 호출 하 여이 개체의 내용을 *오른쪽*의 내용으로 교환 합니다.

## <a name="tellp"></a>  basic_ostream::tellp

출력 스트림 내의 위치를 보고합니다.

```cpp
pos_type tellp();
```

### <a name="return-value"></a>반환 값

출력 스트림 내의 위치입니다.

### <a name="remarks"></a>설명

[fail](../standard-library/basic-ios-class.md#fail)이 **false**인 경우 멤버 함수는 [rdbuf](../standard-library/basic-ios-class.md#rdbuf) **->** [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff)(0, `cur`, **in**)을 반환합니다. 아닌 경우 `pos_type`(-1)를 반환합니다.

### <a name="example"></a>예제

`tellp` 사용 예제는 [seekp](#seekp)를 참조하세요.

## <a name="write"></a>  basic_ostream::write

스트림에 문자를 넣습니다.

```cpp
basic_ostream<Elem, Tr>& write(const char_type* str, streamsize count);
```

### <a name="parameters"></a>매개 변수

*수*\
스트림에 넣을 문자의 수입니다.

*문자열*\
스트림에 넣을 문자입니다.

### <a name="return-value"></a>반환 값

Basic_ostream 개체에 대한 참조입니다.

### <a name="remarks"></a>설명

형식이 지정 되지 않은 [출력 함수](../standard-library/basic-ostream-class.md) 는 *str*에서 시작 하는 *count* 요소의 시퀀스를 삽입 합니다.

### <a name="example"></a>예제

`write` 사용 예제는 [streamsize](../standard-library/ios-typedefs.md#streamsize)를 참조하세요.

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream 프로그래밍](../standard-library/iostream-programming.md)\
[iostreams 규칙](../standard-library/iostreams-conventions.md)
