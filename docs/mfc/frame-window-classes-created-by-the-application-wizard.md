---
title: 응용 프로그램 마법사로 만든 프레임 창 클래스
ms.date: 11/04/2016
f1_keywords:
- CMainFrame
helpviewer_keywords:
- application wizards [MFC], frame window classes created by
- window classes [MFC]
- classes [MFC], frame-window
- CMDIFrameWnd class [MFC], frame windows
- window classes [MFC], frame
- CFrameWnd class [MFC], frame windows
- CMDIChildWnd class [MFC], frame windows
- frame window classes [MFC], created by application wizards
- CMainFrame class [MFC]
ms.assetid: 9947df73-4470-49a0-ac61-7b6ee401a74e
ms.openlocfilehash: 46da8fc0cb98406bdf97285d7c6f824afd61c4bb
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57808354"
---
# <a name="frame-window-classes-created-by-the-application-wizard"></a>응용 프로그램 마법사로 만든 프레임 창 클래스

프로젝트를 새 MFC를 만들 수는 경우는 **새 프로젝트** 대화 상자에서 응용 프로그램, 문서 및 뷰 클래스를 실행 하는 것 외에도 응용 프로그램 마법사는 응용 프로그램의 주 프레임 창에 대 한 파생된 프레임 창 클래스를 만듭니다. 클래스 라고 `CMainFrame` 포함 된 파일과 기본적으로는 해당 이름이 지정 됩니다. H와 해당 합니다. CPP 합니다.

응용 프로그램이 SDI와 경우에 `CMainFrame` 클래스에서 파생 된 클래스 [CFrameWnd](../mfc/reference/cframewnd-class.md)합니다.

응용 프로그램은 MDI `CMainFrame` 클래스에서 파생 되며 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)합니다. 이 경우 `CMainFrame` 메뉴, 도구 모음 및 상태 표시줄을 보유 하는 주 프레임을 구현 합니다. 응용 프로그램 마법사는 새 문서 프레임 창 클래스를 파생 되지 않습니다. 기본 구현을 사용 하 여 대신 [CMDIChildWnd 클래스](../mfc/reference/cmdichildwnd-class.md)합니다. MFC 프레임 워크에는 각 뷰에 포함 하도록 자식 창을 만듭니다 (형식일 수 있는 `CScrollView`, `CEditView`를 `CTreeView`, `CListView`등) 응용 프로그램에서 필요한 합니다. 문서 프레임 창에 사용자 지정 해야 하는 경우 새 문서 프레임 창 클래스를 만들 수 있습니다 (참조 [클래스 추가](../ide/adding-a-class-visual-cpp.md)).

클래스 형식의 멤버 변수 또한에 도구 모음을 지원 하려는 경우 [CToolBar](../mfc/reference/ctoolbar-class.md) 하 고 [CStatusBar](../mfc/reference/cstatusbar-class.md) 와 `OnCreate` 메시지 처리기 함수를 두 초기화 [ 컨트롤 막대](../mfc/control-bars.md)합니다.

이러한 프레임 창 클래스 생성 하는 대로 작동 하지만 해당 기능을 강화 하려면 멤버 변수 및 멤버 함수를 추가 해야 합니다. 다른 Windows 메시지를 처리 하 여 창 클래스를 할 수도 있습니다. 자세한 내용은 [MFC에서 만든 창 스타일 변경](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)합니다.

## <a name="see-also"></a>참고자료

[프레임 창 클래스](../mfc/frame-window-classes.md)<br/>
[MFC 프로그램 또는 컨트롤 소스 및 헤더 파일](../build/reference/mfc-program-or-control-source-and-header-files.md)

