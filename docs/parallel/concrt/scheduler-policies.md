---
title: Scheduler 정책
ms.date: 11/04/2016
helpviewer_keywords:
- scheduler policies
ms.assetid: 58fb68bd-4a57-40a8-807b-6edb6f083cd9
ms.openlocfilehash: e2acfc199e7ad9edf3965dc8ccb4103eb615a66b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408006"
---
# <a name="scheduler-policies"></a>Scheduler 정책

이 문서에서는 동시성 런타임에서 스케줄러 정책의 역할을 설명 합니다. A *스케줄러 정책* 스케줄러가 작업을 관리할 때 사용 하는 전략을 제어 합니다. 예를 들어, 일부 작업은 `THREAD_PRIORITY_NORMAL`에서 실행해야 하고 다른 작업은 `THREAD_PRIORITY_HIGHEST`에서 실행해야 하는 응용 프로그램을 고려해 보겠습니다.  두 가지 스케줄러 인스턴스를 만들 수 있으며, 하나는 `ContextPriority` 정책을 `THREAD_PRIORITY_NORMAL`로 지정하고, 다른 하나는 동일한 정책을 `THREAD_PRIORITY_HIGHEST`로 지정합니다.

스케줄러 정책을 사용하면 사용 가능한 처리 리소스를 나누고 고정된 리소스 집합을 각 스케줄러에 할당할 수 있습니다. 예를 들어 4 개의 프로세서 개로 확장 하는 병렬 알고리즘을는 것이 좋습니다. 4 개 이상의 프로세서를 동시에 사용할 해당 작업을 제한 하는 스케줄러 정책을 만들 수 있습니다.

> [!TIP]
>  동시성 런타임에서는 기본 스케줄러를 제공합니다. 따라서 응용 프로그램에서 만들 필요가 없습니다. 작업 Scheduler를 사용 하면 응용 프로그램의 성능을 미세 조정할 수 있습니다, 있기 때문에 시작 하는 것이 좋습니다 합니다 [PPL 병렬 패턴 라이브러리 ()](../../parallel/concrt/parallel-patterns-library-ppl.md) 또는 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md) 있다면 동시성 런타임으로 새입니다.

