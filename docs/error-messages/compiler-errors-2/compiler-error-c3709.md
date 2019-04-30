---
title: 컴파일러 오류 C3709
ms.date: 11/04/2016
f1_keywords:
- C3709
helpviewer_keywords:
- C3709
ms.assetid: d5576b04-2f93-420a-8f3e-8b8e987e8dab
ms.openlocfilehash: 3eb2963916cbbcbd925f755f9162ce59e9bff569
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328434"
---
# <a name="compiler-error-c3709"></a>컴파일러 오류 C3709

'function': __hook의 이벤트 지정 구문이 /\__unhook

사용 하 여 이벤트 소스를 지정 하는 경우 [__hook](../../cpp/hook.md) 하거나 [__unhook](../../cpp/unhook.md), 첫 번째 매개 변수 메서드여야 유효한 이벤트 및 두 번째 매개 변수는 올바른 이벤트 소스 개체 (메서드 아님) 이어야 합니다.

다음 샘플에서는 C3709 오류가 생성 됩니다.

```
// C3709.cpp
// compile with: /LD
[event_source(native)]
class CEventSrc
{
public:
   __event void event1();
};

[event_receiver(native)]
class CEventRec
{
public:
   void handler1()
   {
   }

   void HookEvents(CEventSrc* pSrc)
   {
      __hook(bad, pSrc, CEventRec::handler1);   // C3709
      // Try the following line instead:
      // __hook(&CEventSrc::event1, pSrc, CEventRec::handler1);
   }

   void UnhookEvents(CEventSrc* pSrc)
   {
      __unhook(&CEventSrc::event1, pSrc, CEventRec::handler1);
   }
};
```