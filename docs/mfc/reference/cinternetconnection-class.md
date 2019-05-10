---
title: CInternetConnection 클래스
ms.date: 11/04/2016
f1_keywords:
- CInternetConnection
- AFXINET/CInternetConnection
- AFXINET/CInternetConnection::CInternetConnection
- AFXINET/CInternetConnection::GetContext
- AFXINET/CInternetConnection::GetServerName
- AFXINET/CInternetConnection::GetSession
helpviewer_keywords:
- CInternetConnection [MFC], CInternetConnection
- CInternetConnection [MFC], GetContext
- CInternetConnection [MFC], GetServerName
- CInternetConnection [MFC], GetSession
ms.assetid: 62a5d1c3-8471-4e36-a064-48831829b2a7
ms.openlocfilehash: 9f17c3ade53ec45ddde654e83c77fe1d817d8495
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62345698"
---
# <a name="cinternetconnection-class"></a>CInternetConnection 클래스

인터넷 서버와의 연결을 관리합니다.

## <a name="syntax"></a>구문

```
class CInternetConnection : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CInternetConnection::CInternetConnection](#cinternetconnection)|`CInternetConnection` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CInternetConnection::GetContext](#getcontext)|이 연결 개체에 대 한 컨텍스트 ID를 가져옵니다.|
|[CInternetConnection::GetServerName](#getservername)|연결과 관련 된 서버의 이름을 가져옵니다.|
|[CInternetConnection::GetSession](#getsession)|포인터를 가져 합니다 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 연결과 관련 된 개체입니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CInternetConnection::operator HINTERNET](#operator_hinternet)|인터넷 세션에 대 한 핸들입니다.|

## <a name="remarks"></a>설명

MFC 클래스에 대 한 기본 클래스 [CFtpConnection](../../mfc/reference/cftpconnection-class.md)를 [CHttpConnection](../../mfc/reference/chttpconnection-class.md), 및 [CGopherConnection](../../mfc/reference/cgopherconnection-class.md)합니다. 각이 클래스는 각 FTP, HTTP 또는 gopher 서버와 통신 하기 위한 추가 기능을 제공 합니다.

인터넷 서버와 직접 통신할 수 있어야 합니다는 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 개체 및 `CInternetConnection` 개체입니다.

WinInet 클래스가 작동 하는 방법에 대 한 자세한 문서를 참조 [WinInet을 사용 하 여 인터넷 프로그래밍](../../mfc/win32-internet-extensions-wininet.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CInternetConnection`

## <a name="requirements"></a>요구 사항

**헤더:** afxinet.h

##  <a name="cinternetconnection"></a>  CInternetConnection::CInternetConnection

이 멤버 함수를 호출 하는 경우는 `CInternetConnection` 개체가 만들어집니다.

```
CInternetConnection(
    CInternetSession* pSession,
    LPCTSTR pstrServer,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>매개 변수

*pSession*<br/>
에 대 한 포인터를 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 개체입니다.

*pstrServer*<br/>
서버 이름을 포함 하는 문자열에 대 한 포인터입니다.

*nPort*<br/>
이 연결에 대 한 인터넷 포트를 식별 하는 숫자입니다.

*dwContext*<br/>
에 대 한 컨텍스트 식별자를 `CInternetConnection` 개체입니다. 참조 **주의** 에 대 한 자세한 내용은 *dwContext*합니다.

### <a name="remarks"></a>설명

호출 하지 `CInternetConnection` 직접; 대신 호출 합니다 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 설정 하려는 연결의 유형에 대 한 멤버 함수:

- [CInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)

- [CInternetSession::GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection)

- [CInternetSession::GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection)

에 대 한 기본값 *dwContext* MFC에서 전송한 합니다 `CInternetConnection`-파생 개체를 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 만든 개체를 **InternetConnection**- 파생된 개체입니다. 기본값은 1로 설정 됩니다. 그러나에서 특정 컨텍스트 식별자를 명시적으로 할당할 수는 [CInternetSession](../../mfc/reference/cinternetsession-class.md#cinternetsession) 연결에 대 한 생성자입니다. 개체 및 수행 작업 컨텍스트 ID와 사용 하 여 연결 됩니다. 컨텍스트 식별자에 반환 됩니다 [cinternetsession:: Onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) 식별 되는 개체의 상태를 제공 합니다. 문서를 참조 [인터넷 첫 번째 단계: WinInet](../../mfc/wininet-basics.md) 컨텍스트 식별자에 대 한 자세한 내용은 합니다.

##  <a name="getcontext"></a>  CInternetConnection::GetContext

이 세션에 대 한 컨텍스트 ID를 가져오려면이 함수를 호출 합니다.

```
DWORD_PTR GetContext() const;
```

### <a name="return-value"></a>반환 값

응용 프로그램 할당 컨텍스트 id입니다.

### <a name="remarks"></a>설명

에 컨텍스트 ID가 지정 된 원래 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 전파 `CInternetConnection`-및 [CInternetFile](../../mfc/reference/cinternetfile-class.md)-열리는 함수에 대 한 호출에서 다르게 지정 하지 않으면 파생 클래스 연결입니다. 컨텍스트 ID를 지정된 된 개체의 모든 작업을 사용 하 여 연결 되며 반환한 작업의 상태 정보를 식별 [cinternetsession:: Onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)합니다.

방법에 대 한 자세한 내용은 `GetContext` 문서를 참조 하는 사용자 상태 정보를 제공 하려면 다른 WinInet 클래스를 사용 하 여 작동 [인터넷 첫 번째 단계: WinInet](../../mfc/wininet-basics.md) 컨텍스트 식별자에 대 한 자세한 내용은 합니다.

##  <a name="getservername"></a>  CInternetConnection::GetServerName

이 인터넷에 연결 된 연결 된 서버의 이름을 가져오려면이 함수를 호출 합니다.

```
CString GetServerName() const;
```

### <a name="return-value"></a>반환 값

이 연결 개체를 사용 중인 서버의 이름입니다.

##  <a name="getsession"></a>  CInternetConnection::GetSession

에 대 한 포인터를 가져오려면이 함수를 호출 합니다 `CInternetSession` 이 연결에 연관 된 개체입니다.

```
CInternetSession* GetSession() const;
```

### <a name="return-value"></a>반환 값

에 대 한 포인터를 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 이 인터넷 연결 개체와 연결 된 개체입니다.

##  <a name="operator_hinternet"></a>  CInternetConnection::operator HINTERNET

이 연산자를 사용 하 여 현재 인터넷 세션에 대 한 API 수준 핸들을 가져올 수 있습니다.

```
operator HINTERNET() const;
```

## <a name="see-also"></a>참고자료

[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
