---
title: event_receiver (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.event_receiver
helpviewer_keywords:
- event_receiver attribute
- event receivers
- events [C++], event receivers (sinks)
- event handling [C++], attributes
- event handling [C++], creating receiver
- event sinks, creating
- event sinks
ms.assetid: bf8fe770-3ea2-4128-b46b-166222ee4097
ms.openlocfilehash: 81a3ec88c336ddeb550f133e657854b3b6f89d96
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409638"
---
# <a name="eventreceiver"></a>event_receiver

이벤트 수신기(싱크)를 만듭니다.

## <a name="syntax"></a>구문

```cpp
[ event_receiver(type
   [, layout_dependent=false]) ]
```

### <a name="parameters"></a>매개 변수

*type*<br/>
다음 값 중 하나의 열거형:

- `native` 관리 되지 않는 c /C++ 코드 (기본 클래스에 대 한 기본값).

- `com` - COM 코드용. 이 값을 사용하려면 다음 헤더 파일을 포함해야 합니다.

    ```cpp
    #define _ATL_ATTRIBUTES
    #include <atlbase.h>
    #include <atlcom.h>
    ```

*layout_dependent*<br/>
지정할 *layout_dependent* 경우에만 `type` = **com**합니다. *layout_dependent* 는 부울입니다.

- **true** 수신기 일치 해야 하는 후크 되어 이벤트 소스 이벤트에서 대리자의 시그니처와 의미 합니다. 이벤트 수신기 처리기 이름은 관련 이벤트 소스 인터페이스에 지정 된 이름과 일치 해야 합니다. 사용 해야 합니다 `coclass` 때 *layout_dependent* 됩니다 **true**합니다. 것이 약간 더 효율적 지정할 **true**합니다.

- **false** (기본값) 즉, 호출 규칙 및 저장소 클래스 (가상, 정적, 등)를 이벤트 메서드와 처리기;와 일치 하지 않아도 또는 처리기 이름은 필요가 이벤트 소스 인터페이스 메서드 이름과 일치 합니다.

## <a name="remarks"></a>설명

합니다 **event_receiver** C++ 특성 지정 클래스 또는 구조체 적용 되는 시각적 개체를 사용 하 여 이벤트 수신기를 C++ 통합된 이벤트 모델.

**event_receiver** 사용 되는 [event_source](event-source.md) 특성 및 [__hook](../../cpp/hook.md) 하 고 [__unhook](../../cpp/unhook.md) 키워드. 사용 하 여 `event_source` 이벤트 원본을 만들 수 있습니다. 사용 하 여 **__hook** 이벤트 원본의 이벤트에 이벤트 수신기 메서드 ("후크")에 연결할 이벤트 수신기의 메서드 내에서. 사용 하 여 **__unhook** 을 분리 합니다.

*layout_dependent* COM 이벤트 수신기만 지정 됩니다 (`type`=**com**). 에 대 한 기본 *layout_dependent* 됩니다 **false**합니다.

> [!NOTE]
> 템플릿 기반 클래스 또는 구조체에 event를 포함시킬 수 없습니다.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|**class**, **struct**|
|**반복 가능**|아니요|
|**필수 특성**|`coclass` 때 *layout_dependent*=**true**|
|**잘못된 특성**|없음|

자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[컴파일러 특성](compiler-attributes.md)<br/>
[event_source](event-source.md)<br/>
[__event](../../cpp/event.md)<br/>
[__hook](../../cpp/hook.md)<br/>
[__unhook](../../cpp/unhook.md)<br/>
[클래스 특성](class-attributes.md)