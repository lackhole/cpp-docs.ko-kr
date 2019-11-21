---
title: 컴파일러 경고 (수준 1) C4374
ms.date: 11/04/2016
f1_keywords:
- C4374
helpviewer_keywords:
- C4374
ms.assetid: 4ac9aaec-d815-4b6e-825f-fa872092dd3b
ms.openlocfilehash: 31a43467020e3d90a2f02c667f7cdb6177b4d833
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966446"
---
# <a name="compiler-warning-level-1-c4374"></a>컴파일러 경고 (수준 1) C4374

' function1 ': 인터페이스 메서드는 비가상 메서드 ' function2 '에 의해 구현 되지 않습니다.

컴파일러는 메서드 정의에서 [가상](../../cpp/virtual-specifier.md) 키워드를 찾아야 합니다.

다음 샘플에서는 C4374를 생성 합니다.

```cpp
// C4374.cpp
// compile with: /clr /W1 /c /WX
public interface class I {
   void f();
};

public ref struct B {
   void f() {
      System::Console::WriteLine("B::f()");
   }
};

public ref struct C {
   virtual void f() {
      System::Console::WriteLine("C::f()");
   }
};

public ref struct D : B, I {};   // C4374
public ref struct E : C, I {};   // OK
```