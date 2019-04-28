---
title: 컴파일러 경고(수준 4) C4740
ms.date: 11/04/2016
f1_keywords:
- C4740
helpviewer_keywords:
- C4740
ms.assetid: 85528969-966a-44b4-8a2f-971704c64477
ms.openlocfilehash: 936dfb5464eabe7b1ac44df24445224fb9e204a0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187032"
---
# <a name="compiler-warning-level-4-c4740"></a>컴파일러 경고(수준 4) C4740

인라인 asm 코드 안팎에서 흐름을 선택 하면 전역 최적화

부재 중 또는 점프 경우는 `asm` 블록에 해당 함수에 대 한 전역 최적화가 해제 됩니다.

다음 샘플에서는 C4740 오류가 생성 됩니다.

```
// C4740.cpp
// compile with: /O2 /W4
// processor: x86
int main() {
   __asm jmp tester
   tester:;
}
```