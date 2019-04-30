---
title: 컴파일러 오류 C2251
ms.date: 11/04/2016
f1_keywords:
- C2251
helpviewer_keywords:
- C2251
ms.assetid: fefe050c-f8d3-4316-b237-8007dbcdd3bf
ms.openlocfilehash: b7ffb5b8d425e74523e491827ffb8878b8e03b38
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62301385"
---
# <a name="compiler-error-c2251"></a>컴파일러 오류 C2251

네임스페이스 'namespace'에 멤버 'member'가 없습니다. 'member'를 사용하시겠습니까?

컴파일러에서 지정된 네임스페이스의 식별자를 찾을 수 없습니다.

다음 샘플에서는 C2251을 생성합니다.

```
// C2251.cpp
// compile with: /c
namespace A {
   namespace B {
      void f1();
   }

   using namespace B;
}

void A::f1() {}   // C2251
void A::B::f1() {}   // OK
```