---
title: 컴파일러 오류 C2911
ms.date: 11/04/2016
f1_keywords:
- C2911
helpviewer_keywords:
- C2911
ms.assetid: 83c7c01a-ab6a-4179-9fb0-289a9ec8d44e
ms.openlocfilehash: 59061ab8126e3ba45c0b456bb4428652cab8a7e9
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761103"
---
# <a name="compiler-error-c2911"></a>컴파일러 오류 C2911

'member': 현재 범위에서 선언하거나 정의할 수 없습니다.

네임스페이스, 클래스 또는 함수 내에서는 동일한 네임스페이스, 클래스 또는 함수의 멤버 또는 동일한 네임스페이스, 클래스 또는 함수로 묶인 멤버만 정의할 수 있습니다.

다음 샘플에서는 C2911을 생성합니다.

```cpp
// C2911.cpp
struct A;

namespace M {
   struct D;
}

namespace N {
   struct C;

   namespace O {
      struct B;
   }

   // in N
   struct ::A {};   // C2911  A is member of global NS
   struct O::B{};   // OK B is in O, O is inside of N
   struct C {};     // OK C is member of N
   struct M::D {};  // C2911 D is member of M, M not enclosed by N
}
```
