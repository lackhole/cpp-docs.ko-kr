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
ms.openlocfilehash: 8d93e46b0323058d93c6d0bd8c1ee566998aef61
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447191"
---
# <a name="ltostreamgt-functions"></a>&lt;ostream&gt; 함수

이러한 함수는 ostream &lt;&gt;에 정의 된 전역 템플릿 함수입니다. 멤버 함수는 [Basic_ostream 클래스](basic-ostream-class.md) 설명서를 참조 하세요.

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

*E*\
요소 형식입니다.

*Ostr*\
**Basic_ostream**형식의 개체입니다.

*비교한*\
문자 특성입니다.

### <a name="return-value"></a>반환 값

**Basic_ostream**형식의 개체입니다.

### <a name="remarks"></a>설명

조작자는 *Ostr*를 호출 합니다. [put](../standard-library/basic-ostream-class.md#put) (*Ostr*. [확대](../standard-library/basic-ios-class.md#widen) (' \n '))을 (를) 호출한 다음 *Ostr*를 호출 합니다. [플러시](../standard-library/basic-ostream-class.md#flush). *Ostr*을 반환 합니다.

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

*E*\
요소 형식입니다.

*Ostr*\
`basic_ostream` 형식의 개체입니다.

*비교한*\
문자 특성입니다.

### <a name="return-value"></a>반환 값

`basic_ostream` 형식의 개체입니다.

### <a name="remarks"></a>설명

조작자는 *Ostr*를 호출 합니다. [put](../standard-library/basic-ostream-class.md#put) (*Elem*(' \ 0 ')). *Ostr*을 반환 합니다.

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

*E*\
요소 형식입니다.

*Ostr*\
`basic_ostream` 형식의 개체입니다.

*비교한*\
문자 특성입니다.

### <a name="return-value"></a>반환 값

`basic_ostream` 형식의 개체입니다.

### <a name="remarks"></a>설명

조작자는 *Ostr*를 호출 합니다. [플러시](../standard-library/basic-ostream-class.md#flush). *Ostr*을 반환 합니다.

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

*E*\
요소 형식입니다.

*비교한*\
문자 특성입니다.

*비어*\
`basic_ostream` 개체에 대한 lvalue 참조입니다.

*오른쪽*\
`basic_ostream` 개체에 대한 lvalue 참조입니다.

### <a name="remarks"></a>설명

템플릿 함수 `swap`은 `left.swap(right)`을 실행합니다.

## <a name="see-also"></a>참고자료

[\<ostream>](../standard-library/ostream.md)
