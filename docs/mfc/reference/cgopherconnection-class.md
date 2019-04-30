---
title: CGopherConnection 클래스
ms.date: 11/04/2016
f1_keywords:
- CGopherConnection
- AFXINET/CGopherConnection
- AFXINET/CGopherConnection::CGopherConnection
- AFXINET/CGopherConnection::CreateLocator
- AFXINET/CGopherConnection::GetAttribute
- AFXINET/CGopherConnection::OpenFile
helpviewer_keywords:
- CGopherConnection [MFC], CGopherConnection
- CGopherConnection [MFC], CreateLocator
- CGopherConnection [MFC], GetAttribute
- CGopherConnection [MFC], OpenFile
ms.assetid: b5b96aea-ac99-430e-bd84-d1372b43f78f
ms.openlocfilehash: d960d566a63531af211592a7a8ae8f1cb35c5958
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386275"
---
# <a name="cgopherconnection-class"></a>CGopherConnection 클래스

Gopher 인터넷 서버 연결을 관리합니다.

> [!NOTE]
>  클래스 `CGopherConnection`, `CGopherFile`를 `CGopherFileFind`, `CGopherLocator` 및 해당 멤버는 사용 되지 않습니다 Windows XP 플랫폼에서 작동 하지 않습니다 하지만 계속 이전 플랫폼에서 작동 합니다.

## <a name="syntax"></a>구문

```
class CGopherConnection : public CInternetConnection
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CGopherConnection::CGopherConnection](#cgopherconnection)|`CGopherConnection` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CGopherConnection::CreateLocator](#createlocator)|만듭니다는 [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) gopher 서버에서 파일을 찾을 개체입니다.|
|[CGopherConnection::GetAttribute](#getattribute)|Gopher 개체에 대 한 특성 정보를 검색합니다.|
|[CGopherConnection::OpenFile](#openfile)|Gopher 파일을 엽니다.|

## <a name="remarks"></a>설명

Gopher 서비스 MFC WinInet 클래스에서 인식 하는 세 가지 인터넷 서비스 중 하나입니다.

클래스 `CGopherConnection` 생성자 및 gopher를 관리 하는 세 가지 추가 멤버 함수를 포함 합니다. [OpenFile](#openfile)하십시오 [CreateLocator](#createlocator), 및 [GetAttribute](#getattribute)합니다.

Gopher 인터넷 서버와 통신 하려면 먼저 만들어야 인스턴스에 [CInternetSession](../../mfc/reference/cinternetsession-class.md), 다음 호출 [CInternetSession::GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection)를 작성 하는 `CGopherConnection` 개체 및에 대 한 포인터를 반환 합니다. 되지 만들기는 `CGopherConnection` 직접 개체입니다.

하는 방법에 자세히 알아보려면 `CGopherConnection` 문서를 참조 하는 다른 인터넷 MFC 클래스와 함께 작동 [WinInet을 사용 하 여 인터넷 프로그래밍](../../mfc/win32-internet-extensions-wininet.md)합니다. 다른 두 개를 사용 하는 방법에 대 한 자세한 내용은 지원 인터넷 서비스에 대 한 FTP 및 HTTP 클래스를 참조 [CHttpConnection](../../mfc/reference/chttpconnection-class.md) 하 고 [CFtpConnection](../../mfc/reference/cftpconnection-class.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CInternetConnection](../../mfc/reference/cinternetconnection-class.md)

`CGopherConnection`

## <a name="requirements"></a>요구 사항

**헤더:** afxinet.h

##  <a name="cgopherconnection"></a>  CGopherConnection::CGopherConnection

이 멤버 함수를 생성 하 라고는 `CGopherConnection` 개체입니다.

```
CGopherConnection(
    CInternetSession* pSession,
    HINTERNET hConnected,
    LPCTSTR pstrServer,
    DWORD_PTR dwContext);

