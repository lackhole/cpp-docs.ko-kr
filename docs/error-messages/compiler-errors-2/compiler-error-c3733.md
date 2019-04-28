---
title: 컴파일러 오류 C3733
ms.date: 11/04/2016
f1_keywords:
- C3733
helpviewer_keywords:
- C3733
ms.assetid: 0cc1a9fe-1400-4be3-b35a-16435cba7a5a
ms.openlocfilehash: 006f87691c6e0839115e2c02ab0d922aa95eaa93
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62327979"
---
# <a name="compiler-error-c3733"></a>컴파일러 오류 C3733

'event': COM 이벤트를 지정 하는 것에 대 한 구문이 잘못 되었습니다 '__interface'를 잊으셨나요?

COM 이벤트에 대 한 잘못 된 구문이 사용 되었습니다. 이 오류를 해결 하려면 이벤트 형식을 변경 하거나 COM 이벤트 규칙을 준수 하는 구문은 수정 합니다.

다음 샘플에서는 C3733 오류가 생성 됩니다.

```
#define _ATL_ATTRIBUTES 1
#include "atlbase.h"
#include "atlcom.h"

[coclass, event_source(com), // change 'com' to 'native' to resolve
uuid("00000000-0000-0000-0000-000000000001")]
class A
{
   __event void func();   // C3733
};

int main()
{
}
```