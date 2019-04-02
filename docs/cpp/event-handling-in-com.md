---
title: COM에서 이벤트 처리
ms.date: 11/04/2016
helpviewer_keywords:
- event handling [C++], COM
- event handling [C++], about event handling
- declaring events
- event handlers [C++], COM
- event handlers
- COM, events
- event receivers, in event handling
- event handling [C++]
- hooking events
- event receivers, name and signature matching
- event sources, in event handling
- declaring events, in COM
- declaring events, event handling in COM
ms.assetid: 6b4617d4-a58e-440c-a8a6-1ad1c715b2bb
ms.openlocfilehash: da255da9fb9ff7a652fa1af796568a8e50759dc4
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58777703"
---
# <a name="event-handling-in-com"></a>COM에서 이벤트 처리

COM 이벤트 처리를 설정한 이벤트 소스와 이벤트 수신기를 사용 하는 [event_source](../windows/attributes/event-source.md) 하 고 [event_receiver](../windows/attributes/event-receiver.md) 특성에 각각 지정 `type` = `com`. 적용되는 클래스가 COM 연결 지점을 통해 이벤트를 발생시키고 처리할 수 있도록 이러한 특성은 사용자 지정, 디스패치 및 이중 인터페이스에 대한 적절한 코드를 삽입합니다.

## <a name="declaring-events"></a>이벤트 선언

이벤트 소스 클래스를 사용 합니다 [__event](../cpp/event.md) 이벤트와 해당 인터페이스의 메서드를 선언 하는 인터페이스 선언에서 키워드입니다. 해당 인터페이스의 이벤트는 이를 인터페이스 메서드로 호출할 때 발생합니다. 이벤트 인터페이스의 메서드는 0 개 이상의 매개 변수를 가질 수 있습니다 (모든 야 *에서* 매개 변수). 반환 형식은 void 또는 모든 정수 계열 형식이 될 수 있습니다.

## <a name="defining-event-handlers"></a>이벤트 처리기 정의

