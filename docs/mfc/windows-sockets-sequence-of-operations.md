---
title: 'Windows 소켓: 작업 순서'
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Sockets [MFC], operations
- Windows Sockets [MFC], stream sockets
- sockets [MFC], stream sockets
- sockets [MFC], operations
- stream sockets [MFC]
ms.assetid: 43ce76f5-aad3-4247-b8a6-16cc7d012796
ms.openlocfilehash: 0f9fd339fdbdfee9381ea693568f40473c2397e9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62296516"
---
# <a name="windows-sockets-sequence-of-operations"></a>Windows 소켓: 작업 순서

이 문서에서는 설명, 나란히 서버 소켓과 클라이언트 소켓에 대 한 작업의 시퀀스입니다. 소켓을 사용 하므로 `CArchive` 개체는 반드시 [스트림 소켓](../mfc/windows-sockets-stream-sockets.md)합니다.

## <a name="sequence-of-operations-for-a-stream-socket-communication"></a>Stream 소켓 통신에 대 한 작업 시퀀스

생성 시점을 `CSocketFile` 개체를 다음 순서를 정확 하 게 (몇 가지 매개 변수 차이점이)와 둘 다에 대해 `CAsyncSocket` 및 `CSocket`합니다. 해당 지점에서 순서가 엄격 하 게 한 `CSocket`합니다. 다음 표에서 클라이언트와 서버 간의 통신을 설정 하기 위한 작업 시퀀스를 보여 줍니다.

### <a name="setting-up-communication-between-a-server-and-a-client"></a>서버와 클라이언트 간의 통신 설정

|서버|클라이언트|
|------------|------------|
|`// construct a socket`<br /><br /> `CSocket sockSrvr;`|`// construct a socket`<br /><br /> `CSocket sockClient;`|
|`// create the SOCKET`<br /><br /> `sockSrvr.Create(nPort);`1,2|`// create the SOCKET`<br /><br /> `sockClient.Create( );`2|
|`// start listening`<br /><br /> `sockSrvr.Listen( );`||
||`// seek a connection`<br /><br /> `sockClient.Connect(strAddr, nPort);`3,4|
|`// construct a new, empty socket`<br /><br /> `CSocket sockRecv;`<br /><br /> `// accept connection`<br /><br /> `sockSrvr.Accept( sockRecv );` 5||
|`// construct file object`<br /><br /> `CSocketFile file(&sockRecv);`|`// construct file object`<br /><br /> `CSocketFile file(&sockClient);`|
|`// construct an archive`<br /><br /> `CArchive arIn(&file, CArchive::load);`<br /><br /> 또는<br /><br /> `CArchive arOut(&file, CArchive::store);`<br /><br /> 또는 둘 다|`// construct an archive`<br /><br /> `CArchive arIn(&file, CArchive::load);`<br /><br /> 또는<br /><br /> `CArchive arOut(&file, CArchive::store);`<br /><br /> 또는 둘 다|
|`// use the archive to pass data:`<br /><br /> `arIn >> dwValue;`<br /><br /> 또는<br /><br /> `arOut << dwValue;`6|`// use the archive to pass data:`<br /><br /> `arIn >> dwValue;`<br /><br /> 또는<br /><br /> `arOut << dwValue;`6|

1. 여기서 *nPort* 는 포트 번호입니다. 참조 [Windows 소켓: 포트 및 소켓 주소](../mfc/windows-sockets-ports-and-socket-addresses.md) 포트에 대 한 세부 정보에 대 한 합니다.

2. 항상 서버는 클라이언트가 연결할 수 있도록 포트를 지정 해야 합니다. `Create` 호출 수도 주소를 지정 합니다. 클라이언트 쪽에서 사용 가능한 모든 포트를 사용 하도록 MFC를 요청 하는 기본 매개 변수를 사용 합니다.

3. 여기서 *nPort* 포트 번호 및 *strAddr* 컴퓨터 주소 또는 IP (인터넷 프로토콜) 주소입니다.

