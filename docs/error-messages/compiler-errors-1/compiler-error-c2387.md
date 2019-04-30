---
title: 컴파일러 오류 C2387
ms.date: 11/04/2016
f1_keywords:
- C2387
helpviewer_keywords:
- C2387
ms.assetid: 6847b8e1-ffac-458d-ab88-0c92f72f2527
ms.openlocfilehash: df9e92bfa333be88e860bbdecd5acaa64ec80440
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393677"
---
# <a name="compiler-error-c2387"></a>컴파일러 오류 C2387

'type': 모호한 기본 클래스

둘 이상의 기본 클래스의 함수가 존재 하기 때문에 컴파일러는 함수 호출을 명확 하 게 확인 하지 못했습니다.

이 오류를 해결 하려면의 상속에서 기본 클래스 중 하나를 제거 하거나 함수 호출을 명시적으로 한정 합니다.

다음 샘플에서는 C2387 오류가 생성 됩니다.

```
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