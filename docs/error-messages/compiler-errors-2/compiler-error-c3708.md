---
title: 컴파일러 오류 C3708
ms.date: 11/04/2016
f1_keywords:
- C3708
helpviewer_keywords:
- C3708
ms.assetid: 45e71564-9c7f-437f-98d8-a735ce162ed0
ms.openlocfilehash: b5a2688cf138733a7a2891238953bc9fd894e483
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757971"
---
# <a name="compiler-error-c3708"></a>컴파일러 오류 C3708

' interface ': ' keyword '를 잘못 사용 했습니다. 호환 되는 이벤트 소스의 멤버 여야 합니다.

인터페이스를 이벤트로 선언 하려면 이벤트 선언이 이벤트 소스에 있어야 합니다.

다음 샘플에서는 C3708를 생성 합니다.

```cpp
// C3708.cpp
// compile with: /c
#define _ATL_ATTRIBUTES 1
#include "atlbase.h"
#include "atlcom.h"

[ module(name="MyLibrary")];

[ object, uuid("00000000-0000-0000-0000-000000000001") ]
__interface I {
   HRESULT func();
};

[ object, uuid("00000000-0000-0000-0000-000000000002") ]
__interface II {
   HRESULT func();
};

__event __interface I;   // C3708

// put the event in an event source
[ coclass, event_source(com), uuid("00000000-0000-0000-0000-000000000003") ]
struct E : II {
   __event __interface II;
};
```
