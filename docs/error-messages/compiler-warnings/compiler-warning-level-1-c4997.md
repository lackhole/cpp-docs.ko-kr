---
title: 컴파일러 경고(수준 1) C4997
ms.date: 11/04/2016
f1_keywords:
- C4997
helpviewer_keywords:
- C4997
ms.assetid: d39678fd-0c1a-4104-8a45-9e3f20de0407
ms.openlocfilehash: 298653e7ebed272db1baa11514ac5bff27944b3c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384116"
---
# <a name="compiler-warning-level-1-c4997"></a>컴파일러 경고(수준 1) C4997

'class': coclass가 COM 인터페이스 또는 의사(pseudo) 인터페이스를 구현하지 않습니다.

[coclass](../../windows/coclass.md) 특성으로 표시된 클래스가 인터페이스를 구현하지 않았습니다.

다음 샘플에서는 C4997을 생성합니다.

```
// C4997.cpp
// compile with: /WX
// to resolve this C4997, uncomment all code
#include <objbase.h>

[ object ]
__interface I {
   HRESULT func();
};

[ coclass ]
struct C /*: I*/ {
   /*
   HRESULT func() {
      return S_OK;
   }
   */
};   // C4997
```