---
title: '연습: 사용자 지정 메시지 블록 만들기'
ms.date: 04/25/2019
helpviewer_keywords:
- creating custom message blocks Concurrency Runtime]
- custom message blocks, creating [Concurrency Runtime]
ms.assetid: 4c6477ad-613c-4cac-8e94-2c9e63cd43a1
ms.openlocfilehash: e7dfc5d78d2281d77b9ce882b302c4d7db776d3b
ms.sourcegitcommit: 283cb64fd7958a6b7fbf0cd8534de99ac8d408eb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64856991"
---
# <a name="walkthrough-creating-a-custom-message-block"></a>연습: 사용자 지정 메시지 블록 만들기

이 문서에는 들어오는 메시지를 우선 순위별로 정렬 하는 사용자 지정 메시지 블록 형식을 만드는 방법을 설명 합니다.

기본 제공 메시지 블록 형식을 다양 한 기능을 제공 하지만 고유의 메시지 블록 형식을 만들고 응용 프로그램의 요구 사항에 맞게 사용자 지정할 수 있습니다. 비동기 에이전트 라이브러리에서 제공 하는 기본 제공 메시지 블록 형식에 대 한 참조 [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)합니다.

## <a name="prerequisites"></a>전제 조건

이 연습을 시작 하기 전에 다음 문서를 읽어 보십시오.

- [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)

- [메시지 전달 함수](../../parallel/concrt/message-passing-functions.md)

##  <a name="top"></a> 섹션

이 연습에는 다음과 같은 섹션이 있습니다.

