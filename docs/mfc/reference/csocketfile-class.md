---
title: CSocketFile 클래스
ms.date: 11/04/2016
f1_keywords:
- CSocketFile
- AFXSOCK/CSocketFile
- AFXSOCK/CSocketFile::CSocketFile
helpviewer_keywords:
- CSocketFile [MFC], CSocketFile
ms.assetid: 7924c098-5f72-40d6-989d-42800a47958f
ms.openlocfilehash: f3fa73320ae34283b0cdac559111a53a879c031c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62324053"
---
# <a name="csocketfile-class"></a>CSocketFile 클래스

Windows 소켓을 통해 네트워크에서 데이터를 보내고 받는 데 사용되는 `CFile` 개체입니다.

## <a name="syntax"></a>구문

```
class CSocketFile : public CFile
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CSocketFile::CSocketFile](#csocketfile)|`CSocketFile` 개체를 생성합니다.|

## <a name="remarks"></a>설명

연결할 수 있습니다 합니다 `CSocketFile` 개체는 `CSocket` 이 목적을 위해 개체입니다. 수 있습니다 하 고 일반적으로 연결을 수행 합니다 `CSocketFile` 개체를 `CArchive` MFC serialization을 사용 하 여 데이터 보내기 및 받기 쉬운 개체입니다.

(송신) 데이터를 serialize 하려면 삽입 하 고 호출 하는 보관 `CSocketFile` 데이터를 기록 하는 멤버 함수는 `CSocket` 개체입니다. Deserialize 하는 데 (수신) 보관 파일에서 추출 하는 데이터입니다. 이 인해 호출에 보관 `CSocketFile` 에서 데이터를 읽을 멤버 함수는 `CSocket` 개체입니다.

> [!TIP]
>  사용 하는 것 외에도 `CSocketFile` 여기에 설명 된 대로 사용할 수 있습니다 독립 실행형 파일 개체로 수행할 수 있는 것 처럼 `CFile`, 해당 기본 클래스입니다. 사용할 수도 있습니다 `CSocketFile` MFC serialization 보관 기반 함수를 사용 하 여 합니다. 때문에 `CSocketFile` 의 일부를 지원 하지 `CFile`의 기능을 몇 가지 기본 MFC 직렬화 함수와 호환 되지 않습니다. `CSocketFile`합니다. 이 특히의 `CEditView` 클래스입니다. Serialize 하지 않아야 `CEditView` 를 통해 데이터를 `CArchive` 개체에 연결을 `CSocketFile` 사용 하 여 개체 `CEditView::SerializeRaw`; 사용 `CEditView::Serialize` 대신 합니다. 합니다 `SerializeRaw` 함수에서는 파일 개체와 같은 함수를 `Seek`는 `CSocketFile` 없습니다.

사용 하는 경우 `CArchive` 사용 하 여 `CSocketFile` 및 `CSocket`, 상황이 발생할 수 있는 `CSocket::Receive` 루프로 실행 (여 `PumpMessages(FD_READ)`) 바이트 요청한 금액에 대 한 대기 합니다. 이 작업할 알림 당 하나만 recv 호출을 허용 하는 Windows 소켓 않으므로 하지만 `CSocketFile` 및 `CSocket` 작업할 당 여러 recv 호출을 허용 합니다. 읽을 데이터가 없는 경우에 작업할을 받게 되 면 응용 프로그램이 중단 됩니다. 얻지 다른 작업할 경우 응용 프로그램이 소켓을 통해 통신을 중지 합니다.

다음과 같이이 문제를 해결할 수 있습니다. 에 `OnReceive` 소켓 클래스, 호출 메서드의 `CAsyncSocket::IOCtl(FIONREAD, ...)` 호출 하기 전에 `Serialize` 소켓에서 읽을 수는 예상 되는 데이터는 하나의 TCP 패킷 (최대 전송 단위 네트워크 중간 크기를 초과 하는 경우 메시지 클래스의 메서드 일반적으로 1096 바이트 이상). 사용 가능한 데이터의 크기 필요한 것 보다 적은 경우 모든 데이터를 받고 그런 후에 읽기 작업을 시작 될 때까지 기다립니다.

다음 예에서 `m_dwExpected` 대략적인 받으려면 사용자가 기대 하는 바이트 수입니다. 이 다른 곳에서 선언한 코드 간주 됩니다.

[!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocketfile-class_1.cpp)]

자세한 내용은 [MFC의 Windows 소켓](../../mfc/windows-sockets-in-mfc.md), [Windows 소켓: 보관 파일을 사용 하 여 소켓을 사용 하 여](../../mfc/windows-sockets-using-sockets-with-archives.md), 뿐만 [Windows 소켓 2 API](/windows/desktop/WinSock/windows-sockets-start-page-2)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

`CSocketFile`

## <a name="requirements"></a>요구 사항

**헤더:** afxsock.h

##  <a name="csocketfile"></a>  CSocketFile::CSocketFile

`CSocketFile` 개체를 생성합니다.

```
explicit CSocketFile(
    CSocket* pSocket,
    BOOL bArchiveCompatible = TRUE);
