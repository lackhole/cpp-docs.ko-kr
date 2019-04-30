---
title: 컴파일러 오류 C3019
ms.date: 11/04/2016
f1_keywords:
- C3019
helpviewer_keywords:
- C3019
ms.assetid: 31a6d9b6-d29f-4499-9ad8-48dd751e87c7
ms.openlocfilehash: bba90917614cbc8facb182659c288f9823d8ab45
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386709"
---
# <a name="compiler-error-c3019"></a>컴파일러 오류 C3019

OpenMP 'for' 문의 증가 식 형식이 잘못 되었습니다.

OpenMP 증가 부분 `for` 루프 인덱스 변수 연산자의 왼쪽과 오른쪽에서 모두를 사용 해야 합니다.

다음 샘플에서는 C3019를 생성합니다.

```
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