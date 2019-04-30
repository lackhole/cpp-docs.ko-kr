---
title: 일반적인 HTTP 클라이언트 응용 프로그램의 단계
ms.date: 11/04/2016
helpviewer_keywords:
- HTTP client applications [MFC]
- client applications [MFC], HTTP
- Internet applications [MFC], HTTP client applications
- applications [MFC], HTTP client
- Internet client applications [MFC], HTTP table
- WinInet classes [MFC], HTTP
ms.assetid: f86552e8-8acd-4b23-bdc5-0c3a247ebd74
ms.openlocfilehash: 59b585d3e6b8c9f13c585f5a712d33abd6123f67
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62306966"
---
# <a name="steps-in-a-typical-http-client-application"></a>일반적인 HTTP 클라이언트 응용 프로그램의 단계

다음 표에서 일반적인 HTTP 클라이언트 응용 프로그램에서 수행할 수 있는 단계를 보여줍니다.

|목표|수행할 작업|효과|
|---------------|----------------------|-------------|
|HTTP 세션을 시작 합니다.|만들기는 [CInternetSession](../mfc/reference/cinternetsession-class.md) 개체입니다.|WinInet을 초기화하고 서버에 연결합니다.|
|HTTP 서버에 연결 합니다.|사용 하 여 [CInternetSession::GetHttpConnection](../mfc/reference/cinternetsession-class.md#gethttpconnection)합니다.|반환 된 [CHttpConnection](../mfc/reference/chttpconnection-class.md) 개체입니다.|
|HTTP 요청을 엽니다.|사용 하 여 [CHttpConnection::OpenRequest](../mfc/reference/chttpconnection-class.md#openrequest)합니다.|반환 된 [CHttpFile](../mfc/reference/chttpfile-class.md) 개체입니다.|
|HTTP 요청을 보냅니다.|사용 하 여 [CHttpFile::AddRequestHeaders](../mfc/reference/chttpfile-class.md#addrequestheaders) 하 고 [chttpfile:: Sendrequest](../mfc/reference/chttpfile-class.md#sendrequest)합니다.|파일을 찾습니다. 파일을 찾을 수 없으면 FALSE를 반환합니다.|
|파일에서 읽습니다.|사용 하 여 [CHttpFile](../mfc/reference/chttpfile-class.md)합니다.|지정 된 사용자가 제공 하는 버퍼를 사용 하 여 바이트 수를 읽습니다.|
|예외 처리|사용 된 [CInternetException](../mfc/reference/cinternetexception-class.md) 클래스입니다.|모든 공용 인터넷 예외 형식을 처리합니다.|
|HTTP 세션을 종료 합니다.|삭제 합니다 [CInternetSession](../mfc/reference/cinternetsession-class.md) 개체입니다.|열린 파일 핸들 및 연결을 자동으로 정리합니다.|

## <a name="see-also"></a>참고자료

[Win32 인터넷 확장(WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[인터넷 클라이언트 클래스의 필수 구성 요소](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[MFC WinInet 클래스를 사용하여 인터넷 클라이언트 애플리케이션 작성](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
