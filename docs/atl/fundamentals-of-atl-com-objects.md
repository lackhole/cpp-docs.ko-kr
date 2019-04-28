---
title: ATL COM 개체의 기본 사항
ms.date: 11/19/2018
helpviewer_keywords:
- COM, and ATL
- ATL, COM
- ATL COM objects
- COM objects, ATL
ms.assetid: 0f9c9d98-cc28-45da-89ac-dc94cee422fe
ms.openlocfilehash: cba26ede01b69e4a077f1e842982adc8c2127331
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62198930"
---
# <a name="fundamentals-of-atl-com-objects"></a>ATL COM 개체의 기본 사항

다음 그림에서는 클래스 및 ATL COM 개체를 정의 하는 데 사용 되는 인터페이스 간의 관계를 보여 줍니다.

![ATL 구조](../atl/media/vc307y1.gif "ATL 구조")

> [!NOTE]
>  이 다이어그램에 따르면 `CComObject` 에서 파생 됩니다 `CYourClass` 반면 `CComAggObject` 하 고 `CComPolyObject` 포함 `CYourClass` 멤버 변수입니다.

ATL COM 개체를 정의 하는 방법은 세 가지가 있습니다. 표준 옵션을 사용 하는 것은 `CComObject` 클래스에서 파생 된 `CYourClass`합니다. 두 번째 옵션을 사용 하 여 집계 개체를 만드는 것은 `CComAggObject` 클래스입니다. 세 번째 옵션을 사용 하는 것은 `CComPolyObject` 클래스입니다. `CComPolyObject` 하이브리드 역할: 작동할 수 있습니다는 `CComObject` 클래스 또는 `CComAggObject` 먼저 생성 되는 방식에 따라 클래스입니다. 사용 하는 방법에 대 한 자세한 내용은 합니다 `CComPolyObject` 클래스를 참조 하십시오 [CComPolyObject 클래스](../atl/reference/ccompolyobject-class.md)합니다.

두 개체를 사용 하는 표준 ATL COM을 사용 하는 경우: 외부 개체 및 내부 개체입니다. 외부 클라이언트 외부 개체에 정의 된 래퍼 함수를 통해 내부 개체의 기능에 액세스 합니다. 외부 개체가 형식의 `CComObject`합니다.

집계 개체를 사용 하면 외부 개체는 내부 개체의 기능에 대 한 래퍼 제공 하지 않습니다. 대신, 외부 개체는 외부 클라이언트에서 직접 액세스 하는 포인터를 제공 합니다. 이 시나리오에서 외부 개체는 형식의 `CComAggObject`합니다. 내부 개체는 외부 개체의 멤버 변수 및 형식 `CYourClass`합니다.

클라이언트는 내부 개체와 상호 작용 하는 외부 개체를 통해 이동 하지 않아도, 때문에 집계 된 개체는 일반적으로 더 효율적입니다. 또한 외부 개체가 없습니다 집계 된 개체의 기능을 알아야 집계 된 개체의 인터페이스는 클라이언트에 직접 사용할 수 있습니다. 그러나 일부 개체를 집계할 수 있습니다. 집계 개체에 대 한 집계 고려에서 하 여 디자인 해야 합니다.

ATL 구현 [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) 두 단계로 진행에서 합니다.

- [CComObject](../atl/reference/ccomobject-class.md), [CComAggObject](../atl/reference/ccomaggobject-class.md), 또는 [CComPolyObject](../atl/reference/ccompolyobject-class.md) 구현 하는 `IUnknown` 메서드.

- [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) 나 [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) 관리에 대 한 참조 횟수와 외부 포인터 `IUnknown`합니다.

ATL COM 개체의 다른 측면은 다른 클래스에 의해 처리 됩니다.

- [CComCoClass](../atl/reference/ccomcoclass-class.md) 개체의 기본 클래스 팩터리 및 집계 모델을 정의 합니다.

- [IDispatchImpl](../atl/reference/idispatchimpl-class.md) 의 기본 구현을 제공 합니다 `IDispatch Interface` 개체에 이중 인터페이스의 일부입니다.

- [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) 구현 된 `ISupportErrorInfo` 오류 정보를 보장 하는 인터페이스 호출 체인을 올바르게 전파 될 수 있습니다.

## <a name="in-this-section"></a>섹션 내용

[CComObjectRootEx 구현](../atl/implementing-ccomobjectrootex.md)<br/>
예제를 구현 하기 위한 COM 맵 엔트리 `CComObjectRootEx`합니다.

[CComObject, CComAggObject 및 CComPolyObject 구현](../atl/implementing-ccomobject-ccomaggobject-and-ccompolyobject.md)<br/>
에 대해 설명 하는 방법을 **DECLARE_\*_AGGREGATABLE** 매크로 사용에 영향을 줄 `CComObject`합니다 `CComAggObject`, 및 `CComPolyObject`합니다.

[IDispatch 및 IErrorInfo 지원](../atl/supporting-idispatch-and-ierrorinfo.md)<br/>
지 원하는 데 ATL 구현 클래스를 나열 합니다 `IDispatch` 및 `IErrorInfo` 인터페이스입니다.

[IDispEventImpl 지원](../atl/supporting-idispeventimpl.md)<br/>
클래스에 대 한 연결 지점을 구현 하는 단계를 설명 합니다.

[기본 클래스 팩터리 및 집계 모델 변경](../atl/changing-the-default-class-factory-and-aggregation-model.md)<br/>
기본 클래스 팩터리 및 집계 모델을 변경 하는 데 어떤 매크로 보여 줍니다.

[집계 개체 만들기](../atl/creating-an-aggregated-object.md)<br/>
집계 개체를 만들기 위한 단계를 나열 합니다.

## <a name="related-sections"></a>관련 단원

[ATL 프로젝트 만들기](../atl/reference/creating-an-atl-project.md)<br/>
ATL COM 개체 만들기에 대 한 정보를 제공 합니다.

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
액티브 템플릿 라이브러리를 사용하여 프로그래밍하는 방법에 대한 개념 항목의 링크를 제공합니다.

## <a name="see-also"></a>참고자료

[개념](../atl/active-template-library-atl-concepts.md)
