---
title: 컴파일러 오류 C2602
ms.date: 11/04/2016
f1_keywords:
- C2602
helpviewer_keywords:
- C2602
ms.assetid: 6c07a40e-537e-4954-b5c5-1e0e58fe1952
ms.openlocfilehash: 4cac8bd8aca0a811e1e009a2fdf07cbc200634f2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74737896"
---
# <a name="compiler-error-c2602"></a>컴파일러 오류 C2602

' class:: Identifier '는 ' class '의 기본 클래스의 멤버가 아닙니다.

`Identifier` 기본 클래스에서 상속 된 멤버가 아니기 때문에 액세스할 수 없습니다.

다음 샘플에서는 C2602를 생성 합니다.

```cpp
// C2602.cpp
// compile with: /c
struct X {
   int x;
};
struct A {
   int a;
};
struct B : public A {
   X::x;   // C2602 B is not derived from X
   A::a;   // OK
};
```
