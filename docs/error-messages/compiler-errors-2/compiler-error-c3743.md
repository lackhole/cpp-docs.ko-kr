---
title: 컴파일러 오류 C3743
ms.date: 11/04/2016
f1_keywords:
- C3743
helpviewer_keywords:
- C3743
ms.assetid: 7ca9a76e-7b60-46d1-ab8b-18600cf1a306
ms.openlocfilehash: 137913e0c6909712cbb6745666112d315925ab0c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62226858"
---
# <a name="compiler-error-c3743"></a>컴파일러 오류 C3743

수만 후크/언 후크 할 전체 인터페이스 event_receiver의 'layout_dependent' 매개 변수가 true 인 경우

[__unhook](../../cpp/unhook.md) 함수에 전달 된 값에 따라 사용 하는 매개 변수 수가 다릅니다 합니다 `layout_dependent` 에서 매개 변수를 [event_receiver](../../windows/event-receiver.md) 클래스입니다.

다음 샘플에서는 C3743 오류가 생성 됩니다.

```
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