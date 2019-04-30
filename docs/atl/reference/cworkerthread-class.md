---
title: CWorkerThread 클래스
ms.date: 11/04/2016
f1_keywords:
- CWorkerThread
- ATLUTIL/ATL::CWorkerThread
- ATLUTIL/ATL::CWorkerThread::CWorkerThread
- ATLUTIL/ATL::CWorkerThread::AddHandle
- ATLUTIL/ATL::CWorkerThread::AddTimer
- ATLUTIL/ATL::CWorkerThread::GetThreadHandle
- ATLUTIL/ATL::CWorkerThread::GetThreadId
- ATLUTIL/ATL::CWorkerThread::Initialize
- ATLUTIL/ATL::CWorkerThread::RemoveHandle
- ATLUTIL/ATL::CWorkerThread::Shutdown
helpviewer_keywords:
- CWorkerThread class
ms.assetid: be79a832-1345-4a36-a13e-a406cc65286f
ms.openlocfilehash: d4645f4a57ce70c3683972c22e0f99cbce87ca6b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62276661"
---
# <a name="cworkerthread-class"></a>CWorkerThread 클래스

이 클래스 작업자 스레드를 만듭니다 또는 기존 항목을 사용 하 여, 하나 이상의 커널 개체 핸들에서 대기 및 핸들 중 하나에 신호가 전달 될 때 지정 된 클라이언트 함수를 실행 합니다.

> [!IMPORTANT]
> 이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <class ThreadTraits = DefaultThreadTraits>
class CWorkerThread
```

### <a name="parameters"></a>매개 변수

*ThreadTraits*<br/>
와 같은 스레드 생성 함수를 제공 하는 클래스 [CRTThreadTraits](../../atl/reference/crtthreadtraits-class.md) 하거나 [Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md)합니다.

## <a name="members"></a>멤버

### <a name="protected-structures"></a>보호 된 구조

|이름|설명|
|----------|-----------------|
|`WorkerClientEntry`||

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CWorkerThread::CWorkerThread](#cworkerthread)|작업자 스레드에 대 한 생성자입니다.|
|[CWorkerThread::~CWorkerThread](#dtor)|작업자 스레드에 대 한 소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CWorkerThread::AddHandle](#addhandle)|작업자 스레드에 의해 유지 관리 목록에는 대기 가능 개체의 핸들을 추가 하려면이 메서드를 호출 합니다.|
|[CWorkerThread::AddTimer](#addtimer)|대기 가능 주기적 타이머 작업자 스레드에 의해 유지 관리 목록에 추가 하려면이 메서드를 호출 합니다.|
|[CWorkerThread::GetThreadHandle](#getthreadhandle)|작업자 스레드의 스레드 핸들을 가져오려면이 메서드를 호출 합니다.|
|[CWorkerThread::GetThreadId](#getthreadid)|작업자 스레드의 스레드 ID를 가져오려면이 메서드를 호출 합니다.|
|[CWorkerThread::Initialize](#initialize)|작업자 스레드를 초기화 하려면이 메서드를 호출 합니다.|
|[CWorkerThread::RemoveHandle](#removehandle)|핸들을 대기 가능 개체의 목록에서 제거 하려면이 메서드를 호출 합니다.|
|[CWorkerThread::Shutdown](#shutdown)|작업자 스레드를 종료 하려면이 메서드를 호출 합니다.|

## <a name="remarks"></a>설명

### <a name="to-use-cworkerthread"></a>CWorkerThread를 사용 하려면

1. 이 클래스의 인스턴스를 만듭니다.

1. 호출 [CWorkerThread::Initialize](#initialize)합니다.

1. 호출 [CWorkerThread::AddHandle](#addhandle) 커널 개체와의 구현에 대 한 핸들로 [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md)합니다.

   \- 또는 -

   호출 [CWorkerThread::AddTimer](#addtimer) 의 구현에 대 한 포인터를 사용 하 여 [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md)합니다.

1. 구현 [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) 핸들 또는 타이머 신호를 받는 경우 몇 가지 작업을 수행 하 합니다.

1. 대기 가능 개체의 목록에서 개체를 제거 하려면 호출 [CWorkerThread::RemoveHandle](#removehandle)합니다.

1. 호출 스레드를 종료 하려면 [CWorkerThread::Shutdown](#shutdown)합니다.

## <a name="requirements"></a>요구 사항

**헤더:** 와 atlutil.h

##  <a name="addhandle"></a>  CWorkerThread::AddHandle

작업자 스레드에 의해 유지 관리 목록에는 대기 가능 개체의 핸들을 추가 하려면이 메서드를 호출 합니다.

```
HRESULT AddHandle(
    HANDLE hObject,
    IWorkerThreadClient* pClient,
    DWORD_PTR dwParam) throw();
```

### <a name="parameters"></a>매개 변수

*hObject*<br/>
대기 가능 개체에 대 한 핸들입니다.

*pClient*<br/>
에 대 한 포인터를 [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md) 핸들 신호가 전달 될 때 호출할 개체의 인터페이스입니다.

*dwParam*<br/>
에 전달할 매개 변수 [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) 핸들이 신호를 받을 때입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

[IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) 를 통해 호출할 *pClient* 때 핸들을 *hObject*, 신호를 받을.

##  <a name="addtimer"></a>  CWorkerThread::AddTimer

대기 가능 주기적 타이머 작업자 스레드에 의해 유지 관리 목록에 추가 하려면이 메서드를 호출 합니다.

```
HRESULT AddTimer(
    DWORD dwInterval,
    IWorkerThreadClient* pClient,
    DWORD_PTR dwParam,
    HANDLE* phTimer) throw();
