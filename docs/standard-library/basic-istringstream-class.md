---
title: basic_istringstream 클래스
ms.date: 11/04/2016
f1_keywords:
- sstream/std::basic_istringstream
- sstream/std::basic_istringstream::allocator_type
- sstream/std::basic_istringstream::rdbuf
- sstream/std::basic_istringstream::str
- sstream/std::basic_istringstream::swap
helpviewer_keywords:
- std::basic_istringstream [C++]
- std::basic_istringstream [C++], allocator_type
- std::basic_istringstream [C++], rdbuf
- std::basic_istringstream [C++], str
- std::basic_istringstream [C++], swap
ms.assetid: 1d5bb4b5-793d-4833-98e5-14676c451915
ms.openlocfilehash: fdf622bbef370e8b3625f419be29f293bc06eacc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400632"
---
# <a name="basicistringstream-class"></a>basic_istringstream 클래스

[basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`> 클래스의 스트림 버퍼에서 요소와 인코드된 개체의 추출을 제어하는 개체를 설명합니다.

## <a name="syntax"></a>구문

```cpp
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>
class basic_istringstream : public basic_istream<Elem, Tr>
```

### <a name="parameters"></a>매개 변수

*Alloc*<br/>
할당자 클래스입니다.

*Elem*<br/>
문자열 기본 요소의 형식입니다.

*Tr*<br/>
문자열의 기본 요소에서 특수화된 문자 특성입니다.

## <a name="remarks"></a>설명

요소의 추출을 제어 하는 개체 및 클래스의 스트림 버퍼에서 인코딩된 개체를 설명 하는 템플릿 클래스 [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>, 형식의 요소를 사용 하 여 *Elem*에서 문자 특성이 클래스에 의해 결정 됩니다 *Tr*를 클래스의할당자에의해할당되는요소가 *Alloc*합니다. 이 개체는 basic_stringbuf< **Elem**, **Tr**, `Alloc`> 클래스의 개체를 저장합니다.

### <a name="constructors"></a>생성자

|생성자|설명|
|-|-|
|[basic_istringstream](#basic_istringstream)|`basic_istringstream` 형식의 개체를 생성합니다.|

### <a name="typedefs"></a>형식 정의

|형식 이름|설명|
|-|-|
|[allocator_type](#allocator_type)|이 형식은 템플릿 매개 변수 `Alloc`의 동의어입니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|설명|
|-|-|
|[rdbuf](#rdbuf)|`pointer` 형식의 저장된 스트림 버퍼 주소를 [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`, `Alloc`>로 반환합니다.|
|[str](#str)|쓰기 위치를 변경하지 않고 문자열 버퍼에서 텍스트를 설정하거나 가져옵니다.|
|[swap](#swap)|이 `basic_istringstream` 개체의 값을 제공된 개체의 값으로 교환합니다.|

### <a name="operators"></a>연산자

|연산자|설명|
|-|-|
|[operator=](#op_eq)|개체 매개 변수에서 이 `basic_istringstream` 개체에 값을 할당합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<sstream>

**네임스페이스:** std

## <a name="allocator_type"></a>  basic_istringstream::allocator_type

이 형식은 템플릿 매개 변수 `Alloc`의 동의어입니다.

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_istringstream"></a>  basic_istringstream::basic_istringstream

`basic_istringstream` 형식의 개체를 생성합니다.

```cpp
explicit basic_istringstream(
    ios_base::openmode _Mode = ios_base::in);

explicit basic_istringstream(
    const basic_string<Elem, Tr, Alloc>& str,
    ios_base::openmode _Mode = ios_base::in);

basic_istringstream(
    basic_istringstream&& right);
```

### <a name="parameters"></a>매개 변수

*_Mode*<br/>
[ios_base::openmode](../standard-library/ios-base-class.md#openmode)의 열거형 중 하나입니다.

*str*<br/>
`basic_string` 형식의 개체입니다.

*right*<br/>
`basic_istringstream` 개체에 대한 rvalue 참조입니다.

### <a name="remarks"></a>설명

첫 번째 생성자는 기본 클래스를 호출 하 여 초기화 [basic_istream](../standard-library/basic-istream-class.md)(`sb`), 여기서 `sb` 클래스의 저장 개체인 [basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  `Elem`하십시오 `Tr`, `Alloc`>. 또한 `basic_stringbuf`< `Elem`, `Tr`, `Alloc`>( `_Mode` &#124; `ios_base::in`)을 호출하여 `sb`를 초기화합니다.

두 번째 생성자는 `basic_istream(sb)`를 호출하여 기본 개체를 초기화합니다. 또한 `basic_stringbuf`< `Elem`, `Tr`, `Alloc`>( `str`, `_Mode` &#124; `ios_base::in`)을 호출하여 `sb`를 초기화합니다.

세 번째 생성자는 내용으로 개체를 초기화 *오른쪽*는 rvalue 참조로 처리 합니다.

## <a name="op_eq"></a>  basic_istringstream::operator=

개체 매개 변수에서 이 `basic_istringstream` 개체에 값을 할당합니다.

```cpp
basic_istringstream& operator=(basic_istringstream&& right);
```

### <a name="parameters"></a>매개 변수

*right*<br/>
`basic_istringstream` 개체에 대한 rvalue 참조입니다.

### <a name="remarks"></a>설명

멤버 연산자의 내용으로 개체의 내용을 바꿉니다 *오른쪽*, rvalue 참조 이동 할당으로 처리 합니다.

## <a name="rdbuf"></a>  basic_istringstream::rdbuf

형식의 저장 된 스트림 버퍼 주소를 반환 합니다 `pointer` 를 [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**하십시오 **Tr**, `Alloc`>.

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>반환 값

형식의 저장 된 스트림 버퍼 주소 `pointer` basic_stringbuf에 < **Elem**하십시오 **Tr**, `Alloc`>.

### <a name="example"></a>예제

`rdbuf`의 사용 예제는 [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close)를 참조하세요.

## <a name="str"></a>  basic_istringstream::str

쓰기 위치를 변경하지 않고 문자열 버퍼에서 텍스트를 설정하거나 가져옵니다.

```cpp
basic_string<Elem, Tr, Alloc> str() const;

void str(
    const basic_string<Elem, Tr, Alloc>& _Newstr);
```

### <a name="parameters"></a>매개 변수

*_Newstr*<br/>
새 문자열입니다.

### <a name="return-value"></a>반환 값

[basic_string](../standard-library/basic-string-class.md)< **Elem**, **Tr**, `Alloc`> 클래스의 개체를 반환합니다. 이 개체의 제어된 시퀀스는 **\*this**에 의해 제어된 시퀀스의 복사본입니다.

### <a name="remarks"></a>설명

첫 번째 멤버 함수는 [rdbuf](#rdbuf) -> [str](../standard-library/basic-stringbuf-class.md#str)을 반환합니다. 두 번째 멤버 함수는 `rdbuf` -> **str**( `_Newstr`)을 호출합니다.

### <a name="example"></a>예제

참조 [basic_stringbuf:: str](../standard-library/basic-stringbuf-class.md#str) 사용 하는 예제에 대 한 `str`합니다.

## <a name="swap"></a>  basic_istringstream::swap

두 `basic_istringstream` 개체의 값을 교환합니다.

```cpp
void swap(basic_istringstream& right);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*right*|`basic_istringstream` 개체에 대한 `lvalue` 참조입니다.|

### <a name="remarks"></a>설명

멤버 함수는이 개체의 값과 값 교환 *오른쪽*합니다.

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream 프로그래밍](../standard-library/iostream-programming.md)<br/>
[iostreams 규칙](../standard-library/iostreams-conventions.md)<br/>
