---
title: 컴파일러 오류 C3040
ms.date: 11/04/2016
f1_keywords:
- C3040
helpviewer_keywords:
- C3040
ms.assetid: 29e857ac-74f0-4ec6-becf-9026e38c160e
ms.openlocfilehash: b0bc4956cfc08ae50026827d78136a70b82d568e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62349999"
---
# <a name="compiler-error-c3040"></a>컴파일러 오류 C3040

'var': 'reduction' 절의 변수 형식이 환산 연산자 'operator'와 호환되지 않습니다.

[reduction](../../parallel/openmp/reference/reduction.md) 절의 변수를 reduction 연산자와 함께 사용할 수 없습니다.

다음 샘플에서는 C3040을 생성합니다.

```
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