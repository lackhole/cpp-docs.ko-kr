---
title: 컴파일러 경고(수준 1) C4077
ms.date: 11/04/2016
f1_keywords:
- C4077
helpviewer_keywords:
- C4077
ms.assetid: c2d28805-b33f-41ad-afba-33b3f788c649
ms.openlocfilehash: 5171ee79c3afd32e847483568fbbf90222747509
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208352"
---
# <a name="compiler-warning-level-1-c4077"></a>컴파일러 경고(수준 1) C4077

알 수 없는 check_stack 옵션입니다.

이전 **check_stack** pragma 형식이 알 수 없는 인수와 함께 사용되었습니다. 인수는 `+`, `-`, `(on)`, `(off)`이거나 비어 있어야 합니다.

컴파일러가 해당 pragma를 무시하고 스택 검사를 변경되지 않은 상태로 그대로 둡니다.

## <a name="example"></a>예제

```
// C4077.cpp
// compile with: /W1 /LD
#pragma check_stack yes // C4077
#pragma check_stack +    // Correct old form
#pragma check_stack (on) // Correct new form
```