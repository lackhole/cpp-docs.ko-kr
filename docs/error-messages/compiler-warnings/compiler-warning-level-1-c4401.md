---
title: 컴파일러 경고 (수준 1) C4401
ms.date: 11/04/2016
f1_keywords:
- C4401
helpviewer_keywords:
- C4401
ms.assetid: 2e7ca136-f144-4b40-b847-82976e8643fc
ms.openlocfilehash: 242c854339608c88d139c898d81d142c52f90134
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966310"
---
# <a name="compiler-warning-level-1-c4401"></a>컴파일러 경고 (수준 1) C4401

' 비트 필드 ': 멤버가 비트 필드입니다.

인라인 어셈블리 코드는 비트 필드 멤버에 액세스 하려고 합니다. 인라인 어셈블리는 비트 필드 멤버에 액세스할 수 없으므로 비트 필드 멤버 앞의 마지막 압축 경계를 사용 합니다.

이 경고를 방지 하려면 인라인 어셈블리 코드에서 참조를 만들기 전에 비트 필드를 적절 한 형식으로 캐스팅 합니다. 다음 샘플에서는 C4401를 생성 합니다.

```cpp
// C4401.cpp
// compile with: /W1
// processor: x86
typedef struct bitfield {
   signed bit : 1;
} mybitfield;

int main() {
   mybitfield bf;
   bf.bit = 0;
   __asm {
      mov bf.bit,0;   // C4401
   }

   /* use the following __asm block to resolve the warning
   int i = (int)bf.bit;
   __asm {
      mov i,0;
   }
   */
}
```