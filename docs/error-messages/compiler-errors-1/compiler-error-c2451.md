---
title: 컴파일러 오류 C2451
ms.date: 11/04/2016
f1_keywords:
- C2451
helpviewer_keywords:
- C2451
ms.assetid: a64c93a5-ab8d-4d39-ae57-9ee7ef803036
ms.openlocfilehash: bd69861b42e14ae30b4d57658719e7a2ce3617ac
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208787"
---
# <a name="compiler-error-c2451"></a>컴파일러 오류 C2451

'type' 형식의 조건식 올바르지 않습니다.

조건 식은 정수 형식으로 평가합니다.

다음 샘플에서는 C2451 오류가 생성 됩니다.

```
// C2451.cpp
class B {};

int main () {
   B b1;
   int i = 0;
   if (b1)   // C2451
   // try the following line instead
   // if (i)
      ;
}
```