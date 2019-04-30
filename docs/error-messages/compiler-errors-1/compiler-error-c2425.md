---
title: 컴파일러 오류 C2425
ms.date: 11/04/2016
f1_keywords:
- C2425
helpviewer_keywords:
- C2425
ms.assetid: 0ce59404-9aff-4e01-aa8d-27d23e92eb30
ms.openlocfilehash: fcbcf06df3330320bf014c132abc543e2e2e8087
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402842"
---
# <a name="compiler-error-c2425"></a>컴파일러 오류 C2425

'token': 'context'에 비상수 식이 있습니다.

이 컨텍스트에서 토큰이 비상수 식의 일부를 형성합니다.

이 문제를 해결하려면 토큰을 상수 리터럴 또는 계산으로 바꿉니다.

다음 샘플에서는 C2425 오류가 발생하는 경우를 보여 줍니다.

```
// C2425.cpp
// processor: x86
int main() {
   int i = 3;
   __asm {
      mov eax, [ebp - i]   // C2425
      mov eax, [ebp - 3]   // OK
   }
}
```