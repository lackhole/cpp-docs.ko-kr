---
title: MFC에서 만든 창 스타일 변경
ms.date: 11/04/2016
helpviewer_keywords:
- window styles [MFC]
- WS_OVERLAPPEDWINDOW macro [MFC]
- single document interface (SDI), changing window attributes
- MDI [MFC], window styles
- windows [MFC], MFC
- child windows [MFC], styles
- MFC, windows
- CFrameWnd class [MFC], window styles
- CREATESTRUCT macro [MFC]
- CMDIChildWnd class [MFC], changing window styles
- multidocument interface style
- PreCreateWindow method [MFC], window styles
- single document interface (SDI), style
- default window style
- defaults [MFC], window style
- PreCreateWindow method [MFC], changing window styles
- CMainFrame class [MFC]
- styles [MFC], windows
ms.assetid: 77fa4f03-96b4-4687-9ade-41e46f7e4b0a
ms.openlocfilehash: ef79fc88604d565a942fdb0ae07d5fc5a2e0ebeb
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69509006"
---
# <a name="changing-the-styles-of-a-window-created-by-mfc"></a>MFC에서 만든 창 스타일 변경

`WinMain` 함수 버전의 MFC는 여러 표준 창 클래스를 등록 합니다. 일반적으로 mfc `WinMain`를 편집 하지 않으므로 해당 함수는 mfc 기본 창 스타일을 변경할 수 있는 기회를 제공 하지 않습니다. 이 문서에서는 기존 응용 프로그램에서 이러한 넌 window 클래스의 스타일을 변경 하는 방법을 설명 합니다.

##  <a name="_core_changing_styles_in_a_new_mfc_application"></a>새 MFC 응용 프로그램에서 스타일 변경

Visual C++ 2.0 이상을 사용 하는 경우 응용 프로그램을 만들 때 응용 프로그램 마법사에서 기본 창 스타일을 변경할 수 있습니다. 응용 프로그램 마법사의 사용자 인터페이스 기능 페이지에서 주 프레임 창 및 MDI 자식 창에 대 한 스타일을 변경할 수 있습니다. 각 창 유형에 대해 프레임 두께 (굵은 또는 씬)와 다음 중 하나를 지정할 수 있습니다.

- 창에 최소화 또는 최대화 컨트롤이 있는지 여부입니다.

- 창이 처음에 최소화, 최대화 또는 둘 다 표시 되지 않는지 여부를 나타냅니다.

주 프레임 창의 경우 창에 시스템 메뉴가 있는지 여부도 지정할 수 있습니다. MDI 자식 창의 경우 창에서 분할자 창을 지원할지 여부를 지정할 수 있습니다.

##  <a name="_core_changing_styles_in_an_existing_application"></a>기존 응용 프로그램에서 스타일 변경

기존 응용 프로그램에서 창 특성을 변경 하는 경우 대신이 문서의 나머지 부분에 있는 지침을 따르세요.

응용 프로그램 마법사를 사용 하 여 만든 프레임 워크 응용 프로그램에서 사용 하는 기본 창 특성을 변경 하려면 창의 [Precreatewindow](../mfc/reference/cwnd-class.md#precreatewindow) 가상 멤버 함수를 재정의 합니다. `PreCreateWindow`응용 프로그램이 일반적으로 [Cdoctemplate](../mfc/reference/cdoctemplate-class.md) 클래스에서 내부적으로 관리 하는 생성 프로세스에 액세스할 수 있도록 합니다. 프레임 워크는 `PreCreateWindow` 창을 만들기 직전에를 호출 합니다. 응용 프로그램은에 `PreCreateWindow`전달 된 [createstruct](/windows/win32/api/winuser/ns-winuser-createstructw) 구조체를 수정 하 여 창을 만드는 데 사용 되는 특성을 변경할 수 있습니다. 예를 들어 창이 캡션을 사용 하지 않도록 하려면 다음 비트 연산을 사용 합니다.

[!code-cpp[NVC_MFCDocView#15](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_1.cpp)]

[CTRLBARS](../overview/visual-cpp-samples.md) 샘플 응용 프로그램은 창 특성을 변경 하기 위한이 기법을 보여 줍니다. 응용 프로그램의 변경 `PreCreateWindow`내용에 따라 함수의 기본 클래스 구현을 호출 해야 할 수 있습니다.

다음 토론에서는 SDI 사례 및 [MDI 사례](#_core_the_mdi_case)에 대해 설명 합니다.

##  <a name="_core_the_sdi_case"></a>SDI 사례

SDI (단일 문서 인터페이스) 응용 프로그램에서 프레임 워크의 기본 창 스타일은 **WS_OVERLAPPEDWINDOW** 및 **FWS_ADDTOTITLE** 스타일의 조합입니다. **FWS_ADDTOTITLE** 는 창 캡션에 문서 제목을 추가 하도록 프레임 워크에 지시 하는 MFC 별 스타일입니다. SDI 응용 프로그램의 창 특성을 변경 하려면에서 `PreCreateWindow` `CFrameWnd` 파생 된 클래스의 함수 (응용 프로그램 마법사 이름 `CMainFrame`)를 재정의 합니다. 예를 들어:

[!code-cpp[NVC_MFCDocViewSDI#11](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_2.cpp)]

이 코드는 최소화 및 최대화 단추를 사용 하지 않고 조정 가능 테두리 없이 주 프레임 창을 만듭니다. 창은 초기에 화면 가운데에 배치 됩니다.

##  <a name="_core_the_mdi_case"></a>MDI 사례

MDI (다중 문서 인터페이스) 응용 프로그램에서 자식 창의 창 스타일을 변경 하려면 약간의 작업을 수행 해야 합니다. 기본적으로 응용 프로그램 마법사를 사용 하 여 만든 MDI 응용 프로그램은 MFC에 정의 된 기본 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) 클래스를 사용 합니다. MDI 자식 창에 대 한 창 스타일을 변경 하려면에서 `CMDIChildWnd` 새 클래스를 파생 하 고 프로젝트의에 `CMDIChildWnd` 대 한 모든 참조를 새 클래스에 대 한 참조로 바꾸어야 합니다. 응용 프로그램의에 대 `CMDIChildWnd` 한 참조는 응용 프로그램의 `InitInstance` 멤버 함수에만 있을 가능성이 높습니다.

MDI 응용 프로그램에서 사용 되는 기본 창 스타일은 **WS_CHILD**, **WS_OVERLAPPEDWINDOW**및 **FWS_ADDTOTITLE** 스타일의 조합입니다. MDI 응용 프로그램의 자식 창에 있는 창 특성을 변경 하려면에서 `CMDIChildWnd`파생 된 클래스의 [precreatewindow](../mfc/reference/cwnd-class.md#precreatewindow) 함수를 재정의 합니다. 예를 들어:

[!code-cpp[NVC_MFCDocView#16](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_3.cpp)]

이 코드는 최대화 단추 없이 MDI 자식 창을 만듭니다.

### <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [Windows 스타일](../mfc/reference/styles-used-by-mfc.md#window-styles)

- [프레임 창 스타일](../mfc/frame-window-styles-cpp.md)

- [창 스타일](/windows/win32/winmsg/window-styles)

## <a name="see-also"></a>참고자료

[프레임 창 스타일](../mfc/frame-window-styles-cpp.md)
