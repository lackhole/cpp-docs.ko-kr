---
title: 컨텍스트
ms.date: 11/04/2016
helpviewer_keywords:
- contexts [Concurrency Runtime]
ms.assetid: 10c1d861-8fbb-4ba0-b2ec-61876b11176e
ms.openlocfilehash: d511f8fa751d61c3c490a184dae660096dd9f76f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62148343"
---
# <a name="contexts"></a>컨텍스트

이 문서 컨텍스트는 동시성 런타임에서 역할을 설명 합니다. 스케줄러에 연결 된 스레드 라고는 *실행 컨텍스트*, 또는 그냥 *상황에 맞는*합니다. 합니다 [concurrency:: wait](reference/concurrency-namespace-functions.md#wait) 함수와 동시성::[상황에 맞는 클래스](../../parallel/concrt/reference/context-class.md) 컨텍스트의 동작을 제어할 수 있도록 합니다. 사용 된 `wait` 함수를 지정된 된 시간에 대 한 현재 컨텍스트를 일시 중단 합니다. 사용 하 여는 `Context` 클래스 또는 현재 컨텍스트에서 초과 구독 하려는 경우 컨텍스트를 차단, 차단 해제 및 양보 때 보다 자세히 제어 해야 합니다.

> [!TIP]
>  동시성 런타임은 기본 스케줄러를 제공하므로 응용 프로그램에서 스케줄러를 만들 필요가 없습니다. 작업 Scheduler를 사용 하면 응용 프로그램의 성능을 미세 조정할 수 있습니다, 있기 때문에 시작 하는 것이 좋습니다 합니다 [PPL 병렬 패턴 라이브러리 ()](../../parallel/concrt/parallel-patterns-library-ppl.md) 또는 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md) 있다면 동시성 런타임으로 새입니다.

## <a name="the-wait-function"></a>Wait 함수

