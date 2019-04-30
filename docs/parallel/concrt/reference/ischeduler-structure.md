---
title: IScheduler 구조체
ms.date: 11/04/2016
f1_keywords:
- IScheduler
- CONCRTRM/concurrency::IScheduler
- CONCRTRM/concurrency::IScheduler::IScheduler::AddVirtualProcessors
- CONCRTRM/concurrency::IScheduler::IScheduler::GetId
- CONCRTRM/concurrency::IScheduler::IScheduler::GetPolicy
- CONCRTRM/concurrency::IScheduler::IScheduler::NotifyResourcesExternallyBusy
- CONCRTRM/concurrency::IScheduler::IScheduler::NotifyResourcesExternallyIdle
- CONCRTRM/concurrency::IScheduler::IScheduler::RemoveVirtualProcessors
- CONCRTRM/concurrency::IScheduler::IScheduler::Statistics
helpviewer_keywords:
- IScheduler structure
ms.assetid: 471de85a-2b1a-4b6d-ab81-2eff2737161e
ms.openlocfilehash: 54db5d664a48f95a952eb1b409839d8ac3421e30
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62337507"
---
# <a name="ischeduler-structure"></a>IScheduler 구조체

작업 스케줄러의 추상화에 대한 인터페이스입니다. 동시성 런타임의 리소스 관리자는 이 인터페이스를 사용하여 작업 스케줄러와 통신합니다.

## <a name="syntax"></a>구문

```
struct IScheduler;
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[IScheduler::AddVirtualProcessors](#addvirtualprocessors)|용도 맞게 가상 프로세서 루트의 집합을 사용 하 여 스케줄러를 제공합니다. 각 `IVirtualProcessorRoot` 인터페이스 스케줄러를 대신 하 여 작업을 수행할 수 있는 단일 스레드를 실행할 수 있는 권한을 나타냅니다.|
|[IScheduler::GetId](#getid)|스케줄러에 대 한 고유 식별자를 반환합니다.|
|[IScheduler::GetPolicy](#getpolicy)|스케줄러 정책의 복사본을 반환합니다. 스케줄러 정책에 대 한 자세한 내용은 참조 하세요. [SchedulerPolicy](schedulerpolicy-class.md)합니다.|
|[IScheduler::NotifyResourcesExternallyBusy](#notifyresourcesexternallybusy)|하드웨어 스레드 배열에 있는 가상 프로세서 루트의 집합을 나타내는이 스케줄러에 알립니다 `ppVirtualProcessorRoots` 다른 스케줄러에 의해 현재 사용 되 고 있습니다.|
|[IScheduler::NotifyResourcesExternallyIdle](#notifyresourcesexternallyidle)|하드웨어 스레드 배열에 있는 가상 프로세서 루트의 집합을 나타내는이 스케줄러에 알립니다 `ppVirtualProcessorRoots` 다른 스케줄러에 의해 사용 되지 않습니다.|
|[IScheduler::RemoveVirtualProcessors](#removevirtualprocessors)|이 스케줄러에 이전에 할당 된 가상 프로세서 루트의 제거를 시작 합니다.|
|[IScheduler::Statistics](#statistics)|작업 도착 및 완료 비율 및 스케줄러에 대 한 변경의 큐 길이 관련 된 정보를 제공 합니다.|

## <a name="remarks"></a>설명

리소스 관리자와 통신 하는 사용자 지정 스케줄러를 구현 하는 경우의 구현을 제공 해야 합니다 `IScheduler` 인터페이스입니다. 이 인터페이스에는 양방향 스케줄러와 리소스 관리자 간의 통신 채널의 한쪽 끝입니다. 반대쪽은 표현 합니다 `IResourceManager` 및 `ISchedulerProxy` Resource Manager에서 구현 되는 인터페이스입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IScheduler`

## <a name="requirements"></a>요구 사항

**헤더:** concrtrm.h

**네임스페이스:** 동시성

##  <a name="addvirtualprocessors"></a>  Ischeduler:: Addvirtualprocessors 메서드

