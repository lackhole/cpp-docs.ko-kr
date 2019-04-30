---
title: 프레임 창 클래스
ms.date: 11/04/2016
helpviewer_keywords:
- frame window classes [MFC], about frame window classes
- frame window classes [MFC]
- windows [MFC], MDI
- document frame windows [MFC], classes
- single document interface (SDI), frame windows
- window classes [MFC], frame
- MFC, frame windows
- MDI [MFC], frame windows
- classes [MFC], window
ms.assetid: c27e43a7-8ad0-4759-b1b7-43f4725f4132
ms.openlocfilehash: d42fa475fca7c92e4ba46b164a9beda9869231c4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62219784"
---
# <a name="frame-window-classes"></a>프레임 창 클래스

각 응용 프로그램에 "주 프레임 창," 캡션을에서 응용 프로그램 이름이 일반적으로 데스크톱 창 하나 있습니다. 각 문서 일반적으로 "문서 프레임 창입니다." 문서 프레임 창에는 문서의 데이터를 제공 하는 하나 이상의 보기가 있습니다.

## <a name="frame-windows-in-sdi-and-mdi-applications"></a>SDI 및 MDI 응용 프로그램의 프레임 Windows

SDI 응용 프로그램은 하나의 프레임 창 클래스에서 파생 된 [CFrameWnd](../mfc/reference/cframewnd-class.md)합니다. 이 창은 주 프레임 창 및 문서 프레임 창 모두입니다. MDI 응용 프로그램에 대 한 주 프레임 창 클래스에서 파생 된 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)에 MDI 자식 창을 문서 프레임 창 클래스에서 파생 됩니다 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)합니다.

## <a name="use-the-frame-window-class-or-derive-from-it"></a>프레임 창 클래스를 사용 하 여 또는에서 파생

이러한 클래스는 대부분의 응용 프로그램에 필요한 프레임 창 기능을 제공 합니다. 정상적인 상황에서 제공 하는 모양과 기본 동작에 요구에 맞게 됩니다. 추가 기능을 할 경우 이러한 클래스에서 파생 됩니다.

### <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [응용 프로그램 마법사로 만든 프레임 창 클래스](../mfc/frame-window-classes-created-by-the-application-wizard.md)

- [프레임 창 스타일](../mfc/frame-window-styles-cpp.md)

- [MFC에서 만든 창 스타일 변경](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)

## <a name="see-also"></a>참고자료

[프레임 창](../mfc/frame-windows.md)