4. 컴퓨터 주소에는 여러 가지 형식을 취할 수 있습니다. "형식인", "microsoft.com"입니다. IP 주소는 "점 있는 번호" 형식 "127.54.67.32"를 사용합니다. `Connect` 함수 인지 여부를 확인 하는 경우 주소는 점으로 구분 된 번호 (하지만 확인 네트워크에 있는 유효한 컴퓨터 수를 확인 하지 않습니다). 그러지 않으면 `Connect` 다른 형식 중 하나는 컴퓨터 이름을 가정 합니다.

5. 호출 하는 경우 `Accept` 서버 쪽에서 새 소켓 개체에 대 한 참조를 전달 합니다. 이 개체를 먼저 구성 해야 하지만 호출 하지 마십시오 `Create` 에 대 한 합니다. 염두에이 소켓 개체가 범위를 연결 닫기 이동 하는 경우. 새 개체를 연결 하는 MFC를 **소켓** 처리 합니다. 표시 된 대로 스택에 또는 힙의 소켓을 생성할 수 있습니다.

6. 보관 및 소켓 파일에는 범위를 벗어날 때 닫힙니다. 소켓 개체의 소멸자가 호출 된 [닫기](../mfc/reference/casyncsocket-class.md#close) 개체가 범위를 벗어날 되거나 삭제 되 면 소켓 개체에 대 한 멤버 함수입니다.

## <a name="additional-notes-about-the-sequence"></a>시퀀스에 대 한 추가 정보

앞의 표에 표시 된 호출 시퀀스로 스트림 소켓입니다. 연결 된 데이터 그램 소켓 필요 하지 않습니다 합니다 [CAsyncSocket::Connect](../mfc/reference/casyncsocket-class.md#connect)를 [수신](../mfc/reference/casyncsocket-class.md#listen), 및 [Accept](../mfc/reference/casyncsocket-class.md#accept) 호출 ( 사용할수도있지만`Connect`). 대신, 클래스를 사용 하는 경우 `CAsyncSocket`, 데이터 그램 소켓 사용 합니다 `CAsyncSocket::SendTo` 및 `ReceiveFrom` 멤버 함수입니다. (사용 하는 경우 `Connect` 사용 하면 데이터 그램 소켓 `Send` 고 `Receive`.) 때문에 `CArchive` 작동 하지 않는 데이터 그램을 사용 하 여 사용 하지 않는 `CSocket` 데이터 그램 소켓 경우 보관을 사용 하 여 합니다.

[CSocketFile](../mfc/reference/csocketfile-class.md) 의 일부를 지원 하지 `CFile`의 기능 `CFile` 와 같은 멤버 `Seek`, 소켓 통신에 대 한 의미가 있는 사용할 수 없습니다. 이 때문에 일부 기본 MFC `Serialize` 함수를 사용 하 여 호환 되지 `CSocketFile`합니다. 이 특히의 `CEditView` 클래스입니다. Serialize 하지 않아야 `CEditView` 를 통해 데이터를 `CArchive` 개체에 연결을 `CSocketFile` 사용 하 여 개체 `CEditView::SerializeRaw`; 사용 `CEditView::Serialize` 대신 (문서화 되지). 합니다 [SerializeRaw](../mfc/reference/ceditview-class.md#serializeraw) 함수는 파일 개체와 같은 함수를 `Seek`는 `CSocketFile` 지원 하지 않습니다.

자세한 내용은 다음을 참조하세요.

- [Windows 소켓: 소켓과 아카이브 함께 사용](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows 소켓: CAsyncSocket 클래스 사용](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows 소켓: 포트 및 소켓 주소](../mfc/windows-sockets-ports-and-socket-addresses.md)

- [Windows 소켓: 스트림 소켓](../mfc/windows-sockets-stream-sockets.md)

- [Windows 소켓: 데이터그램 소켓](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>참고자료

[MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)<br/>
[CSocket 클래스](../mfc/reference/csocket-class.md)<br/>
[CAsyncSocket::Create](../mfc/reference/casyncsocket-class.md#create)<br/>
[CAsyncSocket::Close](../mfc/reference/casyncsocket-class.md#close)
