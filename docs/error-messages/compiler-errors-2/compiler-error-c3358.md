---
title: 컴파일러 오류 C3358
ms.date: 11/04/2016
f1_keywords:
- C3358
helpviewer_keywords:
- C3358
ms.assetid: 180b93df-e78f-441a-91fb-1594c681f7f0
ms.openlocfilehash: 8d57bf7447ba0c05585d3c18cfaaf960ddc0f968
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402621"
---
# <a name="compiler-error-c3358"></a>컴파일러 오류 C3358

'symbol': 기호를 찾을 수 없습니다.

필요한 기호를 찾을 수 없습니다.

다음 샘플에서는 C3358을 생성합니다.

```
// C3358.cpp
#define __ATLEVENT_H__ 1   // remove this line to resolve the error
#define _ATL_ATTRIBUTES 1
#include "atlbase.h"
#include "atlcom.h"

[event_receiver(com)]
struct A   // C3358
{
   void func();
};

int main()
{
}
```