---
title: ATL 속성 페이지 추가
ms.date: 11/04/2016
helpviewer_keywords:
- property pages, adding
- ATL projects, adding property pages
- controls [ATL], property pages
ms.assetid: ddf92b49-42a2-46d2-b6b8-d37baedebeca
ms.openlocfilehash: c61f666865d3e1db4cdcf2dc6d3e07c2113a79c7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62249101"
---
# <a name="adding-an-atl-property-page"></a>ATL 속성 페이지 추가

액티브 템플릿 라이브러리 (ATL) 속성 페이지를 프로젝트에 추가 하려면 프로젝트가 ATL 응용 프로그램 또는 ATL 지원을 포함 하는 MFC 응용 프로그램으로 만들어야 합니다. 사용할 수는 [ATL 프로젝트 마법사](../../atl/reference/atl-project-wizard.md) ATL 응용 프로그램을 만들려면 또는 [MFC 응용 프로그램에 ATL 개체를 추가](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) MFC 응용 프로그램에 ATL 지원을 구현 하기 위해.

컨트롤의 속성 페이지에 추가 하는 컨트롤을 지원 해야 합니다 [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md) 인터페이스입니다. 이 인터페이스는 기본적으로 컨트롤의 파생 목록의 경우 클래스 있습니다 [ATL 컨트롤 만들기](../../atl/reference/adding-an-atl-control.md) 를 사용 하 여는 [ATL 컨트롤 마법사](../../atl/reference/atl-control-wizard.md).

> [!NOTE]
> 컨트롤 클래스에 없는 경우 [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md) 파생 목록에 추가 해야 수동으로.

## <a name="to-add-an-atl-property-page-to-your-project"></a>프로젝트에 ATL 속성 페이지를 추가 하려면

1. 하나로 **솔루션 탐색기** 또는 [클래스 뷰](/visualstudio/ide/viewing-the-structure-of-code), ATL 속성 페이지를 추가 하려면 프로젝트의 이름을 마우스 오른쪽 단추로 클릭 합니다.

1. 바로 가기 메뉴에서 클릭 **추가** 을 클릭 한 다음 **클래스 추가**합니다.

1. 에 [클래스 추가](../../ide/add-class-dialog-box.md) 대화 상자의 **템플릿** 창 클릭 **ATL 속성 페이지** 클릭 하 고 **열기** 합니다 표시할[ATL 속성 페이지 마법사](../../atl/reference/atl-property-page-wizard.md)합니다.

컨트롤의 속성 페이지를 만든 후에 제공 해야 합니다 [PROP_PAGE](property-map-macros.md#prop_page) 컨트롤의 속성 맵에 항목입니다.

## <a name="see-also"></a>참고자료

[속성 페이지(Visual C++)](../../atl/atl-com-property-pages.md)<br/>
[ATL COM 개체 기본 사항](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[예제: 속성 페이지 구현](../../atl/example-implementing-a-property-page.md)
