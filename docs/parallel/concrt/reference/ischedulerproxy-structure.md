---
title: ISchedulerProxy 구조체
ms.date: 11/04/2016
f1_keywords:
- ISchedulerProxy
- CONCRTRM/concurrency::ISchedulerProxy
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::BindContext
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::CreateOversubscriber
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::RequestInitialVirtualProcessors
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::Shutdown
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::SubscribeCurrentThread
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::UnbindContext
helpviewer_keywords:
- ISchedulerProxy structure
ms.assetid: af416973-7a1c-4c30-aa3b-4161c2aaea54
ms.openlocfilehash: 0dddd43a5b3e68992e41f0b95893303e57e7c7ff
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346283"
---
# <a name="ischedulerproxy-structure"></a>ISchedulerProxy 구조체

스케줄러가 리소스 할당을 협상하기 위해 동시성 런타임의 리소스 관리자와 통신하는 데 사용되는 인터페이스입니다.

## <a name="syntax"></a>구문

```
struct ISchedulerProxy;
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[ISchedulerProxy::BindContext](#bindcontext)|아직 하나를 사용 하 여 연결 되지 않은 경우 실행 컨텍스트는 스레드 프록시를 연결 합니다.|
|[ISchedulerProxy::CreateOversubscriber](#createoversubscriber)|기존 실행 리소스와 관련 된 하드웨어 스레드에서 새로운 가상 프로세서 루트를 만듭니다.|
|[ISchedulerProxy::RequestInitialVirtualProcessors](#requestinitialvirtualprocessors)|가상 프로세서 루트의 초기 할당을 요청합니다. 모든 가상 프로세서 루트는 scheduler에 대 한 작업을 수행할 수 있는 하나의 스레드를 실행 하는 기능을 나타냅니다.|
|[ISchedulerProxy::Shutdown](#shutdown)|스케줄러를 종료 하 고는 리소스 관리자에 게 알립니다. 이렇게 하면 즉시 스케줄러에 부여 하는 모든 리소스를 회수 하려면 Resource Manager.|
|[ISchedulerProxy::SubscribeCurrentThread](#subscribecurrentthread)|현재 스레드에서 사용 하 여 리소스 관리자를이 스케줄러와 연결을 등록 합니다.|
|[ISchedulerProxy::UnbindContext](#unbindcontext)|지정 된 컨텍스트 실행 스레드 프록시 연결을 해제 합니다 `pContext` 매개 변수 스레드 프록시 팩터리를 사용 가능한 풀에 반환 합니다. 이 메서드는 실행 컨텍스트를 통해 바인딩된 에서만 호출할 수 있습니다 합니다 [ischedulerproxy:: Bindcontext](#bindcontext) 메서드 되 통해 아직 시작 되지 않은 합니다 `pContext` 의 매개 변수는 [ithreadproxy:: Switchto ](ithreadproxy-structure.md#switchto) 메서드를 호출 합니다.|

## <a name="remarks"></a>설명

전달 하는 리소스 관리자는 `ISchedulerProxy` 인터페이스를 사용 하 여 등록 하는 모든 스케줄러에는 [iresourcemanager:: Registerscheduler](iresourcemanager-structure.md#registerscheduler) 메서드.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`ISchedulerProxy`

## <a name="requirements"></a>요구 사항

**헤더:** concrtrm.h

**네임스페이스:** 동시성

##  <a name="bindcontext"></a>  Ischedulerproxy:: Bindcontext 메서드

아직 하나를 사용 하 여 연결 되지 않은 경우 실행 컨텍스트는 스레드 프록시를 연결 합니다.

```
virtual void BindContext(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>매개 변수

*pContext*<br/>
실행 컨텍스트는 스레드 프록시를 사용 하 여 연결 하는 인터페이스입니다.

### <a name="remarks"></a>설명

일반적으로 [ithreadproxy:: Switchto](ithreadproxy-structure.md#switchto) 메서드는 요청 시 실행 컨텍스트에 스레드 프록시를 바인딩합니다. 그러나가 되도록 사전에 컨텍스트를 바인딩하여 해야 하는 상황을 `SwitchTo` 방법이 이미 바인딩된 컨텍스트를 전환 합니다. 이 경우 메모리를 할당 하는 메서드를 호출할 수 없습니다 일정 컨텍스트에서 ums 및 스레드 프록시가 바인딩 넣어야 메모리 할당 스레드 프록시 팩터리 사용 가능한 풀에서 스레드 프록시를 쉽게 사용할 수 없는 경우.

`invalid_argument` 경우 발생 하는 매개 변수 `pContext` 기본값이 `NULL`합니다.

##  <a name="createoversubscriber"></a>  Ischedulerproxy:: Createoversubscriber 메서드

기존 실행 리소스와 관련 된 하드웨어 스레드에서 새로운 가상 프로세서 루트를 만듭니다.

```
virtual IVirtualProcessorRoot* CreateOversubscriber(_Inout_ IExecutionResource* pExecutionResource) = 0;
```

### <a name="parameters"></a>매개 변수

*pExecutionResource*<br/>
`IExecutionResource` 초과 구독 하려는 하드웨어 스레드를 나타내는 인터페이스입니다.

### <a name="return-value"></a>반환 값

`IVirtualProcessorRoot` 인터페이스입니다.

### <a name="remarks"></a>설명

스케줄러 제한 된 기간에 대 한 특정 하드웨어 스레드의 초과 구독 하려는 경우이 메서드를 사용 합니다. 가상 프로세서 루트를 사용 하 여 완료 되 면 반환 해야 하는 리소스 관리자에 게 호출 하 여는 [제거할](iexecutionresource-structure.md#remove) 메서드를 `IVirtualProcessorRoot` 인터페이스.

`IVirtualProcessorRoot` 인터페이스가 `IExecutionResource` 인터페이스에서 상속하기 때문에 기존 가상 프로세서 루트를 초과 구독할 수도 있습니다.

##  <a name="requestinitialvirtualprocessors"></a>  Ischedulerproxy:: Requestinitialvirtualprocessors 메서드

가상 프로세서 루트의 초기 할당을 요청합니다. 모든 가상 프로세서 루트는 scheduler에 대 한 작업을 수행할 수 있는 하나의 스레드를 실행 하는 기능을 나타냅니다.

```
virtual IExecutionResource* RequestInitialVirtualProcessors(bool doSubscribeCurrentThread) = 0;
```

### <a name="parameters"></a>매개 변수

*doSubscribeCurrentThread*<br/>
현재 스레드를 구독 및 리소스 할당 중에 대 한 계정 여부입니다.

### <a name="return-value"></a>반환 값

합니다 `IExecutionResource` 현재 스레드에 대 한 인터페이스 매개 변수 `doSubscribeCurrentThread` 기본값이 **true**합니다. 값이 **false**, NULL이 반환 됩니다.

### <a name="remarks"></a>설명

스케줄러 작업을 실행 하기 전에 Resource Manager에서 가상 프로세서 루트를 요청 하려면이 메서드를 사용 해야 하 합니다. Resource Manager 스케줄러 정책의 액세스를 사용 하 여 [ischeduler:: Getpolicy](ischeduler-structure.md#getpolicy) 정책 키에 대 한 값을 사용 하 고 `MinConcurrency`, `MaxConcurrency` 및 `TargetOversubscriptionFactor` 에 할당할 하드웨어 스레드 수를 결정 하는 scheduler 처음 및 모든 하드웨어 스레드에 대 한 만들려면 얼마나 많은 가상 프로세서 루트입니다. 스케줄러의 초기 할당을 확인 하려면 스케줄러 정책을 사용 하는 방법에 대 한 자세한 내용은 참조 하세요. [PolicyElementKey](concurrency-namespace-enums.md)합니다.

Resource Manager 리소스를 스케줄러에 메서드를 호출 하 여 부여 [ischeduler:: Addvirtualprocessors](ischeduler-structure.md#addvirtualprocessors) 가상 프로세서 루트의 목록입니다. 메서드는이 메서드가 반환 되기 전에 스케줄러에 대 한 콜백 호출 됩니다.

스케줄러 매개 변수를 설정 하 여 현재 스레드에 대 한 구독을 요청 하는 경우 `doSubscribeCurrentThread` 하 **true**, 메서드는 `IExecutionResource` 인터페이스. 구독을 나중에 사용 하 여 종료 해야 합니다는 [iexecutionresource:: Remove](iexecutionresource-structure.md#remove) 메서드.

하드웨어 스레드 선택을 결정할 때 Resource Manager는 프로세서 노드 선호도 대 한 최적화 하려고 합니다. 현재 스레드에 대 한 구독 요청 될 경우 현재 스레드가이 스케줄러에 할당 된 작업에 참여 하고자 함을 나타냅니다. 이러한 경우 할당 된 가상 프로세서 루트는 현재 스레드가 실행 되 고, 가능한 경우 프로세서 노드에 있습니다.

구독 하는 스레드의 작업 기본 하드웨어 스레드의 구독 수준이 하나 증가 합니다. 구독 수준 구독이 종료 되는 경우 1만 큼 줄어듭니다. 구독 수준에 대 한 자세한 내용은 참조 하세요. [iexecutionresource:: Currentsubscriptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel)합니다.

##  <a name="shutdown"></a>  Ischedulerproxy:: Shutdown 메서드

스케줄러를 종료 하 고는 리소스 관리자에 게 알립니다. 이렇게 하면 즉시 스케줄러에 부여 하는 모든 리소스를 회수 하려면 Resource Manager.

```
virtual void Shutdown() = 0;
```

### <a name="remarks"></a>설명

모든 `IExecutionContext` 메서드를 사용 하는 외부 스레드를 구독 하는 결과로 수신 스케줄러 인터페이스 `ISchedulerProxy::RequestInitialVirtualProcessors` 또는 `ISchedulerProxy::SubscribeCurrentThread` Resource Manager로 반환 되어야 합니다를 사용 하 여 `IExecutionResource::Remove` 스케줄러를 종료 하기 전에 합니다.

스케줄러 있으면 모든 가상 프로세서 루트를 비활성화, 활성화 해야 합니다를 사용 하 여 [ivirtualprocessorroot:: Activate](ivirtualprocessorroot-structure.md#activate), 있고 둡니다 에서도 실행 스레드 프록시를 `Dispatch` 메서드 실행 호출 하기 전에 발송 되는 컨텍스트 `Shutdown` 스케줄러 프록시에서 합니다.

모든 가상 프로세서 루트는 종료 시 리소스 관리자로 반환되기 때문에 리소스 관리자가 `Remove` 메서드 호출을 통해 부여한 모든 가상 프로세서 루트를 스케줄러가 개별적으로 반환할 필요는 없습니다.

##  <a name="subscribecurrentthread"></a>  Ischedulerproxy:: Subscribecurrentthread 메서드

현재 스레드에서 사용 하 여 리소스 관리자를이 스케줄러와 연결을 등록 합니다.

```
virtual IExecutionResource* SubscribeCurrentThread() = 0;
```

### <a name="return-value"></a>반환 값

`IExecutionResource` 런타임에서 현재 스레드를 나타내는 상호 작용 합니다.

### <a name="remarks"></a>설명

사용자의 스케줄러와 다른 스케줄러에 리소스를 할당 하는 동안 현재 스레드에 대 한 계정에 Resource Manager를 하려는 경우이 메서드를 사용 합니다. 작업에 참여 하는 스레드 계획 스케줄러 수신 Resource Manager에서 가상 프로세서 루트와 함께 스케줄러를 대기 하는 경우에 특히 유용 합니다. 리소스 관리자는 시스템의 하드웨어 스레드로 불필요 한 초과 방지 하기 위해 정보를 사용 합니다.

이 메서드를 통해 받은 실행 리소스를 반환할 Resource Manager에 사용 하 여 합니다 [iexecutionresource:: Remove](iexecutionresource-structure.md#remove) 메서드. 호출 하는 스레드는 `Remove` 메서드는 동일한 스레드에서 이전에 호출 해야 합니다.는 `SubscribeCurrentThread` 메서드.

구독 하는 스레드의 작업 기본 하드웨어 스레드의 구독 수준이 하나 증가 합니다. 구독 수준 구독이 종료 되는 경우 1만 큼 줄어듭니다. 구독 수준에 대 한 자세한 내용은 참조 하세요. [iexecutionresource:: Currentsubscriptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel)합니다.

##  <a name="unbindcontext"></a>  Ischedulerproxy:: Unbindcontext 메서드

지정 된 컨텍스트 실행 스레드 프록시 연결을 해제 합니다 `pContext` 매개 변수 스레드 프록시 팩터리를 사용 가능한 풀에 반환 합니다. 이 메서드는 실행 컨텍스트를 통해 바인딩된 에서만 호출할 수 있습니다 합니다 [ischedulerproxy:: Bindcontext](#bindcontext) 메서드 되 통해 아직 시작 되지 않은 합니다 `pContext` 의 매개 변수는 [ithreadproxy:: Switchto ](ithreadproxy-structure.md#switchto) 메서드를 호출 합니다.

```
virtual void UnbindContext(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>매개 변수

*pContext*<br/>
스레드 프록시의 연결을 끊을 실행 컨텍스트.

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[IScheduler 구조체](ischeduler-structure.md)<br/>
[IThreadProxy 구조체](ithreadproxy-structure.md)<br/>
[IVirtualProcessorRoot 구조체](ivirtualprocessorroot-structure.md)<br/>
[IResourceManager 구조체](iresourcemanager-structure.md)
