---
title: 컴파일러 경고(수준 1) C4683
ms.date: 08/27/2018
f1_keywords:
- C4683
helpviewer_keywords:
- C4683
ms.assetid: e6e77364-dba1-46dd-ae1d-03da23070bce
ms.openlocfilehash: 264753ece6cbabded21df8e6b9dbb463f811e8a2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62375160"
---
# <a name="compiler-warning-level-1-c4683"></a>컴파일러 경고(수준 1) C4683

> '*함수*': 이벤트 소스에 'out'-여러 이벤트 처리기를 후크 하는 경우 주의 해야 합니다; 매개 변수

## <a name="remarks"></a>설명

둘 이상의 이벤트 싱크를 COM 이벤트 원본에 수신 하는 경우에 out 매개 변수 값을 무시할 수 있습니다.

다음과 같은 상황에서 메모리 누수가 발생할 수 있는 고려해 야 합니다.

1. 메서드는 내부적으로 할당 된 예를 들어 BSTR out 매개 변수가 하는 경우 *입니다.

2. 이벤트 처리기를 여러 개 있으면 (멀티 캐스트 이벤트입니다).

Out 매개 변수를 둘 이상의 처리기에 의해 설정 되지만 호출 사이트에만 처리기가 반환 하는 마지막 것입니다는 누수에 대 한 이유가 있습니다.

## <a name="example"></a>예제

다음 샘플 C4683 생성 및이 해결 하는 방법을 보여 줍니다.

```cpp
// C4683.cpp
// compile with: /W1 /LD
#define _ATL_ATTRIBUTES 1
#include "atlbase.h"
#include "atlcom.h"

[ module(name="xx") ];

[ object ]
__interface I {
   HRESULT f([out] int* pi);
   // try the following line instead
   // HRESULT f(int* pi);
};

[ coclass, event_source(com) ]
struct E {
   __event __interface I;   // C4683
};
```