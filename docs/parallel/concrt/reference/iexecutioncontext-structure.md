---
title: IExecutionContext 구조체
ms.date: 11/04/2016
f1_keywords:
- IExecutionContext
- CONCRTRM/concurrency::IExecutionContext
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::Dispatch
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetId
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetProxy
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetScheduler
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::SetProxy
helpviewer_keywords:
- IExecutionContext structure
ms.assetid: f3108089-ecda-4b07-86db-3efae60c31e0
ms.openlocfilehash: 8c49df5a8c7f214b574b4f6118d182b63fec5dca
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62262465"
---
# <a name="iexecutioncontext-structure"></a>IExecutionContext 구조체

지정된 가상 프로세서에서 실행되고 협조적으로 컨텍스트가 전환될 수 있는 실행 컨텍스트에 대한 인터페이스입니다.

## <a name="syntax"></a>구문

```
struct IExecutionContext;
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[IExecutionContext::Dispatch](#dispatch)|스레드 프록시는 특정 실행 컨텍스트를 실행 되기 시작 하면 호출 되는 메서드. 이 스케줄러에 대 한 주 작업자 루틴인 이어야 합니다.|
|[IExecutionContext::GetId](#getid)|실행 컨텍스트에 대 한 고유 식별자를 반환합니다.|
|[IExecutionContext::GetProxy](#getproxy)|이 컨텍스트에서 실행 되는 스레드 프록시 인터페이스를 반환 합니다.|
|[IExecutionContext::GetScheduler](#getscheduler)|스케줄러에 인터페이스를 반환이 실행 컨텍스트에 속합니다.|
|[IExecutionContext::SetProxy](#setproxy)|이 실행 컨텍스트를 사용 하 여 스레드 프록시를 연결합니다. 관련된 스레드 프록시 컨텍스트의 실행을 시작 하기 전에이 메서드를 오른쪽으로 호출 `Dispatch` 메서드.|

## <a name="remarks"></a>설명

동시성 런타임의 리소스 관리자와 인터페이스 하는 사용자 지정 스케줄러를 구현 하는 경우 구현 해야 합니다는 `IExecutionContext` 인터페이스입니다. 리소스 관리자가 만든 스레드를 실행 하 여 스케줄러를 대신 하 여 작업을 수행 합니다 `IExecutionContext::Dispatch` 메서드.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IExecutionContext`

## <a name="requirements"></a>요구 사항

**헤더:** concrtrm.h

**네임스페이스:** 동시성

##  <a name="dispatch"></a>  Iexecutioncontext:: Dispatch 메서드

스레드 프록시는 특정 실행 컨텍스트를 실행 되기 시작 하면 호출 되는 메서드. 이 스케줄러에 대 한 주 작업자 루틴인 이어야 합니다.

```
virtual void Dispatch(_Inout_ DispatchState* pDispatchState) = 0;
```

### <a name="parameters"></a>매개 변수

*pDispatchState*<br/>
이 실행 컨텍스트를 디스패치 하는 상태에 대 한 포인터입니다. 디스패치 상태에 대 한 자세한 내용은 참조 하세요. [DispatchState](dispatchstate-structure.md)합니다.

##  <a name="getid"></a>  IExecutionContext::GetId Method

실행 컨텍스트에 대 한 고유 식별자를 반환합니다.

```
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>반환 값

고유 정수 식별자입니다.

### <a name="remarks"></a>설명

메서드를 사용 해야 `GetExecutionContextId` 구현 하는 개체에 대 한 고유 식별자를 가져오는 `IExecutionContext` 인터페이스, 메서드 매개 변수로 인터페이스를 사용 하기 전에 리소스 관리자에서 제공 합니다. 동일한 식별자를 반환 해야 하는 경우는 `GetId` 함수를 호출 합니다.

다른 소스에서 가져온 식별자는 정의 되지 않은 동작이 발생할 수 있습니다.

##  <a name="getproxy"></a>  Iexecutioncontext:: Getproxy 메서드

이 컨텍스트에서 실행 되는 스레드 프록시 인터페이스를 반환 합니다.

```
virtual IThreadProxy* GetProxy() = 0;
```

### <a name="return-value"></a>반환 값

`IThreadProxy` 인터페이스입니다. 실행 컨텍스트의 스레드 프록시를 호출 하 여 초기화 되지 않은 경우 `SetProxy`, 함수 반환 해야 `NULL`합니다.

### <a name="remarks"></a>설명

리소스 관리자를 호출 합니다는 `SetProxy` 메서드는 실행 컨텍스트를 사용 하 여는 `IThreadProxy` 인터페이스에 진입 하기 전에 매개 변수로 `Dispatch` 메서드를는 컨텍스트에 따라 합니다. 이 인수를 저장 하 고 호출에서 반환 해야 `GetProxy()`합니다.

##  <a name="getscheduler"></a>  Iexecutioncontext:: Getscheduler 메서드

스케줄러에 인터페이스를 반환이 실행 컨텍스트에 속합니다.

```
virtual IScheduler* GetScheduler() = 0;
```

### <a name="return-value"></a>반환 값

`IScheduler` 인터페이스입니다.

### <a name="remarks"></a>설명

유효한를 사용 하 여 실행 컨텍스트를 초기화 해야 `IScheduler` 인터페이스 메서드에 매개 변수로 사용 하기 전에 리소스 관리자에서 제공 합니다.

##  <a name="setproxy"></a>  Iexecutioncontext:: Setproxy 메서드

이 실행 컨텍스트를 사용 하 여 스레드 프록시를 연결합니다. 관련된 스레드 프록시 컨텍스트의 실행을 시작 하기 전에이 메서드를 오른쪽으로 호출 `Dispatch` 메서드.

```
virtual void SetProxy(_Inout_ IThreadProxy* pThreadProxy) = 0;
```

### <a name="parameters"></a>매개 변수

*pThreadProxy*<br/>
입력에 있는 스레드 프록시에 대 한 인터페이스를 `Dispatch` 이 실행 컨텍스트에서 메서드.

### <a name="remarks"></a>설명

매개 변수를 저장 해야 하는 `pThreadProxy` 에 대 한 호출에서 반환 된 `GetProxy` 메서드. 리소스 관리자는 실행 컨텍스트를 사용 하 여 연결 된 스레드 프록시 스레드 프록시가 실행 되는 동안 변경 되지 것입니다는 `Dispatch` 메서드.

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[IScheduler 구조체](ischeduler-structure.md)<br/>
[IThreadProxy 구조체](ithreadproxy-structure.md)
