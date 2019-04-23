---
title: 컴파일러 오류 C3910
ms.date: 11/04/2016
f1_keywords:
- C3910
helpviewer_keywords:
- C3910
ms.assetid: cfcbe620-b463-463b-95ea-2d60ad33ebb5
ms.openlocfilehash: 186cd67d77e9aafbfe6a7d9dc18afb2bdbd94f0c
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59776518"
---
# <a name="compiler-error-c3910"></a>컴파일러 오류 C3910

'event': 'method' 멤버를 정의 해야 합니다

이벤트를 정의 되었지만 지정 된 필수 접근자 메서드가 없습니다.

자세한 내용은 [이벤트](../../extensions/event-cpp-component-extensions.md)합니다.

다음 샘플에서는 C3910 오류가 생성 됩니다.

```
// C3910.cpp
// compile with: /clr /c
delegate void H();
ref class X {
   event H^ E {
      // uncomment the following lines
      // void add(H^) {}
      // void remove( H^ h ) {}
      // void raise( ) {}
   };   // C3910

   event H^ E2; // OK data member
};
```