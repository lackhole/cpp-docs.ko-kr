---
title: 컴파일러 오류 C2309
ms.date: 11/04/2016
f1_keywords:
- C2309
helpviewer_keywords:
- C2309
ms.assetid: 6303d5b5-72cf-42b8-92ce-b1eb48e80d48
ms.openlocfilehash: 2567562b5d8a75a40afcb4a94ad453ee65709a00
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759037"
---
# <a name="compiler-error-c2309"></a>컴파일러 오류 C2309

catch 처리기에 괄호로 묶은 예외 선언이 필요 합니다.

Catch 처리기에 괄호로 묶은 형식이 없습니다.

다음 샘플에서는 C2309를 생성 합니다.

```cpp
// C2309.cpp
// compile with: /EHsc
#include <eh.h>
class C {};
int main() {
   try {
      throw "ooops!";
   }
   catch C {}   // C2309
   // try the following line instead
   // catch( C ) {}
}
```
