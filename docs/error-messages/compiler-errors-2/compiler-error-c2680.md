---
title: 컴파일러 오류 C2680
ms.date: 11/04/2016
f1_keywords:
- C2680
helpviewer_keywords:
- C2680
ms.assetid: d6f7129e-dd17-4661-b680-18d6b925b1cc
ms.openlocfilehash: 7a0f58ae16baee00a86038c633f996a7d27a1019
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386813"
---
# <a name="compiler-error-c2680"></a>컴파일러 오류 C2680

'type': 이름에 대 한 잘못 된 대상 형식

캐스팅 연산자는 포인터 또는 참조 되지 않는 형식으로 변환 하려고 했습니다. 합니다 [dynamic_cast](../../cpp/dynamic-cast-operator.md) 연산자는 포인터 또는 참조에 대해서만 사용할 수 있습니다.

다음 샘플에서는 C2680 오류가 생성 됩니다.

```
// C2680.cpp
// compile with: /c
class A { virtual void f(); };
class B : public A {};

void g(B b) {
   A a;
   a = dynamic_cast<A>(b);   // C2680  target not a reference type
   a = dynamic_cast<A&>(b);   // OK
}
```

C2680은 대상이 정의 되지 않은 경우에 발생할 수 있습니다.

```
// C2680b.cpp
// compile with: /clr /c
// C2680 expected
using namespace System::Collections;

// Delete the following line to resolve.
ref class A;   // not defined

// Uncomment the following line to resolve.
// ref class A{};

public ref class B : ArrayList {
   property A^ C[int] {
      A^ get(int index) {
         return dynamic_cast<A^>(this->default::get(index));
      }
      void set(int index, A^ value) {
         this->default::set(index, value);
      }
   }
};
```