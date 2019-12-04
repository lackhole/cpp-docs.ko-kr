---
title: 컴파일러 오류 C3032
ms.date: 11/04/2016
f1_keywords:
- C3032
helpviewer_keywords:
- C3032
ms.assetid: 6a92bd8e-319f-4a99-aef4-a9021f6f9928
ms.openlocfilehash: c9ea9d1baa0bab1141b1a0f3882df78f32208d0b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74748309"
---
# <a name="compiler-error-c3032"></a>컴파일러 오류 C3032

'var': 'clause' 절의 변수는 불완전한 형식 'type'이 될 수 없습니다.

특정 절에 전달되는 형식은 컴파일러에 완벽하게 표시되어야 합니다.

다음 샘플에서는 C3032를 생성합니다.

```cpp
// C3032.cpp
// compile with: /openmp /link vcomps.lib
#include "omp.h"

struct Incomplete;
extern struct Incomplete inc;

int main() {
   int i = 9;
   #pragma omp parallel private(inc)   // C3032
      ;

   #pragma omp parallel private(i)     // OK
      ;

}
```
