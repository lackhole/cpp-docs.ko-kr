---
title: 컴파일러 오류 C3703
ms.date: 11/04/2016
f1_keywords:
- C3703
helpviewer_keywords:
- C3703
ms.assetid: 7e3677d9-f2be-4c26-998f-423564e9023c
ms.openlocfilehash: 1071623c8dbaef52a6a391d8858e7502de9c74b4
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757997"
---
# <a name="compiler-error-c3703"></a>컴파일러 오류 C3703

' event handler ': 이벤트 처리기 메서드는 ' event ' 소스와 동일한 저장소 클래스를 포함 해야 합니다.

[이벤트](../../cpp/event-handling.md) 에 후크 되는 이벤트 처리기와 다른 저장소 클래스가 있습니다. 예를 들어 이벤트 처리기가 정적 멤버 함수이 고 이벤트가 static이 아닌 경우이 오류가 발생 합니다. 이 오류를 해결 하려면 이벤트와 이벤트 처리기에 동일한 저장소 클래스를 지정 합니다.

다음 샘플에서는 C3703를 생성 합니다.

```cpp
// C3703.cpp
// C3703 expected
#include <stdio.h>

[event_source(type=native)]
class CEventSrc {
public:
   __event static void MyEvent();
};

[event_receiver(type=native)]
class CEventHandler {
public:
   // delete the following line to resolve
   void MyHandler() {}

   // try the following line instead
   // static void MyHandler() {}

   void HookIt(CEventSrc* pSource) {
      __hook(CEventSrc::MyEvent, pSource, &CEventHandler::MyHandler);
   }

   void UnhookIt(CEventSrc* pSource) {
      __unhook(CEventSrc::MyEvent, pSource, &CEventHandler::MyHandler);
   }
};

int main() {
   CEventSrc src;
   CEventHandler hnd;

   hnd.HookIt(&src);
   __raise src.MyEvent();
   hnd.UnhookIt(&src);
}
```
