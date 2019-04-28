---
title: Context 클래스
ms.date: 11/04/2016
f1_keywords:
- Context
- CONCRT/concurrency::Context
- CONCRT/concurrency::Context::Block
- CONCRT/concurrency::Context::CurrentContext
- CONCRT/concurrency::Context::GetId
- CONCRT/concurrency::Context::GetScheduleGroupId
- CONCRT/concurrency::Context::GetVirtualProcessorId
- CONCRT/concurrency::Context::Id
- CONCRT/concurrency::Context::IsCurrentTaskCollectionCanceling
- CONCRT/concurrency::Context::IsSynchronouslyBlocked
- CONCRT/concurrency::Context::Oversubscribe
- CONCRT/concurrency::Context::ScheduleGroupId
- CONCRT/concurrency::Context::Unblock
- CONCRT/concurrency::Context::VirtualProcessorId
- CONCRT/concurrency::Context::Yield
helpviewer_keywords:
- Context class
ms.assetid: c0d553f3-961d-4ecd-9a29-4fa4351673b8
ms.openlocfilehash: 9074dad572a3a74a5b456e9790dc359ddf8b7c60
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62262751"
---
# <a name="context-class"></a>Context 클래스

실행 컨텍스트에 대한 추상화를 나타냅니다.

## <a name="syntax"></a>구문

```
class Context;
```

## <a name="members"></a>멤버

### <a name="protected-constructors"></a>Protected 생성자

