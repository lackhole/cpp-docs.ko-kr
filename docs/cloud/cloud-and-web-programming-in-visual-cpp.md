---
title: Visual C++의 클라우드 및 웹 프로그래밍
ms.date: 11/04/2016
ms.assetid: b63611f1-9723-44d0-ba7f-c3ebef341313
ms.openlocfilehash: 3d71e36b6209c693940f2ebe6b5e9c73bc0c9d9d
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65708036"
---
# <a name="cloud-and-web-programming-in-visual-c"></a>Visual C++의 클라우드 및 웹 프로그래밍

C++에는 웹 및 클라우드에 연결하기 위한 다양한 옵션이 있습니다.

## <a name="cloud-programming-options"></a>클라우드 프로그래밍 옵션

- [Microsoft Azure 모바일 서비스](http://www.windowsazure.com/develop/mobile/)

  Microsoft Azure 모바일 서비스에 연결할 UWP(Universal Windows Platform) 또는 Windows 데스크톱 앱에서 사용할 수 있는 API를 제공합니다. 웹 사이트의 대부분 예제는 C#으로 작성되지만 C++를 사용할 수도 있습니다. 자세한 내용은 [빠른 시작: C++를 사용하여 모바일 서비스 추가](https://msdn.microsoft.com/library/windows/apps/dn263181.aspx)를 참조하세요.

- [C++용 Microsoft Azure Storage Client Library](https://blogs.msdn.microsoft.com/windowsazurestorage/2015/04/29/microsoft-azure-storage-client-library-for-c-v1-0-0-general-availability/)

  C++용 Azure Storage Client Library는 Azure 스토리지 작업에 대해 다음 기능을 포함하되 이에 국한되지 않는 포괄적인 API를 제공합니다.

  - Blob 컨테이너, 테이블 및 큐를 만들고, 읽고, 삭제하고, 나열합니다.
  - Blob을 생성, 읽기, 삭제, 나열 및 복사하고 Blob 범위를 읽고 씁니다.
  - Azure 테이블에 엔터티를 삽입, 삭제, 교체, 병합 및 쿼리합니다.
  - Azure 큐에서 메시지를 큐에 넣고 큐에서 제거합니다.
  - 지연 목록 컨테이너, Blob, 테이블, 큐 및 지연 쿼리 엔터티

- [OneDrive API](https://dev.onedrive.com/README.htm)

  OneDrive API는 애플리케이션을 Office 365 및 SharePoint Server 2016의 파일 및 폴더에 연결하는 HTTP 서비스 세트를 제공합니다.

- [C++ REST SDK(코드명 "Casablanca")](https://github.com/Microsoft/cpprestsdk)

  REST 서비스와 상호 작용하기 위한 최신 플랫폼 간 비동기 API를 제공합니다.

  - JSON 문서 구문 분석 및 serialization에 대한 지원이 기본 제공되는 HTTP 서버에 대해 REST 호출 수행
  - 로컬 리디렉션 수신기를 포함하여 OAuth 1 및 2 지원
  - 원격 서비스에 대한 Websocket 연결
  - 기본 제공 threadpool을 비롯한 PPL 기반의 완전 비동기 작업 API

  Windows Desktop(7+), Windows Server(2012+), 유니버설 Windows 플랫폼, Linux, OSX, Android 및 iOS를 지원합니다.

- [Windows::Web::Http::HttpClient](/uwp/api/windows.web.http.httpclient)

  System.Web 네임스페이스에 있는 같은 이름의 .NET Framework 클래스에서 모델링된 Windows 런타임 HTTP 클라이언트 클래스입니다. `HttpClient` 는 HTTP를 통한 비동기 업로드 및 다운로드와 사용자 지정 HTTP 처리기를 파이프라인에 삽입할 수 있게 하는 파이프라인 필터를 완벽하게 지원합니다. Windows SDK에는 데이터 통신 연결 네트워크, OAuth 인증 등에 대한 샘플 필터가 포함됩니다. 유니버설 Windows 플랫폼만 대상으로 하는 앱의 경우 `Windows::Web:HttpClient` 클래스를 사용하는 것이 좋습니다.

- [IXMLHTTPRequest2 인터페이스](/windows/desktop/api/msxml6/nn-msxml6-ixmlhttprequest2)

  HTTP를 통해 인터넷에 연결할 Windows Runtime 앱이나 Windows 데스크톱 앱에서 사용하고 GET, PUT 및 기타 HTTP 명령을 실행할 수 있는 네이티브 COM 인터페이스를 제공합니다. 자세한 내용은 [연습: 작업 및 XML HTTP 요청을 사용하여 연결](../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)을 참조하세요.

- [Windows 인터넷(WinInet)](/windows/desktop/WinInet/portal)

  인터넷에 연결할 Windows 데스크톱 앱에서 사용할 수 있는 Windows API입니다.

## <a name="see-also"></a>참고 항목

[Visual Studio의 C++](../overview/visual-cpp-in-visual-studio.md) <br/>
[네트워크 및 웹 서비스](/windows/uwp/networking/)
