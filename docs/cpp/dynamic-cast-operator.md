---
title: dynamic_cast 연산자
ms.date: 11/19/2018
f1_keywords:
- dynamic_cast_cpp
helpviewer_keywords:
- dynamic_cast keyword [C++]
ms.assetid: f380ada8-6a18-4547-93c9-63407f19856b
ms.openlocfilehash: 3b359885eb72f9272fb1efe14afe9a6cbe6ddb30
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399063"
---
# <a name="dynamiccast-operator"></a>dynamic_cast 연산자

피연산자를 변환 `expression` 형식의 개체에 `type-id`입니다.

## <a name="syntax"></a>구문

```
dynamic_cast < type-id > ( expression )
```

## <a name="remarks"></a>설명

`type-id` 대 한 포인터 또는 이전에 정의 된 클래스 형식에 대 한 참조는 "void"포인터 여야 합니다. `type-id`이 포인터인 경우 `expression`의 형식은 포인터여야 하며 `type-id`이 참조인 경우에는 l 값이어야 합니다.

참조 [static_cast](../cpp/static-cast-operator.md) 에 대 한 설명은 차이 정적 및 동적 캐스팅 변환 사이 및 각 사용 하기에 적합 합니다.

두 가지 주요 변경 내용이의 동작이 **dynamic_cast** 관리 코드에서:

- **dynamic_cast** boxed 열거형의 내부 형식에 대 한 포인터로 변환된 포인터 대신 0을 반환 하는 런타임 시 실패 합니다.

- **dynamic_cast** 더 이상 예외를 throw 하면 `type-id` 는 런타임 시 실패 한 캐스팅을 사용 하 여 값 형식으로 내부 포인터입니다.  이제 캐스팅 throw 하는 대신 0 포인터 값이 반환 됩니다.

하는 경우 `type-id` 는 명확한 액세스할 수 있는 직접 또는 간접 기본 클래스에 대 한 포인터가 `expression`, 형식의 고유한 하위 개체에 대 한 포인터 `type-id` 결과입니다. 예를 들어:

```cpp
// dynamic_cast_1.cpp
// compile with: /c
class B { };
class C : public B { };
class D : public C { };

void f(D* pd) {
   C* pc = dynamic_cast<C*>(pd);   // ok: C is a direct base class
                                   // pc points to C subobject of pd
   B* pb = dynamic_cast<B*>(pd);   // ok: B is an indirect base class
                                   // pb points to B subobject of pd
}
```

파생된 클래스에서 파생 된 클래스에서 클래스 계층에 대 한 포인터를 이동 하기 때문이 유형의 변환 "업캐스팅" 라고 합니다. 업 캐스트는 암시적 변환이 수행 됩니다.

하는 경우 `type-id` 은 void *의 실제 형식을 결정 하는 런타임 검사가 수행 됩니다 `expression`합니다. 결과 완전 한 가리키는 개체에 대 한 포인터는 `expression`합니다. 예를 들어:

```cpp
// dynamic_cast_2.cpp
// compile with: /c /GR
class A {virtual void f();};
class B {virtual void f();};

void f() {
   A* pa = new A;
   B* pb = new B;
   void* pv = dynamic_cast<void*>(pa);
   // pv now points to an object of type A

   pv = dynamic_cast<void*>(pb);
   // pv now points to an object of type B
}
```

경우 `type-id` void *, 없는 경우 개체를 가리키는 참조 하는 런타임 검사가 수행 됩니다 `expression` 가리키는 형식으로 변환할 수 `type-id`입니다.

경우 형식의 `expression` 형식의 기본 클래스인 `type-id`, 있는지는 런타임 검사가 수행 됩니다 `expression` 형식의 완전 한 개체를 가리키는 실제로 `type-id`합니다. True 이면 결과 완전 한 개체의 형식에 대 한 포인터 `type-id`합니다. 예를 들어:

```cpp
// dynamic_cast_3.cpp
// compile with: /c /GR
class B {virtual void f();};
class D : public B {virtual void f();};

void f() {
   B* pb = new D;   // unclear but ok
   B* pb2 = new B;

   D* pd = dynamic_cast<D*>(pb);   // ok: pb actually points to a D
   D* pd2 = dynamic_cast<D*>(pb2);   // pb2 points to a B not a D
}
```

