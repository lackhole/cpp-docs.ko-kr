---
title: '&lt;ostream&gt; 함수'
ms.date: 11/04/2016
f1_keywords:
- ostream/std::swap
- ostream/std::endl
- ostream/std::ends
- ostream/std::flush
ms.assetid: d6e56cc0-c8df-4dbe-be10-98e14c35ed3a
helpviewer_keywords:
- std::swap [C++]
- std::endl [C++]
- std::ends [C++]
- std::flush [C++]
ms.openlocfilehash: fa498f4acbb151eab4321bcddc6af027ee266237
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62370996"
---
# <a name="ltostreamgt-functions"></a>&lt;ostream&gt; 함수

에 정의 된 전역 템플릿 함수는 이러한 &lt;ostream&gt;합니다. 멤버 함수에 대 한 참조를 [basic_ostream 클래스](basic-ostream-class.md) 설명서.

||||
|-|-|-|
|[endl](#endl)|[ends](#ends)|[flush](#flush)|
|[swap](#swap)|

## <a name="endl"></a>endl

줄을 종료하고 버퍼를 플러시합니다.

```cpp
template class<Elem, Tr>
basic_ostream<Elem, Tr>& endl(
   basic_ostream<Elem, Tr>& Ostr);
```

### <a name="parameters"></a>매개 변수

*Elem*<br/>
요소 형식입니다.

*Ostr*<br/>
형식의 개체 **basic_ostream**합니다.

*Tr*<br/>
문자 특성입니다.

### <a name="return-value"></a>반환 값

형식의 개체 **basic_ostream**합니다.

### <a name="remarks"></a>설명

조작자 *Ostr*.[ 배치](../standard-library/basic-ostream-class.md#put)(*Ostr*.[ widen](../standard-library/basic-ios-class.md#widen)('\n'))를 호출 하 고 *Ostr*.[ 플러시](../standard-library/basic-ostream-class.md#flush)합니다. 반환 *Ostr*합니다.

### <a name="example"></a>예제

```cpp
// ostream_endl.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout << "testing" << endl;
}
```

```Output
testing
```

## <a name="ends"></a>끝

문자열을 종료합니다.

```cpp
template class<Elem, Tr>
basic_ostream<Elem, Tr>& ends(
   basic_ostream<Elem, Tr>& Ostr);
```

### <a name="parameters"></a>매개 변수

*Elem*<br/>
요소 형식입니다.

*Ostr*<br/>
`basic_ostream` 형식의 개체입니다.

*Tr*<br/>
문자 특성입니다.

### <a name="return-value"></a>반환 값

`basic_ostream` 형식의 개체입니다.

### <a name="remarks"></a>설명

조작자 *Ostr*.[ 배치](../standard-library/basic-ostream-class.md#put)(*Elem*('\0')). 반환 *Ostr*합니다.

### <a name="example"></a>예제

```cpp
// ostream_ends.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout << "a";
   cout << "b" << ends;
   cout << "c" << endl;
}
```

```Output
ab c
```

## <a name="flush"></a>flush

버퍼를 플러시합니다.

```cpp
template class<Elem, Tr>
basic_ostream<Elem, Tr>& flush(
   basic_ostream<Elem, Tr>& Ostr);
```

### <a name="parameters"></a>매개 변수

*Elem*<br/>
요소 형식입니다.

*Ostr*<br/>
`basic_ostream` 형식의 개체입니다.

*Tr*<br/>
문자 특성입니다.

### <a name="return-value"></a>반환 값

`basic_ostream` 형식의 개체입니다.

### <a name="remarks"></a>설명

조작자 *Ostr*.[ 플러시](../standard-library/basic-ostream-class.md#flush)합니다. 반환 *Ostr*합니다.

### <a name="example"></a>예제

```cpp
// ostream_flush.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout << "testing" << flush;
}
```

```Output
testing
```

## <a name="swap"></a>swap

두 `basic_ostream` 개체의 값을 교환합니다.

```cpp
template <class Elem, class Tr>
void swap(
   basic_ostream<Elem, Tr>& left,
   basic_ostream<Elem, Tr>& right);
```

### <a name="parameters"></a>매개 변수

*Elem*<br/>
요소 형식입니다.

*Tr*<br/>
문자 특성입니다.

*left*<br/>
`basic_ostream` 개체에 대한 lvalue 참조입니다.

*right*<br/>
`basic_ostream` 개체에 대한 lvalue 참조입니다.

### <a name="remarks"></a>설명

템플릿 함수 `swap`은 `left.swap(right)`을 실행합니다.

## <a name="see-also"></a>참고자료

[\<ostream>](../standard-library/ostream.md)
