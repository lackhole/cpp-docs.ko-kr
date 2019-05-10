---
title: bad_typeid 예외
ms.date: 11/04/2016
f1_keywords:
- bad_typeid
- bad_typeid_cpp
helpviewer_keywords:
- bad_typeid exception
- exceptions [C++], bad_typeid
ms.assetid: 5963ed58-4ede-4597-957d-f7bbd06299c2
ms.openlocfilehash: 0389a6db1249ad47d4ca5cc10003169933c7a5c3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392390"
---
# <a name="badtypeid-exception"></a>bad_typeid 예외

**typeid**의 피연산자가 NULL 포인터인 경우 [typeid 연산자](../cpp/typeid-operator.md)가 **bad_typeid** 예외를 throw합니다.

## <a name="syntax"></a>구문

```
catch (bad_typeid)
   statement
```

## <a name="remarks"></a>설명

**bad_typeid**의 인터페이스는 다음과 같습니다.

```cpp
class bad_typeid : public exception
{
public:
   bad_typeid(const char * _Message = "bad typeid");
   bad_typeid(const bad_typeid &);
   virtual ~bad_typeid();
};
```

다음 예제에서는 **bad_typeid** 예외를 throw하는 **typeid** 연산자를 보여 줍니다.

```cpp
// expre_bad_typeid.cpp
// compile with: /EHsc /GR
#include <typeinfo.h>
#include <iostream>

class A{
public:
   // object for class needs vtable
   // for RTTI
   virtual ~A();
};

using namespace std;
int main() {
A* a = NULL;

try {
   cout << typeid(*a).name() << endl;  // Error condition
   }
catch (bad_typeid){
   cout << "Object is NULL" << endl;
   }
}
```

## <a name="output"></a>출력

```Output
Object is NULL
```

## <a name="see-also"></a>참고 항목

[런타임 형식 정보](../cpp/run-time-type-information.md)<br/>
[키워드(C++)](../cpp/keywords-cpp.md)