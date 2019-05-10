---
title: 컴파일러 경고(수준 1) C4405
ms.date: 11/04/2016
f1_keywords:
- C4405
helpviewer_keywords:
- C4405
ms.assetid: 155c64d6-58ae-4455-b61f-ccd711c5da96
ms.openlocfilehash: e85bdc995fe16f91e2e9c734dacc65ca0b7b622d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182382"
---
# <a name="compiler-warning-level-1-c4405"></a>컴파일러 경고(수준 1) C4405

'identifier': 식별자가 예약어입니다.

인라인 어셈블리에 대 한 예약 된 단어를 변수 이름으로 사용 됩니다. 이 예상치 못한 결과가 발생할 수 있습니다. 이 경고를 해결 하려면 인라인 어셈블리에 대 한 예약 된 단어를 사용 하 여 변수 명명을 방지 합니다. 다음 샘플에서는 C4405 오류가 생성 됩니다.

```
// C4405.cpp
// compile with: /W1
// processor: x86
void func1() {
   int mov = 0, i = 0;
   _asm {
      mov mov, 0;   // C4405
      // instead, try ..
      // mov i, 0;
   }
}

int main() {
}
```