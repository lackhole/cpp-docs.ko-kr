---
title: 컴파일러 오류 C2108
ms.date: 11/04/2016
f1_keywords:
- C2108
helpviewer_keywords:
- C2108
ms.assetid: c84f0b47-5e2c-47d2-8edb-427a40e17c36
ms.openlocfilehash: 3979fce67f1ecb7f78bd02d4f1c4d2cca287ceca
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62364560"
---
# <a name="compiler-error-c2108"></a>컴파일러 오류 C2108

첨자가 정수 계열 형식이 아닙니다.

배열 첨자 정수가 아닌 식입니다.

## <a name="example"></a>예제

C2108 잘못 사용한 경우에 발생할 수 있습니다는 `this` 포인터 형식의 기본 인덱서에 액세스 하는 값 형식입니다. 자세한 내용은 [의미 체계가이 포인터](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Semantics_of_the_this_pointer)합니다.

다음 샘플 C2108를 생성합니다.

```
// C2108.cpp
// compile with: /clr
using namespace System;

value struct B {
   property Double default[Double] {
      Double get(Double data) {
         return data*data;
      }
   }
   void Test() {
      Console::WriteLine("{0}", this[3.3]);   // C2108
      Console::WriteLine("{0}", this->default[3.3]);   // OK
   }
};

int main() {
   B ^ myb = gcnew B();
   myb->Test();
}
```