---
title: 컴파일러 오류 C2325
ms.date: 11/04/2016
f1_keywords:
- C2325
helpviewer_keywords:
- C2325
ms.assetid: e6b0a186-3f2a-4adf-beae-fadd75492bf7
ms.openlocfilehash: 28b291bd68971d7759589a75d8bafbf6e873dd39
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300957"
---
# <a name="compiler-error-c2325"></a>컴파일러 오류 C2325

'type': 'name' 오른쪽에 예기치 않은 형식

잘못 된 형식의 소멸자를 호출 합니다.

다음 샘플에서는 C2325 오류가 생성 됩니다.

```
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