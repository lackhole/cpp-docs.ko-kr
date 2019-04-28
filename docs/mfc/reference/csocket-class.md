---
title: CSocket 클래스
ms.date: 11/04/2016
f1_keywords:
- CSocket
- AFXSOCK/CSocket
- AFXSOCK/CSocket::CSocket
- AFXSOCK/CSocket::Attach
- AFXSOCK/CSocket::CancelBlockingCall
- AFXSOCK/CSocket::Create
- AFXSOCK/CSocket::FromHandle
- AFXSOCK/CSocket::IsBlocking
- AFXSOCK/CSocket::OnMessagePending
helpviewer_keywords:
- CSocket [MFC], CSocket
- CSocket [MFC], Attach
- CSocket [MFC], CancelBlockingCall
- CSocket [MFC], Create
- CSocket [MFC], FromHandle
- CSocket [MFC], IsBlocking
- CSocket [MFC], OnMessagePending
ms.assetid: 7f23c081-d24d-42e3-b511-8053ca53d729
ms.openlocfilehash: a861e557b7368d13d615aaf796faded93c72b040
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62323962"
---
# <a name="csocket-class"></a>CSocket 클래스

파생 `CAsyncSocket`, Windows 소켓 API의 캡슐화를 상속 하 고 보다 더 높은 수준의 추상화를 나타냅니다는 `CAsyncSocket` 개체입니다.

## <a name="syntax"></a>구문

