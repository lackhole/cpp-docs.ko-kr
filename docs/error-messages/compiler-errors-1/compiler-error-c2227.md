---
title: 컴파일러 오류 C2227
ms.date: 11/04/2016
f1_keywords:
- C2227
helpviewer_keywords:
- C2227
ms.assetid: d470e8b8-7e15-468b-84fa-37d1a0132271
ms.openlocfilehash: affc500208644cebbef1da93a0eafabd4aeaa094
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759297"
---
# <a name="compiler-error-c2227"></a>컴파일러 오류 C2227

'->member' 왼쪽은 클래스/구조체/공용 구조체/제네릭 형식을 가리켜야 합니다.

`->` 왼쪽의 피연산자가 클래스, 구조체 또는 공용 구조체에 대한 포인터가 아닙니다.

다음 샘플에서는 C2227을 생성합니다.

```cpp
// C2227.cpp
int *pInt;
struct S {
public:
    int member;
} s, *pS = &s;

int main() {
   pInt->member = 0;   // C2227 pInt points to an int
   pS->member = 0;   // OK
}
```
