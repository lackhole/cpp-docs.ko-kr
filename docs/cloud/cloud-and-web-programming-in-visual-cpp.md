---
title: Visual C++의 클라우드 및 웹 프로그래밍
ms.date: 11/04/2016
ms.assetid: b63611f1-9723-44d0-ba7f-c3ebef341313
ms.openlocfilehash: 33431a8f8660af683ed2e39e10811c22fe2f4fcc
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58773088"
---
# <a name="cloud-and-web-programming-in-visual-c"></a>Visual C++의 클라우드 및 웹 프로그래밍

C++에는 웹 및 클라우드에 연결하기 위한 다양한 옵션이 있습니다.

## <a name="cloud-programming-options"></a>클라우드 프로그래밍 옵션

- [Microsoft Azure 모바일 서비스](http://www.windowsazure.com/develop/mobile/)

  Windows Azure Mobile Services에 연결 하려면 유니버설 Windows 플랫폼 (UWP) 앱 이나 Windows 데스크톱 앱에서 사용할 수 있는 네이티브 Api를 제공 합니다. 웹 사이트의 대부분 예제는 C#으로 작성되지만 C++를 사용할 수도 있습니다. 자세한 내용은 [빠른 시작: C + +를 사용 하 여 모바일 서비스 추가](https://msdn.microsoft.com/library/windows/apps/dn263181.aspx)합니다.

- [C + + 용 Microsoft Azure Storage 클라이언트 라이브러리](https://blogs.msdn.microsoft.com/windowsazurestorage/2015/04/29/microsoft-azure-storage-client-library-for-c-v1-0-0-general-availability/)

  에서는 다음 기능에 제한 되지 않고 포함 하 여 Azure storage를 사용 하 여 작업에 대 한 포괄적인 API를 제공 하는 c + + 용 Azure Storage 클라이언트 라이브러리:

  - 만들기, 읽기, 삭제 및 blob 컨테이너, 테이블 및 큐를 나열 합니다.
  - 만들기, 읽기, 삭제, 목록 및 복사 blob 및 blob 범위를 읽고 있습니다.
  - 삽입, 삭제, 바꾸기, 병합 및 Azure 테이블에 엔터티를 쿼리 합니다.
  - 큐에 넣기 및 Azure 큐에 메시지를 큐에서 제거 합니다.
  - 지연 컨테이너, blob, 테이블 및 큐를 나열 하 고 엔터티를 쿼리 지연

- [OneDrive API](https://dev.onedrive.com/README.htm)

  OneDrive API HTTP 서비스를 Office 365 및 SharePoint Server 2016에서 파일 및 폴더에 응용 프로그램 연결 집합을 제공 합니다.

- [C++ REST SDK(코드명 "Casablanca")](https://github.com/Microsoft/cpprestsdk)

  REST 서비스와 상호 작용 하기 위한 최신 플랫폼 간, 비동기 API를 제공 합니다.

  - JSON 문서 구문 분석 및 serialization에 대 한 지원이 기본 제공 되는 HTTP 서버에 대 한 REST 호출 수행
  - OAuth 1과 2를 로컬로 리디렉션되면 수신기를 비롯 한 지원
  - 원격 서비스에 대 한 Websocket 연결
  - 기본 제공 threadpool을 비롯 한 PPL 기반의 API 완전히 비동기 작업

  Windows Desktop (7 +), Windows Server (2012 이상), 유니버설 Windows 플랫폼, Linux, OSX, Android 및 iOS를 지원합니다.

- [Windows::Web::Http::HttpClient](/uwp/api/windows.web.http.httpclient)

  System.Web 네임스페이스에 있는 같은 이름의 .NET Framework 클래스에서 모델링된 Windows 런타임 HTTP 클라이언트 클래스입니다. `HttpClient` 는 HTTP를 통한 비동기 업로드 및 다운로드와 사용자 지정 HTTP 처리기를 파이프라인에 삽입할 수 있게 하는 파이프라인 필터를 완벽하게 지원합니다. Windows SDK에는 데이터 통신 연결 네트워크, OAuth 인증 등에 대한 샘플 필터가 포함됩니다. 유니버설 Windows 플랫폼만 대상으로 하는 앱을 사용 하는 권장 된 `Windows::Web:HttpClient` 클래스입니다.

- [IXMLHTTPRequest2 인터페이스](/windows/desktop/api/msxml6/nn-msxml6-ixmlhttprequest2)

  HTTP를 통해 인터넷에 연결할 Windows 런타임 앱 이나 Windows 데스크톱 앱에서 사용할 수 있으며 문제 GET, PUT 및 기타 HTTP 명령을 네이티브 COM 인터페이스를 제공 합니다. 자세한 내용은 [연습: 작업 및 XML HTTP 요청을 사용 하 여 연결](../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)합니다.

- [Windows 인터넷(WinInet)](/windows/desktop/WinInet/portal)

  인터넷에 연결할 Windows 데스크톱 앱에서 사용할 수 있는 Windows API입니다.

## <a name="see-also"></a>참고자료

[Visual C++](../overview/visual-cpp-in-visual-studio.md) <br/>
[네트워크 및 웹 서비스](/windows/uwp/networking/)
