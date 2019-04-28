---
title: CAtlServiceModuleT 클래스
ms.date: 11/04/2016
f1_keywords:
- CAtlServiceModuleT
- ATLBASE/ATL::CAtlServiceModuleT
- ATLBASE/ATL::CAtlServiceModuleT::CAtlServiceModuleT
- ATLBASE/ATL::CAtlServiceModuleT::Handler
- ATLBASE/ATL::CAtlServiceModuleT::InitializeSecurity
- ATLBASE/ATL::CAtlServiceModuleT::Install
- ATLBASE/ATL::CAtlServiceModuleT::IsInstalled
- ATLBASE/ATL::CAtlServiceModuleT::LogEvent
- ATLBASE/ATL::CAtlServiceModuleT::OnContinue
- ATLBASE/ATL::CAtlServiceModuleT::OnInterrogate
- ATLBASE/ATL::CAtlServiceModuleT::OnPause
- ATLBASE/ATL::CAtlServiceModuleT::OnShutdown
- ATLBASE/ATL::CAtlServiceModuleT::OnStop
- ATLBASE/ATL::CAtlServiceModuleT::OnUnknownRequest
- ATLBASE/ATL::CAtlServiceModuleT::ParseCommandLine
- ATLBASE/ATL::CAtlServiceModuleT::PreMessageLoop
- ATLBASE/ATL::CAtlServiceModuleT::RegisterAppId
- ATLBASE/ATL::CAtlServiceModuleT::Run
- ATLBASE/ATL::CAtlServiceModuleT::ServiceMain
- ATLBASE/ATL::CAtlServiceModuleT::SetServiceStatus
- ATLBASE/ATL::CAtlServiceModuleT::Start
- ATLBASE/ATL::CAtlServiceModuleT::Uninstall
- ATLBASE/ATL::CAtlServiceModuleT::Unlock
- ATLBASE/ATL::CAtlServiceModuleT::UnregisterAppId
- ATLBASE/ATL::CAtlServiceModuleT::WinMain
- ATLBASE/ATL::CAtlServiceModuleT::m_bService
- ATLBASE/ATL::CAtlServiceModuleT::m_dwThreadID
- ATLBASE/ATL::CAtlServiceModuleT::m_hServiceStatus
- ATLBASE/ATL::CAtlServiceModuleT::m_status
- ATLBASE/ATL::CAtlServiceModuleT::m_szServiceName
helpviewer_keywords:
- CAtlServiceModuleT class
ms.assetid: 8fc753ce-4a50-402b-9b4a-0a4ce5dd496c
ms.openlocfilehash: 2d4d5d4a5c4d8a52f792cc04a968974967c1e13a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62260203"
---
# <a name="catlservicemodulet-class"></a>CAtlServiceModuleT 클래스

이 클래스는 서비스를 구현합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <class T, UINT nServiceNameID>
class ATL_NO_VTABLE CAtlServiceModuleT : public CAtlExeModuleT<T>
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
클래스에서 파생 된 `CAtlServiceModuleT`합니다.

