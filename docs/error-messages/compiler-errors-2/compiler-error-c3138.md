---
title: 컴파일러 오류 C3138
ms.date: 11/04/2016
f1_keywords:
- C3138
helpviewer_keywords:
- C3138
ms.assetid: 364ee9e8-9358-410e-bd35-9c4a226a3753
ms.openlocfilehash: 3980bebdae0301dfbbb3cea91d6631053a118995
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761255"
---
# <a name="compiler-error-c3138"></a>컴파일러 오류 C3138

' interface ': ' attribute ' 인터페이스는 IDispatch에서 상속 하거나 IDispatch에서 상속 하는 인터페이스에서 상속 해야 합니다.

[Dual](../../windows/dual.md) 또는 특성이 있는 인터페이스에는 [직접 또는 간접](../../windows/dispinterface.md) 기본 인터페이스로 `IDispatch` 없습니다.

다음 예제에서는 C3138를 생성 합니다.

```cpp
// C3138.cpp
#include <unknwn.h>

[ object, uuid("77ac9240-6e9a-11d2-97de-0000f805d73b") ]
__interface IMyCustomInterface
{
   HRESULT mf1(void);
};

[ dispinterface, uuid("3536f8a0-6e9a-11d2-97de-0000f805d73b") ]
__interface IMyDispInterface : IUnknown
{
   [id(1)] HRESULT mf2(void);
};

[ object, dual, uuid("34e90a10-6e9a-11d2-97de-0000f805d73b") ]
__interface IMyDualInterface : IMyCustomInterface  // C3138 expected
{
   HRESULT mf3(void);
};
```
