---
title: 컴파일러 오류 C2494
ms.date: 11/04/2016
f1_keywords:
- C2494
helpviewer_keywords:
- C2494
ms.assetid: 5dfd07ab-351d-49c9-b54e-f0a104776ab8
ms.openlocfilehash: e46eff4ec2b1afdb309b3c4db89c9283e2fc8971
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757035"
---
# <a name="compiler-error-c2494"></a>컴파일러 오류 C2494

필터 식 또는 __finally/finally 블록 내에서 ' keyword '를 호출할 수 없습니다.

`__finally` 또는 finally 블록에 `keyword`를 사용할 수 없습니다.

다음 샘플에서는 C2494를 생성 합니다.

```cpp
// C2494.cpp
#include <malloc.h>

int main() {
   __try {}
   __except ( _alloca(100), 1 ) {}   // C2494
   __try {}
   __finally {
      _alloca(100);   // C2494
   }
}
```

C2494는 **/clr**을 사용 하는 경우에도 발생할 수 있습니다.

```cpp
// C2494b.cpp
// compile with: /clr
#include <malloc.h>

int main() {
   char * buf;
   try {}
   catch (char * buf2) {}
   finally {
      _alloca(100);   // C2494
   }
}
```
