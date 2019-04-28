---
title: 컴파일러 오류 C3048
ms.date: 11/04/2016
f1_keywords:
- C3048
helpviewer_keywords:
- C3048
ms.assetid: 48e07091-94d9-471d-befe-7e2507631edd
ms.openlocfilehash: 451ae87f26357f47df4efdaa4393450f660a9000
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187637"
---
# <a name="compiler-error-c3048"></a>컴파일러 오류 C3048

'#pragma omp atomic' 다음에 나오는 식의 형식이 잘못되었습니다.

원자성 지시문이 잘못 지정되었습니다.

다음 샘플에서는 C3048을 생성합니다.

```
// C3048.cpp
// compile with: /openmp vcomps.lib
#include "omp.h"
#include <stdio.h>

int main() {
   int a[10];
   omp_set_num_threads(4);
   #pragma omp parallel
   {
      #pragma omp atomic
      a[0] = 1;   // C3048
      // try the following line instead
      // a[0] += 1;
   }
}
```