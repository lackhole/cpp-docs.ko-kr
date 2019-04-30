---
title: 컴파일러 경고(수준 1) C4731
ms.date: 11/04/2016
f1_keywords:
- C4731
helpviewer_keywords:
- C4731
ms.assetid: 5658c24c-3e6f-4505-835b-1fb92d47cab0
ms.openlocfilehash: af091d1d35fff955afcc5af3da48b80416e79f36
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385435"
---
# <a name="compiler-warning-level-1-c4731"></a>컴파일러 경고(수준 1) C4731

'pointer': 프레임 포인터 레지스터가 인라인 어셈블리 코드에 의해 수정 '등록'

프레임 포인터 레지스터를 수정 했습니다. 저장 하 고를 인라인 어셈블리 블록 또는 프레임 변수 (로컬 또는 매개 변수를 수정 하는 레지스터에 따라) 레지스터를 복원 해야 하거나 코드가 제대로 작동 하지 않을 수 있습니다.

다음 샘플에서는 C4731 오류가 생성 됩니다.

```
// C4731.cpp
// compile with: /W1 /LD
// processor: x86
// C4731 expected
void bad(int p) {
   __asm
   {
      mov ebp, 1
   }

   if (p == 1)
   {
      // ...
   }
}
```

EBP 프레임 포인터 (fpo 거부 됨) 이며 수정 중입니다. 때 `p` 중이면 적절 하 게 참조는 참조 `EBP`합니다. 하지만 `EBP` 코드 되므로 프로그램이 제대로 작동 하지 것입니다 오류도 덮어 쓰여졌습니다.