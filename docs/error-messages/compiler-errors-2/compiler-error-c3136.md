---
title: 컴파일러 오류 C3136
ms.date: 10/03/2018
f1_keywords:
- C3136
helpviewer_keywords:
- C3136
ms.assetid: c77103cd-00f7-408e-b74b-4f8562039d31
ms.openlocfilehash: e32ffca067c3b25120301527e7a708d53001d541
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62376252"
---
# <a name="compiler-error-c3136"></a>컴파일러 오류 C3136

'interface': COM 인터페이스를 다른 COM 인터페이스에서 에서만 상속할 수 있습니다, 'interface' COM 인터페이스가 아닙니다.

적용 된 인터페이스는 [interface 특성](../../windows/attributes/interface-attributes.md) COM 인터페이스가 아닌 인터페이스에서 상속 합니다. COM 인터페이스에서 궁극적으로 상속 `IUnknown`합니다. 인터페이스 특성으로 다음에 오는 인터페이스가 COM 인터페이스가입니다.

다음 예제에서는 C3136 오류가 생성 됩니다.

```
// C3136.cpp
#include "unknwn.h"

__interface A   // C3136
// try the following line instead
// _interface A : IUnknown
{
   int a();
};

[object]
__interface B : A
{
   int aa();
};
```