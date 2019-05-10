---
title: 컴파일러 오류 C3035
ms.date: 11/04/2016
f1_keywords:
- C3035
helpviewer_keywords:
- C3035
ms.assetid: af34fad2-2b45-42d0-a9ff-04eab3e91c37
ms.openlocfilehash: e6d42c53407e1047d299e82566c7fadeb639641d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393573"
---
# <a name="compiler-error-c3035"></a>컴파일러 오류 C3035

OpenMP 'ordered' 지시문은 'ordered' 절이 있는 'for' 또는 'parallel for' 지시문에 직접 바인딩되어야 합니다.

순서가 지정된 절의 형식이 잘못되었습니다.

다음 샘플에서는 C3035를 생성합니다.

```
// C3035.cpp
// compile with: /openmp /link vcomps.lib
int main() {
   int n = 0, x, i;

   #pragma omp parallel private(n)
   {
      #pragma omp ordered   // C3035
      // Try the following line instead:
      // #pragma omp for ordered
       for (i = 0 ; i < 10 ; ++i)
         ;
   }
}
```