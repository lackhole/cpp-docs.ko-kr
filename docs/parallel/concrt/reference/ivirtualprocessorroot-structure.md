---
title: IVirtualProcessorRoot 구조체
ms.date: 11/04/2016
f1_keywords:
- IVirtualProcessorRoot
- CONCRTRM/concurrency::IVirtualProcessorRoot
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::Activate
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::Deactivate
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::EnsureAllTasksVisible
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::GetId
helpviewer_keywords:
- IVirtualProcessorRoot structure
ms.assetid: 5ef371b8-9e4f-4fef-bb0d-49099693dd2b
ms.openlocfilehash: 25ede76a81a77d489d0f2316bd3ae4cb7f84d704
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344043"
---
# <a name="ivirtualprocessorroot-structure"></a>IVirtualProcessorRoot 구조체

스레드 프록시가 실행될 수 있는 하드웨어 스레드의 추상화입니다.

## <a name="syntax"></a>구문

```
struct IVirtualProcessorRoot : public IExecutionResource;
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[IVirtualProcessorRoot::Activate](#activate)|실행 컨텍스트 인터페이스에 연결 된 스레드 프록시가 `pContext` 이 가상 프로세서 루트에서 실행을 시작 합니다.|
|[IVirtualProcessorRoot::Deactivate](#deactivate)|스레드 프록시가 실행 컨텍스트를 발송을 중지 하려면이 가상 프로세서 루트에서 현재 실행 합니다. 스레드 프록시는 사용자에 게 다시 시작에 대 한 호출에서 실행 됩니다는 `Activate` 메서드.|
|[IVirtualProcessorRoot::EnsureAllTasksVisible](#ensurealltasksvisible)|시스템에서 모든 프로세서에 표시 되려면 개별 프로세서 메모리 계층 구조에 저장 된 데이터를 발생 합니다. 메서드가 반환 되기 전에 모든 프로세서에서 전체 메모리 펜스를가 실행 되었음을 확인 합니다.|
|[IVirtualProcessorRoot::GetId](#getid)|가상 프로세서 루트에 대 한 고유 식별자를 반환합니다.|

## <a name="remarks"></a>설명

모든 가상 프로세서 루트에 연결 된 실행 리소스입니다. 합니다 `IVirtualProcessorRoot` 인터페이스에서 상속 되는 [IExecutionResource](iexecutionresource-structure.md) 인터페이스입니다. 여러 가상 프로세서 루트는 동일한 기본 하드웨어 스레드로 해당할 수 있습니다.

Resource Manager 리소스에 대 한 요청에 응답 하는 스케줄러에 가상 프로세서 루트를 부여합니다. 스케줄러를 실행 컨텍스트를 사용 하 여 활성화 하 여 작업을 수행 하는 가상 프로세서 루트를 사용할 수 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[IExecutionResource](iexecutionresource-structure.md)

`IVirtualProcessorRoot`

## <a name="requirements"></a>요구 사항

**헤더:** concrtrm.h

**네임스페이스:** 동시성

##  <a name="activate"></a>  Ivirtualprocessorroot:: Activate 메서드

실행 컨텍스트 인터페이스에 연결 된 스레드 프록시가 `pContext` 이 가상 프로세서 루트에서 실행을 시작 합니다.

```
virtual void Activate(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>매개 변수

*pContext*<br/>
이 가상 프로세서 루트에서 발송 되는 실행 컨텍스트를 사용 하는 인터페이스입니다.

### <a name="remarks"></a>설명

실행 컨텍스트 인터페이스를 사용 하 여 연결 되지 않은 경우 Resource Manager 스레드 프록시를 제공 합니다. `pContext`

`Activate` 리소스 관리자에서 반환 하는 새 가상 프로세서 루트에서 작업 실행을 시작 하거나는 비활성화 하거나 비활성화 하는 가상 프로세서 루트에서 스레드 프록시를 다시 메서드를 사용할 수 있습니다. 참조 [ivirtualprocessorroot:: Deactivate](#deactivate) 비활성화에 대 한 자세한 내용은 합니다. 비활성화 된 가상 프로세서 루트를 매개 변수를 다시 시작 된 경우 `pContext` 가상 프로세서 루트를 비활성화 하는 데 사용 하는 매개 변수와 동일 해야 합니다.

가상 프로세서 루트를 처음으로 후속 쌍에 대 한 호출에 대 한 활성화 된 후 `Deactivate` 고 `Activate` 서로 경쟁할 수 있습니다. 즉, Resource Manager에 대 한 호출을 수신 하도록 허용 되는 것 `Activate` 받기 전에 `Deactivate` 을 호출 합니다.

가상 프로세서 루트를 활성화 하면 나타낸다고 Resource Manager에이 가상 프로세서 루트는 작업을 사용 하 여 현재 사용 중입니다. 호출 하는데 스케줄러를이 루트에서 실행할 수 없는 경우는 `Deactivate` 유휴 가상 프로세서 루트는 리소스 관리자에 게 알리는 메서드. Resource Manager는 부하 분산 시스템을 위해이 데이터를 사용 합니다.

`invalid_argument` 경우 발생 하는 인수 `pContext` 기본값이 `NULL`합니다.

`invalid_operation` 경우 throw 되는 인수 `pContext` 최근이 가상 프로세서 루트에서 디스패치 된 실행 컨텍스트를 나타내지 않습니다.

가상 프로세서 루트를 활성화 act 기본 하드웨어 스레드의 구독 수준이 하나 증가 합니다. 구독 수준에 대 한 자세한 내용은 참조 하세요. [iexecutionresource:: Currentsubscriptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel)합니다.

##  <a name="deactivate"></a>  Ivirtualprocessorroot:: Deactivate 메서드

스레드 프록시가 실행 컨텍스트를 발송을 중지 하려면이 가상 프로세서 루트에서 현재 실행 합니다. 스레드 프록시는 사용자에 게 다시 시작에 대 한 호출에서 실행 됩니다는 `Activate` 메서드.

```
virtual bool Deactivate(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>매개 변수

*pContext*<br/>
현재이 루트에서 디스패치되는 컨텍스트.

### <a name="return-value"></a>반환 값

부울 값입니다. 값 **true** 스레드 프록시를 반환 합니다 `Deactivate` 메서드 호출에 대 한 응답에서는 `Activate` 메서드. 값 `false` 스레드 프록시 리소스 관리자에서 알림 이벤트에 대 한 응답으로 메서드에서 반환 함을 나타냅니다. 사용자 모드 예약 가능 (UMS) 스레드 스케줄러에서이 나타내고 항목 스케줄러의 완성 목록에 표시 스케줄러 처리 해야 합니다.

### <a name="remarks"></a>설명

가상 프로세서 루트를 실행 하 여 스케줄러에서 작업을 찾을 수 없는 경우 일시적으로 중지 하려면이 메서드를 사용 합니다. 에 대 한 호출을 `Deactivate` 메서드 내에서 발생 해야 합니다는 `Dispatch` 가상 프로세서 루트와 마지막으로 활성화 된 실행 컨텍스트의 메서드입니다. 즉, 호출 스레드 프록시를 `Deactivate` 메서드는 가상 프로세서 루트에서 현재 실행 중인 것 이어야 합니다. 실행 되지 하는 가상 프로세서 루트에서 메서드를 호출 합니다. 정의 되지 않은 동작이 발생할 수 있습니다.

비활성화 된 가상 프로세서 루트에 대 한 호출을 사용 하 여 해제 될 수 있습니다 합니다 `Activate` 에 전달 된 것과 같은 인수를 사용 하 여 메서드를 `Deactivate` 메서드. Scheduler는를 호출 하는 것을 담당 합니다 `Activate` 및 `Deactivate` 메서드 쌍을 있지만 특정 순서 대로 수신 해야 하는 것은 아닙니다. Resource Manager에 대 한 호출을 받는 처리할 수는 `Activate` 메서드 호출을 수신 하기 전에 `Deactivate` 을 메서드.

가상 프로세서 루트를 활성화 되는 경우의 반환 값을 `Deactivate` 메서드는 값 **false**, 스케줄러를 통해 UMS 완성 목록을 쿼리해야 합니다.는 `IUMSCompletionList::GetUnblockNotifications` 메서드는 해당 정보에는 act 차례로 호출 이후에 `Deactivate` 메서드를 다시 합니다. 이 때까지 반복 해야 합니다 `Deactivate` 메서드 값을 반환 합니다. `true`합니다.

`invalid_argument` 경우 발생 하는 인수 `pContext` 기본값이 NULL입니다.

`invalid_operation` 가상 프로세서 루트에서 활성화 되지 않은 경우 발생 하는 인수 또는 `pContext` 최근이 가상 프로세서 루트에서 디스패치 된 실행 컨텍스트를 나타내지 않습니다.

가상 프로세서 루트를 비활성화 하면 act 구독 수준의 기본 하드웨어 스레드 하나 감소 합니다. 구독 수준에 대 한 자세한 내용은 참조 하세요. [iexecutionresource:: Currentsubscriptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel)합니다.

##  <a name="ensurealltasksvisible"></a>  Ivirtualprocessorroot:: Ensurealltasksvisible 메서드

시스템에서 모든 프로세서에 표시 되려면 개별 프로세서 메모리 계층 구조에 저장 된 데이터를 발생 합니다. 메서드가 반환 되기 전에 모든 프로세서에서 전체 메모리 펜스를가 실행 되었음을 확인 합니다.

```
virtual void EnsureAllTasksVisible(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>매개 변수

*pContext*<br/>
현재이 가상 프로세서 루트에서 디스패치되는 컨텍스트.

### <a name="remarks"></a>설명

새 작업 스케줄러에 추가 하 여 비활성화는 가상 프로세서 루트를 동기화 하려는 경우이 메서드를 유용 알 수 있습니다. 성능상의 이유로 단일 프로세서의 실행 스레드에서 추가 하는 작업 항목 다른 모든 프로세서에 즉시 표시 되지 않습니다. 즉는 메모리 장벽을 실행 하지 않고 스케줄러에 작업 항목을 추가할 결정할 수 있습니다. 와 함께에서이 메서드를 사용 하 여는 `Deactivate` 메서드 스케줄러 모든 가상 프로세서를 비활성화 하지 않도록 보장할 수 있습니다 작업 항목이 스케줄러의 컬렉션에 존재 하는 동안 루트입니다.

에 대 한 호출을 `EnsureAllTasksVisibleThe` 메서드 내에서 발생 해야 합니다는 `Dispatch` 가상 프로세서 루트와 마지막으로 활성화 된 실행 컨텍스트의 메서드입니다. 즉, 호출 스레드 프록시를 `EnsureAllTasksVisible` 메서드는 가상 프로세서 루트에서 현재 실행 중인 것 이어야 합니다. 실행 되지 하는 가상 프로세서 루트에서 메서드를 호출 합니다. 정의 되지 않은 동작이 발생할 수 있습니다.

`invalid_argument` 경우 발생 하는 인수 `pContext` 기본값이 `NULL`합니다.

`invalid_operation` 가상 프로세서 루트에서 활성화 되지 않은 경우 발생 하는 인수 또는 `pContext` 최근이 가상 프로세서 루트에서 디스패치 된 실행 컨텍스트를 나타내지 않습니다.

##  <a name="getid"></a>  Ivirtualprocessorroot:: Getid 메서드

가상 프로세서 루트에 대 한 고유 식별자를 반환합니다.

```
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>반환 값

정수 식별자입니다.

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)
