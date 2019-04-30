---
title: 선언 사용
ms.date: 11/04/2016
helpviewer_keywords:
- using declaration
- declaring namespaces, unqualified names in namespaces
- declarations [C++], using-declaration
- namespaces [C++], unqualified names in
- using keyword [C++]
- declarations [C++], namespaces
ms.assetid: 4184e2b1-3adc-408e-b5f3-0b3f8b554723
ms.openlocfilehash: 46d8b1e13b55988efd40643482ffd6123034ccb5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403349"
---
# <a name="using-declaration"></a>선언 사용

선언을 사용 하 여 이름을는 선언적 영역에 도입 되었습니다는 선언을 사용 하 여 표시 됩니다.

## <a name="syntax"></a>구문

```
using [typename] nested-name-specifier unqualified-id ;
using declarator-list ;
```

### <a name="parameters"></a>매개 변수

*중첩 이름 지정자* 시퀀스로 네임 스페이스, 클래스 또는 열거형 이름 및 범위 확인 연산자 (:), 범위 확인 연산자를 종료 합니다. 이름을 전역 네임 스페이스에서 제공 하는 단일 범위 확인 연산자를 사용할 수 있습니다. 키워드 **typename** 는 선택 사항이 며 기본 클래스에서 클래스 템플릿을 도입할 때 종속 이름을 확인 하기 위해 사용할 수 있습니다.

*정규화 되지 않은 id* 정규화 되지 않은 id-식 식별자, 오버 로드 된 운영자 이름, 사용자 정의 리터럴 연산자 또는 변환 함수 이름, 클래스 소멸자 이름에 또는 템플릿 이름 및 인수 목록 일 수 있습니다.

*선언 자 목록* 쉼표로 구분 된 목록을 [**typename**] *중첩 이름 지정자* *정규화 되지 않은 id* 올 필요에 따라 선언 자는 줄임표 (...)입니다.

## <a name="remarks"></a>설명

