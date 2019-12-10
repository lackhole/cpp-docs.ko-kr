---
title: 컴파일러 오류 C2647
ms.date: 11/04/2016
f1_keywords:
- C2647
helpviewer_keywords:
- C2647
ms.assetid: 1034589e-bc3e-41a6-831f-2a1a4b8a2500
ms.openlocfilehash: 9553c85efeedb4d3eee4bd40f9e3b86707fd7eb1
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758387"
---
# <a name="compiler-error-c2647"></a>컴파일러 오류 C2647

' operator ': ' type2 '에서 ' type1 '을 역 참조할 수 없습니다.

멤버 포인터 연산자 (`->*` 또는 `.*`)의 왼쪽 피연산자를 오른쪽 연산자와 관련 된 형식으로 암시적으로 변환할 수 없습니다.

다음 샘플에서는 C2647를 생성 합니다.

```cpp
// C2647.cpp
class C {};
class D {};

int main() {
   D d, *pd;
   C c, *pc = 0;
   int C::*pmc = 0;
   pd->*pmc = 0;   // C2647
   d.*pmc = 0;   // C2647

   // OK
   pc->*pmc = 0;
   c.*pmc = 0;
}
```
