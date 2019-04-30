---
title: CThreadPool 클래스
ms.date: 11/04/2016
f1_keywords:
- CThreadPool
- ATLUTIL/ATL::CThreadPool
- ATLUTIL/ATL::CThreadPool::CThreadPool
- ATLUTIL/ATL::CThreadPool::AddRef
- ATLUTIL/ATL::CThreadPool::GetNumThreads
- ATLUTIL/ATL::CThreadPool::GetQueueHandle
- ATLUTIL/ATL::CThreadPool::GetSize
- ATLUTIL/ATL::CThreadPool::GetTimeout
- ATLUTIL/ATL::CThreadPool::Initialize
- ATLUTIL/ATL::CThreadPool::QueryInterface
- ATLUTIL/ATL::CThreadPool::QueueRequest
- ATLUTIL/ATL::CThreadPool::Release
- ATLUTIL/ATL::CThreadPool::SetSize
- ATLUTIL/ATL::CThreadPool::SetTimeout
- ATLUTIL/ATL::CThreadPool::Shutdown
helpviewer_keywords:
- CThreadPool class
ms.assetid: 06683718-01b9-413c-9481-2dc1734ec70f
ms.openlocfilehash: 7d363de0d787ecc5015093005b39a379acd82e71
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62277400"
---
# <a name="cthreadpool-class"></a>CThreadPool 클래스

이 클래스는 작업 항목의 큐를 처리 하는 작업자 스레드 풀을 제공 합니다.

## <a name="syntax"></a>구문

```
template <class Worker, class ThreadTraits = DefaultThreadTraits>
class CThreadPool : public IThreadPoolConfig
```

#### <a name="parameters"></a>매개 변수

*Worker*<br/>
따르는 클래스를 [worker 원형](../../atl/reference/worker-archetype.md) 항목 스레드 풀의 큐에 대기 하는 작업을 처리 하는 데 사용 되는 코드를 제공 합니다.

