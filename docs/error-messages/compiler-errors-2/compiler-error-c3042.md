---
title: 컴파일러 오류 C3042
ms.date: 11/04/2016
f1_keywords:
- C3042
helpviewer_keywords:
- C3042
ms.assetid: bf73f61e-5bd2-40a8-9b06-6244e6a15a41
ms.openlocfilehash: 4347e5ee0e61ada700082b4954b616ce894e57b9
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761392"
---
# <a name="compiler-error-c3042"></a>컴파일러 오류 C3042

OpenMP 'directive' 절에 'copyprivate'와 'nowait' 절을 함께 사용할 수 없습니다.

[copyprivate](../../parallel/openmp/reference/copyprivate.md) 및 [nowait](../../parallel/openmp/reference/nowait.md) 절은 지정된 지시문에서 함께 사용할 수 없습니다. 이 오류를 해결하려면 `copyprivate` 또는 `nowait` 절 중 하나 또는 둘 다를 제거합니다.

다음 샘플에서는 C3042를 생성합니다.

```cpp
// C3042.cpp
// compile with: /openmp /c
#include <stdio.h>
#include "omp.h"

double d;

int main() {
    #pragma omp parallel private(d)
   {
      #pragma omp single copyprivate(d) nowait   // C3042
      {
      }
   }
}
```
