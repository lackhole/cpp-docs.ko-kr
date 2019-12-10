---
title: 컴파일러 오류 C3743
ms.date: 11/04/2016
f1_keywords:
- C3743
helpviewer_keywords:
- C3743
ms.assetid: 7ca9a76e-7b60-46d1-ab8b-18600cf1a306
ms.openlocfilehash: c0e2082dc87c6236aa11dd3094d056b0024dfc2f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74752472"
---
# <a name="compiler-error-c3743"></a>컴파일러 오류 C3743

event_receiver의 ' layout_dependent ' 매개 변수가 true 인 경우에만 전체 인터페이스를 후크/언 후크 할 수 있습니다.

[__Unhook](../../cpp/unhook.md) 함수는 [event_receiver](../../windows/event-receiver.md) 클래스의 `layout_dependent` 매개 변수에 전달 된 값을 기준으로 사용 하는 매개 변수의 수에 따라 달라 집니다.

다음 샘플에서는 C3743를 생성 합니다.

```cpp
// C3743.cpp
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>
[module(name="xx")];
[object] __interface I { HRESULT f(); };

[event_receiver(com, layout_dependent=true), coclass]
struct R : I {
        HRESULT f() {
      return 0;
   }
        R() {
   }

   R(I* a) {
      __hook(I, a, &R::f);   // C3743
      // The following line resolves the error.
      // __hook(I, a);
   }
};
```
