---
title: MFC 도구 모음 구현
ms.date: 11/04/2016
helpviewer_keywords:
- toolbars [MFC], creating
- buttons [MFC], MFC toolbars
- toolbars [MFC], docking
- CToolBar class [MFC], creating toolbars
- MFC toolbars
- floating toolbars [MFC]
- toolbars [MFC], floating
- docking toolbars [MFC]
- bitmaps [MFC], toolbar
- toolbar controls [MFC]
- CToolBarCtrl class [MFC], implementing toolbars
- tool tips [MFC], enabling
- toolbars [MFC]
- toolbars [MFC], implementing MFC toolbars
ms.assetid: af3319ad-c430-4f90-8361-e6a2c06fd084
ms.openlocfilehash: 55c43c47b93cd21d86293706fc7c3eb5145c39fd
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58773179"
---
# <a name="mfc-toolbar-implementation"></a>MFC 도구 모음 구현

도구 모음은는 [컨트롤 막대](../mfc/control-bars.md) 컨트롤의 비트맵 이미지를 포함 하는 합니다. 이러한 이미지는 누름 단추, 확인란 또는 라디오 단추 처럼 동작할 수 있습니다. 클래스를 제공 하는 MFC [CToolbar](../mfc/reference/ctoolbar-class.md) 도구 모음을 관리할 수 있습니다.

이 사용 하는 경우 MFC 도구 모음 사용자는 창 가장자리에 도킹 하거나 "이동" 응용 프로그램 창 내에서 수 있습니다. MFC는 개발 환경에서와 같이 사용자 지정 가능한 도구 모음을 지원 하지 않습니다.

MFC에서는 도구 팁: 단추 위로 마우스를 이동 하는 경우 도구 모음 단추의 용도 설명 하는 작은 팝업 창입니다. 기본적으로 사용자가 도구 모음 단추를 누를 때 상태 문자열의 상태 표시줄에 나타납니다 (있는 경우). "플라이 하 여" 상태 표시줄 누르지 않고 마우스를 단추 위로 가져갈 때 상태 문자열을 표시 하려면 업데이트를 활성화할 수 있습니다.

> [!NOTE]
>  MFC 버전 4.0부터 도구 모음 및 도구 설명 구현 됩니다 Windows 95 및 이후 기능을 사용 하 여 MFC에 특정 이전 구현 대신 합니다.

이전 버전과 호환성을 위해 MFC 유지 클래스에서 이전 도구 모음 구현 `COldToolBar`합니다. 이전 버전의 MFC에 대 한 설명서 설명 `COldToolBar` 아래에서 `CToolBar`합니다.

응용 프로그램 마법사에서 도구 모음 옵션을 선택 하 여 프로그램에서 첫 번째 도구 모음을 만듭니다. 또한 추가 도구 모음을 만들 수 있습니다.

다음은이 기사에서 소개한:

