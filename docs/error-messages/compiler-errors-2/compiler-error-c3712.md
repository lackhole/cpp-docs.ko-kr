---
title: 컴파일러 오류 C3712
ms.date: 11/04/2016
f1_keywords:
- C3712
helpviewer_keywords:
- C3712
ms.assetid: 65b1fcaf-be89-4c55-9e40-25ec03457253
ms.openlocfilehash: 51772f22f83cff5c602bd2310d7913c0d317ba66
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74753369"
---
# <a name="compiler-error-c3712"></a>컴파일러 오류 C3712

' method ': 이벤트 처리기 메서드는 ' method ' 소스와 같은 형식을 반환 해야 합니다.

원본 이벤트 메서드와 동일한 형식을 반환 하지 않는 이벤트 처리기 메서드를 정의 했습니다. 이 오류를 해결 하려면 이벤트 처리기 메서드를 소스 이벤트 메서드와 동일한 반환 형식으로 지정 합니다.

다음 샘플에서는 C3712를 생성 합니다.

```cpp
// C3712.cpp
// compile with: /c
[event_source(native)]
class CEventSrc {
public:
   __event void event1();
};

[event_receiver(native)]
class CEventRec {
public:
   int handler1() { return 0; }
   // try the following line instead
   // void handler1() {}

   void HookEvents(CEventSrc* pSrc) {
      __hook(&CEventSrc::event1, pSrc, &CEventRec::handler1);   // C3712
   }
   void UnhookEvents(CEventSrc* pSrc) {
      __unhook(&CEventSrc::event1, pSrc, &CEventRec::handler1);   // C3712
   }
};
```
