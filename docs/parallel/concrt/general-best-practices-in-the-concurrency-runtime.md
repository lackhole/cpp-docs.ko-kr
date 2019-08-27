---
title: 동시성 런타임의 유용한 일반 정보
ms.date: 11/04/2016
helpviewer_keywords:
- Concurrency Runtime, general best practices
ms.assetid: ce5c784c-051e-44a6-be84-8b3e1139c18b
ms.openlocfilehash: e25011e2466d76c946cc55421ed228c8ea174161
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413920"
---
# <a name="general-best-practices-in-the-concurrency-runtime"></a>동시성 런타임의 유용한 일반 정보

이 문서에서는 동시성 런타임의 여러 영역에 적용 되는 모범 사례를 설명 합니다.

##  <a name="top"></a> 섹션

이 문서는 다음 섹션으로 구성됩니다.

- [가능한 경우 협조적 동기화 구문을 사용 하 여](#synchronization)

- [양보 하지 않는 시간이 오래 걸리는 작업 방지](#yield)

- [대기 시간이 긴 하거나 차단 하는 오프셋된 작업에 초과 사용](#oversubscription)

- [가능한 경우 동시 메모리 관리 함수 사용](#memory)

- [RAII 동시성 개체의 수명을 관리 하는 데](#raii)

- [전역 범위에서 동시성 개체를 만들지 마십시오](#global-scope)

- [공유 데이터 세그먼트에서 동시성 개체를 사용 하지 마세요](#shared-data)

##  <a name="synchronization"></a> 가능한 경우 협조적 동기화 구문을 사용 하 여

동시성 런타임은 외부 동기화 개체를 필요 하지 않은 많은 동시성 으로부터 안전한 구문을 제공 합니다. 예를 들어 합니다 [concurrency:: concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) 클래스를 제공 동시성 으로부터 안전한 추가 및 작업에 액세스 하는 요소입니다. 그러나 리소스에 대 한 단독 액세스 해야 하는 경우 런타임에서 제공 합니다 [concurrency:: critical_section](../../parallel/concrt/reference/critical-section-class.md)를 [concurrency:: reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md), 및 [동시성 :: 이벤트](../../parallel/concrt/reference/event-class.md) 클래스입니다. 이러한 형식은 협조적; 동작 따라서 작업 스케줄러를 다시 할당할 수 있습니다 다른 컨텍스트에 처리 리소스를 첫 번째 작업 데이터에 대 한 대기로 합니다. 가능한 경우 동기화 같은 다른 메커니즘이 Windows API에서 제공 하는 협조적으로 작동 하지는 대신 이러한 동기화 형식이 사용 합니다. 이러한 동기화 형식이 및 코드 예제에 대 한 자세한 내용은 참조 하세요. [동기화 데이터 구조](../../parallel/concrt/synchronization-data-structures.md) 하 고 [동기화 데이터 구조는 Windows API와 비교](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md)합니다.

[[맨 위로 이동](#top)]

##  <a name="yield"></a> 양보 하지 않는 시간이 오래 걸리는 작업 방지

작업 scheduler는 협조적으로 동작 하기 때문에 작업 간의 공정성을 제공 하지 않습니다. 따라서 작업부터 다른 작업을 방지할 수 있습니다. 일부 경우에 적용할 경우에 다른 경우에서이 수로 인해 교착 상태 또는 기아 상태.

다음 예제에서는 할당 된 처리 리소스의 수보다 더 많은 작업을 수행합니다. 작업 스케줄러에 첫 번째 작업을 생성 하지 않습니다 고 따라서 두 번째 작업 시작 되지 않은 첫 번째 작업이 완료 될 때까지 합니다.

[!code-cpp[concrt-cooperative-tasks#1](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_1.cpp)]

이 예제는 다음과 같은 출력을 생성합니다.

1: 250000000 1: 500000000 1: 750000000 1: 1000000000 2: 250000000 2: 500000000 2: 750000000 2: 1000000000

두 작업 간의 공동 작업을 사용 하도록 설정 하는 방법은 여러 가지가 있습니다. 하나의 방법은 때때로 장기 실행 작업의 작업 스케줄러를 양보 하는 것입니다. 다음 예제를 수정 합니다 `task` 함수를 호출 하는 [concurrency::Context::Yield](reference/context-class.md#yield) 다른 작업이 실행 될 수 있도록 작업 스케줄러에 실행을 양보 하는 방법.

[!code-cpp[concrt-cooperative-tasks#2](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_2.cpp)]

이 예제는 다음과 같은 출력을 생성합니다.

```Output
1: 250000000
2: 250000000
1: 500000000
2: 500000000
1: 750000000
2: 750000000
1: 1000000000
2: 1000000000
```

`Context::Yield` 메서드는 현재 스레드, 속해 있는 간단한 작업 또는 다른 운영 체제 스레드 스케줄러에서 다른 활성 스레드를 생성 합니다. 이 메서드는 작업에 양보 하지에서 실행 되도록 예약 된 된 [concurrency:: task_group](reference/task-group-class.md) 또는 [concurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) 개체 있지만 아직 시작 되지 않았습니다.

다른 방법으로 장기 실행 작업 간의 협력을 설정할 수 있습니다. 작은 하위 작업으로 많은 작업을 중단할 수 있습니다. 초과 구독 하는 동안 긴 작업을 수행할 수도 있습니다. 초과 구독을 사용하면 사용 가능한 하드웨어 수보다 많은 스레드를 만들 수 있습니다. 초과 구독 긴 작업을 예를 들어, 디스크 또는 네트워크 연결에서 데이터를 읽기 대기 시간이 포함 된 경우에 특히 유용 합니다. 간단한 작업 및 초과 구독 하는 방법에 대 한 자세한 내용은 참조 하세요. [작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)합니다.

[[맨 위로 이동](#top)]

##  <a name="oversubscription"></a> 대기 시간이 긴 하거나 차단 하는 오프셋된 작업에 초과 사용

동시성 런타임은 같은 동기화 기본을 제공 합니다 [concurrency:: critical_section](../../parallel/concrt/reference/critical-section-class.md)를 협조적으로 차단 하 고 서로 생성 작업을 수 있도록 합니다. 하나 이상의 태스크 협조적으로 차단, 생성 하는 경우 작업 스케줄러를 다시 할당할 수 있습니다 다른 컨텍스트에 처리 리소스를 첫 번째 작업 데이터에 대 한 대기로 합니다.

경우에는 동시성 런타임에서 제공 하는 협조적 차단 메커니즘을 사용할 수 없습니다. 예를 들어, 사용 하는 외부 라이브러리는 다양 한 동기화 메커니즘을 사용할 수 있습니다. 또 다른 예는 포함 될 수 있는 대량의 한 대기 시간, 예를 들어 Windows API를 사용 하는 경우 작업을 수행할 때 `ReadFile` 네트워크 연결에서 데이터를 읽는 함수입니다. 이러한 경우 초과 구독에는 다른 작업이 다른 작업 유휴 상태일 때 실행 되도록 설정할 수 있습니다. 초과 구독을 사용하면 사용 가능한 하드웨어 수보다 많은 스레드를 만들 수 있습니다.

다음 함수를 살펴보세요 `download`, 지정된 된 URL에서 파일을 다운로드 하는 합니다. 이 예제에서는 합니다 [concurrency::Context::Oversubscribe](reference/context-class.md#oversubscribe) 메서드 활성 스레드 수를 늘립니다.

[!code-cpp[concrt-download-oversubscription#4](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_3.cpp)]

때문에 `GetHttpFile` 잠재적으로 잠재 연산을 수행 하는 함수, 초과 구독에는 다른 작업이 현재 작업과 데이터에 대 한 대기로 실행 되도록 설정할 수 있습니다. 이 예제의 전체 버전을 참조 하세요. [방법: 초과 구독을 사용 하 여 대기 시간을 오프셋](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)합니다.

[[맨 위로 이동](#top)]

##  <a name="memory"></a> 가능한 경우 동시 메모리 관리 함수 사용

메모리 관리 함수를 사용 하 여 [concurrency:: alloc](reference/concurrency-namespace-functions.md#alloc) 하 고 [concurrency:: free](reference/concurrency-namespace-functions.md#free)자주 수명이 비교적 짧은 작은 개체를 할당 하는 세분화 된 작업이 있는 경우. 동시성 런타임에서 실행 중인 각 스레드에 대해 별도 메모리 캐시를 보유합니다. 합니다 `Alloc` 및 `Free` 함수 할당 및 잠금이나 메모리 장벽을 사용 하지 않고 이러한 캐시 메모리를 확보 합니다.

이러한 메모리 관리 기능에 대 한 자세한 내용은 참조 하세요. [작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)합니다. 이러한 기능을 사용 하는 예제를 보려면 [방법: 할당을 사용 하 여 메모리 성능 향상을 위해 무료](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)합니다.

[[맨 위로 이동](#top)]

##  <a name="raii"></a> RAII 동시성 개체의 수명을 관리 하는 데

동시성 런타임에서 취소와 같은 기능을 구현 하는 예외 처리를 사용 합니다. 따라서 런타임으로 호출 하거나 런타임에 호출 하는 다른 라이브러리를 호출 하는 경우 예외 로부터 안전한 코드를 작성 합니다.

합니다 *Resource Acquisition Is Initialization* (RAII) 패턴은 안전 하 게 지정된 된 범위에서 동시성 개체의 수명을 관리 하는 하나의 방법입니다. RAII 패턴에서 데이터 구조는 스택에 할당 됩니다. 해당 데이터 구조를 초기화 하거나 만들어집니다 및 소멸 또는 데이터 구조 소멸 될 때 해당 리소스를 해제 하는 경우 리소스를 획득 합니다. RAII 패턴 바깥쪽 범위의 종료 되기 전에 소멸자가 호출 되는 것을 보장 합니다. 함수를 여러 개 포함 된 경우이 패턴이 유용 `return` 문입니다. 또한이 패턴에서는 예외 로부터 안전한 코드를 작성할 수 있습니다. 경우는 `throw` 문을 사용 하면 스택이 해제, 소멸자 RAII 개체에 대 한; 따라서 리소스는 항상 올바르게 삭제 또는 해제 합니다.

예를 들어 RAII 패턴을 사용 하는 여러 클래스를 정의 하는 런타임 [:: scoped_lock](../../parallel/concrt/reference/critical-section-class.md#critical_section__scoped_lock_class) 하 고 [scoped_lock](reference/reader-writer-lock-class.md#scoped_lock_class)합니다. 이러한 도우미 클래스 라고 *범위 잠금*합니다. 이러한 클래스는 작업할 때는 여러 가지 이점을 제공 [concurrency:: critical_section](../../parallel/concrt/reference/critical-section-class.md) 하거나 [concurrency:: reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) 개체입니다. 이러한 클래스의 생성자에 제공 된 액세스를 획득 `critical_section` 또는 `reader_writer_lock` 개체; 개체에 대 한 소멸자 릴리스 액세스 합니다. 소멸 될 때 해당 상호 제외 개체에 대 한 액세스를 자동으로 해제 하는 범위가 지정 된 잠금, 때문에 기본 개체 하지 수동으로 해제 수행 있습니다.

다음 클래스를 `account`, 외부 라이브러리에 의해 정의 됩니다 하 고 수정할 수 없습니다.

[!code-cpp[concrt-account-transactions#1](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_4.h)]

다음 예제에서 여러 트랜잭션을 수행는 `account` 병렬로 개체입니다. 이 예제에서는 사용를 `critical_section` 개체에 대 한 액세스를 동기화 하는 `account` 개체를 `account` 클래스는 동시성이 보장 되지 않습니다. 각 병렬 작업에서 사용 하는 `critical_section::scoped_lock` 보장 하는 개체는 `critical_section` 작업이 성공 하거나 실패 하는 경우 개체가 잠긴 아닙니다. 계정 잔액 음수인 경우는 `withdraw` 예외가 발생 하면 작업이 실패 합니다.

[!code-cpp[concrt-account-transactions#2](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_5.cpp)]

이 예제는 다음 예제 출력을 생성합니다.

```Output
Balance before deposit: 1924
Balance after deposit: 2924
Balance before withdrawal: 2924
Balance after withdrawal: -76
Balance before withdrawal: -76
Error details:
    negative balance: -76
```

동시성 개체의 수명을 관리 하는 RAII 패턴을 사용 하는 추가 예제를 보려면 [연습: 사용자 인터페이스 스레드에서 작업 제거](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md), [방법: 상황에 맞는 클래스를 사용 하 여 공동 작업 세마포 구현](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md), 및 [방법: 초과 구독을 사용 하 여 대기 시간을 오프셋](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)합니다.

[[맨 위로 이동](#top)]

##  <a name="global-scope"></a> 전역 범위에서 동시성 개체를 만들지 마십시오

전역 범위에서 동시성 개체를 만드는 경우 교착 상태나 메모리 액세스 위반 등의 문제가 애플리케이션에서 발생할 수 있습니다.

예를 들어 동시성 런타임 개체를 만드는 경우 런타임은 아직 만들어지지 않은 경우 기본 스케줄러를 만듭니다. 전역 개체 생성 중에 만들어지는 런타임 개체가 적절하게 런타임이 이 기본 스케줄러를 만들게 합니다. 그러나 이 프로세스에는 내부 잠금이 사용되므로 동시성 런타임 인프라를 지원하는 다른 개체의 초기화를 방해할 수 있습니다. 이 내부 잠금은 아직 초기화되지 않은 다른 인프라 개체에 필요할 수 있기 때문에 교착 상태가 애플리케이션에서 발생할 수 있습니다.

다음 예제에서는 전역 폭넓은 [concurrency:: scheduler](../../parallel/concrt/reference/scheduler-class.md) 개체입니다. 이 패턴은 `Scheduler` 클래스뿐 아니라 동시성 런타임에서 제공하는 다른 모든 형식에도 적용됩니다. 애플리케이션에서 예기치 않은 동작이 발생할 수 있기 때문에 이 패턴을 따르지 않는 것이 좋습니다.

[!code-cpp[concrt-global-scheduler#1](../../parallel/concrt/codesnippet/cpp/general-best-practices-in-the-concurrency-runtime_6.cpp)]

만들기 위한 올바른 방법의 예제를 보려면 `Scheduler` 개체를 참조 하세요 [작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)합니다.

[[맨 위로 이동](#top)]

##  <a name="shared-data"></a> 공유 데이터 세그먼트에서 동시성 개체를 사용 하지 마세요

동시성 런타임에서 데이터 섹션에서 만든 예를 들어, 공유 데이터 섹션에서 동시성 개체의 사용을 지원 하지 않습니다 합니다 [data_seg](../../preprocessor/data-seg.md) `#pragma` 지시문입니다. 프로세스 간에 공유 되는 동시성 개체는 일관 되지 않거나 잘못 된 상태에서 런타임을 둘 수 있습니다.

[[맨 위로 이동](#top)]

## <a name="see-also"></a>참고자료

[동시성 런타임 유용한 정보](../../parallel/concrt/concurrency-runtime-best-practices.md)<br/>
[PPL(병렬 패턴 라이브러리)](../../parallel/concrt/parallel-patterns-library-ppl.md)<br/>
[비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[동기화 데이터 구조](../../parallel/concrt/synchronization-data-structures.md)<br/>
[동기화 데이터 구조와 Windows API의 비교](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md)<br/>
[방법: Alloc 및 Free를 사용하여 메모리 성능 개선](../../parallel/concrt/how-to-use-alloc-and-free-to-improve-memory-performance.md)<br/>
[방법: 초과 구독을 사용하여 대기 오프셋](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)<br/>
[방법: 컨텍스트 클래스를 사용하여 공동 작업 세마포 구현](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)<br/>
[연습: 사용자 인터페이스 스레드에서 작업 제거](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md)<br/>
[병렬 패턴 라이브러리의 유용한 정보](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md)<br/>
[비동기 에이전트 라이브러리의 모범 사례](../../parallel/concrt/best-practices-in-the-asynchronous-agents-library.md)
