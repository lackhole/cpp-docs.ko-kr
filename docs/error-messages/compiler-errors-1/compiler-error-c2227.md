---
title: 컴파일러 오류 C2227
ms.date: 11/04/2016
f1_keywords:
- C2227
helpviewer_keywords:
- C2227
ms.assetid: d470e8b8-7e15-468b-84fa-37d1a0132271
ms.openlocfilehash: 8f9fc435682eb400574eea61a6f90392fa679233
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404327"
---
# <a name="compiler-error-c2227"></a>컴파일러 오류 C2227

'->member' 왼쪽은 클래스/구조체/공용 구조체/제네릭 형식을 가리켜야 합니다.

`->` 왼쪽의 피연산자가 클래스, 구조체 또는 공용 구조체에 대한 포인터가 아닙니다.

다음 샘플에서는 C2227을 생성합니다.

```
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