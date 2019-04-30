---
title: '&lt;string&gt; 함수'
ms.date: 11/04/2016
f1_keywords:
- string/std::getline
- string/std::stod
- string/std::stof
- string/std::stoi
- string/std::stol
- string/std::stold
- string/std::stoll
- string/std::stoul
- string/std::stoull
- string/std::swap
- string/std::to_string
- string/std::to_wstring
ms.assetid: 1a4ffd11-dce5-4cc6-a043-b95de034c7c4
helpviewer_keywords:
- std::getline [C++]
- std::stod [C++]
- std::stof [C++]
- std::stoi [C++]
- std::stol [C++]
- std::stold [C++]
- std::stoll [C++]
- std::stoul [C++]
- std::stoull [C++]
- std::swap [C++]
- std::to_string [C++]
- std::to_wstring [C++]
ms.openlocfilehash: d10af9bc32acd730db1fe9da3775ac2aa84e5fff
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412347"
---
# <a name="ltstringgt-functions"></a>&lt;string&gt; 함수

||||
|-|-|-|
|[getline](#getline)|[stod](#stod)|[stof](#stof)|
|[stoi](#stoi)|[stol](#stol)|[stold](#stold)|
|[stoll](#stoll)|[stoul](#stoul)|[stoull](#stoull)|
|[swap](#swap)|[to_string](#to_string)|[to_wstring](#to_wstring)|

## <a name="getline"></a>  getline

입력 스트림에서 문자열을 한 줄씩 추출합니다.

```cpp
// (1) delimiter as parameter
template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>& is,
    basic_string<CharType, Traits, Allocator>& str,
    CharType delim);

template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>&& is,
    basic_string<CharType, Traits, Allocator>& str,
    const CharType delim);

// (2) default delimiter used
template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>& is,
    basic_string<CharType, Traits, Allocator>& str);

template <class Allocator, class Traits, class Allocator>
basic_istream<Allocator, Traits>& getline(
    basic_istream<Allocator, Traits>&& is,
    basic_string<Allocator, Traits, Allocator>& str);
```

### <a name="parameters"></a>매개 변수

*is*<br/>
문자열을 추출할 입력 스트림입니다.

*str*<br/>
입력 스트림에서 문자를 읽어들일 문자열입니다.

*delim*<br/>
줄 구분 기호입니다.

### <a name="return-value"></a>반환 값

입력된 스트림에 *는*합니다.

### <a name="remarks"></a>설명

로 표시 된 함수 시그니처 쌍 `(1)` 에서 문자를 추출 *됩니다* 때까지 *delim* 발견 되 면에 저장 하 여 *str*합니다.

로 표시 된 함수 시그니처 쌍 `(2)` 줄 바꿈 기본 줄 구분 기호로 사용 하 고 작동할 **getline**(`is`하십시오 `str`, `is`합니다. `widen`(' `\n`'))으로 동작합니다.

각 쌍의 두 번째 함수는 [value 참조](../cpp/lvalues-and-rvalues-visual-cpp.md)를 지원하기 위한 첫 번째 함수와 유사한 버전입니다.

다음 중 하나가 발생하면 추출이 중지됩니다.

- 파일의 끝의 내부 상태 플래그가 하는 경우 *됩니다* 로 설정 된 `ios_base::eofbit`합니다.

- 함수가 `delim`과 비교 시 같은 요소를 추출하는 경우, 해당 요소는 제어된 시퀀스로 다시 돌아가지도 않고 제어된 시퀀스에 추가되지도 않습니다.

- 함수 추출 `str.` [max_size](../standard-library/basic-string-class.md#max_size) 요소에 있는 경우의 내부 상태 플래그가 *은* 로 설정 된 `ios_base::failbit`합니다.

- 이외의 다른 오류가 이전에 나열 된의 내부 상태 플래그가 대물 *는* 로 설정 되어 `ios_base::badbit`

내부 상태 플래그에 대한 자세한 내용은 [ios_base::iostate](../standard-library/ios-base-class.md#iostate)를 참조하세요.

내부 상태 플래그가 함수가 없는 요소를 추출 하는 경우 *됩니다* 로 설정 된 `ios_base::failbit`합니다. 어떤 경우 든 `getline` 반환 *는*합니다.

예외가 throw 되 면 *은* 하 고 *str* 유효한 상태로 유지 됩니다.

### <a name="example"></a>예제

다음 코드에서는 `getline()`을 두 가지 모드에서 보여 줍니다. 첫 번째 모드에서는 기본 구분 기호(줄 바꿈 문자)를 사용하고 두 번째 모드에서는 공백을 구분 기호로 사용합니다. 파일의 끝 문자(키보드에서 CTRL+Z를 누름)를 사용하여 while 루프 종료를 제어합니다. 그러면 `cin`의 내부 상태 플래그가 `eofbit`로 설정되며, [basic_ios::clear()](../standard-library/basic-ios-class.md#clear)를 사용하여 이 상태를 해제해야 두 번째 while 루프가 정상적으로 작동합니다.

```cpp
// compile with: /EHsc /W4
#include <string>
#include <iostream>
#include <vector>

using namespace std;

int main()
{
    string str;
    vector<string> v1;
    cout << "Enter a sentence, press ENTER between sentences. (Ctrl-Z to stop): " << endl;
    // Loop until end-of-file (Ctrl-Z) is input, store each sentence in a vector.
    // Default delimiter is the newline character.
    while (getline(cin, str)) {
        v1.push_back(str);
    }

    cout << "The following input was stored with newline delimiter:" << endl;
    for (const auto& p : v1) {
        cout << p << endl;
    }

    cin.clear();

    vector<string> v2;
    // Now try it with a whitespace delimiter
    while (getline(cin, str, ' ')) {
        v2.push_back(str);
    }

    cout << "The following input was stored with whitespace as delimiter:" << endl;
    for (const auto& p : v2) {
        cout << p << endl;
    }
}
```

## <a name="stod"></a>  stod

문자 시퀀스를 변환 된 **이중**합니다.

```cpp
double stod(
    const string& str,
    size_t* idx = 0);

double stod(
    const wstring& str,
    size_t* idx = 0
;
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*str*|변환할 문자 시퀀스입니다.|
|*idx*|변환되지 않은 첫 번째 문자의 인덱스 값입니다.|

### <a name="return-value"></a>반환 값

합니다 **이중** 값입니다.

### <a name="remarks"></a>설명

요소 시퀀스를 변환 하는 함수 *str* 값으로 `val` 형식의 **double** 호출 하는 것 처럼 `strtod( str.c_str(), _Eptr)`여기서 `_Eptr` 내부 함수에는 개체. ` str.c_str() == *_Eptr`인 경우 `invalid_argument` 형식의 개체가 throw됩니다. 이러한 호출에서 `errno`를 설정하는 경우에는 `out_of_range` 형식의 개체가 throw됩니다. 그렇지 않고 *idx* null 포인터 이면 함수는 아닙니다 `*_Eptr -  str.c_str()` 에서 `*idx` 반환 `val`합니다.

## <a name="stof"></a>  stof

문자 시퀀스를 float로 변환합니다.

```cpp
float stof(
    const string& str,
    size_t* idx = 0);

float stof(
    const wstring& str,
    size_t* idx = 0);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*str*|변환할 문자 시퀀스입니다.|
|*idx*|변환되지 않은 첫 번째 문자의 인덱스 값입니다.|

### <a name="return-value"></a>반환 값

float 값입니다.

### <a name="remarks"></a>설명

요소 시퀀스를 변환 하는 함수 *str* 값으로 `val` 형식의 **float** 호출 하는 것 처럼 `strtof( str.c_str(), _Eptr)`여기서 `_Eptr` 개체인 내부 함수입니다. ` str.c_str() == *_Eptr`인 경우 `invalid_argument` 형식의 개체가 throw됩니다. 이러한 호출에서 `errno`를 설정하는 경우에는 `out_of_range` 형식의 개체가 throw됩니다. 그렇지 않고 *idx* null 포인터 이면 함수는 아닙니다 `*_Eptr -  str.c_str()` 에서 `*idx` 반환 `val`합니다.

## <a name="stoi"></a>  stoi

문자 시퀀스를 정수로 변환합니다.

```cpp
int stoi(
    const string& str,
    size_t* idx = 0,
    int base = 10);

int stoi(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="return-value"></a>반환 값

정수 값입니다.

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*str*|변환할 문자 시퀀스입니다.|
|*idx*|반환 시 변환되지 않은 첫 번째 문자의 인덱스를 포함합니다.|
|*base*|사용할 기수입니다.|

### <a name="remarks"></a>설명

함수 `stoi` 의 문자 시퀀스로 변환 *str* 형식의 값으로 **int** 값을 반환 합니다. 예를 들어 문자 시퀀스 "10" 전달 시 `stoi`에서 반환하는 값은 정수 10입니다.

`stoi`는 `strtol` 방식으로 호출하는 경우 싱글바이트 문자에 대해 `strtol( str.c_str(), _Eptr, idx)` 함수와 비슷하게 동작하고, `_Eptr` 방식으로 호출하는 경우에는 와이드 문자에 대해 `wcstol` 함수와 비슷하게 동작합니다. 여기서 `wcstol(Str.c_str(), _Eptr, idx)`은 함수 내부의 개체입니다. 자세한 내용은 [strtol, wcstol, _strtol_l, _wcstol_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)을 참조하세요.

경우 `str.c_str() == *_Eptr`하십시오 `stoi` 형식의 개체를 throw `invalid_argument`합니다. 이러한 호출을 설정 하는 경우 `errno`에서 반환된 된 값 형식의 개체로 표현할 수 없는 경우 또는 **int**, 형식의 개체를 throw `out_of_range`합니다. 그렇지 않고 *idx* null 포인터 이면 함수는 아닙니다 `*_Eptr - str.c_str()` 에서 `*idx`합니다.

## <a name="stol"></a>  stol

문자 시퀀스를 변환 된 **긴**합니다.

```cpp
long stol(
    const string& str,
    size_t* idx = 0,
    int base = 10);

long stol(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*str*|변환할 문자 시퀀스입니다.|
|*idx*|변환되지 않은 첫 번째 문자의 인덱스 값입니다.|
|*base*|사용할 기수입니다.|

### <a name="return-value"></a>반환 값

long 정수 값입니다.

### <a name="remarks"></a>설명

요소 시퀀스를 변환 하는 함수 *str* 값으로 `val` 형식의 **긴** 호출 하는 것 처럼 `strtol( str.c_str(), _Eptr, idx)`여기서 `_Eptr` 내부 함수에는 개체. ` str.c_str() == *_Eptr`인 경우 `invalid_argument` 형식의 개체가 throw됩니다. 이러한 호출에서 `errno`를 설정하는 경우에는 `out_of_range` 형식의 개체가 throw됩니다. 그렇지 않고 *idx* null 포인터 이면 함수는 아닙니다 `*_Eptr -  str.c_str()` 에서 `*idx` 반환 `val`합니다.

## <a name="stold"></a>  stold

문자 시퀀스를 변환 된 **long double**합니다.

```cpp
double stold(
    const string& str,
    size_t* idx = 0);

double stold(
    const wstring& str,
    size_t* idx = 0);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*str*|변환할 문자 시퀀스입니다.|
|*idx*|변환되지 않은 첫 번째 문자의 인덱스 값입니다.|

### <a name="return-value"></a>반환 값

합니다 **long double** 값입니다.

### <a name="remarks"></a>설명

요소 시퀀스를 변환 하는 함수 *str* 값으로 `val` 형식의 **long double** 호출 하는 것 처럼 `strtold( str.c_str(), _Eptr)`여기서 `_Eptr` 개체인 내부 함수입니다. ` str.c_str() == *_Eptr`인 경우 `invalid_argument` 형식의 개체가 throw됩니다. 이러한 호출에서 `errno`를 설정하는 경우에는 `out_of_range` 형식의 개체가 throw됩니다. 그렇지 않고 *idx* null 포인터 이면 함수는 아닙니다 `*_Eptr -  str.c_str()` 에서 `*idx` 반환 `val`합니다.

## <a name="stoll"></a>  stoll

문자 시퀀스를 변환 된 **long long**합니다.

```cpp
long long stoll(
    const string& str,
    size_t* idx = 0,
    int base = 10);

long long stoll(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*str*|변환할 문자 시퀀스입니다.|
|*idx*|변환되지 않은 첫 번째 문자의 인덱스 값입니다.|
|*base*|사용할 기수입니다.|

### <a name="return-value"></a>반환 값

합니다 **long long** 값입니다.

### <a name="remarks"></a>설명

요소 시퀀스를 변환 하는 함수 *str* 값으로 `val` 형식의 **long long** 호출 하는 것 처럼 `strtoll( str.c_str(), _Eptr, idx)`여기서 `_Eptr` 개체인 내부 함수입니다. ` str.c_str() == *_Eptr`인 경우 `invalid_argument` 형식의 개체가 throw됩니다. 이러한 호출에서 `errno`를 설정하는 경우에는 `out_of_range` 형식의 개체가 throw됩니다. 그렇지 않고 *idx* null 포인터 이면 함수는 아닙니다 `*_Eptr -  str.c_str()` 에서 `*idx` 반환 `val`합니다.

## <a name="stoul"></a>  stoul

문자 시퀀스를 부호 없는 long으로 변환합니다.

```cpp
unsigned long stoul(
    const string& str,
    size_t* idx = 0,
    int base = 10);

unsigned long stoul(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*str*|변환할 문자 시퀀스입니다.|
|*idx*|변환되지 않은 첫 번째 문자의 인덱스 값입니다.|
|*base*|사용할 기수입니다.|

### <a name="return-value"></a>반환 값

부호 없는 long 정수 값입니다.

### <a name="remarks"></a>설명

함수 변환의 요소 시퀀스 *str* 값으로 `val` 형식의 **부호 없는 long** 호출 하는 것 처럼 `strtoul( str.c_str(), _Eptr, idx)`여기서 `_Eptr` 개체인 내부 함수 . ` str.c_str() == *_Eptr`인 경우 `invalid_argument` 형식의 개체가 throw됩니다. 이러한 호출에서 `errno`를 설정하는 경우에는 `out_of_range` 형식의 개체가 throw됩니다. 그렇지 않고 *idx* null 포인터 이면 함수는 아닙니다 `*_Eptr -  str.c_str()` 에서 `*idx` 반환 `val`합니다.

## <a name="stoull"></a>  stoull

문자 시퀀스를 변환 합니다는 **부호 없는 long long**합니다.

```cpp
unsigned long long stoull(
    const string& str,
    size_t* idx = 0,
    int base = 10);

unsigned long long stoull(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*str*|변환할 문자 시퀀스입니다.|
|*idx*|변환되지 않은 첫 번째 문자의 인덱스 값입니다.|
|*base*|사용할 기수입니다.|

### <a name="return-value"></a>반환 값

합니다 **부호 없는 long long** 값입니다.

### <a name="remarks"></a>설명

함수 변환의 요소 시퀀스 *str* 값으로 `val` 형식의 **부호 없는 long long** 호출 하는 것 처럼 `strtoull( str.c_str(), _Eptr, idx)`여기서 `_Eptr` 개체는 내부에 함수입니다. ` str.c_str() == *_Eptr`인 경우 `invalid_argument` 형식의 개체가 throw됩니다. 이러한 호출에서 `errno`를 설정하는 경우에는 `out_of_range` 형식의 개체가 throw됩니다. 그렇지 않고 *idx* null 포인터 이면 함수는 아닙니다 `*_Eptr -  str.c_str()` 에서 `*idx` 반환 `val`합니다.

## <a name="swap"></a>  swap

두 문자열의 문자 배열을 교환합니다.

```cpp
template <class Traits, class Allocator>
void swap(basic_string<CharType, Traits, Allocator>& left, basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>매개 변수

*left*<br/>
요소를 다른 문자열의 요소와 교환할 단일 문자열입니다.

*right*<br/>
요소가 첫 번째 문자열과 교환되는 다른 문자열입니다.

### <a name="remarks"></a>설명

특수 멤버 함수를 실행 하는 템플릿 함수 *왼쪽*.[ 스왑](../standard-library/basic-string-class.md#swap)(*오른쪽*) 고정적 복잡성을 보장 하는 문자열의 경우.

### <a name="example"></a>예제

```cpp
// string_swap.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   // Declaring an object of type basic_string<char>
   string s1 ( "Tweedledee" );
   string s2 ( "Tweedledum" );
   cout << "Before swapping string s1 and s2:" << endl;
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   swap ( s1 , s2 );
   cout << "\nAfter swapping string s1 and s2:" << endl;
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;
}
```

```Output
Before swapping string s1 and s2:
The basic_string s1 = Tweedledee.
The basic_string s2 = Tweedledum.

After swapping string s1 and s2:
The basic_string s1 = Tweedledum.
The basic_string s2 = Tweedledee.
```

## <a name="to_string"></a>  to_string

값을 `string`로 변환합니다.

```cpp
string to_string(int Val);
string to_string(unsigned int Val);
string to_string(long Val);
string to_string(unsigned long Val);
string to_string(long long Val);
string to_string(unsigned long long Val);
string to_string(float Val);
string to_string(double Val);
string to_string(long double Val);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*Val*|변환할 값입니다.|

### <a name="return-value"></a>반환 값

값을 나타내는 `string`입니다.

### <a name="remarks"></a>설명

함수 변환 *Val* 배열 개체에 저장 된 요소의 시퀀스 `Buf` 호출 하는 것 처럼 함수 내부의 `sprintf(Buf, Fmt, Val)`여기서 `Fmt` 는

- `"%d"` 하는 경우 `Val` 형식이 **int**

- `"%u"` 하는 경우 `Val` 형식이 **부호 없는 int**

- `"%ld"` 하는 경우 `Val` 형식이 **long**

- `"%lu"` 하는 경우 `Val` 형식이 **부호 없는 long**

- `"%lld"` 하는 경우 `Val` 형식이 **long long**

- `"%llu"` 하는 경우 `Val` 형식이 **부호 없는 long long**

- `"%f"` 하는 경우 `Val` 형식이 **float** 또는 **double**

- `"%Lf"` 하는 경우 `Val` 형식이 **long double**

함수에서 `string(Buf)`을 반환합니다.

## <a name="to_wstring"></a>  to_wstring

값을 와이드 문자열로 변환합니다.

```cpp
wstring to_wstring(int Val);
wstring to_wstring(unsigned int Val);
wstring to_wstring(long Val);
wstring to_wstring(unsigned long Val);
wstring to_wstring(long long Val);
wstring to_wstring(unsigned long long Val);
wstring to_wstring(float Val);
wstring to_wstring(double Val);
wstring to_wstring(long double Val);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|`Val`|변환할 값입니다.|

### <a name="return-value"></a>반환 값

값을 나타내는 와이드 문자열입니다.

### <a name="remarks"></a>설명

이 함수는 `Val`가 있는 위치에서 `Buf`를 호출하는 것과 같이 `swprintf(Buf, Len, Fmt, Val)`을 함수 내부의 배열 개체 `Fmt`에 저장된 요소 시퀀스로 변환합니다.

- `L"%d"` 하는 경우 `Val` 형식이 **int**

- `L"%u"` 하는 경우 `Val` 형식이 **부호 없는 int**

- `L"%ld"` 하는 경우 `Val` 형식이 **long**

- `L"%lu"` 하는 경우 `Val` 형식이 **부호 없는 long**

- `L"%lld"` 하는 경우 `Val` 형식이 **long long**

- `L"%llu"` 하는 경우 `Val` 형식이 **부호 없는 long long**

- `L"%f"` 하는 경우 `Val` 형식이 **float** 또는 **double**

- `L"%Lf"` 하는 경우 `Val` 형식이 **long double**

함수에서 `wstring(Buf)`을 반환합니다.

## <a name="see-also"></a>참고자료

[\<string>](../standard-library/string.md)<br/>
