---
title: Win32 인터넷 클래스
ms.date: 09/12/2018
f1_keywords:
- vc.classes.win32
helpviewer_keywords:
- Internet classes [MFC]
- WinInet classes [MFC], classes
- Win32 [MFC], Internet classes
- Windows API [MFC], Internet classes
ms.assetid: b49601d5-3025-4068-9408-316b54ee4375
ms.openlocfilehash: c067d0c0067ee13b0e6ce6d84fd97135274c88b5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62326731"
---
# <a name="win32-internet-classes"></a>Win32 인터넷 클래스

MFC는 인터넷 프로그래밍을 쉽게 수행할 수 있도록 Win32 인터넷 (WinInet) 및 ActiveX 기술은 래핑합니다.

>[!IMPORTANT]
> ActiveX는 새로운 개발에 사용 되지 해야 하는 레거시 기술입니다. ActiveX를 대체 하는 최신 기술에 대 한 자세한 내용은 참조 하세요. [ActiveX 컨트롤](activex-controls.md)합니다.

[CInternetSession](../mfc/reference/cinternetsession-class.md)<br/>
만들고 초기화 한 인터넷 세션 또는 여러 동시 인터넷 세션, 필요한 경우 프록시 서버에 연결을 설명 합니다.

[CInternetConnection](../mfc/reference/cinternetconnection-class.md)<br/>
인터넷 서버와의 연결을 관리합니다.

[CInternetFile](../mfc/reference/cinternetfile-class.md)<br/>
이 클래스와 파생된 클래스에는 인터넷 프로토콜을 사용 하는 원격 시스템에서 파일에 대 한 액세스를 허용 합니다.

[CHttpConnection](../mfc/reference/chttpconnection-class.md)<br/>
HTTP 서버와의 연결을 관리합니다.

[CHttpFile](../mfc/reference/chttpfile-class.md)<br/>
검색 하 여 HTTP 서버에 파일을 참조 하는 기능을 제공 합니다.

[CGopherFile](../mfc/reference/cgopherfile-class.md)<br/>
Gopher 서버에서 파일을 찾고 읽는 기능을 제공합니다.

[CFtpConnection](../mfc/reference/cftpconnection-class.md)<br/>
FTP 서버에 대 한 연결을 관리합니다.

[CGopherConnection](../mfc/reference/cgopherconnection-class.md)<br/>
Gopher 서버에 대 한 연결을 관리합니다.

[CFileFind](../mfc/reference/cfilefind-class.md)<br/>
로컬 및 인터넷 파일 검색을 수행합니다.

[CFtpFileFind](../mfc/reference/cftpfilefind-class.md)<br/>
FTP 서버의 인터넷 파일 검색에 유용합니다.

[CGopherFileFind](../mfc/reference/cgopherfilefind-class.md)<br/>
Gopher 서버의 인터넷 파일 검색에 유용합니다.

[CGopherLocator](../mfc/reference/cgopherlocator-class.md)<br/>
Gopher 서버에서 Gopher "로케이터"를 가져오고 로케이터 형식을 확인하며 `CGopherFileFind`에 로케이터를 사용할 수 있게 합니다.

[CInternetException](../mfc/reference/cinternetexception-class.md)<br/>
인터넷 작업과 관련된 예외 상태를 나타냅니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../mfc/class-library-overview.md)
