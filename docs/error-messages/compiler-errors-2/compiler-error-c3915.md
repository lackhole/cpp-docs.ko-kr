---
title: 컴파일러 오류 C3915
ms.date: 11/04/2016
f1_keywords:
- C3915
helpviewer_keywords:
- C3915
ms.assetid: 2b0a5e5f-3aec-4a4b-9157-233031817084
ms.openlocfilehash: 85654e266c3157ab145e7ac7aab454a0d4f6c102
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58776456"
---
# <a name="compiler-error-c3915"></a>컴파일러 오류 C3915

'type'에 기본 인덱싱된 속성이 (클래스 인덱서)

기본적으로 인덱싱된 속성 형식이 없습니다.

자세한 내용은 [property](../../extensions/property-cpp-component-extensions.md)을 참조하세요.

## <a name="example"></a>예제

다음 샘플 C3915를 생성합니다.

```
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

기본 인덱서를 사용 하 여 정의 된 위치는 동일한 compiland에서 사용 하려는 경우에 C3915 발생할 수 있습니다 <xref:System.Reflection.DefaultMemberAttribute>합니다.

다음 샘플 C3915를 생성합니다.

```
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