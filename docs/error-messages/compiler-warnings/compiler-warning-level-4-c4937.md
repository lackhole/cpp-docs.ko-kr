---
title: 컴파일러 경고(수준 4) C4937
ms.date: 11/04/2016
f1_keywords:
- C4937
helpviewer_keywords:
- C4937
ms.assetid: 2bb9f0e7-bbd6-4697-84de-95955e32ae29
ms.openlocfilehash: 64565ad37c965aa0af3b912988586b37270be6a4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62280271"
---
# <a name="compiler-warning-level-4-c4937"></a>컴파일러 경고(수준 4) C4937

'text1' 및 'text2'를 'directive'에 대한 인수로 구분할 수 없습니다.

컴파일러가 지시문에 대한 인수를 처리하는 방식으로 인해 여러 텍스트 표현(단일 및 이중 밑줄 형식)을 가진 키워드와 같은 컴파일러에 의미가 있는 이름을 구분할 수 없습니다.

이러한 문자열의 예로 __cdecl 및 \__forceinline 합니다.  /Za가 지정된 경우에는 이중 밑줄 형식만 사용할 수 있습니다.

다음 샘플에서는 C4937을 생성합니다.

```
// C4937.cpp
// compile with: /openmp /W4
#include "omp.h"
int main() {
   #pragma omp critical ( __leave )   // C4937
   ;

   // OK
   #pragma omp critical ( leave )
   ;
}
```