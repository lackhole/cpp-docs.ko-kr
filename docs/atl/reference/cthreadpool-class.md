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
ms.openlocfilehash: 07fd470a6aeab0575f2733d72650bd695b8e2752
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68915682"
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
스레드 풀에서 큐에 대기 중인 작업 항목을 처리 하는 데 사용 되는 코드를 제공 하는 [작업자 원형](../../atl/reference/worker-archetype.md) 을 준수 하는 클래스입니다.

*ThreadTraits*<br/>
풀에서 스레드를 만드는 데 사용 되는 함수를 제공 하는 클래스입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|Description|
|----------|-----------------|
|[CThreadPool::CThreadPool](#cthreadpool)|스레드 풀에 대 한 생성자입니다.|
|[CThreadPool::~CThreadPool](#dtor)|스레드 풀에 대 한 소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|Description|
|----------|-----------------|
|[CThreadPool::AddRef](#addref)|구현의 `IUnknown::AddRef`합니다.|
|[CThreadPool::GetNumThreads](#getnumthreads)|풀의 스레드 수를 가져오려면이 메서드를 호출 합니다.|
|[CThreadPool::GetQueueHandle](#getqueuehandle)|작업 항목을 큐에 대기 하는 데 사용 되는 IO 완료 포트의 핸들을 가져오려면이 메서드를 호출 합니다.|
|[CThreadPool::GetSize](#getsize)|풀의 스레드 수를 가져오려면이 메서드를 호출 합니다.|
|[CThreadPool::GetTimeout](#gettimeout)|스레드 풀에서 스레드가 종료 될 때까지 대기 하는 최대 시간 (밀리초)을 가져오려면이 메서드를 호출 합니다.|
|[CThreadPool::Initialize](#initialize)|스레드 풀을 초기화 하려면이 메서드를 호출 합니다.|
|[CThreadPool::QueryInterface](#queryinterface)|구현의 `IUnknown::QueryInterface`합니다.|
|[CThreadPool::QueueRequest](#queuerequest)|풀의 스레드에서 처리할 작업 항목을 큐에 대기 시키려면이 메서드를 호출 합니다.|
|[CThreadPool::Release](#release)|구현의 `IUnknown::Release`합니다.|
|[CThreadPool::SetSize](#setsize)|풀의 스레드 수를 설정 하려면이 메서드를 호출 합니다.|
|[CThreadPool::SetTimeout](#settimeout)|스레드 풀에서 스레드가 종료 될 때까지 대기 하는 최대 시간 (밀리초)을 설정 하려면이 메서드를 호출 합니다.|
|[CThreadPool::Shutdown](#shutdown)|스레드 풀을 종료 하려면이 메서드를 호출 합니다.|

## <a name="remarks"></a>설명

풀의 스레드는 풀을 초기화 하거나 크기를 조정 하거나 종료할 때 생성 되 고 제거 됩니다. 클래스 *작업자* 의 인스턴스는 풀의 각 작업자 스레드 스택에 생성 됩니다. 각 인스턴스는 스레드 수명 동안 지속 됩니다.

스레드를 만든 직후에 *Worker*::`Initialize` 가 해당 스레드와 연결 된 개체에서 호출 됩니다. 스레드의 소멸 직전에 *Worker*::`Terminate` 가 호출 됩니다. 두 방법 모두 **void** <strong>\*</strong> 인수를 허용 해야 합니다. 이 인수의 값은 [Cthreadpool:: Initialize](#initialize)의 *pvWorkerParam* 매개 변수를 통해 스레드 풀로 전달 됩니다.

큐의 작업 항목 및 작업에 사용할 수 있는 작업자 스레드가 있는 경우 작업자 스레드는 항목을 큐에서 끌어오고 해당 스레드에 대 한 *작업자* 개체 `Execute` 의 메서드를 호출 합니다. 그런 다음 세 개의 항목이 메서드에 전달 됩니다. 큐의 항목, `pvWorkerParam` *작업자*:: `Initialize` 및 *worker*:: `Terminate`로 전달 된 항목, IO 완료 포트 큐에 사용 되는 [겹쳐진](/windows/desktop/api/minwinbase/ns-minwinbase-overlapped) 구조에 대 한 포인터 .

*Worker* 클래스는 Typedef, *Worker*:: `RequestType`를 제공 하 여 스레드 풀에서 큐에 대기할 항목의 형식을 선언 합니다. 이 형식은 ULONG_PTR로 캐스팅 될 수 있어야 합니다.

*작업자* 클래스의 예로는 [Cnonstatelessworker 클래스가](../../atl/reference/cnonstatelessworker-class.md)있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층

`IUnknown`

[IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md)

`CThreadPool`

## <a name="requirements"></a>요구 사항

**헤더:**

##  <a name="addref"></a>  CThreadPool::AddRef

구현의 `IUnknown::AddRef`합니다.

```
ULONG STDMETHODCALLTYPE AddRef() throw();
```

### <a name="return-value"></a>반환 값

항상 1을 반환 합니다.

### <a name="remarks"></a>설명

이 클래스는 참조 횟수를 사용 하 여 수명 제어를 구현 하지 않습니다.

##  <a name="cthreadpool"></a>  CThreadPool::CThreadPool

스레드 풀에 대 한 생성자입니다.

```
CThreadPool() throw();
```

### <a name="remarks"></a>설명

ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT에 대 한 시간 제한 값을 초기화 합니다. 기본 시간은 36 초입니다. 필요한 경우이 기호에 대 한 사용자 고유의 양의 정수 값을 정의할 수 있습니다.

##  <a name="dtor"></a>  CThreadPool::~CThreadPool

스레드 풀에 대 한 소멸자입니다.

```
~CThreadPool() throw();
```

### <a name="remarks"></a>설명

[Cthreadpool:: Shutdown](#shutdown)을 호출 합니다.

##  <a name="getnumthreads"></a>  CThreadPool::GetNumThreads

풀의 스레드 수를 가져오려면이 메서드를 호출 합니다.

```
int GetNumThreads() throw();
```

### <a name="return-value"></a>반환 값

풀의 스레드 수를 반환 합니다.

##  <a name="getqueuehandle"></a>  CThreadPool::GetQueueHandle

작업 항목을 큐에 대기 하는 데 사용 되는 IO 완료 포트의 핸들을 가져오려면이 메서드를 호출 합니다.

```
HANDLE GetQueueHandle() throw();
```

### <a name="return-value"></a>반환 값

큐 핸들을 반환 하거나 스레드 풀이 초기화 되지 않은 경우 NULL을 반환 합니다.

##  <a name="getsize"></a>  CThreadPool::GetSize

풀의 스레드 수를 가져오려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE GetSize(int* pnNumThreads) throw();
```

### <a name="parameters"></a>매개 변수

*pnNumThreads*<br/>
제한이 성공 시 풀의 스레드 수를 받는 변수의 주소입니다.

### <a name="return-value"></a>반환 값

는 성공 시 S_OK를 반환 하 고 실패 하면 오류 HRESULT를 반환 합니다.

##  <a name="gettimeout"></a>  CThreadPool::GetTimeout

스레드 풀에서 스레드가 종료 될 때까지 대기 하는 최대 시간 (밀리초)을 가져오려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE GetTimeout(DWORD* pdwMaxWait) throw();
```

### <a name="parameters"></a>매개 변수

*pdwMaxWait*<br/>
제한이 성공 시 스레드 풀에서 스레드가 종료 될 때까지 대기 하는 최대 시간 (밀리초)을 받는 변수의 주소입니다.

### <a name="return-value"></a>반환 값

는 성공 시 S_OK를 반환 하 고 실패 하면 오류 HRESULT를 반환 합니다.

### <a name="remarks"></a>설명

이 시간 제한 값은 해당 메서드에 다른 값이 제공 되지 않은 경우 [Cthreadpool:: Shutdown](#shutdown) 에서 사용 됩니다.

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
작업자 스레드 개체의 `Initialize`, `Execute`및 `Terminate` 메서드에 전달할 작업자 매개 변수입니다.

*nNumThreads*<br/>
풀에서 요청 된 스레드 수입니다.

*Nnumthreads* 가 음수 이면 총 스레드 수를 가져오기 위해 컴퓨터의 프로세서 수에 해당 절대값을 곱합니다.

*Nnumthreads* 가 0 인 경우 ATLS_DEFAULT_THREADSPERPROC은 총 스레드 수를 얻기 위해 컴퓨터의 프로세서 수를 곱합니다.  기본값은 프로세서 당 2 개의 스레드입니다. 필요한 경우이 기호에 대 한 사용자 고유의 양의 정수 값을 정의할 수 있습니다.

*dwStackSize*<br/>
풀에 있는 각 스레드의 스택 크기입니다.

*hCompletion*<br/>
완료 포트와 연결할 개체의 핸들입니다.

### <a name="return-value"></a>반환 값

는 성공 시 S_OK를 반환 하 고 실패 하면 오류 HRESULT를 반환 합니다.

##  <a name="queryinterface"></a>  CThreadPool::QueryInterface

구현의 `IUnknown::QueryInterface`합니다.

```
HRESULT STDMETHODCALLTYPE QueryInterface(REFIID riid, void** ppv) throw();
```

### <a name="remarks"></a>설명

이 클래스의 개체는 `IUnknown` 및 [IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md) 인터페이스에 대해 쿼리할 수 있습니다.

##  <a name="queuerequest"></a>  CThreadPool::QueueRequest

풀의 스레드에서 처리할 작업 항목을 큐에 대기 시키려면이 메서드를 호출 합니다.

```
BOOL QueueRequest(Worker::RequestType request) throw();
```

### <a name="parameters"></a>매개 변수

*request*<br/>
대기 중인 요청입니다.

### <a name="return-value"></a>반환 값

성공 하면 TRUE를 반환 하 고 실패 하면 FALSE를 반환 합니다.

### <a name="remarks"></a>설명

이 메서드는 큐에 작업 항목을 추가 합니다. 풀의 스레드는 수신 된 순서 대로 큐에서 항목을 선택 합니다.

##  <a name="release"></a>  CThreadPool::Release

구현의 `IUnknown::Release`합니다.

```
ULONG STDMETHODCALLTYPE Release() throw();
```

### <a name="return-value"></a>반환 값

항상 1을 반환 합니다.

### <a name="remarks"></a>설명

이 클래스는 참조 횟수를 사용 하 여 수명 제어를 구현 하지 않습니다.

##  <a name="setsize"></a>  CThreadPool::SetSize

풀의 스레드 수를 설정 하려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE SetSizeint nNumThreads) throw();
```

### <a name="parameters"></a>매개 변수

*nNumThreads*<br/>
풀에서 요청 된 스레드 수입니다.

*Nnumthreads* 가 음수 이면 총 스레드 수를 가져오기 위해 컴퓨터의 프로세서 수에 해당 절대값을 곱합니다.

*Nnumthreads* 가 0 인 경우 ATLS_DEFAULT_THREADSPERPROC은 총 스레드 수를 얻기 위해 컴퓨터의 프로세서 수를 곱합니다. 기본값은 프로세서 당 2 개의 스레드입니다. 필요한 경우이 기호에 대 한 사용자 고유의 양의 정수 값을 정의할 수 있습니다.

### <a name="return-value"></a>반환 값

는 성공 시 S_OK를 반환 하 고 실패 하면 오류 HRESULT를 반환 합니다.

### <a name="remarks"></a>설명

지정 된 스레드 수가 풀에 현재 있는 스레드 수보다 적으면 개체는 대기 스레드에서 선택할 종료 메시지를 큐에 넣습니다. 대기 중인 스레드는 큐에서 메시지를 끌어올 때 스레드 풀에 알리고 스레드 프로시저를 종료 합니다. 풀의 스레드 수가 지정 된 수에 도달 하거나 [gettimeout](#gettimeout)/ [SetTimeout](#settimeout)에서 지정한 기간 내에 스레드가 종료 되지 않을 때까지이 프로세스가 반복 됩니다. 이 경우 메서드는 WAIT_TIMEOUT에 해당 하는 HRESULT를 반환 하 고 보류 중인 종료 메시지가 취소 됩니다.

##  <a name="settimeout"></a>  CThreadPool::SetTimeout

스레드 풀에서 스레드가 종료 될 때까지 대기 하는 최대 시간 (밀리초)을 설정 하려면이 메서드를 호출 합니다.

```
HRESULT STDMETHODCALLTYPE SetTimeout(DWORD dwMaxWait) throw();
```

### <a name="parameters"></a>매개 변수

*dwMaxWait*<br/>
스레드 풀에서 스레드가 종료 될 때까지 대기 하는 요청 된 최대 시간 (밀리초)입니다.

### <a name="return-value"></a>반환 값

는 성공 시 S_OK를 반환 하 고 실패 하면 오류 HRESULT를 반환 합니다.

### <a name="remarks"></a>설명

시간 제한은 ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT으로 초기화 됩니다. 기본 시간은 36 초입니다. 필요한 경우이 기호에 대 한 사용자 고유의 양의 정수 값을 정의할 수 있습니다.

*Dwmaxwait* 는 풀에서 단일 스레드가 종료 될 때까지 대기 하는 시간입니다. 풀에서 여러 스레드를 제거 하는 데 사용할 수 있는 최대 시간은 *Dwmaxwait* 에서 스레드 수를 곱한 값 보다 약간 적을 수 있습니다.

##  <a name="shutdown"></a>  CThreadPool::Shutdown

스레드 풀을 종료 하려면이 메서드를 호출 합니다.

```
void Shutdown(DWORD dwMaxWait = 0) throw();
```

### <a name="parameters"></a>매개 변수

*dwMaxWait*<br/>
스레드 풀에서 스레드가 종료 될 때까지 대기 하는 요청 된 최대 시간 (밀리초)입니다. 0 또는 값을 제공 하지 않으면이 메서드는 [Cthreadpool:: SetTimeout](#settimeout)에 의해 설정 된 제한 시간을 사용 합니다.

### <a name="remarks"></a>설명

이 메서드는 풀의 모든 스레드에 종료 요청을 게시 합니다. 제한 시간이 만료 되 면이 메서드는 종료 되지 않은 모든 스레드에서 [TerminateThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-terminatethread) 를 호출 합니다. 이 메서드는 클래스의 소멸자에서 자동으로 호출 됩니다.

## <a name="see-also"></a>참고자료

[IThreadPoolConfig 인터페이스](../../atl/reference/ithreadpoolconfig-interface.md)<br/>
[DefaultThreadTraits](atl-typedefs.md#defaultthreadtraits)<br/>
[클래스](../../atl/reference/atl-classes.md)