|이름|설명|
|----------|-----------------|
|[~ Context 소멸자](#dtor)||

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[블록](#block)|현재 컨텍스트를 차단 합니다.|
|[CurrentContext](#currentcontext)|현재 컨텍스트에 대 한 포인터를 반환합니다.|
|[GetId](#getid)|컨텍스트에 속한 스케줄러 내의 고유한 컨텍스트에 대 한 식별자를 반환 합니다.|
|[GetScheduleGroupId](#getschedulegroupid)|컨텍스트는 현재 작업의 일정 그룹에 대 한 식별자를 반환 합니다.|
|[GetVirtualProcessorId](#getvirtualprocessorid)|컨텍스트는 현재 실행 중인 가상 프로세서에 대 한 식별자를 반환 합니다.|
|[ID](#id)|현재 컨텍스트의 현재 컨텍스트에 속한 scheduler 내에서 고유한 식별자를 반환 합니다.|
|[IsCurrentTaskCollectionCanceling](#iscurrenttaskcollectioncanceling)|반환 여부를 현재 컨텍스트에서 현재 인라인으로 실행 하는 작업 컬렉션을 활성 취소를 도중 (또는 곧).|
|[IsSynchronouslyBlocked](#issynchronouslyblocked)|컨텍스트에서 동기적으로 차단 여부를 결정 합니다. 컨텍스트를 명시적으로 차단 발생 하는 작업을 수행한 경우 동기적으로 차단으로 간주 됩니다.|
|[초과 구독](#oversubscribe)|해당 스케줄러의 가상 프로세서 중 하나에서 실행 컨텍스트에서 호출 될 때 코드 블록 기간에 대 한 스케줄러에 추가 가상 프로세서를 삽입 합니다.|
|[ScheduleGroupId](#schedulegroupid)|현재 컨텍스트는 일정 그룹에 대 한 식별자를 반환 합니다.|
|[차단 해제](#unblock)|컨텍스트를 차단 해제 되 고 실행할 수 없게 합니다.|
|[VirtualProcessorId](#virtualprocessorid)|현재 컨텍스트를 실행 하는 가상 프로세서에 대 한 식별자를 반환 합니다.|
|[Yield](#yield)|다른 컨텍스트에서 실행할 수 있도록 실행을 양도합니다. 양도할 수 있는 다른 컨텍스트가 없는 경우 스케줄러에서 다른 운영 체제 스레드에 양도할 수 있습니다.|

## <a name="remarks"></a>설명

동시성 런타임 스케줄러 (참조 [스케줄러](scheduler-class.md)) 응용 프로그램에서 작업을 실행 하려면 실행 컨텍스트를 사용 하 여 큐에 추가 합니다. Win32 스레드는 Windows 운영 체제에서 실행 컨텍스트의 예시입니다.

언제 든 지 스케줄러의 동시성 수준을 리소스 관리자가 부여 하는 가상 프로세서의 수와 같습니다. 가상 프로세서에는 처리 리소스 및 기본 시스템의 하드웨어 스레드로 맵에 대 한 추상화입니다. 지정된 된 시간에만 단일 스케줄러 컨텍스트는 가상 프로세서에서 실행할 수 있습니다.

스케줄러는 본질적으로 협조적를 대기 상태로 전환 하려는 경우 실행 컨텍스트를 언제 든 지 다른 컨텍스트로 가상 프로세서 생성 수 없습니다. 해당 대기가 충족 하는 경우 스케줄러에서 사용 가능한 가상 프로세서는 실행을 시작할 때까지 다시 시작할 수 없습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`Context`

## <a name="requirements"></a>요구 사항

**헤더:** concrt.h

**네임스페이스:** 동시성

##  <a name="block"></a> Block

현재 컨텍스트를 차단 합니다.

```
static void __cdecl Block();
```

### <a name="remarks"></a>설명

이 메서드를 사용하면 현재 호출 컨텍스트와 연결된 스케줄러가 없는 경우 프로세스의 기본 스케줄러가 생성되고 호출 컨텍스트에 연결됩니다.

가상 프로세서를 실행 하거나 수를 잠재적으로 다른 실행 가능한 컨텍스트를 찾을 수 호출 컨텍스트로 가상 프로세서에서 실행 중인 경우 새로 만듭니다.

후는 `Block` 메서드를 호출한 또는 호출할 호출 하 여 연결 해야 합니다 [차단 해제](#unblock) 다시 실행 하기 위해에서 다른 실행 컨텍스트에서 메서드. 여기서 게시 하는 코드가 다른 스레드에서 호출할 수 있으려면 해당 컨텍스트 지점 간의 중요 한 것에 유의 하세요 합니다 `Unblock` 메서드 및 실제 메서드를 호출 하는 위치 지점 `Block` 이루어집니다. 이 기간 동안에는 잠금 가져오기 등과 같은 개별적인 이유로 차단하거나 차단 해제할 수 있는 메서드를 호출해서는 안 됩니다. 호출을 `Block` 및 `Unblock` 메서드 차단 및 차단 해제 이유를 추적 하지 않습니다. 하나의 개체의 소유권을 가져야를 `Block` -  `Unblock` 쌍입니다.

이 메서드는 다양 한 예외를 포함 하 여 발생할 수 있습니다 [scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md)합니다.

##  <a name="dtor"></a> ~Context

```
virtual ~Context();
```

##  <a name="currentcontext"></a> CurrentContext

현재 컨텍스트에 대 한 포인터를 반환합니다.

```
static Context* __cdecl CurrentContext();
```

### <a name="return-value"></a>반환 값

현재 컨텍스트에 대 한 포인터입니다.

### <a name="remarks"></a>설명

이 메서드를 사용하면 현재 호출 컨텍스트와 연결된 스케줄러가 없는 경우 프로세스의 기본 스케줄러가 생성되고 호출 컨텍스트에 연결됩니다.

##  <a name="getid"></a> GetId

컨텍스트에 속한 스케줄러 내의 고유한 컨텍스트에 대 한 식별자를 반환 합니다.

```
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>반환 값

컨텍스트에 속한 스케줄러 내의 고유한 컨텍스트에 대 한 식별자입니다.

##  <a name="getschedulegroupid"></a> GetScheduleGroupId

컨텍스트는 현재 작업의 일정 그룹에 대 한 식별자를 반환 합니다.

```
virtual unsigned int GetScheduleGroupId() const = 0;
```

### <a name="return-value"></a>반환 값

컨텍스트는 현재 작업 일정 그룹에 대 한 식별자입니다.

### <a name="remarks"></a>설명

이 메서드의 반환 값은 컨텍스트를 실행 하는 일정 그룹의 순간 샘플링입니다. 이 메서드가 현재 컨텍스트가 아닌 다른 컨텍스트에서 호출될 경우 값은 반환되는 순간에 부실 값이 되어 사용할 수 없습니다. 일반적으로이 메서드를 디버깅 하거나 추적 목적 으로만 사용 됩니다.

##  <a name="getvirtualprocessorid"></a> GetVirtualProcessorId

컨텍스트는 현재 실행 중인 가상 프로세서에 대 한 식별자를 반환 합니다.

```
virtual unsigned int GetVirtualProcessorId() const = 0;
```

### <a name="return-value"></a>반환 값

컨텍스트 식별자 컨텍스트; 입력 시 현재 실행 중인 가상 프로세서를 가상 프로세서에서 현재 실행 되는 경우 그렇지 않으면 값 `-1`합니다.

### <a name="remarks"></a>설명

이 메서드의 반환 값은 컨텍스트를 실행 하는 가상 프로세서의 순간 샘플링입니다. 이 값은 반환되는 순간 부실할 수 있으며, 이 값에 의존할 수 없습니다. 일반적으로이 메서드를 디버깅 하거나 추적 목적 으로만 사용 됩니다.

##  <a name="id"></a> Id

현재 컨텍스트의 현재 컨텍스트에 속한 scheduler 내에서 고유한 식별자를 반환 합니다.

```
static unsigned int __cdecl Id();
```

### <a name="return-value"></a>반환 값

현재 컨텍스트가 현재 컨텍스트에 속한; 스케줄러 내의 고유한 현재 컨텍스트에 대 한 식별자는 스케줄러에 연결 된 경우 그렇지 않으면 값 `-1`합니다.

##  <a name="iscurrenttaskcollectioncanceling"></a> IsCurrentTaskCollectionCanceling

반환 여부를 현재 컨텍스트에서 현재 인라인으로 실행 하는 작업 컬렉션을 활성 취소를 도중 (또는 곧).

```
static bool __cdecl IsCurrentTaskCollectionCanceling();
```

### <a name="return-value"></a>반환 값

스케줄러를 호출 컨텍스트에 연결 된 작업 그룹에서 실행 되 고 작업 인라인 해당 컨텍스트를 여부를 해당 작업 그룹을 활성 취소 도중 (또는 곧); 그렇지 않으면 값 `false`합니다.

##  <a name="issynchronouslyblocked"></a> IsSynchronouslyBlocked

컨텍스트에서 동기적으로 차단 여부를 결정 합니다. 컨텍스트를 명시적으로 차단 발생 하는 작업을 수행한 경우 동기적으로 차단으로 간주 됩니다.

```
virtual bool IsSynchronouslyBlocked() const = 0;
```

### <a name="return-value"></a>반환 값

여부 컨텍스트에서 동기적으로 차단 합니다.

### <a name="remarks"></a>설명

컨텍스트를 명시적으로 차단 발생 하는 작업을 수행한 경우 동기적으로 차단으로 간주 됩니다. 스레드 스케줄러에서 이는 `Context::Block` 메서드에 대한 직접 호출이나 `Context::Block` 메서드를 사용하여 작성된 동기화 개체를 나타냅니다.

이 메서드의 반환 값은 컨텍스트에서 동기적으로 차단 여부의 순간 샘플. 이 값 반환 되 고 특정 상황 에서만 사용할 수 있습니다 하는 순간 부실 수 있습니다.

##  <a name="operator_delete"></a> delete 연산자

`Context` 개체 런타임에서 내부적으로 소멸 됩니다. 개체를 명시적으로 삭제할 수 없습니다.

```
void operator delete(void* _PObject);
```

### <a name="parameters"></a>매개 변수

*_PObject*<br/>
삭제할 개체에 대 한 포인터입니다.

##  <a name="oversubscribe"></a> 초과 구독

해당 스케줄러의 가상 프로세서 중 하나에서 실행 컨텍스트에서 호출 될 때 코드 블록 기간에 대 한 스케줄러에 추가 가상 프로세서를 삽입 합니다.

```
static void __cdecl Oversubscribe(bool _BeginOversubscription);
```

### <a name="parameters"></a>매개 변수

*_BeginOversubscription*<br/>
하는 경우 **true**, 초과 구독의 기간에서 추가 가상 프로세서를 추가 해야 함을 나타냅니다. 하는 경우 **false**를 나타내는 값을 초과 구독이 종료 되어야 하는 이전에 추가한 가상 프로세서를 제거 해야 합니다.

##  <a name="schedulegroupid"></a> ScheduleGroupId

현재 컨텍스트는 일정 그룹에 대 한 식별자를 반환 합니다.

```
static unsigned int __cdecl ScheduleGroupId();
```

### <a name="return-value"></a>반환 값

입력 시 현재 컨텍스트의 작동 스케줄러에 현재 컨텍스트와 연결 된 경우에 일정 그룹에 대 한 작업 스케줄러에 대 한 식별자 그룹 그렇지 않으면 값 `-1`합니다.

##  <a name="unblock"></a> Unblock

컨텍스트를 차단 해제 되 고 실행할 수 없게 합니다.

```
virtual void Unblock() = 0;
```

### <a name="remarks"></a>설명

에 대 한 호출에 대 한 완벽 하 게 유효 합니다 `Unblock` 해당 호출 앞에 야 하는 방법의 [블록](#block) 메서드. 호출로 서 오랫동안 합니다 `Block` 및 `Unblock` 메서드 제대로 쌍을 이루는, 런타임에서 제대로 정렬의 자연 스러운 경합을 처리 합니다. `Unblock` 하기 전에 들어오는 호출을 `Block` 호출의 효과 부정 합니다는 `Block` 호출 합니다.

이 메서드에서 throw 될 수 있는 몇 가지 예외가 있습니다. 컨텍스트를 호출 하려고 하는 경우는 `Unblock` 자체에서 메서드를 [context_self_unblock](context-self-unblock-class.md) 예외가 throw 됩니다. 경우에 대 한 호출 `Block` 하 고 `Unblock` 쌍이 잘못 된 (예를 들어 두 호출 `Unblock` 현재 실행 중인 컨텍스트에 대 한 내용이), [context_unblock_unbalanced](context-unblock-unbalanced-class.md) 예외가 throw 됩니다.

여기서 게시 하는 코드가 다른 스레드에서 호출할 수 있으려면 해당 컨텍스트 지점 간의 중요 한 것에 유의 하세요 합니다 `Unblock` 메서드 및 실제 메서드를 호출 하는 위치 지점 `Block` 이루어집니다. 이 기간 동안에는 잠금 가져오기 등과 같은 개별적인 이유로 차단하거나 차단 해제할 수 있는 메서드를 호출해서는 안 됩니다. 호출을 `Block` 및 `Unblock` 메서드 차단 및 차단 해제 이유를 추적 하지 않습니다. 하나의 개체의 소유권을 가져야를 `Block` 고 `Unblock` 쌍입니다.

##  <a name="virtualprocessorid"></a> VirtualProcessorId

현재 컨텍스트를 실행 하는 가상 프로세서에 대 한 식별자를 반환 합니다.

```
static unsigned int __cdecl VirtualProcessorId();
```

### <a name="return-value"></a>반환 값

현재 컨텍스트가 현재 컨텍스트에;에서 실행 중인 가상 프로세서에 대 한 식별자는 스케줄러에 연결 된 경우 그렇지 않으면 값 `-1`합니다.

### <a name="remarks"></a>설명

이 메서드의 반환 값은 현재 컨텍스트를 실행 하는 가상 프로세서의 순간 샘플링입니다. 이 값은 반환되는 순간 부실할 수 있으며, 이 값에 의존할 수 없습니다. 일반적으로이 메서드를 디버깅 하거나 추적 목적 으로만 사용 됩니다.

##  <a name="yield"></a> yield

다른 컨텍스트에서 실행할 수 있도록 실행을 양도합니다. 양도할 수 있는 다른 컨텍스트가 없는 경우 스케줄러에서 다른 운영 체제 스레드에 양도할 수 있습니다.

```
static void __cdecl Yield();
```

### <a name="remarks"></a>설명

이 메서드를 사용하면 현재 호출 컨텍스트와 연결된 스케줄러가 없는 경우 프로세스의 기본 스케줄러가 생성되고 호출 컨텍스트에 연결됩니다.

##  <a name="yieldexecution"></a> YieldExecution

다른 컨텍스트에서 실행할 수 있도록 실행을 양도합니다. 양도할 수 있는 다른 컨텍스트가 없는 경우 스케줄러에서 다른 운영 체제 스레드에 양도할 수 있습니다.

```
static void __cdecl YieldExecution();
```

### <a name="remarks"></a>설명

이 메서드를 사용하면 현재 호출 컨텍스트와 연결된 스케줄러가 없는 경우 프로세스의 기본 스케줄러가 생성되고 호출 컨텍스트에 연결됩니다.

이 함수는 Visual Studio 2015의 새로운와 동일 합니다 [Yield](#yield) 작동 하지만 Windows.h의 Yield 매크로와 충돌 하지 않습니다.

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[Scheduler 클래스](scheduler-class.md)<br/>
[작업 스케줄러](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)
