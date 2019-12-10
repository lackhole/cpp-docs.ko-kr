---
title: 컴파일러 오류 C2135
ms.date: 11/04/2016
f1_keywords:
- C2135
helpviewer_keywords:
- C2135
ms.assetid: aa360d22-4f79-4de1-b384-93cadd10975f
ms.openlocfilehash: 4bc9d8bc3db5fbd826ded37d93ac812116356eb2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757490"
---
# <a name="compiler-error-c2135"></a>컴파일러 오류 C2135

'비트 연산자': 비트 필드 연산이 잘못되었습니다.

address-of 연산자(`&`)는 비트 필드에 적용할 수 없습니다.

다음 샘플에서는 C2135를 생성합니다.

```cpp
// C2135.cpp
struct S {
   int i : 1;
};

struct T {
   int j;
};
int main() {
   &S::i;   // C2135 address of a bit field
   &T::j;   // OK
}
```
