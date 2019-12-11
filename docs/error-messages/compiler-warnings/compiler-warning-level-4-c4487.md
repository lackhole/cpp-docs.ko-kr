---
title: 컴파일러 경고(수준 4) C4487
ms.date: 11/04/2016
f1_keywords:
- C4487
helpviewer_keywords:
- C4487
ms.assetid: 796144cf-cd3c-4edc-b6a4-96192b7eb4f0
ms.openlocfilehash: b83b3b33727db300367156e10f902aaa6ff4bfdb
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990777"
---
# <a name="compiler-warning-level-4-c4487"></a>컴파일러 경고(수준 4) C4487

' derived_class_function ': 상속 된 비가상 메서드 ' base_class_function '과 (와) 일치 하지만 명시적으로 ' n e w '로 표시 되어 있지 않습니다.

파생 클래스의 함수에는 비가상 기본 클래스 함수와 동일한 시그니처가 있습니다. C4487는 파생 클래스 함수가 기본 클래스 함수를 재정의 하지 않는다는 사실을 알려 줍니다. 이 경고를 해결 하려면 파생 클래스 함수를 `new`로 명시적으로 표시 합니다.

자세한 내용은 [new (vtable의 새 슬롯)](../../extensions/new-new-slot-in-vtable-cpp-component-extensions.md)를 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 C4487를 생성 합니다.

```cpp
// C4487.cpp
// compile with: /W4 /clr
using namespace System;
public ref struct B {
   void f() { Console::WriteLine("in B::f"); }
   void g() { Console::WriteLine("in B::g"); }
};

public ref struct D : B {
   void f() { Console::WriteLine("in D::f"); }   // C4487
   void g() new { Console::WriteLine("in D::g"); }   // OK
};

int main() {
   B ^ a = gcnew D;
   // will call base class functions
   a->f();
   a->g();
}
```
