---
title: ToolBar 컨트롤 사용
ms.date: 11/04/2016
helpviewer_keywords:
- GetToolBarCtrl method [MFC]
- toolbars [MFC], accessing common control
- CToolBarCtrl class [MFC], accessing toolbar
- toolbar controls [MFC], accessing
ms.assetid: b19409d5-3831-42c7-80ae-195c49dc9085
ms.openlocfilehash: 88c00bf60f2ce1fccecd757d13b2f814e3a18be4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399501"
---
# <a name="working-with-the-toolbar-control"></a>ToolBar 컨트롤 사용

이 문서에서는 액세스 하는 방법을 설명 합니다 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) 개체 내부를 [CToolBar](../mfc/reference/ctoolbar-class.md) 도구 모음 보다 효율적으로 제어 합니다. 고급 항목입니다.

## <a name="procedures"></a>절차

#### <a name="to-access-the-toolbar-common-control-underlying-your-ctoolbar-object"></a>CToolBar 개체를 기본 도구 모음 공용 컨트롤에 액세스

1. 호출 [CToolBar::GetToolBarCtrl](../mfc/reference/ctoolbar-class.md#gettoolbarctrl)합니다.

`GetToolBarCtrl` 에 대 한 참조를 반환 합니다는 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) 개체입니다. 도구 모음 컨트롤 클래스의 멤버 함수 호출에 대 한 참조를 사용할 수 있습니다.

> [!CAUTION]
>  호출 하는 동안 `CToolBarCtrl` **가져올** 함수를 안전 하 게 호출 하는 경우 주의 해야 합니다 **설정** 함수입니다. 고급 항목입니다. 일반적으로 기본 도구 모음 컨트롤에 액세스할 필요가 없습니다.

### <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [컨트롤 (Windows 공용 컨트롤)](../mfc/controls-mfc.md)

- [도구 모음 기본 사항](../mfc/toolbar-fundamentals.md)

- [도킹 및 부동 도구 모음](../mfc/docking-and-floating-toolbars.md)

- [도구 모음을 동적으로 크기 조정](../mfc/docking-and-floating-toolbars.md)

- [도구 모음 도구 설명](../mfc/toolbar-tool-tips.md)

- [Flyby 상태 표시줄 업데이트](../mfc/toolbar-tool-tips.md)

- [도구 설명 알림 처리](../mfc/handling-tool-tip-notifications.md)

- 합니다 [CToolBar](../mfc/reference/ctoolbar-class.md) 하 고 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) 클래스

- [사용자 지정 알림 처리](../mfc/handling-customization-notifications.md)

- [여러 도구 모음](../mfc/toolbar-fundamentals.md)

- [이전 도구 모음 사용](../mfc/using-your-old-toolbars.md)

- [컨트롤 막대](../mfc/control-bars.md)

Windows 공용 컨트롤을 사용 하는 방법에 대 한 일반적인 정보를 참조 하세요 [공용 컨트롤](/windows/desktop/Controls/common-controls-intro)합니다.

## <a name="see-also"></a>참고자료

[MFC 도구 모음 구현](../mfc/mfc-toolbar-implementation.md)
