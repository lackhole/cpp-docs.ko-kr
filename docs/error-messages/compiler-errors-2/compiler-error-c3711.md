---
title: 컴파일러 오류 C3711
ms.date: 11/04/2016
f1_keywords:
- C3711
helpviewer_keywords:
- C3711
ms.assetid: 26d581cc-2153-4ee0-b814-a371184be3e1
ms.openlocfilehash: 7f2414a51321bf249e3ac049a7048f41b71cb856
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74753408"
---
# <a name="compiler-error-c3711"></a>컴파일러 오류 C3711

' method ': 관리 되지 않는 이벤트 소스 메서드는 void 또는 정수 계열 형식을 반환 해야 합니다.

Void 또는 정수 계열 형식을 반환 하지 않는 메서드를 이벤트 소스에서 정의 했습니다. 이 오류를 해결 하려면 이벤트 및 이벤트 처리기의 반환 형식이 `void` 또는 `int` 또는 `long`와 같은 정수 계열 형식 인지 확인 합니다.

다음 샘플에서는 C3711를 생성 합니다.

```cpp
// C3711.cpp
#include <atlbase.h>
#include <atlcom.h>
#include <atlctl.h>

[event_source(native)]
class CEventSrc {
public:
   __event float event1();   // C3711
   // try the following line instead
   // __event int event1();
   // also change the handler, below
};

[event_receiver(native)]
class CEventRec {
public:
   float handler1() {         // change float to int
      return 0.0;             // change 0.0 to 0
   }
   void HookEvents(CEventSrc* pSrc) {
      __hook(CEventSrc::event1, pSrc, CEventRec::handler1);
   }
   void UnhookEvents(CEventSrc* pSrc) {
      __unhook(CEventSrc::event1, pSrc, CEventRec::handler1);
   }
};

int main() {
}
```