- [도구 모음 단추](#_core_toolbar_buttons)

- [도킹 및 부동 도구 모음](#_core_docking_and_floating_toolbars)

- [도구 모음 및 도구 설명](#_core_toolbars_and_tool_tips)

- [CToolBar 및 CToolBarCtrl 클래스](#_core_the_ctoolbar_and_ctoolbarctrl_classes)

- [도구 모음 비트맵](#_core_the_toolbar_bitmap)

##  <a name="_core_toolbar_buttons"></a> 도구 모음 단추

도구 모음 단추는 메뉴의 항목에 유사 합니다. 두 종류의 사용자 인터페이스 개체 처리기 함수를 제공 하 여 프로그램을 처리 하는 명령을 생성 합니다. 도구 모음 단추 종종 기능과 중복 되는 메뉴 명령, 동일한 기능을 대체 사용자 인터페이스를 제공 합니다. Id가 같을 단추와 메뉴 항목 제공 하면 명령이 복제 됩니다.

도구 모음에서 단추 누름 단추, 확인란 또는 라디오 단추 기호로 표시 및 동작을 만들 수 있습니다. 자세한 내용은 클래스를 참조 하세요 [CToolBar](../mfc/reference/ctoolbar-class.md)합니다.

##  <a name="_core_docking_and_floating_toolbars"></a> 도킹 및 부동 도구 모음

MFC 도구 모음을 수행할 수 있습니다.

- 부모 창의 한쪽 고정 되어 있습니다.

- 끌 및 "고정" 또는 모든 면을 하나 이상 지정 하면 부모 창에 사용자가 연결 합니다.

- "부동" 또는 사용자 서 이동할 수 있으며 모든 편리한 위치에 있으므로 자체 미니 프레임 창의 프레임 창에서 분리 되어야 합니다.

- 부동 하는 동안 크기를 조정할 수 있습니다.

자세한 내용은 문서 참조 [도킹 및 부동 도구 모음](../mfc/docking-and-floating-toolbars.md)합니다.

##  <a name="_core_toolbars_and_tool_tips"></a> 도구 모음 및 도구 설명

"도구 설명"을 표시 하려면 MFC 도구 모음을 만들 수도 있습니다-도구 모음 단추의 용도 대 한 간단한 텍스트 설명을 포함 하는 작은 팝업 창입니다. 도구 모음 단추 위로 마우스를 이동할 때 도구 설명 창이 팝업 힌트를 제공 합니다. 자세한 내용은 문서 참조 [도구 모음 도구 설명](../mfc/toolbar-tool-tips.md)합니다.

##  <a name="_core_the_ctoolbar_and_ctoolbarctrl_classes"></a> CToolBar 및 CToolBarCtrl 클래스

클래스를 통해 응용 프로그램의 도구 모음을 관리할 [CToolBar](../mfc/reference/ctoolbar-class.md)합니다. MFC 버전 4.0부터 `CToolBar` 이상 Windows 95에서 사용할 수 있습니다. 도구 모음 공용 컨트롤 및 Windows NT 버전 3.51 이상 사용 하 여 기준입니다.

MFC를 사용 하기 때문에이 재구현 결과 도구 모음에 대 한 MFC 코드에서 운영 체제 지원을 사용 합니다. 다시 구현에는 기능 향상 됩니다. 사용할 수 있습니다 `CToolBar` 도구 모음 하거나 조작 하는 멤버 함수 내부에 대 한 참조를 가져올 수 있습니다 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) 개체 및 도구 모음 사용자 지정 및 추가 기능에 대 한 해당 멤버 함수를 호출 합니다.

> [!TIP]
>  경우 노력을 투자 했 많이 이전 MFC 구현에서 `CToolBar`, 지원은 여전히 사용할 수 있습니다. 문서를 참조 하세요 [이전 도구 모음 사용 하 여](../mfc/using-your-old-toolbars.md)입니다.

또한 MFC 일반 샘플을 참조 하세요 [DOCKTOOL](../overview/visual-cpp-samples.md)합니다.

##  <a name="_core_the_toolbar_bitmap"></a> 도구 모음 비트맵

생성 된를 `CToolBar` 개체 각 단추에 대 한 개의 이미지가 포함 된 단일 비트맵을 로드 하 여 도구 모음 이미지를 만듭니다. 응용 프로그램 마법사를 시각적으로 사용자 지정할 수 있는 표준 도구 모음 비트맵을 만듭니다 C++ [도구 모음 편집기](../windows/toolbar-editor.md)합니다.

### <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [도구 모음 기본 사항](../mfc/toolbar-fundamentals.md)

- [도킹 및 부동 도구 모음](../mfc/docking-and-floating-toolbars.md)

- [도구 모음 도구 설명](../mfc/toolbar-tool-tips.md)

- [ToolBar 컨트롤 사용](../mfc/working-with-the-toolbar-control.md)

- [이전 도구 모음 사용](../mfc/using-your-old-toolbars.md)

- 합니다 [CToolBar](../mfc/reference/ctoolbar-class.md) 하 고 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) 클래스

## <a name="see-also"></a>참고자료

[도구 모음](../mfc/toolbars.md)<br/>
[도구 모음 편집기](../windows/toolbar-editor.md)
