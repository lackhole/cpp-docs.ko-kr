---
title: CAsyncSocket 클래스
ms.date: 11/04/2016
f1_keywords:
- CAsyncSocket
- AFXSOCK/CAsyncSocket
- AFXSOCK/CAsyncSocket::CAsyncSocket
- AFXSOCK/CAsyncSocket::Accept
- AFXSOCK/CAsyncSocket::AsyncSelect
- AFXSOCK/CAsyncSocket::Attach
- AFXSOCK/CAsyncSocket::Bind
- AFXSOCK/CAsyncSocket::Close
- AFXSOCK/CAsyncSocket::Connect
- AFXSOCK/CAsyncSocket::Create
- AFXSOCK/CAsyncSocket::Detach
- AFXSOCK/CAsyncSocket::FromHandle
- AFXSOCK/CAsyncSocket::GetLastError
- AFXSOCK/CAsyncSocket::GetPeerName
- AFXSOCK/CAsyncSocket::GetPeerNameEx
- AFXSOCK/CAsyncSocket::GetSockName
- AFXSOCK/CAsyncSocket::GetSockNameEx
- AFXSOCK/CAsyncSocket::GetSockOpt
- AFXSOCK/CAsyncSocket::IOCtl
- AFXSOCK/CAsyncSocket::Listen
- AFXSOCK/CAsyncSocket::Receive
- AFXSOCK/CAsyncSocket::ReceiveFrom
- AFXSOCK/CAsyncSocket::ReceiveFromEx
- AFXSOCK/CAsyncSocket::Send
- AFXSOCK/CAsyncSocket::SendTo
- AFXSOCK/CAsyncSocket::SendToEx
- AFXSOCK/CAsyncSocket::SetSockOpt
- AFXSOCK/CAsyncSocket::ShutDown
- AFXSOCK/CASyncSocket::Socket
- AFXSOCK/CAsyncSocket::OnAccept
- AFXSOCK/CAsyncSocket::OnClose
- AFXSOCK/CAsyncSocket::OnConnect
- AFXSOCK/CAsyncSocket::OnOutOfBandData
- AFXSOCK/CAsyncSocket::OnReceive
- AFXSOCK/CAsyncSocket::OnSend
- AFXSOCK/CAsyncSocket::m_hSocket
helpviewer_keywords:
- CAsyncSocket [MFC], CAsyncSocket
- CAsyncSocket [MFC], Accept
- CAsyncSocket [MFC], AsyncSelect
- CAsyncSocket [MFC], Attach
- CAsyncSocket [MFC], Bind
- CAsyncSocket [MFC], Close
- CAsyncSocket [MFC], Connect
- CAsyncSocket [MFC], Create
- CAsyncSocket [MFC], Detach
- CAsyncSocket [MFC], FromHandle
- CAsyncSocket [MFC], GetLastError
- CAsyncSocket [MFC], GetPeerName
- CAsyncSocket [MFC], GetPeerNameEx
- CAsyncSocket [MFC], GetSockName
- CAsyncSocket [MFC], GetSockNameEx
- CAsyncSocket [MFC], GetSockOpt
- CAsyncSocket [MFC], IOCtl
- CAsyncSocket [MFC], Listen
- CAsyncSocket [MFC], Receive
- CAsyncSocket [MFC], ReceiveFrom
- CAsyncSocket [MFC], ReceiveFromEx
- CAsyncSocket [MFC], Send
- CAsyncSocket [MFC], SendTo
- CAsyncSocket [MFC], SendToEx
- CAsyncSocket [MFC], SetSockOpt
- CAsyncSocket [MFC], ShutDown
- CASyncSocket [MFC], Socket
- CAsyncSocket [MFC], OnAccept
- CAsyncSocket [MFC], OnClose
- CAsyncSocket [MFC], OnConnect
- CAsyncSocket [MFC], OnOutOfBandData
- CAsyncSocket [MFC], OnReceive
- CAsyncSocket [MFC], OnSend
- CAsyncSocket [MFC], m_hSocket
ms.assetid: cca4d5a1-aa0f-48bd-843e-ef0e2d7fc00b
ms.openlocfilehash: ef486e653eaf78914ea25663e0c1ab744ab30cd4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62164912"
---
# <a name="casyncsocket-class"></a>CAsyncSocket 클래스

Windows 소켓을 나타냅니다-네트워크 통신의 끝점입니다.

## <a name="syntax"></a>구문

```
class CAsyncSocket : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CAsyncSocket::CAsyncSocket](#casyncsocket)|`CAsyncSocket` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CAsyncSocket::Accept](#accept)|소켓에 대 한 연결을 허용합니다.|
|[CAsyncSocket::AsyncSelect](#asyncselect)|이벤트 알림 소켓에 대 한 요청입니다.|
|[CAsyncSocket::Attach](#attach)|연결에 대 한 소켓 핸들을 `CAsyncSocket` 개체입니다.|
|[CAsyncSocket::Bind](#bind)|소켓을 사용 하 여 로컬 주소를 연결합니다.|
|[CAsyncSocket::Close](#close)|소켓을 닫습니다.|
|[CAsyncSocket::Connect](#connect)|피어 소켓에 대 한 연결을 설정합니다.|
|[CAsyncSocket::Create](#create)|소켓을 만듭니다.|
|[CAsyncSocket::Detach](#detach)|소켓 핸들을 분리는 `CAsyncSocket` 개체입니다.|
|[CAsyncSocket::FromHandle](#fromhandle)|에 대 한 포인터를 반환 합니다.는 `CAsyncSocket` 소켓 핸들을 지정 된 개체입니다.|
|[CAsyncSocket::GetLastError](#getlasterror)|실패 한 마지막 작업에 대 한 오류 상태를 가져옵니다.|
|[CAsyncSocket::GetPeerName](#getpeername)|소켓 연결 되어 있는 피어 소켓의 주소를 가져옵니다.|
|[CAsyncSocket::GetPeerNameEx](#getpeernameex)|소켓 연결된 (핸들 IPv6 주소) 되는 피어 소켓의 주소를 가져옵니다.|
|[CAsyncSocket::GetSockName](#getsockname)|소켓에 대 한 로컬 이름을 가져옵니다.|
|[CAsyncSocket::GetSockNameEx](#getsocknameex)|소켓 (핸들 IPv6 주소)에 대 한 로컬 이름을 가져옵니다.|
|[CAsyncSocket::GetSockOpt](#getsockopt)|소켓 옵션을 검색합니다.|
|[CAsyncSocket::IOCtl](#ioctl)|소켓의 모드를 제어 합니다.|
|[CAsyncSocket::Listen](#listen)|들어오는 연결 요청을 수신 대기 소켓을 설정 합니다.|
|[CAsyncSocket::Receive](#receive)|소켓에서 데이터를 수신합니다.|
|[CAsyncSocket::ReceiveFrom](#receivefrom)|데이터 그램을 받고 소스 주소를 저장 합니다.|
|[CAsyncSocket::ReceiveFromEx](#receivefromex)|데이터 그램을 받고 소스 주소 (핸들 IPv6 주소)를 저장 합니다.|
|[CAsyncSocket::Send](#send)|데이터를 연결된 소켓으로 전송합니다.|
|[CAsyncSocket::SendTo](#sendto)|특정 대상에 데이터를 보냅니다.|
|[CAsyncSocket::SendToEx](#sendtoex)|데이터를 특정 대상 (핸들 IPv6 주소)를 보냅니다.|
|[CAsyncSocket::SetSockOpt](#setsockopt)|소켓 옵션을 설정합니다.|
|[CAsyncSocket::ShutDown](#shutdown)|사용 하지 않도록 설정 `Send` 및/또는 `Receive` 소켓에서 호출 합니다.|
|[CASyncSocket::Socket](#socket)|소켓 핸들을 할당합니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[CAsyncSocket::OnAccept](#onaccept)|호출 하 여 보류 중인 연결 요청 받을 수 있는 수신 대기 소켓 알립니다 `Accept`합니다.|
|[CAsyncSocket::OnClose](#onclose)|소켓에서 소켓 연결을 닫에 알립니다.|
|[CAsyncSocket::OnConnect](#onconnect)|연결 시도가 완전 한지 여부를 정상적으로 수행 되거나 오류가 연결 소켓을 알립니다.|
|[CAsyncSocket::OnOutOfBandData](#onoutofbanddata)|소켓, 일반적으로 긴급 한 메시지를 읽을 대역의 데이터가 수신 소켓에 알립니다.|
|[CAsyncSocket::OnReceive](#onreceive)|호출 하 여 검색할 데이터가 수신 대기 소켓 알립니다 `Receive`합니다.|
|[CAsyncSocket::OnSend](#onsend)|호출 하 여 데이터를 보낼 수는 소켓에 알립니다. `Send`합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CAsyncSocket::operator =](#operator_eq)|새 값을 할당 한 `CAsyncSocket` 개체입니다.|
|[CAsyncSocket::operator SOCKET](#operator_socket)|이 연산자의 소켓 핸들을 검색 하는 데는 `CAsyncSocket` 개체입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CAsyncSocket::m_hSocket](#m_hsocket)|이 연결 된 소켓 핸들을 나타내는 `CAsyncSocket` 개체입니다.|

## <a name="remarks"></a>설명

클래스 `CAsyncSocket` MFC와 함께에서 Windows 소켓을 사용 하려는 프로그래머를 위한 개체 지향적 추상화를 제공 하는 Windows 소켓 함수 API를 캡슐화 합니다.

이 클래스는 가정을 기반으로 네트워크 통신을 이해 합니다. 차단 바이트 순서 차이 처리 하는 일을 담당 하는 하 고 유니코드 및 멀티 바이트 문자 간 변환 (MBCS) 문자열을 설정 합니다. 이러한 문제를 관리 하는 편리한 인터페이스를 클래스를 참조 하세요 [CSocket](../../mfc/reference/csocket-class.md)합니다.

사용 하는 `CAsyncSocket` 개체를 해당 생성자를 호출 호출 합니다 [만들기](#create) 의 기본 소켓 핸들을 만드는 함수 (형식 `SOCKET`), 수락된 소켓을 제외 하 고 합니다. 서버 소켓 호출에 대 한는 [수신](#listen) 멤버 함수 및 클라이언트 소켓 호출에 대 한 합니다 [연결](#connect) 멤버 함수입니다. 서버 소켓 호출 해야 합니다 [Accept](#accept) 연결 요청을 받으면 함수입니다. 나머지를 사용 하 여 `CAsyncSocket` 소켓 간의 통신을 수행 하는 함수입니다. 완료 되 면 삭제 합니다 `CAsyncSocket` 힙에 생성 된 경우 개체; 소멸자를 자동으로 호출 합니다 [닫기](#close) 함수. 소켓 데이터 형식은 문서에 설명 되어 [Windows 소켓: 백그라운드](../../mfc/windows-sockets-background.md)합니다.

> [!NOTE]
>  정적으로 연결 된 MFC 응용 프로그램에서 보조 스레드에서 MFC 소켓을 사용 하는 경우 호출 해야 `AfxSocketInit` 소켓을 사용 하 여 소켓 라이브러리를 초기화 하는 각 스레드에서 합니다. 기본적으로 `AfxSocketInit` 기본 스레드에서만에서 호출 됩니다.

자세한 내용은 참조 하세요. [Windows 소켓: Casyncsocket 클래스 사용](../../mfc/windows-sockets-using-class-casyncsocket.md) 관련 문서. 뿐만 [Windows 소켓 2 API](/windows/desktop/WinSock/windows-sockets-start-page-2)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CAsyncSocket`

## <a name="requirements"></a>요구 사항

**헤더:** afxsock.h

##  <a name="accept"></a>  CAsyncSocket::Accept

소켓에 대 한 연결을 허용 하려면이 멤버 함수를 호출 합니다.

```
virtual BOOL Accept(
    CAsyncSocket& rConnectedSocket,
    SOCKADDR* lpSockAddr = NULL,
    int* lpSockAddrLen = NULL);
```

### <a name="parameters"></a>매개 변수

*rConnectedSocket*<br/>
연결에 사용할 수 있는 새 소켓을 식별 하는 참조 합니다.

*lpSockAddr*<br/>
에 대 한 포인터를 [SOCKADDR](/windows/desktop/winsock/sockaddr-2) 네트워크에서 알려진 구조는 연결의 주소를 수신 하는 소켓입니다. 정확한 형식을 합니다 *lpSockAddr* 인수 소켓 만들어질 때 설정 하는 주소 패밀리에 의해 결정 됩니다. 하는 경우 *lpSockAddr* 및/또는 *lpSockAddrLen* 같은지 NULL로 반환 되 고 받아들인된 소켓의 원격 주소에 대 한 정보가 없습니다.

*lpSockAddrLen*<br/>
주소의 길이에 대 한 포인터 *lpSockAddr* (바이트)에서입니다. *lpSockAddrLen* 는 결과 값 매개 변수: 가리키는 공간의 처음 있어야 *lpSockAddr*; 반환 실제 길이 (바이트) 반환 주소를 포함 합니다.

### <a name="return-value"></a>반환 값

