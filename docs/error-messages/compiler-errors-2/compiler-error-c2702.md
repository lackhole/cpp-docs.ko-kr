---
title: 컴파일러 오류 C2702
ms.date: 11/04/2016
f1_keywords:
- C2702
helpviewer_keywords:
- C2702
ms.assetid: 6def15d4-9a8d-43e7-ae35-42d7cb57c27e
ms.openlocfilehash: 03a982ee35f0ac49a12568fc428de333f57f3ffa
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758322"
---
# <a name="compiler-error-c2702"></a>컴파일러 오류 C2702

종료 블록에 __except 표시 되지 않을 수 있습니다.

예외 처리기 (`__try`/`__except`)는 `__finally` 블록 내에 중첩 될 수 없습니다.

다음 샘플에서는 C2702를 생성 합니다.

```cpp
// C2702.cpp
// processor: x86 IPF
int Counter;
int main() {
   __try {}
   __finally {
      __try {}   // C2702
      __except( Counter ) {}   // C2702
   }
}
```
