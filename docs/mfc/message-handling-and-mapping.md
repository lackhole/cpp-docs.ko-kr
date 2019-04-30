---
title: 메시지 처리 및 매핑
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, messages
- message handling [MFC]
- message maps [MFC]
ms.assetid: 62fe2a1b-944c-449d-a0f0-63c11ee0a3cb
ms.openlocfilehash: 41f3432b3741019a787ee24b0f508fe8e65e0470
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383973"
---
# <a name="message-handling-and-mapping"></a>메시지 처리 및 매핑

이 문서에서는 MFC 프레임 워크에서 명령과 메시지 처리 방법 및 연결 하는 방법에 해당 처리기 함수에 설명 합니다.

Windows에 대 한 기존 프로그램을 Windows 메시지 창 프로시저에서 큰 switch 문에서 처리 됩니다. MFC 대신 사용 하 여 [메시지 맵이](../mfc/message-categories.md) 고유 클래스 멤버 함수에 직접 메시지를 매핑합니다. 메시지 맵은이 목적을 위해 가상 함수 보다 효율적이 고 메시지를 가장 적합 한 하 여 처리할 수 있도록 C++ 개체, 응용 프로그램, 문서, 뷰 및 등입니다. 단일 메시지 또는 메시지를 명령 Id의 범위를 매핑할 수도 있고 컨트롤 Id 수 있습니다.

WM_COMMAND 메시지-메뉴나 도구 모음 단추 액셀러레이터 키에서 일반적으로 생성 된-메시지 맵 메커니즘을 사용할 수도 있습니다. MFC는 표준 정의 하며 [라우팅](../mfc/command-routing.md) 응용 프로그램 간에 명령 메시지의 프레임 창, 뷰 및 프로그램에서 액티브 문서. 해야 할 경우이 라우팅은 재정의할 수 있습니다.

메시지 맵 (예: 메뉴 및 도구 모음 단추), 사용자 인터페이스 개체를 업데이트 하는 방법을 제공 하거나 현재 컨텍스트에 맞게 해제 합니다.

메시지 및 Windows 메시지 큐에 대 한 일반적인 정보를 참조 하세요 [메시지와 메시지 큐](/windows/desktop/winmsg/messages-and-message-queues) Windows SDK에 있습니다.

## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [프레임워크의 메시지 및 명령](../mfc/messages-and-commands-in-the-framework.md)

- [프레임 워크가 메시지 처리기를 호출 하는 방법](../mfc/how-the-framework-calls-a-handler.md)

- [프레임워크가 메시지 맵을 검색하는 방법](../mfc/how-the-framework-searches-message-maps.md)

- [메시지 처리기 함수 선언](../mfc/declaring-message-handler-functions.md)

- [함수에 메시지 매핑](../mfc/reference/mapping-messages-to-functions.md)

- [상태 표시줄에 명령 정보를 표시 하는 방법](../mfc/how-to-display-command-information-in-the-status-bar.md)

- [사용자 인터페이스 개체의 동적 업데이트](../mfc/how-to-update-user-interface-objects.md)

- [방법: 템플릿 클래스에 대한 메시지 맵 만들기](../mfc/how-to-create-a-message-map-for-a-template-class.md)

## <a name="see-also"></a>참고자료

[개념](../mfc/mfc-concepts.md)<br/>
[일반 MFC 항목](../mfc/general-mfc-topics.md)<br/>
[CWnd 클래스](../mfc/reference/cwnd-class.md)<br/>
[CCmdTarget 클래스](../mfc/reference/ccmdtarget-class.md)
