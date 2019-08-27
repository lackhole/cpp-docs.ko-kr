---
title: 일반적인 인터넷 클라이언트 애플리케이션의 단계
ms.date: 11/04/2016
helpviewer_keywords:
- Internet client applications [MFC], general table
- WinInet classes [MFC], programming
- Internet applications [MFC], client applications
ms.assetid: 7aba135c-7c15-4e2f-8c34-bbaf792c89a6
ms.openlocfilehash: 9762e762680e2ac530b87baeac7afdea77ef6f14
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62306940"
---
# <a name="steps-in-a-typical-internet-client-application"></a>일반적인 인터넷 클라이언트 애플리케이션의 단계

다음 표에서 일반적인 인터넷 클라이언트 응용 프로그램에서 수행할 수 있는 단계를 보여 줍니다.

|목표|수행할 작업|효과|
|---------------|----------------------|-------------|
|인터넷 세션을 시작 합니다.|만들기는 [CInternetSession](../mfc/reference/cinternetsession-class.md) 개체입니다.|WinInet을 초기화하고 서버에 연결합니다.|
|(제한 또는 예제에 대 한 재시도 횟수)는 인터넷 쿼리 옵션을 설정 합니다.|사용 하 여 [CInternetSession::SetOption](../mfc/reference/cinternetsession-class.md#setoption)합니다.|작업이 성공 하지 못한 경우 FALSE를 반환 합니다.|
|세션의 상태를 모니터링 하는 콜백 함수를 설정 합니다.|사용 하 여 [CInternetSession::EnableStatusCallback](../mfc/reference/cinternetsession-class.md#enablestatuscallback)합니다.|설정에 대 한 콜백을 [cinternetsession:: Onstatuscallback](../mfc/reference/cinternetsession-class.md#onstatuscallback)합니다. 재정의 `OnStatusCallback` 고유한 콜백 루틴을 만들려고 합니다.|
|인터넷, 인트라넷 서버 또는 로컬 파일에 연결 합니다.|사용 하 여 [CInternetSession::OpenURL](../mfc/reference/cinternetsession-class.md#openurl)합니다.|URL을 구문 분석 하 고 지정된 된 서버에 연결을 엽니다. 반환 된 [CStdioFile](../mfc/reference/cstdiofile-class.md) (전달 하는 경우 `OpenURL` 로컬 파일 이름). 서버 또는 파일에서 검색 데이터에 액세스 하는 개체입니다.|
|파일에서 읽습니다.|사용 하 여 [cinternetfile:: Read](../mfc/reference/cinternetfile-class.md#read)합니다.|지정 된 사용자가 제공 하는 버퍼를 사용 하 여 바이트 수를 읽습니다.|
|예외 처리|사용 된 [CInternetException](../mfc/reference/cinternetexception-class.md) 클래스입니다.|모든 공용 인터넷 예외 형식을 처리합니다.|
|인터넷 세션을 종료 합니다.|삭제 합니다 [CInternetSession](../mfc/reference/cinternetsession-class.md) 개체입니다.|열린 파일 핸들 및 연결을 자동으로 정리합니다.|

## <a name="see-also"></a>참고자료

[Win32 인터넷 확장(WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[인터넷 클라이언트 클래스의 필수 구성 요소](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[MFC WinInet 클래스를 사용하여 인터넷 클라이언트 애플리케이션 작성](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
