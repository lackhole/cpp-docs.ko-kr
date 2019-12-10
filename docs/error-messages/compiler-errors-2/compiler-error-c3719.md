---
title: 컴파일러 오류 C3719
ms.date: 11/04/2016
f1_keywords:
- C3719
helpviewer_keywords:
- C3719
ms.assetid: d0d59d4e-babb-4480-9ef7-70cf1a28165c
ms.openlocfilehash: 4fca5bfd944514bf2658a8af5cbbd58efe5b39fc
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74753187"
---
# <a name="compiler-error-c3719"></a>컴파일러 오류 C3719

' interface ': 인터페이스 기반 이벤트 소스는 COM 이벤트에만 사용할 수 있습니다.

COM이 아닌 컨텍스트에서 인터페이스를 선언 했습니다.

다음 샘플에서는 C3719를 생성 합니다.

```cpp
// C3719a.cpp
#define _ATL_ATTRIBUTES 1
#include "atlbase.h"
#include "atlcom.h"

[module(name="MyLibrary", version="1.2", helpfile="MyHelpFile")];

[object]
__interface I {
   HRESULT func1();
};

[event_source(native), coclass]
struct A {
   __event __interface I;   // C3719

   // try the following line instead
   // __event func2();
};

int main() {
}
```

이 오류를 해결 하려면 [object](../../windows/object-cpp.md), [coclass](../../windows/coclass.md), [event_source](../../windows/event-source.md)및 [event_receiver](../../windows/event-receiver.md) 특성을 적절 하 게 적용 하 여 인터페이스 COM 클래스를 사용 하는 클래스를 만듭니다. 예를 들면 다음과 같습니다.:

```cpp
// C3719b.cpp
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>

[module(name="xx")];
[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface I {
   HRESULT f();
};

[coclass, event_source(com) , uuid("00000000-0000-0000-0000-000000000002")]
struct MyStruct {
   __event __interface I;
};

[event_receiver(com)]
struct MyStruct2 {
   void f() {
   }
   MyStruct2(I* pB) {
      __hook(&I::f, pB, &MyStruct2::f);
   }
};

int main()
{
}
```
