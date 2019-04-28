---
title: 비동기 에이전트 라이브러리의 모범 사례
ms.date: 11/04/2016
helpviewer_keywords:
- best practices, Asynchronous Agents Library
- Asynchronous Agents Library, best practices
- Asynchronous Agents Library, practices to avoid
- practices to avoid, Asynchronous Agents Library
ms.assetid: 85f52354-41eb-4b0d-98c5-f7344ee8a8cf
ms.openlocfilehash: c61393957a63895a9ecbdaaae8d83a5fbd710de3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62236561"
---
# <a name="best-practices-in-the-asynchronous-agents-library"></a>비동기 에이전트 라이브러리의 모범 사례

이 문서에서는 비동기 에이전트 라이브러리를 효과적으로 사용 하는 방법을 설명 합니다. 에이전트 라이브러리에는 행위자 기반 프로그래밍 모델 및 정교 하지 않은 데이터 흐름에 대 한 전달 및 파이프라인 작업을 위해 in-process 메시지를 승격 합니다.

에이전트 라이브러리에 대 한 자세한 내용은 참조 하세요. [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)합니다.

##  <a name="top"></a> 섹션

이 문서는 다음 섹션으로 구성됩니다.

- [격리 상태로 에이전트를 사용 합니다.](#isolation)

- [제한 메커니즘을 사용 하 여 데이터 파이프라인에서 메시지의 수를 제한 하려면](#throttling)

- [데이터 파이프라인에서 세분화 된 작업을 수행 하지 않습니다](#fine-grained)

- [값으로 큰 메시지 페이로드를 전달 하지 마십시오](#large-payloads)

- [데이터 네트워크 경우 소유권은 정의 되지 않은 shared_ptr 사용](#ownership)

##  <a name="isolation"></a> 격리 상태로 에이전트를 사용 합니다.

에이전트 라이브러리는 비동기 메시지 전달 메커니즘을 통해 격리 된 구성 요소를 연결할 수 있도록 하 여 공유 상태에 대 한 대안을 제공 합니다. 비동기 에이전트는 내부 상태를 다른 구성 요소에서 격리할 때 가장 효과적입니다. 상태를 격리 하 여 여러 구성 요소가 작동 하지 않습니다 일반적으로 공유 데이터입니다. 상태 격리 응용 프로그램을 공유 메모리에 대 한 경합이 줄어들기 때문에 확장을 설정할 수 있습니다. 공유 데이터에 대 한 액세스를 동기화 하지 않아도 구성 요소 상태 격리 교착 상태 및 경합 상태 가능성을 줄어듭니다.

일반적으로의 데이터 멤버를 보유 하 여 에이전트에서 상태를 격리 합니다 `private` 또는 `protected` 섹션 에이전트 및 메시지 버퍼를 사용 하 여 상태 변경을 전달 하 여 합니다. 다음 예제는 `basic_agent` 클래스에서 파생 되는 [concurrency:: agent](../../parallel/concrt/reference/agent-class.md)합니다. `basic_agent` 클래스 두 메시지 버퍼를 사용 하 여 외부 구성 요소와 통신 합니다. 들어오는 메시지를 보유 하는 메시지 버퍼 다른 메시지 버퍼 나가는 메시지를 보관합니다.

[!code-cpp[concrt-simple-agent#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-asynchronous-agents-library_1.cpp)]

정의 및 에이전트를 사용 하는 방법에 대 한 전체 예제를 참조 하세요. [연습: 에이전트 기반 응용 프로그램을 만드는](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md) 고 [연습: 데이터 흐름 에이전트 만들기](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)합니다.

[[맨 위로 이동](#top)]

##  <a name="throttling"></a> 제한 메커니즘을 사용 하 여 데이터 파이프라인에서 메시지의 수를 제한 하려면

많은 메시지 버퍼 형식을 같은 [concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md), 메시지의 무제한 포함할 수 있습니다. 메시지 생산자가 메시지를 보내면 데이터 파이프라인을 소비자는 이러한 메시지를 처리할 수 있는 보다 더 빠르게, 응용 프로그램 메모리 부족 또는 메모리 부족 상태를 입력할 수 있습니다. 데이터 파이프라인에서 동시에 활성화 된 메시지의 수를 제한 하려면 예를 들어, 세마포, 조정 메커니즘을 사용할 수 있습니다.

다음 기본 예제에서는 세마포를 사용 하 여 데이터 파이프라인에서 메시지의 수를 제한 하는 방법에 설명 합니다. 데이터 파이프라인 사용 합니다 [concurrency:: wait](reference/concurrency-namespace-functions.md#wait) 적어도 100 시간 (밀리초)을 사용 하는 작업을 시뮬레이션 하는 함수입니다. 보낸 사람에 게 메시지를 소비자는 해당 메시지를 처리할 수 있는 보다 빠르게 생성 하기 때문에이 예제에서는 정의 `semaphore` 클래스를 사용 하는 응용 프로그램을 활성 메시지 수를 제한 합니다.

[!code-cpp[concrt-message-throttling#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-asynchronous-agents-library_2.cpp)]

`semaphore` 개체 동시에 최대 두 개의 메시지를 처리 하는 파이프라인을 제한 합니다.

이 예제에서 생산자는 소비자에 게 비교적 적은 메시지를 보냅니다. 따라서이 예제에서는 잠재적인 메모리 부족 또는 메모리 부족 조건을 보여 주지 않습니다. 그러나이 메커니즘은 데이터 파이프라인을 상대적으로 많은 수의 메시지를 포함 하는 경우 유용 합니다.

이 예제에서 사용 되는 세마포 클래스를 만드는 방법에 대 한 자세한 내용은 참조 하세요. [방법: 상황에 맞는 클래스를 사용 하 여 공동 작업 세마포 구현](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)합니다.

[[맨 위로 이동](#top)]

##  <a name="fine-grained"></a> 데이터 파이프라인에서 세분화 된 작업을 수행 하지 않습니다

에이전트 라이브러리 데이터 파이프라인에서 수행 되는 작업은 매우 정교 하지 않은 경우에 가장 유용 합니다. 예를 들어, 하나의 응용 프로그램 구성 요소 파일 또는 네트워크 연결에서 데이터 읽기 및 다른 구성 요소에 해당 데이터를 가끔씩 보낼 수 있습니다. 에이전트 라이브러리 메시지를 전파 하는 데 사용 하는 프로토콜에서 제공 하는 태스크 병렬 구문 보다 오버 헤드가 많이 발생 하는 메시지 전달 메커니즘을 발생 합니다 [병렬 패턴 라이브러리](../../parallel/concrt/parallel-patterns-library-ppl.md) (PPL). 따라서 데이터 파이프라인에서 수행 되는 작업을이 오버 헤드를 오프셋 하기에 충분히 길지 인지 해야 합니다.

데이터 파이프라인을 있지만 가장 효과적인 태스크가 정교 하지 않은 경우 데이터 파이프라인의 각 단계 더 세분화 된 작업을 수행 하려면 PPL 구문 예: 작업 그룹 및 병렬 알고리즘을 사용할 수 있습니다. 각 처리 단계에서 세부적인 병렬 처리를 사용 하는 정교 하지 않은 데이터 네트워크의 예제를 참조 하세요. [연습: 이미지 처리 네트워크 만들기](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)합니다.

[[맨 위로 이동](#top)]

##  <a name="large-payloads"></a> 값으로 큰 메시지 페이로드를 전달 하지 마십시오

일부 경우에는 런타임 메시지 버퍼에서 다른 메시지 버퍼에 전달 하는 모든 메시지의 복사본을 만듭니다. 예를 들어 합니다 [concurrency:: overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) 클래스는 각 대상에는 수신 하는 모든 메시지의 복사본을 제공 합니다. 와 같은 메시지 전달 함수를 사용 하는 경우 또한 메시지 데이터의 복사본을 만듭니다 런타임에서 [concurrency:: send](reference/concurrency-namespace-functions.md#send) 하 고 [concurrency:: receive](reference/concurrency-namespace-functions.md#receive) 메시지에서 메시지를 읽고 메시지를 쓰는 데 버퍼입니다. 이 메커니즘을 사용 하면 공유 데이터를 쓰는 동시에 위험을 제거, 있지만 메시지 페이로드 비교적 큰 경우 메모리 성능이 저하 발생할 수 있습니다.

포인터를 사용할 수 있고 메시지를 전달할 때 메모리 성능 개선에 대 한 참조는 대용량 페이로드. 다음 예제에서는 동일한 메시지 유형으로 포인터를 전달 하는 값으로 전달 큰 메시지를 비교 합니다. 이 예제에서는 두 개의 에이전트 형식 정의 `producer` 하 고 `consumer`에서 작동 하는 `message_data` 개체입니다. 이 예제에서는 여러 보낼 생산자에 필요한 시간을 비교 `message_data` 개체에 대 한 여러 포인터를 보내도록 생산자 에이전트에 필요한 시간에 소비자에 게 `message_data` 소비자에 게는 개체입니다.

[!code-cpp[concrt-message-payloads#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-asynchronous-agents-library_3.cpp)]

이 예제는 다음 예제 출력을 생성합니다.

```Output
Using message_data...
took 437ms.
Using message_data*...
took 47ms.
```

포인터를 사용 하는 버전의 전체 복사본을 만드는 런타임에 대 한 요구 사항을 제거 하기 때문에 더 잘 수행 모든 `message_data` 생산자에서 소비자에 게 전달 하는 개체입니다.

[[맨 위로 이동](#top)]

##  <a name="ownership"></a> 데이터 네트워크 경우 소유권은 정의 되지 않은 shared_ptr 사용

메시지 전달 파이프라인 또는 네트워크를 통해 포인터에 의해 메시지를 보낼 때 일반적으로 네트워크의 맨 앞에 각 메시지에 대 한 메모리를 할당 및 네트워크의 끝에 해당 메모리를 확보 합니다. 이 메커니즘 자주 작동 하지만 어려운 또는 사용 하는 것이 불가능 한 경우가 있습니다. 예를 들어, 데이터 네트워크에 여러 최종 노드가 포함 되어 있는 경우를 것이 좋습니다. 이 경우에 위치가 없습니다의 선택을 취소 메시지에 대 한 메모리를 해제 합니다.

이 문제를 해결 하기 위해 사용할 수 하는 메커니즘을 예를 들어 [std:: shared_ptr](../../standard-library/shared-ptr-class.md), 수 있도록 하는 여러 구성 요소에서 소유할 수에 대 한 포인터입니다. 때 최종 `shared_ptr` 리소스를 소유 하는 개체 삭제 되 면 리소스가 해제도 됩니다.

다음 예제에 사용 하는 방법을 보여 줍니다. `shared_ptr` 여러 메시지 버퍼에서 포인터 값을 공유 합니다. 이 예제에서는 연결을 [concurrency:: overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) 3 개체 [concurrency:: call](../../parallel/concrt/reference/call-class.md) 개체입니다. `overwrite_buffer` 클래스에는 각 대상에 메시지를 제공 합니다. 이 예제에서는 데이터 네트워크 끝날 때 데이터의 여러 소유자 이기 때문에 `shared_ptr` 각를 사용 하도록 설정 하려면 `call` 메시지의 소유권을 공유 하는 개체입니다.

[!code-cpp[concrt-message-sharing#1](../../parallel/concrt/codesnippet/cpp/best-practices-in-the-asynchronous-agents-library_4.cpp)]

이 예제는 다음 예제 출력을 생성합니다.

```Output
Creating resource 42...
receiver1: received resource 42
Creating resource 64...
receiver2: received resource 42
receiver1: received resource 64
Destroying resource 42...
receiver2: received resource 64
Destroying resource 64...
```

## <a name="see-also"></a>참고자료

[동시성 런타임 유용한 정보](../../parallel/concrt/concurrency-runtime-best-practices.md)<br/>
[비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[연습: 에이전트 기반 애플리케이션 만들기](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)<br/>
[연습: 데이터 흐름 에이전트 만들기](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)<br/>
[연습: 이미지 처리 네트워크 만들기](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)<br/>
[병렬 패턴 라이브러리의 유용한 정보](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md)<br/>
[동시성 런타임의 유용한 일반 정보](../../parallel/concrt/general-best-practices-in-the-concurrency-runtime.md)
