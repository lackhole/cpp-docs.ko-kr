---
title: 컴파일러 오류 C3057
ms.date: 11/04/2016
f1_keywords:
- C3057
helpviewer_keywords:
- C3057
ms.assetid: b0b2ba88-9c74-4bec-bf60-8fc72eade34c
ms.openlocfilehash: b2b827ec8d6b6ac21d80ded43e70f72098b3f367
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62265518"
---
# <a name="compiler-error-c3057"></a>컴파일러 오류 C3057

'symbol': 'threadprivate' 기호의 동적 초기화는 현재 지원되지 않습니다.

[threadprivate](../../parallel/openmp/reference/threadprivate.md) 절에서 사용된 기호의 초기화된 값을 컴파일 시간에 알 수 있어야 합니다.

다음 샘플에서는 C3057을 생성합니다.

```
// C3057.cpp
// compile with: /openmp /c
extern int f();
int x, y = f();
int a, b;
#pragma omp threadprivate(x, y)   // C3057

#pragma omp threadprivate(a, b)

int main() {
   // Delete the following 4 lines to resolve.
   #pragma omp parallel copyin(x, y)
   {
      x = y;
   }

   #pragma omp parallel copyin(a, b)
   {
      a = b;
   }
}
```

다음 샘플에서는 C3057을 생성합니다.

```
// C3057b.cpp
// compile with: /openmp /c
extern int Initialize();
int main() {
   #pragma omp parallel
   {
      static int var = Initialize();
      #pragma omp threadprivate(var)   // C3057
   }

   // OK
   #pragma omp parallel
   {
      static int var2;
      static bool initialized2;
      #pragma omp threadprivate(var2, initialized2)
      if (!initialized2) {
         var2 = Initialize();
         initialized2 = true;
      }
   }
}
```