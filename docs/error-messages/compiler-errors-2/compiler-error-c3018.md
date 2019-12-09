---
title: 컴파일러 오류 C3018
ms.date: 11/04/2016
f1_keywords:
- C3018
helpviewer_keywords:
- C3018
ms.assetid: 685be45f-f116-43a8-a88d-05ab6616e2f1
ms.openlocfilehash: 7d61bcb7364e90f5b5137f549989da769223a04f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74742199"
---
# <a name="compiler-error-c3018"></a>컴파일러 오류 C3018

'var1': OpenMP 'for' 문의 테스트 식 또는 증가 식에는 인덱스 변수 'var2'를 사용해야 합니다.

OpenMP 문의 `for` 루프는 인덱스에 사용하는 것과 동일한 변수를 해당 테스트 식과 증가 식에 사용해야 합니다.

다음 샘플에서는 C3018을 생성합니다.

```cpp
// C3018.cpp
// compile with: /openmp
int main()
{
   int i = 0, j = 5;

   #pragma omp parallel
   {
      #pragma omp for
      for (i = 0; j < 10; ++i)   // C3018
      // try the following line instead
      // for (i = 0; i < 10; ++i)
         j *= 2;

      #pragma omp for
      for (i = 0; i < 10; j = j + i)   // C3018
      // try the following line instead
      // for (i = 0; i < 10; i = j + i)
         j *= 2;
   }
}
```
