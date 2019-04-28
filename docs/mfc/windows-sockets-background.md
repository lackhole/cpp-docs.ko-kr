---
title: 'Windows 소켓: 배경'
ms.date: 11/04/2016
helpviewer_keywords:
- record-oriented data [MFC]
- e-mail [MFC]
- Internet Protocol Suite
- mail [MFC]
- communications [MFC], domain
- Windows Sockets [MFC], stream sockets
- mail [MFC], programming for
- sockets [MFC], stream sockets
- datagram sockets [MFC]
- SOCKET handle
- data types [MFC], socket
- e-mail [MFC], programming for
- X Window servers
- sequenced data flow
- stream sockets [MFC]
ms.assetid: f60d4ed2-bf23-4a0e-98d2-fee77e8473dd
ms.openlocfilehash: 6ab866609d0b75aaf9d06a01c204433d80e7e3d8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62217880"
---
# <a name="windows-sockets-background"></a>Windows 소켓: 배경

이 문서에는 특성과 Windows 소켓의 용도 설명합니다. 문서도:

- ["소켓" 라는 용어를 정의](#_core_definition_of_a_socket)합니다.

- [소켓 핸들 데이터 유형을 설명](#_core_the_socket_data_type)합니다.

- [소켓에 대 한 용도 설명](#_core_uses_for_sockets)합니다.

Windows 소켓 사양 Microsoft Windows에 대 한 이진 호환 네트워크 프로그래밍 인터페이스를 정의합니다. Windows 소켓 Berkeley Software Distribution UNIX 소켓 구현에 기반한 (BSD에서 4.3 릴리스) 버클리 캘리포니아 대학에서에서. 사양은 스타일 BSD 소켓 루틴 및 Windows에 특정 확장에 포함 되어 있습니다. Windows 소켓을 사용 하 여 응용 프로그램 Windows Sockets API에 따르는 모든 네트워크를 통해 통신을 허용 합니다. Win32, Windows 소켓 스레드로부터의 안전성을 제공합니다.

여러 네트워크에 대 한 소프트웨어 공급 업체는 Windows 소켓 Protocol/Internet Protocol TCP/IP (Transmission Control), Xerox 네트워크 시스템 (XNS) Digital Equipment Corporation DECNet 프로토콜, Novell 회사의 인터넷을 포함 하 여 네트워크 프로토콜에서 지원 Packet Exchange/Sequenced 압축 Exchange (IPX/SPX) 및 기타. TCP/IP에 대 한 소켓 추상화를 정의 하는 현재 Windows 소켓 사양, 하지만 모든 네트워크 프로토콜 자체 버전의 Windows 소켓을 구현 하는 동적 연결 라이브러리 (DLL)를 제공 하 여 Windows 소켓 따를 수 있습니다. Windows 소켓을 사용 하 여 작성 하는 상업용 응용 프로그램의 예로 X Windows 서버, 터미널 에뮬레이터 및 전자 메일 시스템을 들 수 있습니다.

> [!NOTE]
>  Windows 소켓의 목적은 응용 프로그램이 소켓을 지 원하는 모든 네트워크에서 실행할 수 있도록 및 해당 네트워크에 대 한 지식이 필요가 없도록 기본 네트워크 추상화입니다. 따라서이 문서는 네트워크 프로토콜의 세부 정보를 설명 하지 않습니다.

Microsoft Foundation 클래스 라이브러리 (MFC)는 두 개의 클래스를 제공 하 여 Windows Sockets API를 사용한 프로그래밍을 지원 합니다. 이러한 클래스 중 하나 `CSocket`, 높은 수준의 네트워크 통신 프로그래밍을 간소화 하는 추상화를 제공 합니다.

Windows 소켓 사양에 Windows 소켓: 네트워크 컴퓨팅에서 Microsoft Windows를 버전 1.1에서 지금 엽니다 인터페이스 큰 그룹의 개인, 회사 TCP/IP 커뮤니티에서 개발한 개방형 네트워킹 표준 및 자유롭게 사용할 수 있습니다. 현재 모델에서는 하나의 "통신 도메인" 프로그래밍, 인터넷 프로토콜 모음의 사용 하 여 소켓입니다. Windows SDK에서 사용할 수 있습니다.

> [!TIP]
>  "Information highway."에 인터넷 통신을 지 원하는 응용 프로그램에 대 한 기본 경로 소켓 인터넷 프로토콜 도구 모음을 사용 하므로

##  <a name="_core_definition_of_a_socket"></a> 소켓 정의

소켓은 통신 끝점-는 Windows 소켓 응용 프로그램을 보내거나 받는 데이터의 패킷이 네트워크를 통해 개체입니다. 소켓 형식이 되며 실행 중인 프로세스를 사용 하 여 연결 및 이라는 것 같습니다. 현재 소켓은 일반적으로 동일한 "통신 도메인에서" 인터넷 프로토콜 모음의 사용 하는 다른 소켓에만 데이터를 교환 합니다.

두 가지 소켓은 양방향입니다. 두 방향 모두에서 동시에 전달 될 수 있는 데이터 흐름 (양방향).

두 개의 소켓 유형은 사용할 수 있습니다.

- Stream 소켓

   레코드 허물기 데이터 흐름에 대 한 제공 Stream 소켓: 바이트 스트림 합니다. 스트림은 배달할 올바르게 시퀀싱 하 고 중복을 보장 됩니다.

- 데이터 그램 소켓

   배달 보장 되지 않으며으로 시퀀싱 할 수 있습니다 하는 데이터 그램 소켓 지원 레코드 지향 데이터 흐름 순차적이 지 않거나 합니다.

"시퀀스"는 패킷이 보낸 순서 대로 배달 하는 것을 의미 합니다. "중복 되지 않은" 특정 패킷을 한 번만 가져올 있습니다 의미 합니다.

> [!NOTE]
>  XNS와 같은 몇 가지 네트워크 프로토콜에서 스트림을 지향적 이며, 바이트 스트림을 아닌 개의 레코드 스트림을 레코드를 수 있습니다. 그러나 보다 일반적인 TCP/IP 프로토콜을 아래 스트림을 바이트 스트림입니다. Windows 소켓 기반 프로토콜 독립적 추상화 수준을 제공합니다.

이러한 형식에 대 한 자세한 내용은 어떤 상황에서 사용 하는 소켓의 종류 및 [Windows 소켓: 소켓 Stream](../mfc/windows-sockets-stream-sockets.md) 고 [Windows 소켓: 데이터 그램 소켓](../mfc/windows-sockets-datagram-sockets.md)합니다.

##  <a name="_core_the_socket_data_type"></a> 소켓 데이터 형식

각 MFC 소켓 개체는 Windows 소켓 개체에 대 한 핸들을 캡슐화합니다. 이 핸들 변수의 데이터 형식이 **소켓**합니다. A **소켓** 핸들이 비슷합니다는 `HWND` 창에 대 한 합니다. MFC 소켓 클래스는 캡슐화 된 핸들에 대 한 작업을 제공합니다.

합니다 **소켓** 데이터 형식을 Windows SDK에 자세히 설명 되어 있습니다. Windows 소켓에서 "소켓 데이터 형식과 오류 값"을 참조 하세요.

##  <a name="_core_uses_for_sockets"></a> 소켓에 대 한 사용

소켓은 세 가지 통신 상황에서 매우 유용 합니다.

- 클라이언트/서버 모델입니다.

- 피어 투 피어 시나리오 메시징 응용 프로그램 등입니다.

- 수신 응용 프로그램 함수 호출으로 메시지를 해석 하 여 원격 프로시저 호출 (RPC)을 수행 합니다.

> [!TIP]
>  통신의 양쪽을 작성 하는 경우 MFC 소켓을 사용 하기 위한 이상적인 사례: 양쪽 끝에서 MFC를 사용 합니다. 비 MFC 응용 프로그램과 통신 하는 경우 대/소문자를 관리 하는 방법을 비롯 하 여이 주제에 대 한 자세한 내용은 참조 하세요. [Windows 소켓: 바이트 순서](../mfc/windows-sockets-byte-ordering.md)합니다.

자세한 내용은 Windows Sockets 사양을 참조: **ntohs**를 **ntohl**를 **htons**를 **htonl**합니다. 또한 다음 항목을 참조 합니다.

- [Windows 소켓: 소켓과 아카이브 함께 사용](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows 소켓: 아카이브를 사용하는 소켓의 예](../mfc/windows-sockets-example-of-sockets-using-archives.md)

- [Windows 소켓: CAsyncSocket 클래스 사용](../mfc/windows-sockets-using-class-casyncsocket.md)

## <a name="see-also"></a>참고자료

[MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)
