---
title: 컴파일러 오류 C2310
ms.date: 11/04/2016
f1_keywords:
- C2310
helpviewer_keywords:
- C2310
ms.assetid: 1969c682-b97e-43fb-b9a9-f783e7ff1710
ms.openlocfilehash: 8bd885a730bfe4890e99fa9ec7beb83169aca4d9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62302126"
---
# <a name="compiler-error-c2310"></a>컴파일러 오류 C2310

catch 처리기 형식을 하나 지정 해야 합니다.

Catch 처리기 없는 형식 또는 여러 형식을 지정 합니다.

다음 샘플에서는 C2310를 생성합니다.

```
// C2310.cpp
// compile with: /EHsc
#include <eh.h>
int main() {
   try {
      throw "Out of memory!";
   }
   catch( int ,int) {}   // C2310 two types
   // try the following line instead
   // catch( int)  {}
}
```