---
title: 컴파일러 오류 C2400
ms.date: 11/04/2016
f1_keywords:
- C2400
helpviewer_keywords:
- C2400
ms.assetid: 1ba441ee-73f9-42a5-bfe9-fbeab93808eb
ms.openlocfilehash: 3ede43ec5ddb61b85c48094193d01d18bacae2bc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62282805"
---
# <a name="compiler-error-c2400"></a>컴파일러 오류 C2400

인라인 어셈블러 구문 오류가 '컨텍스트'; 'token'을 찾을 수합니다

토큰이 지정 된 컨텍스트에서 구문 오류가 발생 했습니다.

다음 샘플에서는 C2400를 생성합니다.

```
// C2400.cpp
// processor: x86
int main() {
   __asm {
      heh ax,bx;   // C2400, heh is not a valid x86 instruction
      mov ax,bx;   // OK
   }
}
```