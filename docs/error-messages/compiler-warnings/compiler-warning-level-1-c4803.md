---
title: 컴파일러 경고(수준 1) C4803
ms.date: 11/04/2016
f1_keywords:
- C4803
helpviewer_keywords:
- C4803
ms.assetid: 2552f3a6-c418-49f4-98a2-a929857be658
ms.openlocfilehash: bb8f5fe9d55a44193325a2fcfe9ef7675a2b3b89
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59779221"
---
# <a name="compiler-warning-level-1-c4803"></a>컴파일러 경고(수준 1) C4803

'method': raise 메서드에 이벤트를 다른 저장소 클래스는 'event'

이벤트 메서드는 이벤트 선언 같은 저장소 클래스가 있어야 합니다. 컴파일러는 저장소 클래스는 동일한 이벤트의 메서드를 조정 합니다.

이 경고는 인터페이스에서 이벤트를 구현 하는 클래스가 있는 경우에 발생할 수 있습니다. 컴파일러 생성 하지 않습니다 암시적으로 이벤트에 raise 메서드가 인터페이스에서. 컴파일러에서 암시적으로 raise 메서드가 생성 및 해당 메서드에 됩니다 가상 따라서 클래스에서 해당 인터페이스를 구현 하는 경우 경고 합니다. 이벤트에 대 한 자세한 내용은 참조 하세요. [이벤트](../../extensions/event-cpp-component-extensions.md)합니다.

참조 [경고](../../preprocessor/warning.md) pragma 경고를 해제 하는 방법에 대 한 정보에 대 한 합니다.

## <a name="example"></a>예제

다음 샘플 C4803를 생성합니다.

```
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
