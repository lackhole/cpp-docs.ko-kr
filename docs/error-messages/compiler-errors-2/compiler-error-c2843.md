---
title: 컴파일러 오류 C2843
ms.date: 11/04/2016
f1_keywords:
- C2843
helpviewer_keywords:
- C2843
ms.assetid: 9d3f2ac4-eea5-4fed-abeb-e752f442bfcc
ms.openlocfilehash: d6ab867323e629695e161f3ac001a3fb2174775e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74752004"
---
# <a name="compiler-error-c2843"></a>컴파일러 오류 C2843

'member': WinRT 또는 관리되는 형식의 비정적 데이터 멤버 주소나 메서드 주소를 가져올 수 없습니다.

WinRT 또는 관리되는 클래스 또는 인터페이스의 비정적 데이터 멤버의 주소를 사용하려면 인스턴스가 필요합니다.

다음 샘플에서는 C2843 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.

```cpp
// C2843_2.cpp
// compile with: /clr
public ref class C {
public:
   int m_i;
};

ref struct MyStruct {
   static void sf() {}
   void f() {}
};

int main() {
   MyStruct ^ps = gcnew MyStruct;
   void (__clrcall MyStruct::*F1)() = & MyStruct::f;   // C2843
   void (__clrcall MyStruct::*F2)() = & ps->f;   // C2843
   void (__clrcall MyStruct::*F3)();   // C2843

   void (__clrcall *F5)() = MyStruct::sf;   // OK
   void (__clrcall *F6)() = & ps->sf;   // OK

   interior_ptr<int> i = &C::m_i; // C2843
   C ^x = gcnew C();
   interior_ptr<int> ii = &x->m_i;
}
```
