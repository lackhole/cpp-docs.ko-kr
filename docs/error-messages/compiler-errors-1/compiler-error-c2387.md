---
title: 컴파일러 오류 C2387
ms.date: 11/04/2016
f1_keywords:
- C2387
helpviewer_keywords:
- C2387
ms.assetid: 6847b8e1-ffac-458d-ab88-0c92f72f2527
ms.openlocfilehash: a884099c7407113d7ef7604f4eec28e0fa86d87e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745102"
---
# <a name="compiler-error-c2387"></a>컴파일러 오류 C2387

' type ': 모호한 기본 클래스입니다.

함수가 둘 이상의 기본 클래스에 있기 때문에 컴파일러에서 함수 호출을 명확 하 게 확인할 수 없습니다.

이 오류를 해결 하려면 상속에서 기본 클래스 중 하나를 제거 하거나 함수 호출을 명시적으로 한정 합니다.

다음 샘플에서는 C2387를 생성 합니다.

```cpp
// C2387.cpp
namespace N1 {
   struct B {
      virtual void f() {
      }
   };
}

namespace N2 {
   struct B {
      virtual void f() {
      }
   };
}

struct D : N1::B, N2::B {
   virtual void f() {
      B::f();   // C2387
      // try the following line instead
      // N1::B::f();
   }
};

int main() {
   D aD;
   aD.f();
}
```
