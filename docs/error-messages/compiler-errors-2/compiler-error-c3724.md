---
title: 컴파일러 오류 C3724
ms.date: 11/04/2016
f1_keywords:
- C3724
helpviewer_keywords:
- C3724
ms.assetid: cab8aba7-14fc-406f-8cc6-32744c8f31c1
ms.openlocfilehash: b107137652c4efde43fdfe9c991240767eb5ced7
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74752979"
---
# <a name="compiler-error-c3724"></a>컴파일러 오류 C3724

이벤트에 다중 스레딩을 사용 하려면 windows > \<#include 해야 합니다.

이벤트에 다중 스레딩을 사용 하는 경우에는 windows .h 파일이 필요 합니다. 이 오류를 해결 하려면 이벤트 원본 및 이벤트 수신기가 정의 된 파일의 맨 위에 `#include <windows.h>`를 추가 합니다.

```cpp
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
