---
title: 컴파일러 오류 C2910
ms.date: 11/04/2016
f1_keywords:
- C2910
helpviewer_keywords:
- C2910
ms.assetid: 09c50e6a-e099-42f6-8ed6-d80e292a7a36
ms.openlocfilehash: 58d56ad834b34425cda4ac7ba081eabd2424e451
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408357"
---
# <a name="compiler-error-c2910"></a>컴파일러 오류 C2910

'function': 명시적으로 특수화할 수 없습니다.

컴파일러에 명시적으로 함수를 두 번 특수화 하려고를 했습니다.

다음 샘플에서는 C2910를 생성합니다.

```
// C2910.cpp
// compile with: /c
template <class T>
struct S;

template <> struct S<int> { void f() {} };
template <> void S<int>::f() {}   // C2910 delete this specialization
```

C2910은 템플릿이 아닌 멤버를 명시적으로 특수화 하려는 경우에 생성할 수 있습니다. 즉, 함수 템플릿을 명시적으로 특수화할 수 있습니다.

다음 샘플에서는 C2910를 생성합니다.

```
// C2910b.cpp
// compile with: /c
template <class T> struct A {
   A(T* p);
};

template <> struct A<void> {
   A(void* p);
};

template <class T>
inline A<T>::A(T* p) {}

template <> A<void>::A(void* p){}   // C2910
// try the following line instead
// A<void>::A(void* p){}
```

이 오류는 Visual Studio.NET 2003에서 수행 된 컴파일러 규칙 작업의 결과로 생성 됩니다: 합니다.

코드를 시각적 개체의 Visual Studio.NET 2003 및 VISUAL Studio 버전에서 사용할 수에 대 한 C++를 제거 `template <>`합니다.

다음 샘플에서는 C2910를 생성합니다.

```
// C2910c.cpp
// compile with: /c
template <class T> class A {
   void f();
};

template <> class A<int> {
   void f();
};

template <> void A<int>::f() {}   // C2910
// try the following line instead
// void A<int>::f(){}   // OK
```