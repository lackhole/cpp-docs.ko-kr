---
title: 프레임 창의 기능
ms.date: 11/04/2016
helpviewer_keywords:
- frame windows [MFC], about frame windows
- frame windows [MFC], tasks
- MFC, frame windows
ms.assetid: 1148a952-6786-4622-b5a8-68a2d7eae584
ms.openlocfilehash: 594700ef1cbe0030bbe452adaa40b29b4a72f4d0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405679"
---
# <a name="what-frame-windows-do"></a>프레임 창의 기능

단순한 뷰 프레임 지정 외에도 프레임 창은 프레임을 해당 뷰 및 애플리케이션에서 조정하는 것과 관련된 여러 작업을 수행합니다. [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) 하 고 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) 에서 상속 [CFrameWnd](../mfc/reference/cframewnd-class.md)갖게 되므로 `CFrameWnd` 기능 뿐만 아니라 추가 된 새로운 기능입니다. 자식 창 예에는 뷰, 단추 및 목록 상자와 같은 컨트롤, 도구 모음, 상태 표시줄 및 대화 상자 막대를 비롯한 컨트롤 막대가 포함됩니다.

프레임 창은 해당 자식 창의 레이아웃을 관리합니다. MFC 프레임워크에서 프레임 창은 클라이언트 영역 내에 모든 컨트롤 막대, 뷰 및 기타 자식 창을 배치합니다.

프레임 창은 또한 명령을 해당 뷰로 전달하며, 컨트롤 창으로부터 알림 메시지에 응답할 수 있습니다.

## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [컨트롤 막대 (에 속하는 방법 프레임 창)](../mfc/control-bars.md)

- [메뉴, 컨트롤 막대 및 액셀러레이터 키 (에 속하는 방법 프레임 창) 관리](../mfc/managing-menus-control-bars-and-accelerators.md)

- [명령 라우팅 (의 프레임 창에서 해당 뷰 및 기타 명령 대상으로)](../mfc/command-routing.md)

- [문서 /View 아키텍처](../mfc/document-view-architecture.md)

- [컨트롤 막대](../mfc/control-bars.md)

- [컨트롤](../mfc/controls-mfc.md)

## <a name="see-also"></a>참고자료

[프레임 창](../mfc/frame-windows.md)
