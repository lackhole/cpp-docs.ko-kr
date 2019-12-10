---
title: 컴파일러 오류 C2443
ms.date: 11/04/2016
f1_keywords:
- C2443
helpviewer_keywords:
- C2443
ms.assetid: 315330d5-24bc-4193-a531-0642095be58f
ms.openlocfilehash: a088f86e09671bb07b516cbae279f31d75717308
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744214"
---
# <a name="compiler-error-c2443"></a>컴파일러 오류 C2443

피연산자 크기가 충돌 합니다.

명령에는 피연산자의 크기가 동일 해야 합니다.

다음 샘플에서는 C2443를 생성 합니다.

```cpp
// C2443.cpp
// processor: x86
short var;
int main() {
   __asm xchg ax,bl   // C2443
   __asm mov al,red   // C2443
   __asm mov al,BYTE PTR var   // OK
}
```
