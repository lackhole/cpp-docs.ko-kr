---
title: 이벤트 처리
ms.date: 11/04/2016
helpviewer_keywords:
- attributes [C++], event handling
- intrinsic functions [C++], event handling
- event handling [C++], Visual C++
ms.assetid: 82de3f9a-2d88-470c-9527-8a5b54c8ced4
ms.openlocfilehash: 4c6701f04544b336de97196e8b65f4d0cd4be296
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58769474"
---
# <a name="event-handling"></a>이벤트 처리

이벤트 처리는 주로 COM 클래스(일반적으로 COM 개체를 구현하는 C++클래스로서 일반적으로 ATL 클래스 또는 [coclass](../windows/coclass.md) 특성(attribute)을 사용합니다)에서 지원됩니다. 자세한 내용은 [COM에서 이벤트 처리](../cpp/event-handling-in-com.md) 를 참조합니다.

COM 개체를 구현하지 않는 C++ 클래스인 네이티브 C++ 클래스도 이벤트 처리가 가능하지만 이는 더 이상 지원되지 않으며 향후 릴리스에서 제거될 수 있습니다.  자세한 내용은 [네이티브 C++에서 이벤트 처리](../cpp/event-handling-in-native-cpp.md)를 참조합니다.

이벤트 처리는 단일 및 다중 스레드 사용을 지원하며 동시 다중 스레드 액세스로부터 데이터를 보호합니다. 이벤트 처리를 사용하면 이벤트를 주고 받는 클래스에서 하위 클래스를 파생시키고 파생된 클래스에서 확장된 이벤트를 보내고 받을 수 있습니다.

Visual C++에는 이벤트와 이벤트 처리기를 선언하는 특성과 키워드가 있습니다. CLR 프로그램과 네이티브 C++ 프로그램에서 이벤트 특성과 키워드를 사용할 수 있습니다.

|항목|설명|
|-----------|-----------------|
|[event_source](../windows/attributes/event-source.md)|이벤트 소스를 만듭니다.|
|[event_receiver](../windows/attributes/event-receiver.md)|이벤트 수신기(싱크)를 만듭니다.|
|[__event](../cpp/event.md)|이벤트를 선언합니다.|
|[__raise](../cpp/raise.md)|이벤트의 호출 사이트를 강조합니다.|
|[__hook](../cpp/hook.md)|처리기 메서드를 이벤트와 연결합니다.|
|[__unhook](../cpp/unhook.md)|처리기 메서드를 이벤트에서 분리합니다.|

## <a name="see-also"></a>참고자료

[C++ 언어 참조](../cpp/cpp-language-reference.md)<br/>
[키워드](../cpp/keywords-cpp.md)