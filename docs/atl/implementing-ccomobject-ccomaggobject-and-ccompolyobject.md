---
title: CComObject, CComAggObject 및 CComPolyObject 구현
ms.date: 11/04/2016
helpviewer_keywords:
- CComPolyObject class, implementing
- CreateInstance method
- CComAggObject class
- CComObject class, implementing
ms.assetid: 5aabe938-104d-492e-9c41-9f7fb1c62098
ms.openlocfilehash: e2413c8fb9f5722f0245883c947067387838e57f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62261789"
---
# <a name="implementing-ccomobject-ccomaggobject-and-ccompolyobject"></a>CComObject, CComAggObject 및 CComPolyObject 구현

템플릿 클래스 [CComObject](../atl/reference/ccomobject-class.md)를 [CComAggObject](../atl/reference/ccomaggobject-class.md), 및 [CComPolyObject](../atl/reference/ccompolyobject-class.md) 상속 체인의 가장 많이 파생 된 클래스는 항상 있습니다. 책임 모든에서 메서드를 처리 하는 것 `IUnknown`: `QueryInterface`를 `AddRef`, 및 `Release`합니다. 또한 `CComAggObject` 하 고 `CComPolyObject` (집계 개체에 대 한 사용) 하는 경우 특별 한 참조 횟수를 제공 및 `QueryInterface` 알 수 없는 내부에 필요한 의미 체계.

여부를 `CComObject`, `CComAggObject`, 또는 `CComPolyObject` 는 다음 매크로 중 하나 (또는 없음)을 선언 하는지 여부에 따라 달라 집니다.

|매크로|효과|
|-----------|------------|
|DECLARE_NOT_AGGREGATABLE|항상 사용 하 여 `CComObject`입니다.|
|DECLARE_AGGREGATABLE|사용 하 여 `CComAggObject` 개체가 집계 되는 경우 및 `CComObject` 없는 경우. `CComCoClass` 이 매크로 포함 합니다 DECLARE_ 하나도 경우 * _AGGREGATABLE 매크로 클래스에서 선언 된이 기본값으로 사용 됩니다.|
|DECLARE_ONLY_AGGREGATABLE|항상 사용 하 여 `CComAggObject`입니다. 개체가 집계 되지 않은 경우 오류를 반환 합니다.|
|DECLARE_POLY_AGGREGATABLE|ATL의 인스턴스를 만듭니다 **CComPolyObject\<CYourClass >** 때 `IClassFactory::CreateInstance` 라고 합니다. 를 만드는 동안 알 수 없는 외부의 값이 확인 됩니다. 이 NULL 이면 `IUnknown` 집계 개체에 대 한 구현 됩니다. 알 수 없는 외부, NULL이 아닌 경우 `IUnknown` 집계 개체에 대해 구현 됩니다.|

사용 하는 이점은 `CComAggObject` 하 고 `CComObject` 구현의 `IUnknown` 생성 되는 개체의 종류에 대해 최적화 됩니다. 예를 들어 집계 개체 하기만 참조 횟수를 모두 알 수 없는 내부에 대 한 참조 횟수에 대 한 포인터 알 수 없는 외부 집합체 해야 하는 동안.

사용 하는 이점은 `CComPolyObject` 는 둘 다 필요 하지 않는 `CComAggObject` 및 `CComObject` 집계 및 집계 경우를 처리 하 여 모듈에서. 단일 `CComPolyObject` 두 경우를 처리 하는 개체입니다. 즉, 모듈에서 vtable의 복사본이 하나만 및 함수의 복사본 하나 존재 합니다. Vtable 큰 경우 현재 모듈 크기가 상당히 줄어들 수 있습니다이 합니다. Vtable이 작은 경우 사용 하는 반면 `CComPolyObject` 집계 또는 집계 개체에 대해 최적화 되어 있지 않으므로 약간 더 큰 모듈 크기를 발생할 수 있습니다는 `CComAggObject` 및 `CComObject`합니다.

## <a name="see-also"></a>참고자료

[ATL COM 개체 기본 사항](../atl/fundamentals-of-atl-com-objects.md)<br/>
[집계 및 클래스 팩터리 매크로](../atl/reference/aggregation-and-class-factory-macros.md)
