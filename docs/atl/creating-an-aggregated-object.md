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

집계 대리자 `IUnknown` 외부 개체에 대 한 포인터를 제공 하는 호출 `IUnknown` 내부 개체입니다.

## <a name="to-create-an-aggregated-object"></a>집계 개체를 만들려면

1. 추가 `IUnknown` 클래스에 대 한 포인터 개체를 생성자에 NULL로 초기화 합니다.

1. 재정의 [FinalConstruct](../atl/reference/ccomobjectrootex-class.md#finalconstruct) 집계를 만드는 합니다.

1. 사용 하 여는 `IUnknown` 포인터에 대 한 두 번째 매개 변수로 1 단계에서에서 정의 된 [COM_INTERFACE_ENTRY_AGGREGATE](reference/com-interface-entry-macros.md#com_interface_entry_aggregate) 매크로입니다.

1. 재정의 [FinalRelease](../atl/reference/ccomobjectrootex-class.md#finalrelease) 해제 하는 `IUnknown` 포인터입니다.

> [!NOTE]
> 사용 하 고 하는 동안 집계 된 개체의 인터페이스를 릴리스 하는 경우 `FinalConstruct`를 추가 해야 합니다 [DECLARE_PROTECT_FINAL_CONSTRUCT](reference/aggregation-and-class-factory-macros.md#declare_protect_final_construct) 클래스 개체의 정의에 매크로입니다.

## <a name="see-also"></a>참고자료

[ATL COM 개체 기본 사항](../atl/fundamentals-of-atl-com-objects.md)
