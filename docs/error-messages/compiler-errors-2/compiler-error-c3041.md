---
title: 컴파일러 오류 C3041
ms.date: 11/04/2016
f1_keywords:
- C3041
helpviewer_keywords:
- C3041
ms.assetid: 9df1ae44-3ac7-4c6c-899f-f35ffe7ccf0d
ms.openlocfilehash: 43f75e9d054f574eb121d20eb35d302cef849566
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182576"
---
# <a name="compiler-error-c3041"></a>컴파일러 오류 C3041

'var': 'copyprivate' 절의 변수는 바깥쪽 컨텍스트에서 private이어야 합니다.

[copyprivate](../../parallel/openmp/reference/copyprivate.md) 에 전달된 변수를 바깥쪽 컨텍스트에서 공유할 수 없습니다.

다음 샘플에서는 C3041을 생성합니다.

```
// C3041.cpp
// compile with: /openmp /c
#include "omp.h"
double d;
int main() {
   #pragma omp parallel shared(d)
   // try the following line instead
   // #pragma omp parallel private(d)
   {
      // or don't make d copyprivate
      #pragma omp single copyprivate(d)   // C3041
      {
      }
   }
}
```