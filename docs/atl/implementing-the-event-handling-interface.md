---
title: 이벤트 처리 인터페이스 구현
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, event handling
- event handling, ATL
- interfaces, event and event sink
ms.assetid: eb2a5b33-88dc-4ce3-bee0-c5c38ea050d7
ms.openlocfilehash: d977b59907266a2e0141defa8c496b1e7bc66a6c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62262075"
---
# <a name="implementing-the-event-handling-interface"></a>이벤트 처리 인터페이스 구현

ATL을 지 원하는 이벤트를 처리 하는 데 필요한 세 요소 모두: 이벤트 인터페이스를 구현 하 고 이벤트 소스를 확인 하 라는 바이 이벤트 소스입니다. 정확한 단계를 수행 해야 응용 프로그램의 성능 요구 사항과 이벤트 인터페이스의 유형에 따라 달라 집니다.

ATL을 사용 하 여 인터페이스를 구현 하는 가장 일반적인 방법은 다음과 같습니다.

- 사용자 지정 인터페이스에서 직접 파생 됩니다.

- 파생 [IDispatchImpl](../atl/reference/idispatchimpl-class.md) 이중 인터페이스의 형식 라이브러리에 설명 합니다.

- 파생 [IDispEventImpl](../atl/reference/idispeventimpl-class.md) 형식 라이브러리에 설명 하는 dispinterface에 대 한 합니다.

- 파생 [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) 런타임에 형식 정보를 로드 하 여 효율성을 개선 하려는 경우 또는 형식 라이브러리에 설명 되지 않은 dispinterface에 대 한 합니다.

호출 하 여 이벤트 소스를 권장 해야 사용자 지정 또는 이중 인터페이스를 구현 하는 경우 [AtlAdvise](reference/connection-point-global-functions.md#atladvise) 하거나 [CComPtrBase::Advise](../atl/reference/ccomptrbase-class.md#advise)합니다. 호출에서 반환 된 쿠키를 추적 해야 합니다. 호출 [AtlUnadvise](reference/connection-point-global-functions.md#atlunadvise) 연결을 끊습니다.

사용 하 여 dispinterface를 구현 하는 경우 `IDispEventImpl` 또는 `IDispEventSimpleImpl`를 호출 하 여 이벤트 소스를 권장 해야 [IDispEventSimpleImpl::DispEventAdvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventadvise)합니다. 호출 [IDispEventSimpleImpl::DispEventUnadvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventunadvise) 연결을 끊습니다.

사용 중인 경우 `IDispEventImpl` 복합 컨트롤의 기본 클래스로 싱크 맵에 나열 된 이벤트 원본이 됩니다 권장 하 고 자동으로 사용 하 여 unadvised [CComCompositeControl::AdviseSinkMap](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)합니다.

합니다 `IDispEventImpl` 고 `IDispEventSimpleImpl` 쿠키를 관리 하는 클래스입니다.

## <a name="see-also"></a>참고자료

[이벤트 처리](../atl/event-handling-and-atl.md)
