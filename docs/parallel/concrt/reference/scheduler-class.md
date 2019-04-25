---
title: Scheduler 클래스
ms.date: 11/04/2016
f1_keywords:
- Scheduler
- CONCRT/concurrency::Scheduler
- CONCRT/concurrency::Scheduler::Scheduler
- CONCRT/concurrency::Scheduler::Attach
- CONCRT/concurrency::Scheduler::Create
- CONCRT/concurrency::Scheduler::CreateScheduleGroup
- CONCRT/concurrency::Scheduler::GetNumberOfVirtualProcessors
- CONCRT/concurrency::Scheduler::GetPolicy
- CONCRT/concurrency::Scheduler::Id
- CONCRT/concurrency::Scheduler::IsAvailableLocation
- CONCRT/concurrency::Scheduler::Reference
- CONCRT/concurrency::Scheduler::RegisterShutdownEvent
- CONCRT/concurrency::Scheduler::Release
- CONCRT/concurrency::Scheduler::ResetDefaultSchedulerPolicy
- CONCRT/concurrency::Scheduler::ScheduleTask
- CONCRT/concurrency::Scheduler::SetDefaultSchedulerPolicy
helpviewer_keywords:
- Scheduler class
ms.assetid: 34cf7961-048d-4852-8a5c-a32f823e3506
ms.openlocfilehash: f27dace61b0764962a78695c2a4c6b180b09d7a3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160135"
---
# <a name="scheduler-class"></a>Scheduler 클래스

동시성 런타임 스케줄러에 대한 추상화를 나타냅니다.

## <a name="syntax"></a>구문

```
class Scheduler;
```

## <a name="members"></a>멤버

### <a name="protected-constructors"></a>Protected 생성자

