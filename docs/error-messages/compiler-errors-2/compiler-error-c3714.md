---
title: 컴파일러 오류 C3714
ms.date: 11/04/2016
f1_keywords:
- C3714
helpviewer_keywords:
- C3714
ms.assetid: 17718f75-5a37-4e42-912b-487e91008a95
ms.openlocfilehash: 1078bf8a97f6cb7afeaf7046489fe262c0bb0199
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74753330"
---
# <a name="compiler-error-c3714"></a>컴파일러 오류 C3714

' method ': 이벤트 처리기 메서드는 ' method ' 소스와 같은 호출 규칙을 포함 해야 합니다.

원본 이벤트 메서드와 동일한 호출 규칙을 사용 하지 않는 이벤트 처리기 메서드를 정의 했습니다. 이 오류를 해결 하려면 이벤트 처리기 메서드에 소스 이벤트 메서드와 동일한 호출 규칙을 제공 합니다. 예를 들어 아래 코드에서 `handler1`의 호출 규칙을 설정 하 고 `event1` 일치 ([__cdecl](../../cpp/cdecl.md) 또는 [__stdcall](../../cpp/stdcall.md) 또는 기타) 합니다. 두 선언에서 호출 규칙 키워드를 제거 하면 문제를 해결 하 고 `event1` 및 `handler1`가 [thiscall](../../cpp/thiscall.md) 호출 규칙을 기본값으로 합니다. 자세한 내용은 [호출 규칙](../../cpp/calling-conventions.md) 을 참조 하세요.

다음 샘플에서는 C3714를 생성 합니다.

```cpp
// C3714.cpp
// compile with: /c
// processor: x86
[event_source(native)]
class CEventSrc {
public:
   __event void __cdecl event1();
   // try the following line instead
   // __event void __stdcall event1();
};

[event_receiver(native)]
class CEventRec {
public:
   void __stdcall handler1() {}

   void HookEvents(CEventSrc* pSrc) {
      __hook(&CEventSrc::event1, pSrc, &CEventRec::handler1);   // C3714
   }

   void UnhookEvents(CEventSrc* pSrc) {
      __unhook(&CEventSrc::event1, pSrc, &CEventRec::handler1); // C3714
   }
};
```
