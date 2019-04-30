---
title: 인터페이스 (ATL)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- COM interfaces
- interfaces, COM
ms.assetid: de6c8b12-6230-4fdc-af66-a28b91d5ee55
ms.openlocfilehash: 5416fb8a99420f0f6c84318753ee3399ccf5db2a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62250316"
---
# <a name="interfaces-atl"></a>인터페이스 (ATL)

인터페이스는 개체가 기능을 외부에 노출하는 방법입니다. COM의 인터페이스는 개체에 의해 구현된 함수에 대한 포인터의 테이블(예: C++ vtable)입니다. 테이블은 인터페이스를 나타내며 이 인터페이스가 가리키는 기능은 해당 인터페이스의 메소드입니다. 개체는 많은 인터페이스를 선택하여 노출할 수 있습니다.

각 인터페이스는 기본 COM 인터페이스인 [IUnknown](../atl/iunknown.md)을 기반으로 합니다. `IUnknown`의 메소드는 개체에 의해 노출된 다른 인터페이스에 대한 탐색을 허용합니다.

또한 각 인터페이스에는 고유한 인터페이스 ID(IID)가 지정됩니다. 이 고유성을 통해 인터페이스 버전 관리를 쉽게 지원할 수 있습니다. 인터페이스의 새 버전은 새로운 IID를 사용하는 단순한 새로운 인터페이스입니다.

> [!NOTE]
>  표준 COM 및 OLE 인터페이스에 대한 IID는 미리 정의됩니다.

## <a name="see-also"></a>참고자료

[COM 소개](../atl/introduction-to-com.md)<br/>
[COM 개체 및 인터페이스](/windows/desktop/com/com-objects-and-interfaces)
