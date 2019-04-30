---
title: 컴파일러 경고(수준 1) C4401
ms.date: 11/04/2016
f1_keywords:
- C4401
helpviewer_keywords:
- C4401
ms.assetid: 2e7ca136-f144-4b40-b847-82976e8643fc
ms.openlocfilehash: c7e6cf8a52288d895b74481678dc91fee387a6a3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62280427"
---
# <a name="compiler-warning-level-1-c4401"></a>컴파일러 경고(수준 1) C4401

'비트 필드': 멤버는 비트 필드

인라인 어셈블리 코드는 비트 필드 멤버에 액세스 하려고 합니다. 인라인 어셈블리 비트 필드 멤버 보다 먼저 마지막 압축 경계를 사용 하도록 비트 필드 멤버를 액세스할 수 없습니다.

이 경고를 방지 하려면 인라인 어셈블리 코드에 대 한 참조를 만들기 전에 비트 필드를 적절 한 형식으로 캐스팅 합니다. 다음 샘플에서는 C4401 오류가 생성 됩니다.

```
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