이벤트 수신기 클래스에서는 처리될 이벤트와 일치하는 시그니처(반환 형식, 호출 규칙 및 인수)가 포함된 메서드인 이벤트 처리기를 정의합니다. COM 이벤트에 대 한 호출 규칙 수행 일치할 필요는 없습니다. 참조 [레이아웃 종속 COM 이벤트](#vcconeventhandlingincomanchorlayoutdependentcomevents) 아래 세부 정보에 대 한 합니다.

## <a name="hooking-event-handlers-to-events"></a>이벤트에 이벤트 처리기 후크

또한 이벤트 수신기 클래스를 사용 하 여 내장 함수 [__hook](../cpp/hook.md) 이벤트 처리기를 사용 하 여 이벤트를 연결 하 고 [__unhook](../cpp/unhook.md) 이벤트 처리기에서 이벤트를 분리 하려면. 한 이벤트 처리기에 여러 이벤트를 후크하거나 한 이벤트에 여러 이벤트 처리기를 후크할 수 있습니다.

> [!NOTE]
>  일반적으로 COM 이벤트 수신기가 이벤트 소스 인터페이스 정의에 액세스할 수 있게 만드는 두 가지 방법이 있습니다. 첫 번째 방법은 아래와 같이 공용 헤더 파일을 공유하는 것입니다. 사용 하는 두 번째 것 [#import](../preprocessor/hash-import-directive-cpp.md) 사용 하 여는 `embedded_idl` 유지 하는 특성에서 생성 된 코드를 사용 하 여 이벤트 소스 형식 라이브러리가.tlh 파일에 기록 됩니다 있도록 한정자를 가져옵니다.

## <a name="firing-events"></a>이벤트 발생

이벤트를 발생 시키는 메서드를 호출로 선언 된 인터페이스에는 **__event** 키워드 이벤트 소스 클래스입니다. 처리기가 이벤트에 후크된 경우 처리기가 호출됩니다.

### <a name="com-event-code"></a>COM 이벤트 코드

다음 예제에서는 COM 클래스에서 이벤트를 발생시키는 방법을 보여 줍니다. 예제를 컴파일 및 실행하려면 코드의 주석을 참조하십시오.

```cpp
// evh_server.h
#pragma once

[ dual, uuid("00000000-0000-0000-0000-000000000001") ]
__interface IEvents {
   [id(1)] HRESULT MyEvent([in] int value);
};

[ dual, uuid("00000000-0000-0000-0000-000000000002") ]
__interface IEventSource {
   [id(1)] HRESULT FireEvent();
};

class DECLSPEC_UUID("530DF3AD-6936-3214-A83B-27B63C7997C4") CSource;
```

서버는 다음과 같습니다.

```cpp
// evh_server.cpp
// compile with: /LD
// post-build command: Regsvr32.exe /s evh_server.dll
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>
#include "evh_server.h"

[ module(dll, name="EventSource", uuid="6E46B59E-89C3-4c15-A6D8-B8A1CEC98830") ];

[coclass, event_source(com), uuid("530DF3AD-6936-3214-A83B-27B63C7997C4")]
class CSource : public IEventSource {
public:
   __event __interface IEvents;

   HRESULT FireEvent() {
      __raise MyEvent(123);
      return S_OK;
   }
};
```

클라이언트는 다음과 같습니다.

```cpp
// evh_client.cpp
// compile with: /link /OPT:NOREF
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>
#include <stdio.h>
#include "evh_server.h"

[ module(name="EventReceiver") ];

[ event_receiver(com) ]
class CReceiver {
public:
   HRESULT MyHandler1(int nValue) {
      printf_s("MyHandler1 was called with value %d.\n", nValue);
      return S_OK;
   }

   HRESULT MyHandler2(int nValue) {
      printf_s("MyHandler2 was called with value %d.\n", nValue);
      return S_OK;
   }

   void HookEvent(IEventSource* pSource) {
      __hook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler1);
      __hook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler2);
   }

   void UnhookEvent(IEventSource* pSource) {
      __unhook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler1);
      __unhook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler2);
   }
};

int main() {
   // Create COM object
   CoInitialize(NULL);
   {
      IEventSource* pSource = 0;
      HRESULT hr = CoCreateInstance(__uuidof(CSource), NULL,         CLSCTX_ALL, __uuidof(IEventSource), (void **) &pSource);
      if (FAILED(hr)) {
         return -1;
      }

      // Create receiver and fire event
      CReceiver receiver;
      receiver.HookEvent(pSource);
      pSource->FireEvent();
      receiver.UnhookEvent(pSource);
   }
   CoUninitialize();
   return 0;
}
```

### <a name="output"></a>출력

```Output
MyHandler1 was called with value 123.
MyHandler2 was called with value 123.
```

##  <a name="vcconeventhandlingincomanchorlayoutdependentcomevents"></a> 레이아웃 종속 COM 이벤트

레이아웃 종속성은 COM 프로그래밍에만 문제가 됩니다. 네이티브 및 관리되는 이벤트 처리에서 처리기의 시그니처(반환 형식, 호출 규칙 및 인수)는 해당 이벤트와 일치해야 하지만 처리기 이름은 해당 이벤트와 일치하지 않아도 됩니다.

그러나 COM 이벤트 처리를 설정 하는 경우에 *layout_dependent* 의 매개 변수 `event_receiver` 하 **true**, 이름 및 서명 일치 적용 됩니다. 즉, 이벤트 수신기에 있는 처리기의 이름 및 시그니처가 후크되어 있는 이벤트의 이름 및 시그니처와 정확하게 일치해야 합니다.

때 *layout_dependent* 로 설정 된 **false**, 호출 규칙 및 저장소 클래스 (가상, 정적 및 등)을 혼합 실행 간에 일치 하 고 이벤트 메서드와 후크 메서드 (해당 대리자)입니다. 것이 약간 더 효율적 *layout_dependent*=**true**합니다.

예를 들어, `IEventSource`가 다음 메서드를 사용하도록 정의되어 있다고 가정합니다.

```cpp
[id(1)] HRESULT MyEvent1([in] int value);
[id(2)] HRESULT MyEvent2([in] int value);
```

이벤트 소스의 형태가 다음과 같다고 가정합니다.

```cpp
[coclass, event_source(com)]
class CSource : public IEventSource {
public:
   __event __interface IEvents;

   HRESULT FireEvent() {
      MyEvent1(123);
      MyEvent2(123);
      return S_OK;
   }
};
```

그런 다음 이벤트 수신기에서 `IEventSource`의 메서드에 후크된 처리기가 다음과 같이 해당 이름과 시그니처를 일치시켜야 합니다.

```cpp
[coclass, event_receiver(com, true)]
class CReceiver {
public:
   HRESULT MyEvent1(int nValue) {  // name and signature matches MyEvent1
      ...
   }
   HRESULT MyEvent2(E c, char* pc) {  // signature doesn't match MyEvent2
      ...
   }
   HRESULT MyHandler1(int nValue) {  // name doesn't match MyEvent1 (or 2)
      ...
   }
   void HookEvent(IEventSource* pSource) {
      __hook(IFace, pSource);  // Hooks up all name-matched events
                               // under layout_dependent = true
      __hook(&IFace::MyEvent1, pSource, &CReceive::MyEvent1);   // valid
      __hook(&IFace::MyEvent2, pSource, &CSink::MyEvent2);   // not valid
      __hook(&IFace::MyEvent1, pSource, &CSink:: MyHandler1); // not valid
   }
};
```

## <a name="see-also"></a>참고자료

[이벤트 처리](../cpp/event-handling.md)