*ThreadTraits*<br/>
풀에서 스레드를 만드는 데 함수를 제공 하는 클래스입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CThreadPool::CThreadPool](#cthreadpool)|스레드 풀에 대 한 생성자입니다.|
|[CThreadPool::~CThreadPool](#dtor)|스레드 풀에 대 한 소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CThreadPool::AddRef](#addref)|구현의 `IUnknown::AddRef`합니다.|
|[CThreadPool::GetNumThreads](#getnumthreads)|풀의 스레드 수를 가져오려면이 메서드를 호출 합니다.|
|[CThreadPool::GetQueueHandle](#getqueuehandle)|작업 항목 큐에 사용 된 IO 완료 포트의 핸들을 가져오려면이 메서드를 호출 합니다.|
|[CThreadPool::GetSize](#getsize)|풀의 스레드 수를 가져오려면이 메서드를 호출 합니다.|
|[CThreadPool::GetTimeout](#gettimeout)|스레드 풀 스레드 종료를 대기할 시간 (밀리초)에는 최대 시간을 가져오려면이 메서드를 호출 합니다.|
|[CThreadPool::Initialize](#initialize)|스레드 풀을 초기화 하려면이 메서드를 호출 합니다.|
|[CThreadPool::QueryInterface](#queryinterface)|구현의 `IUnknown::QueryInterface`합니다.|
|[CThreadPool::QueueRequest](#queuerequest)|풀의 스레드에서 처리할 작업 항목을 큐에이 메서드를 호출 합니다.|
|[CThreadPool::Release](#release)|구현의 `IUnknown::Release`합니다.|
|[CThreadPool::SetSize](#setsize)|풀의 스레드 수를 설정 하려면이 메서드를 호출 합니다.|
|[CThreadPool::SetTimeout](#settimeout)|스레드 풀 스레드 종료를 대기할 시간 (밀리초)에는 최대 시간을 설정 하려면이 메서드를 호출 합니다.|
|[CThreadPool::Shutdown](#shutdown)|스레드 풀을 종료 하려면이 메서드를 호출 합니다.|

## <a name="remarks"></a>설명

풀의 스레드 생성 및 풀은 초기화, 크기 조정 또는 종료 될 때 소멸 됩니다. 클래스의 인스턴스이며 *작업자* 풀의 각 작업자 스레드의 스택에 생성 됩니다. 각 인스턴스는 스레드의 수명에 대 한 라이브 됩니다.

스레드를 만든 직후 *작업자*::`Initialize` 해당 스레드와 연결 된 개체에서 호출 됩니다. 스레드의 소멸 직전 *작업자*::`Terminate` 호출 됩니다. 두 방법 모두 동의 해야 합니다는 **void** <strong>\*</strong> 인수입니다. 이 인수 값의를 통해 스레드 풀으로 전달 합니다 *pvWorkerParam* 의 매개 변수 [CThreadPool::Initialize](#initialize)합니다.

작업자 스레드는 큐와 호출 항목을 가져올 작업 항목 큐 및 작업자 스레드에서 사용할 수 있을 때 작업에 대 한, 합니다 `Execute` 메서드를 *작업자* 해당 스레드에 대 한 개체입니다. 세 가지 항목은 메서드에 전달: 동일한 큐에서 항목 `pvWorkerParam` 전달할 *작업자*:: `Initialize` 하 고 *작업자*:: `Terminate`, 및에 대 한 포인터를 [OVERLAPPED](/windows/desktop/api/minwinbase/ns-minwinbase-_overlapped) IO 완료 포트 큐에 사용 된 구조입니다.

합니다 *작업자* 클래스는 typedef에서 제공 하 여 스레드 풀에서 대기 하는 항목의 형식을 선언 *작업자*:: `RequestType`합니다. 이 형식은 ULONG_PTR에서 캐스팅 될 수 있어야 합니다.

예는 *작업자* 클래스는 [CNonStatelessWorker 클래스](../../atl/reference/cnonstatelessworker-class.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IUnknown`

[IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md)

`CThreadPool`

## <a name="requirements"></a>요구 사항

**헤더:** 와 atlutil.h

##  <a name="addref"></a>  CThreadPool::AddRef

구현의 `IUnknown::AddRef`합니다.

```
ULONG STDMETHODCALLTYPE AddRef() throw();
```

### <a name="return-value"></a>반환 값

항상 1을 반환합니다.

### <a name="remarks"></a>설명

이 클래스는 참조 카운팅을 사용 하 여 수명 제어를 구현 하지 않습니다.

##  <a name="cthreadpool"></a>  CThreadPool::CThreadPool

스레드 풀에 대 한 생성자입니다.

```
CThreadPool() throw();
```

### <a name="remarks"></a>설명

ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT 시간 제한 값을 초기화합니다. 기본 시간은 36 초입니다. 필요한 경우와 atlutil.h 포함 하기 전에이 기호에 대 한 고유한 양의 정수 값을 정의할 수 있습니다.

##  <a name="dtor"></a>  CThreadPool::~CThreadPool

스레드 풀에 대 한 소멸자입니다.

```
~CThreadPool() throw();
```

### <a name="remarks"></a>설명

호출 [CThreadPool::Shutdown](#shutdown)합니다.

##  <a name="getnumthreads"></a>  CThreadPool::GetNumThreads

풀의 스레드 수를 가져오려면이 메서드를 호출 합니다.

```
int GetNumThreads() throw();
```

### <a name="return-value"></a>반환 값

풀의 스레드 수를 반환합니다.

##  <a name="getqueuehandle"></a>  CThreadPool::GetQueueHandle

작업 항목 큐에 사용 된 IO 완료 포트의 핸들을 가져오려면이 메서드를 호출 합니다.

```
HANDLE GetQueueHandle() throw();
```

### <a name="return-value"></a>반환 값

스레드 풀 초기화 되지 않은 경우 큐 핸들 또는 NULL을 반환 합니다.

##  <a name="getsize"></a>  CThreadPool::GetSize

풀의 스레드 수를 가져오려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE GetSize(int* pnNumThreads) throw();
```

### <a name="parameters"></a>매개 변수

*pnNumThreads*<br/>
[out] 성공 하면 풀의 스레드 수를 수신 하는 변수의 주소입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="gettimeout"></a>  CThreadPool::GetTimeout

스레드 풀 스레드 종료를 대기할 시간 (밀리초)에는 최대 시간을 가져오려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE GetTimeout(DWORD* pdwMaxWait) throw();
```

### <a name="parameters"></a>매개 변수

*pdwMaxWait*<br/>
[out] 성공 하면 스레드 풀 스레드 종료를 대기할 시간 (밀리초)에는 최대 시간을 수신 하는 변수의 주소입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

이 제한 시간 값에서 사용 됩니다 [CThreadPool::Shutdown](#shutdown) 를 해당 메서드에 변수에 다른 값이 없는 경우.

##  <a name="initialize"></a>  CThreadPool::Initialize

스레드 풀을 초기화 하려면이 메서드를 호출 합니다.

```
HRESULT Initialize(
    void* pvWorkerParam = NULL,
    int nNumThreads = 0,
    DWORD dwStackSize = 0,
    HANDLE hCompletion = INVALID_HANDLE_VALUE) throw();
```

### <a name="parameters"></a>매개 변수

*pvWorkerParam*<br/>
작업자 매개 변수는 작업자 스레드 개체에 전달할 `Initialize`, `Execute`, 및 `Terminate` 메서드.

*nNumThreads*<br/>
스레드 풀의 요청된 수입니다.

하는 경우 *nNumThreads* 가 음수 이면 절대 값에 곱합니다 스레드의 총 개수를 가져올 컴퓨터의 프로세서 수입니다.

하는 경우 *nNumThreads* 가 0 이면 ATLS_DEFAULT_THREADSPERPROC 스레드의 총 개수를 가져올 컴퓨터의 프로세서 수를 곱한 수 됩니다.  기본값은 프로세서당 2 스레드입니다. 필요한 경우와 atlutil.h 포함 하기 전에이 기호에 대 한 고유한 양의 정수 값을 정의할 수 있습니다.

*dwStackSize*<br/>
풀의 각 스레드의 스택 크기입니다.

*hCompletion*<br/>
완료 포트를 사용 하 여 연결할 개체의 핸들입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="queryinterface"></a>  CThreadPool::QueryInterface

구현의 `IUnknown::QueryInterface`합니다.

```
HRESULT STDMETHODCALLTYPE QueryInterface(REFIID riid, void** ppv) throw();
```

### <a name="remarks"></a>설명

이 클래스의 개체에 대 한 성공적으로 쿼리할 수는 `IUnknown` 하 고 [IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md) 인터페이스입니다.

##  <a name="queuerequest"></a>  CThreadPool::QueueRequest

풀의 스레드에서 처리할 작업 항목을 큐에이 메서드를 호출 합니다.

```
BOOL QueueRequest(Worker::RequestType request) throw();
```

### <a name="parameters"></a>매개 변수

*request*<br/>
요청 큐에 대기할 수입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 큐에 작업 항목을 추가합니다. 풀의 스레드는 받은 순서 대로 큐 항목을 선택 합니다.

##  <a name="release"></a>  CThreadPool::Release

구현의 `IUnknown::Release`합니다.

```
ULONG STDMETHODCALLTYPE Release() throw();
```

### <a name="return-value"></a>반환 값

항상 1을 반환합니다.

### <a name="remarks"></a>설명

이 클래스는 참조 카운팅을 사용 하 여 수명 제어를 구현 하지 않습니다.

##  <a name="setsize"></a>  CThreadPool::SetSize

풀의 스레드 수를 설정 하려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE SetSizeint nNumThreads) throw();
```

### <a name="parameters"></a>매개 변수

*nNumThreads*<br/>
스레드 풀의 요청된 수입니다.

하는 경우 *nNumThreads* 가 음수 이면 절대 값에 곱합니다 스레드의 총 개수를 가져올 컴퓨터의 프로세서 수입니다.

하는 경우 *nNumThreads* 가 0 이면 ATLS_DEFAULT_THREADSPERPROC 스레드의 총 개수를 가져올 컴퓨터의 프로세서 수를 곱한 수 됩니다. 기본값은 프로세서당 2 스레드입니다. 필요한 경우와 atlutil.h 포함 하기 전에이 기호에 대 한 고유한 양의 정수 값을 정의할 수 있습니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

지정 된 스레드 수가 스레드 풀의 현재 개수 보다 적은 경우 개체 종료 메시지를 대기 중인 스레드에 의해 선택 하도록 큐에 넣습니다. 대기 중인 스레드 큐 메시지를 가져오고, 스레드 풀 알리고 스레드 프로시저가 종료 됩니다. 풀의 스레드 수가 지정된 된 수에 도달할 때까지 또는 스레드가 없는 지정 된 기간 내에서 종료 될 때까지이 프로세스가 반복 됩니다 [GetTimeout](#gettimeout)/ [SetTimeout](#settimeout)합니다. 메서드는 wait_timeout 해당 HRESULT이이 상황에서 반환 하 고 보류 중인 종료 메시지 취소 됩니다.

##  <a name="settimeout"></a>  CThreadPool::SetTimeout

스레드 풀 스레드 종료를 대기할 시간 (밀리초)에는 최대 시간을 설정 하려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE SetTimeout(DWORD dwMaxWait) throw();
```

### <a name="parameters"></a>매개 변수

*dwMaxWait*<br/>
스레드 풀 스레드 종료를 대기할 시간 (밀리초) 요청 된 최대 시간입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

제한 시간 ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT으로 초기화 됩니다. 기본 시간은 36 초입니다. 필요한 경우와 atlutil.h 포함 하기 전에이 기호에 대 한 고유한 양의 정수 값을 정의할 수 있습니다.

사실은 *dwMaxWait* 풀에서 단일 스레드 종료를 대기 하는 시간입니다. 여러 스레드 풀에서 제거를 수행할 수 있는 최대 시간 수 보다 약간 작습니다 *dwMaxWait* 스레드 수를 곱합니다.

##  <a name="shutdown"></a>  CThreadPool::Shutdown

스레드 풀을 종료 하려면이 메서드를 호출 합니다.

```
void Shutdown(DWORD dwMaxWait = 0) throw();
```

### <a name="parameters"></a>매개 변수

*dwMaxWait*<br/>
스레드 풀 스레드 종료를 대기할 시간 (밀리초) 요청 된 최대 시간입니다. 이 메서드가 설정한 제한 시간을 사용할지 0 또는 값이 없는 경우 [CThreadPool::SetTimeout](#settimeout)합니다.

### <a name="remarks"></a>설명

이 메서드는 풀의 모든 스레드를 종료 요청을 게시합니다. 제한 시간이 만료 되 면이 메서드를 호출 합니다 [TerminateThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-terminatethread) 스레드의 종료 되지 않았습니다. 이 메서드는 클래스의 소멸자에서 자동으로 호출 됩니다.

## <a name="see-also"></a>참고자료

[IThreadPoolConfig 인터페이스](../../atl/reference/ithreadpoolconfig-interface.md)<br/>
[DefaultThreadTraits](atl-typedefs.md#defaultthreadtraits)<br/>
[클래스](../../atl/reference/atl-classes.md)