CGopherConnection(
    CInternetSession* pSession,
    LPCTSTR pstrServer,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    DWORD_PTR dwContext = 0,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```

### <a name="parameters"></a>매개 변수

*pSession*<br/>
관련에 대 한 포인터 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 개체입니다.

*hConnected*<br/>
현재 인터넷 세션의 Windows 핸들입니다.

*pstrServer*<br/>
FTP 서버 이름을 포함 하는 문자열에 대 한 포인터입니다.

*dwContext*<br/>
작업에 대 한 컨텍스트 식별자입니다. *dwContext* 반환한 작업의 상태 정보를 식별 [cinternetsession:: Onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)합니다. 기본값은 1로 설정 됩니다. 그러나 작업에 대 한 특정 상황에 맞는 ID를 명시적으로 할당할 수 있습니다. 개체 및 수행 작업 컨텍스트 ID와 사용 하 여 연결 됩니다.

*pstrUserName*<br/>
사용자가 로그인의 이름을 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다. NULL 인 경우 기본값은 익명입니다.

*pstrPassword*<br/>
로그인 하는 데 암호를 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다. 둘 다 *pstrPassword* 하 고 *pstrUserName* 이 NULL 이면 기본 익명 암호는 사용자의 전자 메일 이름입니다. 하는 경우 *pstrPassword* NULL (또는 빈 문자열)가 있지만 *pstrUserName* NULL이 아니면 빈 암호가 사용 됩니다. 다음 표에서 동작의 네 가지 가능한 설정에 대 한 설명 *pstrUserName* 하 고 *pstrPassword*:

|*pstrUserName*|*pstrPassword*|FTP 서버에 전송 하는 사용자 이름|FTP 서버에 전송 하는 암호|
|--------------------|--------------------|---------------------------------|---------------------------------|
|NULL 또는 ""|NULL 또는 ""|"anonymous"|사용자의 전자 메일 이름|
|NULL이 아닌 문자열|NULL 또는 ""|*pstrUserName*|" "|
|NULL에서 NULL이 아닌 문자열|오류|오류||
|NULL이 아닌 문자열|NULL이 아닌 문자열|*pstrUserName*|*pstrPassword*|

*nPort*<br/>
서버에서 사용 하 여 TCP/IP 포트를 식별 하는 번호입니다.

### <a name="remarks"></a>설명

되지 만들기는 `CGopherConnection` 직접. 대신 호출 [CInternetSession::GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection)를 작성 하는 `CGopherConnection` 개체 및에 대 한 포인터를 반환 합니다.

##  <a name="createlocator"></a>  CGopherConnection::CreateLocator

이를 찾거나 gopher 서버에서 파일을 식별할 gopher 로케이터를 만드는 함수를 호출 합니다.

```
CGopherLocator CreateLocator(
    LPCTSTR pstrDisplayString,
    LPCTSTR pstrSelectorString,
    DWORD dwGopherType);

static CGopherLocator CreateLocator(LPCTSTR pstrLocator);

static CGopherLocator CreateLocator(
    LPCTSTR pstrServerName,
    LPCTSTR pstrDisplayString,
    LPCTSTR pstrSelectorString,
    DWORD dwGopherType,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```

### <a name="parameters"></a>매개 변수

*pstrDisplayString*<br/>
Gopher 문서 또는 검색할 디렉터리의 이름을 포함 하는 문자열에 대 한 포인터입니다. 경우는 *pstrDisplayString* 매개 변수가 NULL 인 gopher 서버에 대 한 기본 디렉터리 반환 됩니다.

*pstrSelectorString*<br/>
항목을 검색 하기 위해 gopher 서버로 보낼 선택기 문자열에 대 한 포인터입니다. *pstrSelectorString* NULL 일 수 있습니다.

*dwGopherType*<br/>
지정 여부 *pstrSelectorString* 디렉터리 또는 문서를 참조 요청 인지 gopher gopher + 및 합니다. 구조에 대 한 특성을 참조 하세요 [GOPHER_FIND_DATA](/windows/desktop/api/wininet/ns-wininet-gopher_find_dataa) Windows SDK에 있습니다.

*pstrLocator*<br/>
열려는 파일을 식별 하는 문자열에 대 한 포인터입니다. 이 문자열에 대 한 호출에서 반환 되는 일반적으로 [CGopherFileFind::GetLocator](../../mfc/reference/cgopherfilefind-class.md#getlocator)합니다.

*pstrServerName*<br/>
Gopher 서버 이름을 포함 하는 문자열에 대 한 포인터입니다.

*nPort*<br/>
이 연결에 대 한 인터넷 포트를 식별 하는 번호입니다.

### <a name="return-value"></a>반환 값

A [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) 개체입니다.

### <a name="remarks"></a>설명

정적 멤버 함수의 버전에는 static이 아니고 버전에는 연결 개체에서 서버 이름을 사용 하는 동안 서버를 지정 해야 합니다.

Gopher 서버에서 정보를 검색 하기 위해 응용 프로그램 gopher 로케이터를 먼저 가져와야 합니다. 응용 프로그램에 다음 불투명 토큰으로 로케이터를 처리 해야 합니다 (즉, 응용 프로그램 수 로케이터를 사용 하지만 직접적 조작 또는 비교). 일반적으로 응용 프로그램에 대 한 호출에 대 한 로케이터를 사용 합니다 [CGopherFileFind::FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile) 특정 정보를 검색 하려면 멤버 함수입니다.

##  <a name="getattribute"></a>  CGopherConnection::GetAttribute

Gopher 서버에서 항목에 대 한 특정 특성 정보를 검색 하려면이 멤버 함수를 호출 합니다.

```
BOOL GetAttribute(
    CGopherLocator& refLocator    CString strRequestedAttributes,
    CString& strResult,);
```

### <a name="parameters"></a>매개 변수

*refLocator*<br/>
에 대 한 참조를 [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) 개체입니다.

*strRequestedAttributes*<br/>
요청된 된 특성의 이름을 지정 하며 공백으로 구분 된 문자열입니다.

*strResult*<br/>
에 대 한 참조를 [CString](../../atl-mfc-shared/reference/cstringt-class.md) locator 유형을 받는입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다. Win32 함수 호출이 실패 한 경우 [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) 오류의 원인을 확인 하려면 호출 될 수 있습니다.

##  <a name="openfile"></a>  CGopherConnection::OpenFile

Gopher 서버에서 파일을 열려면이 멤버 함수를 호출 합니다.

```
CGopherFile* OpenFile(
    CGopherLocator& refLocator,
    DWORD dwFlags = 0,
    LPCTSTR pstrView = NULL,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>매개 변수

*refLocator*<br/>
에 대 한 참조를 [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) 개체입니다.

*dwFlags*<br/>
INTERNET_FLAG_ 플래그의 모든 조합입니다. 참조 [CInternetSession::OpenUrl](../../mfc/reference/cinternetsession-class.md#openurl) INTERNET_FLAG_ 대 한 자세한 내용은\* 플래그입니다.

*pstrView*<br/>
파일 뷰 문자열 포인터입니다. 서버에서 파일의 여러 뷰 존재 하는 경우이 매개 변수를 열려면 파일 보기를 지정 합니다. 하는 경우 *pstrView* 가 null 인 경우 기본 파일 뷰로 사용 됩니다.

*dwContext*<br/>
열려 있는 파일에 대 한 컨텍스트 ID입니다. 참조 **주의** 에 대 한 자세한 내용은 *dwContext*합니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 [CGopherFile](../../mfc/reference/cgopherfile-class.md) 열 개체입니다.

### <a name="remarks"></a>설명

재정의 된 *dwContext* 기본적으로 선택한 값으로 컨텍스트 식별자를 설정 합니다. 컨텍스트 식별자의이 특정 작업과 연결 되어는 `CGopherConnection` 개체에서 만든 해당 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 개체입니다. 값이 반환 [cinternetsession:: Onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) 식별 되는 작업의 상태를 제공 합니다. 문서를 참조 [인터넷 첫 번째 단계: WinInet](../../mfc/wininet-basics.md) 컨텍스트 식별자에 대 한 자세한 내용은 합니다.

## <a name="see-also"></a>참고자료

[CInternetConnection 클래스](../../mfc/reference/cinternetconnection-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CFtpConnection 클래스](../../mfc/reference/cftpconnection-class.md)<br/>
[CHttpConnection 클래스](../../mfc/reference/chttpconnection-class.md)<br/>
[CInternetConnection 클래스](../../mfc/reference/cinternetconnection-class.md)<br/>
[CGopherLocator 클래스](../../mfc/reference/cgopherlocator-class.md)<br/>
[CGopherFile 클래스](../../mfc/reference/cgopherfile-class.md)<br/>
[CInternetSession 클래스](../../mfc/reference/cinternetsession-class.md)
