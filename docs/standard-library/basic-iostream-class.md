---
title: basic_iostream 클래스
ms.date: 11/04/2016
f1_keywords:
- istream/std::basic_iostream
- istream/std::basic_iostream::swap
helpviewer_keywords:
- basic_iostream class
ms.assetid: 294b680b-eb49-4066-8db2-6d52dac9d6e3
ms.openlocfilehash: 190c9aa23493cea67bae44be93fd3fdbdecc4447
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72690000"
---
# <a name="basic_iostream-class"></a>basic_iostream 클래스

입력과 출력을 둘 다 수행할 수 있는 스트림 클래스입니다.

## <a name="syntax"></a>구문

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_iostream : public basic_istream<Elem, Tr>,
    public basic_ostream<Elem, Tr>
{
public:
    explicit basic_iostream(basic_streambuf<Elem, Tr>* strbuf);

    virtual ~basic_iostream();

};
```

## <a name="remarks"></a>주의

클래스 템플릿은 기본 클래스 [basic_ostream](../standard-library/basic-ostream-class.md) <  `Elem`, `Tr` > 및 추출를 통해 기본 클래스인 [basic_istream](../standard-library/basic-istream-class.md) <  `Elem` `Tr` >를 통해 삽입을 제어 하는 개체를 설명 합니다. 두 개체는 공통 가상 기본 클래스 [basic_ios](../standard-library/basic-ios-class.md)< `Elem`, `Tr`>을 공유합니다. 또한 문자 특성이 `Tr` 클래스에 의해 결정되는 `Elem` 형식의 요소가 포함된 공통 스트림 버퍼를 관리합니다. 이 생성자는 `basic_istream`( **strbuf**) 및 `basic_ostream`( **strbuf**)을 통해 해당 기본 클래스를 초기화합니다.

### <a name="constructors"></a>생성자

|생성자|설명|
|-|-|
|[basic_iostream](#basic_iostream)|`basic_iostream` 개체를 만듭니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|설명|
|-|-|
|[swap](#swap)|제공된 `basic_iostream` 개체의 내용을 이 개체의 내용으로 교환합니다.|

### <a name="operators"></a>연산자

|연산자|설명|
|-|-|
|[operator=](#op_eq)|지정된 `basic_iostream` 개체의 값을 이 개체에 할당합니다. 복사본을 남기지 않는 `rvalue`와 관련된 이동 할당입니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<istream>

**네임스페이스:** std

## <a name="basic_iostream"></a>  basic_iostream::basic_iostream

`basic_iostream` 개체를 만듭니다.

```cpp
explicit basic_iostream(basic_streambuf<Elem, Tr>* strbuf);

basic_iostream(basic_iostream&& right);

basic_iostream();
```

### <a name="parameters"></a>매개 변수

*strbuf* \
기존 `basic_streambuf` 개체입니다.

*오른쪽* \
새 `basic_iostream`을 생성하는 데 사용된 기존 `basic_iostream` 개체입니다.

### <a name="remarks"></a>주의

첫 번째 생성자는 `basic_istream(strbuf)` 및 `basic_ostream(strbuf)`의 방식으로 기본 개체를 초기화합니다.

두 번째 생성자는 `move(right)`를 호출 하 여 기본 개체를 초기화 합니다.

## <a name="op_eq"></a>  basic_iostream::operator=

지정된 `basic_iostream` 개체의 값을 이 개체에 할당합니다. 복사본을 남기지 않는 rvalue와 관련된 이동 할당입니다.

```cpp
basic_iostream& operator=(basic_iostream&& right);
```

### <a name="parameters"></a>매개 변수

*오른쪽* \
할당할 `basic_iostream` 개체에 대한 `rvalue` 참조입니다.

### <a name="remarks"></a>주의

멤버 연산자는 `swap(right)`를 호출 합니다.

## <a name="swap"></a>  basic_iostream::swap

제공된 `basic_iostream` 개체의 내용을 이 개체의 내용으로 교환합니다.

```cpp
void swap(basic_iostream& right);
```

### <a name="parameters"></a>매개 변수

*오른쪽* \
스왑할 `basic_iostream` 개체입니다.

### <a name="remarks"></a>주의

멤버 함수는 `swap(right)`를 호출 합니다.

## <a name="see-also"></a>참조

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream 프로그래밍](../standard-library/iostream-programming.md)\
[iostreams 규칙](../standard-library/iostreams-conventions.md)
