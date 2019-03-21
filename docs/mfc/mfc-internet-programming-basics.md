---
title: MFC 인터넷 프로그래밍 기본 사항
ms.date: 11/19/2018
helpviewer_keywords:
- ISAPI extensions, programming with ISAPI
- Internet applications [MFC]
- ISAPI
- ActiveX controls [MFC], Internet
- programming [MFC], Internet
- Web applications [MFC], MFC classes
- ISAPI filters [MFC], programming with ISAPI
- Internet applications [MFC], ActiveX controls
- Internet applications [MFC], writing
- Internet applications [MFC], Active technology
- Active technology [MFC]
- Internet content [MFC]
- WinInet classes [MFC]
ms.assetid: 6df2dfd0-6e3f-4587-9d01-2a32f00f8a6f
ms.openlocfilehash: 814e63272058200850424e9d5355637111527e1c
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57750287"
---
# <a name="mfc-internet-programming-basics"></a>MFC 인터넷 프로그래밍 기본 사항

Microsoft는 클라이언트와 서버 응용 프로그램 프로그래밍에 대 한 여러 Api를 제공 합니다. 인터넷에 대 한 많은 새 응용 프로그램을 쓰고 있습니다. 및 기술, 브라우저 기능 및 보안 옵션 변경, 새로운 유형의 응용 프로그램 기록 됩니다. 브라우저 실행 클라이언트 컴퓨터에 World Wide Web에 대 한 액세스를 제공 하 고 텍스트, 그래픽, ActiveX 컨트롤 및 문서를 포함 하는 HTML 페이지를 표시 합니다. 서버는 FTP, HTTP 및 gopher 서비스를 제공 하 고 서버 확장 CGI를 사용 하 여 응용 프로그램을 실행 합니다. 사용자 지정 응용 프로그램 정보를 검색 하 고 인터넷에서 데이터를 제공할 수 있습니다.

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용 되지 해야 하는 레거시 기술입니다. 자세한 내용은 [ActiveX 컨트롤](activex-controls.md)합니다.

![클라이언트 및 서버 응용 프로그램](../mfc/media/vc38bq1.gif "클라이언트 및 서버 응용 프로그램")

MFC는 인터넷 프로그래밍을 지 원하는 클래스를 제공 합니다. 사용할 수 있습니다 [COleControl](../mfc/reference/colecontrol-class.md) 하 고 [CDocObjectServer](../mfc/reference/cdocobjectserver-class.md) 및 관련 MFC ActiveX 컨트롤 및 액티브 문서를 작성 하는 클래스입니다. 와 같은 MFC 클래스를 사용할 수 있습니다 [CInternetSession](../mfc/reference/cinternetsession-class.md)를 [CFtpConnection](../mfc/reference/cftpconnection-class.md), 및 [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) 파일 및 FTP와 같은 인터넷 프로토콜을 사용 하 여 정보를 검색 하려면 HTTP 및 gopher 합니다.

## <a name="in-this-section"></a>섹션 내용

- [인터넷 관련 MFC 클래스](../mfc/internet-related-mfc-classes.md)

- [항목별 인터넷 정보](../mfc/internet-information-by-topic.md)

- [작업별 인터넷 정보](../mfc/internet-information-by-task.md)

- [인터넷의 액티브 기술](../mfc/active-technology-on-the-internet.md)

- [WinInet 기본 사항](../mfc/wininet-basics.md)

- [HTML 기본 사항](../mfc/html-basics.md)

## <a name="related-sections"></a>관련 단원

- [인터넷의 ActiveX 컨트롤](../mfc/activex-controls-on-the-internet.md)

- [인터넷의 비동기 모니커](../mfc/asynchronous-monikers-on-the-internet.md)

- [Win32 인터넷 확장(WinInet)](../mfc/win32-internet-extensions-wininet.md)

- [MFC 인터넷 프로그래밍 작업](../mfc/mfc-internet-programming-tasks.md)

- [애플리케이션 디자인 선택](../mfc/application-design-choices.md)

- [MFC 애플리케이션 작성](../mfc/writing-mfc-applications.md)

- [인터넷 애플리케이션 테스트](../mfc/testing-internet-applications.md)

- [인터넷 보안](../mfc/internet-security-cpp.md)

- [DHTML 컨트롤에 대한 ATL 지원](../atl/atl-support-for-dhtml-controls.md)

##  <a name="_core_web_sites_for_more_information"></a> 자세한 내용은 웹 사이트

Microsoft 인터넷 기술에 대 한 자세한 내용은 참조는 [Microsoft 개발자 네트워크 (MSDN)](http://go.microsoft.com/fwlink/p/?linkid=56322) 웹 사이트입니다. (링크는 예 고 없이 변경 될 수 있습니다.)

이 웹 사이트 개발자를 위한 Microsoft 개발 도구 및 기술 및 최근 및 예정 된 회의 대 한 주요 기사를 사용 하 여 정보를 포함 합니다. 이 페이지에서.NET 및 XML 개발자 센터를 비롯 한 많은 관련된 개발자 사이트를 이동할 수 있습니다. 또한 베타 Sdk 및 샘플을 다운로드할 수 있습니다.

합니다 [World Wide Web Consortium (W3C)](http://go.microsoft.com/fwlink/p/?linkid=37125) HTML, HTTP, CGI, 및 다른 웹 기술에 대 한 사양을 게시 합니다.

##  <a name="_core_more_internet_help"></a> 자세한 인터넷 도움말

Windows SDK의 OLE 섹션 OLE 프로그래밍에 대 한 추가 정보를 포함합니다. 이 정보를 직접 보다는 MFC 클래스를 통해 Win32 WinInet 함수를 사용 하는 방법에 대 한 세부 정보를 제공 합니다. 또한 인터넷 기술에 대 한 개요 정보를 포함 합니다.
