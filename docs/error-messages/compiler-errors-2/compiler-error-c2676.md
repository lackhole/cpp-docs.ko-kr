---
title: 컴파일러 오류 C2676
ms.date: 11/04/2016
f1_keywords:
- C2676
helpviewer_keywords:
- C2676
ms.assetid: 838a5e34-c92f-4f65-a597-e150bf8cf737
ms.openlocfilehash: 1a3eab8d1df7534f2bfbed42db5c1a660942eacc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62164999"
---
# <a name="compiler-error-c2676"></a>컴파일러 오류 C2676

이항 'operator': 'type' 정의 하지 않습니다이 연산자 또는 허용 되는 형식으로의 변환을 미리 정의 된 운영자에 게

연산자를 사용하려면 지정된 형식에 대해 오버로드하거나 연산자가 정의된 형식으로의 변환을 정의해야 합니다.

## <a name="example"></a>예제

다음 샘플 C2676를 생성합니다.

```
// C2676.cpp
// C2676 expected
struct C {
   C();
} c;

struct D {
   D();
   D operator >>( C& ){return * new D;}
   D operator <<( C& ){return * new D;}
} d;

struct E {
   // operator int();
};

int main() {
   d >> c;
   d << c;
   E e1, e2;
   e1 == e2;   // uncomment operator int in class E, then
               // it is OK even though neither E::operator==(E) nor
               // operator==(E, E) defined. Uses the conversion to int
               // and then the builtin-operator==(int, int)
}
```

## <a name="example"></a>예제

포인터 산술 연산을 수행 하려는 경우에 C2676 발생할 수 있습니다는 `this` 참조 형식의 포인터입니다.

`this` 포인터는 참조 형식에서 형식 핸들입니다. 자세한 내용은 [의미 체계가이 포인터](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Semantics_of_the_this_pointer)합니다.

다음 샘플 C2676를 생성합니다.

```
// C2676_a.cpp
// compile with: /clr
using namespace System;

ref struct A {
   property Double default[Double] {
      Double get(Double data) {
         return data*data;
      }
   }

   A() {
      Console::WriteLine("{0}", this + 3.3);   // C2676
      Console::WriteLine("{0}", this[3.3]);   // OK
   }
};

int main() {
   A ^ mya = gcnew A();
}
```