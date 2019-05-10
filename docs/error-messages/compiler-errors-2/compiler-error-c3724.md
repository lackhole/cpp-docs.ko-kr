---
title: 컴파일러 오류 C3724
ms.date: 11/04/2016
f1_keywords:
- C3724
helpviewer_keywords:
- C3724
ms.assetid: cab8aba7-14fc-406f-8cc6-32744c8f31c1
ms.openlocfilehash: 126317d78785b14f5ef613ec0c83d3e50b825d60
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328161"
---
# <a name="compiler-error-c3724"></a>컴파일러 오류 C3724

해야 #include \<windows.h >를 사용 하 여 이벤트를 사용 하 여 다중 스레딩

Windows.h 파일을 사용 하는 필요한 경우 이벤트에 다중 스레딩을 사용 합니다. 이 오류를 해결 하려면 추가 `#include <windows.h>` 파일은 이벤트 소스와 이벤트 수신기가 정의 하는 맨 위로 이동 합니다.

```
// C3724.cpp
// uncomment the following line to resolve
// #include <windows.h>

[event_source(native), threading(apartment)]
class CEventSrc {
public:
   __event void event1();   // C3724
};

[event_receiver(native)]
class CEventRec {
public:
   void handler1() {
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