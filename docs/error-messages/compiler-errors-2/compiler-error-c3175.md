---
title: 컴파일러 오류 C3175
ms.date: 11/04/2016
f1_keywords:
- C3175
helpviewer_keywords:
- C3175
ms.assetid: 3f19d513-a05a-4b6c-806f-276fe5c36b90
ms.openlocfilehash: 368e5a9cb9bea04a7889c25c86a7245049677112
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62175468"
---
# <a name="compiler-error-c3175"></a>컴파일러 오류 C3175

'function1': 관리 되지 않는 함수 'function2'에서 관리 되는 형식의 메서드를 호출할 수 없습니다

관리 되지 않는 함수는 관리 되는 클래스의 멤버 함수를 호출할 수 없습니다.

다음 샘플에서는 C3175를 생성합니다.

```
// C3175_2.cpp
// compile with: /clr

ref struct A {
   static void func() {
   }
};

#pragma unmanaged   // remove this line to resolve

void func2() {
   A::func();   // C3175
}

#pragma managed

int main() {
   A ^a = gcnew A;
   func2();
}
```
