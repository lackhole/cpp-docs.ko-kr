---
title: 컴파일러 오류 C3705
ms.date: 11/04/2016
f1_keywords:
- C3705
helpviewer_keywords:
- C3705
ms.assetid: 8361017d-5782-4214-a9d7-e9825fd29bc8
ms.openlocfilehash: 8a1a5a7c3c54742f6952f6885a70fd5c1dcf6e0f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62227072"
---
# <a name="compiler-error-c3705"></a>컴파일러 오류 C3705

'function': 이벤트 인터페이스를 찾을 수 없습니다.

COM 이벤트를 사용 하는 이벤트 인터페이스를 정의 해야 합니다. `#include` 아래 샘플에 표시 된 ATL 헤더 파일의 줄은 COM 이벤트를 사용 하기 위해 필요 합니다. 이 오류를 해결 하려면 정의 주석 처리 제거를 `IEvents` 샘플 코드에서는 인터페이스입니다.

다음 샘플에서는 C3705 오류가 생성 됩니다.

```
// C3705.cpp
// compile with: /c
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>
#include <atlctl.h>

[module(dll, name="idid", uuid="12341234-1234-1234-1234-123412341234")];

// Uncomment the following 4 lines to resolve.
// [object, uuid("00000000-0000-0000-0000-000000000003")]
// __interface IEvents : IUnknown {
//    HRESULT event1([in] int i);
// };

[dual, uuid("00000000-0000-0000-0000-000000000001")]
__interface IBase {
   HRESULT fireEvents();
};

[coclass, event_source(com), uuid("00000000-0000-0000-0000-000000000002")]
class CEventSrc : public IBase {
public:
   __event __interface IEvents;   // C3705 uncomment IEvents to resolve
   HRESULT fireEvents() {
      HRESULT hr = IEvents_event1(123);
      return hr;
   }
};
```