```
class CSocket : public CAsyncSocket
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CSocket::CSocket](#csocket)|`CSocket` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CSocket::Attach](#attach)|연결에 대 한 소켓 핸들을 `CSocket` 개체입니다.|
|[CSocket::CancelBlockingCall](#cancelblockingcall)|현재 진행 중인 차단 호출을 취소 합니다.|
|[CSocket::Create](#create)|소켓을 만듭니다.|
|[CSocket::FromHandle](#fromhandle)|에 대 한 포인터를 반환 합니다.는 `CSocket` 소켓 핸들을 지정 된 개체입니다.|
|[CSocket::IsBlocking](#isblocking)|차단 호출 진행에서 중인지 여부를 결정 합니다.|

### <a name="protected-methods"></a>Protected 메서드

|이름|설명|
|----------|-----------------|
|[CSocket::OnMessagePending](#onmessagepending)|차단 호출이 완료 되기를 기다리는 동안 보류 중인 메시지는 처리 하기 위해 호출 합니다.|

## <a name="remarks"></a>설명

`CSocket` 클래스를 사용 하 여 작동 `CSocketFile` 및 `CArchive` 보내고 받는 데이터를 관리할 수 있습니다.

A `CSocket` 개체가 제공 차단의 동기 작업 하는 데 필수적인 `CArchive`합니다. 와 같은 함수를 차단 `Receive`, `Send`, `ReceiveFrom`, `SendTo`, 및 `Accept` (에서 상속 되는 모든 `CAsyncSocket`)를 반환 하지는 `WSAEWOULDBLOCK` 에 오류가 있습니다. `CSocket`. 대신 이러한 함수는 작업이 완료 될 때까지 기다립니다. 경우 원래 호출은 WSAEINTR 오류로 종료 됩니다는 또한 `CancelBlockingCall` 이러한 함수 중 하나를 차단 하는 동안 호출 됩니다.

사용 하는 `CSocket` 개체를 생성자 호출 호출 `Create` (형식 소켓)의 기본 소켓 핸들을 만드는 합니다. 기본 매개 변수 `Create` 스트림 소켓, 만들기와 소켓을 사용 하지 않는 경우에 `CArchive` 개체 대신 데이터 그램 소켓 만들거나 서버 소켓 만들기에 특정 포트에 바인딩 매개 변수를 지정할 수 있습니다. 사용 하 여 클라이언트 소켓을 연결할 `Connect` 클라이언트 쪽 및 `Accept` 서버 쪽에서 합니다. 만든를 `CSocketFile` 개체와 연결 합니다 `CSocket` 개체는 `CSocketFile` 생성자입니다. 다음으로 만듭니다는 `CArchive` 필요에 따라 데이터를 수신 하는 것에 대 한 전송에 대 한 개체와 연결 하 여 사용 하 여 합니다 `CSocketFile` 개체는 `CArchive` 생성자입니다. 통신 완료 되 면 제거 합니다 `CArchive`, `CSocketFile`, 및 `CSocket` 개체입니다. 소켓 데이터 형식은 문서에 설명 되어 [Windows 소켓: 백그라운드](../../mfc/windows-sockets-background.md)합니다.

사용 하는 경우 `CArchive` 사용 하 여 `CSocketFile` 및 `CSocket`, 상황이 발생할 수 있는 `CSocket::Receive` 루프로 실행 (여 `PumpMessages(FD_READ)`) 바이트 요청한 금액에 대 한 대기 합니다. 이 작업할 알림 당 하나만 recv 호출을 허용 하는 Windows 소켓 않으므로 하지만 `CSocketFile` 및 `CSocket` 작업할 당 여러 recv 호출을 허용 합니다. 읽을 데이터가 없는 경우에 작업할을 받게 되 면 응용 프로그램이 중단 됩니다. 얻지 다른 작업할 경우 응용 프로그램이 소켓을 통해 통신을 중지 합니다.

다음과 같이이 문제를 해결할 수 있습니다. 에 `OnReceive` 소켓 클래스, 호출 메서드의 `CAsyncSocket::IOCtl(FIONREAD, ...)` 호출 하기 전에 `Serialize` 소켓에서 읽을 수는 예상 되는 데이터는 하나의 TCP 패킷 (최대 전송 단위 네트워크 중간 크기를 초과 하는 경우 메시지 클래스의 메서드 일반적으로 1096 바이트 이상). 사용 가능한 데이터의 크기 필요한 것 보다 적은 경우 모든 데이터를 받고 그런 후에 읽기 작업을 시작 될 때까지 기다립니다.

다음 예에서 `m_dwExpected` 대략적인 받으려면 사용자가 기대 하는 바이트 수입니다. 이 다른 곳에서 선언한 코드 간주 됩니다.

[!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocket-class_1.cpp)]

> [!NOTE]
>  정적으로 연결 된 MFC 응용 프로그램에서 보조 스레드에서 MFC 소켓을 사용 하는 경우 호출 해야 `AfxSocketInit` 소켓을 사용 하 여 소켓 라이브러리를 초기화 하는 각 스레드에서 합니다. 기본적으로 `AfxSocketInit` 기본 스레드에서만에서 호출 됩니다.

자세한 내용은 [MFC의 Windows 소켓](../../mfc/windows-sockets-in-mfc.md), [Windows 소켓: 보관 파일을 사용 하 여 소켓을 사용 하 여](../../mfc/windows-sockets-using-sockets-with-archives.md), [Windows 소켓: 보관이 포함 된 소켓의 작동 방식을](../../mfc/windows-sockets-how-sockets-with-archives-work.md), [Windows 소켓: 작업 시퀀스](../../mfc/windows-sockets-sequence-of-operations.md), [Windows 소켓: 아카이브를 사용 하는 소켓의 예](../../mfc/windows-sockets-example-of-sockets-using-archives.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CAsyncSocket](../../mfc/reference/casyncsocket-class.md)

`CSocket`

## <a name="requirements"></a>요구 사항

**헤더:** afxsock.h

##  <a name="attach"></a>  CSocket::Attach

연결 하려면이 멤버 함수를 호출 합니다 `hSocket` 에 대 한 핸들을 `CSocket` 개체입니다.

```
BOOL Attach(SOCKET hSocket);
```

### <a name="parameters"></a>매개 변수

*hSocket*<br/>
소켓에 대 한 핸들을 포함합니다.

### <a name="return-value"></a>반환 값

함수가 성공하는 경우 0이 아닙니다.

### <a name="remarks"></a>설명

SOCKET 핸들 개체에 저장 됩니다 [m_hSocket](../../mfc/reference/casyncsocket-class.md#m_hsocket) 데이터 멤버입니다.

자세한 내용은 참조 하세요. [Windows 소켓: 보관 파일을 사용 하 여 소켓을 사용 하 여](../../mfc/windows-sockets-using-sockets-with-archives.md)입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCSocketThread#1](../../mfc/reference/codesnippet/cpp/csocket-class_2.h)]

[!code-cpp[NVC_MFCSocketThread#2](../../mfc/reference/codesnippet/cpp/csocket-class_3.cpp)]

[!code-cpp[NVC_MFCSocketThread#3](../../mfc/reference/codesnippet/cpp/csocket-class_4.cpp)]

##  <a name="cancelblockingcall"></a>  CSocket::CancelBlockingCall

현재 진행 중인 차단 호출을 취소 하려면이 멤버 함수를 호출 합니다.

```
void CancelBlockingCall();
```

### <a name="remarks"></a>설명

이 함수는이 소켓에 대 한 모든 미해결 차단 작업을 취소합니다. 원래 차단 호출 WSAEINTR 오류가 발생 하 여 가능한 한 빨리 종료 됩니다.

차단 하는 경우 `Connect` 작업 Windows 소켓 구현이 끝납니다 차단 호출 가능 하지만 못할 연결 완료 (및 다시 설정 된) 될 때까지 해제 될 소켓 리소스에 대 한 즉시 또는 시간이 초과 되었습니다. 이 응용 프로그램에는 즉시 새 소켓 (사용 가능한 소켓 없는 경우), 열 또는 동일한 피어에 연결 하려고 하는 경우에 뚜렷하게 나타날 수 있습니다.

이외의 다른 모든 작업을 취소 `Accept` 확정 되지 않은 상태에서 소켓을 그대로 둘 수 있습니다. 소켓에서 차단 작업을 취소 하는 응용 프로그램, 응용 프로그램 소켓에서 수행할 수 있으므로 신뢰할 수 있는 유일한 작업 인지에 대 한 호출 `Close`이지만 다른 작업은 일부 Windows 소켓 구현에서 작동 될 수 있습니다. 응용 프로그램에 대 한 최대 이식성을 원하는 경우에 작업을 취소 한 후 종속 하지 않도록 주의 해야 합니다.

자세한 내용은 참조 하세요. [Windows 소켓: 보관 파일을 사용 하 여 소켓을 사용 하 여](../../mfc/windows-sockets-using-sockets-with-archives.md)입니다.

##  <a name="create"></a>  CSocket::Create

호출 된 **만들기** Windows 소켓을 만들고 연결 하는 소켓 개체를 생성 한 후 멤버 함수입니다.

```
BOOL Create(
    UINT nSocketPort = 0,
    int nSocketType = SOCK_STREAM,
    LPCTSTR lpszSocketAddress = NULL);
