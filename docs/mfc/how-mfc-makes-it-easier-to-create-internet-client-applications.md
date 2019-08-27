---
title: MFC를 사용하여 인터넷 클라이언트 애플리케이션을 손쉽게 만드는 방법
ms.date: 11/04/2016
helpviewer_keywords:
- Internet client applications [MFC], MFC
- Internet applications [MFC], MFC
- MFC, Internet applications
ms.assetid: 94437b3f-f15c-437d-b5fd-264a2efec9ab
ms.openlocfilehash: ffeed3a844fb86acf1bf8c5181c59529824c27f9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405757"
---
# <a name="how-mfc-makes-it-easier-to-create-internet-client-applications"></a>MFC를 사용하여 인터넷 클라이언트 애플리케이션을 손쉽게 만드는 방법

Microsoft Foundation Classes MFC 프로그래머에 게 친숙 한 컨텍스트를 제공 하는 방식으로 Win32 인터넷 확장명 (WinInet) 함수를 캡슐화 합니다. MFC는 세 가지 인터넷 파일 클래스를 제공 ([CInternetFile](../mfc/reference/cinternetfile-class.md)를 [CHttpFile](../mfc/reference/chttpfile-class.md), 및 [CGopherFile](../mfc/reference/cgopherfile-class.md))에서 파생 된 [CStdioFile](../mfc/reference/cstdiofile-class.md) 클래스 . 뿐만 아니라 쉽게 검색 및 인터넷 데이터 조작을 사용 하는 프로그래머에 게 친숙 한 `CStdioFile` 일관 되 고 투명 한 방식으로 로컬 파일 및 인터넷 파일 로컬 파일에 대 한 있지만 이러한 클래스를 사용 하 여 처리할 수 있습니다.

MFC WinInet 클래스와 동일한 기능을 제공 `CStdioFile` 인터넷을 통해 전송 되는 데이터에 대 한 합니다. 이러한 클래스를 사용 하면 HTTP, FTP 및 gopher에 대 한 인터넷 프로토콜을 추상화 하는 프로그래밍 인터페이스가, 인터넷 인식 응용 프로그램을 만드는 빠르고 간단한 경로 제공 합니다. 상위 수준 응용 프로그램에 있습니다. 예를 들어 FTP 서버에 연결할 여전히 낮은 수준에서 여러 단계 하는데 MFC 개발자는 하면 한 번 호출 되도록 `CInternetSession::GetFTPConnection` 해당 연결을 만듭니다.

또한 MFC WinInet 클래스는 다음과 같은 이점을 제공합니다.

- 버퍼링 된 I/O

- 데이터에 대 한 형식이 안전한 핸들

- 다양 한 함수에 대 한 기본 매개 변수

- 일반적인 인터넷 오류의 예외 처리

- 열린 핸들 및 연결의 자동 정리

## <a name="see-also"></a>참고자료

[Win32 인터넷 확장(WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[WinInet을 사용하여 인터넷 클라이언트 애플리케이션을 손쉽게 만드는 방법](../mfc/how-wininet-makes-it-easier-to-create-internet-client-applications.md)
