---
title: 메시지 보내기 및 받기
ms.date: 11/04/2016
helpviewer_keywords:
- Windows messages [MFC], handling in MFC
- control-notification messages [MFC]
- messages [MFC], receiving
- messages [MFC], MFC
- MFC, messages
- messages [MFC], sending
ms.assetid: 9ce189cb-b259-4c3b-b6f2-9cfbed18b98b
ms.openlocfilehash: bda261f4141a7ceb4e678535d9012650818fabce
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384051"
---
# <a name="message-sending-and-receiving"></a>메시지 보내기 및 받기

프로세스 및 프레임 워크의 응답 부분을 보내는 것이 좋습니다.

대부분의 메시지는 프로그램을 사용 하 여 사용자 상호 작용에서 발생합니다. 메뉴 항목 또는 도구 모음 단추에서 마우스 클릭 하거나 액셀러레이터 키 명령은 생성 됩니다. 사용자 생성에서 Windows 메시지 예를 들어, 이동 또는 창 크기를 조정 합니다. 다른 Windows 메시지는 windows와 가져오기 또는 포커스를 손실 등 프로그램 시작 또는 종료와 같은 이벤트가 발생할 때 전송 됩니다. 컨트롤 알림 메시지는 마우스 클릭 또는 대화 상자에서 단추 또는 목록 상자 컨트롤 같은 컨트롤을 사용 하 여 다른 사용자 상호 작용 하 여 생성 됩니다.

합니다 `Run` 클래스의 멤버 함수 `CWinApp` 메시지를 검색 하 고 해당 하는 창에 디스패치합니다. 대부분의 명령 메시지는 응용 프로그램의 주 프레임 창으로 전송 됩니다. `WindowProc` 미리 정의 된 클래스 라이브러리 가져옵니다 메시지 및 범주 받은 메시지에 따라 서로 다르게 라우팅합니다.

프로세스의 수신 부분을 살펴보겠습니다.

초기 메시지를 받는 사람 창 개체 여야 합니다. Windows 메시지는 일반적으로 해당 창의 개체에서 직접 처리 됩니다. 일반적으로 응용 프로그램의 주 프레임 창에서 시작 된 명령 메시지에 설명 된 명령 대상 체인으로 라우팅됩니다 [명령 라우팅](../mfc/command-routing.md)합니다.

메시지 또는 명령을 받을 수 있는 각 개체에는 메시지 또는 해당 처리기의 이름 사용 하 여 명령을 해당 쌍을 매핑하는 자체 메시지입니다.

명령 대상 개체를 메시지 또는 명령을 받으면 일치 하는 자신의 메시지 맵을 검색 합니다. 메시지에 대 한 처리기를 찾으면 해당 처리기를 호출 합니다. 메시지 맵을 검색 하는 방법에 대 한 자세한 내용은 참조 하십시오 [매핑하는 방법의 프레임 워크 검색 메시지](../mfc/how-the-framework-searches-message-maps.md)합니다. 그림을 다시 참조 [프레임 워크에서 명령을](../mfc/user-interface-objects-and-command-ids.md)합니다.

## <a name="see-also"></a>참고자료

[프레임워크가 처리기를 호출하는 방법](../mfc/how-the-framework-calls-a-handler.md)
