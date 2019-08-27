---
title: 스케줄러 인스턴스
ms.date: 11/04/2016
helpviewer_keywords:
- scheduler instances
ms.assetid: 4819365f-ef99-49cc-963e-50a2a35a8d6b
ms.openlocfilehash: 19bd871857dcef6aaef153798388c0272239fa1f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180169"
---
# <a name="scheduler-instances"></a>스케줄러 인스턴스

이 문서에서는 동시성 런타임을 사용 하는 방법에 대 한 스케줄러 인스턴스의 역할을 설명 합니다 [concurrency:: scheduler](../../parallel/concrt/reference/scheduler-class.md) 하 고 [concurrency:: currentscheduler](../../parallel/concrt/reference/currentscheduler-class.md) 클래스를 만들고 관리 스케줄러 인스턴스입니다. 스케줄러 인스턴스는 특정 유형의 워크 로드를 사용 하 여 명시적 일정 예약 정책을 연결 하려는 경우에 유용 합니다. 예를 들어 높은 스레드 우선 순위로 일부 작업을 실행하기 위한 스케줄러 인스턴스를 하나 만들고, 기본 스케줄러를 사용하여 보통 스레드 우선 순위로 다른 작업을 실행할 수 있습니다.

> [!TIP]
>  동시성 런타임은 기본 스케줄러를 제공하므로 애플리케이션에서 스케줄러를 만들 필요가 없습니다. 작업 Scheduler를 사용 하면 응용 프로그램의 성능을 미세 조정할 수 있습니다, 있기 때문에 시작 하는 것이 좋습니다 합니다 [PPL 병렬 패턴 라이브러리 ()](../../parallel/concrt/parallel-patterns-library-ppl.md) 또는 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md) 있다면 동시성 런타임으로 새입니다.

##  <a name="top"></a> 섹션

