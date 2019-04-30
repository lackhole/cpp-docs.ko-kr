---
title: 도구 설명 컨트롤 조작
ms.date: 11/04/2016
helpviewer_keywords:
- CToolTipCtrl class [MFC], manipulating tool tip attributes
- tool tips [MFC], attributes
ms.assetid: 3600afe5-712a-4b56-8456-96e85fe879af
ms.openlocfilehash: d8c994748239871f17b878dd8ea7505a2a8a0b65
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62226159"
---
# <a name="manipulating-the-tool-tip-control"></a>도구 설명 컨트롤 조작

클래스 `CToolTipCtrl` 멤버의 그룹에는 다양 한 특성을 제어 하는 함수를 제공 합니다 `CToolTipCtrl` 개체 및 도구 설명 창이 있습니다.

팝업을 초기 및 도구 설명 창이 설정 하 고 호출 하 여 검색할 수에 대 한 기간을 reshow [GetDelayTime](../mfc/reference/ctooltipctrl-class.md#getdelaytime) 하 고 [SetDelayTime](../mfc/reference/ctooltipctrl-class.md#setdelaytime)합니다.

다음 함수를 사용 하 여 도구 설명 창의 모양을 변경 합니다.

- [GetMargin](../mfc/reference/ctooltipctrl-class.md#getmargin) 하 고 [SetMargin](../mfc/reference/ctooltipctrl-class.md#setmargin) 도구 설명 테두리와 도구 사이의 너비 팁 텍스트를 검색 하 고 설정 합니다.

- [GetMaxTipWidth](../mfc/reference/ctooltipctrl-class.md#getmaxtipwidth) 하 고 [SetMaxTipWidth](../mfc/reference/ctooltipctrl-class.md#setmaxtipwidth) 도구의 최대 너비를 팁 창 설정 및 검색 합니다.

- [GetTipBkColor](../mfc/reference/ctooltipctrl-class.md#gettipbkcolor) 하 고 [SetTipBkColor](../mfc/reference/ctooltipctrl-class.md#settipbkcolor) 도구의 배경색 팁 창 설정 및 검색 합니다.

- [GetTipTextColor](../mfc/reference/ctooltipctrl-class.md#gettiptextcolor) 하 고 [SetTipTextColor](../mfc/reference/ctooltipctrl-class.md#settiptextcolor) 도구의 텍스트 색 팁 창 설정 및 검색 합니다.

WM_LBUTTONXXX 메시지와 같은 중요 한 메시지를 통보 하 여 도구 설명 컨트롤에서 도구 설명 컨트롤에 메시지를 릴레이 해야 합니다. 이 릴레이 대 한 최상의 메서드를 호출 하는 것 [CToolTipCtrl::RelayEvent](../mfc/reference/ctooltipctrl-class.md#relayevent)를 `PreTranslateMessage` 소유자 창의 함수입니다. 다음 예제에서는 가능한 방법 중 하나를 보여 줍니다 (도구 설명 컨트롤 라고 `m_ToolTip`):

[!code-cpp[NVC_MFCControlLadenDialog#41](../mfc/codesnippet/cpp/manipulating-the-tool-tip-control_1.cpp)]

도구 설명 창이 즉시 제거 하려면 호출을 [팝](../mfc/reference/ctooltipctrl-class.md#pop) 멤버 함수입니다.

## <a name="see-also"></a>참고자료

[CToolTipCtrl 사용](../mfc/using-ctooltipctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
