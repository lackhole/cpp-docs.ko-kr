---
title: 컴파일러 오류 C3054
ms.date: 11/04/2016
f1_keywords:
- C3054
helpviewer_keywords:
- C3054
ms.assetid: 6f4b7ac5-0d12-474b-b611-76ff26ee41ac
ms.openlocfilehash: 7a35f72be07799f61587c77b511395223ae72939
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761191"
---
# <a name="compiler-error-c3054"></a>컴파일러 오류 C3054

현재 제네릭 클래스 또는 함수에서는 '#pragma omp parallel'가 지원되지 않습니다.

자세한 내용은 [제네릭](../../extensions/generics-cpp-component-extensions.md) 및 [OpenMP](../../parallel/openmp/openmp-in-visual-cpp.md)를 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C3054를 생성합니다.

```cpp
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
