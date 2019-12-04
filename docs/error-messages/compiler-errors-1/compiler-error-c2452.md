---
title: 컴파일러 오류 C2452
ms.date: 11/04/2016
f1_keywords:
- C2452
helpviewer_keywords:
- C2452
ms.assetid: a4ec7642-6660-4c7a-9866-853d1cc67daf
ms.openlocfilehash: 7e8173c2697a931e5b292dc974b6d1b22f376794
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744110"
---
# <a name="compiler-error-c2452"></a>컴파일러 오류 C2452

' type ': safe_cast의 소스 형식이 잘못 되었습니다.

[Safe_cast](../../extensions/safe-cast-cpp-component-extensions.md) 의 원본 형식이 잘못 되었습니다.  예를 들어 `safe_cast` 작업의 모든 형식은 CLR 형식 이어야 합니다.

다음 샘플에서는 C2452를 생성 합니다.

```cpp
// C2452.cpp
// compile with: /clr

struct A {};
struct B : public A {};

ref struct C {};
ref struct D : public C{};

int main() {
   A a;
   safe_cast<B*>(&a);   // C2452

   // OK
   C ^ c = gcnew C;
   safe_cast<D^>(c);
}
```
