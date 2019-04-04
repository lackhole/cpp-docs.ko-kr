---
title: __hook
ms.date: 11/04/2016
f1_keywords:
- __hook_cpp
helpviewer_keywords:
- __hook keyword [C++]
- event handlers [C++], connecting events to
ms.assetid: f4cabb10-d293-4c0e-a1d2-4745ef9cc22c
ms.openlocfilehash: c4887d85e01344c171fb0fdfe957f2d8a669ff6a
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58771671"
---
# <a name="hook"></a>__hook

처리기 메서드를 이벤트와 연결합니다.

## <a name="syntax"></a>구문

```
long __hook(
    &SourceClass::EventMethod,
    source,
    &ReceiverClass::HandlerMethod
    [, receiver = this]
);
long __hook(
    interface,
    source
);
```

### <a name="parameters"></a>매개 변수

*&SourceClass::EventMethod*<br/>
이벤트 처리기 메서드를 후크할 이벤트 메서드에 대한 포인터입니다.

- 네이티브 c + + 이벤트: *SourceClass* 는 이벤트 소스 클래스와 *EventMethod* 이벤트입니다.

- COM 이벤트: *SourceClass* 는 이벤트 소스 인터페이스 및 *EventMethod* 해당 메서드 중 하나입니다.

- 관리 되는 이벤트: *SourceClass* 는 이벤트 소스 클래스와 *EventMethod* 이벤트입니다.

*interface*<br/>
인터페이스 이름을 후크 되 *받는 사람*는 COM 이벤트 수신기에 대해서만 합니다 *layout_dependent* 의 매개 변수를 [event_receiver](../windows/attributes/event-receiver.md) 특성이 **true**합니다.

*source*<br/>
이벤트 소스의 인스턴스에 대한 포인터입니다. 코드에 따라 `type` 에 지정 된 `event_receiver`를 *원본* 다음 중 하나일 수 있습니다.

- 네이티브 이벤트 소스 개체 포인터입니다.

- `IUnknown`-기반 포인터 (COM 소스)입니다.

- 관리되는 이벤트의 관리되는 개체 포인터입니다.

*&ReceiverClass::HandlerMethod*<br/>
이벤트에 후크될 이벤트 처리기 메서드에 대한 포인터입니다. 클래스 또는 동일한;에 대 한 참조의 메서드로 처리기 지정 클래스 이름을 지정 하지 않으면 **__hook** 는 호출 되는 클래스를 가정 합니다.

- 네이티브 c + + 이벤트: *ReceiverClass* 는 이벤트 수신기 클래스 및 `HandlerMethod` 처리기입니다.

- COM 이벤트: *ReceiverClass* 는 이벤트 수신기 인터페이스 및 `HandlerMethod` 처리기 중 하나입니다.

- 관리 되는 이벤트: *ReceiverClass* 는 이벤트 수신기 클래스 및 `HandlerMethod` 처리기입니다.

*receiver*<br/>
(선택 사항) 이벤트 수신기 클래스의 인스턴스에 대 한 포인터입니다. 수신기를 지정 하지 않으면 경우 기본값은 수신기 클래스 또는 구조체 **__hook** 라고 합니다.

## <a name="usage"></a>사용법

이벤트 수신기 클래스 외부의 main을 포함하여 모든 함수 범위에서 사용할 수 있습니다.

## <a name="remarks"></a>설명

내장 함수를 사용 하 여 **__hook** 연결 하거나 이벤트 메서드에서 처리기 메서드를 후크 할 이벤트 수신기에서. 이렇게 하면 소스에서 지정된 이벤트를 발생시킬 때 지정된 처리기가 호출됩니다. 여러 처리기를 단일 이벤트에 후크하거나 여러 이벤트를 단일 처리기에 후크할 수 있습니다.

두 가지 **__hook**합니다. COM 이벤트 수신기는 특히 대부분의 경우에서 첫 번째 (인수 4) 형태를 사용할 수 있습니다 합니다 *layout_dependent* 의 매개 변수를 [event_receiver](../windows/attributes/event-receiver.md) 특성은 **false** .

이러한 경우 메서드 중 하나에서 이벤트를 발생시키기 전에 인터페이스에서 모든 메서드를 후크할 필요는 없습니다. 이벤트를 처리하는 메서드만 후크해야 합니다. 두 번째 (인수 2 개) 형식으로 사용할 수 있습니다 **__hook** COM 이벤트 수신기는 동안만 *layout_dependent* **= true**합니다.

**__hook** long 값을 반환 합니다. 0이 아닌 반환 값은 오류가 발생했음을 나타냅니다(관리되는 이벤트가 예외를 throw함).

컴파일러는 이벤트가 있는지 확인하고 이벤트 시그니처가 대리자 시그니처와 일치하는지 확인합니다.

COM 이벤트의 경우를 제외 하 고 **__hook** 하 고 **__unhook** 이벤트 수신기가 외부를 호출할 수 있습니다.

사용 하는 대신 **__hook** + = 연산자를 사용 하는 것입니다.

관리 되는 새 구문의 이벤트 코딩에 대 한 내용은 참조 하세요 [이벤트](../extensions/event-cpp-component-extensions.md)합니다.

> [!NOTE]
> 템플릿 기반 클래스 또는 구조체에 event를 포함시킬 수 없습니다.

## <a name="example"></a>예제

참조 [네이티브 c + +에서 이벤트 처리](../cpp/event-handling-in-native-cpp.md) 하 고 [COM에서 이벤트 처리](../cpp/event-handling-in-com.md) 샘플에 대 한 합니다.

## <a name="see-also"></a>참고자료

[키워드](../cpp/keywords-cpp.md)<br/>
[이벤트 처리](../cpp/event-handling.md)<br/>
[event_source](../windows/attributes/event-source.md)<br/>
[event_receiver](../windows/attributes/event-receiver.md)<br/>
[__unhook](../cpp/unhook.md)<br/>
[__raise](../cpp/raise.md)<br/>
