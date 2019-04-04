---
title: ATL COM 속성 페이지
ms.date: 11/04/2016
helpviewer_keywords:
- property pages, COM
- ATL COM objects
- COM property pages
- property pages, ATL
- COM objects, ATL
- ATL property pages
ms.assetid: 663c7caa-2e5e-4b5c-b8ea-fd434ceb1654
ms.openlocfilehash: d374569c6c3e9bb63b6b026d2b0f86226d158f36
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58768415"
---
# <a name="atl-com-property-pages"></a>ATL COM 속성 페이지

속성을 설정 하는 것에 대 한 사용자 인터페이스를 제공 하는 COM 속성 페이지 (또는 메서드를 호출) 하나 이상의 COM 개체입니다. 속성 페이지는 컨트롤 속성을 디자인 타임에 설정 될 수 있는 풍부한 사용자 인터페이스를 제공 하기 위해 ActiveX 컨트롤에서 광범위 하 게 사용 됩니다.

속성 페이지는 COM 구현 하는 개체를 [IPropertyPage](/windows/desktop/api/ocidl/nn-ocidl-ipropertypage) 또는 [IPropertyPage2](/windows/desktop/api/ocidl/nn-ocidl-ipropertypage2) 인터페이스입니다. 이러한 인터페이스는 페이지와 연결할 수 있는 메서드를 제공 된 `site` (페이지의 컨테이너를 나타내는 COM 개체) 및 다양 한 *개체* 메서드가 변경 내용에 대 한 응답으로 호출 됩니다 (COM 개체 수행한 속성 페이지의 사용자). 속성 페이지 컨테이너는 페이지를 표시 하거나 숨기려면 사용자 인터페이스를 지정 하 고 변경 내용을 적용 하는 경우 기본 개체에 사용자가 변경한 경우 속성 페이지 인터페이스에서 메서드를 호출 하는 일을 담당 합니다.

각 속성 페이지 속성을 설정할 수 있습니다 개체와 독립적으로 빌드할 수 있습니다. 모든 속성 페이지를 필요한 경우 특정 인터페이스 (또는 인터페이스의 집합)를 이해 하 고 해당 인터페이스의 메서드를 호출 하는 것에 대 한 사용자 인터페이스를 제공 합니다.

자세한 내용은 [속성 시트 및 속성 페이지](/windows/desktop/com/property-sheets-and-property-pages) Windows SDK에 있습니다.

## <a name="in-this-section"></a>섹션 내용

[속성 페이지 지정](../atl/specifying-property-pages.md)<br/>
제어에 대 한 속성 페이지를 지정 하는 단계를 나열 하 고 클래스 예제를 보여 줍니다.

[속성 페이지 구현](../atl/implementing-property-pages.md)<br/>
속성 페이지를 재정의 하는 방법을 비롯 하 여 구현 하는 단계를 나열 합니다. ATLPages 샘플 프로그램을 기반으로 하는 전체 예제를 안내 합니다.

## <a name="related-sections"></a>관련 단원

[ATLPages 샘플](../overview/visual-cpp-samples.md)<br/>
ATLPages 샘플을 사용 하 여 속성 페이지를 구현 하는 샘플 추상 `IPropertyPageImpl`합니다.

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
액티브 템플릿 라이브러리를 사용하여 프로그래밍하는 방법에 대한 개념 항목의 링크를 제공합니다.

## <a name="see-also"></a>참고자료

[개념](../atl/active-template-library-atl-concepts.md)
