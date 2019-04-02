---
title: 도구 모음 기본 사항
ms.date: 11/04/2016
f1_keywords:
- RT_TOOLBAR
helpviewer_keywords:
- embedding toolbar in frame window class [MFC]
- application wizards [MFC], installing default application toolbars
- toolbars [MFC], creating
- resources [MFC], toolbar
- toolbar controls [MFC], toolbars created using Application Wizard
- toolbar controls [MFC], command ID
- RT_TOOLBAR resource [MFC]
- toolbars [MFC], adding default using Application Wizard
- LoadBitmap method [MFC], toolbars
- Toolbar editor [MFC], Application Wizard
- command IDs [MFC], toolbar buttons
- SetButtons method [MFC]
- CToolBar class [MFC], default toolbars in Application Wizard
- frame window classes [MFC], toolbar embedded in
- LoadToolBar method [MFC]
ms.assetid: cc00aaff-8a56-433b-b0c0-b857d76b4ffd
ms.openlocfilehash: 9c784db2e1a482b313147e6837d6bbbd16d0ecb4
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58775493"
---
# <a name="toolbar-fundamentals"></a>도구 모음 기본 사항

이 문서에서는 응용 프로그램 마법사에서 옵션을 선택 하 여 응용 프로그램에 기본 도구 모음을 추가할 수 있는 기본 MFC 구현에 설명 합니다. 다루는 항목은 다음과 같습니다.

