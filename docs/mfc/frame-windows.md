---
title: 프레임 창
ms.date: 11/19/2018
helpviewer_keywords:
- document frame windows [MFC]
- windows [MFC], MDI
- window classes [MFC], frame
- single document interface (SDI) [MFC]
- single document interface (SDI) [MFC], frame windows
- views [MFC], and frame windows
- CFrameWnd class [MFC], frame windows
- frame windows [MFC]
- frame windows [MFC], about frame windows
- MFC, frame windows
- MDI [MFC], frame windows
- splitter windows [MFC], and frame windows
ms.assetid: 40677339-8135-4f5e-aba6-3fced3078077
ms.openlocfilehash: 939230753f25db38e6ba2f26340f40ddf74d23bf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62219839"
---
# <a name="frame-windows"></a>프레임 창

응용 프로그램이 Windows를 실행 하는 경우 문서 프레임 창에 표시를 사용 하 여 사용자 상호 작용 합니다. 문서 프레임 창에 두 가지 주요 구성 요소: 것의 프레임이 되는 내용과 프레임입니다. 문서 프레임 창 수를 [단일 문서 인터페이스](../mfc/sdi-and-mdi.md) (SDI) 프레임 창 또는 [다중 문서 인터페이스](../mfc/sdi-and-mdi.md) (MDI) 자식 창. Windows 관리 프레임 창 사용 하 여 사용자의 상호 작용의 대부분이: 이동 하 고 창의 크기를 조정에서는 닫기, 최소화 및 최대화 합니다. 콘텐츠 프레임 내에서 관리합니다.

## <a name="frame-windows-and-views"></a>Windows 프레임 및 보기

MFC 프레임 워크는 프레임 창을 사용 하 여 보기가 포함 되어 있습니다. 두 구성 요소-프레임 및 콘텐츠-표시 되 고 MFC의 두 다른 클래스에 의해 관리 됩니다. 프레임 창 클래스는 프레임을 관리 하 고 뷰 클래스 콘텐츠를 관리 합니다. 보기 프레임 창의 자식입니다. 그리기 및 문서를 사용 하 여 사용자 상호 작용이 없습니다 프레임 창의 클라이언트 영역 보기의 클라이언트 영역에서 수행 합니다. 프레임 창의 캡션 표시줄을 최소화 하 고 창을 최대화 단추 컨트롤 메뉴와 같은 표준 창 컨트롤을 사용 하 여 전체 뷰 주위에 보이는 프레임을 제공 하 고 창의 크기를 조정 하는 것에 대 한 제어 합니다. "콘텐츠" 자식 창에서 완벽 하 게 사용 되 고 있는 창의 클라이언트 영역의 구성-보기. 다음 그림 프레임 창 및 뷰 간의 관계를 보여 줍니다.

![프레임 창 보기](../mfc/media/vc37fx1.gif "프레임 창 보기") <br/>
프레임 창 및 뷰

## <a name="frame-windows-and-splitter-windows"></a>프레임 Windows 및 Windows 분할자

다른 일반적인 정렬은 프레임 창을 여러 뷰를 사용 하 여 일반적으로 프레임을 [분할기 창](../mfc/multiple-document-types-views-and-frame-windows.md)합니다. 분할기 창에서 프레임 창의 클라이언트 영역 있으며 뷰가 창 이라고 하는 여러 자식 창에서 분할자 창에서 사용 중입니다.

### <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

**프레임 창의 일반 항목**

- [창 개체](../mfc/window-objects.md)

- [프레임 창 클래스](../mfc/frame-window-classes.md)

- [응용 프로그램 마법사로 만든 프레임 창 클래스](../mfc/frame-window-classes-created-by-the-application-wizard.md)

- [프레임 창 스타일](../mfc/frame-window-styles-cpp.md)

- [프레임 창의 기능](../mfc/what-frame-windows-do.md)

**프레임 Windows를 사용 하 여에 대 한 항목**

- [프레임 창 사용](../mfc/using-frame-windows.md)

- [문서 프레임 창 만들기](../mfc/creating-document-frame-windows.md)

- [프레임 창 제거](../mfc/destroying-frame-windows.md)

- [MDI 자식 창 관리](../mfc/managing-mdi-child-windows.md)

- [현재 뷰 관리](../mfc/managing-the-current-view.md) 둘 이상의 뷰가 포함 된 프레임 창에서

- [메뉴, 컨트롤 막대 및 액셀러레이터 키 (프레임 창의 공간을 공유 하는 다른 개체)를 관리 합니다.](../mfc/managing-menus-control-bars-and-accelerators.md)

**프레임 창의 특수 기능에 대 한 항목**

- [파일 끌어서 놓기](../mfc/dragging-and-dropping-files-in-a-frame-window.md) 파일 탐색기 또는 파일 관리자 프레임 창에

- [동적 데이터 교환 (DDE)에 응답](../mfc/responding-to-dynamic-data-exchange-dde.md)

- [세미 모달 상태: 상황에 맞는 Windows 도움말 (기타 창 작업 조정)](../mfc/orchestrating-other-window-actions.md)

- [세미 모달 상태: 인쇄 및 인쇄 미리 보기 (기타 창 작업 조정)](../mfc/orchestrating-other-window-actions.md)

**다른 종류의 Windows에 대 한 항목**

- [뷰 사용](../mfc/using-views.md)

- [대화 상자](../mfc/dialog-boxes.md)

- [컨트롤](../mfc/controls-mfc.md)

## <a name="see-also"></a>참고자료

[Windows](../mfc/windows.md)
