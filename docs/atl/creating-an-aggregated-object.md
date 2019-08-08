---
title: 집계 개체 만들기
ms.date: 11/04/2016
helpviewer_keywords:
- aggregation [C++], creating aggregated objects
- aggregate objects [C++], creating
ms.assetid: fc29d7aa-fd53-4276-9c2f-37379f71b179
ms.openlocfilehash: 4be8d0e852da91b58125dc01d44eed4560b2b8d9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62250760"
---
# <a name="creating-an-aggregated-object"></a>집계 개체 만들기

집계는 `IUnknown` 호출을 위임하여 외부 개체의 `IUnknown`에 대한 포인터를 내부 개체에 제공합니다.

## <a name="to-create-an-aggregated-object"></a>집계 개체를 만들려면

1. 클래스 개체에 `IUnknown` 포인터를 추가하고 생성자에서 NULL로 초기화 합니다.

1. 재정의 [FinalConstruct](../atl/reference/ccomobjectrootex-class.md#finalconstruct)를 재정의하여 집계를 만듭니다.

1. 1단계에서 정의된 `IUnknown` 포인터를 [COM_INTERFACE_ENTRY_AGGREGATE](reference/com-interface-entry-macros.md#com_interface_entry_aggregate) 매크로의 두번째 매개변수로 사용합니다.

1. [FinalRelease](../atl/reference/ccomobjectrootex-class.md#finalrelease)를 재정의하여 `IUnknown` 포인터를 해제합니다.

> [!NOTE]
> `FinalConstruct` 수행 중 집계된 개체의 인터페이스를 사용하고 해제하는 경우 클래스 개체의 정의에 [DECLARE_PROTECT_FINAL_CONSTRUCT](reference/aggregation-and-class-factory-macros.md#declare_protect_final_construct) 매크로를 추가합니다.

## <a name="see-also"></a>참고자료

[ATL COM 개체 기본 사항](../atl/fundamentals-of-atl-com-objects.md)
