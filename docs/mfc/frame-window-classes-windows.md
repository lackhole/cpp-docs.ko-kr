---
title: 프레임 창 클래스(Windows)
ms.date: 11/04/2016
f1_keywords:
- vc.classes.frame
helpviewer_keywords:
- frame window classes [MFC], reference
ms.assetid: 6342ec5f-f922-4da8-a78e-2f5f994c7142
ms.openlocfilehash: 3e56bd0f449992118db75a44c39b6e0e15cb0d86
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392795"
---
# <a name="frame-window-classes-windows"></a>프레임 창 클래스(Windows)

프레임 창은 windows 응용 프로그램 또는 응용 프로그램의 일부 프레임입니다. 프레임 창에는 일반적으로 뷰, 도구 모음 및 상태 표시줄과 같은 다른 창을 포함 합니다. 경우 `CMDIFrameWnd`를 포함할 수 `CMDIChildWnd` 직접 개체입니다.

[CFrameWnd](../mfc/reference/cframewnd-class.md)<br/>
SDI 응용 프로그램의 주 프레임 창에 대 한 기본 클래스입니다. 기본 다른 모든 프레임 창 클래스에 대 한 클래스는 또한만 합니다.

[CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)<br/>
MDI 응용 프로그램의 주 프레임 창에 대 한 기본 클래스입니다.

[CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)<br/>
MDI 응용 프로그램의 문서 프레임 창에 대 한 기본 클래스입니다.

[CMiniFrameWnd](../mfc/reference/cminiframewnd-class.md)<br/>
일반적으로 부동 도구 모음을 표시 하는 절반 높이 프레임 창입니다.

[클래스에서 파생하는 대신](../mfc/reference/coleipframewnd-class.md)<br/>
준비에서 서버 문서를 편집 하는 경우 프레임 창 보기를 제공 합니다.

## <a name="related-class"></a>관련된 클래스

클래스 `CMenu` 에 응용 프로그램의 메뉴에 액세스할 수 있는 인터페이스를 제공 합니다. 런타임에 메뉴를 동적으로 조작 하는 데 유용 예를 들어, 추가 또는 컨텍스트에 따라 메뉴 항목을 삭제 하는 경우. 메뉴는 대부분의 프레임 창에서 사용한 있지만 데도 사용할 수 있습니다 다른 비 자식 창 및 대화 상자를 사용 하 여 합니다.

[CMenu](../mfc/reference/cmenu-class.md)<br/>
캡슐화를 `HMENU` 응용 프로그램의 메뉴 모음 및 팝업 메뉴에 대 한 핸들입니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../mfc/class-library-overview.md)
