---
title: ATL 단순 개체 추가
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.classes.adding.atl
helpviewer_keywords:
- ATL projects, adding objects
- objects [ATL]
- ATL, simple objects
ms.assetid: 9c57d2ef-0447-4c84-8982-3304b8e49847
ms.openlocfilehash: 95a93268ca76516c1b3f736c106518ae6d94cc27
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62261620"
---
# <a name="adding-an-atl-simple-object"></a>ATL 단순 개체 추가

프로젝트에 ATL (액티브 템플릿 라이브러리) 개체를 추가할 프로젝트는 ATL 응용 프로그램 또는 ATL 지원을 포함 하는 MFC 응용 프로그램으로 만들어야 합니다. [ATL 프로젝트 마법사](../../atl/reference/atl-project-wizard.md)를 사용하여 ATL 애플리케이션을 만들거나 [MFC 애플리케이션에 ATL 개체를 추가](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)하여 MFC 애플리케이션용 ATL 지원을 구현할 수 있습니다.

먼저를 만들거나 사용 하 여 나중에 추가할 때 새 ATL 개체에 대 한 COM 인터페이스를 정의할 수 있습니다는 [인터페이스 구현](../../ide/implement-interface-wizard.md) 에서 명령을 합니다 **클래스 뷰** 바로 가기 메뉴.

## <a name="to-add-an-atl-simple-object-to-your-atl-com-project"></a>ATL COM 프로젝트에 ATL 단순 개체를 추가 하려면

1. 하나로 **솔루션 탐색기** 또는 [클래스 뷰](/visualstudio/ide/viewing-the-structure-of-code), ATL 단순 개체를 추가 하려면 프로젝트의 이름을 마우스 오른쪽 단추로 클릭 합니다.

1. 바로 가기 메뉴에서 **추가**를 클릭한 다음, **클래스 추가**를 클릭합니다.

1. 에 [클래스 추가](../../ide/add-class-dialog-box.md) 대화 상자의 **템플릿** 창 클릭 **ATL 단순 개체**, 클릭 하 고 **열기** 합니다 표시할[ATL 단순 개체 마법사](../../atl/reference/atl-simple-object-wizard.md)합니다.

1. 프로젝트에 대 한 추가 옵션을 설정 합니다 [옵션](../../atl/reference/options-atl-simple-object-wizard.md) 페이지의 **ATL 단순 개체** 마법사.

1. 클릭 **완료** 프로젝트에 개체를 추가 합니다.

## <a name="see-also"></a>참고자료

[클래스 추가](../../ide/adding-a-class-visual-cpp.md)<br/>
[ATL 프로젝트에 새 인터페이스 추가](../../atl/reference/adding-a-new-interface-in-an-atl-project.md)<br/>
[개체에 연결 지점 추가](../../atl/adding-connection-points-to-an-object.md)<br/>
[메서드 추가](../../ide/adding-a-method-visual-cpp.md)<br/>
[MFC 클래스](../../mfc/reference/adding-an-mfc-class.md)<br/>
[일반 C++ 클래스 추가](../../ide/adding-a-generic-cpp-class.md)
