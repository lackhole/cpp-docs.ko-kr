---
title: '연습: 간단한 작업을 사용 하기 위해 기존 코드 조정'
ms.date: 04/25/2019
helpviewer_keywords:
- using lightweight tasks [Concurrency Runtime]
- lightweight tasks, using [Concurrency Runtime]
ms.assetid: 1edfe818-d274-46de-bdd3-e92967c9bbe0
ms.openlocfilehash: 406d4d24d0042c7bded4f94dcef1e7731ab3947f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69512156"
---
# <a name="walkthrough-adapting-existing-code-to-use-lightweight-tasks"></a>연습: 간단한 작업을 사용 하기 위해 기존 코드 조정

이 항목에서는 Windows API를 사용 하 여 간단한 작업을 사용 하는 스레드를 만들고 실행 하는 기존 코드를 조정 하는 방법을 보여 줍니다.

*간단한 작업* 은 [Concurrency:: Scheduler](../../parallel/concrt/reference/scheduler-class.md) 또는 [concurrency:: ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) 개체에서 직접 예약 하는 작업입니다. 간단한 작업은 동시성 런타임의 일정 예약 기능을 사용하도록 기존 코드를 조정하는 경우에 유용합니다.

## <a name="prerequisites"></a>전제 조건

이 연습을 시작 하기 전에 [작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)항목을 참조 하세요.

## <a name="example"></a>예제

### <a name="description"></a>Description

다음 예제에서는 Windows API를 사용 하 여 스레드를 만들고 실행 하는 일반적인 방법을 보여 줍니다. 이 예제에서는 [CreateThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createthread) 함수를 사용 하 여 `MyThreadFunction` 별도의 스레드에서를 호출 합니다.

### <a name="code"></a>코드

[!code-cpp[concrt-windows-threads#1](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_1.cpp)]

### <a name="comments"></a>설명

이 예제의 결과는 다음과 같습니다.

```Output
Parameters = 50, 100
```

다음 단계에서는 동시성 런타임를 사용 하 여 동일한 작업을 수행 하는 코드 예제를 조정 하는 방법을 보여 줍니다.

### <a name="to-adapt-the-example-to-use-a-lightweight-task"></a>간단한 작업을 사용 하는 예제를 조정 하려면

1. 헤더 파일 `#include` 에 대 한 지시문을 추가 합니다.

[!code-cpp[concrt-migration-lwt#2](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_2.cpp)]

1. 네임`concurrency` 스페이스 `using` 에 대 한 지시문을 추가 합니다.

[!code-cpp[concrt-migration-lwt#3](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_3.cpp)]

1. 호출 규칙을 `MyThreadFunction` 사용 하 고를 반환 `void`하도록 선언을 변경 합니다. `__cdecl`

[!code-cpp[concrt-migration-lwt#4](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_4.cpp)]

1. 주 응용 프로그램에 작업이 완료 되었음을 알리는 [concurrency:: event](../../parallel/concrt/reference/event-class.md) 개체를 포함 하도록 구조체를수정합니다.`MyData`

[!code-cpp[concrt-migration-lwt#5](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_5.cpp)]

1. 에 대 `CreateThread` 한 호출을 [concurrency:: currentscheduler:: ScheduleTask](reference/currentscheduler-class.md#scheduletask) 메서드에 대 한 호출로 바꿉니다.

[!code-cpp[concrt-migration-lwt#6](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_6.cpp)]

1. 에 `WaitForSingleObject` 대 한 호출을 [concurrency:: event:: wait](reference/event-class.md#wait) 메서드에 대 한 호출로 바꿔서 작업이 완료 될 때까지 기다립니다.

[!code-cpp[concrt-migration-lwt#7](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_7.cpp)]

1. 에 대 한 `CloseHandle`호출을 제거 합니다.

1. 의 `MyThreadFunction` 정의 서명을 3 단계와 일치 하도록 변경 합니다.

[!code-cpp[concrt-migration-lwt#8](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_8.cpp)]

9. `MyThreadFunction` 함수가 종료 되 면 [concurrency:: event:: set](reference/event-class.md#set) 메서드를 호출 하 여 작업이 완료 되었음을 주 응용 프로그램에 알립니다.

[!code-cpp[concrt-migration-lwt#9](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_9.cpp)]

10. `return` 에서`MyThreadFunction`문을 제거 합니다.

## <a name="example"></a>예제

### <a name="description"></a>Description

다음 완성 된 예제에서는 간단한 작업을 사용 하 여 `MyThreadFunction` 함수를 호출 하는 코드를 보여 줍니다.

### <a name="code"></a>코드

[!code-cpp[concrt-migration-lwt#1](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_10.cpp)]

### <a name="comments"></a>주석

## <a name="see-also"></a>참고자료

[작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Scheduler 클래스](../../parallel/concrt/reference/scheduler-class.md)
