---
title: 컴파일러 오류 C3909
ms.date: 11/04/2016
f1_keywords:
- C3909
helpviewer_keywords:
- C3909
ms.assetid: 0a443132-e53f-42dc-a58b-f086da3e7bfd
ms.openlocfilehash: 69613a1058bd5178ea4c03931664dd00bad7a101
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74748998"
---
# <a name="compiler-error-c3909"></a>컴파일러 오류 C3909

aWinRT 또는 관리 되는 이벤트 선언은 WinRT 또는 관리 되는 형식에서 발생 해야 합니다.

Windows 런타임 이벤트 또는 관리되는 이벤트가 네이티브 형식으로 선언되었습니다. 이 오류를 해결하려면 Windows 런타임 형식 또는 관리되는 형식으로 이벤트를 선언합니다.

자세한 내용은 [이벤트](../../extensions/event-cpp-component-extensions.md)를 참조 하세요.

다음 샘플에서는 C3909를 생성하고 해결 방법을 보여 줍니다.

```cpp
// C3909.cpp
// compile with: /clr /c
delegate void H();
class X {
   event H^ E;   // C3909 - use ref class X instead
};

ref class Y {
   static event H^ E {
      void add(H^) {}
      void remove( H^ h ) {}
      void raise( ) {}
   }
};
```
