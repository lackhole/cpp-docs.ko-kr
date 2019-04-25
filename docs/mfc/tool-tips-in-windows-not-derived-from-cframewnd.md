---
title: CFrameWnd에서 파생되지 않은 창의 도구 설명
ms.date: 11/04/2016
helpviewer_keywords:
- enabling tool tips [MFC]
- TOOLTIPTEXT structure [MFC]
- Help [MFC], tool tips for controls
- TTN_NEEDTEXT message [MFC]
- controls [MFC], tool tips
- handler functions [MFC], tool tips
ms.assetid: cad5ef0f-02e3-4151-ad0d-3d42e6932b0e
ms.openlocfilehash: 3d44f2c503b689360f040e6804d319c331d5c0ca
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62168026"
---
# <a name="tool-tips-in-windows-not-derived-from-cframewnd"></a>CFrameWnd에서 파생되지 않은 창의 도구 설명

이 문서에서는 설명에서 파생 되지 않은 창에서 포함 된 컨트롤에 사용 하도록 설정 하면 도구 설명 [CFrameWnd](../mfc/reference/cframewnd-class.md)합니다. 이 문서 [도구 모음 도구 설명](../mfc/toolbar-tool-tips.md) 컨트롤에 대 한 도구 설명에 대 한 정보를 제공는 `CFrameWnd`합니다.

이 문서에서는 제품군에서 다루는 항목은 다음과 같습니다.

- [도구 설명을 사용하도록 설정](../mfc/enabling-tool-tips.md)

- [도구 설명에 대한 TTN_NEEDTEXT 알림 처리](../mfc/handling-ttn-needtext-notification-for-tool-tips.md)

- [TOOLTIPTEXT 구조체](../mfc/tooltiptext-structure.md)

도구 설명은 단추에 대 한 자동으로 표시 되 고 부모 창에 포함 된 다른 컨트롤에서 파생 된 `CFrameWnd`합니다. 왜냐하면 `CFrameWnd` 에 대 한 기본 처리기가 합니다 [TTN_GETDISPINFO](/windows/desktop/Controls/ttn-getdispinfo) 알림을 처리 하는 **TTN_NEEDTEXT** 도구에서 알림 팁 컨트롤과 연결 된 컨트롤입니다.

그러나이 기본 처리기가 호출 되지 경우는 **TTN_NEEDTEXT** 하지 않은 창에서 컨트롤에 연결 된 도구 설명 컨트롤에서 알림이 전송 됩니다는 `CFrameWnd`, 대화 상자나 폼 보기에서 컨트롤과 같은 합니다. 따라서 것에 대 한 처리기 함수를 제공 하는 데 필요한 합니다 **TTN_NEEDTEXT** 자식 컨트롤에 대 한 도구 설명을 표시 하려면 알림 메시지입니다.

제공 하 여 windows에 대 한 기본 도구 설명을 [CWnd::EnableToolTips](../mfc/reference/cwnd-class.md#enabletooltips) 연결 된 텍스트에 있지 않습니다. 표시할 도구 설명에 대 한 텍스트를 검색 하는 **TTN_NEEDTEXT** 도구 설명 창이 표시 되기 직전에 도구 설명 컨트롤의 부모 창에 알림이 전송 됩니다. 일부 값을 할당할이 메시지에 대 한 처리기가 합니다 *pszText* 의 멤버는 **TOOLTIPTEXT** 구조에 없는 텍스트 도구 설명에 표시 됩니다.

## <a name="see-also"></a>참고자료

[도구 설명](../mfc/tool-tips.md)
