---
title: 인터넷 클라이언트 응용 프로그램을 만들기 위한 MFC 클래스
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, WinInet classes
- WinInet classes [MFC], classes
- classes [MFC], MFC
- Internet client applications [MFC], MFC
- Internet applications [MFC], MFC
ms.assetid: 67d34117-9839-4f4b-8bb8-0e4a9471c606
ms.openlocfilehash: 9201859c6a5d9fe2b31c3fc4348a42ff9566fc8c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62239225"
---
# <a name="mfc-classes-for-creating-internet-client-applications"></a>인터넷 클라이언트 응용 프로그램을 만들기 위한 MFC 클래스

MFC는 인터넷 클라이언트 응용 프로그램을 작성 하기 위한 다음 클래스 및 전역 함수를 제공 합니다. 들여쓰기 된 들여쓰지 않은 상위 클래스에서 파생 되는 것을 나타냅니다. `CGopherFile` 및 `CHttpFile` 에서 파생 `CInternetFile`예를 들어 있습니다. 이러한 클래스 및 전역 함수 afx에서 선언 됩니다. 시간, 제외 하 고 `CFileFind`, AFX에 선언 된 합니다. 8.

## <a name="classes"></a>클래스

- [CInternetSession](../mfc/reference/cinternetsession-class.md)

- [CInternetConnection](../mfc/reference/cinternetconnection-class.md)

   - [CFtpConnection](../mfc/reference/cftpconnection-class.md)

   - [CGopherConnection](../mfc/reference/cgopherconnection-class.md)

   - [CHttpConnection](../mfc/reference/chttpconnection-class.md)

- [CInternetFile](../mfc/reference/cinternetfile-class.md)

   - [CGopherFile](../mfc/reference/cgopherfile-class.md)

   - [CHttpFile](../mfc/reference/chttpfile-class.md)

- [CFileFind](../mfc/reference/cfilefind-class.md)

   - [CFtpFileFind](../mfc/reference/cftpfilefind-class.md)

   - [CGopherFileFind](../mfc/reference/cgopherfilefind-class.md)

- [CGopherLocator](../mfc/reference/cgopherlocator-class.md)

- [CInternetException](../mfc/reference/cinternetexception-class.md)

## <a name="global-functions"></a>전역 함수

- [AfxParseURL](reference/internet-url-parsing-globals.md#afxparseurl)

- [AfxGetInternetHandleType](reference/internet-url-parsing-globals.md#afxgetinternethandletype)

- [AfxThrowInternetException](reference/internet-url-parsing-globals.md#afxthrowinternetexception)

## <a name="see-also"></a>참고자료

[Win32 인터넷 확장(WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[인터넷 클라이언트 클래스의 필수 구성 요소](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[MFC WinInet 클래스를 사용하여 인터넷 클라이언트 애플리케이션 작성](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
