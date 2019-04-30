---
title: MDI 자식 창 관리
ms.date: 11/19/2018
f1_keywords:
- MDICLIENT
helpviewer_keywords:
- MDI [MFC], child windows
- child windows [MFC], and MDICLIENT window
- MDICLIENT window [MFC]
- windows [MFC], MDI
- frame windows [MFC], MDI child windows
- child windows [MFC]
- MDI [MFC], frame windows
ms.assetid: 1828d96e-a561-48ae-a661-ba9701de6bee
ms.openlocfilehash: d4b4a4876f47452361b13837b0279f5bf98f8658
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62279351"
---
# <a name="managing-mdi-child-windows"></a>MDI 자식 창 관리

MDI 주 프레임 창 (응용 프로그램 당 하나)는 MDICLIENT 창 이라는 특수 한 자식 창을 포함 합니다. MDICLIENT 창 주 프레임 창의 클라이언트 영역을 관리 하 고 자식 창 자체에:에서 파생 된 문서 창인 `CMDIChildWnd`합니다. 문서 창은 그 자체로 프레임 창(MDI 자식 창)이기 때문에 고유 자식을 포함할 수도 있습니다. 이러한 모든 경우, 부모 창은 해당 자식 창을 관리하고 일부 명령을 자식 창에 전달합니다.

MDI 프레임 창에서 프레임 창은 컨트롤 막대를 사용 하 여 함께 MDICLIENT 창을 관리 합니다. MDICLIENT 창에는 차례로 모든 MDI 자식 프레임 창을 관리합니다. 다음 그림은 MDI 프레임 창, 해당 MDICLIENT 창 및 해당 자식 문서 프레임 창 사이의 관계를 보여 줍니다.

![MDI 프레임 창의 자식 창](../mfc/media/vc37gb1.gif "MDI 프레임 창의 자식 창") <br/>
MDI 프레임 창 및 자식

MDI 프레임 창은 또한 현재 MDI 자식 창(있는 경우)과 결합한 상태에서도 작동합니다. MDI 프레임 창은 명령 메시지를 직접 처리하려고 시도하기 전에 이를 먼저 MDI 자식에 위임합니다.

## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [문서 프레임 창 만들기](../mfc/creating-document-frame-windows.md)

- [프레임 창 스타일](../mfc/frame-window-styles-cpp.md)

## <a name="see-also"></a>참고자료

[프레임 창 사용](../mfc/using-frame-windows.md)
