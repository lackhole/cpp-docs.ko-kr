---
title: 컴파일러 오류 C3138
ms.date: 11/04/2016
f1_keywords:
- C3138
helpviewer_keywords:
- C3138
ms.assetid: 364ee9e8-9358-410e-bd35-9c4a226a3753
ms.openlocfilehash: d812c14c2f364681fe28a58bdaed68fe3ed8ad30
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62374991"
---
# <a name="compiler-error-c3138"></a>컴파일러 오류 C3138

'interface': 'attribute' 인터페이스는 IDispatch에서 상속 하는 인터페이스 또는 IDispatch에서 상속 해야 합니다

사용 하 여 인터페이스를 [이중](../../windows/dual.md) 또는 [dispinterface](../../windows/dispinterface.md) 특성이 없는 `IDispatch` 직접 또는 간접 기본 인터페이스로 합니다.

다음 예제에서는 C3138를 생성합니다.

```
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