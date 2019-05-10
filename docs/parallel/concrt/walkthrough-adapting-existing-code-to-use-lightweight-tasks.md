---
title: '연습: 간단한 작업을 사용 하도록 기존 코드 조정'
ms.date: 04/25/2019
helpviewer_keywords:
- using lightweight tasks [Concurrency Runtime]
- lightweight tasks, using [Concurrency Runtime]
ms.assetid: 1edfe818-d274-46de-bdd3-e92967c9bbe0
ms.openlocfilehash: 658cc82442bf362b7f50e787169ce75373275d9c
ms.sourcegitcommit: 283cb64fd7958a6b7fbf0cd8534de99ac8d408eb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64857025"
---
# <a name="walkthrough-adapting-existing-code-to-use-lightweight-tasks"></a>연습: 간단한 작업을 사용 하도록 기존 코드 조정

이 항목에서는 Windows API를 사용 하 여 만들고 간단한 작업을 사용 하는 스레드를 실행 하는 기존 코드를 조정 하는 방법을 보여 줍니다.

A *간단한 작업* 에서 직접 예약 된 작업을 [concurrency:: scheduler](../../parallel/concrt/reference/scheduler-class.md) 또는 [concurrency:: schedulegroup](../../parallel/concrt/reference/schedulegroup-class.md) 개체입니다. 간단한 작업은 동시성 런타임의 일정 예약 기능을 사용하도록 기존 코드를 조정하는 경우에 유용합니다.

## <a name="prerequisites"></a>전제 조건

이 연습을 시작 하기 전에 항목을 읽어 [작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)합니다.

## <a name="example"></a>예제

### <a name="description"></a>설명

다음 예제에서는 만들고 스레드를 실행 하는 Windows API의 일반적인 사용법을 보여 줍니다. 이 예제에서는 합니다 [CreateThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createthread) 함수를 호출 하는 `MyThreadFunction` 별도 스레드에서 합니다.

### <a name="code"></a>코드

[!code-cpp[concrt-windows-threads#1](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_1.cpp)]

### <a name="comments"></a>설명

이 예제의 결과는 다음과 같습니다.

```Output
Parameters = 50, 100
```

다음 단계에는 동시성 런타임은 동일한 작업을 수행 하는 데 코드 예제를 조정 하는 방법을 보여 줍니다.

### <a name="to-adapt-the-example-to-use-a-lightweight-task"></a>간단한 작업을 사용 하는 예제에 맞게

1. 추가 된 `#include` 헤더 파일 concrt.h에 대 한 지시문입니다.

[!code-cpp[concrt-migration-lwt#2](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_2.cpp)]

1. 추가 된 `using` 지시문에 대 한는 `concurrency` 네임 스페이스입니다.

[!code-cpp[concrt-migration-lwt#3](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_3.cpp)]

1. 선언을 변경 `MyThreadFunction` 사용 하는 `__cdecl` 호출 규칙 및 반환할 `void`합니다.

[!code-cpp[concrt-migration-lwt#4](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_4.cpp)]

1. 수정 합니다 `MyData` 포함할 구조를 [concurrency:: event](../../parallel/concrt/reference/event-class.md) 작업이 완료 되는 기본 응용 프로그램에 신호를 보내는 개체입니다.

[!code-cpp[concrt-migration-lwt#5](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_5.cpp)]

1. 에 대 한 호출을 바꿉니다 `CreateThread` 에 대 한 호출을 사용 하 여 합니다 [concurrency::CurrentScheduler::ScheduleTask](reference/currentscheduler-class.md#scheduletask) 메서드.

[!code-cpp[concrt-migration-lwt#6](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_6.cpp)]

1. 에 대 한 호출을 바꿉니다 `WaitForSingleObject` 를 호출 하 여는 [끝나기를](reference/event-class.md#wait) 작업이 완료 되기를 대기 하는 방법입니다.

[!code-cpp[concrt-migration-lwt#7](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_7.cpp)]

1. 호출을 제거 `CloseHandle`합니다.

1. 정의의 시그니처 변경 `MyThreadFunction` 3 단계와 일치 하도록 합니다.

[!code-cpp[concrt-migration-lwt#8](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_8.cpp)]

9. 끝에 `MyThreadFunction` 함수를 호출 합니다 [끝났음을](reference/event-class.md#set) 작업이 완료 되는 기본 응용 프로그램에 신호 하는 방법입니다.

[!code-cpp[concrt-migration-lwt#9](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_9.cpp)]

10. 제거 된 `return` 에서 문을 `MyThreadFunction`합니다.

## <a name="example"></a>예제

### <a name="description"></a>설명

다음 완성 된 예제에서는 코드를 호출 하는 간단한 작업을 사용 하 여 `MyThreadFunction` 함수입니다.

### <a name="code"></a>코드

[!code-cpp[concrt-migration-lwt#1](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_10.cpp)]

### <a name="comments"></a>설명

## <a name="see-also"></a>참고자료

[작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Scheduler 클래스](../../parallel/concrt/reference/scheduler-class.md)
