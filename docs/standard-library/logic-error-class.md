---
title: logic_error 클래스
ms.date: 11/04/2016
f1_keywords:
- stdexcept/std::logic_error
helpviewer_keywords:
- logic_error class
ms.assetid: b290d73d-94e1-4288-af86-2bb5d71f677a
ms.openlocfilehash: 9b7c432a649b566b455109f6de1f7bcc0734ff9b
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68453792"
---
# <a name="logicerror-class"></a>logic_error 클래스

이 클래스는 논리적 사전 조건 위반과 같이 프로그램이 실행되기 전에 검색될 수 있는 오류를 보고하기 위해 발생하는 모든 예외에 대한 기본 클래스로 사용됩니다.

## <a name="syntax"></a>구문

```cpp
class logic_error : public exception {
public:
    explicit logic_error(const string& message);

    explicit logic_error(const char *message);

};
```

## <a name="remarks"></a>설명

[what](../standard-library/exception-class.md)에서 반환된 값은 **message**`.`[data](../standard-library/basic-string-class.md#data)의 복사본입니다.

## <a name="example"></a>예제

```cpp
// logic_error.cpp
// compile with: /EHsc /GR
#include <iostream>
using namespace std;

int main( )
{
   try
   {
      throw logic_error( "logic error" );
   }
   catch ( exception &e )
   {
      cerr << "Caught: " << e.what( ) << endl;
      cerr << "Type: " << typeid( e ).name( ) << endl;
   };
}
```

```Output
Caught: logic error
Type: class std::logic_error
```

## <a name="requirements"></a>요구 사항

**헤더:** \<stdexcept>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[exception 클래스](../standard-library/exception-class.md)\
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)