|이름|설명|
|----------|-----------------|
|[Scheduler](#ctor)|개체는 `Scheduler` 클래스 팩터리 메서드를 사용 하 여 만든 수 또는 암시적으로 합니다.|
|[~ Scheduler 소멸자](#dtor)|개체는 `Scheduler` 클래스는 모든 외부 참조가 존재를 중단 하는 경우에 명시적으로 소멸 됩니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[Attach](#attach)|스케줄러를 호출 컨텍스트에 연결 합니다. 이 메서드에서 반환 된 후 스케줄러가 현재 스케줄러와 호출 컨텍스트에 scheduler에 의해 관리 됩니다.|
|[만들기](#create)|해당 동작이 설명 하는 새 스케줄러를 만듭니다는 `_Policy` 매개 변수는 스케줄러에서 초기 참조를 배치 하 고에 대 한 포인터를 반환 합니다.|
|[CreateScheduleGroup](#createschedulegroup)|오버로드됨. 스케줄러 내의 새 일정 그룹을 만듭니다. 매개 변수를 사용 하는 버전 `_Placement` 되도록 해당 매개 변수에 의해 지정 된 위치의 실행 새로 만든된 일정 그룹 내에서 작업을 발생 합니다.|
|[GetNumberOfVirtualProcessors](#getnumberofvirtualprocessors)|스케줄러에 대 한 가상 프로세서의 현재 수를 반환합니다.|
|[GetPolicy](#getpolicy)|스케줄러를 사용 하 여 생성 된 정책의 복사본을 반환 합니다.|
|[ID](#id)|스케줄러에 대 한 고유 식별자를 반환합니다.|
|[IsAvailableLocation](#isavailablelocation)|지정된 된 위치를 스케줄러에서 사용할 수 있는지 확인 합니다.|
|[참조](#reference)|스케줄러 참조 횟수를 증가 시킵니다.|
|[RegisterShutdownEvent](#registershutdownevent)|Windows 이벤트 핸들을 전달 하면은 `_Event` 매개 변수를 스케줄러를 종료 하 고 자체를 제거 하는 경우 신호를 보낼 수 있습니다. 이벤트 신호를 받는 경우 스케줄러에 예약한는 모든 작업이 완료 됩니다. 이 메서드를 통해 여러 종료 이벤트를 등록할 수 있습니다.|
|[릴리스](#release)|스케줄러 참조 횟수를 감소시킵니다.|
|[ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy)|기본 스케줄러 정책의 런타임 기본값으로 다시 설정합니다. 기본 스케줄러를 만든 다음에 런타임 기본 정책 설정이 사용 됩니다.|
|[ScheduleTask](#scheduletask)|오버로드됨. 스케줄러 내에서 간단한 작업을 예약합니다. 간단한 작업은 런타임에 의해 결정되는 일정 그룹에 배치됩니다. `_Placement` 매개 변수를 사용하는 버전은 작업이 지정된 위치에서 실행되도록 합니다.|
|[SetDefaultSchedulerPolicy](#setdefaultschedulerpolicy)|사용자 정의 정책을 기본 스케줄러를 만드는 데 사용할 수 있습니다. 프로세스 내에서 기본 스케줄러가 없는 경우에이 메서드를 호출할 수 있습니다. 다음 유효한 호출 일까 지 적용 됩니다는 기본 정책을 설정한 후 합니다 `SetDefaultSchedulerPolicy` 또는 [ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy) 메서드.|

## <a name="remarks"></a>설명

동시성 런타임 스케줄러 스레드와 같은 운영 체제 실행 컨텍스트를에 매핑되는 실행 컨텍스트를 사용 하 여, 작업 실행을 큐에 추가한 응용 프로그램입니다. 언제 든 지 스케줄러의 동시성 수준을 리소스 관리자가 부여 하는 가상 프로세서의 수와 같습니다. 가상 프로세서에는 처리 리소스 및 기본 시스템의 하드웨어 스레드로 맵에 대 한 추상화입니다. 지정된 된 시간에만 단일 스케줄러 컨텍스트는 가상 프로세서에서 실행할 수 있습니다.

동시성 런타임의 병렬 작업 실행 프로세스 마다 기본 스케줄러를 만듭니다. 또한 사용자 고유의 스케줄러 인스턴스를 만들 하 고이 클래스를 사용 하 여 조작할 수 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`Scheduler`

## <a name="requirements"></a>요구 사항

**헤더:** concrt.h

**네임스페이스:** 동시성

##  <a name="attach"></a> Attach

스케줄러를 호출 컨텍스트에 연결 합니다. 이 메서드에서 반환 된 후 스케줄러가 현재 스케줄러와 호출 컨텍스트에 scheduler에 의해 관리 됩니다.

```
virtual void Attach() = 0;
```

### <a name="remarks"></a>설명

스케줄러에 대 한 참조를 배치 스케줄러를 암시적으로 연결 합니다.

시점에서 나중에 호출 해야 합니다 [currentscheduler:: Detach](currentscheduler-class.md#detach) 메서드를 종료 하려면 스케줄러 수 있도록 합니다.

를 다른 스케줄러에 이미 연결 되어 있는 컨텍스트에서이 메서드를 호출 하면 이전 스케줄러로 기존 scheduler 기억 됩니다 및 새로 만든 스케줄러가 현재 스케줄러입니다. 호출 하는 경우는 `CurrentScheduler::Detach` 나중에 이전 스케줄러에 대 한 메서드는 현재 스케줄러로 복원 됩니다.

이 메서드는 throw 된 [improper_scheduler_attach](improper-scheduler-attach-class.md) 이 스케줄러는 현재 스케줄러 호출 컨텍스트의 경우 예외입니다.

##  <a name="create"></a> 만들기

해당 동작이 설명 하는 새 스케줄러를 만듭니다는 `_Policy` 매개 변수는 스케줄러에서 초기 참조를 배치 하 고에 대 한 포인터를 반환 합니다.

```
static Scheduler* __cdecl Create(const SchedulerPolicy& _Policy);
```

### <a name="parameters"></a>매개 변수

*_Policy*<br/>
새로 만든된 스케줄러의 동작을 설명 하는 scheduler 정책입니다.

### <a name="return-value"></a>반환 값

새로 만든된 스케줄러에 대 한 포인터입니다. 이 `Scheduler` 개체에 배치 될 초기 참조 개수입니다.

### <a name="remarks"></a>설명

스케줄러를 사용 하 여 만들어진 후 합니다 `Create` 호출 해야 합니다는 `Release` 초기 참조 횟수를 제거 하 고 종료 하려면 스케줄러를 허용 하기 위해 나중에 특정 시점 메서드.

이 메서드를 사용 하 여 만들어진 스케줄러 호출 컨텍스트에 연결 되지 됩니다. 사용 하 여 컨텍스트를 연결할 수 있습니다 합니다 [연결](#attach) 메서드.

이 메서드는 다양 한 예외를 포함 하 여 발생할 수 있습니다 [scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md) 하 고 [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md)합니다.

##  <a name="createschedulegroup"></a> CreateScheduleGroup

스케줄러 내의 새 일정 그룹을 만듭니다. 매개 변수를 사용 하는 버전 `_Placement` 되도록 해당 매개 변수에 의해 지정 된 위치의 실행 새로 만든된 일정 그룹 내에서 작업을 발생 합니다.

```
virtual ScheduleGroup* CreateScheduleGroup() = 0;

virtual ScheduleGroup* CreateScheduleGroup(location& _Placement) = 0;
```

### <a name="parameters"></a>매개 변수

*_Placement*<br/>
일정 그룹 내에서 작업 실행 편향가 있는 위치 참조입니다.

### <a name="return-value"></a>반환 값

새로 만든된 일정 그룹에 대 한 포인터입니다. 이 `ScheduleGroup` 개체에 배치 될 초기 참조 개수입니다.

### <a name="remarks"></a>설명

호출 해야 합니다는 [릴리스](schedulegroup-class.md#release) 일정 그룹 일정 관리 작업을 수행한 경우에 메서드. 스케줄러를 일정을 삭제 합니다. 모든 작업이 큐에 추가 하는 경우 그룹 완료 합니다.

이 스케줄러를 명시적으로 만든 경우 스케줄러에서 참조를 해제 하기 전에 일정을 그룹에 대 한 모든 참조를 해제 해야 하는 참고 합니다.

##  <a name="getnumberofvirtualprocessors"></a> GetNumberOfVirtualProcessors

스케줄러에 대 한 가상 프로세서의 현재 수를 반환합니다.

```
virtual unsigned int GetNumberOfVirtualProcessors() const = 0;
```

### <a name="return-value"></a>반환 값

스케줄러에 대 한 가상 프로세서의 현재 수입니다.

##  <a name="getpolicy"></a> GetPolicy

스케줄러를 사용 하 여 생성 된 정책의 복사본을 반환 합니다.

```
virtual SchedulerPolicy GetPolicy() const = 0;
```

### <a name="return-value"></a>반환 값

스케줄러를 사용 하 여 생성 된 정책의 복사본입니다.

##  <a name="id"></a> Id

스케줄러에 대 한 고유 식별자를 반환합니다.

```
virtual unsigned int Id() const = 0;
```

### <a name="return-value"></a>반환 값

스케줄러에 대 한 고유 식별자입니다.

##  <a name="isavailablelocation"></a> IsAvailableLocation

지정된 된 위치를 스케줄러에서 사용할 수 있는지 확인 합니다.

```
virtual bool IsAvailableLocation(const location& _Placement) const = 0;
```

### <a name="parameters"></a>매개 변수

*_Placement*<br/>
에 대 한 스케줄러를 쿼리 하는 위치에 대 한 참조입니다.

### <a name="return-value"></a>반환 값

위치를 지정 하는 여부를 나타내는 표시를 `_Placement` 인수가 스케줄러에서 사용할 수 있습니다.

### <a name="remarks"></a>설명

반환 값은 지정된 위치를 사용할 수 있는지 여부의 순간 샘플링입니다. 여러 스케줄러가 있으면 동적 자원 관리에서 어느 시점에 스케줄러의 리소스를 추가하거나 제거할 수 있습니다. 이 경우 지정된 위치의 가용성이 변경될 수 있습니다.

##  <a name="reference"></a> 참조

스케줄러 참조 횟수를 증가 시킵니다.

```
virtual unsigned int Reference() = 0 ;
```

### <a name="return-value"></a>반환 값

새로 증가 참조 수입니다.

### <a name="remarks"></a>설명

이 구성에 대 한 스케줄러의 수명을 관리 하려면 일반적으로 사용 됩니다. 스케줄러의 참조 횟수가 0이 되면 스케줄러가 종료되고 스케줄러의 모든 작업이 완료된 후 자체적으로 소멸합니다.

메서드에 throw 합니다는 [improper_scheduler_reference](improper-scheduler-reference-class.md) 참조 횟수를 호출 하기 전에 경우 예외를 `Reference` 메서드가 0 및 scheduler에 의해 소유 하지 않은 컨텍스트에서 호출 됩니다.

##  <a name="registershutdownevent"></a> RegisterShutdownEvent

Windows 이벤트 핸들을 전달 하면은 `_Event` 매개 변수를 스케줄러를 종료 하 고 자체를 제거 하는 경우 신호를 보낼 수 있습니다. 이벤트 신호를 받는 경우 스케줄러에 예약한는 모든 작업이 완료 됩니다. 이 메서드를 통해 여러 종료 이벤트를 등록할 수 있습니다.

```
virtual void RegisterShutdownEvent(HANDLE _Event) = 0;
```

### <a name="parameters"></a>매개 변수

*_Event*<br/>
스케줄러를 종료 하 고 자체를 제거 하는 경우 런타임에서 신호는 Windows 이벤트 개체에 대 한 핸들입니다.

##  <a name="release"></a> 릴리스

스케줄러 참조 횟수를 감소시킵니다.

```
virtual unsigned int Release() = 0;
```

### <a name="return-value"></a>반환 값

새로 감소 된 참조 수입니다.

### <a name="remarks"></a>설명

이 구성에 대 한 스케줄러의 수명을 관리 하려면 일반적으로 사용 됩니다. 스케줄러의 참조 횟수가 0이 되면 스케줄러가 종료되고 스케줄러의 모든 작업이 완료된 후 자체적으로 소멸합니다.

##  <a name="resetdefaultschedulerpolicy"></a> ResetDefaultSchedulerPolicy

기본 스케줄러 정책의 런타임 기본값으로 다시 설정합니다. 기본 스케줄러를 만든 다음에 런타임 기본 정책 설정이 사용 됩니다.

```
static void __cdecl ResetDefaultSchedulerPolicy();
```

### <a name="remarks"></a>설명

기본 스케줄러를 프로세스 내에 존재 하는 동안이 메서드를 호출할 수 있습니다. 기존 기본 스케줄러의 정책을 아무런 영향이 없습니다. 그러나 기본 스케줄러를 종료 하는 경우 나중에 새 기본값 된 새 스케줄러 런타임 기본 정책 설정을 사용 합니다.

##  <a name="ctor"></a> Scheduler

개체는 `Scheduler` 클래스 팩터리 메서드를 사용 하 여 만든 수 또는 암시적으로 합니다.

```
Scheduler();
```

### <a name="remarks"></a>설명

프로세스의 기본 스케줄러는 여러 호출 컨텍스트에 연결 스케줄러를 필요로 하는 런타임 함수를 사용 하는 경우 암시적으로 생성 됩니다. 내에서 메서드는 `CurrentScheduler` PPL 및 에이전트 계층의 기능과 클래스는 일반적으로 암시적 첨부 파일을 수행 합니다.

스케줄러를 통해 명시적으로 만들 수도 있습니다는 `CurrentScheduler::Create` 메서드 또는 `Scheduler::Create` 메서드.

##  <a name="dtor"></a> ~Scheduler

개체는 `Scheduler` 클래스는 모든 외부 참조가 존재를 중단 하는 경우에 명시적으로 소멸 됩니다.

```
virtual ~Scheduler();
```

##  <a name="scheduletask"></a> ScheduleTask

스케줄러 내에서 간단한 작업을 예약합니다. 간단한 작업은 런타임에 의해 결정되는 일정 그룹에 배치됩니다. `_Placement` 매개 변수를 사용하는 버전은 작업이 지정된 위치에서 실행되도록 합니다.

```
virtual void ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data) = 0;

virtual void ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data,
    location& _Placement) = 0;
```

### <a name="parameters"></a>매개 변수

*_Proc*<br/>
간단한 작업의 본문을 수행 하기 위해 실행할 함수에 대 한 포인터입니다.

*_Data*<br/>
작업의 본문에 매개 변수로 전달 되는 데이터에 대 한 void 포인터입니다.

*_Placement*<br/>
간단한 작업이 실행될 수 있는 위치에 대한 참조입니다.

##  <a name="setdefaultschedulerpolicy"></a> SetDefaultSchedulerPolicy

사용자 정의 정책을 기본 스케줄러를 만드는 데 사용할 수 있습니다. 프로세스 내에서 기본 스케줄러가 없는 경우에이 메서드를 호출할 수 있습니다. 다음 유효한 호출 일까 지 적용 됩니다는 기본 정책을 설정한 후 합니다 `SetDefaultSchedulerPolicy` 또는 [ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy) 메서드.

```
static void __cdecl SetDefaultSchedulerPolicy(const SchedulerPolicy& _Policy);
```

### <a name="parameters"></a>매개 변수

*_Policy*<br/>
정책 기본 스케줄러 정책으로 설정입니다.

### <a name="remarks"></a>설명

경우는 `SetDefaultSchedulerPolicy` 프로세스 내에서 기본 스케줄러를 이미 있는 경우 메서드가 호출 되 면 런타임에서 throw를 [default_scheduler_exists](default-scheduler-exists-class.md) 예외입니다.

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)<br/>
[Scheduler 클래스](scheduler-class.md)<br/>
[PolicyElementKey](concurrency-namespace-enums.md)<br/>
[작업 스케줄러](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)
