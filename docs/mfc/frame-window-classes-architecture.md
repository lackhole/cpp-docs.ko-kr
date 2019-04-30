---
title: 프레임 창 클래스(아키텍처)
ms.date: 11/04/2016
f1_keywords:
- vc.classes.frame
helpviewer_keywords:
- frame window classes [MFC], document/view architecture
ms.assetid: 5da01fb4-f531-46cc-914f-e422e4f07f5d
ms.openlocfilehash: affa217f481cc6d9e125d526f1b97be9120e0990
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392845"
---
# <a name="frame-window-classes-architecture"></a>프레임 창 클래스(아키텍처)

문서/뷰 아키텍처, 프레임 창에는 뷰 창을 포함 하는 windows. 또한 지원 제어 하지 막대에 연결 합니다.

여러 문서 MDI (인터페이스) 응용 프로그램에서 주 창에서 파생 된 `CMDIFrameWnd`합니다. 이 간접적으로 포함 되는 문서 프레임 `CMDIChildWnd` 개체입니다. `CMDIChildWnd` 개체의 문서 뷰를 포함 합니다.

단일 문서 인터페이스 (SDI) 응용 프로그램 주 창에서 파생 된 `CFrameWnd`, 현재 문서의 뷰를 포함 합니다.

[CFrameWnd](../mfc/reference/cframewnd-class.md)<br/>
SDI 응용 프로그램의 주 프레임 창에 대 한 기본 클래스입니다. 기본 다른 모든 프레임 창 클래스에 대 한 클래스는 또한만 합니다.

[CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)<br/>
MDI 응용 프로그램의 주 프레임 창에 대 한 기본 클래스입니다.

[CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)<br/>
MDI 응용 프로그램의 문서 프레임 창에 대 한 기본 클래스입니다.

[클래스에서 파생하는 대신](../mfc/reference/coleipframewnd-class.md)<br/>
준비에서 서버 문서를 편집 하는 경우 프레임 창 보기를 제공 합니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../mfc/class-library-overview.md)
