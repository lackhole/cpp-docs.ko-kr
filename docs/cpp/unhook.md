---
title: __unhook
ms.date: 11/04/2016
f1_keywords:
- __unhook
- __unhook_cpp
helpviewer_keywords:
- event handlers [C++], dissociating events
- __unhook keyword [C++]
ms.assetid: 953a14f3-5199-459d-81e5-fcf015a19878
ms.openlocfilehash: e8f42c35024995c026ae10fc7f0ab3db77d1e5dc
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58769526"
---
# <a name="unhook"></a>__unhook

처리기 메서드를 이벤트에서 분리합니다.

## <a name="syntax"></a>구문

```cpp
long  __unhook(
   &SourceClass::EventMethod,
   source,
   &ReceiverClass::HandlerMethod
   [, receiver = this]
);
long  __unhook(
   interface,
   source
);
long  __unhook(
   source
);
```

#### <a name="parameters"></a>매개 변수

**&** *SourceClass* `::` *EventMethod* 올를 언 후크 할 이벤트 처리기 메서드에서 이벤트 메서드에 대 한 포인터:

- 네이티브 C++ 이벤트: *SourceClass* 는 이벤트 소스 클래스와 *EventMethod* 이벤트입니다.

- COM 이벤트: *SourceClass* 는 이벤트 소스 인터페이스 및 *EventMethod* 해당 메서드 중 하나입니다.

- 관리 되는 이벤트: *SourceClass* 는 이벤트 소스 클래스와 *EventMethod* 이벤트입니다.

*interface*<br/>
연결 되 고 인터페이스 이름을 *받는 사람*는 COM 이벤트 수신기에 대해서만 합니다 *layout_dependent* 의 매개 변수는 [event_receiver](../windows/attributes/event-receiver.md) 특성이 **true**합니다.

*source*<br/>
이벤트 소스의 인스턴스에 대한 포인터입니다. 코드에 따라 `type` 에 지정 된 `event_receiver`를 *원본* 다음 중 하나일 수 있습니다.

- 네이티브 이벤트 소스 개체 포인터입니다.

- `IUnknown`-기반 포인터 (COM 소스)입니다.

- 관리되는 이벤트의 관리되는 개체 포인터입니다.

**&** *ReceiverClass* `::` `HandlerMethod` 이벤트에서 언 후크 될 이벤트 처리기 메서드에 대 한 포인터입니다. 클래스 또는 동일한;에 대 한 참조의 메서드로 처리기 지정 클래스 이름을 지정 하지 않으면 **__unhook** 는 호출 되는 클래스를 가정 합니다.

- 네이티브 C++ 이벤트: *ReceiverClass* 는 이벤트 수신기 클래스 및 `HandlerMethod` 처리기입니다.

- COM 이벤트: *ReceiverClass* 는 이벤트 수신기 인터페이스 및 `HandlerMethod` 처리기 중 하나입니다.

- 관리 되는 이벤트: *ReceiverClass* 는 이벤트 수신기 클래스 및 `HandlerMethod` 처리기입니다.

*받는 사람*(선택 사항) 이벤트 수신기 클래스의 인스턴스에 대 한 포인터입니다. 수신기를 지정 하지 않으면 경우 기본값은 수신기 클래스 또는 구조체 **__unhook** 라고 합니다.

## <a name="usage"></a>사용법

이벤트 수신기 클래스 외부의 main을 포함하여 모든 함수 범위에서 사용할 수 있습니다.

## <a name="remarks"></a>설명

내장 함수를 사용 하 여 **__unhook** 분리 하거나 "언 후크" 이벤트 메서드에서 처리기 메서드를 이벤트 수신기에서.

세 가지 **__unhook**합니다. 대부분 첫 번째(인수 4개) 형식을 사용할 수 있습니다. 두 번째 (인수 2 개) 형식으로 사용할 수 있습니다 **__unhook** 전체 이벤트 인터페이스를 언 후크합니다 COM 이벤트 수신기;에 대해서만 합니다. 세 번째(인수 1개) 형식을 사용하여 지정된 소스에서 모든 대리자를 언후크할 수 있습니다.

0이 아닌 반환 값은 예외가 발생했음을 나타냅니다(관리되는 이벤트가 예외를 throw함).

호출 하는 경우 **__unhook** 해당 이벤트 및 아직 후크 되지는 이벤트 처리기에서 영향을 주지 것입니다.

컴파일할 때 컴파일러는 이벤트가 있는지 확인하고 지정된 처리기를 사용하여 매개 변수 형식을 검사합니다.

COM 이벤트의 경우를 제외 하 고 **__hook** 하 고 **__unhook** 이벤트 수신기가 외부를 호출할 수 있습니다.

사용 하는 대신 **__unhook** -= 연산자를 사용 하는 것입니다.

관리 되는 새 구문의 이벤트 코딩에 대 한 내용은 참조 하세요 [이벤트](../extensions/event-cpp-component-extensions.md)합니다.

> [!NOTE]
>  템플릿 기반 클래스 또는 구조체에 event를 포함시킬 수 없습니다.

## <a name="example"></a>예제

참조 [네이티브에서 이벤트 처리 C++ ](../cpp/event-handling-in-native-cpp.md) 하 고 [COM에서 이벤트 처리](../cpp/event-handling-in-com.md) 샘플에 대 한 합니다.

## <a name="see-also"></a>참고자료

[C++ 키워드](../cpp/keywords-cpp.md)<br/>
[event_source](../windows/attributes/event-source.md)<br/>
[event_receiver](../windows/attributes/event-receiver.md)<br/>
[__event](../cpp/event.md)<br/>
[__hook](../cpp/hook.md)<br/>
[__raise](../cpp/raise.md)