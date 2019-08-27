---
title: WinInet을 사용하여 인터넷 클라이언트 애플리케이션을 손쉽게 만드는 방법
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Sockets [MFC], vs. WinInet
- WinInet classes [MFC], vs. WinSock
- WinInet classes [MFC], Internet client applications
ms.assetid: dc0f9f47-3184-4e7a-8074-2c63e0359885
ms.openlocfilehash: 6da2ef1595e525bcfd407d67c806aa80cf90f1c3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62262712"
---
# <a name="how-wininet-makes-it-easier-to-create-internet-client-applications"></a>WinInet을 사용하여 인터넷 클라이언트 애플리케이션을 손쉽게 만드는 방법

Win32 인터넷 확장명 또는 WinInet gopher, FTP, HTTP 등 공통 인터넷 프로토콜에 대 한 액세스를 제공 합니다. WinInet을 사용 하 여, WinSock, TCP/IP 또는 특정 인터넷 프로토콜의 세부 정보를 사용 하 여 처리할 필요 없이 더 높은 수준의 프로그래밍 인터넷 클라이언트 응용 프로그램을 작성할 수 있습니다. WinInet 친숙 한 Win32 API 인터페이스를 사용 하 여 세 가지 프로토콜 모두에 대 한 일관 된 함수 집합을 제공합니다. 이 일관성 최소화 코드 변경 내용을 기본 프로토콜 (예를 들어 FTP에서 HTTP로) 변경 하는 경우를 확인 해야 합니다.

Visual C++ WinInet을 사용 하는 두 가지 방법을 제공 합니다. Win32 인터넷 함수를 직접 호출할 수 있습니다 (자세한 내용은 Windows SDK의 OLE 설명서 참조) 또는 WinInet을 통해 사용할 수 있습니다 합니다 [MFC WinInet 클래스](../mfc/mfc-classes-for-creating-internet-client-applications.md)합니다.

**WinInet을 사용할 수 있습니다.**

- HTML 페이지를 다운로드 합니다.

   HTTP는 클라이언트 브라우저에 HTML 페이지는 서버에서 전송 하는 데 사용 되는 프로토콜입니다.

- FTP 업로드 또는 다운로드 파일 또는 디렉터리 목록을 가져오기 요청을 보냅니다.

   일반적인 요청은 파일을 다운로드 하려면 익명으로 로그온 합니다.

- 인터넷 리소스에 액세스 하기 위한 gopher의 메뉴 시스템을 사용 합니다.

   메뉴 항목에는 다른 메뉴, 검색할 수는 인덱싱된 데이터베이스, 뉴스 그룹 또는 파일을 비롯 한 여러 형식이 수 있습니다.

세 가지 프로토콜 모두에 대 한 연결, 서버 요청을 및 연결을 닫습니다.

**MFC WinInet 클래스를 사용 하면 쉽게 하려면:**

- 하드 드라이브에서 파일을 읽는 것 처럼 쉽게 HTTP, FTP 및 gopher 서버에서 정보를 읽습니다.

- WinSock 또는 TCP/IP에 직접 프로그래밍 없이 HTTP, FTP 및 gopher 프로토콜을 사용 합니다.

   Win32 인터넷 기능을 사용 하는 개발자는 TCP/IP 또는 Windows 소켓을 사용 하 여 친숙 한 필요가 없습니다. 여전히 프로그래밍할 수 소켓 수준에서 직접, WinSock 및 TCP/IP 프로토콜을 사용 하 여 이지만 더욱 쉽게 인터넷을 통해 액세스 HTTP, FTP 및 gopher 프로토콜에 MFC WinInet 클래스를 사용할 수 있습니다. 다양 한 일반적인 작업에 대 한 개발자가 사용 하는 특정 프로토콜의 세부 정보를 알 필요가 없습니다.

인터넷 상의 다른 컴퓨터에 클라이언트 컴퓨터에서 수행할 수 있는 많은 작업에는 시간이 오래 걸릴 수 있습니다. 이러한 작업의 속도 일반적으로 네트워크 연결 속도 따라 제한 하지만 다른 네트워크 트래픽 및 복잡 한 작업으로도 적용 될 수 있습니다. 예를 들어 원격 FTP 서버에 연결할 필요 컴퓨터 먼저 해당 주소를 찾으려면 해당 서버 이름을 찾습니다. 해당 주소에서 서버에 연결할 응용 프로그램 시도 됩니다. 연결이 열리면 컴퓨터와 원격 서버는 파일 전송 프로토콜을 사용 하 여 대화 전에 시작 파일을 검색 하는 연결을 실제로 사용할 수 있습니다.

## <a name="see-also"></a>참고자료

[Win32 인터넷 확장(WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[MFC를 사용하여 인터넷 클라이언트 애플리케이션을 손쉽게 만드는 방법](../mfc/how-mfc-makes-it-easier-to-create-internet-client-applications.md)
