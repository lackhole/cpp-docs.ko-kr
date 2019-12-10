---
title: 컴파일러 오류 C3013
ms.date: 11/04/2016
f1_keywords:
- C3013
helpviewer_keywords:
- C3013
ms.assetid: f896777d-27e6-4b6d-baab-1567317f3374
ms.openlocfilehash: c88d78df84af39933e719e02f8ab5839540130fd
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759427"
---
# <a name="compiler-error-c3013"></a>컴파일러 오류 C3013

'clause': OpenMP 'directive' 지시문에는 절이 한 번만 나와야 합니다.

동일한 지시문에 절이 두 번 표시되었습니다. 발생한 절 하나를 삭제합니다.

다음 샘플에서는 C3013을 생성합니다.

```cpp
// C3013.cpp
// compile with: /openmp
int main() {
   int a, b, c, x, y, z;

   #pragma omp parallel shared(a,b,c) private(x)

   #pragma omp for nowait private(x) nowait   // C3013
   // The previous line generates C3013, with two nowait clauses
   // try the following line instead:
   // #pragma omp for nowait private(x)
   for (a = 0 ; a < 10 ; ++a) {
   }
}
```
