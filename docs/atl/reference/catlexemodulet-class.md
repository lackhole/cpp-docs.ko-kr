---
title: CAtlExeModuleT 클래스
ms.date: 11/04/2016
f1_keywords:
- CAtlExeModuleT
- ATLBASE/ATL::CAtlExeModuleT
- ATLBASE/ATL::CAtlExeModuleT::CAtlExeModuleT
- ATLBASE/ATL::CAtlExeModuleT::InitializeCom
- ATLBASE/ATL::CAtlExeModuleT::ParseCommandLine
- ATLBASE/ATL::CAtlExeModuleT::PostMessageLoop
- ATLBASE/ATL::CAtlExeModuleT::PreMessageLoop
- ATLBASE/ATL::CAtlExeModuleT::RegisterClassObjects
- ATLBASE/ATL::CAtlExeModuleT::RevokeClassObjects
- ATLBASE/ATL::CAtlExeModuleT::Run
- ATLBASE/ATL::CAtlExeModuleT::RunMessageLoop
- ATLBASE/ATL::CAtlExeModuleT::UninitializeCom
- ATLBASE/ATL::CAtlExeModuleT::Unlock
- ATLBASE/ATL::CAtlExeModuleT::WinMain
- ATLBASE/ATL::CAtlExeModuleT::m_bDelayShutdown
- ATLBASE/ATL::CAtlExeModuleT::m_dwPause
- ATLBASE/ATL::CAtlExeModuleT::m_dwTimeOut
helpviewer_keywords:
- CAtlExeModuleT class
ms.assetid: 82245f3d-91d4-44fa-aa86-7cc7fbd758d9
ms.openlocfilehash: 87e526a10c9bcd6a52f4544c50344c5145cfa732
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58769552"
---
# <a name="catlexemodulet-class"></a>CAtlExeModuleT 클래스

이 클래스는 응용 프로그램에 대 한 모듈을 나타냅니다.

## <a name="syntax"></a>구문

