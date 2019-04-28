---
title: IExecutionResource 구조체
ms.date: 11/04/2016
f1_keywords:
- IExecutionResource
- CONCRTRM/concurrency::IExecutionResource
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::CurrentSubscriptionLevel
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::GetExecutionResourceId
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::GetNodeId
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::Remove
helpviewer_keywords:
- IExecutionResource structure
ms.assetid: 6b27042b-b98c-4f7f-b831-566950af84cd
ms.openlocfilehash: 9f8f5c5629e9794ca8ee2cc6bedbc4ba6bfdb24d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62262517"
---
# <a name="iexecutionresource-structure"></a>IExecutionResource 구조체

하드웨어 스레드에 대한 추상화입니다.

## <a name="syntax"></a>구문

```
struct IExecutionResource;
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[IExecutionResource::CurrentSubscriptionLevel](#currentsubscriptionlevel)|활성화 된 가상 프로세서 수가 루트 및 외부 위협이 실행 리소스를 나타내는 기본 하드웨어 스레드를 사용 하 여 현재 연결 된 구독을 반환 합니다.|
|[IExecutionResource::GetExecutionResourceId](#getexecutionresourceid)|이 실행 리소스를 나타내는 하드웨어 스레드에 대 한 고유 식별자를 반환 합니다.|
|[IExecutionResource::GetNodeId](#getnodeid)|이 실행 리소스가 속한 프로세서 노드에 대 한 고유 식별자를 반환 합니다.|
|[IExecutionResource::Remove](#remove)|Resource Manager에이 실행 리소스를 반환합니다.|

## <a name="remarks"></a>설명

실행 리소스 취득 가능 하거나 가상 프로세서 루트를 사용 하 여 연결 합니다. 독립 실행형 실행 리소스를 응용 프로그램의 스레드는 스레드 구독을 만들 때 생성 됩니다. 메서드 [ISchedulerProxy::SubscribeThread](ischedulerproxy-structure.md#subscribecurrentthread) 하 고 [ischedulerproxy:: Requestinitialvirtualprocessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors) 스레드 구독을 만들고 반환을 `IExecutionResource` 인터페이스를 나타내는 구독입니다. 스레드 구독을 만드는 Resource Manager 스케줄러에 할당 된 가상 프로세서 루트와 함께 스케줄러에 큐에 대기 작업에 지정 된 스레드가 참가할 리소스 관리자를 알리는 방법입니다. 리소스 관리자를 사용 하드웨어 스레드의 초과 구독 하지 않으려면 수 있는 정보입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IExecutionResource`

## <a name="requirements"></a>요구 사항

**헤더:** concrtrm.h

**네임스페이스:** 동시성

##  <a name="currentsubscriptionlevel"></a>  Iexecutionresource:: Currentsubscriptionlevel 메서드

활성화 된 가상 프로세서 수가 루트 및 외부 위협이 실행 리소스를 나타내는 기본 하드웨어 스레드를 사용 하 여 현재 연결 된 구독을 반환 합니다.

```
virtual unsigned int CurrentSubscriptionLevel() const = 0;
```

### <a name="return-value"></a>반환 값

현재 구독 수준입니다.

### <a name="remarks"></a>설명

구독 수준 하드웨어 스레드를 사용 하 여 연결 된 실행 중인 스레드 수를 알려 줍니다. 이 리소스 관리자는 구독 한 스레드 및 스레드 프록시를 현재 실행 중인 가상 프로세서 루트의 형태로 인식 하는 스레드가 포함 됩니다.

