---
title: 컴파일러 오류 C2184
ms.date: 11/04/2016
f1_keywords:
- C2184
helpviewer_keywords:
- C2184
ms.assetid: 80fc8bff-7d76-4bde-94d2-01d84bb6824a
ms.openlocfilehash: 146035134cc159b9e4271ce10c94f196098581b8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385838"
---
# <a name="compiler-error-c2184"></a>컴파일러 오류 C2184

'type': __except 식의 형식이 잘못되었습니다. 정수여야 합니다.

형식이 [__except](../../c-language/try-except-statement-c.md) 문에서 사용되었지만 형식이 허용되지 않습니다.

다음 샘플에서는 C2184를 생성합니다.

```
// C2184.cpp
void f() {
   int * p;
   __try{}
   __except(p){};   // C2184
}
```

해결 방법:

```
// C2184b.cpp
// compile with: /c
void f() {
   int i = 0;
   __try{}
   __except(i){};
}
```