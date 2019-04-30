---
title: MFC의 상태 표시줄 구현
ms.date: 11/19/2018
f1_keywords:
- COldStatusBar
helpviewer_keywords:
- status bars [MFC], implementing in MFC
- CStatusBarCtrl class [MFC], and MFC status bars
- CStatusBar class [MFC], and CStatusBarCtrl class [MFC]
- CStatusBarCtrl class [MFC], and CStatusBar class [MFC]
- status bars [MFC], backward compatibility
- status bars [MFC], old with COldStatusBar class [MFC]
- COldStatusBar class [MFC]
- status bars [MFC], and CStatusBarCtrl class
- CStatusBar class [MFC], and MFC status bars
- status indicators
- status bars [MFC], Windows 95 implementation
ms.assetid: be5cd876-38e3-4d5c-b8cb-16d57a16a142
ms.openlocfilehash: abd16ecb5e6a492bc42c747f60ec0859e1bc05cb
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346403"
---
# <a name="status-bar-implementation-in-mfc"></a>MFC의 상태 표시줄 구현

A [CStatusBar](../mfc/reference/cstatusbar-class.md) 개체의 텍스트 출력 창 행이 있는 컨트롤 막대입니다. 출력 창 메시지 줄으로 상태 표시기에 자주 사용 됩니다. 선택한 메뉴 명령을 간략하게 설명 하는 메뉴 도움말 메시지 줄 고 SCROLL LOCK, NUM LOCK 및 기타 키의 상태를 나타내는 표시기를 예로 들 수 있습니다.

클래스를 사용 하 여 상태 표시줄은 구현 하는 MFC 버전 4.0부터 [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md), 모음 공용 컨트롤 상태를 캡슐화 합니다. MFC 클래스의 이전 상태 표시줄 구현 유지 하면서 이전 버전과 호환성을 위해 `COldStatusBar`합니다. 이전 버전의 MFC에 대 한 설명서에 설명 합니다 `COldStatusBar` 아래에서 `CStatusBar`합니다.

[CStatusBar::GetStatusBarCtrl](../mfc/reference/cstatusbar-class.md#getstatusbarctrl), 멤버 함수는 새 MFC 4.0 허용 상태 표시줄 사용자 지정 및 추가 기능에 대 한 Windows 공용 컨트롤 지원 기능을 사용할 수 있습니다. `CStatusBar` 멤버 함수는 대부분의 Windows 공용 컨트롤;의 기능 제공. 그러나 호출 하는 경우 `GetStatusBarCtrl`, 상태 표시줄의 특징 중 더 상태 표시줄에를 지정할 수 있습니다. 호출 하는 경우 `GetStatusBarCtrl`에 대 한 참조를 반환 합니다를 `CStatusBarCtrl` 개체입니다. 상태 표시줄 컨트롤을 조작 하는 참조를 사용할 수 있습니다.

다음 그림에는 몇 가지 지표를 표시 하는 상태 표시줄을 보여 줍니다.

![상태 표시줄](../mfc/media/vc37dy1.gif "상태 표시줄") <br/>
상태 표시줄

도구 모음과 같은 상태 표시줄 개체 부모 프레임 창에 포함 된 및 프레임 창 생성 될 때 자동으로 생성 됩니다. 모든 컨트롤 막대와 같은 상태 표시줄을 자동으로 제거도 부모 프레임 소멸 될 때입니다.

## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [상태 표시줄 창의 텍스트 업데이트](../mfc/updating-the-text-of-a-status-bar-pane.md)

- MFC 클래스 [CStatusBar](../mfc/reference/cstatusbar-class.md) 고 [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)

- [컨트롤 막대](../mfc/control-bars.md)

- [대화 상자 모음](../mfc/dialog-bars.md)

- [도구 모음 (MFC 도구 모음 구현)](../mfc/mfc-toolbar-implementation.md)

## <a name="see-also"></a>참고자료

[상태 표시줄](../mfc/status-bars.md)
