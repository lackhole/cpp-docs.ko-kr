---
title: 컴파일러 오류 C2107
ms.date: 11/04/2016
f1_keywords:
- C2107
helpviewer_keywords:
- C2107
ms.assetid: 2866a121-884e-4bb5-8613-36de5817000e
ms.openlocfilehash: 2b388495c6ce31452bd3f8e8bfc6c26a6bfbdbe8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62364794"
---
# <a name="compiler-error-c2107"></a>컴파일러 오류 C2107

인덱스가 잘못 되어 간접 참조 허용 되지 않습니다

첨자는 포인터에는 평가 되지 않는 식에 적용 됩니다.

## <a name="example"></a>예제

C2107 잘못 사용한 경우에 발생할 수 있습니다는 `this` 포인터 형식의 기본 인덱서에 액세스 하는 값 형식입니다. 자세한 내용은 [의미 체계가이 포인터](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Semantics_of_the_this_pointer)합니다.

다음 샘플 C2107를 생성합니다.

```
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