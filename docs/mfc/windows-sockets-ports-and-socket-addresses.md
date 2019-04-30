---
title: 'Windows 소켓: 포트 및 소켓 주소'
ms.date: 11/04/2016
helpviewer_keywords:
- ports [MFC], definition
- Windows Sockets [MFC], ports
- Windows Sockets [MFC], addresses
- ports [MFC]
- addresses [MFC], socket
- sockets [MFC], addresses
- sockets [MFC], ports
ms.assetid: e050261a-9285-4f31-a1c5-6c8033af5b4a
ms.openlocfilehash: c33ec1376c1898272cf80e8d77c5cc273e16f9de
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389374"
---
# <a name="windows-sockets-ports-and-socket-addresses"></a>Windows 소켓: 포트 및 소켓 주소

이 문서는 용어 "port" 및 "address"로 Windows 소켓을 사용 하 여 사용을 설명 합니다.

##  <a name="_core_port"></a> 포트

포트는 서비스가 제공 될 수 있는 고유한 프로세스를 식별 합니다. 현재 컨텍스트에서 포트는 Windows 소켓을 지 원하는 응용 프로그램과 연결 합니다. 컴퓨터에서 동시에 실행 하는 하나 이상의 Windows 소켓 응용 프로그램을 갖도록 각 Windows Sockets 응용 프로그램을 고유 하 게 식별 하는 개념이입니다.

FTP와 같은 공통 서비스의 특정 포트 예약 되어 있습니다. 해당 종류의 서비스를 제공 하는 경우가 아니면 해당 포트를 사용 하지 않아야 합니다. Windows 소켓 사양 이러한 예약 된 포트를 자세히 설명합니다. WINSOCK 파일입니다. H도 나열 됩니다.

사용 가능한 포트를 선택 하는 Windows 소켓 DLL을 수 있도록 하려면 포트 값으로 0을 전달 합니다. MFC는 1,024 10 진수 보다 큰 포트 값을 선택합니다. MFC를 호출 하 여 선택 된 포트 값을 검색할 수는 [CAsyncSocket::GetSockName](../mfc/reference/casyncsocket-class.md#getsockname) 멤버 함수입니다.

##  <a name="_core_socket_address"></a> 소켓 주소

각 소켓 개체는 네트워크에서 IP (인터넷 프로토콜) 주소와 연결 합니다. 일반적으로 주소는 점으로 구분 된 숫자를 "128.56.22.8" 또는 "형식인" 등의 컴퓨터 이름을 합니다.

소켓을 만들려고 하는 경우에 일반적으로 자신의 주소를 지정 하지 필요가.

> [!NOTE]
>  수는 컴퓨터에 네트워크 카드가 여러 개 (또는 이러한 컴퓨터에서 응용 프로그램 실행 될 수도 있습니다) 다른 네트워크를 나타내는입니다. 그렇다면 소켓 사용할지는 네트워크 카드를 지정 하는 주소를 지정 해야 합니다. 이 고급 사용 방법 및 이식성 문제가 발생할 수 있습니다.

자세한 내용은 다음을 참조하세요.

- [Windows 소켓: CAsyncSocket 클래스 사용](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows 소켓: 소켓과 아카이브 함께 사용](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows 소켓: 소켓과 아카이브를 함께 사용하는 방법](../mfc/windows-sockets-how-sockets-with-archives-work.md)

- [Windows 소켓: 스트림 소켓](../mfc/windows-sockets-stream-sockets.md)

- [Windows 소켓: 데이터그램 소켓](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>참고자료

[MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)
