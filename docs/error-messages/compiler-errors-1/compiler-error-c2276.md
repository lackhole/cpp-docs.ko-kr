---
title: 컴파일러 오류 C2276
ms.date: 11/04/2016
f1_keywords:
- C2276
helpviewer_keywords:
- C2276
ms.assetid: 62005ad9-6cb9-4b1f-965d-b875adaf695e
ms.openlocfilehash: 69bbabbf38f7ee02d08f4b5e9dc4bed167919291
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760064"
---
# <a name="compiler-error-c2276"></a>컴파일러 오류 C2276

' operator ': 바인딩된 멤버 함수 식에 대 한 연산이 잘못 되었습니다.

컴파일러가 멤버 포인터를 만들기 위한 구문과 관련 된 문제를 발견 했습니다.

다음 샘플에서는 C2276를 생성 합니다.

```cpp
// C2276.cpp
class A {
public:
   int func(){return 0;}
} a;

int (*pf)() = &a.func;   // C2276
// try the following line instead
// int (A::*pf3)() = &A::func;

class B {
public:
   void mf() {
      &this -> mf;   // C2276
      // try the following line instead
      // &B::mf;
   }
};

int main() {
   A a;
   &a.func;   // C2276
   // try the following line instead
   // &A::func;
}
```
