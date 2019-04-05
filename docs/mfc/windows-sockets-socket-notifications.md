---
title: 'Windows 소켓: 소켓 알림'
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Sockets [MFC], notifications
- notifications [MFC], socket
- sockets [MFC], notifications
ms.assetid: 87d5bf70-6e77-49a9-9a64-aaadee2ad018
ms.openlocfilehash: df7bfe8a95221682d0f7f4ebb123bd15b79144d5
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58774336"
---
# <a name="windows-sockets-socket-notifications"></a>Windows 소켓: 소켓 알림

이 문서에서는 소켓 클래스에서 알림 함수를 설명 합니다. 이러한 멤버 함수는 중요 한 이벤트의 소켓 개체에 알리기 위해 프레임 워크를 호출 하는 콜백 함수입니다. 알림 기능은 다음과 같습니다.

- [OnReceive](../mfc/reference/casyncsocket-class.md#onreceive): 호출 하 여 검색 하려면이 버퍼의 데이터는이 소켓에 게 알립니다 [수신](../mfc/reference/casyncsocket-class.md#receive)합니다.

- [OnSend](../mfc/reference/casyncsocket-class.md#onsend): 호출 하 여 데이터 보내기 이제 수 있습니다이 소켓에 게 알립니다 [보낼](../mfc/reference/casyncsocket-class.md#send)합니다.

- [OnAccept](../mfc/reference/casyncsocket-class.md#onaccept): 호출 하 여 보류 중인 연결 요청 받을 수 있는이 수신 대기 소켓 알립니다 [Accept](../mfc/reference/casyncsocket-class.md#accept)합니다.

- [OnConnect](../mfc/reference/casyncsocket-class.md#onconnect): 이 소켓에 연결 하는 연결 시도가 완료를 알립니다: 또는 아마도 성공적으로 오류가 발생 합니다.

- [OnClose](../mfc/reference/casyncsocket-class.md#onclose): 이 소켓을에 연결 된 소켓 닫을 알립니다.

    > [!NOTE]
    >  추가 알림 기능은 [OnOutOfBandData](../mfc/reference/casyncsocket-class.md#onoutofbanddata)합니다. 이 알림을 보내는 소켓에 보낼 "대역" 데이터가 수신 소켓을 알려 줍니다. 대역의 데이터에 연결 된 스트림 소켓의 각 쌍과 연결 된 논리적으로 독립 채널이 있습니다. 대역의 채널은 "긴급" 데이터를 보내는 데 일반적으로 합니다. MFC 대역의 데이터를 지원합니다. 고급 사용자 클래스를 사용 하 여 작업 [CAsyncSocket](../mfc/reference/casyncsocket-class.md) 대역의 채널 하지만 클래스의 사용자를 사용 해야 [CSocket](../mfc/reference/csocket-class.md) 않는 정보를 사용할 것이 좋습니다. 더 쉬운 방법은 해당 데이터를 전달 하는 데는 두 번째 소켓을 만드는 것입니다. 대역의 데이터에 대 한 자세한 내용은 Windows SDK에서 사용할 수 있는 Windows Sockets 사양을 참조 하세요.

클래스에서 파생할 경우 `CAsyncSocket`, 해당 네트워크 응용 프로그램에 관심 있는 이벤트에 대 한 알림 함수를 재정의 해야 합니다. 클래스에서 클래스를 파생 하는 경우 `CSocket`, 것이 여러분이 관심 알림 함수를 재정의할지 여부를 합니다. 사용할 수도 있습니다 `CSocket` 자체는 경우 알림을 함수 기본적으로 아무런 작업도 수행 합니다.

이러한 함수는 재정의할 수 있는 콜백 함수입니다. `CAsyncSocket` 및 `CSocket` 알림을 메시지 변환 하지만 사용 하려는 경우 알림 응답을 작동 하는 방법을 구현 해야 합니다. 알림 함수는 데이터를 읽을 수 있는지와 같이 관심 이벤트의 소켓 알려집니다 시 호출 됩니다.

MFC는 알림을 받을 때 소켓의 동작을 사용자 지정할 수 있도록 알림 함수를 호출 합니다. 예를 들어, 호출할 수 있습니다 `Receive` 에서 프로그램 `OnReceive` 알림 함수를, 않게 알림을 데이터가 읽기를 호출 합니다 `Receive` 를 읽어야 합니다. 이 방법은 필요 하지 않습니다. 이지만 유용한 시나리오입니다. 진행률을 추적 하려면 알림 함수를 사용할 수 있습니다 인쇄 **추적** 메시지 및 등입니다.

파생 된 소켓 클래스에서 알림 함수를 재정의 하 고 구현을 제공 하 여 이러한 알림 활용을 걸릴 수 있습니다.

데이터를 보내거나 등의 작업 중 한 `CSocket` 개체 동기 상태가 됩니다. 동기 상태에 있는 동안 다른 소켓을 위한 알림은 현재 소켓 좋 알림에 대 한 대기 하는 동안 대기 됩니다. (예를 들어 중를 `Receive` 호출 소켓이 읽기 알림을.) 소켓 해당 동기 작업을 완료 하 고 다시 비동기 상태가 다른 소켓 지연된 알림 수신을 시작할 수 있습니다.

> [!NOTE]
>  `CSocket`, `OnConnect` 알림 함수가 호출 되지 않습니다. 호출 연결에 대 한 `Connect`, (성공적으로 또는 오류에서) 연결이 완료 되 면 반환 합니다. MFC 구현 세부 정보는 연결 알림을 처리 하는 방법입니다.

각 알림 함수에 대 한 자세한 내용은 클래스에서 함수를 참조 하세요 `CAsyncSocket` 에 *MFC 참조*합니다. 소스 코드와 MFC 샘플에 대 한 정보에 대 한 참조 [MFC 샘플](../overview/visual-cpp-samples.md)합니다.

자세한 내용은 다음을 참조하세요.

- [Windows 소켓: Casyncsocket 클래스 사용](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows 소켓: 소켓 클래스에서 파생](../mfc/windows-sockets-deriving-from-socket-classes.md)

- [Windows 소켓: 보관이 포함 된 소켓의 작동 방법](../mfc/windows-sockets-how-sockets-with-archives-work.md)

- [Windows 소켓: 차단](../mfc/windows-sockets-blocking.md)

- [Windows 소켓: 바이트 순서 지정](../mfc/windows-sockets-byte-ordering.md)

- [Windows 소켓: 문자열 변환](../mfc/windows-sockets-converting-strings.md)

## <a name="see-also"></a>참고자료

[MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)
