---
title: 프레임 창 스타일(C++)
ms.date: 11/04/2016
helpviewer_keywords:
- window styles [MFC]
- PreCreateWindow method, setting window styles
- windows [MFC], MFC
- frame windows [MFC], styles
- MFC, frame windows
- styles [MFC], windows
ms.assetid: fc5058c1-eec8-48d8-9f76-3fc01cfa53f7
ms.openlocfilehash: cade8e7e50779437feb73a94058dc62118c03c10
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62219745"
---
# <a name="frame-window-styles-c"></a>프레임 창 스타일(C++)

프레임 창 프레임 워크를 통해 얻을 수 있는 대부분의 프로그램에 적합 하지만 고급 함수를 사용 하 여 추가적인 유연성을 얻을 수 있습니다 [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow) MFC 전역 함수 및 [AfxRegisterWndClass ](../mfc/reference/application-information-and-management.md#afxregisterwndclass). `PreCreateWindow` 멤버 함수는 `CWnd`합니다.

적용 하는 경우는 **WS_HSCROLL** 및 **WS_VSCROLL** 주 프레임 창 스타일을 대신 적용 되는 **MDICLIENT** 사용자는 스크롤할수있도록창**MDICLIENT** 영역입니다.

경우 창의 **FWS_ADDTOTITLE** 스타일 비트가 설정 되 면 (기본적으로 상태), 뷰 보기의 문서 이름을 기반으로 하는 창의 제목 표시줄에 표시할 제목을 프레임 창에 알립니다.

## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [MDI 자식 창 (MDICLIENT) 관리](../mfc/managing-mdi-child-windows.md), MDI 자식 창을 포함 하는 MDI 프레임 창의

- [MFC에서 만든 창 스타일 변경](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)

- [창 스타일](../mfc/reference/styles-used-by-mfc.md#window-styles)

## <a name="see-also"></a>참고자료

[프레임 창](../mfc/frame-windows.md)