이 유형의 변환 이라고는 여기에서 파생 클래스에 지정된 된 클래스에서 클래스 계층 구조 아래쪽에 대 한 포인터를 이동 하기 때문 "다운 캐스팅"입니다.

다중 상속의 경우에서 모호성에 대 한 가능성 도입 됩니다. 다음 그림에 표시 된 클래스 계층 구조를 고려 합니다.

CLR 형식의 경우 **dynamic_cast** 변환이 암시적으로 수행할 수 있으면 no-op 또는 MSIL로 인해 `isinst` 동적 검사를 수행 하 고 반환 하는 명령 **nullptr** 경우는 변환이 실패합니다.

다음 샘플에서는 **dynamic_cast** 클래스 인스턴스의 특정 형식 인지 확인 하려면:

```cpp
// dynamic_cast_clr.cpp
// compile with: /clr
using namespace System;

void PrintObjectType( Object^o ) {
   if( dynamic_cast<String^>(o) )
      Console::WriteLine("Object is a String");
   else if( dynamic_cast<int^>(o) )
      Console::WriteLine("Object is an int");
}

int main() {
   Object^o1 = "hello";
   Object^o2 = 10;

   PrintObjectType(o1);
   PrintObjectType(o2);
}
```

![다중 상속을 보여 주는 계층 구조 클래스](../cpp/media/vc39011.gif "다중 상속을 보여 주는 계층 구조 클래스") <br/>
여러 상속을 보여 주는 클래스 계층 구조

형식의 개체에 대 한 포인터 `D` 안전 하 게 캐스팅할 수 있습니다 `B` 또는 `C`합니다. 그러나 경우 `D` 가리키도록 캐스팅은 `A` 개체의 인스턴스 `A` 초래? 따라서 모호한 캐스팅 오류가 발생 합니다. 를이 문제를 해결 하기 위해 두 개의 모호 하지 않은 캐스트를 수행할 수 있습니다. 예를 들어:

```cpp
// dynamic_cast_4.cpp
// compile with: /c /GR
class A {virtual void f();};
class B {virtual void f();};
class D : public B {virtual void f();};

void f() {
   D* pd = new D;
   B* pb = dynamic_cast<B*>(pd);   // first cast to B
   A* pa2 = dynamic_cast<A*>(pb);   // ok: unambiguous
}
```

가상 기본 클래스를 사용 하는 경우에 추가 모호성을 도입할 수 있습니다. 다음 그림에 표시 된 클래스 계층 구조를 고려 합니다.

![가상 기본 클래스를 보여 주는 계층 구조 클래스](../cpp/media/vc39012.gif "가상 기본 클래스를 보여 주는 계층 구조 클래스") <br/>
가상 기본 클래스를 보여 주는 클래스 계층 구조

이 계층에서 `A` 는 가상 기본 클래스입니다. 클래스의 인스턴스가 지정 된 `E` 에 대 한 포인터를 `A` 하위 개체를 **dynamic_cast** 포인터로 `B` 모호성으로 인해 실패 합니다. 먼저 전체으로 다시 캐스팅 해야 `E` 개체를 만든 다음, 올바른 연결할 명확한 방식으로 작업을 진행 계층 백업 `B` 개체입니다.

다음 그림에 표시 된 클래스 계층 구조를 고려 합니다.

![중복 기본 클래스를 보여 주는 계층 클래스](../cpp/media/vc39013.gif "클래스 중복 기본 클래스를 보여 주는 계층 구조") <br/>
중복된 기본 클래스를 보여 주는 클래스 계층 구조

형식의 개체를 지정 된 `E` 에 대 한 포인터를 `D` 하위 개체에서 탐색 하는 `D` 맨 왼쪽에는 하위 `A` 하위 개체, 세 가지 변환을 만들 수 있습니다. 수행할 수 있습니다는 **dynamic_cast** 변환할 합니다 `D` 에 대 한 포인터를 `E` 포인터를 변환 (하거나 **dynamic_cast** 또는 암시적으로 변환) 에서`E`하 `B`, 및 마지막으로 암시적으로 변환할 `B` 에 `A`입니다. 예를 들어:

