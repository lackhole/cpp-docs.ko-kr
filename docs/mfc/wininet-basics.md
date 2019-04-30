---
title: WinInet 기본 사항
ms.date: 11/04/2016
helpviewer_keywords:
- OnStatusCallback method [MFC]
- WinInet classes [MFC], displaying progress
- WinInet classes [MFC], about WinInet classes
ms.assetid: 665de5ac-e80d-427d-8d91-2ae466885940
ms.openlocfilehash: 79ec102aa27440c64f03c6e22b9f2fe959cac6b9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399553"
---
# <a name="wininet-basics"></a>WinInet 기본 사항

다운로드 하 고 응용 프로그램 내에서 파일을 업로드할 FTP 지원을 추가할 WinInet을 사용할 수 있습니다. 재정의할 수 있습니다 [OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback) 사용 하는 *dwContext* 매개 변수를 검색 하 고 파일을 다운로드 하는 대로 사용자에 게 진행률 정보를 제공 합니다.

이 문서에는 다음 항목이 포함 됩니다.

- [아주 간단한 브라우저를 제작](#_core_create_a_very_simple_browser)

- [웹 페이지를 다운로드 합니다.](#_core_download_a_web_page)

- [FTP 파일](#_core_ftp_a_file)

- [Gopher 디렉터리를 검색 합니다.](#_core_retrieve_a_gopher_directory)

- [파일을 전송 하는 동안 진행률 정보를 표시 합니다.](#_core_display_progress_information_while_transferring_files)

아래의 코드 부분에는 간단한 브라우저를 만들고, 파일을 FTP 웹 페이지를 다운로드, gopher 파일을 검색 하는 방법을 보여 줍니다. 전체 예제로 되지는지 않습니다 및 예외 처리를 포함 하는 일부입니다.

WinInet에 대 한 자세한 내용은 참조 하세요. [Win32 인터넷 확장명 (WinInet)](../mfc/win32-internet-extensions-wininet.md)합니다.

##  <a name="_core_create_a_very_simple_browser"></a> 아주 간단한 브라우저를 제작

[!code-cpp[NVC_MFCWinInet#1](../mfc/codesnippet/cpp/wininet-basics_1.cpp)]

##  <a name="_core_download_a_web_page"></a> 웹 페이지를 다운로드 합니다.

[!code-cpp[NVC_MFCWinInet#2](../mfc/codesnippet/cpp/wininet-basics_2.cpp)]

##  <a name="_core_ftp_a_file"></a> FTP 파일

[!code-cpp[NVC_MFCWinInet#3](../mfc/codesnippet/cpp/wininet-basics_3.cpp)]

##  <a name="_core_retrieve_a_gopher_directory"></a> Gopher 디렉터리를 검색 합니다.

[!code-cpp[NVC_MFCWinInet#4](../mfc/codesnippet/cpp/wininet-basics_4.cpp)]

## <a name="use-onstatuscallback"></a>OnStatusCallback 사용

WinInet 클래스를 사용 하는 경우 사용할 수 있습니다 합니다 [OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback) 응용 프로그램의 소속 [CInternetSession](../mfc/reference/cinternetsession-class.md) 상태 정보를 검색 하는 개체입니다. 파생 하는 경우 사용자 고유의 `CInternetSession` 개체를 재정의 `OnStatusCallback`, 상태 콜백을 사용 하도록 설정 하 고 MFC 호출에 `OnStatusCallback` 인터넷 세션에서 모든 활동에 대 한 진행률 정보를 사용 하 여 함수.

단일 세션 (여기서 해당 수명 동안 다양 한 고유 작업을 수행할 수 있습니다) 여러 연결을 지원 않기 때문에 `OnStatusCallback` 특정 연결이 나 트랜잭션이 사용 하 여 각 상태 변경 내용을 식별 하는 메커니즘을 해야 합니다. 이 메커니즘은 대부분 WinInet 지원 클래스의 멤버 함수에 지정 된 컨텍스트 ID 매개 변수로 제공 됩니다. 이 매개 변수는 항상 형식 **DWORD** 있고 이름이 항상 *dwContext*합니다.

특정 인터넷 개체에 할당 된 컨텍스트 개체에서 발생 하는 활동을 식별 하는 때에 사용 되며 합니다 `OnStatusCallback` 의 멤버는 `CInternetSession` 개체입니다. 에 대 한 호출 `OnStatusCallback` 여러 매개 변수를 수신 합니다. 이러한 매개 변수는 진행는 트랜잭션 및 연결에 대 한 응용 프로그램에 지시 하기 위해 함께 작동 합니다.

만들 때를 `CInternetSession` 지정할 수 있습니다 개체를 *dwContext* 생성자 매개 변수입니다. `CInternetSession` 컨텍스트 ID;을 사용 하지 않는 자체 그 대신, 진행 상황에 맞는 ID 전달 **InternetConnection**-파생 개체를 자체의 컨텍스트 ID를 가져오는 명시적으로 하지 않습니다. 다시, 이러한 `CInternetConnection` 개체에 따라 컨텍스트 ID를 전달 합니다 `CInternetFile` 는 다른 컨텍스트 ID를 명시적으로 지정 하지 않으면 만들 개체 반면에 자신만의 특정 컨텍스트 ID, 개체 및 모든 작업을 지정 수행 하는 경우에 연결 됩니다 컨텍스트 ID와 사용 하 여 컨텍스트 Id를 사용 하 여 사용자에 게 지정 되는 상태 정보를 식별 하 여 `OnStatusCallback` 함수입니다.

##  <a name="_core_display_progress_information_while_transferring_files"></a> 파일을 전송 하는 동안 진행률 정보를 표시 합니다.

예를 들어 파일을 읽기 위해 FTP 서버를 사용 하 여 연결을 만들고 웹 페이지에 HTTP 서버에 연결 하는 응용 프로그램을 작성 하는 경우 해야는 `CInternetSession` 개체, 두 `CInternetConnection` 개체 (하나는 `CFtpSession` 다른 고 `CHttpSession`), 두 개의 `CInternetFile` 개체 (각 연결에 대해 하나). 기본값을 사용 하는 경우는 *dwContext* 매개 변수를 구분 하지 못할 수는 `OnStatusCallback` FTP 연결에 대 한 진행률을 나타내는 호출의 진행률을 나타내는 호출을 HTTP 연결입니다. 지정 하는 경우는 *dwContext* 나중에 대 한 테스트 수 있는 ID `OnStatusCallback`, 작업 생성 콜백을 배울 수 있습니다.

## <a name="see-also"></a>참고자료

[MFC 인터넷 프로그래밍 기본 사항](../mfc/mfc-internet-programming-basics.md)<br/>
[Win32 인터넷 확장(WinInet)](../mfc/win32-internet-extensions-wininet.md)
