---
title: 컴파일러 오류 C2280
ms.date: 04/25/2017
f1_keywords:
- C2280
helpviewer_keywords:
- C2280
ms.assetid: e6c5b1fb-2b9b-4554-8ff9-775eeb37161b
ms.openlocfilehash: e1ec032878fefdc1992605df5ee1aa13c673d4cf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388906"
---
# <a name="compiler-error-c2280"></a>컴파일러 오류 C2280

'*선언*': 삭제 된 함수를 참조 하려고 합니다.

컴파일러가 참조 하려고 했습니다를 `deleted` 함수입니다. 이 오류를 명시적으로 표시 된 멤버 함수를 호출 하 여 발생할 수 있습니다 `= deleted` 소스 코드에서입니다. 이 오류를 자동으로 선언 되 고 표시 하는 클래스 또는 구조체의 암시적 특수 멤버 함수를 호출 하 여 발생할 수 있습니다도 `deleted` 컴파일러에서. 컴파일러를 자동으로 생성 하는 방법에 대 한 자세한 내용은 `default` 나 `deleted` 특수 멤버 함수를 참조 하십시오 [특수 멤버 함수](../../cpp/special-member-functions.md)합니다.

## <a name="example-explicitly-deleted-functions"></a>예제: 명시적으로 삭제 된 함수

에 대 한 호출을 명시적으로 `deleted` 함수에이 오류가 발생 합니다. 명시적으로 `deleted` 멤버 함수는 클래스 또는 구조체에 의도적으로이 문제를 해결 하도록 용도 방지 하기 위해은,이 방지 하려면 코드를 변경 해야 의미 합니다.

```cpp
// C2280_explicit.cpp
// compile with: cl /c /W4 C2280_explicit.cpp
struct A {
    A();
    A(int) = delete;
};

struct B {
    A a1;
    A a2 = A(3); // C2280, calls deleted A::A(int)
    // To fix, remove the call to A(int)
};

void f() {
    B b;    // calls implicit B::B(void)
}
```

## <a name="example-uninitialized-data-members"></a>예제: 초기화 되지 않은 데이터 멤버

초기화 되지 않은 참조 형식 데이터 멤버 또는 `const` 데이터 멤버를 암시적으로 선언한 컴파일러는 `deleted` 기본 생성자입니다. 이 문제를 해결 하려면 선언 되 면 데이터 멤버를 초기화 합니다.

```cpp
// C2280_uninit.cpp
// compile with: cl /c C2280_uninit.cpp
struct A {
    const int i; // uninitialized const-qualified data
    // members or reference type data members cause
    // the implicit default constructor to be deleted.
    // To fix, initialize the value in the declaration:
    // const int i = 42;
} a;    // C2280
```

## <a name="example-reference-and-const-data-members"></a>예제: 참조 및 const 데이터 멤버

A `const` 참조 형식 데이터 멤버를 선언 하는 컴파일러 또는 `deleted` 복사 할당 연산자입니다. 초기화 되 면 간단한 복사 또는 이동 사용할 수 없습니다. 이러한 멤버에 할당할 수 없습니다. 이 문제를 해결 하려면 오류를 일으키는 할당 작업을 제거 하기 위한 논리를 변경 하는 것이 좋습니다.

```cpp
// C2280_ref.cpp
// compile with: cl /c C2280_ref.cpp
extern int k;
struct A {
    A();
    int& ri = k; // a const or reference data member causes
    // implicit copy assignment operator to be deleted.
};

void f() {
    A a1, a2;
    // To fix, consider removing this assignment.
    a2 = a1;    // C2280
}
```

## <a name="example-movable-deletes-implicit-copy"></a>예제: 이동 가능한 암시적 복사본을 삭제합니다.

클래스 이동 생성자 혹은 이동 할당 연산자를 선언 하지만 복사 생성자를 명시적으로 선언 하지 않는 경우 컴파일러가 암시적으로 복사 생성자를 선언 하 고로 정의 `deleted`합니다. 마찬가지로 클래스 이동 생성자 혹은 이동 할당 연산자를 선언 하지만 복사 할당 연산자를 명시적으로 선언 하지 않는 경우 컴파일러가 암시적으로 복사 할당 연산자를 선언 하 고로 정의 `deleted`합니다. 이 문제를 해결 하려면 이러한 멤버를 명시적으로 선언 해야 합니다.