```cpp
// dynamic_cast_5.cpp
// compile with: /c /GR
class A {virtual void f();};
class B : public A {virtual void f();};
class C : public A { };
class D {virtual void f();};
class E : public B, public C, public D {virtual void f();};

void f(D* pd) {
   E* pe = dynamic_cast<E*>(pd);
   B* pb = pe;   // upcast, implicit conversion
   A* pa = pb;   // upcast, implicit conversion
}
```

합니다 **dynamic_cast** 연산자는 "간 캐스팅 합니다." 하는 데 사용할 수도 있습니다 같은 클래스 계층 구조를 사용 하는 것에서 예를 들어 포인터를 캐스팅할 수는 `B` 하위 개체에는 `D` 완전 한 개체는 형식의 하위 개체 `E`합니다.

캐스트 간 고려를 실제로 수 있기에 대 한 포인터에서 변환을 수행 `D` 맨 왼쪽에 대 한 포인터로 `A` 두 단계에서 하위 개체입니다. 크로스에서 캐스팅을 수행할 수 있습니다 `D` 하 `B`, 다음에서 암시적 변환을 `B` 에 `A`입니다. 예를 들어:

```cpp
// dynamic_cast_6.cpp
// compile with: /c /GR
class A {virtual void f();};
class B : public A {virtual void f();};
class C : public A { };
class D {virtual void f();};
class E : public B, public C, public D {virtual void f();};

void f(D* pd) {
   B* pb = dynamic_cast<B*>(pd);   // cross cast
   A* pa = pb;   // upcast, implicit conversion
}
```

Null 포인터 값에서 대상 형식의 null 포인터 값으로 변환할 **dynamic_cast**합니다.

사용 하는 경우 `dynamic_cast < type-id > ( expression )`이면 `expression` 형식으로 안전 하 게 변환할 수 없습니다 `type-id`, 런타임 검사 실패로 캐스팅 하면 됩니다. 예를 들어:

```cpp
// dynamic_cast_7.cpp
// compile with: /c /GR
class A {virtual void f();};
class B {virtual void f();};

void f() {
   A* pa = new A;
   B* pb = dynamic_cast<B*>(pa);   // fails at runtime, not safe;
   // B not derived from A
}
```

포인터 형식으로 실패 한 캐스팅의 값에는 null 포인터가 됩니다. 실패 한 캐스팅 형식을 throw를 참조 하는 [bad_cast 예외](../cpp/bad-cast-exception.md)합니다.   하는 경우 `expression` 가리키도록 하지 않거나 올바른 개체 참조는 `__non_rtti_object` 예외가 throw 됩니다.

참조 [typeid](../cpp/typeid-operator.md) 에 대 한 설명은 `__non_rtti_object` 예외입니다.

## <a name="example"></a>예제

다음 샘플에는 기본 클래스 (구조체는) 포인터를 (C 구조체) 개체를 만듭니다.  이 한 개를 팩트 있습니다 가상 함수가 런타임 다형성을 사용 하도록 설정 합니다.

또한 샘플 계층의 비가상 함수를 호출합니다.

```cpp
// dynamic_cast_8.cpp
// compile with: /GR /EHsc
#include <stdio.h>
#include <iostream>

struct A {
    virtual void test() {
        printf_s("in A\n");
   }
};

struct B : A {
    virtual void test() {
        printf_s("in B\n");
    }

    void test2() {
        printf_s("test2 in B\n");
    }
};

struct C : B {
    virtual void test() {
        printf_s("in C\n");
    }

    void test2() {
        printf_s("test2 in C\n");
    }
};

void Globaltest(A& a) {
    try {
        C &c = dynamic_cast<C&>(a);
        printf_s("in GlobalTest\n");
    }
    catch(std::bad_cast) {
        printf_s("Can't cast to C\n");
    }
}

int main() {
    A *pa = new C;
    A *pa2 = new B;

    pa->test();

    B * pb = dynamic_cast<B *>(pa);
    if (pb)
        pb->test2();

    C * pc = dynamic_cast<C *>(pa2);
    if (pc)
        pc->test2();

    C ConStack;
    Globaltest(ConStack);

   // will fail because B knows nothing about C
    B BonStack;
    Globaltest(BonStack);
}
```

```Output
in C
test2 in B
in GlobalTest
Can't cast to C
```

## <a name="see-also"></a>참고자료

[캐스팅 연산자](../cpp/casting-operators.md)<br/>
[키워드(C++)](../cpp/keywords-cpp.md)