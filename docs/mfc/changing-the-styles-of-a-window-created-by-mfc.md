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
ms.openlocfilehash: 0a002badf9c20ca7b2d1a129eca069e586893f3c
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344201"
---
# <a name="changing-the-styles-of-a-window-created-by-mfc"></a>MFC에서 만든 창 스타일 변경

해당 버전의 `WinMain` MFC 함수를 여러 표준 창 클래스를 등록 합니다. MFC의 정상적으로 편집할 없는 `WinMain`는 함수를 사용 하면 MFC 기본 창 스타일을 변경할 수 없습니다. 이 문서에서는 기존 응용 프로그램에서 이러한 대답할 미리 등록 된 창 클래스 스타일을 변경 하는 방법을 설명 합니다.

##  <a name="_core_changing_styles_in_a_new_mfc_application"></a> 새 MFC 응용 프로그램에서 스타일 변경

시각적 개체를 사용 하는 경우 C++ 응용 프로그램을 만들 때 응용 프로그램 마법사의 기본 창 스타일 2.0 이상 변경할 수 있습니다. 응용 프로그램 마법사의 사용자 인터페이스 기능 페이지를 주 프레임 창 고 MDI 자식 창에 대 한 스타일을 변경할 수 있습니다. 창 유형 중 하나에 대 한 해당 프레임 두께 (굵은 또는 씬)를 지정할 수 있습니다 및 다음 중 하나:

- 창은 최소화 또는 최대화 컨트롤에 있는지 여부.

- 창의 표시 여부 처음에 최소화, 최대화 하거나 사용 하지 않도록 합니다.

주 프레임 창에 대 한 창의 시스템 메뉴에 있는지 여부를 지정할 수 있습니다. MDI 자식 창, 창 분할기 창을 지원 하는지 여부를 지정할 수 있습니다.

##  <a name="_core_changing_styles_in_an_existing_application"></a> 기존 응용 프로그램에 대 한 스타일 변경

기존 응용 프로그램에서 창 특성 변경 하는 경우 대신이 문서의 나머지 부분에서 지침을 따릅니다.

응용 프로그램 마법사로 만든 프레임 워크 응용 프로그램에서 사용 된 기본 창 특성 변경 하려면 창의 재정의 [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow) 가상 멤버 함수입니다. `PreCreateWindow` 일반적으로 내부적으로 관리 하 여 만들기 프로세스에 액세스 하려면 응용 프로그램을 허용 합니다 [CDocTemplate](../mfc/reference/cdoctemplate-class.md) 클래스입니다. 프레임 워크 호출 `PreCreateWindow` 창을 만드는 직전입니다. 수정 하 여 합니다 [CREATESTRUCT](/windows/desktop/api/winuser/ns-winuser-tagcreatestructa) 구조에 전달 된 `PreCreateWindow`, 응용 프로그램 창을 만들기 위해 사용 된 특성을 변경할 수 있습니다. 예를 들어을 보장 하기 위해 창 캡션을 사용 하 여 사용 하지 않는 다음 연산을 사용 합니다.

[!code-cpp[NVC_MFCDocView#15](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_1.cpp)]

합니다 [CTRLBARS](../overview/visual-cpp-samples.md) 샘플 응용 프로그램에 창 특성 변경에 대 한이 기술을 보여 줍니다. 응용 프로그램에서 변경 내용에 따라 `PreCreateWindow`, 함수의 기본 클래스 구현을 호출 하는 일을 할 수 있습니다.

다음 논의에서는 SDI 사례를 설명 하며 [MDI 사례](#_core_the_mdi_case)합니다.

##  <a name="_core_the_sdi_case"></a> SDI 경우

단일 문서 인터페이스 (SDI) 응용 프로그램 프레임 워크의 기본 창 스타일의 조합을 합니다 **WS_OVERLAPPEDWINDOW** 하 고 **FWS_ADDTOTITLE** 스타일입니다. **FWS_ADDTOTITLE** 은 창의 캡션 문서 제목을 추가 하기 위해 프레임 워크에 지시 하는 MFC 관련 스타일입니다. SDI 응용 프로그램에서 창 특성 변경 하려면 재정의 `PreCreateWindow` 에서 파생 된 클래스에서 함수 `CFrameWnd` (하는 응용 프로그램 마법사 이름을 `CMainFrame`). 예를 들어:

[!code-cpp[NVC_MFCDocViewSDI#11](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_2.cpp)]

이 코드를 주 프레임 창 테두리를 크기 조정 가능 하지 않고 최소화 및 최대화 단추를 만듭니다. 창 가운데 처음에 화면에 표시 됩니다.

##  <a name="_core_the_mdi_case"></a> MDI 경우

좀 더 많은 작업은 여러 문서 MDI (인터페이스) 응용 프로그램에서 자식 창의 창 스타일을 변경 해야 합니다. 기본적으로 응용 프로그램 마법사를 사용 하 여 만든 MDI 응용 프로그램에서는 기본 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) MFC에 정의 된 클래스입니다. MDI 자식 창에 창 스타일을 변경 하려면 새 클래스에서 파생 시켜야 `CMDIChildWnd` 에 대 한 모든 참조를 바꾸고 `CMDIChildWnd` 새 클래스에 대 한 참조를 사용 하 여 프로젝트에서. 대부분의 경우에 대 한 유일한 참조가 `CMDIChildWnd` 응용 프로그램에 위치한 응용 프로그램의 `InitInstance` 멤버 함수입니다.

MDI 응용 프로그램에 사용 되는 기본 창 스타일의 조합을는 **WS_CHILD**를 **WS_OVERLAPPEDWINDOW**, 및 **FWS_ADDTOTITLE** 스타일입니다. MDI 응용 프로그램의 자식 창의 창 특성 변경 하려면 재정의 [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow) 에서 파생 된 클래스에서 함수 `CMDIChildWnd`합니다. 예를 들어:

[!code-cpp[NVC_MFCDocView#16](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_3.cpp)]

이 코드는 최대화 단추 없이 windows MDI 자식을 만듭니다.

### <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [Windows 스타일](../mfc/reference/styles-used-by-mfc.md#window-styles)

- [프레임 창 스타일](../mfc/frame-window-styles-cpp.md)

- [창 스타일](/windows/desktop/winmsg/window-styles)

## <a name="see-also"></a>참고자료

[프레임 창 스타일](../mfc/frame-window-styles-cpp.md)
