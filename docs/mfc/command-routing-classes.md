---
title: 명령 라우팅 클래스
ms.date: 11/04/2016
f1_keywords:
- vc.classes.command
helpviewer_keywords:
- MFC, command routing
- command routing [MFC], classes
ms.assetid: 4b50e689-2c54-4e6c-90f0-37333e22b2a1
ms.openlocfilehash: 264e931ba0468cdc44f27c55e5d259948c5392b5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406056"
---
# <a name="command-routing-classes"></a>명령 라우팅 클래스

메뉴 또는 마우스를 사용 하 여 컨트롤 막대 단추를 선택 하 여 상호 작용 하는 응용 프로그램을 사용 하 여 사용자를 응용 프로그램 메시지를 적절 한 명령 대상 개체에 영향을 받는 사용자 인터페이스 개체에서 보냅니다. 명령 대상 클래스에서 파생 된 `CCmdTarget` 포함 [CWinApp](../mfc/reference/cwinapp-class.md), [CWnd](../mfc/reference/cwnd-class.md)를 [CDocTemplate](../mfc/reference/cdoctemplate-class.md), [CDocument](../mfc/reference/cdocument-class.md)합니다 [CView](../mfc/reference/cview-class.md), 클래스를 파생 합니다. 프레임 워크는 자동 명령 라우팅 명령을 응용 프로그램에서 현재 활성 상태인 가장 적합 한 개체에 의해 처리 될 수 있도록 지원 합니다.

클래스의 개체 `CCmdUI` 명령 대상의 업데이트 명령 UI에 전달 됩니다 ([ON_UPDATE_COMMAND_UI](reference/message-map-macros-mfc.md#on_update_command_ui)) 특정 명령에 대 한 사용자 인터페이스의 상태를 업데이트할 수 있도록 하는 처리기 (예를 들어에 check 또는 제거 검사를 메뉴 항목에서)입니다. 멤버 함수를 호출 합니다 `CCmdUI` UI 개체의 상태를 업데이트 하는 개체입니다. UI 개체가 특정 명령과 사용 하 여 연결 된 메뉴 항목 또는 단추 인지이 프로세스는 동일 합니다.

[CCmdTarget](../mfc/reference/ccmdtarget-class.md)<br/>
수신 하 고 메시지에 응답할 수 있는 개체의 모든 클래스에 대 한 기본 클래스로 사용 됩니다.

[CCmdUI](../mfc/reference/ccmdui-class.md)<br/>
메뉴 항목 또는 컨트롤 막대 단추와 같은 사용자 인터페이스 개체 업데이트에 대 한 프로그래밍 인터페이스를 제공 합니다. 명령 대상 개체를 사용 하도록 설정, 사용 하지 않도록 설정, 검사 및/또는이 개체를 사용 하 여 사용자 인터페이스 개체를 지웁니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../mfc/class-library-overview.md)
