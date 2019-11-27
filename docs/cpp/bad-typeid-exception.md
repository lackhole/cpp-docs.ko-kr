---
title: bad_typeid 예외
ms.date: 10/04/2019
f1_keywords:
- bad_typeid
- bad_typeid_cpp
helpviewer_keywords:
- bad_typeid exception
- exceptions [C++], bad_typeid
ms.assetid: 5963ed58-4ede-4597-957d-f7bbd06299c2
ms.openlocfilehash: bb56de77ba001b5a511ef3a2695d18109b1ed3ca
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245925"
---
# <a name="bad_typeid-exception"></a>bad_typeid 예외

**Typeid의 피연산자** 가 NULL 포인터인 경우에는 [typeid 연산자](../cpp/typeid-operator.md) 가 **bad_typeid** 예외를 throw 합니다.

## <a name="syntax"></a>구문

```
catch (bad_typeid)
   statement
```

## <a name="remarks"></a>주의

**Bad_typeid** 에 대 한 인터페이스는 다음과 같습니다.

```cpp
class bad_typeid : public exception
{
public:
   bad_typeid();
   bad_typeid(const char * _Message = "bad typeid");
   bad_typeid(const bad_typeid &);
   virtual ~bad_typeid();

   bad_typeid& operator=(const bad_typeid&);
   const char* what() const;
};
```

다음 예제에서는 **bad_typeid** 예외를 throw 하는 **typeid** 연산자를 보여 줍니다.

```cpp
// expre_bad_typeid.cpp
// compile with: /EHsc /GR
#include <typeinfo>
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

[런타임 형식 정보](../cpp/run-time-type-information.md)\
[키워드](../cpp/keywords-cpp.md)
