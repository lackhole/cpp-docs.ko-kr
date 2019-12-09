---
title: 심각한 오류 C1310
ms.date: 11/04/2016
f1_keywords:
- C1310
helpviewer_keywords:
- C1310
ms.assetid: ac48aa51-8023-42fe-b844-3f8bf228fbef
ms.openlocfilehash: bd8baeb3cfe1624eaf292b3a54fc15a46ea68e11
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74746983"
---
# <a name="fatal-error-c1310"></a>심각한 오류 C1310

OpenMP에서는 프로필 기반 최적화를 사용할 수 없습니다.

[/GL](../../build/reference/ltcg-link-time-code-generation.md) 로 컴파일된 모든 모듈을 [/LTCG:PGI](../../build/reference/gl-whole-program-optimization.md)와 연결할 수 없습니다.

다음 샘플에서는 C1310을 생성합니다.

```cpp
// C1310.cpp
// compile with: /openmp /GL /link /LTCG:PGI
// C1310 expected
int main()
{
   int i = 0, j = 10;

   #pragma omp parallel
   {
      #pragma omp for
      for (i = 0; i < 0; i++)
         --j;
   }
}
```
