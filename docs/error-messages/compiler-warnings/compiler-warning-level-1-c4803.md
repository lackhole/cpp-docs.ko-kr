---
title: 컴파일러 경고 (수준 1) C4803
ms.date: 11/04/2016
f1_keywords:
- C4803
helpviewer_keywords:
- C4803
ms.assetid: 2552f3a6-c418-49f4-98a2-a929857be658
ms.openlocfilehash: ebf7b3baec3519a142c7a1835aa15a980974bb48
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052342"
---
# <a name="compiler-warning-level-1-c4803"></a>컴파일러 경고 (수준 1) C4803

' method ': raise 메서드에 이벤트 ' event '의 저장소 클래스와 다른 저장소 클래스가 있습니다.

이벤트 메서드의 저장소 클래스는 이벤트 선언과 동일 해야 합니다. 컴파일러는 저장소 클래스가 같도록 이벤트의 메서드를 조정 합니다.

이 경고는 인터페이스에서 이벤트를 구현 하는 클래스가 있는 경우에 발생할 수 있습니다. 컴파일러는 인터페이스에서 이벤트에 대 한 raise 메서드를 암시적으로 생성 하지 않습니다. 클래스에서 해당 인터페이스를 구현 하는 경우 컴파일러에서 암시적으로 raise 메서드를 생성 하 고 해당 메서드가 가상이 되지 않으므로 경고가 발생 합니다. 이벤트에 대 한 자세한 내용은 [이벤트](../../extensions/event-cpp-component-extensions.md)를 참조 하세요.

경고를 해제 하는 방법에 대 한 자세한 내용은 [warning](../../preprocessor/warning.md) pragma를 참조 하십시오.

## <a name="example"></a>예제

다음 샘플에서는 C4803를 생성 합니다.

```cpp
// C4803.cpp
// compile with: /clr /W1
using namespace System;

public delegate void Del();

ref struct E {
   Del ^ _pd1;
   event Del ^ E1 {
      void add (Del ^ pd1) {
         _pd1 = dynamic_cast<Del ^>(Delegate::Combine(_pd1, pd1));
      }

      void remove(Del^ pd1) {
         _pd1 = dynamic_cast<Del^> (Delegate::Remove(_pd1, pd1));
      }

      virtual void raise() {   // C4803 warning (remove virtual)
         if (_pd1)
            _pd1();
      }
   }

   void func() {
      Console::WriteLine("In E::func()");
   }
};

int main() {
   E ^ ep = gcnew E;
   ep->E1 += gcnew Del(ep, &E::func);
   ep->E1();
   ep->E1 -= gcnew Del(ep, &E::func);
   ep->E1();
}
```
