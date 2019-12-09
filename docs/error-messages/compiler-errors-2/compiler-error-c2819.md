---
title: 컴파일러 오류 C2819
ms.date: 11/04/2016
f1_keywords:
- C2819
helpviewer_keywords:
- C2819
ms.assetid: fcc7762d-cb82-4bb1-a715-0d82da832edf
ms.openlocfilehash: 9a3768cb23c65eb3e2d818f81ff7c6a561c8d7ec
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74750652"
---
# <a name="compiler-error-c2819"></a>컴파일러 오류 C2819

' type ' 형식에 오버 로드 된 멤버 ' operator-> '이 (가) 없습니다.

이 포인터 작업을 사용 하려면 `operator->()`를 정의 해야 합니다.

다음 샘플에서는 C2819를 생성 합니다.

```cpp
// C2819.cpp
// compile with: /c
class A {
   public:
      int i;
};

class B {};

void C(B j) {
   j->i;   // C2819
}

class D {
   A* pA;

   public:
      A* operator->() {
         return pA;
      }
};

void F(D j) {
   j->i;
}
```

C2819는 [ C++ 참조 형식에 스택 의미 체계를](../../dotnet/cpp-stack-semantics-for-reference-types.md)사용 하는 경우에도 발생할 수 있습니다. 다음 샘플에서는 C2819를 생성 합니다.

```cpp
// C2819_b.cpp
// compile with: /clr
ref struct R {
   void Test() {}
};

int main() {
   R r;
   r->Test();   // C2819
   r.Test();   // OK
}
```
