---
title: 공용 컨트롤에서 알림 받기
ms.date: 11/04/2016
helpviewer_keywords:
- OnNotify method [MFC]
- common controls [MFC], notifications
- ON_NOTIFY macro [MFC]
- controls [MFC], notifications
- receiving notifications from common controls
- notifications [MFC], common controls
- Windows common controls [MFC], notifications
- WM_NOTIFY message
ms.assetid: 50194592-d60d-44d0-8ab3-338a2a2c63e7
ms.openlocfilehash: 73315d4a1107204bc6adc885729fdeeaeb7f98d0
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75298976"
---
# <a name="receiving-notification-from-common-controls"></a>공용 컨트롤에서 알림 받기

공용 컨트롤은 컨트롤에서 사용자 입력과 같은 이벤트가 발생 하는 경우 부모 창에 알림 메시지를 보내는 자식 창입니다.

응용 프로그램은 이러한 알림 메시지를 사용 하 여 사용자가 원하는 작업을 결정 합니다. 가장 일반적인 컨트롤은 WM_NOTIFY 메시지로 알림 메시지를 보냅니다. Windows 컨트롤은 WM_COMMAND 메시지로 대부분의 알림 메시지를 보냅니다. [CWnd:: OnNotify](../mfc/reference/cwnd-class.md#onnotify) 는 WM_NOTIFY 메시지에 대 한 처리기입니다. `CWnd::OnCommand`와 마찬가지로 `OnNotify`를 구현 하면 메시지 맵에서 처리할 `OnCmdMsg` 알림 메시지를 디스패치합니다. 알림 처리를 위한 메시지 맵 항목이 ON_NOTIFY 되었습니다. 자세한 내용은 [기술 참고 61: ON_NOTIFY 및 WM_NOTIFY 메시지](../mfc/tn061-on-notify-and-wm-notify-messages.md)를 참조 하세요.

또는 파생 클래스가 "메시지 리플렉션"을 사용 하 여 자체 알림 메시지를 처리할 수 있습니다. 자세한 내용은 [Technical Note 62: Windows 컨트롤에 대 한 메시지 리플렉션](../mfc/tn062-message-reflection-for-windows-controls.md)을 참조 하세요.

## <a name="retrieving-the-cursor-position-in-a-notification-message"></a>알림 메시지에서 커서 위치 검색

경우에 따라 공용 컨트롤에서 특정 알림 메시지를 받을 때 커서의 현재 위치를 확인 하는 것이 유용 합니다. 예를 들어 공용 컨트롤이 NM_RCLICK 알림 메시지를 받을 때 현재 커서 위치를 확인 하는 것이 좋습니다.

`CWnd::GetCurrentMessage`를 호출 하 여이를 수행할 수 있는 간단한 방법이 있습니다. 그러나이 메서드는 메시지를 보낸 시점의 커서 위치만 검색 합니다. 메시지가 전송 된 이후 커서가 이동 되었을 수 있으므로 현재 커서 위치를 가져오기 위해 `CWnd::GetCursorPos`를 호출 해야 합니다.

> [!NOTE]
>  `CWnd::GetCurrentMessage`는 메시지 처리기 내 에서만 호출 해야 합니다.

알림 메시지 처리기의 본문에 다음 코드를 추가 합니다 (이 예제에서는 NM_RCLICK).

[!code-cpp[NVC_MFCControlLadenDialog#4](../mfc/codesnippet/cpp/receiving-notification-from-common-controls_1.cpp)]

이때 마우스 커서 위치는 `cursorPos` 개체에 저장 됩니다.

## <a name="see-also"></a>참조

[컨트롤 만들기 및 사용](../mfc/making-and-using-controls.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