```
template <class T>
class ATL_NO_VTABLE CAtlExeModuleT : public CAtlModuleT<T>
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
클래스에서 파생 된 `CAtlExeModuleT`합니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CAtlExeModuleT::CAtlExeModuleT](#catlexemodulet)|생성자입니다.|
|[CAtlExeModuleT::~CAtlExeModuleT](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CAtlExeModuleT::InitializeCom](#initializecom)|COM.를 초기화합니다.|
|[CAtlExeModuleT::ParseCommandLine](#parsecommandline)|명령줄을 구문 분석 하 고 필요한 경우 등록을 수행 합니다.|
|[CAtlExeModuleT::PostMessageLoop](#postmessageloop)|이 메서드는 메시지 루프를 종료 한 직후에 호출 됩니다.|
|[CAtlExeModuleT::PreMessageLoop](#premessageloop)|이 메서드는 메시지 루프에 들어가기 직전에 호출 됩니다.|
|[CAtlExeModuleT::RegisterClassObjects](#registerclassobjects)|클래스 개체를 등록합니다.|
|[CAtlExeModuleT::RevokeClassObjects](#revokeclassobjects)|클래스 개체를 취소합니다.|
|[CAtlExeModuleT::Run](#run)|이 메서드는 메시지 루프 실행을 초기화할 EXE 모듈의 코드를 실행 하 고 정리 합니다.|
|[CAtlExeModuleT::RunMessageLoop](#runmessageloop)|이 메서드는 메시지 루프를 실행합니다.|
|[CAtlExeModuleT::UninitializeCom](#uninitializecom)|COM.를 초기화 하지 않습니다.|
|[CAtlExeModuleT::Unlock](#unlock)|모듈의 잠금 횟수를 줄입니다.|
|[CAtlExeModuleT::WinMain](#winmain)|이 메서드는 EXE를 실행 하는 데 필요한 코드를 구현 합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CAtlExeModuleT::m_bDelayShutdown](#m_bdelayshutdown)|모듈을 종료 하는 지연 되도록 나타내는 플래그입니다.|
|[CAtlExeModuleT::m_dwPause](#m_dwpause)|개체를 모두 종료 되기 전에 해제 되도록 하는 데 사용 되는 일시 중지 값입니다.|
|[CAtlExeModuleT::m_dwTimeOut](#m_dwtimeout)|모듈 언로드를 지연 하는 데 사용 되는 시간 제한 값입니다.|

## <a name="remarks"></a>설명

`CAtlExeModuleT` 응용 프로그램 (EXE)에 대 한 모듈을 나타내며 종료 시 만들어 EXE 명령줄 처리, 클래스 개체를 등록, 메시지 루프를 실행 하며 정리를 지 원하는 코드를 포함 합니다.

이 클래스는 COM 개체 EXE 서버에서 지속적으로 생성 되 고 제거 하는 경우 성능 향상을 위해 설계 되었습니다. Exe 파일의 지정 된 기간 동안 대기 마지막 COM 개체 해제 된 후의 [CAtlExeModuleT::m_dwTimeOut](#m_dwtimeout) 데이터 멤버입니다. 이 기간 동안 활동이 없는 경우 (즉, COM 개체가 만들어지면)는 종료 프로세스 시작 됩니다.

합니다 [CAtlExeModuleT::m_bDelayShutdown](#m_bdelayshutdown) 데이터 멤버는 EXE 위에 정의 된 메커니즘을 사용 해야 하는 경우를 결정 하는 데 사용 하는 플래그입니다. False로 설정 됩니다, 모듈 즉시 종료 됩니다.

ATL에서 모듈에 대 한 자세한 내용은 참조 하세요. [ATL 모듈 클래스](../../atl/atl-module-classes.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

`CAtlExeModuleT`

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

##  <a name="catlexemodulet"></a>  CAtlExeModuleT::CAtlExeModuleT

생성자입니다.

```
CAtlExeModuleT() throw();
```

### <a name="remarks"></a>설명

EXE 모듈을 초기화할 수 없습니다, 경우 WinMain 추가적인 처리 없이 즉시 반환 됩니다.

##  <a name="dtor"></a>  CAtlExeModuleT::~CAtlExeModuleT

소멸자입니다.

```
~CAtlExeModuleT() throw();
```

### <a name="remarks"></a>설명

할당 된 모든 리소스를 해제합니다.

##  <a name="initializecom"></a>  CAtlExeModuleT::InitializeCom

COM.를 초기화합니다.

```
static HRESULT InitializeCom() throw();
```

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

이 메서드는 생성자에서 호출 되며 기본 구현에서 다른 방법으로 COM을 초기화 하기 위해 재정의할 수 있습니다. 기본 구현 하거나 호출 `CoInitializeEx(NULL, COINIT_MULTITHREADED)` 또는 `CoInitialize(NULL)` 프로젝트 구성에 따라 합니다.

재정의 해야 일반적으로이 메서드를 재정의 [CAtlExeModuleT::UninitializeCom](#uninitializecom)합니다.

##  <a name="m_bdelayshutdown"></a>  CAtlExeModuleT::m_bDelayShutdown

모듈을 종료 하는 지연 되도록 나타내는 플래그입니다.

```
bool m_bDelayShutdown;
```

### <a name="remarks"></a>설명

참조 된 [CAtlExeModuleT 개요](../../atl/reference/catlexemodulet-class.md) 세부 정보에 대 한 합니다.

##  <a name="m_dwpause"></a>  CAtlExeModuleT::m_dwPause

모든 개체는 종료 되기 전에 완료를 확인 하는 데 사용 되는 일시 중지 값입니다.

```
DWORD m_dwPause;
```

### <a name="remarks"></a>설명

호출한 후이 값을 변경 [CAtlExeModuleT::InitializeCom](#initializecom) 서버를 종료 하는 것에 대 한 일시 중지 값으로 사용 하는 시간 (밀리초)의 수를 설정 합니다. 기본값은 1000 밀리초입니다.

##  <a name="m_dwtimeout"></a>  CAtlExeModuleT::m_dwTimeOut

모듈 언로드를 지연 하는 데 사용 되는 시간 제한 값입니다.

```
DWORD m_dwTimeOut;
```

### <a name="remarks"></a>설명

호출한 후이 값을 변경 [CAtlExeModuleT::InitializeCom](#initializecom) 서버를 종료 하는 것에 대 한 제한 시간 값으로 사용 하는 시간 (밀리초)의 수를 정의 합니다. 기본값은 5000밀리초입니다. 참조 된 [CAtlExeModuleT 개요](../../atl/reference/catlexemodulet-class.md) 대 한 자세한 내용은 합니다.

##  <a name="parsecommandline"></a>  CAtlExeModuleT::ParseCommandLine

명령줄을 구문 분석 하 고 필요한 경우 등록을 수행 합니다.

```
bool ParseCommandLine(LPCTSTR lpCmdLine, HRESULT* pnRetCode) throw();
```

### <a name="parameters"></a>매개 변수

*lpCmdLine*<br/>
명령줄 응용 프로그램에 전달 합니다.

*pnRetCode*<br/>
(발생 해당) 하는 경우 해당 등록 하는 HRESULT입니다.

### <a name="return-value"></a>반환 값

응용 프로그램 실행, 그렇지 않으면 false를 계속 해야 하면 true를 반환 합니다.

### <a name="remarks"></a>설명

이 메서드는 [CAtlExeModuleT::WinMain](#winmain) 명령줄 스위치를 처리 하도록 재정의할 수 있습니다. 기본 구현에 대 한 확인 **/RegServer** 하 고 **/UnRegServer** 명령줄 인수 하 고 등록 또는 등록 취소를 수행 합니다.

##  <a name="postmessageloop"></a>  CAtlExeModuleT::PostMessageLoop

이 메서드는 메시지 루프를 종료 한 직후에 호출 됩니다.

```
HRESULT PostMessageLoop() throw();
```

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

사용자 지정 응용 프로그램 정리를 수행 하려면이 메서드를 재정의 합니다. 기본 구현 호출 [CAtlExeModuleT::RevokeClassObjects](#revokeclassobjects)합니다.

##  <a name="premessageloop"></a>  CAtlExeModuleT::PreMessageLoop

이 메서드는 메시지 루프에 들어가기 직전에 호출 됩니다.

```
HRESULT PreMessageLoop(int nShowCmd) throw();
```

### <a name="parameters"></a>매개 변수

*nShowCmd*<br/>
로 전달 된 값을 *nShowCmd* WinMain에서 매개 변수입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

응용 프로그램에 대 한 사용자 지정 초기화 코드를 추가 하려면이 메서드를 재정의 합니다. 기본 구현은 클래스 개체를 등록합니다.

##  <a name="registerclassobjects"></a>  CAtlExeModuleT::RegisterClassObjects

다른 응용 프로그램에 연결할 수 있도록 OLE를 사용 하 여 클래스 개체를 등록 합니다.

```
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```

### <a name="parameters"></a>매개 변수

*dwClsContext*<br/>
클래스 개체를 실행할의 컨텍스트를 지정 합니다. 가능한 값은 CLSCTX_INPROC_SERVER, CLSCTX_INPROC_HANDLER, 또는 CLSCTX_LOCAL_SERVER입니다.

*dwFlags*<br/>
클래스 개체에 연결 형식을 결정합니다. 가능한 값은 REGCLS_SINGLEUSE, REGCLS_MULTIPLEUSE, 또는 REGCLS_MULTI_SEPARATE입니다.

### <a name="return-value"></a>반환 값

성공, S_FALSE를 등록 하려면 클래스가 있다면 또는 실패 시 오류 HRESULT는 S_OK를 반환 합니다.

##  <a name="revokeclassobjects"></a>  CAtlExeModuleT::RevokeClassObjects

클래스 개체를 제거합니다.

```
HRESULT RevokeClassObjects() throw();
```

### <a name="return-value"></a>반환 값

성공, S_FALSE를 등록 하려면 클래스가 있다면 또는 실패 시 오류 HRESULT는 S_OK를 반환 합니다.

##  <a name="run"></a>  CAtlExeModuleT::Run

이 메서드는 메시지 루프 실행을 초기화할 EXE 모듈의 코드를 실행 하 고 정리 합니다.

```
HRESULT Run(int nShowCmd = SW_HIDE) throw();
```

### <a name="parameters"></a>매개 변수

*nShowCmd*<br/>
창 표시 방법을 지정 합니다. 이 매개 변수에서 설명 하는 값 중 하나일 수 있습니다 합니다 [WinMain](/windows/desktop/api/winbase/nf-winbase-winmain) 섹션입니다. SW_HIDE 기본값은입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

이 메서드를 재정의할 수 있습니다. 그러나 실제로 것이 더 재정의할 [CAtlExeModuleT::PreMessageLoop](#premessageloop)를 [CAtlExeModuleT::RunMessageLoop](#runmessageloop), 또는 [CAtlExeModuleT::PostMessageLoop](#postmessageloop) 대신 합니다.

##  <a name="runmessageloop"></a>  CAtlExeModuleT::RunMessageLoop

이 메서드는 메시지 루프를 실행합니다.

```
void RunMessageLoop() throw();
```

### <a name="remarks"></a>설명

메시지 루프의 동작을 변경 하려면이 메서드를 재정의할 수 있습니다.

##  <a name="uninitializecom"></a>  CAtlExeModuleT::UninitializeCom

COM.를 초기화 하지 않습니다.

```
static void UninitializeCom() throw();
```

### <a name="remarks"></a>설명

기본적으로이 메서드를 호출 [CoUninitialize](/windows/desktop/api/combaseapi/nf-combaseapi-couninitialize) 소멸자에서 호출 됩니다. 이 메서드를 재정의 하는 경우 재정의 [CAtlExeModuleT::InitializeCom](#initializecom)합니다.

##  <a name="unlock"></a>  CAtlExeModuleT::Unlock

모듈의 잠금 횟수를 줄입니다.

```
LONG Unlock() throw();
```

### <a name="return-value"></a>반환 값

진단에 대 한 유용한 또는 테스트 값을 반환 합니다.

##  <a name="winmain"></a>  CAtlExeModuleT::WinMain

이 메서드는 EXE를 실행 하는 데 필요한 코드를 구현 합니다.

```
int WinMain(int nShowCmd) throw();
```

### <a name="parameters"></a>매개 변수

*nShowCmd*<br/>
창 표시 방법을 지정 합니다. 이 매개 변수에서 설명 하는 값 중 하나일 수 있습니다 합니다 [WinMain](/windows/desktop/api/winbase/nf-winbase-winmain) 섹션입니다.

### <a name="return-value"></a>반환 값

실행 파일의 반환 값을 반환합니다.

### <a name="remarks"></a>설명

이 메서드를 재정의할 수 있습니다. 재정의 하는 경우 [CAtlExeModuleT::PreMessageLoop](#premessageloop)하십시오 [CAtlExeModuleT::PostMessageLoop](#postmessageloop), 또는 [CAtlExeModuleT::RunMessageLoop](#runmessageloop) 충분 한 유연성을 제공 하지 않습니다 를 재정의할 수는 `WinMain` 이 메서드를 사용 하 여 작동 합니다.

## <a name="see-also"></a>참고자료

[ATLDuck 샘플](../../overview/visual-cpp-samples.md)<br/>
[CAtlModuleT 클래스](../../atl/reference/catlmodulet-class.md)<br/>
[CAtlDllModuleT 클래스](../../atl/reference/catldllmodulet-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
