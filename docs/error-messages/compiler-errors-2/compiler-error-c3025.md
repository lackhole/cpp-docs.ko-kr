---
title: 컴파일러 오류 C3025
ms.date: 11/04/2016
f1_keywords:
- C3025
helpviewer_keywords:
- C3025
ms.assetid: 4442f5a3-d9ea-4873-b1fb-e7e5bd3cbe5e
ms.openlocfilehash: bb3337cb563125ce0329146f64c4da3f33e28ce7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360075"
---
# <a name="compiler-error-c3025"></a>컴파일러 오류 C3025

'clause': 정수 계열 식이 있어야 합니다.

절에 정수 식이 필요하지만 정수가 아닌 식이 제공되었습니다.

## <a name="example"></a>예제

다음 샘플에서는 C3025를 생성합니다.

```
// C3025.cpp
// compile with: /openmp /link vcomps.lib
#include <stdio.h>
#include "omp.h"

float f = 2.0F;

int main()
{
    int i = 0;

    // OK
    puts("Test with int");
    #pragma omp parallel for num_threads(i)
    for (i = 1; i <= 2; ++i)
        printf_s("Hello World - thread %d - iteration %d\n",
                 omp_get_thread_num(), i);

    puts("Test with float");
    #pragma omp parallel for num_threads(f)   // C3025
    for (i = 1; i <= 2; ++i)
        printf_s("Hello World - thread %d - iteration %d\n",
                 omp_get_thread_num(), i);
}
```