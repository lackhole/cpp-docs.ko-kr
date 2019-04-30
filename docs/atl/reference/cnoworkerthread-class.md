---
title: CNoWorkerThread 클래스
ms.date: 11/04/2016
f1_keywords:
- CNoWorkerThread
- ATLUTIL/ATL::CNoWorkerThread
- ATLUTIL/ATL::CNoWorkerThread::AddHandle
- ATLUTIL/ATL::CNoWorkerThread::AddTimer
- ATLUTIL/ATL::CNoWorkerThread::GetThreadHandle
- ATLUTIL/ATL::CNoWorkerThread::GetThreadId
- ATLUTIL/ATL::CNoWorkerThread::Initialize
- ATLUTIL/ATL::CNoWorkerThread::RemoveHandle
- ATLUTIL/ATL::CNoWorkerThread::Shutdown
helpviewer_keywords:
- CNoWorkerThread class
ms.assetid: 29f06bae-b658-4aac-9c14-331e996d25d1
ms.openlocfilehash: fcd103283738ce7d573faa2fb1025ee2af642021
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62258496"
---
# <a name="cnoworkerthread-class"></a>CNoWorkerThread 클래스

이 클래스에 대 한 인수로 사용 된 `MonitorClass` 동적 캐시 유지 관리를 사용 하지 않도록 설정 하려는 경우에 캐시 클래스 템플릿 매개 변수입니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CNoWorkerThread
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CNoWorkerThread::AddHandle](#addhandle)|비기능적 표현한 [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)합니다.|
|[CNoWorkerThread::AddTimer](#addtimer)|비기능적 표현한 [CWorkerThread::AddTimer](../../atl/reference/cworkerthread-class.md#addtimer)합니다.|
|[CNoWorkerThread::GetThreadHandle](#getthreadhandle)|비기능적 표현한 [CWorkerThread::GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle)합니다.|
|[CNoWorkerThread::GetThreadId](#getthreadid)|비기능적 표현한 [CWorkerThread::GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid)합니다.|
|[CNoWorkerThread::Initialize](#initialize)|비기능적 표현한 [CWorkerThread::Initialize](../../atl/reference/cworkerthread-class.md#initialize)합니다.|
|[CNoWorkerThread::RemoveHandle](#removehandle)|비기능적 표현한 [CWorkerThread::RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle)합니다.|
|[CNoWorkerThread::Shutdown](#shutdown)|비기능적 표현한 [CWorkerThread::Shutdown](../../atl/reference/cworkerthread-class.md#shutdown)합니다.|

## <a name="remarks"></a>설명

이 클래스와 동일한 공용 인터페이스를 제공 [CWorkerThread](../../atl/reference/cworkerthread-class.md)합니다. 이 인터페이스에서 제공 될는 `MonitorClass` 캐시 클래스 템플릿 매개 변수입니다.

이 클래스의 메서드는 아무 작업도 수행 하도록 구현 됩니다. 항상 HRESULT를 반환 하는 메서드는 S_OK를 반환 하 고 항상 핸들 또는 스레드 ID를 반환 하는 메서드가 0을 반환 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** 와 atlutil.h

##  <a name="addhandle"></a>  CNoWorkerThread::AddHandle

비기능적 표현한 [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)합니다.

```
HRESULT AddHandle(HANDLE /* hObject */,
    IWorkerThreadClient* /* pClient */,
    DWORD_PTR /* dwParam */) throw();
```

### <a name="return-value"></a>반환 값

항상 S_OK를 반환합니다.

### <a name="remarks"></a>설명

이 클래스에서 제공 하는 구현은 아무 작업도 수행 하지.

##  <a name="addtimer"></a>  CNoWorkerThread::AddTimer

비기능적 표현한 [CWorkerThread::AddTimer](../../atl/reference/cworkerthread-class.md#addtimer)합니다.

```
HRESULT AddTimer(DWORD /* dwInterval */,
    IWorkerThreadClient* /* pClient */,
    DWORD_PTR /* dwParam */,
    HANDLE* /* phTimer */) throw();
```

### <a name="return-value"></a>반환 값

항상 S_OK를 반환합니다.

### <a name="remarks"></a>설명

이 클래스에서 제공 하는 구현은 아무 작업도 수행 하지.

##  <a name="getthreadhandle"></a>  CNoWorkerThread::GetThreadHandle

비기능적 표현한 [CWorkerThread::GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle)합니다.

```
HANDLE GetThreadHandle() throw();
```

### <a name="return-value"></a>반환 값

항상 NULL을 반환합니다.

### <a name="remarks"></a>설명

이 클래스에서 제공 하는 구현은 아무 작업도 수행 하지.

##  <a name="getthreadid"></a>  CNoWorkerThread::GetThreadId

비기능적 표현한 [CWorkerThread::GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid)합니다.

```
DWORD GetThreadId() throw();
```

### <a name="return-value"></a>반환 값

항상 0을 반환합니다.

### <a name="remarks"></a>설명

이 클래스에서 제공 하는 구현은 아무 작업도 수행 하지.

##  <a name="initialize"></a>  CNoWorkerThread::Initialize

비기능적 표현한 [CWorkerThread::Initialize](../../atl/reference/cworkerthread-class.md#initialize)합니다.

```
HRESULT Initialize() throw();
```

### <a name="return-value"></a>반환 값

항상 S_OK를 반환합니다.

### <a name="remarks"></a>설명

이 클래스에서 제공 하는 구현은 아무 작업도 수행 하지.

##  <a name="removehandle"></a>  CNoWorkerThread::RemoveHandle

비기능적 표현한 [CWorkerThread::RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle)합니다.

```
HRESULT RemoveHandle(HANDLE /* hObject */) throw();
```

### <a name="return-value"></a>반환 값

항상 S_OK를 반환합니다.

### <a name="remarks"></a>설명

이 클래스에서 제공 하는 구현은 아무 작업도 수행 하지.

##  <a name="shutdown"></a>  CNoWorkerThread::Shutdown

비기능적 표현한 [CWorkerThread::Shutdown](../../atl/reference/cworkerthread-class.md#shutdown)합니다.

```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```

### <a name="return-value"></a>반환 값

항상 S_OK를 반환합니다.

### <a name="remarks"></a>설명

이 클래스에서 제공 하는 구현은 아무 작업도 수행 하지.
