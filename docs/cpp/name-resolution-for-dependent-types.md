---
title: 종속적인 형식에 대한 이름 확인
ms.date: 11/04/2016
ms.assetid: 34066bb4-0c79-4fd8-bda7-539a60a277ab
ms.openlocfilehash: 798cc7067967e8992c32d7c0ced9f647e4877110
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222408"
---
# <a name="name-resolution-for-dependent-types"></a>종속적인 형식에 대한 이름 확인

템플릿 정의의 정규화된 이름에 **typename**을 사용하여 지정된 정규화 이름이 형식을 식별한다는 것을 컴파일러에 지시합니다. 자세한 내용은 [typename](../cpp/typename.md)을 참조하십시오.

```cpp
// template_name_resolution1.cpp
#include <stdio.h>
template <class T> class X
{
public:
   void f(typename T::myType* mt) {}
};

class Yarg
{
public:
   struct myType { };
};

int main()
{
   X<Yarg> x;
   x.f(new Yarg::myType());
   printf("Name resolved by using typename keyword.");
}
```

```Output
Name resolved by using typename keyword.
```

종속 이름에 대한 이름 검색은 템플릿 정의의 컨텍스트(다음 예제에서 `myFunction(char)`를 검색하는 컨텍스트) 및 템플릿 인스턴스화의 컨텍스트에서 이름을 조사합니다. 다음 예제에서는 템플릿이 main에서 인스턴스화되므로 `MyNamespace::myFunction`은 인스턴스화된 지점부터 표시되며 더 잘 일치하는 것으로 선택됩니다. `MyNamespace::myFunction`의 이름이 바뀐 경우 `myFunction(char)`이 대신 호출됩니다.

모든 이름은 종속 이름인 것처럼 확인됩니다. 그러나 충돌 발생 가능성이 있을 경우 철저하게 정규화된 이름을 사용하는 것이 좋습니다.

```cpp
// template_name_resolution2.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

void myFunction(char)
{
   cout << "Char myFunction" << endl;
}

template <class T> class Class1
{
public:
   Class1(T i)
   {
      // If replaced with myFunction(1), myFunction(char)
      // will be called
      myFunction(i);
}
};

namespace MyNamespace
{
   void myFunction(int)
   {
      cout << "Int MyNamespace::myFunction" << endl;
   }
};

using namespace MyNamespace;

int main()
{
   Class1<int>* c1 = new Class1<int>(100);
}
```

### <a name="output"></a>출력

```Output
Int MyNamespace::myFunction
```

### <a name="template-disambiguation"></a>템플릿 명확성

Visual Studio 2012의 Visual C++는 "템플릿" 키워드를 사용하여 명확성에 대한 C++ 98/03/11 표준 규칙을 적용합니다. 다음 예제에서는 Visual Studio 2010는 표준에 맞지 않는 줄 및 표준에 맞는 줄 수락 합니다.  Visual Studio 2012의 Visual C++는 표준에 맞는 줄만 허용합니다.

```cpp
#include <iostream>
#include <ostream>
#include <typeinfo>
using namespace std;

template <typename T> struct Allocator {
    template <typename U> struct Rebind {
        typedef Allocator<U> Other;
    };
};

template <typename X, typename AY> struct Container {
    #if defined(NONCONFORMANT)
        typedef typename AY::Rebind<X>::Other AX; // nonconformant
    #elif defined(CONFORMANT)
        typedef typename AY::template Rebind<X>::Other AX; // conformant
    #else
        #error Define NONCONFORMANT or CONFORMANT.
    #endif
};

int main() {
    cout << typeid(Container<int, Allocator<float>>::AX).name() << endl;
}
```

기본적으로 C++에서는 `AY::Rebind`가 템플릿이 아니며 컴파일러에서 다음 " `<`"을 less-than으로 해석한다고 가정하기 때문에 명확성 규칙 준수가 필요합니다. C++에 `Rebind`가 템플릿이라는 것을 인지시켜 "`<`"을 꺾쇠로 올바르게 구문 분석할 수 있도록 해야 합니다.

## <a name="see-also"></a>참고 항목

[템플릿 및 이름 확인](../cpp/templates-and-name-resolution.md)
