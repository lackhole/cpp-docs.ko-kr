---
title: 'Windows 소켓: 소켓 클래스에서 파생'
ms.date: 11/04/2016
helpviewer_keywords:
- derived classes [MFC], from socket classes
- Windows Sockets [MFC], deriving from socket classes
- sockets [MFC], deriving from socket classes
ms.assetid: 3a26e67a-e323-433b-9b05-eca018799801
ms.openlocfilehash: 12ab66cfd9212cd79752e2f6359b857194c6428c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385260"
---
# <a name="windows-sockets-deriving-from-socket-classes"></a>Windows 소켓: 소켓 클래스에서 파생

이 문서에서는 소켓 클래스 중 하나에서 고유한 클래스를 파생 하 여 얻을 수 있는 기능 중 일부를 설명 합니다.

고유한 소켓 클래스를 파생 시킬 수 있습니다 [CAsyncSocket](../mfc/reference/casyncsocket-class.md) 또는 [CSocket](../mfc/reference/csocket-class.md) 고유한 기능을 추가 합니다. 특히, 이러한 클래스는 다양 한 재정의할 수 있는 가상 멤버 함수를 제공 합니다. 이러한 함수를 포함 [OnReceive](../mfc/reference/casyncsocket-class.md#onreceive)를 [OnSend](../mfc/reference/casyncsocket-class.md#onsend)를 [OnAccept](../mfc/reference/casyncsocket-class.md#onaccept)를 [OnConnect](../mfc/reference/casyncsocket-class.md#onconnect), 및 [OnClose](../mfc/reference/casyncsocket-class.md#onclose)합니다. 네트워크 이벤트가 발생할 때 제공 되는 알림 활용 하기 위해 파생된 소켓 클래스에서 함수를 재정의할 수 있습니다. 프레임 워크를 알리는 데이터 수신 등의 중요 한 소켓 이벤트 읽기를 시작할 수 있습니다 이러한 알림 콜백 함수를 호출 합니다. 알림 함수에 대 한 자세한 내용은 참조 하세요. [Windows 소켓: 알림 소켓](../mfc/windows-sockets-socket-notifications.md)합니다.

또한 클래스 `CSocket` 제공 합니다 [OnMessagePending](../mfc/reference/csocket-class.md#onmessagepending) 멤버 함수 (고급 재정의 가능). MFC 소켓은 Windows 기반 메시지를 펌프 하는 동안이 함수를 호출 합니다. 재정의할 수 있습니다 `OnMessagePending` Windows에서 특정 메시지를 확인 하 여 응답할 수 있습니다.

기본 버전 `OnMessagePending` 클래스에 제공 된 `CSocket` 차단 호출이 완료 되기를 기다리는 동안 WM_PAINT 메시지에 대 한 메시지 큐를 검사 합니다. 해당 표시 품질을 향상 시키고 그리기 메시지를 디스패치합니다. 유용한 작업을 수행 하는 것 외이 보여 줍니다 함수를 재정의 하는 한 가지 방법은 직접. 또 다른 예로, 사용 하 여 것이 좋습니다. `OnMessagePending` 다음 태스크에 대 한 합니다. 네트워크 트랜잭션이 완료 되기를 기다리는 동안 모덜리스 대화 상자를 표시 한다고 가정 합니다. 대화 상자 사용자 시간이 오래 걸리는 차단 트랜잭션을 취소 하는 데 사용할 수 있는 취소 단추를 포함 합니다. 프로그램 `OnMessagePending` 재정의이 모덜리스 대화 상자와 관련 된 메시지를 펌프 수 있습니다.

사용자 `OnMessagePending` 재정의 반환 **TRUE** 의 기본 클래스 버전에 대 한 호출에서 반환 된 값 또는 `OnMessagePending`합니다. 수행 하려는 작업을 계속 수행 하는 경우 기본 클래스 버전을 호출 합니다.

자세한 내용은 다음을 참조하세요.

- [Windows 소켓: 소켓과 아카이브 함께 사용](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows 소켓: CAsyncSocket 클래스 사용](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows 소켓: 차단](../mfc/windows-sockets-blocking.md)

- [Windows 소켓: 바이트 순서 지정](../mfc/windows-sockets-byte-ordering.md)

- [Windows 소켓: 문자열 변환](../mfc/windows-sockets-converting-strings.md)

## <a name="see-also"></a>참고자료

[MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)
