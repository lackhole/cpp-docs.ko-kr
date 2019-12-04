---
title: 컴파일러 오류 C2101
ms.date: 11/04/2016
f1_keywords:
- C2101
helpviewer_keywords:
- C2101
ms.assetid: 42f0136f-8cc1-4f2b-be1c-721ec9278e66
ms.openlocfilehash: 8bea258bd3e20cba1dbfabdd3a669a44414b89f8
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74752342"
---
# <a name="compiler-error-c2101"></a>컴파일러 오류 C2101

상수에 '&'가 있습니다.

연산자 주소( `&` )에 피연산자로 l 값이 있어야 합니다.

다음 샘플에서는 C2101을 생성합니다.

```cpp
// C2101.cpp
int main() {
   char test;
   test = &'a';   // C2101
   test = 'a';   // OK
}
```
