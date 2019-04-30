---
title: 비동기 에이전트
ms.date: 11/19/2018
helpviewer_keywords:
- asynchronous agents
- agents [Concurrency Runtime]
ms.assetid: 6cf6ccc6-87f1-4e14-af15-ea8ba58fef1a
ms.openlocfilehash: ff6fa851519066c3c399a28557fd8f103d0e94be
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412818"
---
# <a name="asynchronous-agents"></a>비동기 에이전트

*비동기 에이전트* (또는 그냥 *에이전트*)는 대규모 컴퓨팅 작업을 해결 하기 위해 다른 에이전트를 사용 하 여 비동기적으로 작동 하는 응용 프로그램 구성 요소입니다. 에이전트 수명 주기가 설정 하는 작업으로 간주 합니다. 예를 들어, 하나의 에이전트를 사용할 수 있는 데이터는 입/출력 장치 (예: 키보드, 디스크에서 파일 또는 네트워크 연결) 및 다른 에이전트에서 해당 데이터에 대해 작업 수행할 수 있습니다를 읽을 수 있습니다. 첫 번째 에이전트는 더 많은 데이터를 사용할 수 있는지에 두 번째 에이전트를 알리기 위해 메시지 전달을 사용 합니다. 차단 협조적으로 양보 하는 에이전트를 사용 하는 효율적인 메커니즘을 제공 하는 동시성 런타임 작업 scheduler 비효율적인 선점 하지 않고도 합니다.

에이전트 라이브러리에 정의 된 [concurrency:: agent](../../parallel/concrt/reference/agent-class.md) 비동기 에이전트를 나타내는 클래스입니다. `agent` 가상 메서드를 선언 하는 추상 클래스인 [concurrency::agent::run](reference/agent-class.md#run)합니다. `run` 메서드는 에이전트에서 수행 되는 작업을 실행 합니다. 때문에 `run` 는 추상이 메서드를 구현 해야이에서 파생 되는 모든 클래스에서 `agent`합니다.

## <a name="agent-life-cycle"></a>에이전트 수명 주기

에이전트에 수명 주기를 설정된 합니다. 합니다 [concurrency:: agent_status](reference/concurrency-namespace-enums.md#agent_status) 열거형은 에이전트의 다양 한 상태를 정의 합니다. 다음 그림은 다른 에이전트의 상태가 진행 하는 방식을 보여 주는 상태 다이어그램. 실선은이 그림에서는 응용 프로그램에서 호출 하는 메서드를 나타냅니다. 점선은 런타임에서 호출 되는 메서드를 나타냅니다.

![에이전트 상태 다이어그램](../../parallel/concrt/media/agentstate.png "에이전트 상태 다이어그램")

다음 표에서 각 상태에는 `agent_status` 열거형입니다.

|에이전트 상태|설명|
|-----------------|-----------------|
|`agent_created`|에이전트 실행에 대 한 예약 되지 않았습니다.|
|`agent_runnable`|런타임 실행을 위해 에이전트를 예약 하는 합니다.|
|`agent_started`|에이전트에서 시작 하 고 실행 합니다.|
|`agent_done`|에이전트를 완료 했습니다.|
|`agent_canceled`|에이전트를 시작 하기 전에 취소 된는 `started` 상태입니다.|

`agent_created` 에이전트의 초기 상태입니다 `agent_runnable` 하 고 `agent_started` 는 활성 상태, 및 `agent_done` 및 `agent_canceled` 터미널 상태에는 합니다.

사용 된 [concurrency::agent::status](reference/agent-class.md#status) 의 현재 상태를 검색 하는 메서드는 `agent` 개체. 하지만 `status` 메서드는 동시성 으로부터 안전한, 시간 에이전트의 상태를 변경할 수는 `status` 메서드가 반환 합니다. 예를 들어, 에이전트 수를 `agent_started` 를 호출할 때 상태를 `status` 이동 하지만 메서드를를 `agent_done` 직후 상태를 `status` 메서드가 반환 합니다.

## <a name="methods-and-features"></a>메서드 및 기능

다음 표에서 일부에 속해 있는 중요 한 메서드는 `agent` 클래스입니다. 모든 대 한 자세한 내용은 합니다 `agent` 클래스 메서드를 참조 하십시오 [agent 클래스](../../parallel/concrt/reference/agent-class.md)합니다.

|메서드|설명|
|------------|-----------------|
|[start](reference/agent-class.md#start)|일정 합니다 `agent` 실행에 대 한 개체를 설정 하 고는 `agent_runnable` 상태.|
|[run](reference/agent-class.md#run)|수행할 수 있는 작업을 실행 합니다 `agent` 개체입니다.|
|[done](reference/agent-class.md#done)|에이전트를 이동 합니다 `agent_done` 상태입니다.|
|[cancel](../../parallel/concrt/cancellation-in-the-ppl.md#cancel)|에이전트가 시작 되지 않은 경우이 메서드는 에이전트의 실행을 취소 하 고로 설정 합니다는 `agent_canceled` 상태입니다.|
|[status](reference/agent-class.md#status)|현재 상태를 검색 합니다 `agent` 개체입니다.|
|[wait](reference/agent-class.md#wait)|될 때까지 대기 합니다 `agent` 입력 개체를 `agent_done` 또는 `agent_canceled` 상태입니다.|
|[wait_for_all](reference/agent-class.md#wait_for_all)|제공 된 모든 대기 `agent` 개체를 입력 합니다 `agent_done` 또는 `agent_canceled` 상태입니다.|
|[wait_for_one](reference/agent-class.md#wait_for_one)|제공 된 하나 이상의 대기 `agent` 개체를 입력 합니다 `agent_done` 또는 `agent_canceled` 상태입니다.|

에이전트 개체를 만든 후 호출 된 [concurrency::agent::start](reference/agent-class.md#start) 실행에 대 한 예약 하는 방법입니다. 런타임 호출을 `run` 에이전트를 예약 하 고 설정 후 메서드는 `agent_runnable` 상태입니다.

런타임이 비동기 에이전트에서 throw 된 예외를 관리 하지 않습니다. 예외 처리 및 에이전트에 대 한 자세한 내용은 참조 하세요. [예외 처리](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)합니다.

## <a name="example"></a>예제

기본 에이전트 기반 응용 프로그램을 만드는 방법을 보여 주는 예제를 참조 하세요. [연습: 에이전트 기반 응용 프로그램을 만드는](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)합니다.

## <a name="see-also"></a>참고자료

[비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)