- [사용자 지정 메시지 블록 디자인](#design)

- [Priority_buffer 클래스를 정의합니다.](#class)

- [전체 예제](#complete)

##  <a name="design"></a> 사용자 지정 메시지 블록 디자인

메시지 블록의 메시지 보내기 및 받기 작업에 참여 합니다. 메시지를 보내는 메시지 블록 이라고는 *소스 블록*합니다. 메시지를 수신 하는 메시지 블록 이라고는 *대상 블록*합니다. 메시지 블록을 보내고 메시지를 수신 하 라고 한 *전파자 블록*합니다. 에이전트 라이브러리에서는 추상 클래스 [concurrency:: isource](../../parallel/concrt/reference/isource-class.md) 소스 블록을 나타내고 추상 클래스 [concurrency:: itarget](../../parallel/concrt/reference/itarget-class.md) 를 대상 블록을 나타냅니다. 메시지 블록 형식을 작동 하는 원본에서 파생 `ISource`;에서 파생 되는 대상 메시지 블록 작동 하는 형식을 `ITarget`합니다.

직접 메시지 블록 형식을 파생할 수 있지만 `ISource` 고 `ITarget`, 에이전트 라이브러리에 공통 된 모든 메시지 블록 형식, 예를 들어, 오류 처리 기능을 많이 수행 하는 세 가지 기본 클래스를 정의 하 고 동시성 으로부터 안전한 방식으로 메시지 블록을 함께 연결 합니다. 합니다 [concurrency:: source_block](../../parallel/concrt/reference/source-block-class.md) 클래스에서 파생 되며 `ISource` 하 고 다른 블록에 메시지를 보냅니다. 합니다 [concurrency:: target_block](../../parallel/concrt/reference/target-block-class.md) 클래스에서 파생 되며 `ITarget` 다른 블록에서 메시지를 받습니다. 합니다 [concurrency:: propagator_block](../../parallel/concrt/reference/propagator-block-class.md) 클래스에서 파생 됩니다 `ISource` 및 `ITarget` 고 다른 블록에서 메시지를 수신 하는 다른 블록에 메시지를 보냅니다. 이러한 세 가지 기본 클래스를 사용 하 여 메시지 블록의 동작에 집중할 수 있도록 인프라 세부 정보를 처리 하는 것이 좋습니다.

`source_block`, `target_block`, 및 `propagator_block` 클래스는 형식 연결, 관리 또는 링크에 대해, 원본 및 대상 블록 간의 및 메시지를 처리 하는 방법을 관리 하는 형식 매개 변수화 된 템플릿입니다. 에이전트 라이브러리 정의 링크 관리를 수행 하는 두 형식이 [concurrency:: single_link_registry](../../parallel/concrt/reference/single-link-registry-class.md) 하 고 [concurrency:: multi_link_registry](../../parallel/concrt/reference/multi-link-registry-class.md)합니다. `single_link_registry` 클래스를 사용 하면 단일 대상에 대 한 소스와 연결할 메시지 블록입니다. `multi_link_registry` 클래스를 사용 하면 메시지 블록을 여러 원본 또는 대상을 여러 개 연결할 수 있습니다. 에이전트 라이브러리 정의 메시지 관리를 수행 하는 클래스인 [concurrency:: ordered_message_processor](../../parallel/concrt/reference/ordered-message-processor-class.md)합니다. `ordered_message_processor` 클래스 메시지 블록이 해당 받는 순서 대로 메시지를 처리할 수 있습니다.

원본 및 대상 메시지 블록의 관계를 더 잘 이해 하려면 다음 예제를 살펴보겠습니다. 이 예의 선언을 보여 줍니다.는 [concurrency:: transformer](../../parallel/concrt/reference/transformer-class.md) 클래스입니다.

[!code-cpp[concrt-priority-buffer#20](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_1.cpp)]

`transformer` 클래스에서 파생 되며 `propagator_block`, 하며 따라서 모두 소스 블록 및 대상 블록입니다. 형식의 메시지를 수락 `_Input` 유형의 메시지를 보내고 `_Output`합니다. 합니다 `transformer` 클래스를 지정 `single_link_registry` 모든 대상 블록에 대 한 연결 관리자 및 `multi_link_registry` 소스 블록에 대 한 연결 관리자입니다. 따라서는 `transformer` 하나의 대상 및 원본 개수에 제한 없이 개체가 있습니다.

파생 된 클래스 `source_block` 6 가지 메서드를 구현 해야 합니다. [propagate_to_any_targets](reference/source-block-class.md#propagate_to_any_targets)를 [accept_message](reference/source-block-class.md#accept_message)를 [reserve_message](reference/source-block-class.md#reserve_message), [ consume_message](reference/source-block-class.md#consume_message)하십시오 [release_message](reference/source-block-class.md#release_message), 및 [resume_propagation](reference/source-block-class.md#resume_propagation)합니다. 파생 된 클래스 `target_block` 구현 해야 합니다는 [propagate_message](reference/propagator-block-class.md#propagate_message) 메서드 및 선택적으로 구현할 수는 [send_message](reference/propagator-block-class.md#send_message) 메서드. 파생 `propagator_block` 둘 다에서 파생 하는 기능적 `source_block` 고 `target_block`합니다.

`propagate_to_any_targets` 메서드가 동기적 또는 비동기적으로 들어오는 메시지를 처리 하 고 모든 나가는 메시지를 전파 하기 위해 런타임에서 호출 됩니다. `accept_message` 메시지를 받을 대상 블록에서 호출 됩니다. 와 같은 블록 형식인 메시지 대부분 `unbounded_buffer`, 메시지를 받는 첫 번째 대상만 보냅니다. 따라서 대상에 메시지의 소유권을 전송합니다. 와 같은 다른 메시지 블록 형식 [concurrency:: overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md), 각 대상 블록에 메시지를 제공 합니다. 따라서 `overwrite_buffer` 각 대상에 대 한 메시지의 복사본을 만듭니다.

합니다 `reserve_message`, `consume_message`, `release_message`, 및 `resume_propagation` 메서드 메시지 예약에 참여 하려면 메시지 요소를 사용 합니다. 대상 호출을 차단 합니다 `reserve_message` 메서드는 메시지를 제공 하며 나중에 사용할 메시지를 예약 해야 하는 경우. 대상 블록은 메시지를 예약한 후 호출할 수는 `consume_message` 해당 메시지를 사용 하는 방법 또는 `release_message` 예약을 취소 하는 방법입니다. 와 마찬가지로 합니다 `accept_message` 메서드를 구현 `consume_message` 메시지의 소유권을 전송 하거나 메시지의 복사본을 반환 합니다. 대상 블록을 사용 하거나 예약된 된 메시지를 해제, 런타임이 호출을 `resume_propagation` 메서드. 일반적으로이 메서드는 큐의 다음 메시지 부터는 메시지 전파를 계속 합니다.

런타임 호출을 `propagate_message` 다른 블록에서 현재 메시지를 비동기적으로 전송 하는 방법입니다. 합니다 `send_message` 메서드가 유사 `propagate_message`동기적으로 대신 비동기적으로 메시지를 보낼 대상 블록에는 제외 합니다. 기본 구현을 `send_message` 모든 들어오는 메시지를 거부 합니다. 런타임 호출 하지 않습니다 이러한 방법 중 하나는 메시지는 대상 블록을 사용 하 여 연결 된 선택적 필터 함수를 통과 하지 못한 경우. 메시지 필터에 대 한 자세한 내용은 참조 하세요. [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)합니다.

[[맨 위로 이동](#top)]

##  <a name="class"></a> Priority_buffer 클래스를 정의합니다.

`priority_buffer` 클래스는 우선 순위별로 정리한 다음 메시지를 수신 하는 순서에 따라 들어오는 메시지를 먼저 정리 하는 사용자 지정 메시지 블록 형식입니다. 합니다 `priority_buffer` 클래스와 유사 합니다 [concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) 메시지 큐를 포함 하기 때문에 클래스 및 소스 및 대상 메시지 블록으로 작동 하며 여러 소스 및 여러를 가질 수 있으므로 대상으로 합니다. 그러나 `unbounded_buffer` 기본 메시지는 해당 원본에서 메시지를 수신 하는 순서에만 전파 합니다.

`priority_buffer` 유형의 메시지를 수신 하는 클래스 std::[튜플](../../standard-library/tuple-class.md) 포함 하는 `PriorityType` 및 `Type` 요소입니다. `PriorityType` 각 메시지의 우선 순위를 보유 하는 형식을 참조합니다 `Type` 메시지의 데이터 부분을 가리킵니다. 합니다 `priority_buffer` 클래스의 형식의 메시지를 보내는 `Type`합니다. 합니다 `priority_buffer` 클래스에는 또한 두 개의 메시지 큐 관리:를 [std::priority_queue](../../standard-library/priority-queue-class.md) 들어오는 메시지에 대 한 개체 및는 std::[큐](../../standard-library/queue-class.md) 보내는 메시지에 대 한 개체입니다. 우선 순위에 따라 메시지 순서 지정은 경우에 유용는 `priority_buffer` 소비자가 메시지를 읽기 전에 여러 메시지를 받는 경우 또는 개체에 동시에 여러 메시지를 수신 합니다.

7 메서드 외에도 파생 된 클래스 `propagator_block` 구현 해야 합니다 `priority_buffer` 클래스에 재정의는 `link_target_notification` 및 `send_message` 메서드. `priority_buffer` 클래스에는 또한 두 개의 공용 도우미 메서드를 정의 `enqueue` 하 고 `dequeue`, 및 전용 도우미 메서드를 `propagate_priority_order`입니다.

다음 절차를 구현 하는 방법에 설명 합니다 `priority_buffer` 클래스입니다.

#### <a name="to-define-the-prioritybuffer-class"></a>Priority_buffer 클래스를 정의 하려면

1. 만들기는 C++ 헤더 파일 하 고 이름을 `priority_buffer.h`합니다. 또는 프로젝트의 일부인 기존 헤더 파일을 사용할 수 있습니다.

1. `priority_buffer.h`, 다음 코드를 추가 합니다.

[!code-cpp[concrt-priority-buffer#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_2.h)]

1. 에 `std` 네임 스페이스의 특수화를 정의 [std:: less](../../standard-library/less-struct.md) 하 고 [std::greater](../../standard-library/greater-struct.md) 동시성에서 작동 하는::[메시지](../../parallel/concrt/reference/message-class.md) 개체.

[!code-cpp[concrt-priority-buffer#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_3.h)]

   합니다 `priority_buffer` 저장소 클래스 `message` 개체를 `priority_queue` 개체입니다. 메시지 우선 순위에 따라 정렬 우선 순위 큐를 사용 하는 이러한 형식 특수화 합니다. 우선 순위는 첫 번째 요소는 `tuple` 개체입니다.

1. 에 `concurrencyex` 네임 스페이스를 선언 합니다 `priority_buffer` 클래스입니다.

[!code-cpp[concrt-priority-buffer#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_4.h)]

   `priority_buffer` 클래스는 `propagator_block`에서 파생됩니다. 따라서이 수 모두 송신 및 수신 메시지. 합니다 `priority_buffer` 클래스의 형식의 메시지를 수신 하는 여러 대상이 있을 수 있습니다 `Type`합니다. 유형의 메시지를 전송 하는 여러 원본 수도 `tuple<PriorityType, Type>`합니다.

1. 에 `private` 의 섹션은 `priority_buffer` 클래스에 다음 멤버 변수를 추가 합니다.

[!code-cpp[concrt-priority-buffer#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_5.h)]

   합니다 `priority_queue` 들어오는 메시지를 보유 하는 개체, `queue` 개체는 보내는 메시지를 보유 합니다. A `priority_buffer` 개체는 동시에 여러 메시지를 받을 수 있습니다; 그리고 `critical_section` 입력된 메시지의 큐에 대 한 액세스를 동기화 하는 개체입니다.

1. 에 `private` 섹션, 복사 생성자 및 대입 연산자를 정의 합니다. 그러면 `priority_queue` 개체를 할당할 수 없게 합니다.

[!code-cpp[concrt-priority-buffer#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_6.h)]

1. 에 `public` 섹션, 여러 메시지 블록 형식에 공통 되는 생성자를 정의 합니다. 소멸자를 정의할 수도 있습니다.

[!code-cpp[concrt-priority-buffer#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_7.h)]

1. 에 `public` 섹션에서 메서드를 정의 합니다 `enqueue` 및 `dequeue`합니다. 이러한 도우미 메서드는 메시지를 전송에서 메시지를 수신 하는 대체 방법을 제공 합니다.는 `priority_buffer` 개체입니다.

[!code-cpp[concrt-priority-buffer#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_8.h)]

9. 에 `protected` 섹션을 정의 합니다 `propagate_to_any_targets` 메서드.

[!code-cpp[concrt-priority-buffer#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_9.h)]

   `propagate_to_any_targets` 메서드는 입력된 큐 출력 큐의 앞에 있고 출력 큐의 모든 메시지를 전파 하는 메시지를 전송 합니다.

10. 에 `protected` 섹션을 정의 합니다 `accept_message` 메서드.

[!code-cpp[concrt-priority-buffer#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_10.h)]

   대상 블록을 호출 하는 경우는 `accept_message` 메서드는 `priority_buffer` 수락 하는 첫 번째 대상 블록에 메시지의 소유권을 전송 하는 클래스입니다. (의 동작과 비슷합니다이 `unbounded_buffer`.)

11. 에 `protected` 섹션을 정의 합니다 `reserve_message` 메서드.

[!code-cpp[concrt-priority-buffer#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_11.h)]

   `priority_buffer` 클래스를 사용 하면 제공 된 메시지 식별자가 큐의 앞에 있는 메시지의 식별자와 일치 하는 경우 메시지를 예약 하는 대상 블록입니다. 즉, 통해 대상 하는 경우 메시지를 예약할 수는 `priority_buffer` 개체는 추가 메시지를 아직 받지 않은 및 현재 아직 전파 되지 않습니다.

12. 에 `protected` 섹션을 정의 합니다 `consume_message` 메서드.

[!code-cpp[concrt-priority-buffer#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_12.h)]

   대상 블록은 호출 `consume_message` 예약 된 메시지의 소유권을 전송 합니다.

13. 에 `protected` 섹션을 정의 합니다 `release_message` 메서드.

[!code-cpp[concrt-priority-buffer#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_13.h)]

   대상 블록은 호출 `release_message` 메시지에 대 한 예약을 취소 합니다.

14. 에 `protected` 섹션을 정의 합니다 `resume_propagation` 메서드.

[!code-cpp[concrt-priority-buffer#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_14.h)]

   런타임 호출 `resume_propagation` 후 대상 블록을 사용 하거나 예약된 된 메시지를 해제 합니다. 이 메서드는 출력 큐에 있는 모든 메시지를 전파 합니다.

15. 에 `protected` 섹션을 정의 합니다 `link_target_notification` 메서드.

[!code-cpp[concrt-priority-buffer#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_15.h)]

   합니다 `_M_pReservedFor` 멤버 변수는 기본 클래스를 정의한 `source_block`합니다. 이 멤버 변수는 출력 큐의 앞에 있는 메시지에 대 한 예약을 포함 하는 경우 대상 블록을 가리킵니다. 런타임 호출 `link_target_notification` 새 대상에 연결 되는 경우는 `priority_buffer` 개체입니다. 이 메서드 대상이 없습니다. 예약을 보유 하는 경우 출력 큐에 있는 모든 메시지를 전파 합니다.

16. 에 `private` 섹션을 정의 합니다 `propagate_priority_order` 메서드.

[!code-cpp[concrt-priority-buffer#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_16.h)]

   이 메서드는 출력 큐에서 모든 메시지 전파합니다. 큐의 모든 메시지는 대상 블록 중 하나에서 메시지를 수락 될 때까지 모든 대상 블록에 제공 됩니다. `priority_buffer` 클래스는 나가는 메시지의 순서를 유지 합니다. 따라서 출력 큐의 첫 번째 메시지에 동의 해야 합니다는 대상 블록에 의해이 메서드는 대상 블록에 있는 다른 모든 메시지를 제공 합니다.

17. 에 `protected` 섹션을 정의 합니다 `propagate_message` 메서드.

[!code-cpp[concrt-priority-buffer#16](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_17.h)]

   `propagate_message` 메서드를 사용 하면은 `priority_buffer` 나 대상 하는 클래스는 메시지 받는 사람 역할을 합니다. 이 메서드는 제공 된 소스 블록에서 제공 하 고 우선 순위 큐에 메시지를 삽입 하는 메시지를 받습니다. `propagate_message` 메서드 다음 비동기적으로 보내는 모든 대상 블록에 메시지를 출력 합니다.

   호출할 때 런타임에서이 메서드를 호출 합니다 [concurrency:: asend](reference/concurrency-namespace-functions.md#asend) 함수 또는 메시지 블록이 다른 메시지 블록에 연결 되어 경우.

18. 에 `protected` 섹션을 정의 합니다 `send_message` 메서드.

[!code-cpp[concrt-priority-buffer#17](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_18.h)]

   합니다 `send_message` 메서드가 유사 `propagate_message`합니다. 그러나 비동기적으로 대신 동기적으로 출력 메시지를 보냅니다.

   런타임에서 호출 하는 경우 등의 동기 전송 작업을 하는 동안이 메서드를 호출 합니다 [concurrency:: send](reference/concurrency-namespace-functions.md#send) 함수입니다.

`priority_buffer` 클래스는 일반적으로 여러 메시지 블록 형식에는 생성자 오버 로드를 포함 합니다. 일부 생성자 오버 로드 [concurrency:: scheduler](../../parallel/concrt/reference/scheduler-class.md) 하거나 [concurrency:: schedulegroup](../../parallel/concrt/reference/schedulegroup-class.md) 특정 작업 스케줄러로 관리 되는 메시지 블록을 사용 하도록 설정 하는 개체입니다. 다른 생성자 오버 로드는 필터 함수를 받습니다. 필터 함수를 사용 하면 메시지 블록을 수락 하거나 해당 페이로드를 기준으로 메시지를 거부 합니다. 메시지 필터에 대 한 자세한 내용은 참조 하세요. [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)합니다. 작업 스케줄러에 대 한 자세한 내용은 참조 하세요. [작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)합니다.

때문에 합니다 `priority_buffer` 클래스는 우선 순위를 기준으로 메시지를 정렬 하 고 다음 메시지가 수신 되는 순서에서이 클래스는 가장 유용한 받으면 메시지를 비동기적으로 예를 들어, 호출 하는 경우는 [concurrency:: asend](reference/concurrency-namespace-functions.md#asend)함수 또는 메시지 블록이 다른 메시지 블록에 연결 되어 경우.

[[맨 위로 이동](#top)]

##  <a name="complete"></a> 전체 예제

다음 예제에서는의 전체 정의 `priority_buffer` 클래스입니다.

[!code-cpp[concrt-priority-buffer#18](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_19.h)]

다음 예제에서는 동시에 수행 하는 다양 한 `asend` 하 고 [concurrency:: receive](reference/concurrency-namespace-functions.md#receive) 에 대 한 작업을 `priority_buffer` 개체입니다.

[!code-cpp[concrt-priority-buffer#19](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_20.cpp)]

이 예제에서는 다음 샘플 출력을 생성합니다.

```Output
36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36
24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24
12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12
```

`priority_buffer` 클래스 주문 메시지가 먼저 우선 순위와 메시지를 받는 순서에 따라 합니다. 이 예제에서 큰 숫자 우선 순위를 사용 하 여 메시지 큐의 앞쪽 방향으로 삽입 됩니다.

[[맨 위로 이동](#top)]

## <a name="compiling-the-code"></a>코드 컴파일

예제 코드를 복사 하 고 Visual Studio 프로젝트에 붙여 넣습니다 또는의 정의 `priority_buffer` 라는 파일에는 클래스 `priority_buffer.h` 이라고 하는 파일에서 프로그램을 테스트 하 고 `priority_buffer.cpp` 후 Visual Studio에서 다음 명령을 실행 하 고 명령 프롬프트 창입니다.

**cl.exe /EHsc priority_buffer.cpp**

## <a name="see-also"></a>참고자료

[동시성 런타임 연습](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[메시지 전달 함수](../../parallel/concrt/message-passing-functions.md)