사용 하는 경우는 [concurrency::CurrentScheduler::Create](reference/currentscheduler-class.md#create)하십시오 [concurrency::Scheduler::Create](reference/scheduler-class.md#create), 또는 [concurrency::Scheduler::SetDefaultSchedulerPolicy](reference/scheduler-class.md#setdefaultschedulerpolicy) 제공한 스케줄러 인스턴스를 만드는 메서드를 [concurrency:: schedulerpolicy](../../parallel/concrt/reference/schedulerpolicy-class.md) 스케줄러의 동작을 지정 하는 키-값 쌍의 컬렉션을 포함 하는 개체입니다. `SchedulerPolicy` 생성자는 가변 개수의 인수를 사용 합니다. 첫 번째 인수를 지정 하는 정책 요소입니다. 나머지 인수는 각 정책 요소에 대 한 키-값 쌍입니다. 다음 예제에서는 `SchedulerPolicy` 세 가지 정책 요소를 지정 하는 개체입니다. 런타임에서는 지정되지 않은 정책 키에 대해 기본값을 사용합니다.

[!code-cpp[concrt-scheduler-policy#2](../../parallel/concrt/codesnippet/cpp/scheduler-policies_1.cpp)]

합니다 [concurrency:: policyelementkey](reference/concurrency-namespace-enums.md#policyelementkey) 열거형은 작업 스케줄러와 연결 된 정책 키를 정의 합니다. 다음 표에서 정책 키 및 각각에 대해 런타임을 사용 하는 기본값을 설명 합니다.

|정책 키|설명|기본값|
|----------------|-----------------|-------------------|
|`SchedulerKind`|A [concurrency:: schedulertype](reference/concurrency-namespace-enums.md#schedulertype) 작업 일정을 사용 하는 스레드 형식을 지정 하는 값입니다.|`ThreadScheduler`(일반 스레드 사용) 이 키에 유효한 유일한 값입니다.|
|`MaxConcurrency`|`unsigned int` 스케줄러를 사용 하는 동시성 리소스의 최대 수를 지정 하는 값입니다.|[concurrency::MaxExecutionResources](reference/concurrency-namespace-constants1.md#maxexecutionresources)|
|`MinConcurrency`|`unsigned int` 스케줄러를 사용 하는 동시성 리소스의 최소 수를 지정 하는 값입니다.|`1`|
|`TargetOversubscriptionFactor`|`unsigned int` 각 처리 리소스를 할당할 스레드의 수를 지정 하는 값입니다.|`1`|
|`LocalContextCacheSize`|`unsigned int` 각각의 가상 프로세서의 로컬 큐에 캐시할 수 있는 컨텍스트의 최대 수를 지정 하는 값입니다.|`8`|
|`ContextStackSize`|`unsigned int` 스택의 크기 (킬로바이트) 각 컨텍스트에 대 한 예약을 지정 하는 값입니다.|`0` (기본 스택 크기를 사용)|
|`ContextPriority`|`int` 컨텍스트마다의 스레드 우선 순위를 지정 하는 값입니다. 에 전달할 수 있는 모든 값일 수 있습니다 [SetThreadPriority](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) 또는 `INHERIT_THREAD_PRIORITY`합니다.|`THREAD_PRIORITY_NORMAL`|

|`SchedulingProtocol`| A [concurrency:: schedulingprotocoltype](reference/concurrency-namespace-enums.md#schedulingprotocoltype) 예약 알고리즘을 사용 하 여 지정 하는 값입니다. | `EnhanceScheduleGroupLocality`| | `DynamicProgressFeedback`| A [concurrency:: dynamicprogressfeedbacktype](reference/concurrency-namespace-enums.md#dynamicprogressfeedbacktype) 통계에 기반한 진행 정보에 따라 리소스를 다시 여부를 나타내는 값입니다.<br /><br /> **참고** 이 정책을 설정 하지 않으면 `ProgressFeedbackDisabled` 런타임에서 사용 하기 위해 예약 되어 있으므로. |`ProgressFeedbackEnabled`|

각 스케줄러 작업을 예약할 때 고유한 정책을 사용 합니다. 한 스케줄러와 연결된 정책은 다른 스케줄러의 동작에 영향을 주지 않습니다. 만든 후 스케줄러 정책의 변경할 수 없습니다는 또한는 `Scheduler` 개체입니다.

> [!IMPORTANT]
>  스케줄러 정책에 대 한를 사용 하 여 런타임에서 만든 스레드에 대 한 특성을 제어 하 합니다. 정의되지 않은 동작이 발생할 수 있기 때문에 런타임에서 생성된 스레드의 스레드 선호도 또는 우선 순위를 변경하지 마십시오.

명시적으로 작성 되지 않습니다 하는 경우 런타임은 기본 스케줄러를를 만듭니다. 응용 프로그램에서 기본 스케줄러를 사용 하려고 하지만 호출을 사용 하 되 해당 스케줄러에 대 한 정책을 지정 하려는 경우는 [concurrency::Scheduler::SetDefaultSchedulerPolicy](reference/scheduler-class.md#setdefaultschedulerpolicy) 병렬 작업을 예약 하기 전에 메서드. 호출 하지 않으면 경우는 `Scheduler::SetDefaultSchedulerPolicy` 메서드, 기본 정책 값 테이블에서 사용 하 여 런타임입니다.

사용 된 [concurrency::CurrentScheduler::GetPolicy](reference/currentscheduler-class.md#getpolicy) 하며 [concurrency::Scheduler::GetPolicy](reference/scheduler-class.md#getpolicy) 스케줄러 정책의 복사본을 검색 하는 방법. 이러한 메서드에서 수신 하는 정책 값은 스케줄러를 만들 때 지정 하는 정책 값에서 다를 수 있습니다.

## <a name="example"></a>예제

특정 스케줄러 정책을 사용 하 여 스케줄러의 동작을 제어 하는 예제를 검사 하려면 참조 [방법: 특정 스케줄러 정책 지정](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md) 고 [방법: 특정 스케줄러 정책을 사용 하는 에이전트 만들기](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)합니다.

## <a name="see-also"></a>참고자료

[작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[방법: 특정 스케줄러 정책 지정](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)<br/>
[방법: 특정 스케줄러 정책을 사용하는 에이전트 만들기](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)
