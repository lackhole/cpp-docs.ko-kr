---
title: 컴파일러 오류 C3052
ms.date: 11/04/2016
f1_keywords:
- C3052
helpviewer_keywords:
- C3052
ms.assetid: 87480c42-1ceb-4775-8d20-88c54a7bb6a6
ms.openlocfilehash: ed9c27e1602f9372cb9137615ef66932a8df960c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62265778"
---
# <a name="compiler-error-c3052"></a>컴파일러 오류 C3052

'var': default(none) 절 밑의 데이터 공유 절에 변수가 없습니다.

[default(none)](../../parallel/openmp/reference/default-openmp.md) 가 사용되는 경우 구조화된 블록에 사용되는 모든 변수가 [shared](../../parallel/openmp/reference/shared-openmp.md) 또는 [private](../../parallel/openmp/reference/private-openmp.md)으로 명시적으로 지정되어야 합니다.

다음 샘플에서는 C3052를 생성합니다.

```
// C3052.cpp
// compile with: /openmp /c
int main() {
   int n1 = 1;

   #pragma omp parallel default(none) // shared(n1) private(n1)
   {
      n1 = 0;   // C3052 use either a shared or private clause
   }
}
```