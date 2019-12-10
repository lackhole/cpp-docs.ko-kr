---
title: 컴파일러 경고(수준 4) C4681
ms.date: 11/04/2016
f1_keywords:
- C4681
helpviewer_keywords:
- C4681
ms.assetid: a4e6d85f-3e21-4b45-a551-c23d3c554d3f
ms.openlocfilehash: 543034c9b5369b5ceac082ebc4133faf29397c8b
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990381"
---
# <a name="compiler-warning-level-4-c4681"></a>컴파일러 경고(수준 4) C4681

'class': coclass가 이벤트 소스인 기본 인터페이스를 지정하지 않습니다.

클래스에 대한 [소스](../../windows/source-cpp.md) 인터페이스를 지정하지 않았습니다.

다음 샘플에서는 C4681을 생성합니다.

```cpp
// C4681.cpp
// compile with: /W4 /c
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>

[module(name="test")];

[dual, uuid("00000000-0000-0000-0000-000000000000")]
__interface IEvent { [id(3)] HRESULT myEvent(); };

[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface ISource { HRESULT Fire(); };

[ coclass,
  source(IEvent),
  default(ISource),
  // Uncomment the following line to resolve.
  // default(IEvent),
  uuid("00000000-0000-0000-0000-000000000002")
]
struct CSource : ISource {   // C4681
   HRESULT Fire() { return 0; }
};
```
