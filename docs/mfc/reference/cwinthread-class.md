---
title: CWinThread 클래스
ms.date: 11/04/2016
f1_keywords:
- CWinThread
- AFXWIN/CWinThread
- AFXWIN/CWinThread::CWinThread
- AFXWIN/CWinThread::CreateThread
- AFXWIN/CWinThread::ExitInstance
- AFXWIN/CWinThread::GetMainWnd
- AFXWIN/CWinThread::GetThreadPriority
- AFXWIN/CWinThread::InitInstance
- AFXWIN/CWinThread::IsIdleMessage
- AFXWIN/CWinThread::OnIdle
- AFXWIN/CWinThread::PostThreadMessage
- AFXWIN/CWinThread::PreTranslateMessage
- AFXWIN/CWinThread::ProcessMessageFilter
- AFXWIN/CWinThread::ProcessWndProcException
- AFXWIN/CWinThread::PumpMessage
- AFXWIN/CWinThread::ResumeThread
- AFXWIN/CWinThread::Run
- AFXWIN/CWinThread::SetThreadPriority
- AFXWIN/CWinThread::SuspendThread
- AFXWIN/CWinThread::m_bAutoDelete
- AFXWIN/CWinThread::m_hThread
- AFXWIN/CWinThread::m_nThreadID
- AFXWIN/CWinThread::m_pActiveWnd
- AFXWIN/CWinThread::m_pMainWnd
helpviewer_keywords:
- CWinThread [MFC], CWinThread
- CWinThread [MFC], CreateThread
- CWinThread [MFC], ExitInstance
- CWinThread [MFC], GetMainWnd
- CWinThread [MFC], GetThreadPriority
- CWinThread [MFC], InitInstance
- CWinThread [MFC], IsIdleMessage
- CWinThread [MFC], OnIdle
- CWinThread [MFC], PostThreadMessage
- CWinThread [MFC], PreTranslateMessage
- CWinThread [MFC], ProcessMessageFilter
- CWinThread [MFC], ProcessWndProcException
- CWinThread [MFC], PumpMessage
- CWinThread [MFC], ResumeThread
- CWinThread [MFC], Run
- CWinThread [MFC], SetThreadPriority
- CWinThread [MFC], SuspendThread
- CWinThread [MFC], m_bAutoDelete
- CWinThread [MFC], m_hThread
- CWinThread [MFC], m_nThreadID
- CWinThread [MFC], m_pActiveWnd
- CWinThread [MFC], m_pMainWnd
ms.assetid: 10cdc294-4057-4e76-ac7c-a8967a89af0b
ms.openlocfilehash: 9f17561941d785e5eb7b5fd8c52ab452aa6369e7
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220430"
---
# <a name="cwinthread-class"></a>CWinThread 클래스

애플리케이션 내의 실행 스레드를 나타냅니다.

## <a name="syntax"></a>구문

