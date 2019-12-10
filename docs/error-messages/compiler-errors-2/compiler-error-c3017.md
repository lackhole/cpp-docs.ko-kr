---
title: 컴파일러 오류 C3017
ms.date: 11/04/2016
f1_keywords:
- C3017
helpviewer_keywords:
- C3017
ms.assetid: 12ab2c2a-d0d2-4900-9cbf-39be0af590dd
ms.openlocfilehash: af3f24a1a814fa79fa63b7e5bee204083006c9a2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74749742"
---
# <a name="compiler-error-c3017"></a>컴파일러 오류 C3017

OpenMP 'for' 문의 종료 테스트 형식이 잘못되었습니다.

OpenMP 문의 `for` 루프를 완벽하고 명시적으로 지정해야 합니다.

다음 샘플에서는 C3017을 생성합니다.

```cpp
// C3017.cpp
// compile with: /openmp
int main()
{
   int i = 0, j = 10;

   #pragma omp parallel
   {
      #pragma omp for
      for (i = 0; i; ++i)   // C3017
      // Try the following line instead:
      // for (i = 0; i < 10; ++i)
         ;
   }
}
```