오류 C2280을 연결 하 여 표시 되 면를 `unique_ptr`, 방식일 것은 해당 복사 생성자를 호출 하려고 하기 때문에 `deleted` 함수. 기본적으로 `unique_ptr` 복사할 수 없습니다. 이동 생성자를 사용 하 여 소유권을 대신 합니다.

```cpp
// C2280_move.cpp
// compile with: cl /c C2280_move.cpp
class base
{
public:
    base();
    ~base();
    base(base&&);
    // Move constructor causes copy constructor to be
    // implicitly declared as deleted. To fix this
    // issue, you can explicitly declare a copy constructor:
    // base(base&);
    // If you want the compiler default version, do this:
    // base(base&) = default;
};

void copy(base *p)
{
    base b{*p};  // C2280
}
```

## <a name="example-variant-and-volatile-members"></a>예제: 변형 및 volatile 멤버

버전의 Visual Studio 2015 업데이트 2 이전 컴파일러는 익명 공용 구조체의 비준수 및 생성 된 기본 생성자 및 소멸자 되었습니다. 로 암시적으로 선언 이제 이러한 `deleted`합니다. 이러한 버전의 암시적 정의가 비준수 허용 `default` 복사 및 이동 생성자 및 `default` 복사 및 이동 할당 연산자가 있는 클래스 및 구조체에서 `volatile` 멤버 변수입니다. 컴파일러에서 이제 trivial이 아닌 생성자 및 대입 연산자를 고려 하 고 생성 하지 않습니다 `default` 구현 합니다. 로 복사 및 이동 생성자 및 공용 구조체 또는 클래스의 복사 및 이동 할당 연산자를 암시적으로 정의 된 이러한 클래스는 공용 구조체 또는 클래스 내의 익명 공용 구조체의 멤버인 경우 `deleted`합니다. 이 문제를 해결 하려면 필요한 특수 멤버 함수를 명시적으로 선언 해야 합니다.

```cpp
// C2280_variant.cpp
// compile with: cl /c C2280_variant.cpp
struct A {
    A() = default;
    A(const A&);
};

struct B {
    union {
        A a;
        int i;
    };
    // To fix this issue, declare the required
    // special member functions:
    // B();
    // B(const B& b);
};

int main() {
    B b1;
    B b2(b1);  // C2280
}
```

## <a name="example-indirect-base-members-deleted"></a>예제: 간접 기본 멤버 삭제

버전의 Visual Studio 2015 업데이트 2 이전 컴파일러 비준수 되었으며 특수 멤버의 함수를 호출할 간접적으로 파생 된 파생된 클래스를 허용 `private virtual` 기본 클래스입니다. 이제 컴파일러는 이러한 호출이 수행 되 면 컴파일러 오류 C2280을 발급 합니다.

이 예제에서는 클래스 `top` 가상 사설에서 간접적으로 파생 `base`합니다. 준수 하는 코드의 멤버 수 있습니다 `base` 액세스할 수 없습니다 `top`형식의 개체는 `top` 없습니다 기본 생성 또는 소멸 가능 합니다. 이전 컴파일러 동작에 의존 하는 코드에서이 문제를 해결 하려면 사용 하는 중간 클래스를 변경 `protected virtual` 파생 또는 변경 된 `top` 직접 파생을 사용 하는 클래스:

```cpp
// C2280_indirect.cpp
// compile with: cl /c C2280_indirect.cpp
class base
{
protected:
    base();
    ~base();
};

class middle : private virtual base {};
// Possible fix: Replace line above with:
// class middle : protected virtual base {};
class top : public virtual middle {};    // C4594, C4624
// Another possible fix: use direct derivation:
// class top : public virtual middle, private virtual base {};

void destroy(top *p)
{
    delete p;  // C2280
}
```
