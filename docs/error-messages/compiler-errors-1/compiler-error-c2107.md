---
title: 컴파일러 오류 C2107
ms.date: 11/04/2016
f1_keywords:
- C2107
helpviewer_keywords:
- C2107
ms.assetid: 2866a121-884e-4bb5-8613-36de5817000e
ms.openlocfilehash: e492f58717a8356da54f7f26bd0d5db905f858a0
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745878"
---
# <a name="compiler-error-c2107"></a>컴파일러 오류 C2107

잘못 된 인덱스입니다. 간접 참조는 허용 되지 않습니다.

첨자가 포인터로 계산 되지 않는 식에 적용 됩니다.

## <a name="example"></a>예제

C2107는 값 형식의 `this` 포인터를 잘못 사용 하 여 형식의 기본 인덱서에 액세스 하는 경우에 발생할 수 있습니다. 자세한 내용은 [이 포인터의 의미 체계](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Semantics_of_the_this_pointer)를 참조 하세요.

다음 샘플에서는 C2107를 생성 합니다.

```cpp
// C2107.cpp
// compile with: /clr
using namespace System;

value struct B {
   property String ^ default[String ^] {
      String ^ get(String ^ data) {
         return "abc";
      }
   }
   void Test() {
      Console::WriteLine("{0}", this["aa"]);   // C2107
      Console::WriteLine("{0}", this->default["aa"]);   // OK
   }
};

int main() {
   B ^ myb = gcnew B();
   myb->Test();
}
```
