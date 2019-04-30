---
title: '방법: 실행 순서를 영향을 주는 일정 그룹 사용'
ms.date: 11/04/2016
helpviewer_keywords:
- schedule groups, using [Concurrency Runtime]
- using schedule groups [Concurrency Runtime]
ms.assetid: 73124194-fc3a-491e-a23f-fbd7b5a4455c
ms.openlocfilehash: 99e0383fc8d16f3eeb6e43e59424ab0984ee5c14
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62367046"
---
# <a name="how-to-use-schedule-groups-to-influence-order-of-execution"></a>방법: 실행 순서를 영향을 주는 일정 그룹 사용

동시성 런타임에서 작업 예정인 순서 명확 하지 않습니다. 그러나 작업이 실행 되는 순서에 영향을 줍니다 일정 예약 정책을 사용할 수 있습니다. 이 항목에서는 함께 일정 그룹을 사용 하는 방법을 보여 줍니다.는 [concurrency::SchedulingProtocol](reference/concurrency-namespace-enums.md#policyelementkey) 스케줄러 정책 작업이 실행 되는 순서에 영향을 줍니다.

이 예제에서는 다른 예약 정책을 사용 하 여 각 작업을 두 번의 집합을 실행합니다. 두 정책 모두 두 개의 처리 리소스의 최대 수를 제한 합니다. 처음 사용 하 여 실행 합니다 `EnhanceScheduleGroupLocality` 정책, 기본값 및 두 번째 실행에서는 `EnhanceForwardProgress` 정책입니다. 아래는 `EnhanceScheduleGroupLocality` 정책을 스케줄러 모든 작업 그룹에서 실행 한 일정 각 태스크를 완료 하거나 생성 될 때까지 합니다. 아래는 `EnhanceForwardProgress` 정책을 스케줄러는 다음 일정 그룹으로 이동 라운드 로빈 방식으로 작업 중 하나를 완료 하거나 생성 후 합니다.

각 일정 그룹 관련된 작업을 포함 하는 경우는 `EnhanceScheduleGroupLocality` 정책 성능이 향상 작업 간에 캐시 집약성이 유지 하기 때문에 일반적으로 발생 합니다. `EnhanceForwardProgress` 정책 작업 앞으로 진행할 수 있으며 일정 그룹 간의 공정성을 예약 해야 하는 경우에 유용 합니다.

## <a name="example"></a>예제

이 예제에서는 정의 된 `work_yield_agent` 클래스에서 파생 되는 [concurrency:: agent](../../parallel/concrt/reference/agent-class.md)합니다. `work_yield_agent` 클래스 작업 단위를 수행 현재 컨텍스트를 생성 하 고 다른 작업 단위를 수행 합니다. 에이전트를 사용 하는 [concurrency:: wait](reference/concurrency-namespace-functions.md#wait) 다른 컨텍스트에서 실행할 수 있도록 현재 컨텍스트를 협조적으로 양보 하는 함수입니다.

이 예제에서는 네 가지 `work_yield_agent` 개체입니다. 에이전트가 실행 되는 순서에 영향을 주도록 스케줄러 정책을 설정 하는 방법을 설명 하기 위해,이 예제에서는 하나의 일정 그룹 및 다른 일정 그룹을 사용 하 여 다른 두 명의 에이전트를 사용 하 여 처음 두 에이전트를 연결 합니다. 이 예제에서는 사용 합니다 [concurrency::CurrentScheduler::CreateScheduleGroup](reference/currentscheduler-class.md#createschedulegroup) 메서드를를 [concurrency:: schedulegroup](../../parallel/concrt/reference/schedulegroup-class.md) 개체입니다. 이 예제에서는 다른 예약 정책 사용 하 여 각 시간을 두 번 모든 네 명의 에이전트를 실행합니다.

[!code-cpp[concrt-scheduling-protocol#1](../../parallel/concrt/codesnippet/cpp/how-to-use-schedule-groups-to-influence-order-of-execution_1.cpp)]

이 예제의 결과는 다음과 같습니다.

```Output
Using EnhanceScheduleGroupLocality...
group 0,
    task 0: first loop...
group 0,
    task 1: first loop...
group 0,
    task 0: waiting...
group 1,
    task 0: first loop...
group 0,
    task 1: waiting...
group 1,
    task 1: first loop...
group 1,
    task 0: waiting...
group 0,
    task 0: second loop...
group 1,
    task 1: waiting...
group 0,
    task 1: second loop...
group 0,
    task 0: finished...
group 1,
    task 0: second loop...
group 0,
    task 1: finished...
group 1,
    task 1: second loop...
group 1,
    task 0: finished...
group 1,
    task 1: finished...

Using EnhanceForwardProgress...
group 0,
    task 0: first loop...
group 1,
    task 0: first loop...
group 0,
    task 0: waiting...
group 0,
    task 1: first loop...
group 1,
    task 0: waiting...
group 1,
    task 1: first loop...
group 0,
    task 1: waiting...
group 0,
    task 0: second loop...
group 1,
    task 1: waiting...
group 1,
    task 0: second loop...
group 0,
    task 0: finished...
group 0,
    task 1: second loop...
group 1,
    task 0: finished...
group 1,
    task 1: second loop...
group 0,
    task 1: finished...
group 1,
    task 1: finished...
```

두 정책 모두 동일한 이벤트 시퀀스를 생성합니다. 그러나 사용 하는 정책은 `EnhanceScheduleGroupLocality` 두 번째 그룹의 일부인 에이전트를 시작 하기 전에 첫 번째 일정 그룹에 포함 된 두 에이전트를 시작 합니다. 사용 하는 정책을 `EnhanceForwardProgress` 첫 번째 그룹에서 하나의 에이전트를 시작 하 고 다음 두 번째 그룹의 첫 번째 에이전트를 시작 합니다.

## <a name="compiling-the-code"></a>코드 컴파일

예제 코드를 복사하여 Visual Studio 프로젝트 또는 `scheduling-protocol.cpp` 파일에 붙여넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.

**cl.exe /EHsc 예약 protocol.cpp**

## <a name="see-also"></a>참고자료

[일정 그룹](../../parallel/concrt/schedule-groups.md)<br/>
[비동기 에이전트](../../parallel/concrt/asynchronous-agents.md)
