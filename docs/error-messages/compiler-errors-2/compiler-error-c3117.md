---
title: 컴파일러 오류 C3117
ms.date: 11/04/2016
f1_keywords:
- C3117
helpviewer_keywords:
- C3117
ms.assetid: dceee392-d4c7-4599-b75e-7aaac7c36fdd
ms.openlocfilehash: 66efcf95599a18e0d93ff36f0e684ad350941977
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345538"
---
# <a name="compiler-error-c3117"></a>컴파일러 오류 C3117

'%$S: 인터페이스는 하나의 기본 클래스를 하나만 사용할 수 있습니다

다중 기본 클래스에서 상속 하는 인터페이스를 선언 했습니다.

다음 샘플에서는 C3117 오류가 생성 됩니다.

```
// C3117.cpp
#include <windows.h>

[ object, uuid("00000000-0000-0000-0000-000000000001") ]
__interface I1
{
};

[ object, uuid("00000000-0000-0000-0000-000000000002") ]
__interface I2
{
};

[ object, uuid("00000000-0000-0000-0000-000000000003") ]
__interface I3 : I1, I2
{   // C3117
};
```