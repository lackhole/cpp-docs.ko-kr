---
title: 컴파일러 오류 C3020
ms.date: 11/04/2016
f1_keywords:
- C3020
helpviewer_keywords:
- C3020
ms.assetid: f625c7a3-afaa-4bd8-9c1b-51891b832f36
ms.openlocfilehash: 0e2d8e70dcc9b23c56a321487cd4b933a1086387
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386683"
---
# <a name="compiler-error-c3020"></a>컴파일러 오류 C3020

'var': OpenMP 'for' 루프 인덱스 변수는 루프 본문에서 수정할 수 없습니다

OpenMP `for` 루프의 본문에 인덱스 (루프 카운터)를 수정할 수 없습니다는 `for` 루프입니다.

다음 샘플에서는 C3020를 생성합니다.

```
// C3020.cpp
// compile with: /openmp
int main() {
   int i = 0, n = 3;

   #pragma omp parallel
   {
      #pragma omp for
      for (i = 0; i < 10; i += n)
         i *= 2;   // C3020
         // try the following line instead
         // n++;
   }
}
```

사용 하 여 선언 된 변수에 [lastprivate](../../parallel/openmp/reference/lastprivate.md) 병렬된 루프 내에서 인덱스로 사용할 수 없습니다.

해당 lastprivate for 루프 내에서 가장 바깥쪽 idx_a 쓸 트리거할 때문에 다음 샘플에 대 한 두 번째 lastprivate C3020를 제공 합니다. 첫 번째 lastprivate 해당 lastprivate 트리거합니다 (기술적으로 매우 끝 마지막 반복)에 루프에 대 한 가장 바깥쪽 외부 idx_a 쓰기 때문에 오류를 제공 하지 않습니다. 다음 샘플 C3020를 생성합니다.

```
// C3020b.cpp
// compile with: /openmp /c
float a[100][100];
int idx_a, idx_b;
void test(int first, int last)
{
   #pragma omp parallel for lastprivate(idx_a)
   for (idx_a = first; idx_a <= last; ++idx_a) {
      #pragma omp parallel for lastprivate(idx_a)   // C3020
      for (idx_b = first; idx_b <= last; ++idx_b) {
         a[idx_a][idx_b] += 1.0f;
      }
   }
}
```

다음 샘플에는 가능한 해결 방법을 보여 줍니다.

```
// C3020c.cpp
// compile with: /openmp /c
float a[100][100];
int idx_a, idx_b;
void test(int first, int last)
{
   #pragma omp parallel for lastprivate(idx_a)
   for (idx_a = first; idx_a <= last; ++idx_a) {
      #pragma omp parallel for lastprivate(idx_b)
      for (idx_b = first; idx_b <= last; ++idx_b) {
         a[idx_a][idx_b] += 1.0f;
      }
   }
}
```