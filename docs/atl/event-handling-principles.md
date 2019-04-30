---
title: 이벤트 처리 (ATL) 원칙
ms.date: 11/04/2016
helpviewer_keywords:
- event handling, implementing
- event handling, advising event sources
- interfaces, event and event sink
- dual interfaces, event interfaces
- event handling, dual event interfaces
ms.assetid: d17ca7cb-54f2-4658-ab8b-b721ac56801d
ms.openlocfilehash: b882a1d356a431f75be1feb6e7bd997abed41c33
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62234773"
---
# <a name="event-handling-principles"></a>이벤트 처리 원리

모든 이벤트 처리에 공통적으로 적용는 세 가지 단계가 있습니다. 해야 합니다.

- 개체에서 이벤트 인터페이스를 구현 합니다.

- 개체 이벤트를 수신 하려는 이벤트 소스는 것이 좋습니다.

- 개체는 더 이상 이벤트를 수신 해야 할 때 이벤트 소스를 unadvise입니다.

이벤트 인터페이스를 구현 하는 방법은 해당 형식에 따라 달라 집니다. 이벤트 인터페이스는 vtable, 이중, 또는 dispinterface를 수 있습니다. 인터페이스를 정의 하는 이벤트 소스 디자이너에 달려 가 해당 인터페이스를 구현할 수 있습니다.

> [!NOTE]
>  이벤트 인터페이스를 이중 수 없는 기술 없는 이유가 있더라도 이중 사용 하지 않도록 하는 좋은 디자인 이유 중는 여러 가지가 있습니다. 그러나 이것은 이벤트의 디자이너/구현 자가 결정 *원본*합니다. 이벤트의 관점에서 작업 이므로 `sink`를 선택할 때는 없을 수 있습니다 가능성에 대 한 허용 하지만 이중 인터페이스를 구현 하도록 해야 합니다. 이중 인터페이스에 대 한 자세한 내용은 참조 하세요. [이중 인터페이스 및 ATL](../atl/dual-interfaces-and-atl.md)합니다.

싱 수 나눌 수 3 단계:

- 원본 개체를 쿼리할 [IConnectionPointContainer](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpointcontainer)합니다.

- 호출 [IConnectionPointContainer::FindConnectionPoint](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpointcontainer-findconnectionpoint) 관심 있는 이벤트 인터페이스의 IID를 전달 합니다. 성공 하면이 경우 반환 됩니다 합니다 [IConnectionPoint](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpoint) 연결 지점 개체의 인터페이스입니다.

- 호출 [IConnectionPoint::Advise](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpoint-advise) 전달 된 `IUnknown` 이벤트 싱크의 합니다. 성공 하면이 경우 반환 됩니다는 `DWORD` 연결을 나타내는 쿠키입니다.

이벤트 수신에 관심을 가져를 성공적으로 등록 되 면 소스 개체에 의해 발생 한 이벤트에 따라 개체의 이벤트 인터페이스의 메서드에 호출 됩니다. 를 더 이상 이벤트를 수신 해야 하는 경우를 통해 연결 지점에 다시 쿠키를 전달할 수 없습니다 [iconnectionpoint:: Unadvise](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpoint-unadvise)합니다. 이 원본과 싱크 간의 연결이 끊어집니다.

참조 하지 않도록 주의 이벤트를 처리할 때는 순환 합니다.

## <a name="see-also"></a>참고자료

[이벤트 처리](../atl/event-handling-and-atl.md)
