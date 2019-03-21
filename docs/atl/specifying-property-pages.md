---
title: 속성 페이지 지정 (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- ISpecifyPropertyPages method
- property pages, specifying
ms.assetid: ee8678cf-c708-49ab-b0ad-fc2db31f1ac3
ms.openlocfilehash: 3e1dd623ef6dc49e0d48e7ff91b18041e1c46916
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57811760"
---
# <a name="specifying-property-pages"></a>속성 페이지를 지정합니다.

ActiveX 컨트롤을 만들 때 컨트롤의 속성을 설정 하려면 사용할 수 있는 속성 페이지를 사용 하 여 연결 하려는 경우가 많습니다. 컨테이너 사용을 제어 하는 `ISpecifyPropertyPages` 인터페이스 컨트롤의 속성을 설정 하는 속성 페이지를 사용할 수를 확인 합니다. 컨트롤에서이 인터페이스를 구현 해야 합니다.

구현 `ISpecifyPropertyPages` ATL을 사용 하 여 다음 단계를 수행 합니다.

1. 클래스를 파생 [ISpecifyPropertyPagesImpl](../atl/reference/ispecifypropertypagesimpl-class.md)합니다.

1. 항목을 추가 `ISpecifyPropertyPages` 클래스의 COM 맵에 있습니다.

1. 추가 된 [PROP_PAGE](reference/property-map-macros.md#prop_page) 속성 맵에 컨트롤을 사용 하 여 연결 된 각 페이지에 대 한 항목입니다.

> [!NOTE]
> 표준 컨트롤을 생성 하는 경우는 [ATL 컨트롤 마법사](../atl/reference/atl-control-wizard.md), PROP_PAGE 항목 속성 맵에 추가할만 해야 합니다. 마법사는 다른 단계에 필요한 코드를 생성합니다.

때 컨테이너 속성 맵에 PROP_PAGE 항목으로 같은 순서로 지정 된 속성 페이지를 표시 됩니다. 일반적으로 넣어야 표준 속성 페이지 항목 항목 후 속성 맵에 사용자 지정 페이지에 대 한 사용자 컨트롤에 관련 된 페이지를 먼저 표시 되도록 합니다.

## <a name="example"></a>예제

일정에 대 한 다음 클래스를 사용 하 여 제어 합니다 `ISpecifyPropertyPages` 사용자 지정 날짜 페이지와 주식 색 페이지를 사용 하 여 해당 속성을 설정할 수 있는 컨테이너를 구별 하는 인터페이스입니다.

[!code-cpp[NVC_ATL_Windowing#72](../atl/codesnippet/cpp/specifying-property-pages_1.h)]

## <a name="see-also"></a>참고자료

[속성 페이지(Visual C++)](../atl/atl-com-property-pages.md)<br/>
[ATLPages 샘플](../visual-cpp-samples.md)
