---
title: 컴파일러 오류 C3706
ms.date: 11/04/2016
f1_keywords:
- C3706
helpviewer_keywords:
- C3706
ms.assetid: d20a33eb-d625-46c5-ac87-32075a590d07
ms.openlocfilehash: 2d474db5a4d50aed7b59e6f48fb5a3e8165f10c6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400294"
---
# <a name="compiler-error-c3706"></a>컴파일러 오류 C3706

'function': COM 이벤트를 발생 시키려면 COM 인터페이스 이어야 합니다

COM 이벤트를 발생 시키는 데 사용 하는 이벤트 인터페이스에는 COM 인터페이스 이어야 합니다. 이 경우 인터페이스 중 하나 정의 해야 시각적 개체를 사용 하 여 C++ 특성 또는 사용 하 여 가져온 [#import](../../preprocessor/hash-import-directive-cpp.md) #import의 embedded_idl 특성을 사용 하 여 형식 라이브러리에서.

`#include` 아래 샘플에 표시 된 ATL 헤더 파일의 줄은 COM 이벤트를 사용 하기 위해 필요 합니다. 이 오류를 해결 하려면 `IEvents` (이벤트 인터페이스) 인터페이스 정의를 다음 중 하나를 적용 하 여 COM 인터페이스 특성: [개체](../../windows/object-cpp.md)하십시오 [이중](../../windows/dual.md), 또는 [ dispinterface](../../windows/dispinterface.md)합니다.

MIDL에서 생성 된 헤더 파일에서 인터페이스 인 경우 컴파일러가 인식 되지 않습니다 COM 인터페이스입니다.

다음 샘플에서는 C3706 오류가 생성 됩니다.

```
// C3706.cpp
// compile with: /c
// C3706 expected
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>
#include <atlctl.h>

[module(dll, name="idid", uuid="12341234-1234-1234-1234-123412341234")];

// Uncomment the following line to resolve.
// [object, uuid="12341234-1234-1234-1234-123412341237"]
__interface IEvents : IUnknown {
   HRESULT event1(/*[in]*/ int i);   // uncomment [in]
};

[dual, uuid="12341234-1234-1234-1234-123412341235"]
__interface IBase {
   HRESULT fireEvents();
};

[coclass, event_source(com), uuid="12341234-1234-1234-1234-123412341236"]
class CEventSrc : public IBase {
   public:
   __event __interface IEvents;

   HRESULT fireEvents() {
      HRESULT hr = IEvents_event1(123);
      return hr;
   }
};
```