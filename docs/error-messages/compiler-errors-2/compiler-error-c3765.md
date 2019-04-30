---
title: 컴파일러 오류 C3765
ms.date: 11/04/2016
f1_keywords:
- C3765
helpviewer_keywords:
- C3765
ms.assetid: feadee7a-fcfb-402c-af2f-0e656f814a13
ms.openlocfilehash: 86c043889c5342ed4f3edfc4d8a298bcbd345b3b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400242"
---
# <a name="compiler-error-c3765"></a>컴파일러 오류 C3765

'event': event_receiver로 표시 된 'type' 클래스/구조체에서 이벤트를 정의할 수 없습니다

클래스에 표시 되는 경우는 [event_receiver](../../windows/event-receiver.md) 특성 클래스를 포함할 수 없습니다는 [__event](../../cpp/event.md) 선언 합니다.

다음 샘플에서는 C3765 오류가 생성 됩니다.

```
// C3765.cpp
[event_receiver(native)]
struct ER2 {
   __event void f();   // C3765
   __event void b(int);   // C3765
};
```