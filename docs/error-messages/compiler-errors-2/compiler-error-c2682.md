---
title: 컴파일러 오류 C2682
ms.date: 11/04/2016
f1_keywords:
- C2682
helpviewer_keywords:
- C2682
ms.assetid: 30c6a7c4-f5f7-4fe8-81a8-c48938521ab4
ms.openlocfilehash: c1ce0132ed0db418359effe60f59e1eb2d3cc221
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760285"
---
# <a name="compiler-error-c2682"></a>컴파일러 오류 C2682

casting_operator를 사용 하 여 ' type1 '에서 ' type2 ' (으)로 변환할 수 없습니다.

캐스팅 연산자가 호환 되지 않는 형식 간에 변환 하려고 했습니다. 예를 들어 [dynamic_cast](../../cpp/dynamic-cast-operator.md) 연산자를 사용 하 여 포인터를 참조로 변환할 수 없습니다. `dynamic_cast` 연산자를 사용 하 여 한정자를 캐스트할 수 없습니다. 형식에 대 한 모든 한정자가 일치 해야 합니다.

`const_cast` 연산자를 사용 하 여 `const`, `volatile`또는 `__unaligned`와 같은 특성을 제거할 수 있습니다.

다음 샘플에서는 C2682를 생성 합니다.

```cpp
// C2682.cpp
class A { virtual void f(); };
class B: public A {};

void g(A* pa) {
    B& rb = dynamic_cast<B&>(pa); // C2682
}
```

다음 샘플에서는 C2682를 생성 합니다.

```cpp
// C2682b.cpp
// compile with: /clr
ref struct R{};
ref struct RR : public R{};
ref struct H {
   RR^ r ;
   short s;
   int i;
};

int main() {
   H^ h = gcnew H();
   interior_ptr<int>lr = &(h->i);
   interior_ptr<short>ssr = safe_cast<interior_ptr<short> >(lr);   // C2682
   interior_ptr<short>ssr = reinterpret_cast<interior_ptr<short> >(lr);   // OK
}
```
