---
title: 컴파일러 오류 C2602
ms.date: 11/04/2016
f1_keywords:
- C2602
helpviewer_keywords:
- C2602
ms.assetid: 6c07a40e-537e-4954-b5c5-1e0e58fe1952
ms.openlocfilehash: da38600ea099c9b0d73e929a100a8c338bd3388f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62215531"
---
# <a name="compiler-error-c2602"></a>컴파일러 오류 C2602

'class::Identifier' 기본 'class' 클래스의 구성원이 아닙니다.

`Identifier` 모든 기본 클래스에서 상속 된 멤버가 없기 때문에 액세스할 수 없습니다.

다음 샘플에서는 C2602 오류가 생성 됩니다.

```
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