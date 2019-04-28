---
title: 메시지 범주
ms.date: 11/04/2016
helpviewer_keywords:
- messages [MFC], categories
- control-notification messages [MFC]
- Windows messages [MFC], categories
- controls [MFC], notifications
- command messages [MFC]
- messages [MFC], Windows
- message handling [MFC], message types
ms.assetid: 68e1db75-9da6-4a4d-b2c2-dc4d59f8d87b
ms.openlocfilehash: 07d9e706e8ed01a81ee580e7c4e11fa1f1a7a8df
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62206882"
---
# <a name="message-categories"></a>메시지 범주

어떤 종류의 메시지 처리기를 작성할 세 가지 주요 범주에 대 한 합니다.

1. Windows 메시지

   여기에 사용 하 여 시작 하는 메시지에 주로 합니다 **WM_** WM_COMMAND 제외 하 고 접두사입니다. Windows 메시지는 windows 및 보기에서 처리 됩니다. 이러한 메시지는 메시지를 처리 하는 방법을 결정 하는 데 사용 되는 매개 변수가 있는 경우가 많습니다.

1. 컨트롤 알림

   부모 창에 WM_COMMAND 알림 메시지에서 컨트롤 및 기타 자식 창을 포함 됩니다. 예를 들어 편집 컨트롤을 사용자가 편집 컨트롤의 텍스트를 변경할 수 있는 동작을 수행한 경우에에서 EN_CHANGE 컨트롤 알림 코드를 포함 하는 WM_COMMAND 메시지 부모를 보냅니다. 창 메시지 처리기는 컨트롤의 텍스트를 검색 하는 등의 적절 한 방법으로 알림 메시지에 응답 합니다.

   프레임 워크는 같은 다른 컨트롤 알림 메시지를 라우팅하고 **WM_** 메시지입니다. 그러나 단, 해당 사용자가 단추를 보낸 BN_CLICKED 컨트롤 알림 메시지를입니다. 이 메시지는 특별히 명령 메시지를 처리 하며 다른 명령 처럼 라우팅됩니다.

1. 명령 메시지

   여기에 사용자 인터페이스 개체에서 알림 메시지 WM_COMMAND: 메뉴, 도구 모음 단추 및 바로 가기 키입니다. 프레임 워크 명령을 다르게 다른 메시지를 처리 하 고에 설명 된 대로 많은 종류의 개체를 처리할 수 있습니다 [명령 대상](../mfc/command-targets.md)합니다.

##  <a name="_core_windows_messages_and_control.2d.notification_messages"></a> Windows 메시지 및 컨트롤 알림 메시지

범주 1 및 2의에서 메시지-Windows 메시지 및 컨트롤 알림에-windows에 의해 처리 됩니다: 클래스에서 파생 된 클래스의 개체 `CWnd`합니다. 여기에 `CFrameWnd`, `CMDIFrameWnd`를 `CMDIChildWnd`를 `CView`, `CDialog`, 이러한 기본 클래스에서 파생 된 고유한 클래스입니다. 이러한 개체를 캡슐화는 `HWND`, Windows 창에 대 한 핸들입니다.

##  <a name="_core_command_messages"></a> 명령 메시지

범주 3 메시지-명령-다양 한 개체에서 처리할 수 있습니다: 문서, 문서 템플릿 및 창 및 뷰 외에도 응용 프로그램 개체 자체입니다. 명령에서 직접 몇 가지 특정 개체에 영향을 하면 개체가 명령을 처리 하는 것이 좋습니다. 파일 메뉴에서 열기 명령을 응용 프로그램과 함께 논리적으로 연결 되는 예를 들어: 응용 프로그램 명령의 받을 때 지정된 된 문서를 엽니다. 따라서 열려 있는 명령에 대 한 처리기는 응용 프로그램 클래스의 멤버 함수입니다. 명령 및 개체에 라우팅되는 방식을 대 한 자세한 내용은 참조 하세요 [프레임 워크가 처리기를 호출 하는 방법을](../mfc/how-the-framework-calls-a-handler.md)합니다.

## <a name="see-also"></a>참고자료

[프레임워크의 메시지 및 명령](../mfc/messages-and-commands-in-the-framework.md)
