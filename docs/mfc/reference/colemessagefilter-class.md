---
title: COleMessageFilter 클래스
ms.date: 11/04/2016
f1_keywords:
- COleMessageFilter
- AFXOLE/COleMessageFilter
- AFXOLE/COleMessageFilter::COleMessageFilter
- AFXOLE/COleMessageFilter::BeginBusyState
- AFXOLE/COleMessageFilter::EnableBusyDialog
- AFXOLE/COleMessageFilter::EnableNotRespondingDialog
- AFXOLE/COleMessageFilter::EndBusyState
- AFXOLE/COleMessageFilter::OnMessagePending
- AFXOLE/COleMessageFilter::Register
- AFXOLE/COleMessageFilter::Revoke
- AFXOLE/COleMessageFilter::SetBusyReply
- AFXOLE/COleMessageFilter::SetMessagePendingDelay
- AFXOLE/COleMessageFilter::SetRetryReply
helpviewer_keywords:
- COleMessageFilter [MFC], COleMessageFilter
- COleMessageFilter [MFC], BeginBusyState
- COleMessageFilter [MFC], EnableBusyDialog
- COleMessageFilter [MFC], EnableNotRespondingDialog
- COleMessageFilter [MFC], EndBusyState
- COleMessageFilter [MFC], OnMessagePending
- COleMessageFilter [MFC], Register
- COleMessageFilter [MFC], Revoke
- COleMessageFilter [MFC], SetBusyReply
- COleMessageFilter [MFC], SetMessagePendingDelay
- COleMessageFilter [MFC], SetRetryReply
ms.assetid: b1fd1639-fac4-4fd0-bf17-15172deba13c
ms.openlocfilehash: a06891f9413979895175808e109cc4abb7d75e09
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62224368"
---
# <a name="colemessagefilter-class"></a>COleMessageFilter 클래스

OLE 애플리케이션의 상호 작용으로 요구되는 동시성을 관리합니다.

## <a name="syntax"></a>구문

```
class COleMessageFilter : public CCmdTarget
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[COleMessageFilter::COleMessageFilter](#colemessagefilter)|`COleMessageFilter` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[COleMessageFilter::BeginBusyState](#beginbusystate)|응용 프로그램 사용 중 상태로 전환 합니다.|
|[COleMessageFilter::EnableBusyDialog](#enablebusydialog)|사용 하도록 설정 하 고 호출된 응용 프로그램을 사용 중인 경우 표시 되는 대화 상자를 사용 하지 않도록 설정 합니다.|
|[COleMessageFilter::EnableNotRespondingDialog](#enablenotrespondingdialog)|사용 하도록 설정 하 고 호출된 응용 프로그램을 응답 하지 않을 경우 표시 되는 대화 상자를 사용 하지 않도록 설정 합니다.|
|[COleMessageFilter::EndBusyState](#endbusystate)|응용 프로그램의 사용 중 상태를 종료합니다.|
|[COleMessageFilter::OnMessagePending](#onmessagepending)|OLE 호출이 진행 중인 동안 메시지를 처리 하기 위해 프레임 워크에서 호출 됩니다.|
|[COleMessageFilter::Register](#register)|OLE 시스템 Dll 사용 하 여 메시지 필터를 등록합니다.|
|[COleMessageFilter::Revoke](#revoke)|OLE 시스템 Dll 사용 하 여 메시지 필터의 등록을 취소합니다.|
|[COleMessageFilter::SetBusyReply](#setbusyreply)|OLE 호출에 사용 중인 응용 프로그램의 회신을 결정합니다.|
|[COleMessageFilter::SetMessagePendingDelay](#setmessagependingdelay)|응용 프로그램을 OLE 호출에 대 한 응답을 기다리는 기간을 결정 합니다.|
|[COleMessageFilter::SetRetryReply](#setretryreply)|호출 응용 프로그램의 회신을 실행 중인 응용 프로그램을 결정합니다.|

## <a name="remarks"></a>설명

`COleMessageFilter` 클래스는 OLE 자동화 응용 프로그램 뿐만 아니라 비주얼 편집 서버 및 컨테이너 응용 프로그램에 유용 합니다. 호출 되는 서버 응용 프로그램에 대 한 다른 컨테이너 응용 프로그램에서 들어오는 호출을 취소 하거나 나중에 다시 시도 되도록 응용 프로그램을 "없음"이이 클래스를 사용 수 있습니다. 이 클래스는 호출된 응용 프로그램이 사용 중인 경우 응용 프로그램을 호출 하 여 수행할 작업을 결정 하려면 데도 사용할 수 있습니다.

호출 하는 서버 응용 프로그램에 대 한 일반적인 사용법은 [BeginBusyState](#beginbusystate) 하 고 [EndBusyState](#endbusystate) 경우 위험할 수는 문서 또는 다른 OLE 액세스 가능 개체도 소멸 될 예정입니다. 이러한 호출은 내용이 [CWinApp::OnIdle](../../mfc/reference/cwinapp-class.md#onidle) 사용자 인터페이스 업데이트 중입니다.

기본적으로 `COleMessageFilter` 개체는 응용 프로그램 초기화 될 때 할당 됩니다. 사용 하 여 검색할 수 있습니다 [AfxOleGetMessageFilter](application-control.md#afxolegetmessagefilter)합니다.

이 클래스는 고급 클래스; 거의 직접 사용 해야 합니다.

자세한 내용은 문서를 참조 하세요. [서버: 서버 구현](../../mfc/servers-implementing-a-server.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleMessageFilter`

