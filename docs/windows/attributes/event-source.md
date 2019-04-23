---
title: event_source (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.event_source
helpviewer_keywords:
- event handling, attributes
- event logs, event source
- event sources, creating
- event_source attribute
- event sources
- event handling, creating event source
ms.assetid: 0983e36a-6127-4fbb-8a22-8dfec6564c16
ms.openlocfilehash: 81eba3c032a3556d1c69ad02652455ebc07ab6be
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59035934"
---
# <a name="eventsource"></a>event_source

이벤트 소스를 만듭니다.

## <a name="syntax"></a>구문

```cpp
[ event_source(type, optimize=[speed | size], decorate=[true | false]) ]
```

### <a name="parameters"></a>매개 변수

*type*<br/>
다음 값 중 하나의 열거형:

- `native` - 관리되지 않는 C/C++ 코드용(관리되지 않는 클래스에 대한 기본값).

- `com` - COM 코드용. 사용 해야 합니다 `coclass` 때 `type` = `com`합니다. 이 값을 사용하려면 다음 헤더 파일을 포함해야 합니다.

    ```cpp
    #define _ATL_ATTRIBUTES
    #include <atlbase.h>
    #include <atlcom.h>
    ```

*optimize*<br/>
때 *형식* 됩니다 `native`를 지정할 수 있습니다 `optimize=size`는 4 바이트의 저장소 (minimum)가 모든 이벤트에 대 한 클래스에서 나타내기 위해 또는 `optimize=speed` (기본값) 4 임을 나타내려면 * (이벤트의 수) 바이트의 저장소입니다.

*decorate*<br/>
때 *형식* 됩니다 `native`를 지정할 수 있습니다 `decorate=false`병합 된 (.mrg) 파일에 확장된 된 이름이 바깥쪽 클래스 이름을 포함 하지 않아야 함을 나타내기 위해. [/Fx](../../build/reference/fx-merge-injected-code.md) 로는 .mrg 파일을 생성할 수 있습니다. `decorate=false`를 기본값인 기본값인 병합된 된 파일의 정규화 된 형식 이름이 생성 됩니다.

## <a name="remarks"></a>설명

**event_source** C++ 특성은, 이 특성이 적용되는 클래스 또는 구조가 이벤트 소스가 될 것임을 지정합니다.

**event_source** 는 [event_receiver](event-receiver.md) 특성 및 [__event](../../cpp/event.md) 키워드와 함께 사용됩니다. 사용 하 여 `event_receiver` 이벤트 수신기를 만들려고 합니다. 사용 하 여 **__event** 메서드 내의 이벤트로 이러한 메서드를 지정 하는 이벤트 소스입니다.

> [!NOTE]
> 템플릿 기반 클래스 또는 구조체에 event를 포함시킬 수 없습니다.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|**class**, **struct**|
|**반복 가능**|아니요|
|**필수 특성**|**coclass** 때 `type`=`com`|
|**잘못된 특성**|없음|

자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[컴파일러 특성](compiler-attributes.md)<br/>
[event_receiver](event-receiver.md)<br/>
[__event](../../cpp/event.md)<br/>
[__hook](../../cpp/hook.md)<br/>
[__unhook](../../cpp/unhook.md)<br/>
[클래스 특성](class-attributes.md)