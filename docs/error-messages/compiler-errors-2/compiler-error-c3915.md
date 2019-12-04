---
title: 컴파일러 오류 C3915
ms.date: 11/04/2016
f1_keywords:
- C3915
helpviewer_keywords:
- C3915
ms.assetid: 2b0a5e5f-3aec-4a4b-9157-233031817084
ms.openlocfilehash: 26fdcd3b7989d9030249133e6dc1d277aa1a9f44
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756281"
---
# <a name="compiler-error-c3915"></a>컴파일러 오류 C3915

' type '에 인덱싱된 기본 속성 (클래스 인덱서)이 없습니다.

형식에 인덱싱된 기본 속성이 없습니다.

자세한 내용은 [property](../../extensions/property-cpp-component-extensions.md)을 참조하세요.

## <a name="example"></a>예제

다음 샘플에서는 C3915를 생성 합니다.

```cpp
// C3915.cpp
// compile with: /clr
ref class X {
public:
// uncomment property to resolve this C3915
//   property int default[]
//   {
//      int get(int i)
//      {
//         return 863;
//      }
//   }
};

int main() {
   X^ x = new X;
   System::Console::WriteLine(x[1]);   // C3915
}
```

## <a name="example"></a>예제

C3915 <xref:System.Reflection.DefaultMemberAttribute>로 정의 된 동일한 compiland에서 기본 인덱서를 사용 하려고 시도 하는 경우에도이 발생할 수 있습니다.

다음 샘플에서는 C3915를 생성 합니다.

```cpp
// C3915_b.cpp
// compile with: /clr
using namespace System;

[Reflection::DefaultMember("XXX")]
ref struct A {
   property Double XXX[Double] {
      Double get(Double data) {
         return data*data;
      }
   }
};

ref struct B {
   property Double default[Double] {
      Double get(Double data) {
         return data*data;
      }
   }
};

int main() {
   A ^ mya = gcnew A();
   Console::WriteLine("{0}", mya[3]);   // C3915

   B ^ myb = gcnew B();
   Console::WriteLine("{0}", myb[3]);   // OK
}
```