메서드를 호출 [ischedulerproxy:: Subscribecurrentthread](ischedulerproxy-structure.md#subscribecurrentthread), 또는 메서드 [ischedulerproxy:: Requestinitialvirtualprocessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors) 매개 변수를 사용 하 여 `doSubscribeCurrentThread` 값으로설정**true** 씩 하드웨어 스레드 구독 수준을 증가 시킵니다. 반환 한다는 점에서 `IExecutionResource` 구독을 나타내는 인터페이스입니다. 해당 호출을 [iexecutionresource:: Remove](#remove) 감소 씩 하드웨어 스레드의 구독 수준입니다.

메서드를 사용 하는 가상 프로세서 루트를 활성화 act [ivirtualprocessorroot:: Activate](ivirtualprocessorroot-structure.md#activate) 구독 수준 하드웨어 스레드를 1 씩입니다. 메서드 [ivirtualprocessorroot:: Deactivate](ivirtualprocessorroot-structure.md#deactivate), 또는 [iexecutionresource:: Remove](#remove) 구독 수준은 활성화 된 가상 프로세서 루트에서 호출 되 면 1 씩 감소 합니다.

Resource Manager 스케줄러 간에 리소스를 이동 하는 시기를 결정 하는 방법 중 하나로 구독 수준 정보를 사용 합니다.

##  <a name="getexecutionresourceid"></a>  Iexecutionresource:: Getexecutionresourceid 메서드

이 실행 리소스를 나타내는 하드웨어 스레드에 대 한 고유 식별자를 반환 합니다.

```
virtual unsigned int GetExecutionResourceId() const = 0;
```

### <a name="return-value"></a>반환 값

이 실행 리소스를 기본 하드웨어 스레드에 대 한 고유 식별자입니다.

### <a name="remarks"></a>설명

각 하드웨어 스레드는 동시성 런타임에서 고유 식별자를 할당 됩니다. 여러 실행 리소스에 연결 된 하드웨어 경우 스레드는 모두 동일한 실행 리소스 식별자를 갖습니다.

##  <a name="getnodeid"></a>  Iexecutionresource:: Getnodeid 메서드

이 실행 리소스가 속한 프로세서 노드에 대 한 고유 식별자를 반환 합니다.

```
virtual unsigned int GetNodeId() const = 0;
```

### <a name="return-value"></a>반환 값

프로세서 노드에 대 한 고유 식별자입니다.

### <a name="remarks"></a>설명

동시성 런타임 시스템에서 프로세서 노드의 그룹 하드웨어 스레드를 나타냅니다. 노드는 일반적으로 시스템의 하드웨어 토폴로지에서 파생 됩니다. 예를 들어, 특정 NUMA 노드 또는 특정 소켓의 모든 프로세서가 동일한 프로세서 노드에서 속할 수 있습니다. 부터 이러한 노드에 고유 식별자를 할당 하는 Resource Manager `0` including `nodeCount - 1`여기서 `nodeCount` 시스템에서 프로세서 노드의 총 수를 나타냅니다.

노드 함수에서 얻을 수 있습니다 [GetProcessorNodeCount](concurrency-namespace-functions.md)합니다.

##  <a name="remove"></a>  Iexecutionresource:: Remove 메서드

Resource Manager에이 실행 리소스를 반환합니다.

```
virtual void Remove(_Inout_ IScheduler* pScheduler) = 0;
```

### <a name="parameters"></a>매개 변수

*pScheduler*<br/>
이 실행 리소스를 제거를 요청 하는 스케줄러에는 인터페이스입니다.

### <a name="remarks"></a>설명

이 메서드를 사용 하 여 Resource Manager에 가상 프로세서 루트와 연결 된 실행 리소스 뿐만 아니라 독립 실행형 실행 리소스 돌아갑니다.

메서드 중 하나에서 수신 하는 경우 독립 실행형 실행 리소스 [ischedulerproxy:: Subscribecurrentthread](ischedulerproxy-structure.md#subscribecurrentthread) 또는 [ischedulerproxy:: Requestinitialvirtualprocessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors)를 호출 합니다 메서드 `Remove` 리소스를 만든 스레드 구독 종료 됨을 나타냅니다. 스케줄러 프록시를 종료 하기 전에 모든 스레드 구독을 종료 하는 데 필요한를 호출 해야 `Remove` 구독을 만든 스레드에서 합니다.

인터페이스 `Remove`는 `IVirtualProcessorRoot` 인터페이스에서 상속되기 때문에 `IExecutionResource` 메서드를 호출하여 리소스 관리자에 가상 프로세서 루트도 반환할 수 있습니다. 가상 프로세서 루트에 대 한 호출에 대 한 응답에서 반환 해야 합니다 [ischeduler:: Removevirtualprocessors](ischeduler-structure.md#removevirtualprocessors) 메서드를에서 얻은 줄이고자 가상 프로세서 루트를 사용 하 여 완료 되 면 또는 [ Ischedulerproxy:: Createoversubscriber](ischedulerproxy-structure.md#createoversubscriber) 메서드. 가상 프로세서 루트에 대 한 제한은 없습니다 스레드를 호출할 수는 `Remove` 메서드.

`invalid_argument` 경우 발생 하는 매개 변수 `pScheduler` 로 설정 된 `NULL`합니다.

`invalid_operation` 경우 발생 하는 매개 변수 `pScheduler` 현재 스레드의 스레드 구독을 만든 스레드가 아닌 다른 경우에이 실행 리소스가 만들어졌는지, 또는 독립 실행형 실행 리소스를 사용 하 여 스케줄러 다릅니다.

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[IVirtualProcessorRoot 구조체](ivirtualprocessorroot-structure.md)
