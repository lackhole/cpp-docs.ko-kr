---
title: strstream 클래스
ms.date: 11/04/2016
f1_keywords:
- strstream/std::strstream::freeze
- strstream/std::strstream::pcount
- strstream/std::strstream::rdbuf
- strstream/std::strstream::str
helpviewer_keywords:
- std::strstream [C++], freeze
- std::strstream [C++], pcount
- std::strstream [C++], rdbuf
- std::strstream [C++], str
ms.assetid: 63f3be31-9e36-42b1-9715-a474a5997e2a
ms.openlocfilehash: 53baa350121796d5198211e1fdb08f4341df6b80
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459097"
---
# <a name="strstream-class"></a>strstream 클래스

[strstreambuf](../standard-library/strstreambuf-class.md) 클래스의 스트림 버퍼를 사용한 요소 및 인코드된 개체 삽입 및 추출을 제어하는 개체를 설명합니다.

## <a name="syntax"></a>구문

```cpp
class strstream : public iostream
```

## <a name="remarks"></a>설명

이 개체는 `strstreambuf` 클래스의 개체를 저장합니다.

> [!NOTE]
> 이 클래스는 사용되지 않습니다. 대신 [stringstream](../standard-library/sstream-typedefs.md#stringstream) 또는 [wstringstream](../standard-library/sstream-typedefs.md#wstringstream)을 사용하는 것이 좋습니다.

### <a name="constructors"></a>생성자

|생성자|Description|
|-|-|
|[strstream](#strstream)|`strstream` 형식의 개체를 생성합니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|설명|
|-|-|
|[freeze](#freeze)|스트림 버퍼 작업을 통해 스트림 버퍼를 사용할 수 없게 합니다.|
|[pcount](#pcount)|제어되는 시퀀스에 기록되는 요소 수의 개수를 반환합니다.|
|[rdbuf](#rdbuf)|스트림의 연결된 `strstreambuf` 개체에 대한 포인터를 반환합니다.|
|[str](#str)|[freeze](../standard-library/strstreambuf-class.md#freeze)를 호출한 다음 제어되는 시퀀스의 시작 부분에 대한 포인터를 반환합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<strstream >

**네임스페이스:** std

## <a name="freeze"></a>  strstream::freeze

스트림 버퍼 작업을 통해 스트림 버퍼를 사용할 수 없게 합니다.

```cpp
void freeze(bool _Freezeit = true);
```

### <a name="parameters"></a>매개 변수

*_Freezeit*\
스트림을 고정 시킬 것인지 여부를 나타내는 **부울** 입니다.

### <a name="remarks"></a>설명

구성원 함수는 [rdbuf](#rdbuf) -> [freeze](../standard-library/strstreambuf-class.md#freeze)(_ *Freezeit*)를 호출합니다.

### <a name="example"></a>예제

을 사용 `freeze`하는 예제는 [strstreambuf:: freeze](../standard-library/strstreambuf-class.md#freeze) 를 참조 하세요.

## <a name="pcount"></a>  strstream::pcount

제어되는 시퀀스에 기록되는 요소 수의 개수를 반환합니다.

```cpp
streamsize pcount() const;
```

### <a name="return-value"></a>반환 값

제어되는 시퀀스에 기록되는 요소 수의 개수입니다.

### <a name="remarks"></a>설명

구성원 함수는 [rdbuf](#rdbuf) -> [pcount](../standard-library/strstreambuf-class.md#pcount)를 반환합니다.

### <a name="example"></a>예제

pcount를 사용하는 샘플은 [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount)를 참조하세요.

## <a name="rdbuf"></a>  strstream::rdbuf

스트림의 연결된 strstreambuf 개체에 대한 포인터를 반환합니다.

```cpp
strstreambuf *rdbuf() const
```

### <a name="return-value"></a>반환 값

스트림의 연결된 strstreambuf 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

멤버 함수는 형식의 `pointer` 저장 된 스트림 버퍼 주소를 [strstreambuf](../standard-library/strstreambuf-class.md)에 반환 합니다.

### <a name="example"></a>예제

`rdbuf`를 사용하는 샘플은 [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount)를 참조하세요.

## <a name="str"></a>  strstream::str

[freeze](../standard-library/strstreambuf-class.md#freeze)를 호출한 다음 제어되는 시퀀스의 시작 부분에 대한 포인터를 반환합니다.

```cpp
char *str();
```

### <a name="return-value"></a>반환 값

제어되는 시퀀스의 시작 부분에 대한 포인터입니다.

### <a name="remarks"></a>설명

구성원 함수는 [rdbuf](#rdbuf) -> [str](../standard-library/strstreambuf-class.md#str)을 반환합니다.

### <a name="example"></a>예제

를 사용 `str`하는 샘플은 [strstreambuf:: str](../standard-library/strstreambuf-class.md#str) 을 참조 하세요.

## <a name="strstream"></a>  strstream::strstream

`strstream` 형식의 개체를 생성합니다.

```cpp
strstream();

strstream(char* ptr,
    streamsize count,
    ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>매개 변수

*수*\
버퍼의 크기입니다.

*모드 (_s)* \
버퍼의 입력 및 출력 모드입니다. 자세한 내용은 [ios_base::openmode](../standard-library/ios-base-class.md#openmode)를 참조하세요.

*ptr*\
버퍼입니다.

### <a name="remarks"></a>설명

두 생성자는 모두 [streambuf](../standard-library/streambuf-typedefs.md#streambuf)( **sb**)를 호출 하 여 기본 클래스 `sb` 를 초기화 합니다. 여기서은 [strstreambuf](../standard-library/strstreambuf-class.md)클래스의 저장 된 개체입니다. 또한 첫 번째 생성자는 `sb` [strstreambuf](../standard-library/strstreambuf-class.md#strstreambuf)를 호출 하 여 초기화 합니다. 두 번째 생성자는 다음의 두 가지 방법 중 하나로 기본 클래스를 초기화합니다.

- `_Mode` **Ios_base:: app**= = 0 인 `ptr` `strstreambuf`  & 경우 *ptr* `count` 은 요소 배열의 첫 번째 요소를 지정 해야 하며 생성자는 ( `ptr`, `count`,)를 호출 합니다. .

- 그렇지 않으면 *ptr* 은 첫 번째 요소가 *ptr*로 지정 된 C 문자열을 포함 하는 count 요소 배열의 첫 번째 요소를 지정 해야 하 고 생성자는 ( `strstreambuf` `ptr`, `count`,를 `ptr` 호출합니다. +  `strlen`( `ptr`) ).

## <a name="see-also"></a>참고자료

[iostream](../standard-library/istream-typedefs.md#iostream)\
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream 프로그래밍](../standard-library/iostream-programming.md)\
[iostreams 규칙](../standard-library/iostreams-conventions.md)
