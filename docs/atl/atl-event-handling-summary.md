---
title: ATL 이벤트 처리 요약
ms.date: 11/04/2016
helpviewer_keywords:
- event handling, implementing
ms.assetid: e8b47ef0-0bdc-47ff-9dd6-34df11dde9a2
ms.openlocfilehash: 0e3a47719e3160170ed1bfa64b315415ddc7a1c8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62252150"
---
# <a name="atl-event-handling-summary"></a>ATL 이벤트 처리 요약

일반적으로 COM 이벤트 처리는 과정은 비교적 간단 합니다. 세 가지 주요 단계:

- 개체에서 이벤트 인터페이스를 구현 합니다.

- 개체 이벤트를 수신 하려는 이벤트 소스는 것이 좋습니다.

- 개체는 더 이상 이벤트를 수신 해야 할 때 이벤트 소스를 unadvise입니다.

## <a name="implementing-the-interface"></a>인터페이스 구현

네 가지 주요 ATL.를 사용 하 여 인터페이스를 구현 합니다.

|파생|인터페이스 형식에 적합|모든 메서드 * 구현 해야 합니다.|런타임 시 형식 라이브러리가 필요|
|-----------------|---------------------------------|---------------------------------------------|-----------------------------------------|
|인터페이스|Vtable|예|아니요|
|[IDispatchImpl](../atl/reference/idispatchimpl-class.md)|이중|예|예|
|[IDispEventImpl](../atl/reference/idispeventimpl-class.md)|Dispinterface|아니요|예|
|[IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)|Dispinterface|아니요|아니요|

\* ATL 지원 클래스를 사용 하는 경우 되지 해야 구현 하는 `IUnknown` 또는 `IDispatch` 메서드 수동으로.

## <a name="advising-and-unadvising-the-event-source"></a>이벤트 소스를 바이 및 조언

세 가지 주요 조언 및 바이 ATL.를 사용 하는 이벤트 원본

|함수는 것이 좋습니다|Unadvise 함수|사용에 대 한 가장 적합 한|쿠키를 추적 해야 합니다.|설명|
|---------------------|-----------------------|--------------------------------|---------------------------------------------|--------------|
|[AtlAdvise](reference/connection-point-global-functions.md#atladvise), [CComPtrBase::Advise](../atl/reference/ccomptrbase-class.md#advise)|[AtlUnadvise](reference/connection-point-global-functions.md#atlunadvise)|Vtable 또는 이중 인터페이스|예|`AtlAdvise` 전역 ATL 함수가입니다. `CComPtrBase::Advise` 사용해 [CComPtr](../atl/reference/ccomptr-class.md) 하 고 [CComQIPtr](../atl/reference/ccomqiptr-class.md)합니다.|
|[IDispEventSimpleImpl::DispEventAdvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventadvise)|[IDispEventSimpleImpl::DispEventUnadvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventunadvise)|[IDispEventImpl](../atl/reference/idispeventimpl-class.md) 또는 [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)|아니요|보다 더 적은 매개 변수가 `AtlAdvise` 하므로 더 많은 작업을 수행 하는 기본 클래스입니다.|
|[CComCompositeControl::AdviseSinkMap(TRUE)](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)|[CComCompositeControl::AdviseSinkMap(FALSE)](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)|복합 컨트롤의 ActiveX 컨트롤|아니요|`CComCompositeControl::AdviseSinkMap` 모든 항목에는 이벤트 맵 싱크 권고 합니다. 동일한 함수 unadvises 항목입니다. 이 메서드는 자동으로 호출 된 `CComCompositeControl` 클래스입니다.|
|[CAxDialogImpl::AdviseSinkMap(TRUE)](../atl/reference/caxdialogimpl-class.md#advisesinkmap)|[CAxDialogImpl::AdviseSinkMap(FALSE)](../atl/reference/caxdialogimpl-class.md#advisesinkmap)|대화 상자에서 ActiveX 컨트롤|아니요|`CAxDialogImpl::AdviseSinkMap` 조언 하 고 대화 상자 리소스에서 모든 ActiveX 컨트롤 unadvises 합니다. 이를 자동으로 수행 됩니다.|

## <a name="see-also"></a>참고자료

[이벤트 처리](../atl/event-handling-and-atl.md)<br/>
[IDispEventImpl 지원](../atl/supporting-idispeventimpl.md)
