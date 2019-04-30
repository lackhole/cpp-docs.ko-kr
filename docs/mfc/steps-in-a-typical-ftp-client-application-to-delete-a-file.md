---
title: 일반적인 FTP 클라이언트 응용 프로그램에서 파일을 삭제하는 단계
ms.date: 11/04/2016
helpviewer_keywords:
- Internet client applications [MFC], FTP delete
- WinInet classes [MFC], FTP
- FTP (File Transfer Protocol) [MFC], client applications
- Internet applications [MFC], FTP client applications
ms.assetid: 2c347a96-c0a4-4827-98fe-668406e552bc
ms.openlocfilehash: 6d2a920d3053a920638dd20a23e1c2334745bbc3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62307057"
---
# <a name="steps-in-a-typical-ftp-client-application-to-delete-a-file"></a>일반적인 FTP 클라이언트 응용 프로그램에서 파일을 삭제하는 단계

다음 표에서는 파일을 삭제하는 일반적인 FTP 클라이언트 응용 프로그램에서 수행할 수 있는 단계를 보여 줍니다.

|목표|수행할 작업|효과|
|---------------|----------------------|-------------|
|FTP 세션을 시작합니다.|만들기는 [CInternetSession](../mfc/reference/cinternetsession-class.md) 개체입니다.|WinInet을 초기화하고 서버에 연결합니다.|
|FTP 서버에 연결합니다.|사용 하 여 [cinternetsession:: Getftpconnection](../mfc/reference/cinternetsession-class.md#getftpconnection)합니다.|반환 된 [CFtpConnection](../mfc/reference/cftpconnection-class.md) 개체입니다.|
|FTP 서버의 올바른 디렉터리에 있는지 확인합니다.|사용 하 여 [cftpconnection:: Getcurrentdirectory](../mfc/reference/cftpconnection-class.md#getcurrentdirectory) 하거나 [cftpconnection:: Getcurrentdirectoryasurl](../mfc/reference/cftpconnection-class.md#getcurrentdirectoryasurl)합니다.|선택한 멤버 함수에 따라 서버에서 현재 연결된 디렉터리의 URL 또는 이름을 반환합니다.|
|서버의 새로운 FTP 디렉터리로 변경합니다.|사용 하 여 [:: Setcurrentdirectory](../mfc/reference/cftpconnection-class.md#setcurrentdirectory)합니다.|서버에서 현재 연결된 디렉터리를 변경합니다.|
|FTP 디렉터리에서 첫 번째 파일을 찾습니다.|사용 하 여 [:: Findfile](../mfc/reference/cftpfilefind-class.md#findfile)합니다.|첫 번째 파일을 찾습니다. 파일이 발견되지 않으면 FALSE를 반환합니다.|
|FTP 디렉터리에서 다음 파일을 찾습니다.|사용 하 여 [:: Findnextfile](../mfc/reference/cftpfilefind-class.md#findnextfile)합니다.|다음 파일을 찾습니다. 파일을 찾을 수 없으면 FALSE를 반환합니다.|
|찾은 파일을 삭제 `FindFile` 또는 `FindNextFile`합니다.|사용 하 여 [CFtpConnection::Remove](../mfc/reference/cftpconnection-class.md#remove), 파일 이름을 사용 하 여 반환한 `FindFile` 또는 `FindNextFile`합니다.|서버에서 읽기 또는 쓰기용 파일을 삭제합니다.|
|예외 처리|사용 된 [CInternetException](../mfc/reference/cinternetexception-class.md) 클래스입니다.|모든 공용 인터넷 예외 형식을 처리합니다.|
|FTP 세션을 종료합니다.|삭제 합니다 [CInternetSession](../mfc/reference/cinternetsession-class.md) 개체입니다.|열린 파일 핸들 및 연결을 자동으로 정리합니다.|

## <a name="see-also"></a>참고자료

[Win32 인터넷 확장(WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[인터넷 클라이언트 클래스의 필수 구성 요소](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[MFC WinInet 클래스를 사용하여 인터넷 클라이언트 애플리케이션 작성](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
