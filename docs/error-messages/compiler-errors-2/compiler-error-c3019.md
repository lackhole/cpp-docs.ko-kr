---
title: 컴파일러 오류 C3019
ms.date: 11/04/2016
f1_keywords:
- C3019
helpviewer_keywords:
- C3019
ms.assetid: 31a6d9b6-d29f-4499-9ad8-48dd751e87c7
ms.openlocfilehash: 15b2dbf55b18c50020140eae25a71b18ceb10b10
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74742134"
---
# <a name="compiler-error-c3019"></a>컴파일러 오류 C3019

OpenMP ' for ' 문의 증가값 형식이 잘못 되었습니다.

OpenMP `for` 루프의 증분 부분은 연산자의 왼쪽과 오른쪽 모두에 인덱스 변수를 사용 해야 합니다.

다음 샘플에서는 C3019를 생성 합니다.

```cpp
// C3019.cpp
// compile with: /openmp
int main()
{
   int i = 0, j = 1, n = 3;

   #pragma omp parallel
   {
      #pragma omp for
      for (i = 0; i < 10; i = j + n)   // C3019
      // Try the following line instead:
      // for (i = 0; i < 10; i++)
         j *= 2;
   }
}
```
