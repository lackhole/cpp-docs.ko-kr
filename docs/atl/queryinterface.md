---
title: QueryInterface
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- interfaces, pointers
- interfaces, availability
- QueryInterface method
ms.assetid: 62fce95e-aafa-4187-b50b-e6611b74c3b3
ms.openlocfilehash: 28f3781706981b06d49829c0277014c09574ef6b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62250362"
---
# <a name="queryinterface"></a>QueryInterface

개체가 인스턴스화되기 전에 정적으로 제공하는 기능을 표현할 수 있는 메커니즘이 있지만, 기본적으로 COM 메커니즘은 [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_))라는 `IUnknown` 메서드를 사용합니다.

모든 인터페이스는 `IUnknown`에서 파생되므로, 모든 인터페이스는 `QueryInterface` 구현이 있습니다. 구현에 관계없이 이 메서드는 호출자가 포인터 인터페이스의 IID를 사용하여 개체를 쿼리합니다. 개체가 해당 인터페이스를 지원하면 `QueryInterface`는 `AddRef`를 호출하면서 인터페이스에 대한 포인터를 검색합니다. 그렇지 않으면 E_NOINTERFACE 오류 코드를 반환합니다.

[참조 카운팅](../atl/reference-counting.md) 계산 규칙을 항상 지켜야 합니다. 참조 횟수를 0으로 감소시키기 위해 `Release`를 인터페이스 포인터로 호출한 후에는 다시 그 포인터를 사용하면 안 됩니다. 경우에 따라 개체에 대한 약한 참조가 필요할 수도 있습니다. (즉, 참조 횟수를 증가하지 않고 해당 인터페이스 중 하나의 포인터가 필요할 수 있습니다.) 하지만 `Release`를 호출한 뒤 `QueryInterface`를 호출할 수 없습니다. 이러한 방식으로 얻은 포인터는 잘못되었으며 사용할 수 없습니다. 이것은 [_ATL_DEBUG_INTERFACES](reference/debugging-and-error-reporting-macros.md#_atl_debug_interfaces)가 정의될 때 더 쉽게 드러나므로, 이 매크로를 정의하는 것은 참조 계산 버그를 찾는 데 도움이 됩니다.

## <a name="see-also"></a>참고자료

[COM 소개](../atl/introduction-to-com.md)<br/>
[QueryInterface: 개체에서 탐색](/windows/desktop/com/queryinterface--navigating-in-an-object)
