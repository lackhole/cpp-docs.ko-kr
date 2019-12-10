---
title: 컴파일러 오류 C3706
ms.date: 11/04/2016
f1_keywords:
- C3706
helpviewer_keywords:
- C3706
ms.assetid: d20a33eb-d625-46c5-ac87-32075a590d07
ms.openlocfilehash: 810ec59a814b04349913648fb49a03eb63912cd9
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757984"
---
# <a name="compiler-error-c3706"></a>컴파일러 오류 C3706

' function ': COM 이벤트를 발생 시키려면 COM 인터페이스 여야 합니다.

COM 이벤트를 발생 시키는 데 사용 하는 이벤트 인터페이스는 COM 인터페이스 여야 합니다. 이 경우 인터페이스는 시각적 C++ 특성을 사용 하 여 정의 되거나 #import의 embedded_idl 특성이 있는 형식 라이브러리의 [#import](../../preprocessor/hash-import-directive-cpp.md) 를 사용 하 여 가져와야 합니다.

아래 샘플에 표시 된 ATL 헤더 파일의 `#include` 줄은 COM 이벤트를 사용 하는 데 필요 합니다. 이 오류를 해결 하려면 다음 특성 중 하나를 인터페이스 정의에 적용 하 여 (이벤트 인터페이스) COM 인터페이스를 `IEvents` 합니다 ( [개체](../../windows/object-cpp.md), [이중](../../windows/dual.md)또는 인터페이스 정의 [).](../../windows/dispinterface.md)

인터페이스가 MIDL에 의해 생성 된 헤더 파일에서 가져온 경우 컴파일러는 COM 인터페이스로 인식 하지 못합니다.

다음 샘플에서는 C3706를 생성 합니다.

```cpp
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
