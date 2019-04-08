---
title: 컴파일러 오류 C3054
ms.date: 11/04/2016
f1_keywords:
- C3054
helpviewer_keywords:
- C3054
ms.assetid: 6f4b7ac5-0d12-474b-b611-76ff26ee41ac
ms.openlocfilehash: 1dd6450d661700d9b2f7f94e625abd9ecc64ed08
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58772997"
---
# <a name="compiler-error-c3054"></a>컴파일러 오류 C3054

현재 제네릭 클래스 또는 함수에서는 '#pragma omp parallel'가 지원되지 않습니다.

자세한 내용은 [제네릭을](../../extensions/generics-cpp-component-extensions.md) 하 고 [OpenMP](../../parallel/openmp/openmp-in-visual-cpp.md)합니다.

## <a name="example"></a>예제

다음 샘플에서는 C3054를 생성합니다.

```
// C3054.cpp
// compile with: /openmp /clr /c
#include <omp.h>

ref struct MyBaseClass {
   // Delete the following 7 lines to resolve.
   generic <class ItemType>
   void Test(ItemType i) {   // C3054
      #pragma omp parallel num_threads(4)
      {
         int i = omp_get_thread_num();
      }
   }

   // OK
   void Test2() {
      #pragma omp parallel num_threads(4)
      {
         int i = omp_get_thread_num();
      }
   }
};
```