함수에 성공 하면 0이 아닌 값 0이 고 특정 오류 코드를 호출 하 여 검색할 수 있습니다이 고, 그렇지 [GetLastError](#getlasterror)합니다. 이 멤버 함수에 다음 오류가 적용 됩니다.

- WSANOTINITIALISED는 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하 여 앞에 있어야 합니다.

- WSAENETDOWN The Windows 소켓 구현이 네트워크 하위 시스템 실패 했음을 발견 했습니다.

- WSAEFAULT 합니다 *lpSockAddrLen* 인수가 너무 작아서 (의 크기 보다 작은 [SOCKADDR](/windows/desktop/winsock/sockaddr-2) 구조).

- Windows 소켓을 차단 호출 WSAEINPROGRESS는 진행 중입니다.

- WSAEINVAL `Listen` 적용할 호출된 전에 없습니다.

- WSAEMFILE 큐가 비어 허용에 진입할 때 및 사용할 수 없는 설명자입니다.

- 같은 WSAENOBUFS 아니요 버퍼 공간이 사용할 수 있습니다.

- 설명자 WSAENOTSOCK 소켓 아닙니다.

- 참조 된 소켓 WSAEOPNOTSUPP 연결 지향 서비스를 지 원하는 유형이 아닙니다.

- WSAEWOULDBLOCK 소켓 표시 되어 비차단으로 받아들여질 수 있는 상태인 연결이 없습니다.

### <a name="remarks"></a>설명

이 루틴의 보류 중인 연결 큐에 첫 번째 연결을 추출, 동일한 속성에는이 소켓을 사용 하 여 새 소켓을 만듭니다 및에 연결 *rConnectedSocket*합니다. 큐에 보류 중인 연결이 있는 경우 `Accept` 0을 반환 하 고 `GetLastError` 오류를 반환 합니다. 받아들여진된 소켓이 ( *rConnectedSocket)* 자세한 연결을 허용 하도록 사용할 수 없습니다. 원래 소켓이 열려 있어 수신 대기 합니다.

인수 *lpSockAddr* 통신 계층에 알려진 연결 소켓의 주소를 사용 하 여 입력은 결과 매개 변수입니다. `Accept` 같은 SOCK_STREAM 소켓 연결 기반 형식에 사용 됩니다.

##  <a name="asyncselect"></a>  CAsyncSocket::AsyncSelect

소켓에 대 한 이벤트 알림 요청 하려면이 멤버 함수를 호출 합니다.

```
BOOL AsyncSelect(long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```

### <a name="parameters"></a>매개 변수

*lEvent*<br/>
응용 프로그램에는 관여 하는 네트워크 이벤트의 조합을 지정 하는 비트 마스크입니다.

- 작업할 준비 읽기에 대 한 알림을 받도록 하려고 합니다.

- FD_WRITE 데이터를 읽을 때 알림을 받으려면 하려고 합니다.

- FD_OOB 대역의 데이터에 대 한 알림을 수신 하려고 합니다.

- FD_ACCEPT 들어오는 연결에 대 한 알림을 수신 하려고 합니다.

- FD_CONNECT 연결 결과 대 한 알림을 수신 하려고 합니다.

- FD_CLOSE 소켓 피어에 의해 닫힌 경우 알림 수신 하려고 합니다.

### <a name="return-value"></a>반환 값

함수에 성공 하면 0이 아닌 값 0이 고 특정 오류 코드를 호출 하 여 검색할 수 있습니다이 고, 그렇지 [GetLastError](#getlasterror)합니다. 이 멤버 함수에 다음 오류가 적용 됩니다.

- WSANOTINITIALISED는 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하 여 앞에 있어야 합니다.

- WSAENETDOWN The Windows 소켓 구현이 네트워크 하위 시스템 실패 했음을 발견 했습니다.

- WSAEINVAL 나타내는 지정된 된 매개 변수 중 하나는 잘못 되었습니다.

- WSAEINPROGRESS는 차단 하는 Windows 소켓 작업이 진행 중입니다.

### <a name="remarks"></a>설명

이 함수는 소켓에 대해 MFC 콜백 알림 함수를 호출할 수는 지정에 사용 됩니다. `AsyncSelect` 이 소켓 비블로킹 모드로 자동 설정 됩니다. 자세한 내용은 문서를 참조 하세요. [Windows 소켓: 알림 소켓](../../mfc/windows-sockets-socket-notifications.md)합니다.

##  <a name="attach"></a>  CAsyncSocket::Attach

연결 하려면이 멤버 함수를 호출 합니다 *hSocket* 에 대 한 핸들을 `CAsyncSocket` 개체입니다.

```
BOOL Attach(
    SOCKET hSocket, long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```

### <a name="parameters"></a>매개 변수

*hSocket*<br/>
소켓에 대 한 핸들을 포함합니다.

*lEvent*<br/>
응용 프로그램에는 관여 하는 네트워크 이벤트의 조합을 지정 하는 비트 마스크입니다.

- 작업할 준비 읽기에 대 한 알림을 받도록 하려고 합니다.

- FD_WRITE 데이터를 읽을 때 알림을 받으려면 하려고 합니다.

- FD_OOB 대역의 데이터에 대 한 알림을 수신 하려고 합니다.

- FD_ACCEPT 들어오는 연결에 대 한 알림을 수신 하려고 합니다.

- FD_CONNECT 연결 결과 대 한 알림을 수신 하려고 합니다.

- FD_CLOSE 소켓 피어에 의해 닫힌 경우 알림 수신 하려고 합니다.

### <a name="return-value"></a>반환 값

함수가 성공하는 경우 0이 아닙니다.

### <a name="remarks"></a>설명

SOCKET 핸들 개체에 저장 됩니다 [m_hSocket](#m_hsocket) 데이터 멤버입니다.

##  <a name="bind"></a>  CAsyncSocket::Bind

소켓을 사용 하 여 로컬 주소를 연결 하려면이 멤버 함수를 호출 합니다.

```
BOOL Bind(
    UINT nSocketPort,
    LPCTSTR lpszSocketAddress = NULL);

BOOL Bind (
    const SOCKADDR* lpSockAddr,
    int nSockAddrLen);
```

### <a name="parameters"></a>매개 변수

*nSocketPort*<br/>
소켓 응용 프로그램을 식별 하는 포트입니다.

*lpszSocketAddress*<br/>
네트워크 주소 "128.56.22.8" 같은 점으로 구분 된 번호입니다. 이 매개 변수를 나타내는 문자열을 NULL이 전달 된 `CAsyncSocket` 인스턴스는 모든 네트워크 인터페이스에서 클라이언트 활동에 대 한 수신 대기 해야 합니다.

*lpSockAddr*<br/>
에 대 한 포인터를 [SOCKADDR](/windows/desktop/winsock/sockaddr-2) 이 소켓에 할당할 주소를 포함 하는 구조입니다.

*nSockAddrLen*<br/>
주소의 길이 *lpSockAddr* (바이트)에서입니다.

### <a name="return-value"></a>반환 값

함수에 성공 하면 0이 아닌 값 0이 고 특정 오류 코드를 호출 하 여 검색할 수 있습니다이 고, 그렇지 [GetLastError](#getlasterror)합니다. 이 멤버 함수에 다음 오류가 적용 됩니다.

- WSANOTINITIALISED는 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하 여 앞에 있어야 합니다.

- WSAENETDOWN The Windows 소켓 구현이 네트워크 하위 시스템 실패 했음을 발견 했습니다.

- WSAEADDRINUSE 지정 된 주소를 이미 사용 중인 경우 (아래 SO_REUSEADDR 소켓 옵션을 참조 하세요 [SetSockOpt](#setsockopt).)

- WSAEFAULT 합니다 *nSockAddrLen* 인수가 너무 작아서 (의 크기 보다 작은 [SOCKADDR](/windows/desktop/winsock/sockaddr-2) 구조).

- Windows 소켓을 차단 호출 WSAEINPROGRESS는 진행 중입니다.

- 지정된 된 주소 패밀리 WSAEAFNOSUPPORT이이 포트에서 지원 되지 않습니다.

- WSAEINVAL 소켓 주소에 이미 바인딩되어 있습니다.

- 같은 WSAENOBUFS 없습니다 충분히 사용 가능한 버퍼링 연결이 너무 많습니다.

- 설명자 WSAENOTSOCK 소켓 아닙니다.

### <a name="remarks"></a>설명

이 루틴 되는 연결 되지 않은 데이터 그램 또는 스트림 소켓에서 전에 후속 `Connect` 또는 `Listen` 호출 합니다. 서버 소켓의 수신 대기 포트 번호를 선택 하며 있도록 알려진 Windows 소켓을 호출 하 여 연결 요청을 허용 하려면, `Bind`합니다. `Bind` 명명 되지 않은 소켓에 로컬 이름을 지정 하 여 소켓의 로컬 연결 (호스트 주소/포트 번호)을 설정 합니다.

##  <a name="casyncsocket"></a>  CAsyncSocket::CAsyncSocket

빈 소켓 개체를 생성합니다.

```
CAsyncSocket();
```

### <a name="remarks"></a>설명

호출 해야 개체를 생성 한 후 해당 `Create` 소켓 데이터 구조를 만들고 해당 주소를 바인딩하는 멤버 함수입니다. (Windows 소켓 통신을 수신 대기 소켓에서 사용 하는 소켓을 만들 때의 서버 쪽에는 `Accept` 호출을 호출 하지 않으면 `Create` 해당 소켓에 대 한 합니다.)

##  <a name="close"></a>  CAsyncSocket::Close

소켓을 닫습니다.

```
virtual void Close();
```

### <a name="remarks"></a>설명

이 함수는 참조가 WSAENOTSOCK 오류로 인해 실패 하는 추가 되도록 소켓 설명자를 해제 합니다. 내부 소켓에 대 한 마지막 참조 인 경우 연결 된 명명 정보 및 대기 중인된 데이터가 삭제 됩니다. 소켓 개체의 소멸자 호출 `Close` 있습니다.

에 대 한 `CAsyncSocket`, 아닌 `CSocket`의 의미 체계 `Close` SO_LINGER 및 SO_DONTLINGER 소켓 옵션 영향을 받지 합니다. 자세한 내용은 멤버 함수를 참조 하세요. `GetSockOpt`합니다.

##  <a name="connect"></a>  CAsyncSocket::Connect

연결 되지 않은 스트림 또는 데이터 그램 소켓에 연결 하려면이 멤버 함수를 호출 합니다.

```
BOOL Connect(
    LPCTSTR lpszHostAddress,
    UINT nHostPort);

BOOL Connect(
    const SOCKADDR* lpSockAddr,
    int nSockAddrLen);
```

### <a name="parameters"></a>매개 변수

*lpszHostAddress*<br/>
이 개체가 연결 되는 소켓의 네트워크 주소: "형식인" 또는 "128.56.22.8" 같은 점으로 구분 된 번호와 같은 컴퓨터 이름입니다.

*nHostPort*<br/>
소켓 응용 프로그램을 식별 하는 포트입니다.

*lpSockAddr*<br/>
에 대 한 포인터를 [SOCKADDR](/windows/desktop/winsock/sockaddr-2) 연결된 된 소켓의 주소를 포함 하는 구조입니다.

*nSockAddrLen*<br/>
주소의 길이 *lpSockAddr* (바이트)에서입니다.

### <a name="return-value"></a>반환 값

함수에 성공 하면 0이 아닌 값 0이 고 특정 오류 코드를 호출 하 여 검색할 수 있습니다이 고, 그렇지 [GetLastError](#getlasterror)합니다. 응용 프로그램이 받을 WSAEWOULDBLOCK, 오류 코드를 나타냅니다이 응용 프로그램에 재정의 가능한 콜백을 사용 하는 경우는 `OnConnect` 연결 작업이 완료 되 면 메시지입니다. 이 멤버 함수에 다음 오류가 적용 됩니다.

- WSANOTINITIALISED는 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하 여 앞에 있어야 합니다.

- WSAENETDOWN The Windows 소켓 구현이 네트워크 하위 시스템 실패 했음을 발견 했습니다.

- WSAEADDRINUSE 지정 된 주소를 이미 사용 중인 경우

- Windows 소켓을 차단 호출 WSAEINPROGRESS는 진행 중입니다.

- 지정된 된 주소 WSAEADDRNOTAVAIL 로컬 컴퓨터에서 사용할 수 없는 경우

- 이 소켓을 사용 하 여 지정된 된 제품군의 WSAEAFNOSUPPORT 주소를 사용할 수 없습니다.

- WSAECONNREFUSED 연결 시도가 거부 되었습니다.

- WSAEDESTADDRREQ는 대상 주소가 필요 합니다.

- WSAEFAULT 합니다 *nSockAddrLen* 인수가 올바르지 않습니다.

- 잘못 된 WSAEINVAL 호스트 주소입니다.

- WSAEISCONN 소켓이 이미 연결 되었습니다.

- WSAEMFILE 아니요 더 이상 파일 설명자를 사용할 수 있습니다.

- WSAENETUNREACH 네트워크에서 연결할 수 없습니다이 호스트에서이 시간입니다.

- 같은 WSAENOBUFS 아니요 버퍼 공간이 사용할 수 있습니다. 소켓을 연결할 수 없습니다.

- 설명자 WSAENOTSOCK 소켓 아닙니다.

- 연결 하지 않고 초과 WSAETIMEDOUT 연결 하려고 합니다.

- 소켓 표시 되어 WSAEWOULDBLOCK 비차단으로 연결을 즉시 완료할 수 없습니다.

### <a name="remarks"></a>설명

소켓이 바인딩되어 있지 않습니다. 고유 값은 시스템에서 로컬 연결에 할당 하 고 소켓으로 표시 되어 바인딩됩니다. 해당 경우 이름 구조체의 주소 필드는 모두 0으로 `Connect` 0을 반환 합니다. 확장 오류 정보를 가져오기, 호출 된 `GetLastError` 멤버 함수입니다.

스트림 소켓 (SOCK_STREAM 유형)에 대 한 외래 호스트에 대 한 활성 연결이 시작 됩니다. 소켓 호출이 성공적으로 완료 되 면 소켓 송신/수신 데이터 준비가 됩니다.

데이터 그램 소켓 (SOCK_DGRAM 유형)의 경우 기본 대상 설정 되어 후속 사용 될 `Send` 고 `Receive` 호출 합니다.

##  <a name="create"></a>  CAsyncSocket::Create

호출 된 `Create` Windows 소켓을 만들고 연결 하는 소켓 개체를 생성 한 후 멤버 함수입니다.

```
BOOL Create(
    UINT nSocketPort = 0,
    int nSocketType = SOCK_STREAM,
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE,
    LPCTSTR lpszSocketAddress = NULL);
```

### <a name="parameters"></a>매개 변수

*nSocketPort*<br/>
Windows 소켓 포트를 선택 하려는 경우, 소켓 또는 0을 사용 하 여 사용할 잘 알려진 포트입니다.

*nSocketType*<br/>
SOCK_STREAM 또는 SOCK_DGRAM 합니다.

*lEvent*<br/>
응용 프로그램에는 관여 하는 네트워크 이벤트의 조합을 지정 하는 비트 마스크입니다.

- 작업할 준비 읽기에 대 한 알림을 받도록 하려고 합니다.

- FD_WRITE 작성 하기 위한 준비에 대 한 알림을 수신 하려고 합니다.

- FD_OOB 대역의 데이터에 대 한 알림을 수신 하려고 합니다.

- FD_ACCEPT 들어오는 연결에 대 한 알림을 수신 하려고 합니다.

- FD_CONNECT 완료 된 연결에 대 한 알림을 수신 하려고 합니다.

- FD_CLOSE 소켓 닫기를 처리 알림을 받도록 하려고 합니다.

*lpszSockAddress*<br/>
연결된 된 소켓 "128.56.22.8" 같은 점으로 구분 된 숫자의 네트워크 주소를 포함 하는 문자열에 대 한 포인터입니다. 이 매개 변수를 나타내는 문자열을 NULL이 전달 된 `CAsyncSocket` 인스턴스는 모든 네트워크 인터페이스에서 클라이언트 활동에 대 한 수신 대기 해야 합니다.

### <a name="return-value"></a>반환 값

함수에 성공 하면 0이 아닌 값 0이 고 특정 오류 코드를 호출 하 여 검색할 수 있습니다이 고, 그렇지 [GetLastError](#getlasterror)합니다. 이 멤버 함수에 다음 오류가 적용 됩니다.

- WSANOTINITIALISED는 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하 여 앞에 있어야 합니다.

- WSAENETDOWN The Windows 소켓 구현이 네트워크 하위 시스템 실패 했음을 발견 했습니다.

- 지정된 된 주소 패밀리 WSAEAFNOSUPPORT 지원 되지 않습니다.

- WSAEINPROGRESS는 차단 하는 Windows 소켓 작업이 진행 중입니다.

- WSAEMFILE 아니요 더 이상 파일 설명자를 사용할 수 있습니다.

- 같은 WSAENOBUFS 아니요 버퍼 공간이 사용할 수 있습니다. 소켓을 만들 수 없습니다.

- 지정된 된 포트 WSAEPROTONOSUPPORT 지원 되지 않습니다.

- WSAEPROTOTYPE 지정된 된 포트에는이 소켓에 대 한 잘못 된 형식입니다.

- 이 주소 패밀리에서는 WSAESOCKTNOSUPPORT 지정된 된 소켓 형식이 지원 되지 않습니다.

### <a name="remarks"></a>설명

`Create` 호출 [소켓](#socket) 호출 성공 하면 [바인딩할](#bind) 소켓 지정 된 주소로 바인딩할 합니다. 다음 소켓 형식이 지원 됩니다.

- SOCK_STREAM 시퀀싱 신뢰성 있는 양방향 연결 기반의 바이트 스트림을 제공 합니다. 인터넷 주소 제품군에 대 한 (TCP (Transmission Control Protocol)를 사용합니다.

- 최대 길이가 고정된 (대개 작음)의 연결 없는, 안정적이 지 않은 패킷은 SOCK_DGRAM 지원 데이터 그램입니다. 인터넷 주소 제품군에 대 한 사용자 데이터 그램 프로토콜 (UDP)을 사용합니다.

    > [!NOTE]
    >  합니다 `Accept` 멤버 함수는 비어 있는 새에 대 한 참조 `CSocket` 매개 변수로 개체입니다. 호출 하기 전에이 개체를 생성 해야 `Accept`합니다. 염두에이 소켓 개체가 범위를 연결 닫기 이동 하는 경우. 호출 하지 마십시오 `Create` 이 새 소켓 개체에 대 한 합니다.

> [!IMPORTANT]
> `Create` 됩니다 **되지** 스레드로부터 안전 합니다.  호출 하는 경우 해당 다중 스레드 환경에서 동시에 서로 다른 스레드에 의해 호출 될 수 없습니다, 뮤텍스 또는 다른 동기화 잠금을 사용 하 여 각 호출을 보호 해야 합니다.

스트림 및 데이터 그램 소켓에 대 한 자세한 내용은 문서를 참조 하세요. [Windows 소켓: 백그라운드](../../mfc/windows-sockets-background.md) 고 [Windows 소켓: 포트 및 소켓 주소](../../mfc/windows-sockets-ports-and-socket-addresses.md) 하 고 [Windows 2 소켓 API](/windows/desktop/WinSock/windows-sockets-start-page-2)합니다.

##  <a name="detach"></a>  CAsyncSocket::Detach

소켓 핸들을 분리 하려면이 멤버 함수를 호출 합니다 *m_hSocket* 에서 데이터 멤버는 `CAsyncSocket` 개체 및 설정 *m_hSocket* NULL로 합니다.

```
SOCKET Detach();
```

##  <a name="fromhandle"></a>  CAsyncSocket::FromHandle

에 대 한 포인터를 반환 합니다.는 `CAsyncSocket` 개체입니다.

```
static CAsyncSocket* PASCAL FromHandle(SOCKET hSocket);
```

### <a name="parameters"></a>매개 변수

*hSocket*<br/>
소켓에 대 한 핸들을 포함합니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 `CAsyncSocket` 개체 이거나 없는 경우 NULL 없습니다 `CAsyncSocket` 개체에 연결 *hSocket*합니다.

### <a name="remarks"></a>설명

경우 소켓 핸들을 지정 하는 경우는 `CAsyncSocket` 개체가 핸들에 연결 되지 않은, 멤버 함수는 NULL을 반환 합니다.

##  <a name="getlasterror"></a>  CAsyncSocket::GetLastError

실패 한 마지막 작업에 대 한 오류 상태를 가져오려면이 함수를 호출 합니다.

```
static int PASCAL GetLastError();
```

### <a name="return-value"></a>반환 값

반환 값이이 스레드가 수행한 마지막 Windows Sockets API 루틴에 대 한 오류 코드를 나타냅니다.

### <a name="remarks"></a>설명

특정 멤버 함수는 오류가 발생을 나타내는 경우 `GetLastError` 적절 한 오류 코드 검색을 호출 해야 합니다. 해당 오류 코드의 목록에 대 한 개별 멤버 함수 설명을 참조 하십시오.

오류 코드에 대 한 자세한 내용은 참조 하세요. [Windows 소켓 2 API](/windows/desktop/WinSock/windows-sockets-start-page-2)합니다.

##  <a name="getpeername"></a>  CAsyncSocket::GetPeerName

이 소켓 연결 되어 있는 피어 소켓의 주소를 가져오려면이 함수를 호출 합니다.

```
BOOL GetPeerName(
    CString& rPeerAddress,
    UINT& rPeerPort);

BOOL GetPeerName(
    SOCKADDR* lpSockAddr,
    int* lpSockAddrLen);
```

### <a name="parameters"></a>매개 변수

*rPeerAddress*<br/>
에 대 한 참조를 `CString` 점으로 구분 된 숫자 IP 주소를 받는 개체입니다.

*rPeerPort*<br/>
포트를 저장 하는 UINT에 대 한 참조입니다.

*lpSockAddr*<br/>
에 대 한 포인터를 [SOCKADDR](/windows/desktop/winsock/sockaddr-2) 구조체 피어 소켓의 이름입니다.

*lpSockAddrLen*<br/>
주소의 길이에 대 한 포인터 *lpSockAddr* (바이트)에서입니다. 반환 된 *lpSockAddrLen* 의 실제 크기를 포함 하는 인수 *lpSockAddr* 바이트 단위로 반환 합니다.

### <a name="return-value"></a>반환 값

함수에 성공 하면 0이 아닌 값 0이 고 특정 오류 코드를 호출 하 여 검색할 수 있습니다이 고, 그렇지 [GetLastError](#getlasterror)합니다. 이 멤버 함수에 다음 오류가 적용 됩니다.

- WSANOTINITIALISED는 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하 여 앞에 있어야 합니다.

- WSAENETDOWN The Windows 소켓 구현이 네트워크 하위 시스템 실패 했음을 발견 했습니다.

- WSAEFAULT 합니다 *lpSockAddrLen* 인수 만큼 크지 않습니다.

- Windows 소켓을 차단 호출 WSAEINPROGRESS는 진행 중입니다.

- WSAENOTCONN 소켓이 연결 되지 않았습니다.

- 설명자 WSAENOTSOCK 소켓 아닙니다.

### <a name="remarks"></a>설명

IPv6 주소를 처리 하려면 [CAsyncSocket::GetPeerNameEx](#getpeernameex)합니다.

##  <a name="getpeernameex"></a>  CAsyncSocket::GetPeerNameEx

이 소켓 연결된 (핸들 IPv6 주소) 되는 피어 소켓의 주소를 가져오려면이 함수를 호출 합니다.

```
BOOL GetPeerNameEx(
    CString& rPeerAddress,
    UINT& rPeerPort);
```

### <a name="parameters"></a>매개 변수

*rPeerAddress*<br/>
에 대 한 참조를 `CString` 점으로 구분 된 숫자 IP 주소를 받는 개체입니다.

*rPeerPort*<br/>
포트를 저장 하는 UINT에 대 한 참조입니다.

### <a name="return-value"></a>반환 값

함수에 성공 하면 0이 아닌 값 0이 고 특정 오류 코드를 호출 하 여 검색할 수 있습니다이 고, 그렇지 [GetLastError](#getlasterror)합니다. 이 멤버 함수에 다음 오류가 적용 됩니다.

- WSANOTINITIALISED는 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하 여 앞에 있어야 합니다.

- WSAENETDOWN The Windows 소켓 구현이 네트워크 하위 시스템 실패 했음을 발견 했습니다.

- WSAEFAULT 합니다 *lpSockAddrLen* 인수 만큼 크지 않습니다.

- Windows 소켓을 차단 호출 WSAEINPROGRESS는 진행 중입니다.

- WSAENOTCONN 소켓이 연결 되지 않았습니다.

- 설명자 WSAENOTSOCK 소켓 아닙니다.

### <a name="remarks"></a>설명

이 함수는 동일 [CAsyncSocket::GetPeerName](#getpeername) IPv6 처리 한다는 점을 제외 하면 주소도으로 이전 프로토콜입니다.

##  <a name="getsockname"></a>  CAsyncSocket::GetSockName

소켓에 대 한 로컬 이름을 가져오려면이 함수를 호출 합니다.

```
BOOL GetSockName(
    CString& rSocketAddress,
    UINT& rSocketPort);

BOOL GetSockName(
    SOCKADDR* lpSockAddr,
    int* lpSockAddrLen);
```

### <a name="parameters"></a>매개 변수

*rSocketAddress*<br/>
에 대 한 참조를 `CString` 점으로 구분 된 숫자 IP 주소를 받는 개체입니다.

*rSocketPort*<br/>
포트를 저장 하는 UINT에 대 한 참조입니다.

*lpSockAddr*<br/>
에 대 한 포인터를 [SOCKADDR](/windows/desktop/winsock/sockaddr-2) 소켓의 주소를 수신 하는 구조입니다.

*lpSockAddrLen*<br/>
주소의 길이에 대 한 포인터 *lpSockAddr* (바이트)에서입니다.

### <a name="return-value"></a>반환 값

함수에 성공 하면 0이 아닌 값 0이 고 특정 오류 코드를 호출 하 여 검색할 수 있습니다이 고, 그렇지 [GetLastError](#getlasterror)합니다. 이 멤버 함수에 다음 오류가 적용 됩니다.

- WSANOTINITIALISED는 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하 여 앞에 있어야 합니다.

- WSAENETDOWN The Windows 소켓 구현이 네트워크 하위 시스템 실패 했음을 발견 했습니다.

- WSAEFAULT 합니다 *lpSockAddrLen* 인수 만큼 크지 않습니다.

- WSAEINPROGRESS는 차단 하는 Windows 소켓 작업이 진행 중입니다.

- 설명자 WSAENOTSOCK 소켓 아닙니다.

- 소켓 주소와 바인딩되지 않은 WSAEINVAL `Bind`합니다.

### <a name="remarks"></a>설명

이 호출은 때 특히 유용를 `Connect` 호출 수행 하지 않고를 `Bind` 먼저이 호출을 사용 하면만 사용 되는 시스템에서 설정 된 로컬 연결을 확인할 수 있습니다.

IPv6 주소를 처리 하려면 [CAsyncSocket::GetSockNameEx](#getsocknameex)

##  <a name="getsocknameex"></a>  CAsyncSocket::GetSockNameEx

소켓 (핸들 IPv6 주소)에 대 한 로컬 이름을 가져오려면이 함수를 호출 합니다.

```
BOOL GetSockNameEx(
    CString& rSocketAddress,
    UINT& rSocketPort);
```

### <a name="parameters"></a>매개 변수

*rSocketAddress*<br/>
에 대 한 참조를 `CString` 점으로 구분 된 숫자 IP 주소를 받는 개체입니다.

*rSocketPort*<br/>
포트를 저장 하는 UINT에 대 한 참조입니다.

### <a name="return-value"></a>반환 값

함수에 성공 하면 0이 아닌 값 0이 고 특정 오류 코드를 호출 하 여 검색할 수 있습니다이 고, 그렇지 [GetLastError](#getlasterror)합니다. 이 멤버 함수에 다음 오류가 적용 됩니다.

- WSANOTINITIALISED는 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하 여 앞에 있어야 합니다.

- WSAENETDOWN The Windows 소켓 구현이 네트워크 하위 시스템 실패 했음을 발견 했습니다.

- WSAEFAULT 합니다 *lpSockAddrLen* 인수 만큼 크지 않습니다.

- WSAEINPROGRESS는 차단 하는 Windows 소켓 작업이 진행 중입니다.

- 설명자 WSAENOTSOCK 소켓 아닙니다.

- 소켓 주소와 바인딩되지 않은 WSAEINVAL `Bind`합니다.

### <a name="remarks"></a>설명

이 호출은 동일 [CAsyncSocket::GetSockName](#getsockname) IPv6 처리 한다는 점을 제외 하면 주소도으로 이전 프로토콜입니다.

이 호출은 때 특히 유용를 `Connect` 호출 수행 하지 않고를 `Bind` 먼저이 호출을 사용 하면만 사용 되는 시스템에서 설정 된 로컬 연결을 확인할 수 있습니다.

##  <a name="getsockopt"></a>  CAsyncSocket::GetSockOpt

소켓 옵션을 검색 하려면이 멤버 함수를 호출 합니다.

```
BOOL GetSockOpt(
    int nOptionName,
    void* lpOptionValue,
    int* lpOptionLen,
    int nLevel = SOL_SOCKET);
```

### <a name="parameters"></a>매개 변수

*nOptionName*<br/>
값은 검색할 소켓 옵션입니다.

*lpOptionValue*<br/>
반환할 요청된 옵션에 대 한 값이 있는 버퍼에 대 한 포인터입니다. 버퍼에서 선택한 옵션과 관련 된 값이 반환 됩니다 *lpOptionValue*합니다. 가리키는 정수 *lpOptionLen* (바이트)이이 버퍼의 크기를 원래 있어야 하 고 반환이 반환 되는 값의 크기를 설정할 수는 있습니다. SO_LINGER에 대 한 크기 됩니다는 `LINGER` 구조체 않으면 다른 모든 옵션에 대 한 크기는 bool 됩니다 또는 **int**옵션에 따라 합니다. 옵션 및 설명 부분에 해당 크기 목록을 참조 하세요.

*lpOptionLen*<br/>
크기에 대 한 포인터를 *lpOptionValue* 바이트 버퍼입니다.

*nLevel*<br/>
입니다 옵션 정의 되어 있으면 수준 만 지원 되는 수준은 SOL_SOCKET 및 IPPROTO_TCP 합니다.

### <a name="return-value"></a>반환 값

함수에 성공 하면 0이 아닌 값 0이 고 특정 오류 코드를 호출 하 여 검색할 수 있습니다이 고, 그렇지 [GetLastError](#getlasterror)합니다. 옵션을 사용 하 여 설정 되지 않았으면 하는 경우 `SetSockOpt`, 다음 `GetSockOpt` 옵션에 대 한 기본값을 반환 합니다. 이 멤버 함수에 다음 오류가 적용 됩니다.

- WSANOTINITIALISED는 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하 여 앞에 있어야 합니다.

- WSAENETDOWN The Windows 소켓 구현이 네트워크 하위 시스템 실패 했음을 발견 했습니다.

- WSAEFAULT 합니다 *lpOptionLen* 인수가 잘못 되었습니다.

- WSAEINPROGRESS는 차단 하는 Windows 소켓 작업이 진행 중입니다.

- WSAENOPROTOOPT 옵션을 알 수 없거나 지원 되지 않는 경우 특히 SO_BROADCAST SO_ACCEPTCONN "," SO_DONTLINGER "," SO_KEEPALIVE "," SO_LINGER, "및" SO_OOBINLINE 하는 동안 SOCK_STREAM sockets SOCK_DGRAM 형식의 지원 되지 않습니다 형식의 소켓에서 지원 되지 않습니다.

- 설명자 WSAENOTSOCK 소켓 아닙니다.

### <a name="remarks"></a>설명

`GetSockOpt` 모든 상태에서 모든 형식의 소켓을 사용 하 여 연결 된 소켓 옵션에 대 한 현재 값을 검색 하 고 결과를 저장 *lpOptionValue*합니다. 옵션 패킷과 대역의 데이터 전송 등의 라우팅 등의 소켓 작업을 영향을 줍니다.

다음 옵션을 지 `GetSockOpt`합니다. 형식으로 주소가 지정 된 데이터의 형식을 식별 *lpOptionValue*합니다. TCP_NODELAY 옵션은 수준 IPPROTO_TCP;을 사용합니다. 다른 모든 옵션에는 SOL_SOCKET 수준을 사용합니다.

|값|형식|의미|
|-----------|----------|-------------|
|SO_ACCEPTCONN|BOOL|소켓이 수신 중입니다.|
|SO_BROADCAST|BOOL|소켓의 브로드캐스트 메시지 전송에 대 한 구성 됩니다.|
|SO_DEBUG|BOOL|디버깅을 사용할 수 있습니다.|
|SO_DONTLINGER|BOOL|True 이면 SO_LINGER 옵션을 사용할 수 없습니다.|
|SO_DONTROUTE|BOOL|라우팅이 비활성화 됩니다.|
|SO_ERROR|**int**|오류 상태를 검색 하 고 지웁니다.|
|SO_KEEPALIVE|BOOL|Keep-alive 보내고 있습니다.|
|SO_LINGER|`struct LINGER`|현재 링거 옵션을 반환 합니다.|
|SO_OOBINLINE|BOOL|일반 데이터 스트림의 대역의 데이터를 받고 합니다.|
|SO_RCVBUF|int|에 대 한 버퍼 크기를 받습니다.|
|SO_REUSEADDR|BOOL|소켓이 이미 사용 되는 주소에 바인딩될 수 있습니다.|
|SO_SNDBUF|**int**|버퍼 크기를 보냅니다.|
|SO_TYPE|**int**|형식 (예를 들어 SOCK_STREAM) 소켓입니다.|
|TCP_NODELAY|BOOL|보내기 통합을 위해 Nagle 알고리즘을 비활성화합니다.|

Berkeley 소프트웨어 배포 (BSD) 옵션에 대 한 지원 되지 않습니다 `GetSockOpt` 됩니다.

|값|형식|의미|
|-----------|----------|-------------|
|SO_RCVLOWAT|**int**|하위 워터 마크를 수신 합니다.|
|SO_RCVTIMEO|**int**|수신 시간 제한입니다.|
|SO_SNDLOWAT|**int**|하위 워터 마크를 보냅니다.|
|SO_SNDTIMEO|**int**|제한 시간을 보냅니다.|
|IP_OPTIONS||IP 헤더의 옵션을 가져옵니다.|
|TCP_MAXSEG|**int**|TCP 최대 세그먼트 크기를 가져옵니다.|

호출 `GetSockOpt` 는 지원 되지 않는 옵션을 사용 하면 WSAENOPROTOOPT에서 반환 되는 오류 코드가 `GetLastError`합니다.

##  <a name="ioctl"></a>  CAsyncSocket::IOCtl

소켓의 모드를 제어 하려면이 멤버 함수를 호출 합니다.

```
BOOL IOCtl(
    long lCommand,
    DWORD* lpArgument);
```

### <a name="parameters"></a>매개 변수

*lCommand*<br/>
소켓에서 수행 하는 명령입니다.

*lpArgument*<br/>
에 대 한 매개 변수에 대 한 포인터 *lCommand*합니다.

### <a name="return-value"></a>반환 값

함수에 성공 하면 0이 아닌 값 0이 고 특정 오류 코드를 호출 하 여 검색할 수 있습니다이 고, 그렇지 [GetLastError](#getlasterror)합니다. 이 멤버 함수에 다음 오류가 적용 됩니다.

- WSANOTINITIALISED는 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하 여 앞에 있어야 합니다.

- WSAENETDOWN The Windows 소켓 구현이 네트워크 하위 시스템 실패 했음을 발견 했습니다.

- WSAEINVAL *lCommand* 올바른 명령이 아닙니다 또는 *lpArgument* 에 대 한 허용 가능한 매개 변수가 아닌 *lCommand*, 또는 명령을 제공 하는 소켓의 종류에 적용 되지 않습니다. .

- WSAEINPROGRESS는 차단 하는 Windows 소켓 작업이 진행 중입니다.

- 설명자 WSAENOTSOCK 소켓 아닙니다.

### <a name="remarks"></a>설명

모든 상태에서 모든 소켓에서이 루틴을 사용할 수 있습니다. 가져오기 또는 연결 된 소켓, 프로토콜 및 통신 하위 시스템의 독립적인 운영 매개 변수를 검색 하는 것이 됩니다. 다음 명령이 지원됩니다.

- FIONBIO 사용 하거나 소켓에서 비차단 모드를 사용 하지 않도록 설정 합니다. 합니다 *lpArgument* 매개 변수를 가리키는 `DWORD`는 비차단 모드를 사용 하도록 설정 하려면 0이 아닌 이며 사용할 수 없게 하는 경우 0입니다. 하는 경우 `AsyncSelect` 실행 된 소켓을 사용 하려는 모든 시도 `IOCtl` WSAEINVAL를 사용 하 여 블로킹 모드 다시 실패 소켓을 설정 합니다. 소켓이 블로킹 모드 다시 설정 하 고 WSAEINVAL 오류 방지, 응용 프로그램 해제 해야 합니다 `AsyncSelect` 를 호출 하 여 `AsyncSelect` 사용 하 여 합니다 *lEvent* 매개 변수를 0으로 호출 `IOCtl`합니다.

- 하나를 사용 하 여 읽을 수 있는 바이트의 최대 수를 결정 하는 FIONREAD `Receive` 이 소켓에서 호출 합니다. 합니다 *lpArgument* 매개 변수를 가리키는 `DWORD` 는 `IOCtl` 결과 저장 합니다. 이 소켓 SOCK_STREAM 형식의 경우 단일에서 FIONREAD 읽을 수 있는 데이터의 총 크기를 반환 합니다 `Receive`;이 일반적으로 동일한 소켓에서 큐에 대기 된 데이터의 총 크기입니다. 이 소켓 SOCK_DGRAM 형식의 경우 FIONREAD 소켓에서 대기열에 첫 번째 데이터 그램의 크기를 반환 합니다.

- SIOCATMARK 결정 모든 대역의 데이터를 읽고 나면 여부. 이 인라인 수신 대역의 데이터 (SO_OOBINLINE)에 구성 된 SOCK_STREAM 형식의 소켓에만 적용 됩니다. 대역의 데이터가 없는 읽을 대기 중인 경우 작업이 0이 아닌 값을 반환 합니다. 그렇지 않으면 0이 고, 다음 반환 `Receive` 또는 `ReceiveFrom` 수행할 소켓 앞에 "표시" 하는 데이터의 일부 또는 전부를 검색 합니다; 응용 프로그램 데이터가 남아 있는지 여부를 확인 하려면 SIOCATMARK 작업을 사용 해야 합니다. 일반 데이터 앞에 "긴급" (대역) 데이터를 순서 대로 받습니다. (유의 한 `Receive` 또는 `ReceiveFrom` 대역의 및 일반 데이터는 동일한 호출에서을 혼합 해서는 안 됩니다.) 합니다 *lpArgument* 매개 변수를 가리키는 `DWORD` 는 `IOCtl` 결과 저장 합니다.

이 함수는 하위 집합 `ioctl()` Berkeley 소켓에서 사용 합니다. 특히 SIOCATMARK는 지원 되는 소켓 수준 명령을 해당 FIOASYNC, 하는 명령이 없기 때문입니다.

##  <a name="listen"></a>  CAsyncSocket::Listen

들어오는 연결 요청을 수신 하려면이 멤버 함수를 호출 합니다.

```
BOOL Listen(int nConnectionBacklog = 5);
```

### <a name="parameters"></a>매개 변수

*nConnectionBacklog*<br/>
보류 중인 연결 큐 증가할 수 있는 최대 길이입니다. 유효한 범위는 1에서 5입니다.

### <a name="return-value"></a>반환 값

함수에 성공 하면 0이 아닌 값 0이 고 특정 오류 코드를 호출 하 여 검색할 수 있습니다이 고, 그렇지 [GetLastError](#getlasterror)합니다. 이 멤버 함수에 다음 오류가 적용 됩니다.

- WSANOTINITIALISED는 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하 여 앞에 있어야 합니다.

- WSAENETDOWN The Windows 소켓 구현이 네트워크 하위 시스템 실패 했음을 발견 했습니다.

- 사용 하 여 주소에서 수신 대기할 WSAEADDRINUSE 시도 되었습니다.

- WSAEINPROGRESS는 차단 하는 Windows 소켓 작업이 진행 중입니다.

- 소켓으로 바인딩되지 않은 WSAEINVAL `Bind` 또는 이미 연결 합니다.

- WSAEISCONN 소켓이 이미 연결 되었습니다.

- WSAEMFILE 아니요 더 이상 파일 설명자를 사용할 수 있습니다.

- 같은 WSAENOBUFS 아니요 버퍼 공간이 사용할 수 있습니다.

- 설명자 WSAENOTSOCK 소켓 아닙니다.

- 참조 된 소켓을 지 원하는 형식이 아닙니다 WSAEOPNOTSUPP는 `Listen` 작업 합니다.

### <a name="remarks"></a>설명

연결을 수락 하면 소켓 처음으로 만들어집니다 `Create`, 들어오는 연결에 대 한 백로그를 사용 하 여 지정 된 `Listen`를 사용 하 여 연결 허용 되는 다음 `Accept`합니다. `Listen` 에 적용 됩니다 소켓 연결을 지 원하는, SOCK_STREAM 형식의 합니다. 이 소켓 여기서 들어오는 연결이 승인 되며 프로세스에 의해 승인 보류 중인 큐에 대기 "수동" 모드로 설정 됩니다.

서버 (또는 연결을 허용 하려는 모든 응용 프로그램)이이 함수는 일반적으로 한 번에 둘 이상의 연결 요청을 있는 수 없습니다: 전체 큐를 사용 하 여 연결 요청이 도착 하면 클라이언트 오류가 발생 하는 WSAECONNREFUSED 합니다.

`Listen` 계속 해 서 사용할 수 있는 포트 없음 (설명자) 경우 상대의 작동 하려고 합니다. 이 연결을 수락 하며 큐를 비울 때까지 합니다. 포트를 사용할 수 있게 하는 경우 이후의 호출 `Listen` 또는 `Accept` 가능한 경우에 현재 또는 가장 최근 ","백로그 큐를 충전 하 고 들어오는 연결을 수신 대기를 다시 시작 됩니다.

##  <a name="m_hsocket"></a>  CAsyncSocket::m_hSocket

이 캡슐화 된 소켓의 소켓 핸들을 포함 `CAsyncSocket` 개체입니다.

```
SOCKET m_hSocket;
```

##  <a name="onaccept"></a>  CAsyncSocket::OnAccept

호출 하 여 보류 중인 연결 요청 받을 수 있는 수신 대기 소켓에 알리기 위해 프레임 워크에서 호출 된 [Accept](#accept) 멤버 함수입니다.

```
virtual void OnAccept(int nErrorCode);
```

### <a name="parameters"></a>매개 변수

*nErrorCode*<br/>
소켓에서 가장 최근의 오류입니다. 다음 오류 코드에 적용 된 `OnAccept` 멤버 함수:

- **0** 성공적으로 실행 하는 함수입니다.

- WSAENETDOWN The Windows 소켓 구현이 네트워크 하위 시스템 실패 했음을 발견 했습니다.

### <a name="remarks"></a>설명

자세한 내용은 참조 하세요. [Windows 소켓: 알림 소켓](../../mfc/windows-sockets-socket-notifications.md)합니다.

##  <a name="onclose"></a>  CAsyncSocket::OnClose

해당 프로세스에 의해 연결된 된 소켓 닫히도록이 소켓에 알리기 위해 프레임 워크에서 호출 됩니다.

```
virtual void OnClose(int nErrorCode);
```

### <a name="parameters"></a>매개 변수

*nErrorCode*<br/>
소켓에서 가장 최근의 오류입니다. 다음 오류 코드에 적용 된 `OnClose` 멤버 함수:

- **0** 성공적으로 실행 하는 함수입니다.

- WSAENETDOWN The Windows 소켓 구현이 네트워크 하위 시스템 실패 했음을 발견 했습니다.

- 원격 측에 의해 WSAECONNRESET 연결 다시 설정 되었습니다.

- WSAECONNABORTED 연결 제한 시간 또는 다른 오류로 인해 중단 되었습니다.

### <a name="remarks"></a>설명

자세한 내용은 참조 하세요. [Windows 소켓: 알림 소켓](../../mfc/windows-sockets-socket-notifications.md)합니다.

##  <a name="onconnect"></a>  CAsyncSocket::OnConnect

해당 연결 시도가 완료 되 면 성공적으로 또는 오류가이 연결 소켓에 알리기 위해 프레임 워크에서 호출 됩니다.

```
virtual void OnConnect(int nErrorCode);
```

### <a name="parameters"></a>매개 변수

*nErrorCode*<br/>
소켓에서 가장 최근의 오류입니다. 다음 오류 코드에 적용 된 `OnConnect` 멤버 함수:

- **0** 성공적으로 실행 하는 함수입니다.

- WSAEADDRINUSE 지정 된 주소를 이미 사용 중인 경우

- 지정된 된 주소 WSAEADDRNOTAVAIL 로컬 컴퓨터에서 사용할 수 없는 경우

- 이 소켓을 사용 하 여 지정된 된 제품군의 WSAEAFNOSUPPORT 주소를 사용할 수 없습니다.

- WSAECONNREFUSED 연결 시도가 강제로 거부 되었습니다.

- WSAEDESTADDRREQ는 대상 주소가 필요 합니다.

- WSAEFAULT 합니다 *lpSockAddrLen* 인수가 올바르지 않습니다.

- WSAEINVAL 소켓 주소에 이미 바인딩되어 있습니다.

- WSAEISCONN 소켓이 이미 연결 되었습니다.

- WSAEMFILE 아니요 더 이상 파일 설명자를 사용할 수 있습니다.

- WSAENETUNREACH 네트워크에서 연결할 수 없습니다이 호스트에서이 시간입니다.

- 같은 WSAENOBUFS 아니요 버퍼 공간이 사용할 수 있습니다. 소켓을 연결할 수 없습니다.

- WSAENOTCONN 소켓이 연결 되지 않았습니다.

- WSAENOTSOCK 설명자는 파일, 소켓 없습니다.

- 연결 하지 않고 연결 시도가 WSAETIMEDOUT 초과 합니다.

### <a name="remarks"></a>설명

> [!NOTE]
>  [CSocket](../../mfc/reference/csocket-class.md), `OnConnect` 알림 함수가 호출 되지 않습니다. 연결의 경우 단순히 호출 `Connect`, (성공적으로 또는 오류에서) 연결이 완료 되 면 반환 합니다. MFC 구현 세부 정보는 연결 알림을 처리 하는 방법입니다.

자세한 내용은 참조 하세요. [Windows 소켓: 알림 소켓](../../mfc/windows-sockets-socket-notifications.md)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCAsyncSocket#1](../../mfc/reference/codesnippet/cpp/casyncsocket-class_1.cpp)]

##  <a name="onoutofbanddata"></a>  CAsyncSocket::OnOutOfBandData

보내는 소켓 보낼 대역의 데이터가 포함 된 수신 소켓에 알리기 위해 프레임 워크에서 호출 됩니다.

```
virtual void OnOutOfBandData(int nErrorCode);
```

### <a name="parameters"></a>매개 변수

*nErrorCode*<br/>
소켓에서 가장 최근의 오류입니다. 다음 오류 코드에 적용 된 `OnOutOfBandData` 멤버 함수:

- **0** 성공적으로 실행 하는 함수입니다.

- WSAENETDOWN The Windows 소켓 구현이 네트워크 하위 시스템 실패 했음을 발견 했습니다.

### <a name="remarks"></a>설명

대역의 데이터는 각 쌍이 SOCK_STREAM 형식의 연결 된 소켓의 연결 된 논리적으로 독립 채널. 채널은 긴급 한 데이터를 보내는 데 일반적으로 합니다.

MFC에는 있지만 클래스의 사용자가 대역의 데이터를 지 원하는 `CAsyncSocket` 않는 정보를 사용할 것이 좋습니다. 더 쉬운 방법은 해당 데이터를 전달 하는 데는 두 번째 소켓을 만드는 것입니다. 대역의 데이터에 대 한 자세한 내용은 참조 하세요. [Windows 소켓: 알림 소켓](../../mfc/windows-sockets-socket-notifications.md)합니다.

##  <a name="onreceive"></a>  CAsyncSocket::OnReceive

호출 하 여 검색할 수 있는 버퍼의 데이터는이 소켓에 알리기 위해 프레임 워크에서 호출 된 `Receive` 멤버 함수입니다.

```
virtual void OnReceive(int nErrorCode);
```

### <a name="parameters"></a>매개 변수

*nErrorCode*<br/>
소켓에서 가장 최근의 오류입니다. 다음 오류 코드에 적용 된 `OnReceive` 멤버 함수:

- **0** 성공적으로 실행 하는 함수입니다.

- WSAENETDOWN The Windows 소켓 구현이 네트워크 하위 시스템 실패 했음을 발견 했습니다.

### <a name="remarks"></a>설명

자세한 내용은 참조 하세요. [Windows 소켓: 알림 소켓](../../mfc/windows-sockets-socket-notifications.md)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCAsyncSocket#2](../../mfc/reference/codesnippet/cpp/casyncsocket-class_2.cpp)]

##  <a name="onsend"></a>  CAsyncSocket::OnSend

호출 하 여 데이터 보내기 이제 수 소켓에 알리기 위해 프레임 워크에서 호출 된 `Send` 멤버 함수입니다.

```
virtual void OnSend(int nErrorCode);
```

### <a name="parameters"></a>매개 변수

*nErrorCode*<br/>
소켓에서 가장 최근의 오류입니다. 다음 오류 코드에 적용 된 `OnSend` 멤버 함수:

- **0** 성공적으로 실행 하는 함수입니다.

- WSAENETDOWN The Windows 소켓 구현이 네트워크 하위 시스템 실패 했음을 발견 했습니다.

### <a name="remarks"></a>설명

자세한 내용은 참조 하세요. [Windows 소켓: 알림 소켓](../../mfc/windows-sockets-socket-notifications.md)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCAsyncSocket#3](../../mfc/reference/codesnippet/cpp/casyncsocket-class_3.cpp)]

##  <a name="operator_eq"></a>  CAsyncSocket::operator =

새 값을 할당 한 `CAsyncSocket` 개체입니다.

```
void operator=(const CAsyncSocket& rSrc);
```

### <a name="parameters"></a>매개 변수

*rSrc*<br/>
기존에 대 한 참조 `CAsyncSocket` 개체입니다.

### <a name="remarks"></a>설명

기존 복사 하려면이 함수를 호출 `CAsyncSocket` 개체를 다른 `CAsyncSocket` 개체입니다.

##  <a name="operator_socket"></a>  CAsyncSocket::operator SOCKET

이 연산자의 소켓 핸들을 검색 하는 데는 `CAsyncSocket` 개체입니다.

```
operator SOCKET() const;
```

### <a name="return-value"></a>반환 값

성공 하면 소켓 개체;의 핸들 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

Windows Api를 직접 호출 하는 핸들을 사용할 수 있습니다.

##  <a name="receive"></a>  CAsyncSocket::Receive

소켓에서 데이터를 수신 하려면이 멤버 함수를 호출 합니다.

```
virtual int Receive(
    void* lpBuf,
    int nBufLen,
    int nFlags = 0);
```

### <a name="parameters"></a>매개 변수

*lpBuf*<br/>
들어오는 데이터에 대 한 버퍼입니다.

*nBufLen*<br/>
길이가 *lpBuf* (바이트)에서입니다.

*nFlags*<br/>
호출 되는 방식을 지정 합니다. 이 함수의 의미 체계 소켓 옵션에 의해 결정 되 고 *nFlags* 매개 변수입니다. 다음 값 중 하나를 결합 하 여 생성 되 고 후자는 C++ **나** 연산자:

- MSG_PEEK 들어오는 데이터를 피킹합니다. 데이터 버퍼에 복사 됩니다 있지만 입력된 큐에서 제거 되지 않습니다.

- MSG_OOB 프로세스 대역의 데이터입니다.

### <a name="return-value"></a>반환 값

오류가 발생 하지 않으면, `Receive` 받은 바이트 수를 반환 합니다. 연결이 닫힌 경우 0을 반환 합니다. 그렇지 않으면 SOCKET_ERROR의 값이 반환 하 고 특정 오류 코드를 호출 하 여 검색할 수 있습니다 [GetLastError](#getlasterror)합니다. 이 멤버 함수에 다음 오류가 적용 됩니다.

- WSANOTINITIALISED는 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하 여 앞에 있어야 합니다.

- WSAENETDOWN The Windows 소켓 구현이 네트워크 하위 시스템 실패 했음을 발견 했습니다.

- WSAENOTCONN 소켓이 연결 되지 않았습니다.

- WSAEINPROGRESS는 차단 하는 Windows 소켓 작업이 진행 중입니다.

- 설명자 WSAENOTSOCK 소켓 아닙니다.

- WSAEOPNOTSUPP MSG_OOB 지정 되었지만 소켓 SOCK_STREAM 유형이 아닙니다.

- 소켓 WSAESHUTDOWN 종료 되었습니다. 호출 하는 것이 불가능 `Receive` 한 후 소켓 `ShutDown` 를 호출 했습니다 *nHow* 0 또는 2로 설정 합니다.

- 소켓 표시 되어 WSAEWOULDBLOCK으로 비차단 및 `Receive` 작업이 중단 됩니다.

- WSAEMSGSIZE 데이터 그램이 너무 커서 지정된 된 버퍼에 맞지 않습니다 및 잘렸습니다.

- 소켓으로 바인딩되지 않은 WSAEINVAL `Bind`합니다.

- WSAECONNABORTED 가상 회로가 시간 초과 또는 기타 오류로 인해 중단 되었습니다.

- 가상 회로가 WSAECONNRESET 원격 측에 의해 다시 설정 되었습니다.

### <a name="remarks"></a>설명

이 함수는 연결 된 스트림 또는 데이터 그램 소켓에 사용 되 고 들어오는 데이터를 읽는 데 사용 됩니다.

형식의 SOCK_STREAM 소켓, 제공 된 버퍼의 크기를 현재 사용 가능한 한 많은 정보 반환 됩니다. 소켓 대역의 데이터 (소켓 옵션 SO_OOBINLINE)의 인라인 수신에 구성 된 경우 대역의 데이터를 읽지 대역의 데이터만 반환 됩니다. 응용 프로그램에서 사용할 수는 `IOCtlSIOCATMARK` 옵션 또는 [OnOutOfBandData](#onoutofbanddata) 밴드를 보다 데이터가 남아를 읽을 수 있는지 여부를 확인 하려면.

데이터 그램 소켓에 대 한 데이터는 제공 된 버퍼의 크기를 최대 첫 번째 큐에 넣은 데이터 그램에서 추출 됩니다. 데이터 그램 제공 된 버퍼 보다 큰 경우 버퍼가 데이터 그램의 첫 번째 부분을 사용 하 여 채워집니다, 초과 데이터는 손실 및 `Receive` 오류 코드로 SOCKET_ERROR 값 WSAEMSGSIZE로 반환 합니다. 소켓에서 사용할 수 있는 들어오는 데이터가 없는 경우 SOCKET_ERROR 값 WSAEWOULDBLOCK로 오류 코드로 반환 됩니다. 합니다 [OnReceive](#onreceive) 더 많은 데이터가 도착 하는 경우를 결정 하는 콜백 함수를 사용할 수 있습니다.

소켓 SOCK_STREAM 형식이 며 원격측에 연결이 정상적으로 종료, 하는 경우는 `Receive` 수신한 0 바이트를 사용 하 여 즉시 완료 됩니다. 연결을 다시 설정 된 `Receive` WSAECONNRESET 오류로 인해 실패 합니다.

`Receive` 각 시간에 대 한 한 번만 호출 해야 [CAsyncSocket::OnReceive](#onreceive) 라고 합니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CAsyncSocket::OnReceive](#onreceive)합니다.

##  <a name="receivefrom"></a>  CAsyncSocket::ReceiveFrom

데이터 그램을 받고에서 원본 주소를 저장 하려면이 멤버 함수를 호출 합니다 [SOCKADDR](/windows/desktop/winsock/sockaddr-2) 구조 나 *rSocketAddress*합니다.

```
int ReceiveFrom(
    void* lpBuf,
    int nBufLen,
    CString& rSocketAddress,
    UINT& rSocketPort,
    int nFlags = 0);

int ReceiveFrom(
    void* lpBuf,
    int nBufLen,
    SOCKADDR* lpSockAddr,
    int* lpSockAddrLen,
    int nFlags = 0);
```

### <a name="parameters"></a>매개 변수

*lpBuf*<br/>
들어오는 데이터에 대 한 버퍼입니다.

*nBufLen*<br/>
길이가 *lpBuf* (바이트)에서입니다.

*rSocketAddress*<br/>
에 대 한 참조를 `CString` 점으로 구분 된 숫자 IP 주소를 받는 개체입니다.

*rSocketPort*<br/>
포트를 저장 하는 UINT에 대 한 참조입니다.

*lpSockAddr*<br/>
에 대 한 포인터를 [SOCKADDR](/windows/desktop/winsock/sockaddr-2) 반환 될 때 원본 주소를 보유 하는 구조입니다.

*lpSockAddrLen*<br/>
원본 주소 길이에 대 한 포인터 *lpSockAddr* (바이트)에서입니다.

*nFlags*<br/>
호출 되는 방식을 지정 합니다. 이 함수의 의미 체계 소켓 옵션에 의해 결정 되 고 *nFlags* 매개 변수입니다. 다음 값 중 하나를 결합 하 여 생성 되 고 후자는 C++ **나** 연산자:

- MSG_PEEK 들어오는 데이터를 피킹합니다. 데이터 버퍼에 복사 됩니다 있지만 입력된 큐에서 제거 되지 않습니다.

- MSG_OOB 프로세스 대역의 데이터입니다.

### <a name="return-value"></a>반환 값

오류가 발생 하지 않으면, `ReceiveFrom` 받은 바이트 수를 반환 합니다. 연결이 닫힌 경우 0을 반환 합니다. 그렇지 않으면 SOCKET_ERROR의 값이 반환 하 고 특정 오류 코드를 호출 하 여 검색할 수 있습니다 `GetLastError`합니다. 이 멤버 함수에 다음 오류가 적용 됩니다.

- WSANOTINITIALISED는 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하 여 앞에 있어야 합니다.

- WSAENETDOWN The Windows 소켓 구현이 네트워크 하위 시스템 실패 했음을 발견 했습니다.

- WSAEFAULT 합니다 *lpSockAddrLen* 인수가 잘못 되었습니다: 합니다 *lpSockAddr* 버퍼가 너무 작아서 피어 주소를 수용 하기 위해.

- WSAEINPROGRESS는 차단 하는 Windows 소켓 작업이 진행 중입니다.

- 소켓으로 바인딩되지 않은 WSAEINVAL `Bind`합니다.

- 소켓 아닙니다 WSAENOTCONN 연결 (SOCK_STREAM에만 해당).

- 설명자 WSAENOTSOCK 소켓 아닙니다.

- WSAEOPNOTSUPP MSG_OOB 지정 되었지만 소켓 SOCK_STREAM 유형이 아닙니다.

- 소켓 WSAESHUTDOWN 종료 되었습니다. 호출 하는 것이 불가능 `ReceiveFrom` 한 후 소켓 `ShutDown` 를 호출 했습니다 *nHow* 0 또는 2로 설정 합니다.

- 소켓 표시 되어 WSAEWOULDBLOCK으로 비차단 및 `ReceiveFrom` 작업이 중단 됩니다.

- WSAEMSGSIZE 데이터 그램이 너무 커서 지정된 된 버퍼에 맞지 않습니다 및 잘렸습니다.

- WSAECONNABORTED 가상 회로가 시간 초과 또는 기타 오류로 인해 중단 되었습니다.

- 가상 회로가 WSAECONNRESET 원격 측에 의해 다시 설정 되었습니다.

### <a name="remarks"></a>설명

이 함수는 (가능한 경우 연결된) 소켓에서 들어오는 데이터를 읽고 데이터를 보낸 주소에 사용 됩니다.

IPv6 주소를 처리 하려면 [CAsyncSocket::ReceiveFromEx](#receivefromex)합니다.

형식의 SOCK_STREAM 소켓, 제공 된 버퍼의 크기를 현재 사용 가능한 한 많은 정보 반환 됩니다. 소켓 대역의 데이터 (소켓 옵션 SO_OOBINLINE)의 인라인 수신에 구성 된 경우 대역의 데이터를 읽지 대역의 데이터만 반환 됩니다. 응용 프로그램에서 사용할 수는 `IOCtlSIOCATMARK` 옵션 또는 `OnOutOfBandData` 밴드를 보다 데이터가 남아를 읽을 수 있는지 여부를 확인 하려면. 합니다 *lpSockAddr* 하 고 *lpSockAddrLen* SOCK_STREAM 소켓에 대 한 매개 변수가 무시 됩니다.

데이터 그램 소켓에 대 한 데이터는 제공 된 버퍼의 크기를 최대 첫 번째 큐에 넣은 데이터 그램에서 추출 됩니다. 데이터 그램 제공 된 버퍼 보다 큰 경우 메시지의 첫 번째 부분을 사용 하 여 버퍼가 채워집니다, 초과 데이터는 손실 및 `ReceiveFrom` 오류 코드로 SOCKET_ERROR 값 WSAEMSGSIZE로 반환 합니다.

하는 경우 *lpSockAddr* 이 값은 0 및 소켓은 SOCK_DGRAM 형식의 데이터를 전송 하는 소켓의 네트워크 주소를 해당 복사할 [SOCKADDR](/windows/desktop/winsock/sockaddr-2) 구조입니다. 가리키는 값 *lpSockAddrLen* 이 구조체의 크기로 초기화 되 고 여기에 저장 된 주소의 실제 크기를 나타내기 위해 반환이 수정 됩니다. 소켓에서 들어오는 데이터가 없는 경우는 `ReceiveFrom` 소켓이 아닌 도착 하는 데이터에 대 한 호출은 기다립니다 비차단 합니다. 이 경우 SOCKET_ERROR 값 WSAEWOULDBLOCK로 오류 코드로 반환 됩니다. `OnReceive` 콜백 더 많은 데이터가 도착 하는 경우 결정 데 사용할 수 있습니다.

소켓 SOCK_STREAM 형식이 며 원격측에 연결이 정상적으로 종료, 하는 경우는 `ReceiveFrom` 수신한 0 바이트를 사용 하 여 즉시 완료 됩니다.

##  <a name="receivefromex"></a>  CAsyncSocket::ReceiveFromEx

데이터 그램을 받고에서 원본 주소를 저장 하려면이 멤버 함수를 호출 합니다 [SOCKADDR](/windows/desktop/winsock/sockaddr-2) 구조 나 *rSocketAddress* (IPv6 주소 처리).

```
int ReceiveFromEx(
    void* lpBuf,
    int nBufLen,
    CString& rSocketAddress,
    UINT& rSocketPort,
    int nFlags = 0);
```

### <a name="parameters"></a>매개 변수

*lpBuf*<br/>
들어오는 데이터에 대 한 버퍼입니다.

*nBufLen*<br/>
길이가 *lpBuf* (바이트)에서입니다.

*rSocketAddress*<br/>
에 대 한 참조를 `CString` 점으로 구분 된 숫자 IP 주소를 받는 개체입니다.

*rSocketPort*<br/>
포트를 저장 하는 UINT에 대 한 참조입니다.

*nFlags*<br/>
호출 되는 방식을 지정 합니다. 이 함수의 의미 체계 소켓 옵션에 의해 결정 되 고 *nFlags* 매개 변수입니다. 다음 값 중 하나를 결합 하 여 생성 되 고 후자는 C++ **나** 연산자:

- MSG_PEEK 들어오는 데이터를 피킹합니다. 데이터 버퍼에 복사 됩니다 있지만 입력된 큐에서 제거 되지 않습니다.

- MSG_OOB 프로세스 대역의 데이터입니다.

### <a name="return-value"></a>반환 값

오류가 발생 하지 않으면, `ReceiveFromEx` 받은 바이트 수를 반환 합니다. 연결이 닫힌 경우 0을 반환 합니다. 그렇지 않으면 SOCKET_ERROR의 값이 반환 하 고 특정 오류 코드를 호출 하 여 검색할 수 있습니다 `GetLastError`합니다. 이 멤버 함수에 다음 오류가 적용 됩니다.

- WSANOTINITIALISED는 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하 여 앞에 있어야 합니다.

- WSAENETDOWN The Windows 소켓 구현이 네트워크 하위 시스템 실패 했음을 발견 했습니다.

- WSAEFAULT 합니다 *lpSockAddrLen* 인수가 잘못 되었습니다: 합니다 *lpSockAddr* 버퍼가 너무 작아서 피어 주소를 수용 하기 위해.

- WSAEINPROGRESS는 차단 하는 Windows 소켓 작업이 진행 중입니다.

- 소켓으로 바인딩되지 않은 WSAEINVAL `Bind`합니다.

- 소켓 아닙니다 WSAENOTCONN 연결 (SOCK_STREAM에만 해당).

- 설명자 WSAENOTSOCK 소켓 아닙니다.

- WSAEOPNOTSUPP MSG_OOB 지정 되었지만 소켓 SOCK_STREAM 유형이 아닙니다.

- 소켓 WSAESHUTDOWN 종료 되었습니다. 호출 하는 것이 불가능 `ReceiveFromEx` 한 후 소켓 `ShutDown` 를 호출 했습니다 *nHow* 0 또는 2로 설정 합니다.

- 소켓 표시 되어 WSAEWOULDBLOCK으로 비차단 및 `ReceiveFromEx` 작업이 중단 됩니다.

- WSAEMSGSIZE 데이터 그램이 너무 커서 지정된 된 버퍼에 맞지 않습니다 및 잘렸습니다.

- WSAECONNABORTED 가상 회로가 시간 초과 또는 기타 오류로 인해 중단 되었습니다.

- 가상 회로가 WSAECONNRESET 원격 측에 의해 다시 설정 되었습니다.

### <a name="remarks"></a>설명

이 함수는 (가능한 경우 연결된) 소켓에서 들어오는 데이터를 읽고 데이터를 보낸 주소에 사용 됩니다.

이 함수는 동일 [CAsyncSocket::ReceiveFrom](#receivefrom) IPv6 처리 한다는 점을 제외 하면 주소도으로 이전 프로토콜입니다.

형식의 SOCK_STREAM 소켓, 제공 된 버퍼의 크기를 현재 사용 가능한 한 많은 정보 반환 됩니다. 소켓 대역의 데이터 (소켓 옵션 SO_OOBINLINE)의 인라인 수신에 구성 된 경우 대역의 데이터를 읽지 대역의 데이터만 반환 됩니다. 응용 프로그램에서 사용할 수는 `IOCtlSIOCATMARK` 옵션 또는 `OnOutOfBandData` 밴드를 보다 데이터가 남아를 읽을 수 있는지 여부를 확인 하려면. 합니다 *lpSockAddr* 하 고 *lpSockAddrLen* SOCK_STREAM 소켓에 대 한 매개 변수가 무시 됩니다.

데이터 그램 소켓에 대 한 데이터는 제공 된 버퍼의 크기를 최대 첫 번째 큐에 넣은 데이터 그램에서 추출 됩니다. 데이터 그램 제공 된 버퍼 보다 큰 경우 메시지의 첫 번째 부분을 사용 하 여 버퍼가 채워집니다, 초과 데이터는 손실 및 `ReceiveFromEx` 오류 코드로 SOCKET_ERROR 값 WSAEMSGSIZE로 반환 합니다.

하는 경우 *lpSockAddr* 이 값은 0 및 소켓은 SOCK_DGRAM 형식의 데이터를 전송 하는 소켓의 네트워크 주소를 해당 복사할 [SOCKADDR](/windows/desktop/winsock/sockaddr-2) 구조입니다. 가리키는 값 *lpSockAddrLen* 이 구조체의 크기로 초기화 되 고 여기에 저장 된 주소의 실제 크기를 나타내기 위해 반환이 수정 됩니다. 소켓에서 들어오는 데이터가 없는 경우는 `ReceiveFromEx` 소켓이 아닌 도착 하는 데이터에 대 한 호출은 기다립니다 비차단 합니다. 이 경우 SOCKET_ERROR 값 WSAEWOULDBLOCK로 오류 코드로 반환 됩니다. `OnReceive` 콜백 더 많은 데이터가 도착 하는 경우 결정 데 사용할 수 있습니다.

소켓 SOCK_STREAM 형식이 며 원격측에 연결이 정상적으로 종료, 하는 경우는 `ReceiveFromEx` 수신한 0 바이트를 사용 하 여 즉시 완료 됩니다.

##  <a name="send"></a>  CAsyncSocket::Send

연결된 된 소켓에서 데이터를 보내도록이 멤버 함수를 호출 합니다.

```
virtual int Send(
    const void* lpBuf,
    int nBufLen,
    int nFlags = 0);
```

### <a name="parameters"></a>매개 변수

*lpBuf*<br/>
전송할 데이터가 들어 있는 버퍼입니다.

*nBufLen*<br/>
에 있는 데이터의 길이 *lpBuf* (바이트)에서입니다.

*nFlags*<br/>
호출 되는 방식을 지정 합니다. 이 함수의 의미 체계 소켓 옵션에 의해 결정 되 고 *nFlags* 매개 변수입니다. 다음 값 중 하나를 결합 하 여 생성 되 고 후자는 C++ **나** 연산자:

- MSG_DONTROUTE 데이터 라우팅 적용 되지 않아야 지정 합니다. Windows 소켓 공급자는이 플래그를 무시 하도록 선택할 수 있습니다.

- MSG_OOB 대역의 데이터 보내기 (SOCK_STREAM에만 해당).

### <a name="return-value"></a>반환 값

오류가 발생 하지 않으면, `Send` 전송 되는 문자의 총 수를 반환 합니다. (나타난 수보다 작을 수 있습니다이 *nBufLen*.) 그렇지 않으면 SOCKET_ERROR의 값이 반환 하 고 특정 오류 코드를 호출 하 여 검색할 수 있습니다 [GetLastError](#getlasterror)합니다. 이 멤버 함수에 다음 오류가 적용 됩니다.

- WSANOTINITIALISED는 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하 여 앞에 있어야 합니다.

- WSAENETDOWN The Windows 소켓 구현이 네트워크 하위 시스템 실패 했음을 발견 했습니다.

- 요청된 된 주소 WSAEACCES 브로드캐스트 주소 이지만 적절 한 플래그 설정 되지 않았습니다.

- WSAEINPROGRESS는 차단 하는 Windows 소켓 작업이 진행 중입니다.

- WSAEFAULT 합니다 *lpBuf* 사용자 주소 공간의 유효한 부분에 인수가 아닙니다.

- Windows 소켓 구현을 삭제 하므로 WSAENETRESET 연결 다시 설정 해야 합니다.

- 같은 WSAENOBUFS The Windows 소켓 구현을 버퍼 교착 상태를 보고합니다.

- WSAENOTCONN 소켓이 연결 되지 않았습니다.

- 설명자 WSAENOTSOCK 소켓 아닙니다.

- WSAEOPNOTSUPP MSG_OOB 지정 되었지만 소켓 SOCK_STREAM 유형이 아닙니다.

- 소켓 WSAESHUTDOWN 종료 되었습니다. 호출 하는 것이 불가능 `Send` 한 후 소켓 `ShutDown` 를 호출 했습니다 *nHow* 1 또는 2로 설정 합니다.

- 소켓 표시 되어 WSAEWOULDBLOCK 비차단으로 요청 된 작업이 차단 됩니다.

- 소켓 WSAEMSGSIZE SOCK_DGRAM, 형식이 며 데이터 그램 Windows 소켓 구현에서 지원 되는 최대값 보다 큽니다.

- 소켓으로 바인딩되지 않은 WSAEINVAL `Bind`합니다.

- WSAECONNABORTED 가상 회로가 시간 초과 또는 기타 오류로 인해 중단 되었습니다.

- 가상 회로가 WSAECONNRESET 원격 측에 의해 다시 설정 되었습니다.

### <a name="remarks"></a>설명

`Send` 연결 된 스트림 또는 데이터 그램 소켓에 보내는 데이터를 쓸 사용 됩니다. 데이터 그램 소켓에 대 한 주의 해야 하지 하 여 제공 된 기본 서브넷으로 최대 IP 패킷 크기를 초과 하는 `iMaxUdpDg` 요소에는 [WSADATA](/windows/desktop/api/winsock2/ns-winsock2-wsadata) 반환한 구조 `AfxSocketInit`합니다. 데이터가 너무 길어 기본 프로토콜을 통해 자동으로 전달할 경우 WSAEMSGSIZE는 반환 된 오류를 통해 `GetLastError`, 데이터가 전송 됩니다.

데이터 그램 소켓 성공적으로 완료 된을 `Send` 성공적으로 전달 된 데이터를 나타내지 않습니다.

`CAsyncSocket` SOCK_STREAM 형식의 개체에 쓴 바이트 수가-로컬 및 외부 호스트의 버퍼 가용성에 따라 요청된 된 길이 1 사이의 수입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CAsyncSocket::OnSend](#onsend)합니다.

##  <a name="sendto"></a>  CAsyncSocket::SendTo

특정 대상에 데이터를 보내도록이 멤버 함수를 호출 합니다.

```
int SendTo(
    const void* lpBuf,
    int nBufLen,
    UINT nHostPort,
    LPCTSTR lpszHostAddress = NULL,
    int nFlags = 0);

int SendTo(
    const void* lpBuf,
    int nBufLen,
    const SOCKADDR* lpSockAddr,
    int nSockAddrLen,
    int nFlags = 0);
```

### <a name="parameters"></a>매개 변수

*lpBuf*<br/>
전송할 데이터가 들어 있는 버퍼입니다.

*nBufLen*<br/>
에 있는 데이터의 길이 *lpBuf* (바이트)에서입니다.

*nHostPort*<br/>
소켓 응용 프로그램을 식별 하는 포트입니다.

*lpszHostAddress*<br/>
이 개체가 연결 되는 소켓의 네트워크 주소: "형식인," 또는 "128.56.22.8" 같은 점으로 구분 된 번호와 같은 컴퓨터 이름입니다.

*nFlags*<br/>
호출 되는 방식을 지정 합니다. 이 함수의 의미 체계 소켓 옵션에 의해 결정 되 고 *nFlags* 매개 변수입니다. 다음 값 중 하나를 결합 하 여 생성 되 고 후자는 C++ **나** 연산자:

- MSG_DONTROUTE 데이터 라우팅 적용 되지 않아야 지정 합니다. Windows 소켓 공급자는이 플래그를 무시 하도록 선택할 수 있습니다.

- MSG_OOB 대역의 데이터 보내기 (SOCK_STREAM에만 해당).

*lpSockAddr*<br/>
에 대 한 포인터를 [SOCKADDR](/windows/desktop/winsock/sockaddr-2) 대상 소켓의 주소를 포함 하는 구조입니다.

*nSockAddrLen*<br/>
주소의 길이 *lpSockAddr* (바이트)에서입니다.

### <a name="return-value"></a>반환 값

오류가 발생 하지 않으면, `SendTo` 전송 되는 문자의 총 수를 반환 합니다. (나타난 수보다 작을 수 있습니다이 *nBufLen*.) 그렇지 않으면 SOCKET_ERROR의 값이 반환 하 고 특정 오류 코드를 호출 하 여 검색할 수 있습니다 [GetLastError](#getlasterror)합니다. 이 멤버 함수에 다음 오류가 적용 됩니다.

- WSANOTINITIALISED는 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하 여 앞에 있어야 합니다.

- WSAENETDOWN The Windows 소켓 구현이 네트워크 하위 시스템 실패 했음을 발견 했습니다.

- 요청된 된 주소 WSAEACCES 브로드캐스트 주소 이지만 적절 한 플래그 설정 되지 않았습니다.

- WSAEINPROGRESS는 차단 하는 Windows 소켓 작업이 진행 중입니다.

- WSAEFAULT 합니다 *lpBuf* 또는 *lpSockAddr* 매개 변수 사용자 주소 공간에 속하지 않는 또는 *lpSockAddr* 인수가 너무 작아서 ( 는크기보다작은[SOCKADDR](/windows/desktop/winsock/sockaddr-2) 구조).

- WSAEINVAL 호스트 이름이 올바르지 않습니다.

- Windows 소켓 구현을 삭제 하므로 WSAENETRESET 연결 다시 설정 해야 합니다.

- 같은 WSAENOBUFS The Windows 소켓 구현을 버퍼 교착 상태를 보고합니다.

- 소켓 아닙니다 WSAENOTCONN 연결 (SOCK_STREAM에만 해당).

- 설명자 WSAENOTSOCK 소켓 아닙니다.

- WSAEOPNOTSUPP MSG_OOB 지정 되었지만 소켓 SOCK_STREAM 유형이 아닙니다.

- 소켓 WSAESHUTDOWN 종료 되었습니다. 호출 하는 것이 불가능 `SendTo` 한 후 소켓 `ShutDown` 를 호출 했습니다 *nHow* 1 또는 2로 설정 합니다.

- 소켓 표시 되어 WSAEWOULDBLOCK 비차단으로 요청 된 작업이 차단 됩니다.

- 소켓 WSAEMSGSIZE SOCK_DGRAM, 형식이 며 데이터 그램 Windows 소켓 구현에서 지원 되는 최대값 보다 큽니다.

- WSAECONNABORTED 가상 회로가 시간 초과 또는 기타 오류로 인해 중단 되었습니다.

- 가상 회로가 WSAECONNRESET 원격 측에 의해 다시 설정 되었습니다.

- 지정된 된 주소 WSAEADDRNOTAVAIL 로컬 컴퓨터에서 사용할 수 없는 경우

- 이 소켓을 사용 하 여 지정된 된 제품군의 WSAEAFNOSUPPORT 주소를 사용할 수 없습니다.

- WSAEDESTADDRREQ는 대상 주소가 필요 합니다.

- WSAENETUNREACH 네트워크에서 연결할 수 없습니다이 호스트에서이 시간입니다.

### <a name="remarks"></a>설명

`SendTo` 데이터 그램 또는 스트림 소켓에서 사용 됩니다 하 고 소켓에 보내는 데이터를 쓸 사용 됩니다. 데이터 그램 소켓에 대 한 주의 해야 하지 하 여 제공 된 기본 서브넷으로 최대 IP 패킷 크기를 초과 하는 `iMaxUdpDg` 요소에는 [WSADATA](/windows/desktop/api/winsock2/ns-winsock2-wsadata) 구조 작성 하 여 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit). 데이터가 너무 길어 기본 프로토콜을 통해 자동으로 전달 하는 경우 오류 WSAEMSGSIZE 반환 되 고 데이터가 전송 됩니다.

성공적으로 완료 된 `SendTo` 성공적으로 전달 된 데이터를 나타내지 않습니다.

`SendTo` 로 식별 되는 특정 소켓에 데이터 그램을 보내려면 SOCK_DGRAM 소켓에만 사용 합니다 *lpSockAddr* 매개 변수입니다.

브로드캐스트는 SOCK_DGRAM만), (on 보낼 주소를 *lpSockAddr* INADDR_BROADCAST (WINSOCK Windows 소켓 헤더 파일에 정의 특수 IP 주소를 사용 하 여 매개 변수를 생성 해야 합니다. H)와 함께 원하는 포트 번호입니다. 또는 경우에는 *lpszHostAddress* 매개 변수가 NULL 이면 브로드캐스트에 대 한 소켓 구성 됩니다. 조각화가 발생할 수 있습니다 크기를 초과 하는 브로드캐스트 데이터 그램을 일반적으로 권장 되지 즉, 데이터 그램 (머리글 제외)의 데이터 부분 512 바이트를 넘지 않아야 합니다.

IPv6 주소를 처리 하려면 [CAsyncSocket::SendToEx](#sendtoex)합니다.

##  <a name="sendtoex"></a>  CAsyncSocket::SendToEx

데이터를 특정 대상 (핸들 IPv6 주소)를 전송 하려면이 멤버 함수를 호출 합니다.

```
int SendToEx(
    const void* lpBuf,
    int nBufLen,
    UINT nHostPort,
    LPCTSTR lpszHostAddress = NULL,
    int nFlags = 0);
```

### <a name="parameters"></a>매개 변수

*lpBuf*<br/>
전송할 데이터가 들어 있는 버퍼입니다.

*nBufLen*<br/>
에 있는 데이터의 길이 *lpBuf* (바이트)에서입니다.

*nHostPort*<br/>
소켓 응용 프로그램을 식별 하는 포트입니다.

*lpszHostAddress*<br/>
이 개체가 연결 되는 소켓의 네트워크 주소: "형식인," 또는 "128.56.22.8" 같은 점으로 구분 된 번호와 같은 컴퓨터 이름입니다.

*nFlags*<br/>
호출 되는 방식을 지정 합니다. 이 함수의 의미 체계 소켓 옵션에 의해 결정 되 고 *nFlags* 매개 변수입니다. 다음 값 중 하나를 결합 하 여 생성 되 고 후자는 C++ **나** 연산자:

- MSG_DONTROUTE 데이터 라우팅 적용 되지 않아야 지정 합니다. Windows 소켓 공급자는이 플래그를 무시 하도록 선택할 수 있습니다.

- MSG_OOB 대역의 데이터 보내기 (SOCK_STREAM에만 해당).

### <a name="return-value"></a>반환 값

오류가 발생 하지 않으면, `SendToEx` 전송 되는 문자의 총 수를 반환 합니다. (나타난 수보다 작을 수 있습니다이 *nBufLen*.) 그렇지 않으면 SOCKET_ERROR의 값이 반환 하 고 특정 오류 코드를 호출 하 여 검색할 수 있습니다 [GetLastError](#getlasterror)합니다. 이 멤버 함수에 다음 오류가 적용 됩니다.

- WSANOTINITIALISED는 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하 여 앞에 있어야 합니다.

- WSAENETDOWN The Windows 소켓 구현이 네트워크 하위 시스템 실패 했음을 발견 했습니다.

- 요청된 된 주소 WSAEACCES 브로드캐스트 주소 이지만 적절 한 플래그 설정 되지 않았습니다.

- WSAEINPROGRESS는 차단 하는 Windows 소켓 작업이 진행 중입니다.

- WSAEFAULT 합니다 *lpBuf* 또는 *lpSockAddr* 매개 변수 사용자 주소 공간에 속하지 않는 또는 *lpSockAddr* 인수가 너무 작아서 ( 는크기보다작은[SOCKADDR](/windows/desktop/winsock/sockaddr-2) 구조).

- WSAEINVAL 호스트 이름이 올바르지 않습니다.

- Windows 소켓 구현을 삭제 하므로 WSAENETRESET 연결 다시 설정 해야 합니다.

- 같은 WSAENOBUFS The Windows 소켓 구현을 버퍼 교착 상태를 보고합니다.

- 소켓 아닙니다 WSAENOTCONN 연결 (SOCK_STREAM에만 해당).

- 설명자 WSAENOTSOCK 소켓 아닙니다.

- WSAEOPNOTSUPP MSG_OOB 지정 되었지만 소켓 SOCK_STREAM 유형이 아닙니다.

- 소켓 WSAESHUTDOWN 종료 되었습니다. 호출 하는 것이 불가능 `SendToEx` 한 후 소켓 `ShutDown` 를 호출 했습니다 *nHow* 1 또는 2로 설정 합니다.

- 소켓 표시 되어 WSAEWOULDBLOCK 비차단으로 요청 된 작업이 차단 됩니다.

- 소켓 WSAEMSGSIZE SOCK_DGRAM, 형식이 며 데이터 그램 Windows 소켓 구현에서 지원 되는 최대값 보다 큽니다.

- WSAECONNABORTED 가상 회로가 시간 초과 또는 기타 오류로 인해 중단 되었습니다.

- 가상 회로가 WSAECONNRESET 원격 측에 의해 다시 설정 되었습니다.

- 지정된 된 주소 WSAEADDRNOTAVAIL 로컬 컴퓨터에서 사용할 수 없는 경우

- 이 소켓을 사용 하 여 지정된 된 제품군의 WSAEAFNOSUPPORT 주소를 사용할 수 없습니다.

- WSAEDESTADDRREQ는 대상 주소가 필요 합니다.

- WSAENETUNREACH 네트워크에서 연결할 수 없습니다이 호스트에서이 시간입니다.

### <a name="remarks"></a>설명

이 메서드는 동일 [CAsyncSocket::SendTo](#sendto) IPv6 처리 한다는 점을 제외 하면 주소도으로 이전 프로토콜입니다.

`SendToEx` 데이터 그램 또는 스트림 소켓에서 사용 됩니다 하 고 소켓에 보내는 데이터를 쓸 사용 됩니다. 데이터 그램 소켓에 대 한 주의 해야 하지 하 여 제공 된 기본 서브넷으로 최대 IP 패킷 크기를 초과 하는 `iMaxUdpDg` 요소에는 [WSADATA](/windows/desktop/api/winsock2/ns-winsock2-wsadata) 구조 작성 하 여 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit). 데이터가 너무 길어 기본 프로토콜을 통해 자동으로 전달 하는 경우 오류 WSAEMSGSIZE 반환 되 고 데이터가 전송 됩니다.

성공적으로 완료 된 `SendToEx` 성공적으로 전달 된 데이터를 나타내지 않습니다.

`SendToEx` 로 식별 되는 특정 소켓에 데이터 그램을 보내려면 SOCK_DGRAM 소켓에만 사용 합니다 *lpSockAddr* 매개 변수입니다.

브로드캐스트는 SOCK_DGRAM만), (on 보낼 주소를 *lpSockAddr* INADDR_BROADCAST (WINSOCK Windows 소켓 헤더 파일에 정의 특수 IP 주소를 사용 하 여 매개 변수를 생성 해야 합니다. H)와 함께 원하는 포트 번호입니다. 또는 경우에는 *lpszHostAddress* 매개 변수가 NULL 이면 브로드캐스트에 대 한 소켓 구성 됩니다. 조각화가 발생할 수 있습니다 크기를 초과 하는 브로드캐스트 데이터 그램을 일반적으로 권장 되지 즉, 데이터 그램 (머리글 제외)의 데이터 부분 512 바이트를 넘지 않아야 합니다.

##  <a name="setsockopt"></a>  CAsyncSocket::SetSockOpt

소켓 옵션을 설정 하려면이 멤버 함수를 호출 합니다.

```
BOOL SetSockOpt(
    int nOptionName,
    const void* lpOptionValue,
    int nOptionLen,
    int nLevel = SOL_SOCKET);
```

### <a name="parameters"></a>매개 변수

*nOptionName*<br/>
설정할 값이 있는 소켓 옵션입니다.

*lpOptionValue*<br/>
요청된 옵션에 대 한 값을 제공 하는 데는 버퍼에 대 한 포인터입니다.

*nOptionLen*<br/>
크기를 *lpOptionValue* 바이트 버퍼입니다.

*nLevel*<br/>
입니다 옵션 정의 되어 있으면 수준 만 지원 되는 수준은 SOL_SOCKET 및 IPPROTO_TCP 합니다.

### <a name="return-value"></a>반환 값

함수에 성공 하면 0이 아닌 값 0이 고 특정 오류 코드를 호출 하 여 검색할 수 있습니다이 고, 그렇지 [GetLastError](#getlasterror)합니다. 이 멤버 함수에 다음 오류가 적용 됩니다.

- WSANOTINITIALISED는 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하 여 앞에 있어야 합니다.

- WSAENETDOWN The Windows 소켓 구현이 네트워크 하위 시스템 실패 했음을 발견 했습니다.

- WSAEFAULT *lpOptionValue* 프로세스 주소 공간의 유효한 부분에 아닙니다.

- WSAEINPROGRESS는 차단 하는 Windows 소켓 작업이 진행 중입니다.

- WSAEINVAL *nLevel* 유효 하지 않은에서 정보나 *lpOptionValue* 올바르지 않습니다.

- SO_KEEPALIVE 설정 되 면 WSAENETRESET 연결 시간이 초과 되었습니다.

- WSAENOPROTOOPT 옵션을 알 수 없거나 지원 되지 않는 경우 특히 SO_BROADCAST SO_DONTLINGER, SO_KEEPALIVE, SO_LINGER, 및 SO_OOBINLINE 하는 동안 SOCK_STREAM sockets SOCK_DGRAM 형식의 지원 되지 않습니다 형식의 소켓에서 지원 되지 않습니다.

- WSAENOTCONN 연결 SO_KEEPALIVE 설정 된 경우 다시 설정 되었습니다.

- 설명자 WSAENOTSOCK 소켓 아닙니다.

### <a name="remarks"></a>설명

`SetSockOpt` 모든 상태에서 모든 형식의 소켓을 사용 하 여 연결 된 소켓 옵션의 현재 값을 설정 합니다. 옵션 여러 프로토콜 수준에서 존재할 수 있지만이 사양은 위 "소켓" 수준에서 존재 하는 옵션을 정의 합니다. 옵션 브로드캐스트 메시지 소켓에 전송할 수 있습니다 하 고 등 일반 데이터 스트림에서 긴급된 데이터가 수신 되는 여부와 같은 소켓 작업을 영향을 줍니다.

소켓 옵션는 다음과 같은 두 종류가 있습니다. 기능 또는 동작을 활성화 또는 비활성화 하는 부울 옵션 및는 정수 값 또는 구조를 필요로 하는 옵션입니다. 부울 옵션을 사용할 수 있도록 *lpOptionValue* 0이 아닌 정수를 가리킵니다. 옵션을 사용 하지 않으려면 *lpOptionValue* 0과 같은 정수를 가리킵니다. *nOptionLen* 같아야 `sizeof(BOOL)` 부울 옵션에 대 한 합니다. 다른 옵션에 대 한 *lpOptionValue* 정수 또는 옵션을 원하는 값을 포함 하는 구조를 가리키는 하 고 *nOptionLen* 클래스 또는 구조체는 정수입니다.

SO_LINGER 소켓에서 대기 하는 보내지 않은 데이터가 때 수행할 동작을 제어 및 `Close` 함수가 호출 되어 소켓을 닫습니다.

기본적으로 소켓을 바인딩할 수 없습니다 (참조 [바인딩할](#bind)) 이미 사용 되는 로컬 주소입니다. 그러나 경우에 따라는 것이 바람직합니다이 방식으로 주소를 "다시"입니다. 모든 연결은 로컬 및 원격 주소의 조합으로 고유 하 게 식별 됩니다, 이므로 원격 주소는 다른으로 동일한 로컬 주소에 바인딩된 두 개의 소켓 있는 문제가 없습니다.

Windows 소켓 구현에 알림을 보내야 하는 `Bind` 소켓에 대 한 호출이 다른 소켓에서 사용 하 여 이미 원하는 주소 기 때문에 허용 되지 해야, 응용 프로그램 실행 하기 전에 소켓 SO_REUSEADDR 소켓 옵션을 설정 해야 합니다 `Bind` 호출 합니다. 옵션의 경우에만 해석 됩니다는 `Bind` 호출: 따라서 필요 없는 (무해) 하지만 기존 주소를 바인딩할 필요가 소켓 옵션을 설정 하 고 하거나 다시 설정 후 옵션을는 `Bind` 호출에 이 또는 다른 소켓에 아무런 영향이 없습니다.

응용 프로그램은 Windows 소켓 구현이 SO_KEEPALIVE 소켓 옵션을 설정 하 여 전송 제어 프로토콜 (TCP) 연결에서 "유지" 패킷 사용할 수 있도록 요청할 수 있습니다. Windows 소켓 구현을 연결 유지 사용을 지원 하지 않아도:이 경우 정확한 의미 체계 구현 별 되지만의 RFC 1122 4.2.3.6를 준수 해야 합니다. "인터넷 호스트에 대 한 요구 사항-통신 계층입니다." 연결 결과로 삭제 되 면 "연결 유지"의 오류 코드 WSAENETRESET 진행 중인 모든 호출에 소켓에서 돌아가고 WSAENOTCONN를 사용 하 여 모든 후속 호출은 실패 합니다.

TCP_NODELAY 옵션 Nagle 알고리즘을 사용 하지 않도록 설정 합니다. Nagle 알고리즘은 큰 패킷을 보낼 수까지 어댑터로 송신 데이터를 버퍼링 하 여 호스트에서 전송 하는 작은 패킷 수를 줄이는 데 사용 됩니다. 그러나 일부 응용 프로그램에 대 한이 알고리즘 성능 방해할 수 있으며 TCP_NODELAY 해제 데 사용할 수 있습니다. 아닌 경우의 영향 하므로 잘 알려져 있으며 원하는 TCP_NODELAY 설정 네트워크 성능에 크게 저하 될 수 있으므로 응용 프로그램 작성자 TCP_NODELAY를 설정 하지 않아야 합니다. TCP_NODELAY은 경우에 지원 되는 수준 IPPROTO_TCP;를 사용 하는 소켓 옵션 다른 모든 옵션에는 SOL_SOCKET 수준을 사용합니다.

Windows 소켓 공급의 일부 구현 SO_DEBUG 옵션은 응용 프로그램으로 설정 하는 경우 디버그 정보를 출력 합니다.

다음 옵션을 지 `SetSockOpt`합니다. 형식으로 주소가 지정 된 데이터의 형식을 식별 *lpOptionValue*합니다.

|값|형식|의미|
|-----------|----------|-------------|
|SO_BROADCAST|BOOL|소켓의 브로드캐스트 메시지의 전송을 허용 합니다.|
|SO_DEBUG|BOOL|디버깅 정보를 기록합니다.|
|SO_DONTLINGER|BOOL|차단 되지 않도록 `Close` 보내지 않은 데이터를 보내도록 대기 합니다. 이 옵션을 설정 하는 것으로 SO_LINGER `l_onoff` 0으로 설정 합니다.|
|SO_DONTROUTE|BOOL|라우팅 하지 않습니다: 인터페이스에 직접 전송 합니다.|
|SO_KEEPALIVE|BOOL|연결 유지 메시지를 보냅니다.|
|SO_LINGER|`struct LINGER`|가 지연 `Close` 데이터가 있는 보내지 않은 경우.|
|SO_OOBINLINE|BOOL|정상 데이터 스트림에서 대역의 데이터를 수신 합니다.|
|SO_RCVBUF|**int**|수신 버퍼 크기를 지정 합니다.|
|SO_REUSEADDR|BOOL|소켓이 이미 사용 되는 주소에 바인딩될 수 있습니다. (참조 [바인딩할](#bind).)|
|SO_SNDBUF|**int**|전송에 대 한 버퍼 크기를 지정 합니다.|
|TCP_NODELAY|BOOL|보내기 통합을 위해 Nagle 알고리즘을 비활성화합니다.|

Berkeley 소프트웨어 배포 (BSD) 옵션에 대 한 지원 되지 않습니다 `SetSockOpt` 됩니다.

|값|형식|의미|
|-----------|----------|-------------|
|SO_ACCEPTCONN|BOOL|소켓이 수신 중입니다.|
|SO_ERROR|**int**|오류 상태를 가져오고 지웁니다.|
|SO_RCVLOWAT|**int**|하위 워터 마크를 수신 합니다.|
|SO_RCVTIMEO|**int**|수신 시간 제한|
|SO_SNDLOWAT|**int**|하위 워터 마크를 보냅니다.|
|SO_SNDTIMEO|**int**|제한 시간을 보냅니다.|
|SO_TYPE|**int**|소켓의 형식입니다.|
|IP_OPTIONS||IP 헤더에 옵션 필드를 설정 합니다.|

##  <a name="shutdown"></a>  CAsyncSocket::ShutDown

호출을 사용 하지 않도록 설정 하려면이 멤버 함수를 보냅니다. 받는 소켓에 또는 둘 다.

```
BOOL ShutDown(int nHow = sends);
```

### <a name="parameters"></a>매개 변수

*nHow*<br/>
작업의 종류를 설명 하는 플래그는 더 이상 허용은 다음 열거형된 값을 사용 하 여:

- **receives = 0**

- **sends = 1**

- **both = 2**

### <a name="return-value"></a>반환 값

함수에 성공 하면 0이 아닌 값 0이 고 특정 오류 코드를 호출 하 여 검색할 수 있습니다이 고, 그렇지 [GetLastError](#getlasterror)합니다. 이 멤버 함수에 다음 오류가 적용 됩니다.

- WSANOTINITIALISED는 성공적인 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) 이 API를 사용 하 여 앞에 있어야 합니다.

- WSAENETDOWN The Windows 소켓 구현이 네트워크 하위 시스템 실패 했음을 발견 했습니다.

- WSAEINVAL *nHow* 올바르지 않습니다.

- WSAEINPROGRESS는 차단 하는 Windows 소켓 작업이 진행 중입니다.

- 소켓 아닙니다 WSAENOTCONN 연결 (SOCK_STREAM에만 해당).

- 설명자 WSAENOTSOCK 소켓 아닙니다.

### <a name="remarks"></a>설명

`ShutDown` 수신, 전송 또는 둘 다 사용 하지 않도록 설정 하는 소켓의 모든 형식에 사용 됩니다. 하는 경우 *nHow* 가 0 이면에서 후속 받는 소켓을 사용할 수 없습니다. 하위 프로토콜 계층에서 효과가 없습니다.

에 대 한 프로토콜 TCP (Transmission Control), TCP 창 변경 되지 않으며 들어오는 데이터가 창 가득 찰 때까지 (승인 되지) 이지만 허용 합니다. 에 대 한 사용자 데이터 그램 프로토콜 (UDP), 들어오는 데이터 그램은 수락 및 대기 합니다. 없는 경우 ICMP 오류 패킷을 생성 됩니다. 하는 경우 *nHow* 는 1, 후속 보내기 허용 되지 않습니다. TCP 소켓을 FIN 전송 됩니다. 설정 *nHow* 받고 위에서 설명한 대로 2로 모두 사용 하지 않도록 설정 합니다.

사실은 `ShutDown` 않습니다 하지 닫고 소켓 및 소켓에 연결 된 리소스를 해제 되지 것입니다까지 `Close` 라고 합니다. 응용 프로그램 종료 한 후 소켓을 재사용 하에 의존 하지 않아야 합니다. 특히 Windows 소켓 구현이 필요가 없습니다 사용 하 여 `Connect` 이러한 소켓입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [CAsyncSocket::OnReceive](#onreceive)합니다.

##  <a name="socket"></a>  CASyncSocket::Socket

소켓 핸들을 할당합니다.

```
BOOL Socket(
    int nSocketType = SOCK_STREAM,
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE,
    int nProtocolType = 0,
    int nAddressFormat = PF_INET);
```

### <a name="parameters"></a>매개 변수

*nSocketType*<br/>
지정 `SOCK_STREAM` 또는 `SOCK_DGRAM`합니다.

*lEvent*<br/>
응용 프로그램에는 관여 하는 네트워크 이벤트의 조합을 지정 하는 비트 마스크입니다.

- `FD_READ`: 읽기에 대 한 준비 상태에 대 한 알림을 수신 하려고 합니다.

- `FD_WRITE`: 작성 하기 위한 준비에 대 한 알림을 수신 하려고 합니다.

- `FD_OOB`: 대역의 데이터에 대 한 알림을 수신 하려고 합니다.

- `FD_ACCEPT`: 들어오는 연결에 대 한 알림을 수신 하려고 합니다.

- `FD_CONNECT`: 완료 된 연결에 대 한 알림을 수신 하려고 합니다.

- `FD_CLOSE`: 소켓 닫기를 처리 알림을 받도록 하려고 합니다.

*nProtocolType*<br/>
표시 된 주소 패밀리에 관련 된 소켓을 사용 하 여 사용할 프로토콜입니다.

*nAddressFormat*<br/>
주소 패밀리 사양입니다.

### <a name="return-value"></a>반환 값

성공하면 `TRUE`를 반환하고 실패하면 `FALSE`를 반환합니다.

### <a name="remarks"></a>설명

이 메서드는 소켓 핸들을 할당합니다. 호출 하지 않습니다 [CAsyncSocket::Bind](#bind) 소켓을 바인딩하지 지정된 된 주소에 호출 해야 하므로 `Bind` 나중에 바인딩할 소켓 주소를 지정된 합니다. 사용할 수 있습니다 [CAsyncSocket::SetSockOpt](#setsockopt) 연결 되기 전에 소켓 옵션을 설정 합니다.

## <a name="see-also"></a>참고자료

[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CSocket 클래스](../../mfc/reference/csocket-class.md)<br/>
[CSocketFile 클래스](../../mfc/reference/csocketfile-class.md)
