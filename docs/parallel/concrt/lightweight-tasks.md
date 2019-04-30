---
title: 간단한 작업
ms.date: 11/04/2016
helpviewer_keywords:
- lightweight tasks
ms.assetid: b6dcfc7a-9fa9-4144-96a6-2845ea272017
ms.openlocfilehash: 19918cf73c2b5b03db895c4751b22b1666ce01de
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346346"
---
# <a name="lightweight-tasks"></a>간단한 작업

이 문서는 동시성 런타임에서 간단한 작업의 역할을 설명합니다. A *간단한 작업* 에서 직접 예약 된 작업을 `concurrency::Scheduler` 또는 `concurrency::ScheduleGroup` 개체입니다. 간단한 작업을 Windows API를 제공 하는 함수를 유사 [CreateThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createthread) 함수입니다. 따라서 간단한 작업은 동시성 런타임의 일정 예약 기능을 사용 하도록 기존 코드를 조정 하는 경우 유용 합니다. 동시성 런타임 자체에서 비동기 에이전트를 예약 하 여 비동기 메시지 블록 간에 메시지를 보낼 간단한 작업을 사용 합니다.

> [!TIP]
>  동시성 런타임은 기본 스케줄러를 제공하므로 응용 프로그램에서 스케줄러를 만들 필요가 없습니다. 작업 Scheduler를 사용 하면 응용 프로그램의 성능을 미세 조정할 수 있습니다, 있기 때문에 시작 하는 것이 좋습니다 합니다 [PPL 병렬 패턴 라이브러리 ()](../../parallel/concrt/parallel-patterns-library-ppl.md) 또는 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md) 있다면 동시성 런타임으로 새입니다.

간단한 작업은 비동기 에이전트 및 작업 그룹 보다 오버 헤드가 적습니다. 예를 들어, 런타임은 알리지 않습니다 있습니다 간단한 작업을 완료 하는 경우. 또한 런타임은 catch 하거나 처리 하지 않는 간단한 작업에서 throw 되는 예외입니다. 예외 처리 및 간단한 작업에 대 한 자세한 내용은 참조 하세요. [예외 처리](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)합니다.

대부분의 작업에 대 한 병렬 알고리즘 보다 쉽게 수 있으므로 복잡 한 작업으로 분할 기본적인 작업을 작업 그룹과 같은 보다 강력한 기능을 사용 하는 것이 좋습니다. 작업 그룹에 대 한 자세한 내용은 참조 하세요. [작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)합니다. 병렬 알고리즘에 대 한 자세한 내용은 참조 하세요. [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)합니다.

간단한 작업을 호출 합니다 [concurrency::ScheduleGroup::ScheduleTask](reference/schedulegroup-class.md#scheduletask)를 [concurrency::CurrentScheduler::ScheduleTask](reference/currentscheduler-class.md#scheduletask), 또는 [concurrency::Scheduler::ScheduleTask ](reference/scheduler-class.md#scheduletask) 메서드. 대기를 종료 하거나 같은 동기화 메커니즘을 사용 하 여 부모 스케줄러 간단한 작업이 끝나기를 대기 하는 [concurrency:: event](../../parallel/concrt/reference/event-class.md) 개체입니다.

## <a name="example"></a>예제

간단한 작업을 사용 하도록 기존 코드를 조정 하는 방법을 보여 주는 예제를 참조 하세요. [연습: 간단한 작업을 사용 하도록 기존 코드 조정](../../parallel/concrt/walkthrough-adapting-existing-code-to-use-lightweight-tasks.md)합니다.

## <a name="see-also"></a>참고자료

[작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[연습: 간단한 작업을 사용하기 위해 기존 코드 조정](../../parallel/concrt/walkthrough-adapting-existing-code-to-use-lightweight-tasks.md)
