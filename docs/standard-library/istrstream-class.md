---
title: istrstream 클래스
ms.date: 11/04/2016
f1_keywords:
- strstream/std::istrstream::rdbuf
- strstream/std::istrstream::str
helpviewer_keywords:
- istrstream class
ms.assetid: c2d41c75-bd2c-4437-bd77-5939ce1b97af
ms.openlocfilehash: 70e71ac5a6fd523f0b7589625f4e88fdb41ee0e2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62224276"
---
# <a name="istrstream-class"></a>istrstream 클래스

[strstreambuf](../standard-library/strstreambuf-class.md) 클래스의 스트림 버퍼에서 요소 및 인코드된 개체의 추출을 제어하는 개체를 설명합니다.

## <a name="syntax"></a>구문

```cpp
class istrstream : public istream
```

## <a name="remarks"></a>설명

이 개체는 `strstreambuf` 클래스의 개체를 저장합니다.

> [!NOTE]
> 이 클래스는 사용되지 않습니다. 대신 [istringstream](../standard-library/sstream-typedefs.md#istringstream) 또는 [wistringstream](../standard-library/sstream-typedefs.md#wistringstream)을 사용하는 것이 좋습니다.

### <a name="constructors"></a>생성자

|생성자|설명|
|-|-|
|[istrstream](#istrstream)|`istrstream` 형식의 개체를 생성합니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|설명|
|-|-|
|[rdbuf](#rdbuf)|스트림의 연결된 `strstreambuf` 개체에 대한 포인터를 반환합니다.|
|[str](#str)|[freeze](../standard-library/strstreambuf-class.md#freeze)를 호출한 다음 제어되는 시퀀스의 시작 부분에 대한 포인터를 반환합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<strstream >

**네임스페이스:** std

## <a name="istrstream"></a>  istrstream::istrstream

`istrstream` 형식의 개체를 생성합니다.

```cpp
explicit istrstream(
    const char* ptr);

explicit istrstream(
    char* ptr);

istrstream(
    const char* ptr,
    streamsize count);

istrstream(
    char* ptr,
    int count);
```

### <a name="parameters"></a>매개 변수

*count*<br/>
버퍼의 길이 (*ptr*).

*ptr*<br/>
버퍼가 초기화되는 콘텐츠입니다.

### <a name="remarks"></a>설명

모든 생성자를 호출 하 여 기본 클래스를 초기화 [istream](../standard-library/istream-typedefs.md#istream)(**sb**) 여기서 `sb` 클래스의 저장 개체인 [strstreambuf](../standard-library/strstreambuf-class.md)합니다. 처음 두 생성자를 초기화할 수도 `sb` 호출한 `strstreambuf`(( **const** `char` \*) `ptr`, 0). 나머지 두 생성자는 대신 `strstreambuf`( ( **const**`char` *) `ptr`, `count` )를 호출합니다.

## <a name="rdbuf"></a>  istrstream::rdbuf

스트림의 연결된 strstreambuf 개체에 대한 포인터를 반환합니다.

```cpp
strstreambuf *rdbuf() const
```

### <a name="return-value"></a>반환 값

스트림의 연결된 strstreambuf 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

멤버 함수는 pointer 형식의 저장된 스트림 버퍼 주소를 [strstreambuf](../standard-library/strstreambuf-class.md)에 반환합니다.

### <a name="example"></a>예제

`rdbuf`를 사용하는 샘플은 [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount)를 참조하세요.

## <a name="str"></a>  istrstream::str

[freeze](../standard-library/strstreambuf-class.md#freeze)를 호출한 다음 제어되는 시퀀스의 시작 부분에 대한 포인터를 반환합니다.

```cpp
char *str();
```

### <a name="return-value"></a>반환 값

제어되는 시퀀스의 시작 부분에 대한 포인터입니다.

### <a name="remarks"></a>설명

구성원 함수는 [rdbuf](#rdbuf) -> [str](../standard-library/strstreambuf-class.md#str)을 반환합니다.

### <a name="example"></a>예제

참조 [strstream:: str](../standard-library/strstreambuf-class.md#str) 사용 하는 샘플에 대 한 `str`합니다.

## <a name="see-also"></a>참고자료

[istream](../standard-library/istream-typedefs.md#istream)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream 프로그래밍](../standard-library/iostream-programming.md)<br/>
[iostreams 규칙](../standard-library/iostreams-conventions.md)<br/>
