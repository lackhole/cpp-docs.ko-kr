---
title: MFC WinInet 클래스를 사용하여 인터넷 클라이언트 응용 프로그램 작성
ms.date: 11/04/2016
helpviewer_keywords:
- Internet client applications [MFC]
- WinInet classes [MFC], programming
- Internet client applications [MFC], writing
- Internet applications [MFC], WinInet
- Internet applications [MFC], client applications
- MFC, Internet applications
ms.assetid: a2c4a40c-a94e-4b3e-9dbf-f8a8dc8e5428
ms.openlocfilehash: 6e32210217321e4eb59d7d3e666a4f5494eb3642
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399475"
---
# <a name="writing-an-internet-client-application-using-mfc-wininet-classes"></a>MFC WinInet 클래스를 사용하여 인터넷 클라이언트 응용 프로그램 작성

모든 인터넷 클라이언트 응용 프로그램의 기본은 인터넷 세션입니다. MFC 인터넷 세션 클래스의 개체로 구현 [CInternetSession](../mfc/reference/cinternetsession-class.md)합니다. 이 클래스를 사용 하 여 인터넷 세션을 하나 또는 여러 개의 세션을 만들 수 있습니다.

해야 하는 서버와 통신 하는 [CInternetConnection](../mfc/reference/cinternetconnection-class.md) 개체와 `CInternetSession`합니다. 만들 수 있습니다는 `CInternetConnection` 를 사용 하 여 [cinternetsession:: Getftpconnection](../mfc/reference/cinternetsession-class.md#getftpconnection)하십시오 [CInternetSession::GetHttpConnection](../mfc/reference/cinternetsession-class.md#gethttpconnection), 또는 [CInternetSession::GetGopherConnection](../mfc/reference/cinternetsession-class.md#getgopherconnection). 이러한 호출의 각 프로토콜 종류에 따라 다릅니다. 이러한 호출은 읽기 또는 쓰기에 대 한 서버에서 파일을 열지 마십시오. 데이터를 쓰거나 읽을 하려는 경우 별도 단계로 파일을 열어야 합니다.

대부분의 인터넷 세션에 대 한 합니다 `CInternetSession` 사용 하 여 손에서 직접 작동 하는 개체를 [CInternetFile](../mfc/reference/cinternetfile-class.md) 개체:

- 인스턴스의 인터넷 세션을 만들어야 [CInternetSession](../mfc/reference/cinternetsession-class.md)합니다.

- 인스턴스의 경우 인터넷 세션을 읽거나 쓰는 데이터를 만들어야 `CInternetFile` (또는 해당 서브 클래스 [CHttpFile](../mfc/reference/chttpfile-class.md) 하거나 [CGopherFile](../mfc/reference/cgopherfile-class.md)). 데이터를 읽는 가장 쉬운 방법은 호출 하는 것 [CInternetSession::OpenURL](../mfc/reference/cinternetsession-class.md#openurl)합니다. 이 함수는 로케이터 URL (Universal Resource) 사용자가 제공 구문 분석 URL에서 지정한 서버에 연결 하 고 읽기 전용 반환 `CInternetFile` 개체입니다. `CInternetSession::OpenURL` 프로토콜 형식으로 한정 되지-모든 FTP, HTTP 또는 gopher URL에 대 한 동일한 호출을 작동 합니다. `CInternetSession::OpenURL` 로컬 파일에도 작동 (반환 된 `CStdioFile` 대신를 `CInternetFile`).

- 세션 읽기 하지 않거나 데이터를 쓰는 인터넷 하지만 FTP 디렉터리의 파일을 삭제 하는 등의 다른 작업을 수행 하는 경우의 인스턴스를 만들 해야 하지 `CInternetFile`합니다.

두 가지 방법으로 만들려면를 `CInternetFile` 개체:

- 사용 하는 경우 `CInternetSession::OpenURL` 서버 연결에 대 한 호출을 연결할 `OpenURL` 반환을 `CStdioFile`입니다.

- 경우 사용 하 여 `CInternetSession::GetFtpConnection`, `GetGopherConnection`, 또는 `GetHttpConnection` 호출 하 여 서버 연결 해야 합니다 `CFtpConnection::OpenFile`, `CGopherConnection::OpenFile`, 또는 `CHttpConnection::OpenRequest`각각 반환 하는 `CInternetFile`를 `CGopherFile`, 또는 `CHttpFile`, 각각.

인터넷 클라이언트 응용 프로그램을 구현 하는 단계에 따라 일반 인터넷 클라이언트를 만드는 지 여부에 따라 달라 집니다 `OpenURL` 중 하나를 사용 하는 프로토콜별 클라이언트는 `GetConnection` 함수입니다.

## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [FTP, HTTP 및 gopher를 사용 하 여 일반적으로 작동 하는 인터넷 클라이언트 응용 프로그램을 작성 하는 방법](../mfc/steps-in-a-typical-internet-client-application.md)

- [파일을 FTP 클라이언트 응용 프로그램을 작성 하는 방법](../mfc/steps-in-a-typical-ftp-client-application.md)

- [파일을 열지 않습니다 하지만 파일을 삭제 하는 등 디렉터리 작업을 수행 하는 FTP 클라이언트 응용 프로그램을 작성 하는 방법](../mfc/steps-in-a-typical-ftp-client-application-to-delete-a-file.md)

- [Gopher 클라이언트 응용 프로그램을 작성 하는 방법](../mfc/steps-in-a-typical-gopher-client-application.md)

- [HTTP 클라이언트 응용 프로그램을 작성 하는 방법](../mfc/steps-in-a-typical-http-client-application.md)

## <a name="see-also"></a>참고자료

[Win32 인터넷 확장(WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[인터넷 클라이언트 애플리케이션을 만들기 위한 MFC 클래스](../mfc/mfc-classes-for-creating-internet-client-applications.md)<br/>
[인터넷 클라이언트 클래스의 필수 구성 요소](../mfc/prerequisites-for-internet-client-classes.md)