```

### <a name="parameters"></a>매개 변수

*pSocket*<br/>
소켓에 연결 된 `CSocketFile` 개체입니다.

*bArchiveCompatible*<br/>
사용 된 파일 개체 인지 여부를 지정 된 `CArchive` 개체입니다. 사용 하려는 경우에 FALSE 전달 합니다 `CSocketFile` 독립 실행형 마찬가지로 독립 실행형 방식으로 개체 `CFile` 특정 제한 사항과 함께 개체입니다. 이 플래그를 변경 하는 방법을 `CArchive` 개체에 연결 된 `CSocketFile` 개체는 읽기에 대 한 해당 버퍼를 관리 합니다.

### <a name="remarks"></a>설명

개체의 소멸자가 개체가 범위를 벗어날 되거나 삭제 되 면 자체 소켓 개체에서 분리 합니다.

> [!NOTE]
>  A `CSocketFile` 없이 (제한 됨) 파일로 사용할 수도 있습니다는 `CArchive` 개체입니다. 기본적으로 `CSocketFile` 생성자 *bArchiveCompatible* 매개 변수는 TRUE입니다. 이 보관 파일 사용에 대 한 파일 개체를 지정 합니다. 개체를 사용 하는 파일을 보관 하지 않고, FALSE를 전달 합니다 *bArchiveCompatible* 매개 변수입니다.

"보관 호환 되는" 모드로 `CSocketFile` 개체는 더 나은 성능을 제공 줄이고 "deadlock."의 위험 송신 및 수신 소켓은 서로 또는 공용 리소스에 대 한 대기 중인 교착 상태가 발생 합니다. 하는 경우이 상황이 발생할 수 있습니다는 `CArchive` 와 협력 하는 개체를 `CSocketFile` 와 서는 `CFile` 개체. 사용 하 여 `CFile`, 보관 파일을 요청한 것 보다 더 적은 바이트를 수신 하는 경우 파일의 끝에 도달 했음을 가정할 수 있습니다.

그러나 사용 하 여 `CSocketFile`, 데이터를 기반으로 하는 메시지 버퍼에서 여러 메시지를 포함할 수, 있으므로 요청 된 바이트 수보다 적은 받는 파일의 끝을 의미 하지 않습니다. 사용 하 여 처럼이 경우 응용 프로그램 차단 하지 않습니다 `CFile`, 버퍼가 비어 때까지 버퍼에서 메시지 읽기를 계속할 수 있습니다. 합니다 [CArchive::IsBufferEmpty](../../mfc/reference/carchive-class.md#isbufferempty) 함수는 이러한 경우 보관 파일의 버퍼의 상태를 모니터링 하는 데 유용 합니다.

사용에 대 한 자세한 내용은 `CSocketFile`, 문서를 참조 [Windows 소켓: 보관 파일을 사용 하 여 소켓을 사용 하 여](../../mfc/windows-sockets-using-sockets-with-archives.md) 고 [Windows 소켓: 아카이브를 사용 하는 소켓의 예](../../mfc/windows-sockets-example-of-sockets-using-archives.md)합니다.

## <a name="see-also"></a>참고자료

[CFile 클래스](../../mfc/reference/cfile-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CAsyncSocket 클래스](../../mfc/reference/casyncsocket-class.md)<br/>
[CSocket 클래스](../../mfc/reference/csocket-class.md)