## <a name="requirements"></a>요구 사항

**헤더:** afxole.h

##  <a name="beginbusystate"></a>  COleMessageFilter::BeginBusyState

사용 중 상태를 시작 하려면이 함수를 호출 합니다.

```
virtual void BeginBusyState();
```

### <a name="remarks"></a>설명

와 함께에서 작동 [EndBusyState](#endbusystate) 응용 프로그램의 사용 중 상태를 제어 합니다. 함수 [SetBusyReply](#setbusyreply) 많을 경우 응용 프로그램을 호출 하는 응용 프로그램의 회신을 결정 합니다.

합니다 `BeginBusyState` 고 `EndBusyState` 호출 증가 및 감소를 각각: 응용 프로그램 사용 중인지 여부를 결정 하는 카운터입니다. 예를 들어 두 호출 `BeginBusyState` 한 번 호출 하 고 `EndBusyState` 사용 중 상태에서 결과 계속 합니다. 호출할 필요는 사용 중 상태를 취소 하려면 `EndBusyState` 횟수 만큼 `BeginBusyState` 가 호출 되었습니다.

기본적으로 프레임 워크 유휴 처리를 수행 하는 동안 사용 중 상태에 들어갈 [CWinApp::OnIdle](../../mfc/reference/cwinapp-class.md#onidle)합니다. 응용 프로그램 처리 하는 동안 ON_COMMANDUPDATEUI 알림, 들어오는 호출 유휴 처리가 완료 된 후 나중에 처리 됩니다.

##  <a name="colemessagefilter"></a>  COleMessageFilter::COleMessageFilter

`COleMessageFilter` 개체를 만듭니다.

```
COleMessageFilter();
```

##  <a name="enablebusydialog"></a>  COleMessageFilter::EnableBusyDialog

사용 하도록 설정 하 고 메시지 보류 중인 지연 만료 되 면 표시 되는 사용 중인 대화 상자를 사용 하지 않도록 설정 (참조 [SetRetryReply](#setretryreply)) OLE 호출 하는 동안.

```
void EnableBusyDialog(BOOL bEnableBusy = TRUE);
```

### <a name="parameters"></a>매개 변수

*bEnableBusy*<br/>
"Busy" 대화 상자 사용 되는지 여부를 지정 합니다.

##  <a name="enablenotrespondingdialog"></a>  COleMessageFilter::EnableNotRespondingDialog

있으며 키보드 또는 마우스 메시지의 보류 중인 경우 표시 되는 "응답 하지 않습니다." 대화 상자를 사용 하지 않도록 설정 하는 동안 OLE 호출 및 호출 시간이 초과 되었습니다.

```
void EnableNotRespondingDialog(BOOL bEnableNotResponding = TRUE);
```

### <a name="parameters"></a>매개 변수

*bEnableNotResponding*<br/>
"응답 하지 않습니다." 대화 상자 사용 되는지 여부를 지정 합니다.

##  <a name="endbusystate"></a>  COleMessageFilter::EndBusyState

사용 중 상태를 종료 하려면이 함수를 호출 합니다.

```
virtual void EndBusyState();
```

### <a name="remarks"></a>설명

와 함께에서 작동 [BeginBusyState](#beginbusystate) 응용 프로그램의 사용 중 상태를 제어 합니다. 함수 [SetBusyReply](#setbusyreply) 많을 경우 응용 프로그램을 호출 하는 응용 프로그램의 회신을 결정 합니다.

합니다 `BeginBusyState` 고 `EndBusyState` 호출 증가 및 감소를 각각: 응용 프로그램 사용 중인지 여부를 결정 하는 카운터입니다. 예를 들어 두 호출 `BeginBusyState` 한 번 호출 하 고 `EndBusyState` 사용 중 상태에서 결과 계속 합니다. 호출할 필요는 사용 중 상태를 취소 하려면 `EndBusyState` 횟수 만큼 `BeginBusyState` 가 호출 되었습니다.

기본적으로 프레임 워크 유휴 처리를 수행 하는 동안 사용 중 상태에 들어갈 [CWinApp::OnIdle](../../mfc/reference/cwinapp-class.md#onidle)합니다. 응용 프로그램 처리 하는 동안 ON_UPDATE_COMMAND_UI 알림, 유휴 상태 처리가 완료 되 면 들어오는 호출 처리 됩니다.

##  <a name="onmessagepending"></a>  COleMessageFilter::OnMessagePending

OLE 호출이 진행 중인 동안 메시지를 처리 하기 위해 프레임 워크에서 호출 됩니다.

```
virtual BOOL OnMessagePending(const MSG* pMsg);
```

### <a name="parameters"></a>매개 변수

*pMsg*<br/>
보류 중인 메시지에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아닌 값이고, 실패하면 0입니다.

### <a name="remarks"></a>설명

프레임 워크를 호출 하는 호출 응용 프로그램을 완료할 수에 대 한 호출을 기다리는 경우 `OnMessagePending` 보류 중인 메시지에 대 한 포인터를 사용 하 여 합니다. 기본적으로 창이 업데이트는 시간이 오래 걸리는 호출 하는 동안 발생할 수 있도록 프레임 워크 WM_PAINT 메시지를 디스패치합니다.

호출 하 여 메시지 필터를 등록 해야 합니다 [등록](#register) 활성화 될 수 있습니다.

##  <a name="register"></a>  COleMessageFilter::Register

OLE 시스템 Dll 사용 하 여 메시지 필터를 등록합니다.

```
BOOL Register();
```

### <a name="return-value"></a>반환 값

성공하면 0이 아닌 값이고, 실패하면 0입니다.

### <a name="remarks"></a>설명

시스템 Dll 사용 하 여 등록 되지 않은 메시지 필터 효과가 없습니다. 일반적으로 응용 프로그램의 초기화 코드는 응용 프로그램의 메시지 필터를 등록합니다. 호출 하 여 프로그램을 종료 하기 전에 응용 프로그램에서 등록 된 다른 메시지 필터를 해지 해야 [Revoke](#revoke)합니다.

프레임 워크의 기본 메시지 필터가 자동으로 초기화 하는 동안 등록 되 고 종료 시 해지 합니다.

##  <a name="revoke"></a>  COleMessageFilter::Revoke

이전 등록을 해지에 대 한 호출을 수행한 [등록](#register)합니다.

```
void Revoke();
```

### <a name="remarks"></a>설명

프로그램이 종료 되기 전에 메시지 필터를 해지 해야 합니다.

프레임 워크에서 자동으로 등록을 만들고 있는 기본 메시지 필터를 자동으로 해지 됩니다.

##  <a name="setbusyreply"></a>  COleMessageFilter::SetBusyReply

이 함수는 응용 프로그램의 "사용 중 회신을입니다."를 설정합니다.

```
void SetBusyReply(SERVERCALL nBusyReply);
```

### <a name="parameters"></a>매개 변수

*nBusyReply*<br/>
값을 `SERVERCALL` COMPOBJ에 정의 된 열거형입니다. 8. 다음 값 중 하나를 가질 수 있습니다.

- SERVERCALL_ISHANDLED 응용 프로그램 호출을 허용할 수 있지만 특정 호출이 처리에 실패할 수 있습니다.

- SERVERCALL_REJECTED 응용 프로그램 됩니다 하지 수 있을 호출을 처리 합니다.

- SERVERCALL_RETRYLATER 응용 프로그램 일시적으로는 호출을 처리할 수 없는 상태입니다.

### <a name="remarks"></a>설명

합니다 [BeginBusyState](#beginbusystate) 하 고 [EndBusyState](#endbusystate) 함수 응용 프로그램의 사용 중 상태를 제어 합니다.

응용 프로그램이 수행 되었을 경우에 대 한 호출을 사용 하 여 사용 중인 `BeginBusyState`, 호출에 OLE 시스템 Dll에서에서 사용 하 여 응답의 마지막 설정에 따라 결정 된 값 `SetBusyReply`합니다. 호출 응용 프로그램에 수행할 동작을 확인 하려면이 사용 중 응답을 사용 합니다.

기본적으로 사용 중인 회신 SERVERCALL_RETRYLATER는 합니다. 이 회신 하면 호출 응용 프로그램이 가능한 한 빨리 호출을 다시 시도 합니다.

##  <a name="setmessagependingdelay"></a>  COleMessageFilter::SetMessagePendingDelay

호출 응용 프로그램 추가 작업을 수행 하기 전에 호출된 된 응용 프로그램의 응답을 기다리는 기간을 결정 합니다.

```
void SetMessagePendingDelay(DWORD nTimeout = 5000);
```

### <a name="parameters"></a>매개 변수

*nTimeout*<br/>
메시지-보류 중인 지연 시간 (밀리초)의 수입니다.

### <a name="remarks"></a>설명

이 함수는 함께에서 작동 [SetRetryReply](#setretryreply)합니다.

##  <a name="setretryreply"></a>  COleMessageFilter::SetRetryReply

호출된 응용 프로그램에서 사용 중 응답을 받을 때 호출 응용 프로그램의 동작을 결정 합니다.

```
void SetRetryReply(DWORD nRetryReply = 0);
```

### <a name="parameters"></a>매개 변수

*nRetryReply*<br/>
재시도 사이의 밀리초 수입니다.

### <a name="remarks"></a>설명

호출된 응용 프로그램을 사용 중인 것을 나타내는, 경우에 호출 응용 프로그램 서버 사용량이 더 이상를 즉시 다시 시도 하거나 지정된 된 간격 후에 다시 시도 될 때까지 대기할 결정할 수 없습니다. 호출을 모두 취소 하려는 경우도 해당.

호출자의 응답이 함수에 의해 제어 됩니다 `SetRetryReply` 하 고 [SetMessagePendingDelay](#setmessagependingdelay)합니다. `SetRetryReply` 호출 응용 프로그램이 지정된 된 호출에 대해 재시도 간에 대기 해야 하는 시간을 결정 합니다. `SetMessagePendingDelay` 호출 응용 프로그램 서버에서 응답에 대 한 추가 작업을 수행 하기 전에 대기 하는 기간을 결정 합니다.

일반적으로 기본값을 적합 하 고 변경할 필요가 없습니다. 프레임 워크 호출을 다시 시도 마다 *nRetryReply* 호출이 나 메시지 보류 중인 지연 만료 될 때까지 시간 (밀리초)입니다. 값이 0에 대 한 *nRetryReply* 지정를 즉시 다시 시도 및-1 호출의 취소를 지정 합니다.

메시지 보류 중인 지연 시간을 초과한 경우, "사용 중 대화 상자" OLE (참조 [COleBusyDialog](../../mfc/reference/colebusydialog-class.md)) 사용자 취소 하거나 다시 호출 하도록 선택할 수 있도록 표시 됩니다. 호출 [EnableBusyDialog](#enablebusydialog) 사용 하도록 설정 하거나이 대화 상자를 사용 하지 않도록 설정 합니다.

키보드 또는 마우스 메시지를 보류 중인 경우 호출 및 호출 하는 동안 시간이 초과 되었습니다. (메시지 보류 중인 지연 시간을 초과), "응답 하지 않습니다." 대화 상자가 표시 됩니다. 호출 [EnableNotRespondingDialog](#enablenotrespondingdialog) 사용 하도록 설정 하거나이 대화 상자를 사용 하지 않도록 설정 합니다. 일반적으로이 상태가 오류가 발생 했는지를 사용자를 가져오는 솔 나타냅니다.

대화 상자를 사용 하지 않는 경우에 현재 "재시도 회신"는 항상 사용 중인 응용 프로그램에 대 한 호출에 대 한 사용 됩니다.

## <a name="see-also"></a>참고자료

[CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)
