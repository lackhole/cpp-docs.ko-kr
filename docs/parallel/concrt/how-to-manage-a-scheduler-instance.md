---
title: '방법: 스케줄러 인스턴스 관리'
ms.date: 11/04/2016
helpviewer_keywords:
- managing a scheduler instance [Concurrency Runtime]
- scheduler instances, managing [Concurrency Runtime]
ms.assetid: 2cc804f0-5ff3-498b-97f1-a9f67a005448
ms.openlocfilehash: bc7adfaeb4c96245488bbcb5cd70cdae9daf9e26
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413881"
---
# <a name="how-to-manage-a-scheduler-instance"></a>방법: 스케줄러 인스턴스 관리

스케줄러 인스턴스를 통해 다양 한 종류의 워크 로드를 사용 하 여 특정 일정 예약 정책을 연결할 수 있습니다. 이 항목에서는 만들고 스케줄러 인스턴스를 관리 하는 방법을 보여 주는 두 가지 기본 예제를 포함 합니다.

예제에서는 기본 스케줄러 정책을 사용 하는 스케줄러를 만듭니다. 스케줄러를 만드는 예제를 사용자 지정 정책에서는 참조 [방법: 특정 스케줄러 정책 지정](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)합니다.

### <a name="to-manage-a-scheduler-instance-in-your-application"></a>응용 프로그램에서 스케줄러 인스턴스 관리

1. 만들기는 [concurrency:: schedulerpolicy](../../parallel/concrt/reference/schedulerpolicy-class.md) 정책이 포함 된 개체를 사용 하 여 스케줄러에 대 한 값입니다.

1. 호출 된 [concurrency::CurrentScheduler::Create](reference/currentscheduler-class.md#create) 메서드 또는 [concurrency::Scheduler::Create](reference/scheduler-class.md#create) 스케줄러 인스턴스를 만드는 방법.

   사용 하는 경우는 `Scheduler::Create` 메서드를 호출 합니다 [concurrency::Scheduler::Attach](reference/scheduler-class.md#attach) 메서드는 현재 컨텍스트를 사용 하 여 스케줄러를 연결 해야 하는 경우.

1. 호출 된 [CreateEvent](/windows/desktop/api/synchapi/nf-synchapi-createeventa) 신호를 자동 재설정 이벤트 개체에 대 한 핸들을 만드는 함수입니다.

1. 방금 만든 이벤트 개체에 핸들을 전달 합니다 [concurrency::CurrentScheduler::RegisterShutdownEvent](reference/currentscheduler-class.md#registershutdownevent) 메서드 또는 [concurrency::Scheduler::RegisterShutdownEvent](reference/scheduler-class.md#registershutdownevent) 메서드. 이 스케줄러 소멸 될 때 설정할 이벤트를 등록 합니다.

1. 현재 스케줄러로 예약 하려는 작업을 수행 합니다.

1. 호출 된 [concurrency::CurrentScheduler::Detach](reference/currentscheduler-class.md#detach) 메서드를 현재 스케줄러를 분리 하 고 현재 이전 스케줄러를 복원 합니다.

   사용 하는 경우는 `Scheduler::Create` 메서드를 호출 합니다 [concurrency::Scheduler::Release](reference/scheduler-class.md#release) 참조 횟수를 감소 시키기 위해 메서드를 `Scheduler` 개체.

1. 이벤트에 핸들을 전달 합니다 [WaitForSingleObject](/windows/desktop/api/synchapi/nf-synchapi-waitforsingleobject) 함수를 종료 하려면 스케줄러에 대 한 대기 합니다.

1. 호출 된 [CloseHandle](/windows/desktop/api/handleapi/nf-handleapi-closehandle) 함수를 이벤트 개체에 대 한 핸들을 닫습니다.

## <a name="example"></a>예제

다음 코드는 두 가지 스케줄러 인스턴스 관리 방법으로 보여 줍니다. 각 예제는 먼저 현재 스케줄러의 고유 식별자를 출력 하는 작업을 수행 하려면 기본 스케줄러를 사용 합니다. 각 예제는 다음 동일한 작업을 다시 수행 하도록 스케줄러 인스턴스를 사용 합니다. 마지막으로, 각 예제는 현재 기본 스케줄러를 복원 하 고 한 번 더 작업을 수행 합니다.

사용 하 여 첫 번째 예제는 [concurrency:: currentscheduler](../../parallel/concrt/reference/currentscheduler-class.md) 스케줄러 인스턴스를 만들고 현재 컨텍스트와 연결 하는 클래스입니다. 사용 하 여 두 번째 예제는 [concurrency:: scheduler](../../parallel/concrt/reference/scheduler-class.md) 동일한 작업을 수행 하는 클래스입니다. 일반적으로 `CurrentScheduler` 클래스 현재 스케줄러를 사용 하는 데 사용 됩니다. 사용 하는 두 번째 예제는 `Scheduler` 클래스, 스케줄러가 현재 컨텍스트에 연결 된 경우 또는 특정 작업을 사용 하 여 특정 스케줄러를 연결 하려는 경우를 제어 하려는 경우에 유용 합니다.

[!code-cpp[concrt-scheduler-instance#1](../../parallel/concrt/codesnippet/cpp/how-to-manage-a-scheduler-instance_1.cpp)]

이 예제의 결과는 다음과 같습니다.

```Output
Using CurrentScheduler class...

Current scheduler id: 0
Creating and attaching scheduler...
Current scheduler id: 1
Detaching scheduler...
Current scheduler id: 0

Using Scheduler class...

Current scheduler id: 0
Creating scheduler...
Attaching scheduler...
Current scheduler id: 2
Detaching scheduler...
Current scheduler id: 0
```

## <a name="compiling-the-code"></a>코드 컴파일

예제 코드를 복사하여 Visual Studio 프로젝트 또는 `scheduler-instance.cpp` 파일에 붙여넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.

**cl.exe /EHsc scheduler-instance.cpp**

## <a name="see-also"></a>참고자료

[스케줄러 인스턴스](../../parallel/concrt/scheduler-instances.md)<br/>
[방법: 특정 스케줄러 정책 지정](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)
