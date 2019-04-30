---
title: 컴파일러 오류 C3037
ms.date: 11/04/2016
f1_keywords:
- C3037
helpviewer_keywords:
- C3037
ms.assetid: 9ba8a890-d3c7-4cce-93c5-d358e2bfad28
ms.openlocfilehash: a022cfe6057f9ea518664090b5842faf4e822cb5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350207"
---
# <a name="compiler-error-c3037"></a>컴파일러 오류 C3037

'var': 'reduction' 절의 변수는 바깥쪽 컨텍스트에서 shared여야 합니다.

[reduction](../../parallel/openmp/reference/reduction.md) 절에 지정된 변수는 컨텍스트의 각 스레드에 private일 수 없습니다.

다음 샘플에서는 C3037을 생성합니다.

```
// C3037.cpp
// compile with: /openmp /c
int g_i;

int main() {
   int i;

   #pragma omp parallel private(g_i)
   // try the following line instead
   // #pragma omp parallel
   {
      #pragma omp for reduction(+:g_i)   // C3037
      for (i = 0 ; i < 10 ; ++i) {
         g_i += i;
      }
   }
}
```