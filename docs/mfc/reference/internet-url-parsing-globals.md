---
title: 인터넷 URL 전역 구문 분석 및 도우미
ms.date: 04/03/2017
f1_keywords:
- vc.mfc.macros.isapi
helpviewer_keywords:
- parsing, URLs
- URLs, parsing
ms.assetid: 46c6384f-e4a6-4dbd-9196-219c19040ec5
ms.openlocfilehash: 0831d94f1a6f0293d3605a5e2e9ebde0564baf24
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62322003"
---
# <a name="internet-url-parsing-globals-and-helpers"></a>인터넷 URL 전역 구문 분석 및 도우미

클라이언트의 인터넷 서버에 쿼리를 보내면 클라이언트에 대 한 정보를 추출할 URL 전역 구문 분석 중 하나를 사용할 수 있습니다. 도우미 함수는 다른 인터넷 기능을 제공합니다.

## <a name="internet-url-parsing-globals"></a>인터넷 URL 전역 구문 분석

|||
|-|-|
|[AfxParseURL](#afxparseurl)|URL 문자열을 구문 분석 하 고 서비스 및 해당 구성 요소의 형식을 반환 합니다.|
|[AfxParseURLEx](#afxparseurlex)|URL 문자열을 구문 분석 하 고 사용자 이름 및 암호를 제공 합니다. 뿐만 아니라 서비스 및 해당 구성 요소 형식을 반환 합니다.|

## <a name="other-internet-helpers"></a>다른 인터넷 도우미

|||
|-|-|
|[AfxThrowInternetException](#afxthrowinternetexception)|인터넷 연결에 관련 된 예외가 throw 됩니다.|
|[AfxGetInternetHandleType](#afxgetinternethandletype)|인터넷 핸들의 형식을 결정합니다.|

##  <a name="afxparseurl"></a>  AfxParseURL

이 전역에서 사용 됩니다 [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)합니다.

```
BOOL AFXAPI AfxParseURL(
    LPCTSTR pstrURL,
    DWORD& dwServiceType,
    CString& strServer,
    CString& strObject,
    INTERNET_PORT& nPort);
```

### <a name="parameters"></a>매개 변수

*pstrURL*<br/>
구문 분석 될 URL을 포함 하는 문자열에 대 한 포인터입니다.

*dwServiceType*<br/>
인터넷 서비스의 유형을 나타냅니다. 다음과 같은 값을 사용할 수 있습니다.

- AFX_INET_SERVICE_FTP

- AFX_INET_SERVICE_HTTP

- AFX_INET_SERVICE_HTTPS

- AFX_INET_SERVICE_GOPHER

- AFX_INET_SERVICE_FILE

- AFX_INET_SERVICE_MAILTO

- AFX_INET_SERVICE_NEWS

- AFX_INET_SERVICE_NNTP

- AFX_INET_SERVICE_TELNET

- AFX_INET_SERVICE_WAIS

- AFX_INET_SERVICE_MID

- AFX_INET_SERVICE_CID

- AFX_INET_SERVICE_PROSPERO

- AFX_INET_SERVICE_AFS

- AFX_INET_SERVICE_UNK

*strServer*<br/>
서비스 형식 URL의 첫 번째 세그먼트입니다.

*strObject*<br/>
URL이 가리키는 개체 (비어 있을 수 있습니다).

*nPort*<br/>
있는 경우 URL의 서버 또는 개체 부분에서 결정 합니다.

### <a name="return-value"></a>반환 값

0이 아닌 URL을 구문 분석 했습니다. 이 고, 그렇지 않으면 0 비어 있거나 알려진된 인터넷 서비스 형식이 없습니다.

### <a name="remarks"></a>설명

URL 문자열을 구문 분석 하 고 서비스 및 해당 구성 요소의 형식을 반환 합니다.

예를 들어 `AfxParseURL` 형식의 Url을 구문 분석 *service://server/dir/dir/object.ext:port* 다음과 같이 저장 된 구성 요소를 반환 합니다.

*strServer* == "server"

*strObject* == "/dir/dir/object/object.ext"

*nPort* == #port

*dwServiceType* == #service

> [!NOTE]
>  이 함수를 호출 하려면 프로젝트가 AFXINET 포함 해야 합니다. 8.

### <a name="requirements"></a>요구 사항

  **헤더** afxinet.h

##  <a name="afxparseurlex"></a>  AfxParseURLEx

이 전역 함수는 확장 된 버전의 [AfxParseURL](#afxparseurl) 에 사용 됩니다 [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)합니다.

```
BOOL AFXAPI AfxParseURLEx(
    LPCTSTR pstrURL,
    DWORD& dwServiceType,
    CString& strServer,
    CString& strObject,
    INTERNET_PORT& nPort,
    CString& strUsername,
    CString& strPassword,
    DWORD dwFlags = 0);
```

### <a name="parameters"></a>매개 변수

*pstrURL*<br/>
구문 분석 될 URL을 포함 하는 문자열에 대 한 포인터입니다.

*dwServiceType*<br/>
인터넷 서비스의 유형을 나타냅니다. 다음과 같은 값을 사용할 수 있습니다.

- AFX_INET_SERVICE_FTP

- AFX_INET_SERVICE_HTTP

- AFX_INET_SERVICE_HTTPS

- AFX_INET_SERVICE_GOPHER

- AFX_INET_SERVICE_FILE

- AFX_INET_SERVICE_MAILTO

- AFX_INET_SERVICE_NEWS

- AFX_INET_SERVICE_NNTP

- AFX_INET_SERVICE_TELNET

- AFX_INET_SERVICE_WAIS

- AFX_INET_SERVICE_MID

- AFX_INET_SERVICE_CID

- AFX_INET_SERVICE_PROSPERO

- AFX_INET_SERVICE_AFS

- AFX_INET_SERVICE_UNK

*strServer*<br/>
서비스 형식 URL의 첫 번째 세그먼트입니다.

*strObject*<br/>
URL이 가리키는 개체 (비어 있을 수 있습니다).

*nPort*<br/>
있는 경우 URL의 서버 또는 개체 부분에서 결정 합니다.

*strUsername*<br/>
에 대 한 참조를 `CString` 사용자의 이름을 포함 하는 개체입니다.

*strPassword*<br/>
에 대 한 참조를 `CString` 사용자의 암호를 포함 하는 개체입니다.

*dwFlags*<br/>
URL을 구문 분석 하는 방법을 제어 하는 플래그입니다. 다음 값의 조합일 수 있습니다.

|값|의미|
|-----------|-------------|
|ICU_DECODE|%XX 이스케이프 시퀀스를 문자로 변환 합니다.|
|ICU_NO_ENCODE|안전 하지 않은 문자 이스케이프 시퀀스를 변환 하지 않습니다.|
|ICU_NO_META|Meta 시퀀스 (예: "\."를 제거 하지 마세요 및 "\..") 해야 합니다.|
|ICU_ENCODE_SPACES_ONLY|공백만을 인코딩하십시오.|
|ICU_BROWSER_MODE|인코딩 하지 않거나 '#' 뒤에 문자를 디코딩할 또는 ', 후 후행 공백을 제거 하지 마십시오 '. 이 값을 지정 하지 않으면 전체 URL 인코딩 되 고 후행 공백이 제거 됩니다.|

모든 안전 하지 않은 문자 및 메타 순서 함수 변환 플래그가 없으므로 MFC 기본값을 사용 하는 경우 (같은 \\., \..., 및 \\...) 이스케이프 시퀀스입니다.

### <a name="return-value"></a>반환 값

0이 아닌 URL을 구문 분석 했습니다. 이 고, 그렇지 않으면 0 비어 있거나 알려진된 인터넷 서비스 형식이 없습니다.

### <a name="remarks"></a>설명

URL 문자열을 구문 분석 하 고 사용자의 이름 및 암호를 제공 합니다. 뿐만 아니라 서비스 및 해당 구성 요소 유형을 반환 합니다. 플래그를 나타내는 방법을 안전 하지 않은 문자 처리 됩니다.

> [!NOTE]
>  이 함수를 호출 하려면 프로젝트가 AFXINET 포함 해야 합니다. 8.

### <a name="requirements"></a>요구 사항

  **헤더** afxinet.h

## <a name="afxgetinternethandletype"></a>  AfxGetInternetHandleType

이 전역 함수를 사용 하 여 인터넷 핸들의 형식을 결정 합니다.

### <a name="syntax"></a>구문

  ```
DWORD AFXAPI AfxGetInternetHandleType(  HINTERNET hQuery );
```

### <a name="parameters"></a>매개 변수

*hQuery*<br/>
쿼리를 인터넷에 대 한 핸들입니다.

### <a name="return-value"></a>반환 값

인터넷의 모든 서비스 WININET에서 정의 된 형식입니다. 8. 이러한 인터넷 서비스의 목록은 설명 섹션을 참조 하세요. 핸들을 null 또는 인식 되지 경우 AFX_INET_SERVICE_UNK 반환 합니다.

### <a name="remarks"></a>설명

다음 목록은 가능한 인터넷 형식을 반환한 `AfxGetInternetHandleType`합니다.

- INTERNET_HANDLE_TYPE_INTERNET

- INTERNET_HANDLE_TYPE_CONNECT_FTP

- INTERNET_HANDLE_TYPE_CONNECT_GOPHER

- INTERNET_HANDLE_TYPE_CONNECT_HTTP

- INTERNET_HANDLE_TYPE_FTP_FIND

- INTERNET_HANDLE_TYPE_FTP_FIND_HTML

- INTERNET_HANDLE_TYPE_FTP_FILE

- INTERNET_HANDLE_TYPE_FTP_FILE_HTML

- INTERNET_HANDLE_TYPE_GOPHER_FIND

- INTERNET_HANDLE_TYPE_GOPHER_FIND_HTML

- INTERNET_HANDLE_TYPE_GOPHER_FILE

- INTERNET_HANDLE_TYPE_GOPHER_FILE_HTML

- INTERNET_HANDLE_TYPE_HTTP_REQUEST

> [!NOTE]
>  이 함수를 호출 하려면 프로젝트가 AFXINET 포함 해야 합니다. 8.

### <a name="requirements"></a>요구 사항

**헤더:** afxinet.h

## <a name="afxthrowinternetexception"></a>  AfxThrowInternetException

인터넷 예외가 throw 됩니다.

### <a name="syntax"></a>구문

```
   void AFXAPI AfxThrowInternetException(  DWORD dwContext,  DWORD dwError = 0 );
```

### <a name="parameters"></a>매개 변수

*dwContext*<br/>
오류를 발생 시킨 작업에 대 한 컨텍스트 식별자입니다. 기본값인 *dwContext* 에 원래 지정 된 [CInternetSession](cinternetsession-class.md) 전달 됩니다 [CInternetConnection](cinternetconnection-class.md)-및 [CInternetFile](cinternetfile-class.md)-클래스를 파생 합니다. 연결 또는 파일에서 수행 하는 특정 작업에 대해 일반적으로 기본값을 사용 하 여가 재정의 한 *dwContext* 자신만의 합니다. 그런 다음이 값에 반환 됩니다 [cinternetsession:: Onstatuscallback](cinternetsession-class.md#onstatuscallback) 특정 작업의 상태를 식별 합니다.

*dwError*<br/>
예외를 발생 시킨 오류입니다.

### <a name="remarks"></a>설명

운영 체제 오류 코드를 기반으로 하 여 원인을 확인할 책임이 있습니다.

> [!NOTE]
>  이 함수를 호출 하려면 프로젝트가 AFXINET 포함 해야 합니다. 8.

### <a name="requirements"></a>요구 사항

**헤더:** afxinet.h

## <a name="see-also"></a>참고자료

[매크로 및 전역](mfc-macros-and-globals.md)<br/>
[CInternetException 클래스](cinternetexception-class.md)<br/>
[AfxParseURL](internet-url-parsing-globals.md#afxparseurl)
