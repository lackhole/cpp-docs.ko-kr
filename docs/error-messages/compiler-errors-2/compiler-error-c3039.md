---
title: 컴파일러 오류 C3039
ms.date: 11/04/2016
f1_keywords:
- C3039
helpviewer_keywords:
- C3039
ms.assetid: 02776f16-f57a-4ffd-b7f7-9c696b633e08
ms.openlocfilehash: 69be1b25254119108e517cee2f1e14368e0163f3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350103"
---
# <a name="compiler-error-c3039"></a>컴파일러 오류 C3039

'var': OpenMP 'for' 문의 인덱스 변수는 환산(reduction) 변수가 될 수 없습니다.

인덱스 변수는 암시적으로 전용 변수이므로 [환산(reduction)](../../parallel/openmp/reference/reduction.md) 절의 바깥쪽 [병렬](../../parallel/openmp/reference/parallel.md) 지시문에 사용할 수 없습니다.

## <a name="example"></a>예제

다음 샘플에서는 C3039를 생성합니다.

```
// C3039.cpp
// compile with: /openmp /c
int g_i;

int main() {
   int i;

   #pragma omp parallel reduction(+: i)
   {
      #pragma omp for
      for (i = 0; i < 10; ++i)   // C3039
         g_i += i;
   }
}
```