엔터티에 대 한 동의어로 정규화 되지 않은 이름을 소개 선언을 사용 하 여 다른 곳에서 선언 합니다. 나타나는 선언 지역의 명시적 한정자 없이 사용할 특정 네임 스페이스에서 단일 이름 수 있습니다. 이 달리는 [지시문을 사용 하 여](../cpp/namespaces-cpp.md#using_directives)를 허용 하는 *모든* 네임 스페이스 한정자 없이 사용할 수 있는 이름입니다. 합니다 **를 사용 하 여** 키워드에도 사용 됩니다 [별칭을 입력](../cpp/aliases-and-typedefs-cpp.md)합니다.

## <a name="example"></a>예제

클래스 정의에서 선언을 사용 하 여 사용할 수 있습니다.

```cpp
// using_declaration1.cpp
#include <stdio.h>
class B {
public:
   void f(char) {
      printf_s("In B::f()\n");
   }

   void g(char) {
      printf_s("In B::g()\n");
   }
};

class D : B {
public:
   using B::f;    // B::f(char) is now visible as D::f(char)
   using B::g;    // B::g(char) is now visible as D::g(char)
   void f(int) {
      printf_s("In D::f()\n");
      f('c');     // Invokes B::f(char) instead of recursing
   }

   void g(int) {
      printf_s("In D::g()\n");
      g('c');     // Invokes B::g(char) instead of recursing
   }
};

int main() {
   D myD;
   myD.f(1);
   myD.g('a');
}
```

```Output
In D::f()
In B::f()
In B::g()
```

## <a name="example"></a>예제

사용 하 여 멤버를 선언 하는 데 사용 하는 경우 기본 클래스의 멤버로 선언 참조 해야 합니다.

```cpp
// using_declaration2.cpp
#include <stdio.h>

class B {
public:
   void f(char) {
      printf_s("In B::f()\n");
   }

   void g(char) {
      printf_s("In B::g()\n");
   }
};

class C {
public:
   int g();
};

class D2 : public B {
public:
   using B::f;   // ok: B is a base of D2
   // using C::g;   // error: C isn't a base of D2
};

int main() {
   D2 MyD2;
   MyD2.f('a');
}
```

```Output
In B::f()
```

## <a name="example"></a>예제

사용 하 여 선언 된 멤버 선언 명시적 정규화를 사용 하 여 참조할 수 있습니다. `::` 전역 네임 스페이스 접두사를 참조 합니다.

```cpp
// using_declaration3.cpp
#include <stdio.h>

void f() {
   printf_s("In f\n");
}

namespace A {
   void g() {
      printf_s("In A::g\n");
   }
}

namespace X {
   using ::f;   // global f is also visible as X::f
   using A::g;   // A's g is now visible as X::g
}

void h() {
   printf_s("In h\n");
   X::f();   // calls ::f
   X::g();   // calls A::g
}

int main() {
   h();
}
```

```Output
In h
In f
In A::g
```

## <a name="example"></a>예제

사용 하는 경우 선언한, 선언에 의해 만들어진 동의어에서 참조를 사용 하 여 지점에서 사용할 수 있는 정의에 선언 합니다. 사용 하 여 네임 스페이스에 추가 된 정의 선언이 올바른 동의어 없는 합니다.

정의한 이름을 **를 사용 하 여** 선언이 원래 이름에 대 한 별칭입니다. 형식, 링크 또는 기타 특성 원래 선언에는 영향을 주지 않습니다.

```cpp
// post_declaration_namespace_additions.cpp
// compile with: /c
namespace A {
   void f(int) {}
}

using A::f;   // f is a synonym for A::f(int) only

namespace A {
   void f(char) {}
}

void f() {
   f('a');   // refers to A::f(int), even though A::f(char) exists
}

void b() {
   using A::f;   // refers to A::f(int) AND A::f(char)
   f('a');   // calls A::f(char);
}
```

## <a name="example"></a>예제

로컬 선언 집합을 하는 경우 네임 스페이스의 함수에 대해 단일 이름은 선언적 영역에 지정 된, 해야 모두 동일한 엔터티를 참조 하거나 해야 모든 함수에 참조 선언을 사용 하 여 및 합니다.

```cpp
// functions_in_namespaces1.cpp
// C2874 expected
namespace B {
    int i;
    void f(int);
    void f(double);
}

void g() {
    int i;
    using B::i;   // error: i declared twice
    void f(char);
    using B::f;   // ok: each f is a function
}
```

위의 예제는 `using B::i` 문을 사용 하면 두 번째 `int i` 에 선언 해야 합니다 `g()` 함수입니다. `using B::f` 문을 사용 하 여 충돌 하지 합니다 `f(char)` 함수 이름을 정의 하 여 함수 `B::f` 형식이 다른 매개 변수.

## <a name="example"></a>예제

로컬 함수 선언은 선언을 사용 하 여 도입 된 함수와 동일한 이름과 형식을 가질 수 없습니다. 예를 들어:

```cpp
// functions_in_namespaces2.cpp
// C2668 expected
namespace B {
    void f(int);
    void f(double);
}

namespace C {
    void f(int);
    void f(double);
    void f(char);
}

void h() {
    using B::f;          // introduces B::f(int) and B::f(double)
    using C::f;          // C::f(int), C::f(double), and C::f(char)
    f('h');              // calls C::f(char)
    f(1);                // C2668 ambiguous: B::f(int) or C::f(int)?
    void f(int);         // C2883 conflicts with B::f(int) and C::f(int)
}
```

## <a name="example"></a>예제

상속을 기준으로 사용 하는 경우 선언은 이름을 기본 클래스에서 기본 클래스에서 동일한 이름 및 인수 형식에서 파생 된 클래스 재정의 가상 멤버 함수는 멤버 함수, 파생된 클래스 범위로 합니다.

```cpp
// using_declaration_inheritance1.cpp
#include <stdio.h>
struct B {
   virtual void f(int) {
      printf_s("In B::f(int)\n");
   }

   virtual void f(char) {
      printf_s("In B::f(char)\n");
   }

   void g(int) {
      printf_s("In B::g\n");
   }

   void h(int);
};

struct D : B {
   using B::f;
   void f(int) {   // ok: D::f(int) overrides B::f(int)
      printf_s("In D::f(int)\n");
   }

   using B::g;
   void g(char) {   // ok: there is no B::g(char)
      printf_s("In D::g(char)\n");
   }

   using B::h;
   void h(int) {}   // Note: D::h(int) hides non-virtual B::h(int)
};

void f(D* pd) {
   pd->f(1);     // calls D::f(int)
   pd->f('a');   // calls B::f(char)
   pd->g(1);     // calls B::g(int)
   pd->g('a');   // calls D::g(char)
}

int main() {
   D * myd = new D();
   f(myd);
}
```

```Output
In D::f(int)
In B::f(char)
In B::g
In D::g(char)
```

## <a name="example"></a>예제

모든 인스턴스의 이름 사용 하 여 언급 된 선언 액세스할 수 있어야 합니다. 특히, 파생된 클래스를 사용 하 여 사용 하는 경우 멤버 이름 기본 클래스의 멤버에 액세스 하려면 선언 액세스할 수 있어야 합니다. 이름이 오버 로드 된 멤버 함수는 라는 모든 함수에 액세스할 수 있어야 합니다.

멤버의 액세스 가능성에 자세한 내용은 참조 [멤버 Access Control](../cpp/member-access-control-cpp.md)합니다.

```cpp
// using_declaration_inheritance2.cpp
// C2876 expected
class A {
private:
   void f(char);
public:
   void f(int);
protected:
   void g();
};

class B : public A {
   using A::f;   // C2876: A::f(char) is inaccessible
public:
   using A::g;   // B::g is a public synonym for A::g
};
```

## <a name="see-also"></a>참고자료

[네임스페이스](../cpp/namespaces-cpp.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)