용도 맞게 가상 프로세서 루트의 집합을 사용 하 여 스케줄러를 제공합니다. 각 `IVirtualProcessorRoot` 인터페이스 스케줄러를 대신 하 여 작업을 수행할 수 있는 단일 스레드를 실행할 수 있는 권한을 나타냅니다.

```
virtual void AddVirtualProcessors(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```

### <a name="parameters"></a>매개 변수

*ppVirtualProcessorRoots*<br/>
배열을 `IVirtualProcessorRoot` 가상 프로세서를 나타내는 인터페이스 스케줄러에 추가할 루트입니다.

*count*<br/>
수가 `IVirtualProcessorRoot` 배열에 대 한 인터페이스입니다.

### <a name="remarks"></a>설명

Resource Manager를 호출 하 여 `AddVirtualProcessor` 스케줄러로 가상 프로세서 루트의 초기 집합을 부여 하는 방법입니다. 스케줄러 간에 리소스 균형 경우 스케줄러를 가상 프로세서 루트를 추가 하는 메서드를 호출할 수도 없습니다.

##  <a name="getid"></a>  Ischeduler:: Getid 메서드

스케줄러에 대 한 고유 식별자를 반환합니다.

```
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>반환 값

고유 정수 식별자입니다.

### <a name="remarks"></a>설명

사용 해야 합니다 [GetSchedulerId](concurrency-namespace-functions.md) 함수를 구현 하는 개체에 대 한 고유 식별자를 `IScheduler` 인터페이스, 메서드 매개 변수로 인터페이스를 사용 하기 전에 리소스 관리자에서 제공 합니다. 동일한 식별자를 반환 해야 하는 경우는 `GetId` 함수를 호출 합니다.

다른 소스에서 가져온 식별자는 정의 되지 않은 동작이 발생할 수 있습니다.

##  <a name="getpolicy"></a>  Ischeduler:: Getpolicy 메서드

스케줄러 정책의 복사본을 반환합니다. 스케줄러 정책에 대 한 자세한 내용은 참조 하세요. [SchedulerPolicy](schedulerpolicy-class.md)합니다.

```
virtual SchedulerPolicy GetPolicy() const = 0;
```

### <a name="return-value"></a>반환 값

스케줄러 정책의 복사본입니다.

##  <a name="notifyresourcesexternallybusy"></a>  Ischeduler:: Notifyresourcesexternallybusy 메서드

하드웨어 스레드 배열에 있는 가상 프로세서 루트의 집합을 나타내는이 스케줄러에 알립니다 `ppVirtualProcessorRoots` 다른 스케줄러에 의해 현재 사용 되 고 있습니다.

```
virtual void NotifyResourcesExternallyBusy(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```

### <a name="parameters"></a>매개 변수

*ppVirtualProcessorRoots*<br/>
배열을 `IVirtualProcessorRoot` 인터페이스가 있는 다른 스케줄러 사용 중 상태가 된 하드웨어 스레드를 사용 하 여 연결 합니다.

*count*<br/>
수가 `IVirtualProcessorRoot` 배열에 대 한 인터페이스입니다.

### <a name="remarks"></a>설명

특정 하드웨어 스레드를 동시에 여러 스케줄러에 할당할 수는 것이 가능 합니다. 그 이유 중 하나는 시스템 리소스를 공유 하지 않고 모든 스케줄러에 대 한 최소 동시성을 충족 하기에 충분 한 하드웨어 스레드 많지 않은지 수 있습니다. 또 다른 가능성은 리소스 할당 되어 있는지 일시적으로 다른 스케줄러를 비활성화 하 고 해당 하드웨어 스레드에서 모든 가상 프로세서 루트를 통해,를 소유 하는 scheduler가 사용 하지 않는 경우.

하드웨어 스레드 구독 수준 구독된 스레드 수가 표시 됩니다 및 해당 하드웨어 스레드를 사용 하 여 연결 된 가상 프로세서 루트를 활성화 합니다. 특정 스케줄러의 관점에서 하드웨어 스레드 외부 구독 수준 부분은 다른 스케줄러에 영향을 구독 합니다. 알림 리소스는 외부에서 사용 중인 하드웨어 스레드에 대 한 외부 구독 수준 양의 territory에 0에서 이동 하면 스케줄러에 전송 됩니다.

정책이 스케줄러에만이 메서드를 통해 알림을 전송 됩니다 위치에 대 한 값을 `MinConcurrency` 정책 키에 대 한 값 같음은 `MaxConcurrency` 정책 키. 스케줄러 정책에 대 한 자세한 내용은 참조 하세요. [SchedulerPolicy](schedulerpolicy-class.md)합니다.

알림에 대 한 정하는 스케줄러는 집합을 가져옵니다 초기 알림를 만들 때만 할당 된 리소스는 외부에서 사용 중 또는 유휴 상태 여부를 알립니다.

##  <a name="notifyresourcesexternallyidle"></a>  Ischeduler:: Notifyresourcesexternallyidle 메서드

하드웨어 스레드 배열에 있는 가상 프로세서 루트의 집합을 나타내는이 스케줄러에 알립니다 `ppVirtualProcessorRoots` 다른 스케줄러에 의해 사용 되지 않습니다.

```
virtual void NotifyResourcesExternallyIdle(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```

### <a name="parameters"></a>매개 변수

*ppVirtualProcessorRoots*<br/>
배열을 `IVirtualProcessorRoot` 인터페이스가 있는 다른 스케줄러가 유휴 상태가 된 하드웨어 스레드를 사용 하 여 연결 합니다.

*count*<br/>
수가 `IVirtualProcessorRoot` 배열에 대 한 인터페이스입니다.

### <a name="remarks"></a>설명

특정 하드웨어 스레드를 동시에 여러 스케줄러에 할당할 수는 것이 가능 합니다. 그 이유 중 하나는 시스템 리소스를 공유 하지 않고 모든 스케줄러에 대 한 최소 동시성을 충족 하기에 충분 한 하드웨어 스레드 많지 않은지 수 있습니다. 또 다른 가능성은 리소스 할당 되어 있는지 일시적으로 다른 스케줄러를 비활성화 하 고 해당 하드웨어 스레드에서 모든 가상 프로세서 루트를 통해,를 소유 하는 scheduler가 사용 하지 않는 경우.

하드웨어 스레드 구독 수준 구독된 스레드 수가 표시 됩니다 및 해당 하드웨어 스레드를 사용 하 여 연결 된 가상 프로세서 루트를 활성화 합니다. 특정 스케줄러의 관점에서 하드웨어 스레드 외부 구독 수준 부분은 다른 스케줄러에 영향을 구독 합니다. 알림 리소스는 외부에서 사용 중인 하드웨어 스레드에 대 한 외부 구독 수준에서 이전 양수 값을 0으로 떨어질 때 스케줄러에 전송 됩니다.

정책이 스케줄러에만이 메서드를 통해 알림을 전송 됩니다 위치에 대 한 값을 `MinConcurrency` 정책 키에 대 한 값 같음은 `MaxConcurrency` 정책 키. 스케줄러 정책에 대 한 자세한 내용은 참조 하세요. [SchedulerPolicy](schedulerpolicy-class.md)합니다.

알림에 대 한 정하는 스케줄러는 집합을 가져옵니다 초기 알림를 만들 때만 할당 된 리소스는 외부에서 사용 중 또는 유휴 상태 여부를 알립니다.

##  <a name="removevirtualprocessors"></a>  IScheduler::RemoveVirtualProcessors Method

이 스케줄러에 이전에 할당 된 가상 프로세서 루트의 제거를 시작 합니다.

```
virtual void RemoveVirtualProcessors(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```

### <a name="parameters"></a>매개 변수

*ppVirtualProcessorRoots*<br/>
배열을 `IVirtualProcessorRoot` 제거할 가상 프로세서 루트를 나타내는 인터페이스입니다.

*count*<br/>
수가 `IVirtualProcessorRoot` 배열에 대 한 인터페이스입니다.

### <a name="remarks"></a>설명

Resource Manager를 호출 하 여 `RemoveVirtualProcessors` 스케줄러에서 다시 가상 프로세서 루트의 집합을 수행 하는 방법입니다. 스케줄러는 호출 해야 합니다 [제거](iexecutionresource-structure.md#remove) 가상 프로세서 루트를 사용 하 여 완료 되 면 각 인터페이스에서 메서드. 사용 하지 마십시오는 `IVirtualProcessorRoot` 호출한 후 인터페이스를 `Remove` 메서드를 합니다.

매개 변수 `ppVirtualProcessorRoots` 인터페이스의 배열을 가리킵니다. 제거할 가상 프로세서 루트도 집합 간에 활성화 되지 않은 루트 사용 하 여 즉시 반환 될 수는 `Remove` 메서드. 루트는 활성화 된 서비스와 작업을 실행 하거나 또는 비활성화 된 있고 작업 도착 하기를 기다리고 비동기적으로 반환 되어야 합니다. 스케줄러에는 가상 프로세서 루트를 최대한 빨리 제거 하려고 할 때마다 확인 해야 합니다. 가상 프로세서 루트 제거 지연 스케줄러 내의 의도 하지 않은 초과 될 수 있습니다.

##  <a name="statistics"></a>  Ischeduler:: Statistics 메서드

작업 도착 및 완료 비율 및 스케줄러에 대 한 변경의 큐 길이 관련 된 정보를 제공 합니다.

```
virtual void Statistics(
    _Out_ unsigned int* pTaskCompletionRate,
    _Out_ unsigned int* pTaskArrivalRate,
    _Out_ unsigned int* pNumberOfTasksEnqueued) = 0;
```

### <a name="parameters"></a>매개 변수

*pTaskCompletionRate*<br/>
이 메서드를 마지막으로 호출한 이후 scheduler에 의해 완료 된 작업의 수입니다.

*pTaskArrivalRate*<br/>
이 메서드를 마지막으로 호출한 이후 스케줄러에 도착 한 태스크 수입니다.

*pNumberOfTasksEnqueued*<br/>
모든 스케줄러 큐에 작업의 총 수입니다.

### <a name="remarks"></a>설명

이 메서드는 리소스 관리자에서 스케줄러에 대 한 통계를 수집 하기 위해 호출 됩니다. 여기에 수집 된 통계는 스케줄러에 더 많은 리소스를 할당 하려면 적절 한 경우 및 리소스를 소모할 시기를 결정 하는 동적 피드백 알고리즘 드라이브에 사용 됩니다. Scheduler에 의해 제공 된 값 최적화 될 수 있으며 반드시 않아도 현재 수를 정확 하 게 반영 합니다.

리소스 관리자에서 작업 도착 등에 대한 피드백을 사용하여 사용자의 스케줄러와 리소스 관리자에 등록된 다른 스케줄러 간에 리소스 균형을 조정하는 방법을 결정하려면 이 메서드를 구현해야 합니다. 통계를 수집 하지 않으려는 경우에 정책 키를 설정할 수 있습니다 `DynamicProgressFeedback` 값으로 `DynamicProgressFeedbackDisabled` Manager 스케줄러의 정책 및 리소스에 스케줄러에서이 메서드를 호출 하지 됩니다.

통계 정보가 없는 경우, Resource Manager에서는 하드웨어 스레드 구독 수준 리소스 할당 및 마이그레이션 결정을 내릴 수 사용 합니다. 구독 수준에 대 한 자세한 내용은 참조 하세요. [iexecutionresource:: Currentsubscriptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel)합니다.

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[PolicyElementKey](concurrency-namespace-enums.md)<br/>
[SchedulerPolicy 클래스](schedulerpolicy-class.md)<br/>
[IExecutionContext 구조체](iexecutioncontext-structure.md)<br/>
[IThreadProxy 구조체](ithreadproxy-structure.md)<br/>
[IVirtualProcessorRoot 구조체](ivirtualprocessorroot-structure.md)<br/>
[IResourceManager 구조체](iresourcemanager-structure.md)
