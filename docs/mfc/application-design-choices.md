---
title: 애플리케이션 디자인 선택
ms.date: 11/04/2016
helpviewer_keywords:
- design
- application design [MFC], design goals
- application design [MFC], Internet applications
- Internet applications [MFC], designing applications
- Internet [MFC], vs. intranets
- applications [MFC], Internet
- server applications [MFC], vs. client applications on Internet
- client applications [MFC], vs. server applications on Internet
ms.assetid: 9b96172c-b4d4-4c69-bfb2-226ce0de6d08
ms.openlocfilehash: cdb294e4ab808a7e4cbcec457f6e744eff9f12cb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394665"
---
# <a name="application-design-choices"></a>애플리케이션 디자인 선택

이 문서에서는 인터넷에 대 한 프로그래밍 하는 경우를 고려해 야 할 디자인 문제 중 일부를 설명 합니다.

이 문서에서 다루는 항목은 다음과 같습니다.

- [Intranet Versus Internet](#_core_intranet_versus_internet)

- [클라이언트 또는 서버 응용 프로그램](#_core_client_or_server_application)

- [](#_core_the_web_page)

- [브라우저 또는 독립 실행형 응용 프로그램](#_core_browser_or_standalone)

- [인터넷에서 COM](#_core_com_on_the_internet)

- [클라이언트 데이터 서비스 다운로드](#_core_client_data_download_services)

이제 프로그램 작성을 시작, 참조에 준비가 되었으면 [MFC 응용 프로그램 작성](../mfc/writing-mfc-applications.md)합니다.

##  <a name="_core_intranet_versus_internet"></a> Intranet Versus Internet

대부분의 응용 프로그램에는 인터넷에서 실행 되며 브라우저 및 인터넷 액세스를 가진 사람이 면 누구나 액세스할 수 있습니다. 기업 인트라넷 TCP/IP 프로토콜을 사용 하 여 회사 전체 네트워크가 있으며 웹 브라우저도 구현 합니다. 인트라넷 회사 수준 정보를 쉽게 업그레이드할 수 있도록 중앙 원본을 제공합니다. 소프트웨어를 업그레이드 하는 데, 제공 하 고 설문 조사를 불러와, 고객 지원에 대 한 및 정보를 사용할 수 있습니다. 다음 표에서 인터넷 및 인트라넷의 기능을 비교 합니다.

|인터넷|Intranet|
|--------------|--------------|
|낮은 대역폭|높은 대역폭|
|데이터 및 시스템의 보안이 약화|데이터 및 시스템에 대 한 액세스 제어|
|콘텐츠의 최소 컨트롤|콘텐츠의 높은 제어|

##  <a name="_core_client_or_server_application"></a> 클라이언트 또는 서버 응용 프로그램

응용 프로그램은 클라이언트 컴퓨터 또는 서버 컴퓨터에서 실행할 수 있습니다. 응용 프로그램 수는 서버에 저장 및 다음 인터넷에서 다운로드 되어 클라이언트 컴퓨터에서 실행 합니다. MFC WinInet 클래스 파일을 다운로드 하도록 클라이언트 응용 프로그램에 사용 됩니다. MFC 및 비동기 모니커 클래스 파일을 다운로드 하 고 컨트롤 속성에 사용 됩니다. ActiveX 컨트롤 및 액티브 문서 클래스는 클라이언트 응용 프로그램 및 클라이언트에서 실행 하려면 서버에서 다운로드 하는 응용 프로그램에 사용 됩니다.

##  <a name="_core_the_web_page"></a> 웹 페이지: HTML, 액티브 문서 ActiveX 컨트롤

Microsoft는 웹 페이지의 콘텐츠를 제공 하는 몇 가지를 제공 합니다. 표준 HTML 또는 HTML를 사용할 수 있는 웹 페이지와 같은 ActiveX 컨트롤과 같은 동적 콘텐츠를 제공 하는 개체 태그를 확장 합니다.

웹 브라우저는 일반적으로 HTML 페이지를 표시합니다. 액티브 문서는 COM 지원 브라우저의 간단한 포인트 클릭 인터페이스에서 응용 프로그램의 데이터를 표시할 수도 있습니다. 액티브 문서 서버 자체 메뉴 및 도구 모음을 사용 하 여 전체 클라이언트 영역에서 문서를 전체 프레임을 표시할 수 있습니다.

작성 된 ActiveX 컨트롤을 서버에서 비동기적으로 다운로드 하 고 웹 페이지에 표시 수입니다. 서버에 정보를 보내기 전에 클라이언트 쪽 유효성 검사를 수행할 VBScript 같은 스크립트 언어를 사용할 수 있습니다.

##  <a name="_core_browser_or_standalone"></a> 브라우저 또는 독립 실행형 응용 프로그램

브라우저에서 볼 수 있는 액티브 문서 서버 HTML 페이지에 포함 된 ActiveX 컨트롤을 작성할 수 있습니다. 웹 서버에서 ISAPI 응용 프로그램을 실행 하 라는 요청을 전송 하는 단추를 포함 하는 HTML 페이지를 작성할 수 있습니다. 인터넷 프로토콜을 사용 하 여 파일을 다운로드 하 고 브라우저 응용 프로그램을 사용할 필요 없이 사용자에 게 정보를 표시 하는 독립 실행형 응용 프로그램을 작성할 수 있습니다.

##  <a name="_core_com_on_the_internet"></a> 인터넷에서 COM

ActiveX 컨트롤, 액티브 문서 및 비동기 모니커 모든 COM (구성 요소 개체 모델) 기술을 사용합니다.

ActiveX 컨트롤 인터넷 사이트에서 문서와 페이지에 동적 콘텐츠를 제공합니다. COM을 사용 하 여 ActiveX 컨트롤 및 액티브 문서를 사용 하 여 전체 프레임 문서를 작성할 수 있습니다.

비동기 모니커는 증분을 포함 하 여 인터넷 환경에서 제대로 작동 하려면 컨트롤을 사용 하도록 설정 하려면 기능을 제공 하거나 점진적으로 데이터를 다운로드할 것을 의미 합니다. 컨트롤 수도 검색 데이터 비동기적으로 동시에 있는 다른 컨트롤과 함께 잘 작동도 해야 합니다.

##  <a name="_core_client_data_download_services"></a> 클라이언트 데이터 서비스 다운로드

두 가지 클라이언트에 데이터를 전송 하는 데 도움이 되는 Api 집합은 WinInet 및 비동기 모니커입니다. 큰.gif,.avi 파일 및 HTML 페이지에서 ActiveX 컨트롤에 있는 경우에 하거나 비동기 모니커를 사용 하 여 비동기적으로 WinInet을 사용 하 여 비동기적으로 다운로드 하 여 사용자에 대 한 응답성을 늘릴 수 있습니다.

인터넷에서 일반적인 작업 데이터를 전송 합니다. 이미 액티브 기술 (예: ActiveX 컨트롤을 사용 하는 경우)를 사용할 경우 점진적으로 다운로드 될 때 데이터를 렌더링할 비동기 모니커를 사용할 수 있습니다. Gopher HTTP, FTP 등 공통 인터넷 프로토콜을 사용 하 여 데이터를 전송할 WinInet을 사용할 수 있습니다. 두 방법 모두 프로토콜 독립성을 제공 하 고 WinSock 및 TCP/IP를 사용 하는 추상 계층을 제공 합니다. 계속 사용할 수 있습니다 [WinSock](../mfc/windows-sockets-in-mfc.md) 직접.

다음 표에서 MFC를 사용 하 여 인터넷을 통해 데이터를 전송 하는 몇 가지를 보여 줍니다.

|이 프로토콜을 사용 하 여|이러한 상황에서|이러한 클래스를 사용 하 여|
|-----------------------|----------------------------|-------------------------|
|[인터넷 다운로드를 사용 하 여 비동기 모니커](../mfc/asynchronous-monikers-on-the-internet.md)|COM, ActiveX 컨트롤을 사용 하 여 비동기 전송 및의 인터넷 프로토콜입니다.|[CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md), [CDataPathProperty](../mfc/reference/cdatapathproperty-class.md)|
|[WinInet](../mfc/win32-internet-extensions-wininet.md)|HTTP, FTP 및 gopher 인터넷 프로토콜입니다. 데이터는 동기적 또는 비동기적으로 전송 될 수 있습니다 하 고 시스템 캐시에 저장 됩니다.|[CInternetSession](../mfc/reference/cinternetsession-class.md), [CFtpFileFind](../mfc/reference/cftpfilefind-class.md)를 [CGopherFileFind](../mfc/reference/cgopherfilefind-class.md), 등입니다.|
|[WinSock](../mfc/windows-sockets-in-mfc.md)|최대 효율성 및 제어 합니다. 소켓 및 TCP/IP 프로토콜에 대 한 이해가 필요 합니다.|[CSocket](../mfc/reference/csocket-class.md), [CAsyncSocket](../mfc/reference/casyncsocket-class.md)|

## <a name="see-also"></a>참고자료

[MFC 인터넷 프로그래밍 작업](../mfc/mfc-internet-programming-tasks.md)<br/>
[MFC 인터넷 프로그래밍 기본 사항](../mfc/mfc-internet-programming-basics.md)<br/>
[Win32 인터넷 확장(WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[인터넷의 비동기 모니커](../mfc/asynchronous-monikers-on-the-internet.md)