```
class CWinThread : public CCmdTarget
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CWinThread::CWinThread](#cwinthread)|`CWinThread` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CWinThread::CreateThread](#createthread)|실행을 시작 하는 `CWinThread` 개체입니다.|
|[CWinThread::ExitInstance](#exitinstance)|스레드가 종료 될 때 정리 하기 위해 재정의 합니다.|
|[CWinThread::GetMainWnd](#getmainwnd)|스레드에 대 한 주 창에 대 한 포인터를 검색합니다.|
|[CWinThread::GetThreadPriority](#getthreadpriority)|현재 스레드의 우선 순위를 가져옵니다.|
|[CWinThread::InitInstance](#initinstance)|스레드 인스턴스 초기화를 수행 하도록 재정의 합니다.|
|[CWinThread::IsIdleMessage](#isidlemessage)|특별 한 메시지를 확인 합니다.|
|[CWinThread::OnIdle](#onidle)|스레드별 유휴 시간 처리를 수행 하려면 재정의 합니다.|
|[CWinThread::PostThreadMessage](#postthreadmessage)|다른 메시지를 게시 `CWinThread` 개체입니다.|
|[CWinThread::PreTranslateMessage](#pretranslatemessage)|Windows 함수로 디스패치 되기 전에 메시지를 필터링 [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) 하 고 [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage)합니다.|
|[CWinThread::ProcessMessageFilter](#processmessagefilter)|응용 프로그램에 도달 하기 전에 특정 메시지를 차단 합니다.|
|[CWinThread::ProcessWndProcException](#processwndprocexception)|처리 되지 않은 모든 스레드의 메시지 및 명령 처리기에서 throw 된 예외를 가로챕니다.|
|[CWinThread::PumpMessage](#pumpmessage)|스레드의 메시지 루프를 포함합니다.|
|[CWinThread::ResumeThread](#resumethread)|스레드의 감소 개수를 일시 중단합니다.|
|[CWinThread::Run](#run)|메시지 펌프를 사용 하 여 스레드에 대 한 함수를 제어 합니다. 기본 메시지 루프를 사용자 지정을 재정의 합니다.|
|[CWinThread::SetThreadPriority](#setthreadpriority)|현재 스레드의 우선 순위를 설정 합니다.|
|[CWinThread::SuspendThread](#suspendthread)|스레드 a 증가 수 일시 중단합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CWinThread::operator 핸들](#operator_handle)|핸들을 검색 합니다 `CWinThread` 개체입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CWinThread::m_bAutoDelete](#m_bautodelete)|스레드 종료 시 개체를 삭제할지 여부를 지정 합니다.|
|[CWinThread::m_hThread](#m_hthread)|현재 스레드를 처리 합니다.|
|[CWinThread::m_nThreadID](#m_nthreadid)|현재 스레드의 ID입니다.|
|[CWinThread::m_pActiveWnd](#m_pactivewnd)|OLE 서버에 내부 활성화 되 면 컨테이너 응용 프로그램의 주 창에 대 한 포인터입니다.|
|[CWinThread::m_pMainWnd](#m_pmainwnd)|응용 프로그램의 주 창에 대 한 포인터를 보유합니다.|

## <a name="remarks"></a>설명

파생 된 개체에서 주 스레드 실행은 일반적으로 제공 `CWinApp`; `CWinApp` 에서 파생 된 `CWinThread`합니다. 추가 `CWinThread` 개체는 지정된 된 응용 프로그램 내에 여러 스레드를 사용 합니다.

두 가지 유형의 스레드를 가지는 `CWinThread` 지원: 사용자 인터페이스 스레드와 작업자 스레드 수입니다. 작업자 스레드 메시지 펌프가 없습니다: 예를 들어 스프레드시트 응용 프로그램에서 백그라운드 계산을 수행 하는 스레드입니다. 사용자 인터페이스 스레드는 메시지 펌프가 및 시스템에서 수신한 메시지를 처리 합니다. [CWinApp](../../mfc/reference/cwinapp-class.md) 클래스에서 파생 된 사용자 인터페이스 스레드 예가 되며 합니다. 다른 사용자 인터페이스 스레드에서 직접 파생 될 수도 있습니다 `CWinThread`합니다.

클래스의 개체 `CWinThread` 스레드 기간에 대 한 일반적으로 존재 합니다. 이 동작을 수정 하려는 경우 설정할 [m_bAutoDelete](#m_bautodelete) FALSE로 합니다.

`CWinThread` 클래스는 하는 데 필요한 코드와 MFC 완벽 하 게 스레드로부터 안전 합니다. 관리 하는 스레드 관련 정보를 유지 하기 위해 프레임 워크에서 사용 되는 스레드 로컬 데이터 `CWinThread` 개체입니다. 에 대 한이 종속성이로 인해 `CWinThread` 스레드 로컬 데이터를 처리 하려면 MFC를 사용 하는 모든 스레드 MFC에서 만든 해야 합니다. 예를 들어, 런타임 함수에서 만든 스레드 [_beginthread, _beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md) MFC Api를 사용할 수 없습니다.

호출 스레드를 만드는 [AfxBeginThread](application-information-and-management.md#afxbeginthread)합니다. 작업자 또는 사용자 인터페이스 스레드 여부에 따라 두 가지 형식이 있습니다. 사용자 인터페이스 스레드를 원한다 면 전달할 `AfxBeginThread` 에 대 한 포인터를 `CRuntimeClass` 의 프로그램 `CWinThread`-클래스를 파생 합니다. 작업자 스레드를 만들지 않으려면 전달할 `AfxBeginThread` 제어 함수 및 매개 변수를 제어 하는 함수에 대 한 포인터입니다. 작업자 스레드 및 사용자 인터페이스 스레드 모두에 대 한 우선 순위, 스택 크기, 생성 플래그 및 보안 특성을 수정 하는 선택적 매개 변수를 지정할 수 있습니다. `AfxBeginThread` 새 사용자에 대 한 포인터를 반환 합니다 `CWinThread` 개체입니다.

호출 하는 대신 `AfxBeginThread`를 생성할 수는 `CWinThread`-파생 개체와 호출 `CreateThread`합니다. 이 두 단계 생성 방법은 다시 사용 하려는 경우에 유용 합니다 `CWinThread` 연속 생성 및 종료 스레드 실행 간에 개체입니다.

대 한 자세한 내용은 `CWinThread`, 문서를 참조 하세요 [스레딩 C++ 및 MFC](../../parallel/multithreading-with-cpp-and-mfc.md)하십시오 [다중 스레딩: 사용자 인터페이스 스레드 만들기](../../parallel/multithreading-creating-user-interface-threads.md), [다중 스레딩: 작업자 스레드를 만들지](../../parallel/multithreading-creating-worker-threads.md), 및 [다중 스레딩: 동기화 클래스 사용 방법](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CWinThread`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

