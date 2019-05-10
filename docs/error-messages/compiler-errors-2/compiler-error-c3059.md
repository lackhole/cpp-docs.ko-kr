---
title: 컴파일러 오류 C3059
ms.date: 11/04/2016
f1_keywords:
- C3059
helpviewer_keywords:
- C3059
ms.assetid: 57220324-8286-4cab-a1ab-45385eb1eae0
ms.openlocfilehash: df1f65f231f72f2efa90458fe9b21339dda80080
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404249"
---
# <a name="compiler-error-c3059"></a>컴파일러 오류 C3059

'var': 'threadprivate' 기호는 'clause' 절에서 사용할 수 없습니다.

[threadprivate](../../parallel/openmp/reference/threadprivate.md) 기호가 절에서 사용되었습니다.

다음 샘플에서는 C3059를 생성합니다.

```
// C3059.cpp
// compile with: /openmp
#include "omp.h"
int x, y;
#pragma omp threadprivate(x, y)

int main() {
   #pragma omp parallel private(x, y)   // C3059
   {
      x = y;
   }
}
```

해결 방법:

```
// C3059b.cpp
// compile with: /openmp
#include "omp.h"
int x = 0, y = 0;

int main() {
   #pragma omp parallel firstprivate(y) private(x)
   {
      x = y;
   }
}
```