```

### <a name="parameters"></a>매개 변수

*nSocketPort*<br/>
MFC 포트를 선택 하려는 경우, 소켓 또는 0을 사용 하 여 사용할 특정 포트입니다.

*nSocketType*<br/>
SOCK_STREAM 또는 SOCK_DGRAM 합니다.

*lpszSocketAddress*<br/>
연결된 된 소켓 "128.56.22.8" 같은 점으로 구분 된 숫자의 네트워크 주소를 포함 하는 문자열에 대 한 포인터입니다. 이 매개 변수를 나타내는 문자열을 NULL이 전달 된 `CSocket` 인스턴스는 모든 네트워크 인터페이스에서 클라이언트 활동에 대 한 수신 대기 해야 합니다.

### <a name="return-value"></a>반환 값

함수에 성공 하면 0이 아닌 값 0이 고 특정 오류 코드를 호출 하 여 검색할 수 있습니다이 고, 그렇지 `GetLastError`합니다.

### <a name="remarks"></a>설명

`Create` 그런 다음 호출 `Bind` 소켓 지정 된 주소로 바인딩할 합니다. 다음 소켓 형식이 지원 됩니다.

- SOCK_STREAM 시퀀싱, 신뢰할 수 있는 양방향 연결 기반의 바이트 스트림을 제공 합니다. 인터넷 주소 제품군에 대 한 프로토콜 TCP (Transmission Control)를 사용합니다.

- 고정 된 최대 길이 (대개 작음)의 연결 없는, 신뢰할 수 없는 버퍼 SOCK_DGRAM 지원 데이터 그램입니다. 인터넷 주소 제품군에 대 한 사용자 데이터 그램 프로토콜 (UDP)을 사용합니다. 이 옵션을 사용 하려면 사용 하면 안 된 소켓을 `CArchive` 개체입니다.

    > [!NOTE]
    >  합니다 `Accept` 멤버 함수는 비어 있는 새에 대 한 참조 `CSocket` 매개 변수로 개체입니다. 호출 하기 전에이 개체를 생성 해야 `Accept`합니다. 염두에이 소켓 개체가 범위를 연결 닫기 이동 하는 경우. 호출 하지 마십시오 `Create` 이 새 소켓 개체에 대 한 합니다.

스트림 및 데이터 그램 소켓에 대 한 자세한 내용은 문서를 참조 하세요. [Windows 소켓: 백그라운드](../../mfc/windows-sockets-background.md), [Windows 소켓: 포트 및 소켓 주소](../../mfc/windows-sockets-ports-and-socket-addresses.md), 및 [Windows 소켓: 보관 파일을 사용 하 여 소켓을 사용 하 여](../../mfc/windows-sockets-using-sockets-with-archives.md)입니다.

##  <a name="csocket"></a>  CSocket::CSocket

`CSocket` 개체를 생성합니다.

```
CSocket();
```

### <a name="remarks"></a>설명

생성 후에 호출 해야 합니다는 `Create` 멤버 함수입니다.

자세한 내용은 참조 하세요. [Windows 소켓: 보관 파일을 사용 하 여 소켓을 사용 하 여](../../mfc/windows-sockets-using-sockets-with-archives.md)입니다.

##  <a name="fromhandle"></a>  CSocket::FromHandle

에 대 한 포인터를 반환 합니다.는 `CSocket` 개체입니다.

```
static CSocket* PASCAL FromHandle(SOCKET hSocket);
```

### <a name="parameters"></a>매개 변수

*hSocket*<br/>
소켓에 대 한 핸들을 포함합니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 `CSocket` 개체 이거나 없는 경우 NULL 없습니다 `CSocket` 개체에 연결 *hSocket*합니다.

### <a name="remarks"></a>설명

경우 소켓 핸들을 지정 하는 경우는 `CSocket` 개체가 핸들에 연결 되지 않은, 멤버 함수는 NULL을 반환 하 고 임시 개체를 만들지 않습니다.

자세한 내용은 참조 하세요. [Windows 소켓: 보관 파일을 사용 하 여 소켓을 사용 하 여](../../mfc/windows-sockets-using-sockets-with-archives.md)입니다.

##  <a name="isblocking"></a>  CSocket::IsBlocking

차단 호출 진행에서 중인지 확인 하려면이 멤버 함수를 호출 합니다.

```
BOOL IsBlocking();
```

### <a name="return-value"></a>반환 값

소켓; 차단 하는 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

자세한 내용은 참조 하세요. [Windows 소켓: 보관 파일을 사용 하 여 소켓을 사용 하 여](../../mfc/windows-sockets-using-sockets-with-archives.md)입니다.

##  <a name="onmessagepending"></a>  CSocket::OnMessagePending

Windows에서 특정 메시지를 확인 하면 소켓에 응답할 수를이 멤버 함수를 재정의 합니다.

```
virtual BOOL OnMessagePending();
```

### <a name="return-value"></a>반환 값

메시지가 처리 된 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 고급 재정의할 수 있습니다.

프레임 워크 호출 `OnMessagePending` 소켓은 응용 프로그램에 관심 있는 메시지를 처리 하는 기회를 제공 하려면 Windows 메시지를 펌프 하는 동안. 사용 하는 방법의 예제를 보려면 `OnMessagePending`, 문서를 참고 [Windows 소켓: 소켓 클래스에서 파생](../../mfc/windows-sockets-deriving-from-socket-classes.md)합니다.

자세한 내용은 참조 하세요. [Windows 소켓: 보관 파일을 사용 하 여 소켓을 사용 하 여](../../mfc/windows-sockets-using-sockets-with-archives.md)입니다.

## <a name="see-also"></a>참고자료

[CAsyncSocket 클래스](../../mfc/reference/casyncsocket-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CAsyncSocket 클래스](../../mfc/reference/casyncsocket-class.md)<br/>
[CSocketFile 클래스](../../mfc/reference/csocketfile-class.md)
