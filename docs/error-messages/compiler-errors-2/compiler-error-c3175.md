---
title: 컴파일러 오류 C3175
ms.date: 11/04/2016
f1_keywords:
- C3175
helpviewer_keywords:
- C3175
ms.assetid: 3f19d513-a05a-4b6c-806f-276fe5c36b90
ms.openlocfilehash: 8be6cfa72c33212593c0b2a73ad38ad9fc113f26
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761714"
---
# <a name="compiler-error-c3175"></a>컴파일러 오류 C3175

' function1 ': 관리 되는 형식의 메서드를 관리 되지 않는 함수 ' function2 '에서 호출할 수 없습니다.

관리 되지 않는 함수는 관리 되는 클래스의 멤버 함수를 호출할 수 없습니다.

다음 샘플에서는 C3175를 생성 합니다.

```cpp
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
