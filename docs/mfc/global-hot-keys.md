---
title: 전역 바로 가기 키
ms.date: 11/04/2016
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- CHotKeyCtrl class [MFC], global hot keys
- access keys [MFC], hot keys
- global hot keys [MFC]
ms.assetid: e0b95d14-c571-4c9a-9cd1-e7fc1f0e278d
ms.openlocfilehash: eedeb0547320c8b421fa72647f51b02f834af300
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62219608"
---
# <a name="global-hot-keys"></a>전역 바로 가기 키

전역 바로 가기 키를 특정 비 자식 창에 연관 됩니다. 사용자를 시스템의 모든 부분에서 창을 활성화를 수 있습니다. 보내 특정 창에 대 한 전역 바로 가기 키를 설정 하는 응용 프로그램을 [WM_SETHOTKEY](/windows/desktop/inputdev/wm-sethotkey) 창에는 메시지입니다. 예를 들어 경우 `m_HotKeyCtrl` 되는 [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md) 개체 및 `pMainWnd` 포인터가 바로 가기 키를 누르면 활성화할 창으로 컨트롤에 지정 된 바로 가기 키를 연결 하려면 다음 코드를 사용할 수 있습니다 창에서 가리키는 `pMainWnd`합니다.

[!code-cpp[NVC_MFCControlLadenDialog#18](../mfc/codesnippet/cpp/global-hot-keys_1.cpp)]

전역 바로 가기 키를 누를 때마다 지정 된 창의 수신 된 [WM_SYSCOMMAND](/windows/desktop/menurc/wm-syscommand) 지정 하는 메시지 **SC_HOTKEY** 명령 형식으로 합니다. 이 메시지는 수신 하는 창도 활성화 합니다. 이 메시지는 정확한 키를 눌렀는지에 대 한 정보 포함 되어 있지 않으므로,이 메서드를 사용 하 여 없도록 동일한 창에 연결 될 수 있는 다양 한 바로 가기 키를 구별 합니다. 전송한 응용 프로그램 바로 가기 키까지 유효 **WM_SETHOTKEY** 종료 합니다.

## <a name="see-also"></a>참고자료

[CHotKeyCtrl 사용](../mfc/using-chotkeyctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