```

### <a name="parameters"></a>매개 변수

*dwInterval*<br/>
타이머의 기간을 밀리초 단위로 지정 합니다.

*pClient*<br/>
에 대 한 포인터를 [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md) 핸들 신호가 전달 될 때 호출할 개체의 인터페이스입니다.

*dwParam*<br/>
에 전달할 매개 변수 [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) 핸들이 신호를 받을 때입니다.

*phTimer*<br/>
[out] 성공 하면 새로 만든된 타이머에 대 한 핸들을 수신 하는 핸들 변수의 주소입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

[IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute) 를 통해 호출할 *pClient* 타이머 신호를 받을 때입니다.

타이머 핸들을 전달 *phTimer* 하 [CWorkerThread::RemoveHandle](#removehandle) 를 타이머를 닫습니다.

##  <a name="cworkerthread"></a>  CWorkerThread::CWorkerThread

생성자입니다.

```
CWorkerThread() throw();
```

##  <a name="dtor"></a>  CWorkerThread::~CWorkerThread

소멸자입니다.

```
~CWorkerThread() throw();
```

### <a name="remarks"></a>설명

호출 [CWorkerThread::Shutdown](#shutdown)합니다.

##  <a name="getthreadhandle"></a>  CWorkerThread::GetThreadHandle

작업자 스레드의 스레드 핸들을 가져오려면이 메서드를 호출 합니다.

```
HANDLE GetThreadHandle() throw();
```

### <a name="return-value"></a>반환 값

작업자 스레드가 초기화 되지 않은 경우 스레드 핸들 또는 NULL을 반환 합니다.

##  <a name="getthreadid"></a>  CWorkerThread::GetThreadId

작업자 스레드의 스레드 ID를 가져오려면이 메서드를 호출 합니다.

```
DWORD GetThreadId() throw();
```

### <a name="return-value"></a>반환 값

작업자 스레드가 초기화 되지 않은 경우에 스레드 ID 또는 NULL을 반환 합니다.

##  <a name="initialize"></a>  CWorkerThread::Initialize

작업자 스레드를 초기화 하려면이 메서드를 호출 합니다.

```
HRESULT Initialize() throw();

HRESULT Initialize(CWorkerThread<ThreadTraits>* pThread) throw();
```

### <a name="parameters"></a>매개 변수

*pThread*<br/>
기존 작업자 스레드입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

이 메서드를 호출 하 여 만든 후 또는 호출 후에 개체를 초기화 하는 [CWorkerThread::Shutdown](#shutdown)합니다.

두 개 이상 있어야 `CWorkerThread` 개체가 동일한 작업자 스레드를 사용 하 여, 다음 인수를 해당 개체에 포인터를 전달 하는 전달 하지 않고 그 중 하나를 초기화 합니다 `Initialize` 다른 메서드. 포인터를 사용 하 여 초기화 하는 개체를 초기화 하는 데 사용 되는 개체 전에 종료 해야 합니다.

참조 [CWorkerThread::Shutdown](#shutdown) 기존 개체에 대 한 포인터를 사용 하 여 초기화할 때 해당 메서드의 동작이 변경 하는 방법에 대 한 정보에 대 한 합니다.

##  <a name="removehandle"></a>  CWorkerThread::RemoveHandle

핸들을 대기 가능 개체의 목록에서 제거 하려면이 메서드를 호출 합니다.

```
HRESULT RemoveHandle(HANDLE hObject) throw();
```

### <a name="parameters"></a>매개 변수

*hObject*<br/>
제거에 대 한 핸들입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

핸들 제거 되 면 [IWorkerThreadClient::CloseHandle](../../atl/reference/iworkerthreadclient-interface.md#closehandle) 에 전달 된 연결된 된 개체에서 호출 되는 [AddHandle](#addhandle)합니다. 이 호출이 실패 하면 `CWorkerThread` 는 Windows를 호출 하는 [CloseHandle](/windows/desktop/api/handleapi/nf-handleapi-closehandle) 핸들에는 함수입니다.

##  <a name="shutdown"></a>  CWorkerThread::Shutdown

작업자 스레드를 종료 하려면이 메서드를 호출 합니다.

```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```

### <a name="parameters"></a>매개 변수

*dwWait*<br/>
작업자 스레드가 종료 될 때까지 기다리는 시간 (밀리초) 시간입니다. ATL_WORKER_THREAD_WAIT 기본값은 10 초입니다. 필요한 경우와 atlutil.h 포함 하기 전에이 기호에 대 한 고유한 값을 정의할 수 있습니다.

### <a name="return-value"></a>반환 값

경우와 같이 실패 HRESULT 오류가 성공 시 S_OK를 반환 합니다. 제한 시간 값을 *dwWait*를 초과 합니다.

### <a name="remarks"></a>설명

개체를 다시 사용 하려면 호출 [CWorkerThread::Initialize](#initialize) 후이 메서드를 호출 합니다.

호출 `Shutdown` 간에 대 한 포인터를 사용 하 여 초기화 하는 개체에서 `CWorkerThread` 개체 영향을 주지 않으며 항상 S_OK를 반환 합니다.

## <a name="see-also"></a>참고자료

[DefaultThreadTraits](atl-typedefs.md#defaultthreadtraits)<br/>
[클래스](../../atl/reference/atl-classes.md)<br/>
[다중 스레딩: 작업자 스레드 만들기](../../parallel/multithreading-creating-worker-threads.md)<br/>
[IWorkerThreadClient 인터페이스](../../atl/reference/iworkerthreadclient-interface.md)
