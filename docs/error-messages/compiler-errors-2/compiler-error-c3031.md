---
title: 컴파일러 오류 C3031
ms.date: 11/04/2016
f1_keywords:
- C3031
helpviewer_keywords:
- C3031
ms.assetid: 7e621e7e-eda7-45b5-8836-29599cd05255
ms.openlocfilehash: a892ff2bdbefbf6034da58c45c499fd6f65ad965
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74748322"
---
# <a name="compiler-error-c3031"></a>컴파일러 오류 C3031

'var': 'reduction' 절의 변수는 스칼라 산술 형식이어야 합니다.

잘못된 형식의 변수가 reduction 절에 전달되었습니다.

다음 샘플에서는 C3031을 생성합니다.

```cpp
// C3031.cpp
// compile with: /openmp /link vcomps.lib
#include <stdio.h>
#include "omp.h"

typedef struct {
   int n;
} Incomplete;

extern Incomplete inc;
int i = 9;

int main() {
   #pragma omp parallel reduction(+: inc)   // C3031
      ;

   #pragma omp parallel reduction(+: i)     // OK
      ;
}
```
