---
title: 'Windows 소켓: 차단'
ms.date: 11/04/2016
helpviewer_keywords:
- sockets [MFC], blocking mode
- Windows Sockets [MFC], Windows platforms
- Windows Sockets [MFC], blocking mode
- sockets [MFC], behavior on different Windows platforms
- blocking mode sockets
ms.assetid: 10aca9b1-bfba-41a8-9c55-ea8082181e63
ms.openlocfilehash: 26a361bc63da5f6e75144cc91fe837498a7f656b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62371966"
---
# <a name="windows-sockets-blocking"></a>Windows 소켓: 차단

이 문서 및 두 개의 참조 문서에서는 Windows 소켓 프로그래밍의 몇 가지 문제를 설명합니다. 이 문서는 차단에 대해 설명합니다. 다른 문제는 문서에 적용 됩니다. [Windows 소켓: 바이트 순서](../mfc/windows-sockets-byte-ordering.md) 고 [Windows 소켓: 문자열 변환](../mfc/windows-sockets-converting-strings.md)합니다.

사용 하거나 클래스에서 파생 되는 경우 [CAsyncSocket](../mfc/reference/casyncsocket-class.md), 이러한 문제를 직접 관리 해야 합니다. 사용 하거나 클래스에서 파생 되는 경우 [CSocket](../mfc/reference/csocket-class.md), MFC를 관리 합니다.

## <a name="blocking"></a>차단

소켓은 "차단 모드" 또는 "비차단 모드"일 수 있습니다. 차단(또는 동기) 모드에서 소켓의 함수는 작업을 완료할 수 있을 때가지 반환되지 않습니다. 이를 차단이라고 부르는 이유는 함수가 호출되는 소켓이 호출이 반환될 때까지 아무 것도 할 수 없이 차단되기 때문입니다. 에 대 한 호출을 `Receive` 멤버 함수에 예를 들어를 임의로 시간이 오래 걸릴 수 보낼 보내는 응용 프로그램에 대 한 완료를 (사용 하는 경우 이것이 `CSocket`, 또는 사용 하 여 `CAsyncSocket` 차단). 경우는 `CAsyncSocket` 개체가 비차단 모드 (비동기적으로 작동 중), 호출이 즉시 반환 하 고 검색할 수 있는 현재 오류 코드는 [GetLastError](../mfc/reference/casyncsocket-class.md#getlasterror) 멤버 함수는 **WSAEWOULDBLOCK**, 호출 차단 됨을 나타내는 했 모드로 인해 즉시 반환 되지 않습니다. (`CSocket` 반환 하지 않습니다 **WSAEWOULDBLOCK**합니다. 이 클래스는 사용자를 위해 차단을 관리합니다.)

32비트 및 64비트 운영 체제(예: Windows 95 또는 Windows 98)와 16비트 운영 체제(예: Windows 3.1)에서는 소켓의 동작이 달라집니다. 16비트 운영 체제와 달리 32비트 및 64비트 운영 체제는 선점형 멀티태스킹을 사용하며 다중 스레딩을 제공합니다. 32비트 및 64비트 운영 체제에서는 별개의 작업자 스레드에 소켓을 넣을 수 있습니다. 스레드에 있는 소켓은 애플리케이션의 다른 작업을 간섭하지 않고, 차단 시 컴퓨팅 시간을 소비하지 않고 차단할 수 있습니다. 다중 스레드 프로그래밍에 대 한 내용은 문서 참조 [다중 스레딩](../parallel/multithreading-support-for-older-code-visual-cpp.md)합니다.

> [!NOTE]
>  다중 스레드 응용 프로그램에서는 `CSocket`의 차단 특성을 사용해서 사용자 인터페이스의 응답성에 영향을 주지 않고 프로그램의 디자인을 간소화할 수 있습니다. 주 스레드에서 사용자 인터페이스를 처리하고 대체 스레드에서 `CSocket` 프로세싱을 처리함으로써 이러한 논리적 작업을 구분할 수 있습니다. 다중 스레드가 아닌 응용 프로그램에서 이러한 두 작업은 서로 결합되어 단일 스레드로 처리되어야 합니다. 즉, 필요에 따라 통신 요청을 처리할 수 있도록 `CAsyncSocket`을 사용하거나, 오래 걸리는 동기 작업 중에 사용자 작업을 처리할 수 있도록 `CSocket::OnMessagePending`을 재정의합니다.

이 설명의 나머지 부분은 16비트 운영 체제를 대상으로 하는 프로그래머를 위한 것입니다.

일반적으로 `CAsyncSocket`을 사용 중이면 차단 작업 사용을 피하고 대신 비동기적으로 작업을 수행해야 합니다. 수신 하는 지점에서 비동기 작업의 경우에 **WSAEWOULDBLOCK** 호출한 후 오류 코드 `Receive`, 될 때까지 대기 하는 예를 들어, 프로그램 `OnReceive` 를 읽을 수 있는지 여부를 알리는 구성원 함수가 호출 되 다시 실행 합니다. 소켓의 적절 한 콜백 알림 함수를 같은 콜백 하 여 비동기 호출 [OnReceive](../mfc/reference/casyncsocket-class.md#onreceive)합니다.

Windows에서 차단 호출은 좋지 않은 방법으로 고려됩니다. 기본적으로 [CAsyncSocket](../mfc/reference/casyncsocket-class.md) 고 지 원하는 비동기 호출, 콜백 알림을 사용해 직접 차단을 관리 해야 합니다. 클래스 [CSocket](../mfc/reference/csocket-class.md), 다른 한편으로 동기적입니다. 이 클래스는 사용자를 위해 Windows 메시지를 제공하고 차단을 관리합니다.

차단에 대한 자세한 내용은 Windows Sockets 사양을 참조하십시오. "On" 함수에 대 한 자세한 내용은 참조 하세요. [Windows 소켓: 알림 소켓](../mfc/windows-sockets-socket-notifications.md) 고 [Windows 소켓: 소켓 클래스에서 파생](../mfc/windows-sockets-deriving-from-socket-classes.md)합니다.

자세한 내용은 다음을 참조하세요.

- [Windows 소켓: CAsyncSocket 클래스 사용](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows 소켓: 소켓과 아카이브 함께 사용](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows 소켓: 배경](../mfc/windows-sockets-background.md)

- [Windows 소켓: 스트림 소켓](../mfc/windows-sockets-stream-sockets.md)

- [Windows 소켓: 데이터그램 소켓](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>참고자료

[MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)<br/>
[CAsyncSocket::OnSend](../mfc/reference/casyncsocket-class.md#onsend)