*nServiceNameID*<br/>
서비스의 리소스 식별자입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CAtlServiceModuleT::CAtlServiceModuleT](#catlservicemodulet)|생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CAtlServiceModuleT::Handler](#handler)|서비스에 대 한 처리기 루틴입니다.|
|[CAtlServiceModuleT::InitializeSecurity](#initializesecurity)|기본 서비스에 대 한 보안 설정을 제공합니다.|
|[CAtlServiceModuleT::Install](#install)|설치 하 고 서비스를 만듭니다.|
|[CAtlServiceModuleT::IsInstalled](#isinstalled)|서비스가 설치 되어 있는지 확인 합니다.|
|[CAtlServiceModuleT::LogEvent](#logevent)|이벤트 로그에 씁니다.|
|[CAtlServiceModuleT::OnContinue](#oncontinue)|서비스를 계속 하려면이 메서드를 재정의 합니다.|
|[CAtlServiceModuleT::OnInterrogate](#oninterrogate)|서비스를 조사 하려면이 메서드를 재정의 합니다.|
|[CAtlServiceModuleT::OnPause](#onpause)|서비스를 일시 중지 하려면이 메서드를 재정의 합니다.|
|[CAtlServiceModuleT::OnShutdown](#onshutdown)|서비스를 종료 하려면이 메서드를 재정의 합니다.|
|[CAtlServiceModuleT::OnStop](#onstop)|서비스를 중지 하려면이 메서드를 재정의 합니다.|
|[CAtlServiceModuleT::OnUnknownRequest](#onunknownrequest)|서비스에 알 수 없는 요청을 처리 하려면이 메서드를 재정의 합니다.|
|[CAtlServiceModuleT::ParseCommandLine](#parsecommandline)|명령줄을 구문 분석 하 고 필요한 경우 등록을 수행 합니다.|
|[CAtlServiceModuleT::PreMessageLoop](#premessageloop)|이 메서드는 메시지 루프에 들어가기 직전에 호출 됩니다.|
|[CAtlServiceModuleT::RegisterAppId](#registerappid)|레지스트리에 서비스를 등록합니다.|
|[CAtlServiceModuleT::Run](#run)|서비스를 실행 합니다.|
|[CAtlServiceModuleT::ServiceMain](#servicemain)|서비스 제어 관리자에 의해 호출 된 메서드가 있습니다.|
|[CAtlServiceModuleT::SetServiceStatus](#setservicestatus)|서비스 상태를 업데이트합니다.|
|[CAtlServiceModuleT::Start](#start)|호출한 `CAtlServiceModuleT::WinMain` 서비스가 시작할 때입니다.|
|[CAtlServiceModuleT::Uninstall](#uninstall)|중지 하 고 서비스를 제거 합니다.|
|[CAtlServiceModuleT::Unlock](#unlock)|서비스의 잠금 횟수를 줄입니다.|
|[CAtlServiceModuleT::UnregisterAppId](#unregisterappid)|레지스트리에서 서비스를 제거합니다.|
|[CAtlServiceModuleT::WinMain](#winmain)|이 메서드는 서비스를 실행 하는 데 필요한 코드를 구현 합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CAtlServiceModuleT::m_bService](#m_bservice)|서비스로 실행 되 고 프로그램을 나타내는 플래그입니다.|
|[CAtlServiceModuleT::m_dwThreadID](#m_dwthreadid)|스레드 식별자를 저장 하는 멤버 변수입니다.|
|[CAtlServiceModuleT::m_hServiceStatus](#m_hservicestatus)|현재 서비스에 대 한 상태 정보 구조체에 대 한 핸들을 저장 하는 멤버 변수입니다.|
|[CAtlServiceModuleT::m_status](#m_status)|현재 서비스에 대 한 상태 정보 구조를 저장 하는 멤버 변수입니다.|
|[CAtlServiceModuleT::m_szServiceName](#m_szservicename)|등록할 서비스의 이름입니다.|

## <a name="remarks"></a>설명

`CAtlServiceModuleT`에서 파생 된 [CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md), ATL 서비스 모듈을 구현 합니다. `CAtlServiceModuleT` 명령줄 처리, 설치, 등록 및 제거에 대 한 메서드를 제공 합니다. 추가 기능이 필요한 경우 이러한 메서드와 다른 재정의할 수 있습니다.

이 클래스는 사용 되지 않는 대체 [CComModule 클래스](../../atl/reference/ccommodule-class.md) ATL.의 이전 버전에서 사용 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

[CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)

`CAtlServiceModuleT`

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

##  <a name="catlservicemodulet"></a>  CAtlServiceModuleT::CAtlServiceModuleT

생성자입니다.

```
CAtlServiceModuleT() throw();
```

### <a name="remarks"></a>설명

데이터 멤버를 초기화 하 고 초기 서비스의 상태를 설정 합니다.

##  <a name="handler"></a>  CAtlServiceModuleT::Handler

서비스에 대 한 처리기 루틴입니다.

```
void Handler(DWORD dwOpcode) throw();
```

### <a name="parameters"></a>매개 변수

*dwOpcode*<br/>
처리기 작업을 정의 하는 스위치입니다. 자세한 내용은 설명을 참조 하세요.

### <a name="remarks"></a>설명

서비스 제어 관리자 (SCM) 호출 일시 중지 또는 중지와 같은 서비스 및 문제 지침의 상태를 검색 하는 코드입니다. SCM에 아래에 나와 있는 작업 코드를 전달 `Handler` 서비스가 수행할 동작을 나타냅니다.

|작업 코드|의미|
|--------------------|-------------|
|SERVICE_CONTROL_STOP|서비스를 중지합니다. 메서드 재정의 [CAtlServiceModuleT::OnStop](#onstop) 동작을 변경 하는 atlbase.h에서.|
|SERVICE_CONTROL_PAUSE|사용자를 구현 합니다. 빈 메서드 재정의 [CAtlServiceModuleT::OnPause](#onpause) 서비스를 일시 중지 하는 atlbase.h에서.|
|SERVICE_CONTROL_CONTINUE|사용자를 구현 합니다. 빈 메서드 재정의 [CAtlServiceModuleT::OnContinue](#oncontinue) 서비스를 계속 하려면 atlbase.h에서.|
|SERVICE_CONTROL_INTERROGATE|사용자를 구현 합니다. 빈 메서드 재정의 [CAtlServiceModuleT::OnInterrogate](#oninterrogate) 서비스를 질의 하는 atlbase.h에서.|
|SERVICE_CONTROL_SHUTDOWN|사용자를 구현 합니다. 빈 메서드 재정의 [CAtlServiceModuleT::OnShutdown](#onshutdown) 서비스를 종료 하는 atlbase.h에서.|

작업 코드 인식 되지 않는 경우 메서드가 [CAtlServiceModuleT::OnUnknownRequest](#onunknownrequest) 라고 합니다.

기본 ATL 생성 서비스 중지 명령을 처리합니다. 중지 명령이 SCM를 통과 하면 서비스 인지 여부를 SCM는 프로그램을 중지 하려고 합니다. 서비스 호출 `PostThreadMessage` 자신에 게 종료 메시지를 게시 합니다. 메시지 루프를 종료 하 고 서비스를 궁극적으로 닫힙니다.

##  <a name="initializesecurity"></a>  CAtlServiceModuleT::InitializeSecurity

기본 서비스에 대 한 보안 설정을 제공합니다.

```
HRESULT InitializeSecurity() throw();
```

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

Visual Studio.NET 2003에서이 메서드가 기본 클래스에서 구현 되지 않습니다. Visual Studio 프로젝트 마법사에서 생성된 된 코드에서이 메서드를 포함 하지만 경우 시각적 개체의 이전 버전에서 만든 프로젝트를 컴파일 오류가 발생 합니다 C++ ATL 7.1을 사용 하 여 컴파일됩니다. 파생 되는 모든 클래스 `CAtlServiceModuleT` 파생된 클래스에서이 메서드를 구현 해야 합니다.

호출에서 PKT 수준 인증, RPC_C_IMP_LEVEL_IDENTIFY의 가장 수준 및 적절 한 null이 아닌 보안 설명자를 사용 하 여 `CoInitializeSecurity`입니다.

마법사 생성 하지 않는 서비스 프로젝트의 경우이 설정 됩니다.

[!code-cpp[NVC_ATL_Service#1](../../atl/reference/codesnippet/cpp/catlservicemodulet-class_1.cpp)]

특성이 지정 된 서비스 프로젝트의 경우이 설정 됩니다.

[!code-cpp[NVC_ATL_ServiceAttrib#1](../../atl/reference/codesnippet/cpp/catlservicemodulet-class_2.cpp)]

##  <a name="install"></a>  CAtlServiceModuleT::Install

설치 하 고 서비스를 만듭니다.

```
BOOL Install() throw();
```

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

서비스 제어 관리자 (SCM) 데이터베이스로 서비스를 설치 하 고 그런 다음 서비스 개체를 만듭니다. 서비스를 만들 수 없습니다, 하는 경우 메시지 상자가 표시 되 고 메서드가 FALSE를 반환 합니다.

##  <a name="isinstalled"></a>  CAtlServiceModuleT::IsInstalled

서비스가 설치 되어 있는지 확인 합니다.

```
BOOL IsInstalled() throw();
```

### <a name="return-value"></a>반환 값

서비스인 경우 설치 된이 고, FALSE 그렇지 않은 경우 TRUE를 반환 합니다.

##  <a name="logevent"></a>  CAtlServiceModuleT::LogEvent

이벤트 로그에 씁니다.

```
void __cdecl LogEvent(LPCTSTR pszFormat, ...) throw();
```

### <a name="parameters"></a>매개 변수

*pszFormat*<br/>
이벤트 로그에 쓸 문자열입니다.

*...*<br/>
이벤트 로그를 쓸 수 있도록 선택적 추가 문자열입니다.

### <a name="remarks"></a>설명

이 메서드 함수를 사용 하 여 이벤트 로그에 세부 정보를 씁니다 [ReportEvent](/windows/desktop/api/winbase/nf-winbase-reporteventa)합니다. 서비스가 실행 중인 경우 문자열 콘솔로 전송 됩니다.

##  <a name="m_bservice"></a>  CAtlServiceModuleT::m_bService

서비스로 실행 되 고 프로그램을 나타내는 플래그입니다.

```
BOOL m_bService;
```

### <a name="remarks"></a>설명

응용 프로그램 EXE에서 서비스 EXE를 구분 하는 데 사용 합니다.

##  <a name="m_dwthreadid"></a>  CAtlServiceModuleT::m_dwThreadID

멤버 변수를 서비스의 스레드 식별자를 저장 합니다.

```
DWORD m_dwThreadID;
```

### <a name="remarks"></a>설명

이 변수는 현재 스레드의 스레드 식별자를 저장합니다.

##  <a name="m_hservicestatus"></a>  CAtlServiceModuleT::m_hServiceStatus

현재 서비스에 대 한 상태 정보 구조체에 대 한 핸들을 저장 하는 멤버 변수입니다.

```
SERVICE_STATUS_HANDLE m_hServiceStatus;
```

### <a name="remarks"></a>설명

합니다 [SERVICE_STATUS](/windows/desktop/api/winsvc/ns-winsvc-_service_status) 구조는 서비스에 대 한 정보가 들어 있습니다.

##  <a name="m_status"></a>  CAtlServiceModuleT::m_status

현재 서비스에 대 한 상태 정보 구조를 저장 하는 멤버 변수입니다.

```
SERVICE_STATUS m_status;
```

### <a name="remarks"></a>설명

합니다 [SERVICE_STATUS](/windows/desktop/api/winsvc/ns-winsvc-_service_status) 구조는 서비스에 대 한 정보가 들어 있습니다.

##  <a name="m_szservicename"></a>  CAtlServiceModuleT::m_szServiceName

등록할 서비스의 이름입니다.

```
TCHAR [256] m_szServiceName;
```

### <a name="remarks"></a>설명

서비스의 이름을 저장 하는 null로 끝나는 문자열입니다.

##  <a name="oncontinue"></a>  CAtlServiceModuleT::OnContinue

서비스를 계속 하려면이 메서드를 재정의 합니다.

```
void OnContinue() throw();
```

##  <a name="oninterrogate"></a>  CAtlServiceModuleT::OnInterrogate

서비스를 조사 하려면이 메서드를 재정의 합니다.

```
void OnInterrogate() throw();
```

##  <a name="onpause"></a>  CAtlServiceModuleT::OnPause

서비스를 일시 중지 하려면이 메서드를 재정의 합니다.

```
void OnPause() throw();
```

##  <a name="onshutdown"></a>  CAtlServiceModuleT::OnShutdown

서비스를 종료 하려면이 메서드를 재정의 합니다.

```
void OnShutdown() throw();
```

##  <a name="onstop"></a>  CAtlServiceModuleT::OnStop

서비스를 중지 하려면이 메서드를 재정의 합니다.

```
void OnStop() throw();
```

##  <a name="onunknownrequest"></a>  CAtlServiceModuleT::OnUnknownRequest

서비스에 알 수 없는 요청을 처리 하려면이 메서드를 재정의 합니다.

```
void OnUnknownRequest(DWORD /* dwOpcode*/) throw();
```

### <a name="parameters"></a>매개 변수

*dwOpcode*<br/>
예약됨.

##  <a name="parsecommandline"></a>  CAtlServiceModuleT::ParseCommandLine

명령줄을 구문 분석 하 고 필요한 경우 등록을 수행 합니다.

```
bool ParseCommandLine(LPCTSTR lpCmdLine, HRESULT* pnRetCode) throw();
```

### <a name="parameters"></a>매개 변수

*lpCmdLine*<br/>
명령줄입니다.

*pnRetCode*<br/>
(발생 해당) 하는 경우 해당 등록 하는 HRESULT입니다.

### <a name="return-value"></a>반환 값

성공 또는 명령줄에 제공 된 RGS 파일 등록 하지 못한 경우 false에서 true를 반환 합니다.

### <a name="remarks"></a>설명

명령줄을 구문 분석 및 등록 하거나 필요한 경우 제공 된 RGS 파일의 등록을 취소 합니다. 이 메서드를 호출 [CAtlExeModuleT::ParseCommandLine](../../atl/reference/catlexemodulet-class.md#parsecommandline) 확인할 **/RegServer** 하 고 **/UnregServer**합니다. 인수를 추가 **-서비스 /** 서비스를 등록 합니다.

##  <a name="premessageloop"></a>  CAtlServiceModuleT::PreMessageLoop

이 메서드는 메시지 루프에 들어가기 직전에 호출 됩니다.

```
HRESULT PreMessageLoop(int nShowCmd) throw();
```

### <a name="parameters"></a>매개 변수

*nShowCmd*<br/>
이 매개 변수가 전달 [CAtlExeModuleT::PreMessageLoop](../../atl/reference/catlexemodulet-class.md#premessageloop)합니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

서비스에 대 한 사용자 지정 초기화 코드를 추가 하려면이 메서드를 재정의 합니다.

##  <a name="registerappid"></a>  CAtlServiceModuleT::RegisterAppId

레지스트리에 서비스를 등록합니다.

```
inline HRESULT RegisterAppId(bool bService = false) throw();
```

### <a name="parameters"></a>매개 변수

*bService*<br/>
서비스로 등록 하려면 true 여야 합니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="run"></a>  CAtlServiceModuleT::Run

서비스를 실행 합니다.

```
HRESULT Run(int nShowCmd = SW_HIDE) throw();
```

### <a name="parameters"></a>매개 변수

*nShowCmd*<br/>
창 표시 방법을 지정 합니다. 이 매개 변수에서 설명 하는 값 중 하나일 수 있습니다 합니다 [WinMain](/windows/desktop/api/winbase/nf-winbase-winmain) 섹션입니다. 기본값은 SW_HIDE 합니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

호출 된 후 `Run` 호출 [CAtlServiceModuleT::PreMessageLoop](#premessageloop)하십시오 [CAtlExeModuleT::RunMessageLoop](../../atl/reference/catlexemodulet-class.md#runmessageloop), 및 [CAtlExeModuleT::PostMessageLoop](../../atl/reference/catlexemodulet-class.md#postmessageloop).

##  <a name="servicemain"></a>  CAtlServiceModuleT::ServiceMain

이 메서드는 서비스 제어 관리자에 의해 호출 됩니다.

```
void ServiceMain(DWORD dwArgc, LPTSTR* lpszArgv) throw();
```

### <a name="parameters"></a>매개 변수

*dwArgc*<br/>
Argc 인수입니다.

*lpszArgv*<br/>
Argv 인수입니다.

### <a name="remarks"></a>설명

서비스 제어 관리자 (SCM) 호출 하 여 `ServiceMain` 제어판에서 서비스 응용 프로그램을 열면 서비스를 선택 하 고 시작을 클릭 합니다.

호출 후 SCM `ServiceMain`, 서비스는 SCM 처리기 함수를 제공 해야 합니다. 이 함수를 사용 하면 서비스의 상태를 가져오고 (예: 일시 중지 또는 중지) 특정 지침을 전달 하는 SCM이 있습니다. 이후에 [catlservicemodulet:: Run](#run) 서비스의 기본 작업을 수행 하기 위해 호출 됩니다. `Run` 서비스가 중지 될 때까지 실행을 계속 합니다.

##  <a name="setservicestatus"></a>  CAtlServiceModuleT::SetServiceStatus

이 메서드는 서비스의 상태를 업데이트합니다.

```
void SetServiceStatus(DWORD dwState) throw();
```

### <a name="parameters"></a>매개 변수

*dwState*<br/>
새 상태입니다. 참조 [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) 가능한 값에 대 한 합니다.

### <a name="remarks"></a>설명

서비스에 대 한 서비스 제어 관리자의 상태 정보를 업데이트합니다. 에 의해 호출 됩니다 [catlservicemodulet:: Run](#run)하십시오 [catlservicemodulet:: Servicemain](#servicemain) 및 기타 처리기 메서드. 상태는 멤버 변수에 저장 된 수도 [CAtlServiceModuleT::m_status](#m_status)합니다.

##  <a name="start"></a>  CAtlServiceModuleT::Start

호출한 `CAtlServiceModuleT::WinMain` 서비스가 시작할 때입니다.

```
HRESULT Start(int nShowCmd) throw();
```

### <a name="parameters"></a>매개 변수

*nShowCmd*<br/>
창 표시 방법을 지정 합니다. 이 매개 변수에서 설명 하는 값 중 하나일 수 있습니다 합니다 [WinMain](/windows/desktop/api/winbase/nf-winbase-winmain) 섹션입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

합니다 [CAtlServiceModuleT::WinMain](#winmain) 메서드는 등록 및 설치를 모두 처리 뿐만 아니라 작업 관련 레지스트리 항목을 제거 하 고 모듈을 제거 합니다. 서비스가 실행 되 면 `WinMain` 호출 `Start`합니다.

##  <a name="uninstall"></a>  CAtlServiceModuleT::Uninstall

중지 하 고 서비스를 제거 합니다.

```
BOOL Uninstall() throw();
```

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

실행에서 서비스를 중지 하 고 서비스 제어 관리자 데이터베이스에서 제거 합니다.

##  <a name="unlock"></a>  CAtlServiceModuleT::Unlock

서비스의 잠금 횟수를 줄입니다.

```
LONG Unlock() throw();
```

### <a name="return-value"></a>반환 값

디버깅 및 진단에 대 한 일 수 있는 잠금 수를 반환 합니다.

##  <a name="unregisterappid"></a>  CAtlServiceModuleT::UnregisterAppId

레지스트리에서 서비스를 제거합니다.

```
HRESULT UnregisterAppId() throw();
```

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="winmain"></a>  CAtlServiceModuleT::WinMain

이 메서드는 서비스를 시작 하는 데 필요한 코드를 구현 합니다.

```
int WinMain(int nShowCmd) throw();
```

### <a name="parameters"></a>매개 변수

*nShowCmd*<br/>
창 표시 방법을 지정 합니다. 이 매개 변수에서 설명 하는 값 중 하나일 수 있습니다 합니다 [WinMain](/windows/desktop/api/winbase/nf-winbase-winmain) 섹션입니다.

### <a name="return-value"></a>반환 값

서비스의 반환 값을 반환합니다.

### <a name="remarks"></a>설명

이 메서드는 명령줄 처리 (사용 하 여 [CAtlServiceModuleT::ParseCommandLine](#parsecommandline)) 서비스 시작 (사용 하 여 [catlservicemodulet:: Start](#start)).

## <a name="see-also"></a>참고자료

[CAtlExeModuleT 클래스](../../atl/reference/catlexemodulet-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
