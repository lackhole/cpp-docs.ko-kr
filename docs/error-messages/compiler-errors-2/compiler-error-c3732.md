---
title: 컴파일러 오류 C3732
ms.date: 11/04/2016
f1_keywords:
- C3732
helpviewer_keywords:
- C3732
ms.assetid: 2d55a7e1-9c39-4379-a093-2f7beb27e2ca
ms.openlocfilehash: c71cca3643f6337060de6e4bb56ac64d8f0d6e4e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62327992"
---
# <a name="compiler-error-c3732"></a>컴파일러 오류 C3732

'interface': COM 이벤트를 발생 시키는 사용자 지정 인터페이스는 IDispatch에서 상속할 수 없습니다

COM 이벤트를 지 원하는 인터페이스에서 상속할 수 없습니다 `IDispatch`합니다. 자세한 내용은 [COM에서 이벤트 처리](../../cpp/event-handling-in-com.md) 를 참조합니다.

다음 오류 C3732를 생성합니다.

```
// C3732.cpp
#define _ATL_ATTRIBUTES 1
#include "atlbase.h"
#include "atlcom.h"

[module(name="test")];

// to resolve this C3732, use dual instead of object
// or inherit from IUnknown
[ object ]
__interface I : IDispatch
{
};

[ event_source(com), coclass ]
struct A
{
   __event __interface I;   // C3732
};

int main()
{
}
```