- [Scheduler 및 CurrentScheduler 클래스](#classes)

- [스케줄러 인스턴스 만들기](#creating)

- [스케줄러 인스턴스 수명 관리](#managing)

- [메서드 및 기능](#features)

- [예제](#example)

##  <a name="classes"></a> Scheduler 및 CurrentScheduler 클래스

작업 스케줄러를 사용 하면 하나 이상의 사용 하도록 응용 프로그램 *스케줄러 인스턴스* 에 작업을 예약 합니다. 합니다 [concurrency:: scheduler](../../parallel/concrt/reference/scheduler-class.md) 클래스 스케줄러 인스턴스를 나타내고 작업 예약과 관련 된 기능을 캡슐화 합니다.

스케줄러에 연결 된 스레드 라고는 *실행 컨텍스트*, 또는 그냥 *상황에 맞는*합니다. 언제 든 지 하나의 스케줄러가 현재 컨텍스트에 따라 활성화할 수 있습니다. 활성 스케줄러가 라고도 합니다 *현재 스케줄러*합니다. 동시성 런타임을 사용 하 여 [concurrency:: currentscheduler](../../parallel/concrt/reference/currentscheduler-class.md) 현재 스케줄러에 대 한 액세스를 제공 하는 클래스입니다. 하나의 컨텍스트에 대 한 현재 스케줄러를 다른 컨텍스트에 대 한 현재 스케줄러에서 다를 수 있습니다. 런타임은 프로세스 수준 표현을 현재 스케줄러를 제공 하지 않습니다.

일반적으로 `CurrentScheduler` 클래스 현재 스케줄러에 액세스 하는 데 사용 됩니다. `Scheduler` 클래스는 현재 없는 스케줄러를 관리 해야 하는 경우에 유용 합니다.

다음 섹션에서는 만들고 스케줄러 인스턴스 관리 방법에 설명 합니다. 이러한 작업을 보여 주는 전체 예제를 참조 하세요. [방법: 스케줄러 인스턴스 관리](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)합니다.

[[맨 위로 이동](#top)]

##  <a name="creating"></a> 스케줄러 인스턴스 만들기

이러한 세 가지 방법으로 만들려면를 `Scheduler` 개체:

- 스케줄러가 없는 경우 런타임은 런타임 기능을 예를 들어 병렬 알고리즘을 사용 하 여 작업을 수행 하면 기본 스케줄러를 만듭니다. 기본 스케줄러를 현재 스케줄러는 병렬 작업을 시작 하는 상황에 맞는 됩니다.

- 합니다 [concurrency::CurrentScheduler::Create](reference/currentscheduler-class.md#create) 메서드를 만듭니다를 `Scheduler` 는 특정 정책을 사용 하 고 현재 컨텍스트를 사용 하 여 해당 스케줄러를 연결 하는 개체입니다.

- 합니다 [concurrency::Scheduler::Create](reference/scheduler-class.md#create) 메서드를 만듭니다를 `Scheduler` 개체는 특정 정책을 사용 하지만 현재 컨텍스트와 연결 하지는 않습니다.

런타임은 기본 스케줄러를 만들 수 있도록 모든 동시 작업을 같은 스케줄러를 공유할 수 있습니다. 제공 하는 기능을 일반적으로 [병렬 패턴 라이브러리](../../parallel/concrt/parallel-patterns-library-ppl.md) (PPL) 또는 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md) 병렬 작업을 수행 하는 데 사용 됩니다. 스케줄러 정책 또는 수명을 제어 하려면 직접 작업할 필요가 없습니다. PPL 또는 에이전트 라이브러리를 사용 하면 존재 하지 않는 경우 각 컨텍스트에 대 한 현재 스케줄러를 사용 하면 런타임은 기본 스케줄러를 만듭니다. 경우 스케줄러를 만들고을 런타임에 해당 스케줄러를 사용 하 여 작업을 예약할 수를 현재 스케줄러로 설정 합니다. 특정 일정 정책을 해야 하는 경우에 추가 스케줄러 인스턴스를 만듭니다. 스케줄러와 연결 된 정책에 대 한 자세한 내용은 참조 하세요. [스케줄러 정책](../../parallel/concrt/scheduler-policies.md)합니다.

[[맨 위로 이동](#top)]

##  <a name="managing"></a> 스케줄러 인스턴스 수명 관리

런타임에 참조 카운팅 메커니즘의 수명을 제어를 사용 하 여 `Scheduler` 개체입니다.

사용 하는 경우는 `CurrentScheduler::Create` 메서드 또는 `Scheduler::Create` 메서드를 한 `Scheduler` 개체를 런타임에 해당 스케줄러의 초기 참조 횟수를 1로 설정 합니다. 호출 하면 런타임에서 참조 횟수를 증가 합니다 [concurrency::Scheduler::Attach](reference/scheduler-class.md#attach) 메서드. 합니다 `Scheduler::Attach` 메서드 담당자는 `Scheduler` 개체를 현재 컨텍스트와 함께 합니다. 이렇게 하면 현재 스케줄러입니다. 호출 하는 경우는 `CurrentScheduler::Create` 메서드는 모두 런타임에 생성을 `Scheduler` 개체 컨텍스트에 연결 (및 참조 횟수를 1로 설정). 사용할 수도 있습니다는 [concurrency::Scheduler::Reference](reference/scheduler-class.md#reference) 의 참조 횟수를 증가 시킬 메서드를 `Scheduler` 개체입니다.

참조 횟수를 호출 하는 경우 런타임 감소 합니다 [concurrency::CurrentScheduler::Detach](reference/currentscheduler-class.md#detach) 현재 스케줄러를 분리 하는 방법 호출 또는 합니다 [concurrency::Scheduler::Release](reference/scheduler-class.md#release) 메서드. 참조 횟수가 0에 도달 하면 런타임에서 소멸을 `Scheduler` 개체 결국 작업 완료를 예약 합니다. 실행 중인 작업을 현재 스케줄러의 참조 횟수를 증가 시킬 수 있습니다. 따라서 참조 횟수가 0 참조 횟수를 증가 하는 작업을 하는 경우 런타임은 제거 하지 않습니다는 `Scheduler` 참조 횟수를 다시 0이 되 고 모든 작업이 끝날 때까지 개체입니다.

런타임에서 유지의 내부 스택에서 `Scheduler` 각 컨텍스트에 대 한 개체입니다. 호출 하는 경우는 `Scheduler::Attach` 또는 `CurrentScheduler::Create` 메서드를 런타임에 푸시 `Scheduler` 현재 컨텍스트에 대해 스택에 개체입니다. 이렇게 하면 현재 스케줄러입니다. 호출 하는 경우 `CurrentScheduler::Detach`, 런타임은 현재 컨텍스트에 대 한 스택 으로부터 현재 스케줄러를 팝 하 고 이전과 현재 스케줄러로 설정 합니다.

런타임에서는 스케줄러 인스턴스의 수명을 관리 하는 여러 방법을 제공 합니다. 다음 표에서 해제 하거나 만들거나 스케줄러를 현재 컨텍스트에 연결 하는 각 메서드에 대 한 현재 컨텍스트에서 스케줄러를 분리 하는 적절 한 메서드를 보여 줍니다.

|만들거나 attach 메서드|릴리스 또는 detach 메서드|
|-----------------------------|------------------------------|
|`CurrentScheduler::Create`|`CurrentScheduler::Detach`|
|`Scheduler::Create`|`Scheduler::Release`|
|`Scheduler::Attach`|`CurrentScheduler::Detach`|
|`Scheduler::Reference`|`Scheduler::Release`|

적절 하지 않은 호출 릴리스 또는 런타임에서 메서드 생성 지정 되지 않은 동작을 분리 합니다.

예를 들어, PPL를 기본 스케줄러를 만들 런타임 시키는 기능을 사용 하는 경우 릴리스 하지 않거나이 스케줄러를 분리 합니다. 런타임에 생성 되는 모든 스케줄러 수명을 관리 합니다.

런타임에서 소멸 시 키 지 않습니다 때문에 `Scheduler` 모든 작업을 완료 하기 전에 개체를 사용할 수는 [concurrency::Scheduler::RegisterShutdownEvent](reference/scheduler-class.md#registershutdownevent) 메서드 또는 [concurrency:: currentscheduler:: RegisterShutdownEvent](reference/currentscheduler-class.md#registershutdownevent) 알림을 수신 하는 방법 면을 `Scheduler` 개체는 소멸 됩니다. 에 예약 된 모든 작업에 대 한 대기 해야 하는 경우에 유용는 `Scheduler` 개체가 완료 합니다.

[[맨 위로 이동](#top)]

##  <a name="features"></a> 메서드 및 기능

이 섹션에서는 요약의 중요 한 메서드를 `CurrentScheduler` 고 `Scheduler` 클래스입니다.

생각할는 `CurrentScheduler` 현재 컨텍스트에서 사용에 대 한 스케줄러를 만들기 위한 도우미 클래스입니다. `Scheduler` 클래스를 사용 하면 다른 컨텍스트에 속하는 스케줄러를 제어할 수 있습니다.

다음 표에서 여 정의 된 중요 한 메서드는 `CurrentScheduler` 클래스입니다.

|메서드|설명|
|------------|-----------------|
|[만들기](reference/currentscheduler-class.md#create)|만듭니다는 `Scheduler` 지정된 정책을 사용 하 여 현재 컨텍스트와 연결 하는 개체입니다.|
|[Get](reference/currentscheduler-class.md#get)|에 대 한 포인터를 검색 합니다 `Scheduler` 현재 컨텍스트와 연결 된 개체입니다. 이 메서드는 참조 횟수를 늘리지 않습니다는 `Scheduler` 개체입니다.|
|[Detach](reference/currentscheduler-class.md#detach)|현재 컨텍스트에서 현재 스케줄러를 분리 하 고 현재 스케줄러로 이전 한을 설정 합니다.|
|[RegisterShutdownEvent](reference/currentscheduler-class.md#registershutdownevent)|현재 스케줄러를 소멸 될 때 런타임에서 설정 하는 이벤트를 등록 합니다.|
|[CreateScheduleGroup](reference/currentscheduler-class.md#createschedulegroup)|만듭니다는 [concurrency:: schedulegroup](../../parallel/concrt/reference/schedulegroup-class.md) 현재 스케줄러에는 개체입니다.|
|[ScheduleTask](reference/currentscheduler-class.md#scheduletask)|현재 스케줄러의 일정 큐에 간단한 작업을 추가합니다.|
|[GetPolicy](reference/currentscheduler-class.md#getpolicy)|연결 된 현재 스케줄러 정책의 복사본을 검색 합니다.|

다음 표에서 여 정의 된 중요 한 메서드는 `Scheduler` 클래스입니다.

|메서드|설명|
|------------|-----------------|
|[만들기](reference/scheduler-class.md#create)|만듭니다는 `Scheduler` 지정된 정책을 사용 하는 개체입니다.|
|[Attach](reference/scheduler-class.md#attach)|연결 된 `Scheduler` 개체를 현재 컨텍스트와 함께 합니다.|
|[참조](reference/scheduler-class.md#reference)|참조 카운터가 증가 하는 `Scheduler` 개체입니다.|
|[릴리스](reference/scheduler-class.md#release)|감소의 참조 카운터를 `Scheduler` 개체입니다.|
|[RegisterShutdownEvent](reference/scheduler-class.md#registershutdownevent)|런타임에 설정 될 때 이벤트를 등록 합니다 `Scheduler` 개체는 소멸 됩니다.|
|[CreateScheduleGroup](reference/scheduler-class.md#createschedulegroup)|만듭니다는 [concurrency:: schedulegroup](../../parallel/concrt/reference/schedulegroup-class.md) 개체는 `Scheduler` 개체입니다.|
|[ScheduleTask](reference/scheduler-class.md#scheduletask)|간단한 작업을 예약 합니다 `Scheduler` 개체입니다.|
|[GetPolicy](reference/scheduler-class.md#getpolicy)|연결 된 정책의 복사본을 검색 합니다 `Scheduler` 개체입니다.|
|[SetDefaultSchedulerPolicy](reference/scheduler-class.md#setdefaultschedulerpolicy)|기본 스케줄러를 만들 때 사용에 런타임에 대 한 정책을 설정 합니다.|
|[ResetDefaultSchedulerPolicy](reference/scheduler-class.md#resetdefaultschedulerpolicy)|기본 정책을 호출 하기 전에 활성 상태 였던 것 복원 `SetDefaultSchedulerPolicy`합니다. 이 호출 후 기본 스케줄러를 만든 경우 런타임이 기본 정책 설정을 사용 하 여 스케줄러를 만듭니다.|

[[맨 위로 이동](#top)]

##  <a name="example"></a> 예제

만들기 및 스케줄러 인스턴스를 관리 하는 방법의 기본 예제를 참조 하세요. [방법: 스케줄러 인스턴스 관리](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)합니다.

## <a name="see-also"></a>참고자료

[작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[방법: 스케줄러 인스턴스 관리](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)<br/>
[스케줄러 정책](../../parallel/concrt/scheduler-policies.md)<br/>
[일정 그룹](../../parallel/concrt/schedule-groups.md)