합니다 [concurrency:: wait](reference/concurrency-namespace-functions.md#wait) 함수는 지정 된 기간 (밀리초)에 대 한 현재 컨텍스트의 실행을 협조적으로 양보 합니다. 런타임에서 다른 작업을 수행 하는 yield 시간을 사용 합니다. 지정 된 시간이 경과한 후 런타임에서 실행할 컨텍스트를 다시 예약 합니다. 따라서 합니다 `wait` 함수에 제공 된 값 보다 오래 현재 컨텍스트를 일시 중지할 수 있습니다는 `milliseconds` 매개 변수입니다.

0 (영)에 대해 전달 된 `milliseconds` 매개 변수를 현재 다른 모든 컨텍스트 작업을 수행 하는 기회가 제공 되는 때까지 현재 컨텍스트를 일시 중단 런타임에서. 이렇게 하면 다른 모든 활성 작업 하는 작업을 생성 합니다.

### <a name="example"></a>예제

사용 하는 예는 `wait` 함수를 현재 컨텍스트를 생성 하 고 다른 컨텍스트 실행, 참조를 허용 하므로 [방법: 실행 순서를 영향을 주는 일정 그룹 사용](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)합니다.

## <a name="the-context-class"></a>Context 클래스

Concurrency::[컨텍스트 클래스](../../parallel/concrt/reference/context-class.md) 실행 컨텍스트에 대 한 프로그래밍 추상화를 제공 하며 두 가지 중요 한 기능을 제공 합니다: 협조적으로 차단, 차단 해제 및 현재 컨텍스트를 생성 하는 기능 및 기능을 현재 컨텍스트에서 초과 구독 합니다.

### <a name="cooperative-blocking"></a>협조적 차단

`Context` 클래스를 사용 하면 차단 하거나 현재 실행 컨텍스트를 생성 합니다. 차단 또는 양보는 현재 컨텍스트는 리소스를 사용할 수 없기 때문에 계속할 수 없는 경우에 유용 합니다.

합니다 [concurrency::Context::Block](reference/context-class.md#block) 메서드는 현재 컨텍스트를 차단 합니다. 런타임에서 다른 작업을 수행할 수 있도록 차단 된 컨텍스트를 해당 처리 리소스를 생성 합니다. 합니다 [concurrency::Context::Unblock](reference/context-class.md#unblock) 메서드는 차단 된 컨텍스트를 차단 해제 합니다. 합니다 `Context::Unblock` 메서드를 호출 하는 것 보다 다른 컨텍스트에서 호출 해야 `Context::Block`합니다. 런타임에서 throw [concurrency:: context_self_unblock](../../parallel/concrt/reference/context-self-unblock-class.md) 컨텍스트 자체를 차단 해제 하려고 합니다.

협조적으로 차단 하 고 컨텍스트를 차단 해제를 호출 하 고 일반적 [concurrency::Context::CurrentContext](reference/context-class.md#currentcontext) 에 대 한 포인터를 검색 하는 `Context` 고 결과 저장 하 고 현재 스레드와 연결 된 개체입니다. 그런 다음 호출을 `Context::Block` 현재 컨텍스트를 차단 하는 방법입니다. 나중에 호출 `Context::Unblock` 차단 된 컨텍스트를 차단을 해제 하려면 별도 컨텍스트에서 합니다.

각 쌍에 대 한 호출을 일치 시켜야 `Context::Block` 고 `Context::Unblock`입니다. 런타임에서 throw [concurrency:: context_unblock_unbalanced](../../parallel/concrt/reference/context-unblock-unbalanced-class.md) 때 합니다 `Context::Block` 또는 `Context::Unblock` 메서드는 일치 하는 다른 메서드 호출 없이 연속적으로 호출 됩니다. 그러나 호출할 필요가 없습니다 `Context::Block` 를 호출 하기 전에 `Context::Unblock`입니다. 예를 들어 하나의 컨텍스트 호출 `Context::Unblock` 다른 컨텍스트 호출 하기 전에 `Context::Block` 동일한 컨텍스트, 해당 상황에 맞는 계속 차단 해제 합니다.

합니다 [concurrency::Context::Yield](reference/context-class.md#yield) 런타임에서 다른 작업을 수행 하 고 다음 실행할 컨텍스트를 다시 예약 수 있도록 메서드 실행을 양보 합니다. 호출 하는 경우는 `Context::Block` 메서드, 런타임 컨텍스트 다시 예약 하지 않습니다.

#### <a name="example"></a>예제

사용 하는 예는 `Context::Block`, `Context::Unblock`, 및 `Context::Yield` 공동 작업 세마포 클래스를 구현 하는 방법을 참조 [하는 방법: 상황에 맞는 클래스를 사용 하 여 공동 작업 세마포 구현](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)합니다.

##### <a name="oversubscription"></a>초과 구독

기본 스케줄러는 사용할 수 있는 하드웨어 스레드의 같은 수의 스레드를 만듭니다. 사용할 수 있습니다 *초과 구독* 특정된 하드웨어 스레드에 대 한 추가 스레드를 만들 수 있습니다.

계산 집약적 작업에 대 한 초과 구독 일반적으로 확장 되지 않습니다 추가 오버 헤드가 될 수 있으므로. 그러나 작업의 대기 시간이 있는 경우 예를 들어, 디스크 또는 네트워크 연결에서 데이터를 읽는 초과 구독 향상 시킬 수 일부 응용 프로그램의 전반적인 효율성.

> [!NOTE]
>  동시성 런타임을 통해 생성된 스레드에서만 초과 구독을 사용하도록 설정하십시오. 초과 구독 (main 메서드가 포함) 런타임에 의해 생성 되지 않은 스레드에서 호출 될 때에 영향이 없습니다.

현재 컨텍스트에서 초과 구독을 사용 하도록 설정 하려면 호출을 [concurrency::Context::Oversubscribe](reference/context-class.md#oversubscribe) 메서드를 `_BeginOversubscription` 매개 변수 설정 **true**합니다. 동시성 런타임에 의해 생성 된 스레드의 초과 구독을 사용 하도록 설정 하면 하나의 추가 스레드를 만드는 데 런타임입니다. 초과 구독 완료 해야 하는 모든 작업을 표시 한 후 호출 `Context::Oversubscribe` 사용 하 여 합니다 `_BeginOversubscription` 매개 변수 설정 **false**합니다.

여러 번에서 현재 컨텍스트에서 초과 구독을 설정할 수 있습니다. 하지만를 사용할 수 있는 횟수 만큼 해제 해야 합니다. 초과 구독 중첩 될 수도 있습니다. 즉, 초과 구독을 사용 하는 다른 작업에 의해 만들어지는 작업 컨텍스트 초과 구독할 수도 있습니다. 그러나 중첩된 된 작업 및 해당 부모는 동일한 컨텍스트를 가장 바깥쪽 호출만에 속하는 경우 `Context::Oversubscribe` 추가 스레드가 만들어지도록 합니다.

> [!NOTE]
>  런타임에서 throw [concurrency:: invalid_oversubscribe_operation](../../parallel/concrt/reference/invalid-oversubscribe-operation-class.md) 초과 사용 하기 전에 사용 하지 않도록 설정 됩니다.

###### <a name="example"></a>예제

초과 구독을 사용 하 여 네트워크 연결에서 데이터 읽기를 통해 발생 하는 대기 시간을 오프셋 하는 예제를 참조 하세요. [방법: 초과 구독을 사용 하 여 대기 시간을 오프셋](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)합니다.

## <a name="see-also"></a>참고자료

[작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[방법: 실행 순서에 영향을 주는 일정 그룹 사용](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)<br/>
[방법: 컨텍스트 클래스를 사용하여 공동 작업 세마포 구현](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)<br/>
[방법: 초과 구독을 사용하여 대기 오프셋](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)