- [응용 프로그램 마법사 도구 모음 옵션](#_core_the_appwizard_toolbar_option)

- [코드에서 도구 모음](#_core_the_toolbar_in_code)

- [도구 모음 리소스 편집](#_core_editing_the_toolbar_resource)

- [여러 도구 모음](#_core_multiple_toolbars)

##  <a name="_core_the_appwizard_toolbar_option"></a> 응용 프로그램 마법사 도구 모음 옵션

기본 단추를 사용 하 여 단일 도구 모음을 가져오려면 사용자 인터페이스 기능 페이지의 표준 도킹 도구 모음 옵션을 선택 합니다. 그러면 응용 프로그램에 코드를 추가 하는:

- 도구 모음 개체를 만듭니다.

- 도킹 또는 고정 해제 하는 기능을 포함 하 여 도구 모음을 관리 합니다.

##  <a name="_core_the_toolbar_in_code"></a> 코드에서 도구 모음

도구 모음을 한 [CToolBar](../mfc/reference/ctoolbar-class.md) 응용 프로그램의 데이터 멤버로 선언 된 개체 `CMainFrame` 클래스입니다. 즉, 도구 모음 개체를 주 프레임 창 개체에 포함 됩니다. 즉, 프레임 창을 만들고 프레임 창 제거 됩니다 하는 경우 도구 모음을 삭제 하는 경우 MFC 도구 모음을 만듭니다. 여러 문서 MDI (인터페이스) 응용 프로그램에 대해 다음 partial 클래스 선언에 포함된 된 도구 모음 및 포함 된 상태 표시줄을 대 한 데이터 멤버를 보여 줍니다. 또한 재정의 보여 줍니다는 `OnCreate` 멤버 함수입니다.

[!code-cpp[NVC_MFCListView#6](../atl/reference/codesnippet/cpp/toolbar-fundamentals_1.h)]

도구 모음 만들기에서 발생 `CMainFrame::OnCreate`합니다. MFC 호출 [OnCreate](../mfc/reference/cwnd-class.md#oncreate) 프레임 있지만 표시 되기 전에 창을 만든 후 합니다. 기본 `OnCreate` 다음 도구 모음 작업을 수행 하는 응용 프로그램 마법사를 생성 합니다.

1. 호출 된 `CToolBar` 개체의 [만들기](../mfc/reference/ctoolbar-class.md#create) 멤버 함수를 만드는 기본 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) 개체입니다.

1. 호출 [LoadToolBar](../mfc/reference/ctoolbar-class.md#loadtoolbar) 도구 모음 리소스 정보를 로드 합니다.

1. 도킹, 부동 및 도구 팁을 활성화 하는 함수를 호출 합니다. 이러한 호출에 대 한 자세한 내용은 문서 참조 [도킹 및 부동 도구 모음](../mfc/docking-and-floating-toolbars.md)합니다.

> [!NOTE]
>  MFC 일반 샘플 [DOCKTOOL](../overview/visual-cpp-samples.md) 이전 및 새 MFC 도구 모음 그림을 포함 합니다. 사용 하는 도구 모음 `COldToolbar` 2 단계에서 호출 해야 `LoadBitmap` (대신 `LoadToolBar`) 및 `SetButtons`합니다. 새 도구 모음에 대 한 호출을 필요한 `LoadToolBar`합니다.

도킹, 부동 및 도구 팁 호출 하는 선택적입니다. 해당 줄을 제거할 수 있습니다 `OnCreate` 하려는 경우. 결과는 고정, float 또는 도킹할 수 없습니다 및 도구 설명을 표시할 수 없습니다 남아 있는 도구 모음입니다.

##  <a name="_core_editing_the_toolbar_resource"></a> 도구 모음 리소스 편집

응용 프로그램 마법사를 통해 얻을 수 있는 기본 도구 모음의 기반을 **RT_TOOLBAR** MFC 버전 4.0에에서 도입 된 사용자 지정 리소스입니다. 사용 하 여이 리소스를 편집할 수는 [도구 모음 편집기](../windows/toolbar-editor.md)합니다. 편집기를 사용 하면 쉽게 추가, 삭제 및 단추를 다시 정렬할 수 있습니다. Visual c + +에서 일반 그래픽 편집기로 매우 유사한 단추에 대 한 그래픽 편집기를 포함 합니다. Visual c + +의 이전 버전의 도구 모음을 편집한 경우 있습니다 작업이 훨씬 더 쉽게 이제.

도구 모음 단추를 명령에 연결 하려면 있습니다 단추 명령 ID와 같이 지정 `ID_MYCOMMAND`합니다. 속성 페이지 도구 모음 편집기에서 단추의 명령 ID를 지정 합니다. 그런 다음 명령에 대해 처리기 함수를 만듭니다 (참조 [함수에 메시지 매핑](../mfc/reference/mapping-messages-to-functions.md) 자세한).

새 [CToolBar](../mfc/reference/ctoolbar-class.md) 멤버 함수를 사용 합니다 **RT_TOOLBAR** 리소스입니다. [LoadToolBar](../mfc/reference/ctoolbar-class.md#loadtoolbar) 대신 더 길어진 [LoadBitmap](../mfc/reference/ctoolbar-class.md#loadbitmap) 도구 모음 단추 이미지의 비트맵을 로드 하 고 [SetButtons](../mfc/reference/ctoolbar-class.md#setbuttons) 단추 스타일을 설정 하 고 비트맵 이미지를 사용 하 여 단추를 연결 하려면.

도구 모음 편집기를 사용 하는 방법에 대 한 자세한 내용은 참조 하세요 [도구 모음 편집기](../windows/toolbar-editor.md)합니다.

##  <a name="_core_multiple_toolbars"></a> 여러 도구 모음

응용 프로그램 마법사를 하나의 기본 도구 모음을 제공합니다. 응용 프로그램에서 둘 이상의 도구 모음을 할 경우에 기본 도구 모음에 대 한 마법사에서 생성 된 코드를 기반으로 하는 추가 도구 모음에 대 한 코드를 모델링할 수 있습니다.

명령의 결과로 도구 모음을 표시 하려는 경우을 해야 합니다.

- 편집기 도구 모음을 사용 하 여 새 도구 모음 리소스 만들기 및에서 로드할 `OnCreate` 사용 하 여는 [LoadToolbar](../mfc/reference/ctoolbar-class.md#loadtoolbar) 멤버 함수입니다.

- 새 embed [CToolBar](../mfc/reference/ctoolbar-class.md) 주 프레임 창 클래스의 개체입니다.

- 적절 한 함수를 호출 하는 확인 `OnCreate` 도킹 하거나 부동 도구 모음, 해당 스타일을 설정 및 등입니다.

### <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [MFC 도구 모음 구현 (도구 모음에 대 한 개요 정보)](../mfc/mfc-toolbar-implementation.md)

- [도킹 및 부동 도구 모음](../mfc/docking-and-floating-toolbars.md)

- [도구 모음 도구 설명](../mfc/toolbar-tool-tips.md)

- 합니다 [CToolBar](../mfc/reference/ctoolbar-class.md) 하 고 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) 클래스

- [Toolbar 컨트롤 사용](../mfc/working-with-the-toolbar-control.md)

- [이전 도구 모음 사용](../mfc/using-your-old-toolbars.md)

## <a name="see-also"></a>참고자료

[MFC 도구 모음 구현](../mfc/mfc-toolbar-implementation.md)
