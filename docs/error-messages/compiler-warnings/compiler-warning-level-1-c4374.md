---
title: 컴파일러 경고(수준 1) C4374
ms.date: 11/04/2016
f1_keywords:
- C4374
helpviewer_keywords:
- C4374
ms.assetid: 4ac9aaec-d815-4b6e-825f-fa872092dd3b
ms.openlocfilehash: 5cf18a3dcd94f59ce1ae8feb675f251bea5715a5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62302243"
---
# <a name="compiler-warning-level-1-c4374"></a>컴파일러 경고(수준 1) C4374

'function1': 인터페이스 메서드 'function2' 비가상 메서드로 구현 되지 것입니다

컴파일러를 찾지 못했습니다 합니다 [가상](../../cpp/virtual-specifier.md) 메서드 정의에서 키워드입니다.

다음 샘플에서는 C4374 오류가 생성 됩니다.

```
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