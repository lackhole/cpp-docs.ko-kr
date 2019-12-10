---
title: 컴파일러 오류 C2400
ms.date: 11/04/2016
f1_keywords:
- C2400
helpviewer_keywords:
- C2400
ms.assetid: 1ba441ee-73f9-42a5-bfe9-fbeab93808eb
ms.openlocfilehash: 61043f3f97d4d91b66c3902cc33ed4be526541ae
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744773"
---
# <a name="compiler-error-c2400"></a>컴파일러 오류 C2400

' context '에서 인라인 어셈블러 구문 오류가 발생 했습니다. ' token '이 있습니다.

토큰에 지정 된 컨텍스트에서 구문 오류가 발생 했습니다.

다음 샘플에서는 C2400를 생성 합니다.

```cpp
// C2400.cpp
// processor: x86
int main() {
   __asm {
      heh ax,bx;   // C2400, heh is not a valid x86 instruction
      mov ax,bx;   // OK
   }
}
```
