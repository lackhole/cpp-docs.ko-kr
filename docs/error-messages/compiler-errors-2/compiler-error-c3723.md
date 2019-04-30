---
title: 컴파일러 오류 C3723
ms.date: 11/04/2016
f1_keywords:
- C3723
helpviewer_keywords:
- C3723
ms.assetid: ef0fb1ff-3f9a-4093-a6b6-894d1ab0c4b9
ms.openlocfilehash: a61a59c89bacbdc1e4f6e6848b3bb616c6a91772
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328200"
---
# <a name="compiler-error-c3723"></a>컴파일러 오류 C3723

'function': 이벤트를 확인할 수 없습니다.

`function` 호출 하는 이벤트를 확인 하지 못했습니다.

다음 샘플에서는 C3723 오류가 생성 됩니다.

```
// C3723.cpp
struct A {
   // To resolve, comment void f(int); and uncomment the __event function
   void f(int);
   // __event void f(int);
   void f(float);

};

struct B {
   void g(int);
   B(A* a) {
   __hook(&A::f, a, &B::g);   // C3723
   }
};

int main() {
}
```

`__hook` 및 `__unhook` /clr 프로그래밍을 사용 하 여 호환 되지 않습니다.  대신 + = 및-= 연산자를 사용 합니다.

다음 샘플에서는 C3723 오류가 생성 됩니다.

```
// C3723b.cpp
// compile with: /clr
using namespace System;

public delegate void delegate1();

public ref class CPSource {
public:
   event delegate1^ event1;
};

public ref class CReceiver {
public:
   void Handler1() {
   }

   void UnhookAll(CPSource^ pSrc) {
      __unhook(&CPSource::event1, pSrc, &CReceiver::Handler1); // C3723
      // Try the following line instead.
      // pSrc->event1 -= gcnew delegate1(this, &CReceiver::Handler1);
   }
};

int main() {
}
```