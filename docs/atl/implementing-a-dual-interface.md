---
title: 이중 인터페이스 (ATL) 구현
ms.date: 11/04/2016
helpviewer_keywords:
- IDispatchImpl class, implementing dual interfaces
- dual interfaces, implementing
ms.assetid: d1da3633-b445-4dcd-8a0a-3efdafada3ea
ms.openlocfilehash: ecd6a0cc90ca4175c4ae898f2e9aa8bf00508a3e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62262231"
---
# <a name="implementing-a-dual-interface"></a>이중 인터페이스를 구현합니다.

사용 하 여 이중 인터페이스를 구현할 수 있습니다 합니다 [IDispatchImpl](../atl/reference/idispatchimpl-class.md) 의 기본 구현을 제공 하는 클래스는 `IDispatch` 이중 인터페이스에서 메서드. 자세한 내용은 [Implementing the IDispatch Interface](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)을 참조하십시오.

이 클래스를 사용 합니다.

- 형식 라이브러리에 이중 인터페이스를 정의 합니다.

- 특수화에서 클래스를 파생 `IDispatchImpl` (템플릿 인수로 인터페이스와 형식 라이브러리에 대 한 정보를 전달).

- (또는 항목)를 통해 이중 인터페이스를 노출 하는 COM 맵 추가할 `QueryInterface`합니다.

- 클래스의 vtable 부분 인터페이스를 구현 합니다.

- 런타임에 인터페이스 정의 포함 하는 형식 라이브러리 개체에 사용할 수 있는지 확인 합니다.

## <a name="atl-simple-object-wizard"></a>ATL 단순 개체 마법사

새 인터페이스를 만들고 새 클래스를 구현 하려는 경우 사용할 수 있습니다는 [ATL 클래스 추가 대화 상자](../ide/add-class-dialog-box.md)를 차례로 합니다 [ATL 단순 개체 마법사](../atl/reference/atl-simple-object-wizard.md)합니다.

## <a name="implement-interface-wizard"></a>인터페이스 구현 마법사

기존 인터페이스를 만든 경우 사용할 수 있습니다 합니다 [인터페이스 구현 마법사](../atl/reference/adding-a-new-interface-in-an-atl-project.md) 기존 클래스에 필요한 기본 클래스를 COM 맵 엔트리 및 스 켈 레 톤 메서드 구현을 추가 합니다.

> [!NOTE]
>  형식 라이브러리의 주 및 부 버전 번호를 템플릿 인수로 전달 되도록 생성된 된 기본 클래스를 조정 해야 할 수 있습니다 프로그램 `IDispatchImpl` 기본 클래스입니다. 인터페이스 구현 마법사를 형식 라이브러리 버전 번호를 확인 하지 않습니다.

## <a name="implementing-idispatch"></a>IDispatch를 구현합니다.

사용할 수는 `IDispatchImpl` 기본 클래스는 dispinterface의 구현을 제공 하 고 COM 맵에에서 적절 한 항목을 지정 하면 (사용 하 여 합니다 [COM_INTERFACE_ENTRY2](reference/com-interface-entry-macros.md#com_interface_entry2) 또는 [COM_INTERFACE_ENTRY_IID](reference/com-interface-entry-macros.md#com_interface_entry_iid) 매크로) 해당 하는 이중 인터페이스를 설명 하는 형식 라이브러리를가지고 있습니다. 상당히 일반적인 구현 하는 것은 `IDispatch` 예를 들어이 방식으로 인터페이스입니다. 인터페이스 구현 마법사 구현 하려는 가정 둘 다 고 ATL 단순 개체 마법사 `IDispatch` 이러한 방식으로 하므로 이러한는 적절 한 항목 맵에 추가 합니다.

> [!NOTE]
>  ATL 제공 합니다 [IDispEventImpl](../atl/reference/idispeventimpl-class.md) 및 [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) 클래스는 호환 되는 이중 인터페이스 정의가 포함 된 형식 라이브러리를 요구 하지 않고 dispinterface를 구현할 수 있습니다.

## <a name="see-also"></a>참고자료

[이중 인터페이스 및 ATL](../atl/dual-interfaces-and-atl.md)
