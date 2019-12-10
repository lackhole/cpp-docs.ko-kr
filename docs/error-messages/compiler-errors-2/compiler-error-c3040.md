---
title: 컴파일러 오류 C3040
ms.date: 11/04/2016
f1_keywords:
- C3040
helpviewer_keywords:
- C3040
ms.assetid: 29e857ac-74f0-4ec6-becf-9026e38c160e
ms.openlocfilehash: 8a7ee7b814be1963e2d98b54e547cc5965eef9d3
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754955"
---
# <a name="compiler-error-c3040"></a>컴파일러 오류 C3040

'var': 'reduction' 절의 변수 형식이 환산 연산자 'operator'와 호환되지 않습니다.

[reduction](../../parallel/openmp/reference/reduction.md) 절의 변수를 reduction 연산자와 함께 사용할 수 없습니다.

다음 샘플에서는 C3040을 생성합니다.

```cpp
// C3040.cpp
// compile with: /openmp /c
#include "omp.h"
double d;

int main() {
   #pragma omp parallel reduction(&:d)   // C3040
      ;

   #pragma omp parallel reduction(-:d)  // OK
      ;
}
```
