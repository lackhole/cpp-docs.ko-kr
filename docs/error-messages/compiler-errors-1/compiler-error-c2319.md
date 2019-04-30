---
title: 컴파일러 오류 C2319
ms.date: 11/04/2016
f1_keywords:
- C2319
helpviewer_keywords:
- C2319
ms.assetid: 25263e6e-f5ba-4d2c-8727-8c2d8ca2e5ce
ms.openlocfilehash: f0ec35cfb74fd08180969344180ff42d485d58c0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404301"
---
# <a name="compiler-error-c2319"></a>컴파일러 오류 C2319

'try/catch'는 복합 문이 뒤에 와야 합니다. '{'가 없습니다.

`try` 또는 `catch` 블록이 `try` 또는 `catch` 문 다음에 오지 않습니다. 블록은 중괄호로 묶어야 합니다.

다음 샘플에서는 C2319를 생성합니다.

```
// C2319.cpp
// compile with: /EHsc
#include <eh.h>
class C {};
int main() {
   try {
      throw "ooops!";
   }
   catch( C ) ;    // C2319
   // try the following line instead
   // catch( C ) {}
}
```