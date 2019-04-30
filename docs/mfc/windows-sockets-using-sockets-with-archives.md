---
title: 'Windows 소켓: 소켓을 사용 하 여 아카이브를 함께 사용'
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Sockets [MFC], archives
- sockets [MFC], with archives
- archives [MFC], and Windows Sockets
- CSocket class [MFC], programming model
ms.assetid: 17e71a99-a09e-4e1a-9fda-13d62805c824
ms.openlocfilehash: 71a7ed1f1b67bed157805328679a18ceabf201d3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62358289"
---
# <a name="windows-sockets-using-sockets-with-archives"></a>Windows 소켓: 소켓을 사용 하 여 아카이브를 함께 사용

이 문서에 설명 합니다 [CSocket 프로그래밍 모델](#_core_the_csocket_programming_model)합니다. 클래스 [CSocket](../mfc/reference/csocket-class.md) 클래스 보다 더 높은 수준의 추상화에서 소켓 지원을 제공 [CAsyncSocket](../mfc/reference/casyncsocket-class.md)합니다. `CSocket` MFC serialization 프로토콜의 버전을 사용 하 여 MFC 통해 소켓 개체에서 데이터를 전달 [CArchive](../mfc/reference/carchive-class.md) 개체입니다. `CSocket`은 차단을 제공하며(Windows 메시지의 백그라운드 처리 관리), 원시 API 또는 `CArchive`클래스를 사용할 경우 직접 수행해야 하는 문서의 여러 측면에 대한 관리 작업을 수행하는 `CAsyncSocket`에 액세스할 수 있게 해줍니다.

> [!TIP]
>  `CSocket`의 편리한 버전으로 `CAsyncSocket` 클래스를 직접 사용할 수 있지만 가장 간단한 프로그래밍 모델은 `CSocket` 개체에 `CArchive`을 사용하는 것입니다.

아카이브가 포함 된 소켓 구현의 작동 하는 방법에 대 한 자세한 내용은 참조 하세요. [Windows 소켓: 아카이브가 포함 된 소켓 방식](../mfc/windows-sockets-how-sockets-with-archives-work.md)합니다. 예를 들어 코드를 참조 하십시오 [Windows 소켓: 작업 시퀀스](../mfc/windows-sockets-sequence-of-operations.md) 고 [Windows 소켓: 아카이브를 사용 하는 소켓의 예](../mfc/windows-sockets-example-of-sockets-using-archives.md)합니다. 소켓 클래스에서 고유한 클래스를 파생 하 여 얻을 수 있는 일부의 기능에 대 한 정보를 참조 하세요. [Windows 소켓: 소켓 클래스에서 파생](../mfc/windows-sockets-deriving-from-socket-classes.md)합니다.

> [!NOTE]
>  설정된(MFC 이외) 서버와 통신하도록 MFC 클라이언트 프로그램을 작성하는 경우 아카이브를 통해 C++ 개체를 전송하지 마십시오. 사용자가 전송하려는 개체 종류를 인식하는 MFC 응용 프로그램이 아니면 개체를 수신하고 이를 deserialize할 수 없습니다. 비 MFC 응용 프로그램을 사용 하 여 통신에 관련된 자료에 대 한 문서를 참조도 [Windows 소켓: 바이트 순서](../mfc/windows-sockets-byte-ordering.md)합니다.

##  <a name="_core_the_csocket_programming_model"></a> CSocket 프로그래밍 모델

`CSocket` 개체 사용 시에는 여러 MFC 클래스 개체를 함께 만들고 연결하는 작업이 포함됩니다. 아래의 일반 절차에서 각 단계는 각 소켓 유형에 서로 다른 작업이 필요한 3단계를 제외하고 서버 소켓과 클라이언트 소켓 모두에서 수행됩니다.

> [!TIP]
>  런타임에 서버 응용 프로그램은 일반적으로 먼저 시작되어 준비되며, 클라이언트 응용 프로그램이 연결을 검색할 때 이를 수신 대기합니다. 클라이언트가 연결을 시도할 때 서버가 준비되어 있지 않으면 일반적으로 사용자 응용 프로그램이 나중에 연결을 다시 시도해야 합니다.

#### <a name="to-set-up-communication-between-a-server-socket-and-a-client-socket"></a>서버 소켓과 클라이언트 소켓 사이의 통신을 설정하려면

1. 생성 된 [CSocket](../mfc/reference/csocket-class.md) 개체입니다.

1. 개체를 사용 하 여 기본 만들려는 **소켓** 처리 합니다.

   에 `CSocket` 클라이언트 개체를 일반적으로 기본 매개 변수를 사용 해야 [만들기](../mfc/reference/casyncsocket-class.md#create)데이터 그램 소켓 필요 하지 않은 경우, 합니다. 에 `CSocket` 서버 개체에서 포트를 지정 해야 합니다는 `Create` 호출 합니다.

    > [!NOTE]
    >  `CArchive`는 데이터그램 소켓에서 작동하지 않습니다. 데이터그램 소켓에 대해 `CSocket`을 사용하려는 경우에는 `CAsyncSocket`을 사용할 때와 마찬가지로, 아카이브 없이 클래스를 사용해야 합니다. 데이터그램은 안정적이지 않기 때문에(수신이 보장되지 않고 반복되거나 순서가 바뀔 수 있음), 아카이브를 통한 serialization과 호환되지 않습니다. serialization 작업은 안정적으로 그리고 순차적으로 완료할 것으로 예상됩니다. 데이터그램에 대해 `CSocket` 개체와 함께 `CArchive`을 사용하려고 시도하면 MFC 어설션이 실패합니다.

1. 클라이언트 소켓을 사용 하는 경우 호출 [CAsyncSocket::Connect](../mfc/reference/casyncsocket-class.md#connect) 소켓 개체를 서버 소켓 연결 합니다.

     또는

   소켓이 서버인 경우 호출할 [CAsyncSocket::Listen](../mfc/reference/casyncsocket-class.md#listen) 하려면 클라이언트에서 연결 시도 대 한 수신 대기 합니다. 연결 요청을 받으면 호출 하 여 수락 [CAsyncSocket::Accept](../mfc/reference/casyncsocket-class.md#accept)합니다.

    > [!NOTE]
    >  합니다 `Accept` 멤버 함수는 비어 있는 새에 대 한 참조 `CSocket` 매개 변수로 개체입니다. 호출 하기 전에이 개체를 생성 해야 `Accept`합니다. 이 소켓 개체가 범위를 벗어나면 연결이 닫힙니다. 호출 하지 마십시오 `Create` 이 새 소켓 개체에 대 한 합니다.

1. 만들기는 [CSocketFile](../mfc/reference/csocketfile-class.md) 개체를 연결 합니다 `CSocket` 개체를 합니다.

1. 만들기는 [CArchive](../mfc/reference/carchive-class.md) 개체 로드 (수신) 또는 (송신) 데이터를 저장 합니다. 아카이브는 `CSocketFile` 개체와 연결됩니다.

   `CArchive`는 데이터그램 소켓에서 작동하지 않습니다.

1. 클라이언트 및 서버 소켓 사이에 데이터를 전달하려면 `CArchive` 개체를 사용합니다.

   특정 `CArchive` 개체는 데이터를 한 방향으로만 이동합니다. 즉, 로드(수신) 또는 저장(송신) 방향으로만 이동합니다. 일부 경우에는 데이터 송신 및 수신 확인을 위해 두 개의 `CArchive` 개체를 사용합니다.

   연결을 수락하고 아카이브를 설정한 후에는 암호 유효성 검사와 같은 작업을 수행할 수 있습니다.

1. 아카이브, 소켓 파일 및 소켓 개체를 삭제합니다.

    > [!NOTE]
    >  `CArchive` 클래스는 `IsBufferEmpty` 클래스에 사용할 수 있도록 `CSocket` 멤버 함수를 제공합니다. 예를 들어 버퍼에 여러 데이터 메시지가 포함된 경우에는 모든 항목이 읽혀지고 버퍼가 비워질 때까지 반복해야 합니다. 그렇지 않으면 수신할 데이터가 있음에 대한 다음 알림이 무기한 지연될 수 있습니다. 모든 데이터를 검색할 수 있도록 `IsBufferEmpty`를 사용합니다.

문서 [Windows 소켓: 작업 시퀀스](../mfc/windows-sockets-sequence-of-operations.md) 예제 코드를 사용 하 여이 프로세스의 양면을 모두 보여줍니다.

자세한 내용은 다음을 참조하세요.

- [Windows 소켓: 스트림 소켓](../mfc/windows-sockets-stream-sockets.md)

- [Windows 소켓: 데이터그램 소켓](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>참고자료

[MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)<br/>
[CSocket::Create](../mfc/reference/csocket-class.md#create)
