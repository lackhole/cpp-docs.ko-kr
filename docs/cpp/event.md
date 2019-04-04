---
title: __event
ms.date: 11/04/2016
f1_keywords:
- __event_cpp
- __event
helpviewer_keywords:
- __event keyword [C++]
- events [C++], __event
ms.assetid: d3019b3e-722e-48df-8536-c05878461f9e
ms.openlocfilehash: 3a837e30d3cd66f7caa9b44971f432e00b0917ae
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58778262"
---
# <a name="event"></a>__event

이벤트를 선언합니다.

## <a name="syntax"></a>구문

```
__event method-declarator;
__event __interface interface-specifier;
__event member-declarator;
```

## <a name="remarks"></a>설명

키워드 **__event**는 메서드 선언, 인터페이스 선언 또는 데이터 멤버 선언에 사용할 수 있습니다. 그러나 **__event**를 중첩된 클래스의 맴버 한정자로 사용할 수는 없습니다.

이벤트를 주고 받는 주체가 네이티브C++, COM 또는 매니지드(.NET Framework)인가에 따라 다음 구문을 이벤트로 사용할 수 있습니다.

|네이티브 C++|COM|매니지드(.NET Framework)|
|------------------|---------|--------------------------------|
|메서드|—|메서드|
|—|interface(인터페이스)|—|
|—|—|데이터 멤버|

이벤트 수신기에서 [__hook](../cpp/hook.md)을 사용하여 핸들러 메서드를 이벤트 메서드에 연결합니다. **__event** 키워드로 이벤트를 만든 후 이벤트가 호출되면, 그 이벤트에 후킹된 모든 이벤트 핸들러가 호출됩니다.

**__event** 메서드 선언은 정의될 수 없습니다. 정의가 암시적으로 생성되므로 이벤트 메서드는 일반 메소드처럼 호출됩니다.

> [!NOTE]
>  템플릿 기반 클래스 또는 구조체는 event를 포함할 수 없습니다.

## <a name="native-events"></a>네이티브 이벤트

네이티브 이벤트는 메서드입니다. 반환 형식은 일반적으로 HRESULT 또는 **void**이지만 **열거형**을 포함한 모든 정수 형식이 될 수 있습니다. 이벤트가 정수 계열 반환 형식을 사용하는 경우 이벤트 처리기가 0이 아닌 값을 반환할 때 오류 조건이 정의됩니다. 이 경우 발생하는 이벤트는 다른 대리자를 호출합니다.

```cpp
// Examples of native C++ events:
__event void OnDblClick();
__event HRESULT OnClick(int* b, char* s);
```

[네이티브 C++에서 이벤트 처리](../cpp/event-handling-in-native-cpp.md)에 대한 샘플 코드를 참조합니다.

## <a name="com-events"></a>COM 이벤트

COM 이벤트는 인터페이스입니다. 이벤트 소스 인터페이스의 메서드 매개 변수 여야 합니다 *에* 매개 변수 (그러나 엄격 하 게 적용 되지) 때문에 *out* 매개 변수는 멀티 캐스팅 시 유용 하지 않습니다. *out* 매개 변수를 사용하는 경우 1단계 수준의 경고가 발생됩니다

반환 유형은 일반적으로 HRESULT 또는 **void**이지만 **열거형**을 포함한 모든 정수 유형이 될 수 있습니다. 이벤트가 정수 계열 반환 형식을 사용하고 이벤트 처리기가 0이 아닌 값을 반환하는 경우는 오류가 발생하며 이 경우 발생하는 이벤트가 다른 대리자에 대한 호출을 중단합니다. 컴파일러는 IDL을 생성하여 자동으로 이벤트 [소스](../windows/attributes/source-cpp.md) 인터페이스를 표시 합니다.

[__interface](../cpp/interface.md) 키워드는 COM 이벤트 소스에 대해 **__event**를 사용한 후 반드시 필요합니다.

```cpp
// Example of a COM event:
__event __interface IEvent1;
```

샘플 코드는 [COM에서 이벤트 처리](../cpp/event-handling-in-com.md)를 참조하십시오.

## <a name="managed-events"></a>매니지드 이벤트

새 구문의 이벤트 코딩에 대한 자세한 내용은 [이벤트](../extensions/event-cpp-component-extensions.md)를 참조하세요.

매니지드 이벤트는 데이터 멤버 또는 메서드입니다. 이벤트를 사용할 경우 대리자의 [공용 언어 사양](/dotnet/standard/language-independence-and-language-independent-components) 반환 형식을 준수해야 합니다 이벤트 처리기의 반환 형식은 대리자의 반환 형식과 일치해야 합니다. 대리자에 대 한 자세한 내용은 참조 하세요. [대리자 및 이벤트](../dotnet/delegates-and-events.md)를 참조합니다. 매니지드 이벤트가 데이터 멤버인 경우 그 형식은 대리자에 대한 포인터여야 합니다.

.NET Framework에서 데이터 멤버를 메서드(즉, 해당 대리자의 `Invoke` 메서드)인 것처럼 처리할 수 있습니다. 매니지드 이벤트 데이터 멤버를 선언하기 위한 대리자 형식을 미리 정의해야 합니다. 반면에 매니지드 이벤트 메서드는 해당 관리되는 대리자가 정의되지 않은 경우 이를 암시적으로 정의합니다. 예를 들어 `OnClick`과 같은 이벤트 값을 다음과 같이 이벤트로 선언할 수 있습니다.

```cpp
// Examples of managed events:
__event ClickEventHandler* OnClick;  // data member as event
__event void OnClick(String* s);  // method as event
```

매니지드 이벤트를 암시적으로 선언할 때 이벤트 처리기가 추가되거나 제거되는 경우 호출될 add 및 remove 접근자를 지정할 수 있습니다. 클래스 외부에서 이벤트를 호출하는(발생시키는) 메서드를 정의할 수도 있습니다.

## <a name="example-native-events"></a>예제: 네이티브 이벤트

```cpp
// EventHandling_Native_Event.cpp
// compile with: /c
[event_source(native)]
class CSource {
public:
   __event void MyEvent(int nValue);
};
```

## <a name="example-com-events"></a>예제: COM 이벤트

```cpp
// EventHandling_COM_Event.cpp
// compile with: /c
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>

[ module(dll, name="EventSource", uuid="6E46B59E-89C3-4c15-A6D8-B8A1CEC98830") ];

[ dual, uuid("00000000-0000-0000-0000-000000000002") ]
__interface IEventSource {
   [id(1)] HRESULT MyEvent();
};
[ coclass, uuid("00000000-0000-0000-0000-000000000003"),  event_source(com) ]
class CSource : public IEventSource {
public:
   __event __interface IEventSource;
   HRESULT FireEvent() {
      __raise MyEvent();
      return S_OK;
   }
};
```

## <a name="see-also"></a>참고자료

[키워드](../cpp/keywords-cpp.md)<br/>
[이벤트 처리](../cpp/event-handling.md)<br/>
[event_source](../windows/attributes/event-source.md)<br/>
[event_receiver](../windows/attributes/event-receiver.md)<br/>
[__hook](../cpp/hook.md)<br/>
[__unhook](../cpp/unhook.md)<br/>
[__raise](../cpp/raise.md)