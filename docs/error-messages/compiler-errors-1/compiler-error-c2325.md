---
title: 컴파일러 오류 C2325
ms.date: 11/04/2016
f1_keywords:
- C2325
helpviewer_keywords:
- C2325
ms.assetid: e6b0a186-3f2a-4adf-beae-fadd75492bf7
ms.openlocfilehash: 4ed0ca7403ff88ddcd0bd71123b1cbead7d020e1
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74747815"
---
# <a name="compiler-error-c2325"></a>컴파일러 오류 C2325

' type ': ' name ' 오른쪽에 예기치 않은 형식이 있습니다.

잘못 된 형식의 소멸자를 호출 했습니다.

다음 샘플에서는 C2325를 생성 합니다.

```cpp
// C2325.cpp
// compile with: /c
class A {};
typedef A* pA_t;
void f() {
    A** ppa = new A *;
    ppa->~A*;   // C2325

   pA_t *ppa2 = new pA_t;
   ppa2->~pA_t();   // OK
}
```
