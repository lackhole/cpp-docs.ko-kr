---
title: 컴파일러 경고(수준 3) C4243
ms.date: 11/04/2016
f1_keywords:
- C4243
helpviewer_keywords:
- C4243
ms.assetid: ca72f9ad-ce0b-43a9-a68c-106e1f8b90ef
ms.openlocfilehash: e08a8538c93681c59779f681812a9ba8f7e316a9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402205"
---
# <a name="compiler-warning-level-3-c4243"></a>컴파일러 경고(수준 3) C4243

'conversion type' 변환이 'type1'에서 'type2'에 있지만 액세스할 수 없는

파생된 클래스에 대 한 포인터를 기본 클래스에 대 한 포인터로 변환 됩니다 있지만 파생된 클래스는 private 또는 protected 액세스를 사용 하 여 기본 클래스를 상속 합니다.

다음 샘플에서는 C4243 오류가 생성 됩니다.

```
// C4243.cpp
// compile with: /W3
// C4243 expected
struct B {
   int f() {
      return 0;
   };
};

struct D : private B {};
struct E : public B {};

int main() {
   // Delete the following 2 lines to resolve.
   int (D::* d)() = (int(D::*)()) &B::f;
   d;

   int (E::* e)() = (int(E::*)()) &B::f; // OK
   e;
}
```