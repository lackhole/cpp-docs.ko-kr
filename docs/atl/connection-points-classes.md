---
title: 연결 지점 클래스 (ATL)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- classes [C++], connection points
- connection points classes
ms.assetid: 076365fa-299a-4dce-84c3-a5dff0e0da1f
ms.openlocfilehash: 8e1ee67f75af1fa38693f7ddb487580ab733cc58
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62250816"
---
# <a name="connection-points-classes"></a>연결 지점 클래스

연결 지점에 대 한 지원을 제공 하는 다음 클래스:

- [IConnectionPointContainerImpl](../atl/reference/iconnectionpointcontainerimpl-class.md) 연결 지점 컨테이너를 구현 합니다.

- [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) 연결 지점을 구현 합니다.

- [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) 연결 지점을 나타내는 구현 합니다 [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink) 인터페이스입니다.

- [CComDynamicUnkArray](../atl/reference/ccomdynamicunkarray-class.md) 연결 지점 및 해당 싱크 간의 무제한 연결을 관리 합니다.

- [CComUnkArray](../atl/reference/ccomunkarray-class.md) 고정된 된 수의 연결 지점 및 해당 싱크 간의 연결을 관리 합니다.

- [CFirePropNotifyEvent](../atl/reference/cfirepropnotifyevent-class.md) 개체 속성 변경 되었거나 변경 되려고 하는 클라이언트의 싱크를에 알립니다.

- [IDispEventImpl](../atl/reference/idispeventimpl-class.md) ATL COM 개체에 대 한 연결 지점에 대 한 지원을 제공 합니다. 이러한 연결점은 COM 개체에서 제공 하는 이벤트 싱크 맵과 매핑됩니다.

- [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) 에 적절 한 처리기 함수로 이벤트를 라우팅하도록 클래스에서 이벤트 싱크 함께 매핑합니다.

## <a name="related-articles"></a>관련 문서

[연결 지점](../atl/atl-connection-points.md)

[이벤트 처리 및 ATL](../atl/event-handling-and-atl.md)

## <a name="see-also"></a>참고자료

[클래스 개요](../atl/atl-class-overview.md)<br/>
[연결 지점 매크로](../atl/reference/connection-point-macros.md)<br/>
[연결 지점 전역 함수](../atl/reference/connection-point-global-functions.md)