##  <a name="createthread"></a>  CWinThread::CreateThread

호출 프로세스의 주소 공간 내에서 실행 되도록 스레드를 만듭니다.

```
BOOL CreateThread(
    DWORD dwCreateFlags = 0,
    UINT nStackSize = 0,
    LPSECURITY_ATTRIBUTES lpSecurityAttrs = NULL);
```

### <a name="parameters"></a>매개 변수

*dwCreateFlags*<br/>
스레드 생성을 제어 하는 추가 플래그를 지정 합니다. 이 플래그는 두 값 중 하나를 포함할 수 있습니다.

- CREATE_SUSPENDED 일시 중단 횟수 하나를 사용 하 여 스레드를 시작 합니다. 모든 멤버 데이터를 초기화 하려는 경우 CREATE_SUSPENDED를 사용 합니다 `CWinThread` 개체와 같은 [m_bAutoDelete](#m_bautodelete) 또는 스레드가 실행을 시작 하기 전에 파생된 클래스의 모든 멤버입니다. 초기화 완료 되 면 사용 합니다 [cwinthread:: Resumethread](#resumethread) 실행 스레드를 시작 합니다. 될 때까지 스레드가 실행 되지 것입니다 `CWinThread::ResumeThread` 라고 합니다.

- **0** 스레드를 만든 후 즉시 시작 합니다.

*nStackSize*<br/>
새 스레드의 스택 (바이트)에서 크기를 지정합니다. 하는 경우 **0**, 스택 크기를 프로세스의 주 스레드는 동일한 크기를 기본값으로 합니다.

*lpSecurityAttrs*<br/>
가리키는 [SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560) 스레드에 대 한 보안 특성을 지정 하는 구조입니다.

### <a name="return-value"></a>반환 값

스레드가 성공적으로 생성 되는 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

사용 하 여 `AfxBeginThread` 스레드 개체를 만들고 한 번에 실행 합니다. 사용 하 여 `CreateThread` 연속 생성 및 종료 스레드 실행 간에 스레드 개체를 다시 사용 하려는 경우.

##  <a name="cwinthread"></a>  CWinThread::CWinThread

`CWinThread` 개체를 생성합니다.

```
CWinThread();
```

### <a name="remarks"></a>설명

호출 스레드의 실행을 시작 합니다 [CreateThread](#createthread) 멤버 함수입니다. 일반적으로 스레드를 호출 하 여 만들려는 [AfxBeginThread](application-information-and-management.md#afxbeginthread),이 생성자는 호출 및 `CreateThread`합니다.

##  <a name="exitinstance"></a>  CWinThread::ExitInstance

드물게 재정의 내에서 프레임 워크에서 호출 [실행](#run) 멤버 함수는 스레드를 종료를 호출 하는 경우 또는 [InitInstance](#initinstance) 실패 합니다.

```
virtual int ExitInstance();
```

### <a name="return-value"></a>반환 값

스레드의 종료 코드 0은 오류 없이 나타내고 0 보다 큰 값에 오류가 발생 합니다. 이 값을 호출 하 여 검색할 수 있습니다 [GetExitCodeThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getexitcodethread)합니다.

### <a name="remarks"></a>설명

호출 하지 마십시오이 멤버 함수 어디에서 나 하지만 내는 `Run` 멤버 함수입니다. 이 멤버 함수는 사용자 인터페이스 스레드 에서만에서 사용 됩니다.

이 함수의 기본 구현은 삭제 합니다 `CWinThread` 경우 개체 [m_bAutoDelete](#m_bautodelete) 은 TRUE입니다. 스레드가 종료 될 때 추가 정리를 수행 하려는 경우이 함수를 재정의 합니다. 구현의 `ExitInstance` 코드를 실행 한 후에 기본 클래스의 버전을 호출 해야 합니다.

##  <a name="getmainwnd"></a>  CWinThread::GetMainWnd

OLE 서버 응용 프로그램을 사용 하는 경우 직접 참조 하는 대신 응용 프로그램의 활성 주 창에 대 한 포인터를 검색 하려면이 함수를 호출 합니다 `m_pMainWnd` 응용 프로그램 개체의 멤버입니다.

```
virtual CWnd* GetMainWnd();
```

### <a name="return-value"></a>반환 값

이 함수는 windows의 두 형식 중 하나에 대 한 포인터를 반환합니다. 이 함수를 반환 하는 경우 스레드 OLE 서버 부분을 현재는 컨테이너 내에서 내부 활성화 하는 개체에는 [CWinApp::m_pActiveWnd](../../mfc/reference/cwinapp-class.md#m_pactivewnd) 의 데이터 멤버는 `CWinThread` 개체입니다.

이 함수를 반환 하는 경우 컨테이너 내에서 내부 활성화 된 개체가 없거나 응용 프로그램이 OLE 서버가 아닙니다.에 [m_pMainWnd](#m_pmainwnd) 스레드 개체의 데이터 멤버입니다.

### <a name="remarks"></a>설명

사용자 인터페이스 스레드의 경우 같습니다 직접 참조 하는 `m_pActiveWnd` 응용 프로그램 개체의 멤버입니다.

응용 프로그램이 OLE 서버가 아닌 경우 이 함수의 호출은 응용 프로그램 개체의 `m_pMainWnd` 멤버를 직접 참조하는 것과 동일합니다.

기본 동작을 수정 하려면이 함수를 재정의 합니다.

##  <a name="getthreadpriority"></a>  CWinThread::GetThreadPriority

이 스레드의 현재 스레드 우선 순위 수준을 가져옵니다.

```
int GetThreadPriority();
```

### <a name="return-value"></a>반환 값

현재 스레드 우선 순위는 우선 순위 클래스 내의 수준입니다. 반환 되는 값은 다음 중 하나가 됩니다 순위가 가장 높은 우선 순위를 나열 합니다.

- THREAD_PRIORITY_TIME_CRITICAL

- THREAD_PRIORITY_HIGHEST

- THREAD_PRIORITY_ABOVE_NORMAL

- THREAD_PRIORITY_NORMAL

- THREAD_PRIORITY_BELOW_NORMAL

- THREAD_PRIORITY_LOWEST

- THREAD_PRIORITY_IDLE

이러한 우선 순위에 대 한 자세한 내용은 참조 하세요. [SetThreadPriority](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) Windows SDK에 있습니다.

##  <a name="initinstance"></a>  CWinThread::InitInstance

`InitInstance` 재정의 하는 사용자 인터페이스 스레드의 각 새 인스턴스를 초기화 해야 합니다.

```
virtual BOOL InitInstance();
```

### <a name="return-value"></a>반환 값

초기화에 성공 하면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

재정의 하는 일반적으로 `InitInstance` 스레드를 처음 만들 때 완료 해야 하는 작업을 수행할 수 있습니다.

이 멤버 함수는 사용자 인터페이스 스레드 에서만에서 사용 됩니다. 에 전달 된 제어 함수에서 작업자 스레드는 초기화를 수행 [AfxBeginThread](application-information-and-management.md#afxbeginthread)합니다.

##  <a name="isidlemessage"></a>  CWinThread::IsIdleMessage

계속 하려면이 함수를 재정의 `OnIdle` 특정 메시지 생성 되 면 호출 되 고 있습니다.

```
virtual BOOL IsIdleMessage(MSG* pMsg);
```

### <a name="parameters"></a>매개 변수

*pMsg*<br/>
현재 처리 중인 메시지를 가리킵니다.

### <a name="return-value"></a>반환 값

0이 아닌 경우 `OnIdle` 처리 후 호출할 메시지 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

기본 구현을 호출 하지 않습니다 `OnIdle` 중복 마우스 메시지 후 캐럿 깜박임에서 생성 된 메시지입니다.

응용 프로그램에서 간단한 타이머를 만든 경우 `OnIdle` 호출할 자주 인해 성능 문제가 발생 합니다. 이러한 응용 프로그램의 성능을 개선 하기 위해 재정의 `IsIdleMessage` 응용 프로그램의 `CWinApp`-WM_TIMER 메시지에 대 한 다음과 같은 확인 하는 클래스를 파생 합니다.

[!code-cpp[NVC_MFCDocView#189](../../mfc/codesnippet/cpp/cwinthread-class_1.cpp)]

WM_TIMER이 방식으로 처리 하면 간단한 타이머를 사용 하는 응용 프로그램의 성능이 향상 됩니다.

##  <a name="m_bautodelete"></a>  CWinThread::m_bAutoDelete

스레드 종료 시 `CWinThread` 개체를 자동으로 삭제할지 여부를 지정합니다.

```
BOOL m_bAutoDelete;
```

### <a name="remarks"></a>설명

`m_bAutoDelete` 데이터 멤버는 BOOL 형식의 공용 변수입니다.

값 `m_bAutoDelete` 스레드 핸들이 닫혀 어떻게 영향을 주지 않습니다 하지만 핸들을 닫는 시기에 영향 을지 않습니다. 스레드 핸들은 항상 `CWinThread` 개체가 제거될 때 닫힙니다.

##  <a name="m_hthread"></a>  CWinThread::m_hThread

이 연결 된 스레드로 처리 `CWinThread`합니다.

```
HANDLE m_hThread;
```

### <a name="remarks"></a>설명

`m_hThread` 데이터 멤버는 핸들 형식의 공용 변수입니다. 핸들을 아직 닫히지 기본 커널 스레드 개체 현재 있는 경우에 유효 합니다.

CWinThread 소멸자에서 CloseHandle 호출 `m_hThread`합니다. 하는 경우 [m_bAutoDelete](#m_bautodelete) 는 스레드가 종료 되 면 TRUE이 고는 CWinThread 개체 제거 CWinThread 개체 및 해당 멤버 변수에 대 한 모든 포인터를 무효화 하는 합니다. 해야 할 수도 있습니다는 `m_hThread` 멤버 스레드 종료 값을 확인 하거나 신호를 기다려야 합니다. CWinThread 개체를 유지 하 고 `m_hThread` 멤버 스레드 실행 중 이며, 종료 된 후 설정 `m_bAutoDelete` 스레드 실행을 계속 허용 하기 전에 FALSE로 합니다. 이 고, 그렇지 스레드 수 종료, CWinThread 개체를 제거 하 고 사용 하기 전에 핸들을 닫습니다. 이 기법을 사용 하는 CWinThread 개체의 삭제를 담당 합니다.

##  <a name="m_nthreadid"></a>  CWinThread::m_nThreadID

이 연결 된 스레드의 ID `CWinThread`합니다.

```
DWORD m_nThreadID;
```

### <a name="remarks"></a>설명

`m_nThreadID` 데이터 멤버는 DWORD 형식의 공용 변수입니다. 기본 커널 스레드 개체는 현재 존재 하는 경우에 유효 합니다.
에 대 한 설명을 참조 하세요 [m_hThread](#m_hthread) 수명입니다.

### <a name="example"></a>예제

  예를 참조 하세요 [AfxGetThread](application-information-and-management.md#afxgetthread)합니다.

##  <a name="m_pactivewnd"></a>  CWinThread::m_pActiveWnd

이 데이터 멤버를 사용 하 여 스레드의 활성 창 개체에 대 한 포인터를 저장 합니다.

```
CWnd* m_pActiveWnd;
```

### <a name="remarks"></a>설명

창에서 참조 하는 경우 Microsoft Foundation Class 라이브러리를 스레드를 자동으로 종료 됩니다 `m_pActiveWnd` 닫혀 있습니다. 이 스레드는 응용 프로그램에 대 한 주 스레드, 응용 프로그램 종료 됨. 이 데이터 멤버가 NULL 이면 응용 프로그램의 활성 창 `CWinApp` 개체 상속 됩니다. `m_pActiveWnd` 형식의 공용 변수 `CWnd*`합니다.

재정의 하는 경우이 멤버 변수를 설정할 일반적으로 `InitInstance`입니다. 작업자 스레드에서이 데이터 멤버의 값은 부모 스레드에서 상속 됩니다.

##  <a name="m_pmainwnd"></a>  CWinThread::m_pMainWnd

이 데이터 멤버를 사용 하 여 스레드의 주 창 개체에 대 한 포인터를 저장 합니다.

```
CWnd* m_pMainWnd;
```

### <a name="remarks"></a>설명

창에서 참조 하는 경우 Microsoft Foundation Class 라이브러리를 스레드를 자동으로 종료 됩니다 `m_pMainWnd` 닫혀 있습니다. 이 스레드는 응용 프로그램에 대 한 주 스레드, 응용 프로그램 종료 됨. 이 데이터 멤버가 null 인 경우 응용 프로그램의 주 창 하는 경우 `CWinApp` 스레드를 종료 하는 경우를 확인 하려면 개체를 사용 합니다. `m_pMainWnd` 형식의 공용 변수 `CWnd*`합니다.

재정의 하는 경우이 멤버 변수를 설정할 일반적으로 `InitInstance`입니다. 작업자 스레드에서이 데이터 멤버의 값은 부모 스레드에서 상속 됩니다.

##  <a name="onidle"></a>  CWinThread::OnIdle

유휴 시간 처리를 수행 하려면이 멤버 함수를 재정의 합니다.

```
virtual BOOL OnIdle(LONG lCount);
```

### <a name="parameters"></a>매개 변수

*lCount*<br/>
카운터를 증가 될 때마다 `OnIdle` 스레드의 메시지 큐가 비어 있을 때 호출 됩니다. 이 횟수가 새 메시지가 처리 될 때마다 0으로 재설정 됩니다. 사용할 수는 *lCount* 매개 변수에 지정 된 메시지를 처리 하지 않고 스레드는 유휴 상태 였습니다 상대 기간입니다.

### <a name="return-value"></a>반환 값

유휴 처리 시간이; 받으려면 0이 아닌 값 더 이상 유휴 처리 시간이 필요 하는 경우 0입니다.

### <a name="remarks"></a>설명

`OnIdle` 스레드의 메시지 큐가 비어 있을 때 기본 메시지 루프에서 호출 됩니다. 고유한 백그라운드 유휴 처리기 작업을 호출 하려면 재정의 사용 합니다.

`OnIdle` 추가 유휴 처리 시간이 필요한 임을 나타내려면 0을 반환 해야 합니다. 합니다 *lCount* 매개 변수 될 때마다 증가 `OnIdle` 메시지 큐를 빈 상태가 되 고 새 메시지를 처리 될 때마다 0으로 설정 될 때 호출 됩니다. 이 수에 따라 다른 유휴 루틴을 호출할 수 있습니다.

이 멤버 함수를 기본 구현에는 임시 개체 및 메모리에서 사용 되지 않는 동적 연결 라이브러리를 해제합니다.

이 멤버 함수는 사용자 인터페이스 스레드 에서만에서 사용 됩니다.

응용 프로그램까지 메시지를 처리할 수 없습니다 때문에 `OnIdle` 이 함수에서 반환 되는 경우 시간이 오래 걸리는 작업을 수행 하지 않습니다.

##  <a name="operator_handle"></a>  CWinThread::operator HANDLE

핸들을 검색 합니다 `CWinThread` 개체입니다.

```
operator HANDLE() const;
```

### <a name="return-value"></a>반환 값

성공 하면는 스레드 개체의 핸들 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

핸들을 사용 하 여 Windows Api 직접 호출 합니다.

##  <a name="postthreadmessage"></a>  CWinThread::PostThreadMessage

다른 사용자 정의 메시지를 게시할 호출 `CWinThread` 개체입니다.

```
BOOL PostThreadMessage(
    UINT message,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>매개 변수

*message*<br/>
사용자 정의 메시지의 ID입니다.

*wParam*<br/>
첫 번째 메시지 매개 변수입니다.

*lParam*<br/>
두 번째 메시지 매개 변수입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

게시 된 메시지는 메시지 맵 매크로 ON_THREAD_MESSAGE에 의해 적절 한 메시지 처리기에 매핑됩니다.

> [!NOTE]
> 호출 하는 경우 [PostThreadMessage](/windows/desktop/api/winuser/nf-winuser-postthreadmessagea), 메시지는 스레드의 메시지 큐에 배치 됩니다. 그러나 이러한 방식으로 게시 되는 메시지 창에 연결 되어 있지 않으므로 MFC는 디스패치하지 해당 메시지나 명령 처리기에. 이러한 메시지를 처리 하기 위해 재정의 `PreTranslateMessage()` CWinApp 파생의 함수 클래스를 수동으로 메시지를 처리 합니다.

##  <a name="pretranslatemessage"></a>  CWinThread::PreTranslateMessage

창 메시지를 필터링 하려면이 함수를 재정의 하 여 Windows 함수로 디스패치 되기 전에 [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) 하 고 [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage)합니다.

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>매개 변수

*pMsg*<br/>
가리키는 [MSG 구조체](/windows/desktop/api/winuser/ns-winuser-tagmsg) 처리할 메시지를 포함 합니다.

### <a name="return-value"></a>반환 값

메시지에서 완전히 처리 된 경우 0이 아닌 `PreTranslateMessage` 하며 추가로 처리할 수 없습니다. 일반적인 방법으로 메시지를 처리 해야 하면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 사용자 인터페이스 스레드 에서만에서 사용 됩니다.

##  <a name="processmessagefilter"></a>  CWinThread::ProcessMessageFilter

프레임 워크의 후크 함수는 필터링 하 고 특정 Windows 메시지에 응답 하려면이 멤버 함수를 호출 합니다.

```
virtual BOOL ProcessMessageFilter(
    int code,
    LPMSG lpMsg);
```

### <a name="parameters"></a>매개 변수

*코드*<br/>
후크 코드를 지정합니다. 이 멤버 함수는 코드를 사용 하 여 처리 하는 방법을 결정 *lpMsg 합니다.*

*lpMsg*<br/>
Windows에 대 한 포인터 [MSG 구조체](/windows/desktop/api/winuser/ns-winuser-tagmsg)합니다.

### <a name="return-value"></a>반환 값

0이 아닌 메시지를 처리 합니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

응용 프로그램의 일반 메시지를 보내기 전에 이벤트를 처리 하는 후크 함수를 처리 합니다.

이 고급 기능을 재정의 하는 경우 사용할 프레임 워크의 유지 관리 하는 기본 클래스 버전을 호출 해야 처리를 연결 합니다.

##  <a name="processwndprocexception"></a>  CWinThread::ProcessWndProcException

프레임 워크는 처리기에 스레드의 메시지 또는 명령 처리기 중 하나에서 throw 된 예외를 catch 하지 않습니다 때마다이 멤버 함수를 호출 합니다.

```
virtual LRESULT ProcessWndProcException(
    CException* e,
    const MSG* pMsg);
```

### <a name="parameters"></a>매개 변수

*e*<br/>
처리 되지 않은 예외를 가리킵니다.

*pMsg*<br/>
가리키는 [MSG 구조체](/windows/desktop/api/winuser/ns-winuser-tagmsg) 예외를 throw 하기 위해 프레임 워크를 발생 시킨 windows 메시지에 대 한 정보를 포함 합니다.

### <a name="return-value"></a>반환 값

-1 이면 WM_CREATE 예외를 생성 됩니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수를 직접 호출 하지 마세요.

이 멤버 함수를 기본 구현에는 다음 메시지에서 생성 된 예외만 처리 합니다.

|명령|작업|
|-------------|------------|
|WM_CREATE|실패 합니다.|
|WM_PAINT|따라서 생성 되 고 다른 WM_PAINT 메시지를 방지 하 고 영향을 받는 창 유효성을 검사 합니다.|

전역 예외 처리를 제공 하려면이 멤버 함수를 재정의 합니다. 기본 동작을 표시 하려는 경우에 기본 기능을 호출 합니다.

이 멤버 함수는 메시지 펌프가 스레드 에서만 사용 됩니다.

##  <a name="pumpmessage"></a>  CWinThread::PumpMessage

스레드의 메시지 루프를 포함합니다.

```
virtual BOOL PumpMessage();
```

### <a name="remarks"></a>설명

`PumpMessage` 스레드의 메시지 루프를 포함합니다. `PumpMessage` 호출한 `CWinThread` 스레드의 메시지 펌프를 합니다. 호출할 수 있습니다 `PumpMessage` 처리할 메시지를 재정의할 수 있습니다 또는 직접 `PumpMessage` 해당 기본 동작을 변경 합니다.

호출 `PumpMessage` 직접 고급 사용자 에게만 해당 기본 동작 재정의 것이 좋습니다.

##  <a name="resumethread"></a>  CWinThread::ResumeThread

호출 하 여 일시 중지 된 스레드의 실행을 다시 시작 합니다 [있는 경우 SuspendThread](#suspendthread) 멤버 함수 또는 CREATE_SUSPENDED 플래그를 사용 하 여 만든 스레드입니다.

```
DWORD ResumeThread();
```

### <a name="return-value"></a>반환 값

스레드의 이전 일시 중단 횟수가 성공할 경우 `0xFFFFFFFF` 그렇지 않은 경우. 반환 값이 0 이면 현재 스레드의 일시 중단 되지 되었습니다. 반환 값이 1 이면 스레드가 일시 중단 되지만 다시 시작 됩니다. 스레드는 한 가지 방법은 보다 큰 모든 반환 값에 일시 중단 된 상태로 유지 됩니다.

### <a name="remarks"></a>설명

현재 스레드의 일시 중단 횟수가 1만 큼 줄어듭니다. 일시 중단 횟수가 감소 하는 경우 스레드를 0으로 실행을 다시 시작 그렇지 않으면 스레드가 일시 중단 된 상태로 합니다.

##  <a name="run"></a>  CWinThread::Run

사용자 인터페이스 스레드에 대 한 기본 메시지 루프를 제공합니다.

```
virtual int Run();
```

### <a name="return-value"></a>반환 값

**int** 스레드에 의해 반환 되는 값입니다. 이 값을 호출 하 여 검색할 수 있습니다 [GetExitCodeThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getexitcodethread)합니다.

### <a name="remarks"></a>설명

`Run` 획득 및 응용 프로그램에서 받을 때까지 Windows 메시지를 디스패치를 [WM_QUIT](/windows/desktop/winmsg/wm-quit) 메시지입니다. 스레드의 메시지 큐에 현재 없는 메시지를 포함 하는 경우 `Run` 호출 `OnIdle` 유휴 시간 처리를 수행 합니다. 들어오는 메시지를 [PreTranslateMessage](#pretranslatemessage) 특수 한 처리 한 다음 Windows 함수에 멤버 함수 [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) 표준 키보드 변환에 대 한 합니다. 마지막으로, 합니다 [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) Windows 함수를 호출 합니다.

`Run` 대부분 재정의 하지만 특수 동작을 구현 하도록 재정의할 수 있습니다.

이 멤버 함수는 사용자 인터페이스 스레드 에서만에서 사용 됩니다.

##  <a name="setthreadpriority"></a>  CWinThread::SetThreadPriority

이 함수는 해당 우선 순위 클래스 내에서 현재 스레드의 우선 순위 수준을 설정합니다.

```
BOOL SetThreadPriority(int nPriority);
```

### <a name="parameters"></a>매개 변수

*nPriority*<br/>
해당 우선 순위 클래스 내에서 새 스레드 우선 순위 수준을 지정합니다. 이 매개 변수는 순위가 가장 높은 우선 순위에서 나열 된 다음 값 중 하나 여야 합니다.

- THREAD_PRIORITY_TIME_CRITICAL

- THREAD_PRIORITY_HIGHEST

- THREAD_PRIORITY_ABOVE_NORMAL

- THREAD_PRIORITY_NORMAL

- THREAD_PRIORITY_BELOW_NORMAL

- THREAD_PRIORITY_LOWEST

- THREAD_PRIORITY_IDLE

이러한 우선 순위에 대 한 자세한 내용은 참조 하세요. [SetThreadPriority](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) Windows SDK에 있습니다.

### <a name="return-value"></a>반환 값

함수에 성공 하면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

후에 호출할 수 있습니다 [CreateThread](#createthread) 성공적으로 반환 합니다.

##  <a name="suspendthread"></a>  CWinThread::SuspendThread

현재 증가 스레드의 개수를 일시 중단 합니다.

```
DWORD SuspendThread();
```

### <a name="return-value"></a>반환 값

스레드의 이전 일시 중단 횟수가 성공할 경우 `0xFFFFFFFF` 그렇지 않은 경우.

### <a name="remarks"></a>설명

모든 스레드를 일시 중단 횟수가 0 이상에 있는 경우 해당 스레드는 실행 되지 않습니다. 스레드를 호출 하 여 다시 시작할 수 있습니다 합니다 [ResumeThread](#resumethread) 멤버 함수입니다.

## <a name="see-also"></a>참고자료

[CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CWinApp 클래스](../../mfc/reference/cwinapp-class.md)<br/>
[CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)
