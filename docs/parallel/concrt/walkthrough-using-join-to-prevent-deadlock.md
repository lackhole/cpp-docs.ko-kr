---
title: '연습: 교착 상태 방지 조인을 사용 하 여'
ms.date: 04/25/2019
helpviewer_keywords:
- preventing deadlock with joins [Concurrency Runtime]
- deadlock, preventing [Concurrency Runtime]
- non-greedy joins, example
- join class, example
ms.assetid: d791f697-bb93-463e-84bd-5df1651b7446
ms.openlocfilehash: 2f9e0f50866ed0635fbaa4b700dbf522f09458d9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407905"
---
# <a name="walkthrough-using-join-to-prevent-deadlock"></a>연습: 교착 상태 방지 조인을 사용 하 여

이 항목에서는 사용 하는 방법을 보여 주기 위해 철학자 만찬 문제를 사용 합니다 [concurrency:: join](../../parallel/concrt/reference/join-class.md) 응용 프로그램에서 교착 상태를 방지 하는 클래스입니다. 소프트웨어 애플리케이션에서 *교착 상태*는 두 개 이상의 프로세스가 각각 리소스를 보유하고 함께 다른 프로세스가 다른 리소스를 해제할 때까지 대기하는 경우 발생합니다.

식당 철학자 문제는 일반 리소스 집합을 여러 개의 동시 프로세스 간에 공유 되는 경우 발생할 수 있는 문제 집합의 특정 예제.

## <a name="prerequisites"></a>전제 조건

이 연습을 시작 하기 전에 다음 항목을 읽어보세요.

- [비동기 에이전트](../../parallel/concrt/asynchronous-agents.md)

- [연습: 에이전트 기반 애플리케이션 만들기](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)

- [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)

- [메시지 전달 함수](../../parallel/concrt/message-passing-functions.md)

- [동기화 데이터 구조](../../parallel/concrt/synchronization-data-structures.md)

##  <a name="top"></a> 섹션

이 연습에는 다음과 같은 섹션이 있습니다.

- [철학자 만찬 문제](#problem)

- [간단한 구현](#deadlock)

- [교착 상태 방지 조인을 사용 하 여](#solution)

##  <a name="problem"></a> 철학자 만찬 문제

식당 철학자 문제가 응용 프로그램에서 교착 상태가 발생 하는 방법을 보여 줍니다. 이 문제가 5 철학자 라운드 테이블에 배치 합니다. 모든 철학자 생각과 식사 간에 대체 합니다. 왼쪽을 인접 한 항목을 사용 하 여 모든 철학자 젓가락을 공유 해야 사람과 오른쪽에 있습니다. 다음 그림에서는이 레이아웃을 보여 줍니다.

![식당 철학자 문제가](../../parallel/concrt/media/dining_philosophersproblem.png "만찬 철학자 문제")

식사를 철학자 두 젓가락 보유 해야 합니다. 모든 철학자 하나만 젓가락을 보유 하 고 다른 기다리고 음식을 먹을 수 다음 및 모든 고갈.

[[맨 위로 이동](#top)]

##  <a name="deadlock"></a> 간단한 구현

다음 예제에서는 식당 철학자 문제의 한 간단한 구현을 보여 줍니다. 합니다 `philosopher` 클래스에서 파생 되는 [concurrency:: agent](../../parallel/concrt/reference/agent-class.md), 각 철학자가 독립적으로 작동할 수 있습니다. 이 예제에서는 사용의 공유 배열을 [concurrency:: critical_section](../../parallel/concrt/reference/critical-section-class.md) 각 개체 `philosopher` 개체 젓가락 쌍에 단독으로 액세스 합니다.

그림 구현의 관계를 설정 하는 `philosopher` 한 철학자 클래스를 나타냅니다. `int` 변수 각 젓가락을 나타냅니다. `critical_section` 개체 소유자는 젓가락 rest 역할도 합니다. `run` 메서드 철학자 기간을 시뮬레이션 합니다. 합니다 `think` 생각의 동작을 시뮬레이션 하는 메서드 및 `eat` 메서드는 먹는 동작을 시뮬레이션 합니다.

A `philosopher` 개체를 모두 잠급니다 `critical_section` 젓가락 전에 소유자에서 제거를 시뮬레이션 하기 위해 호출 개체는 `eat` 메서드. 호출한 후 `eat`의 `philosopher` 개체의 소유자를 설정 하 여 젓가락을 반환 합니다 `critical_section` 개체 잠금 해제 된 상태를 다시 합니다.

`pickup_chopsticks` 교착 상태가 발생할 수 있는 메서드를 보여 줍니다. 모든 경우 `philosopher` 개체 잠금 중 하나를 없음에 대 한 액세스 권한을 얻습니다 `philosopher` 다른 잠금을 다른 제어 되므로 개체가 계속 해 서 `philosopher` 개체입니다.

## <a name="example"></a>예제

### <a name="description"></a>설명

### <a name="code"></a>코드

[!code-cpp[concrt-philosophers-deadlock#1](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_1.cpp)]

## <a name="compiling-the-code"></a>코드 컴파일

예제 코드를 복사하여 Visual Studio 프로젝트 또는 `philosophers-deadlock.cpp` 파일에 붙여넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.

**cl.exe /EHsc philosophers-deadlock.cpp**

[[맨 위로 이동](#top)]

##  <a name="solution"></a> 교착 상태 방지 조인을 사용 하 여

이 섹션에서는 교착 상태가 발생할 가능성을 제거 하려면 메시지 버퍼 및 메시지 전달 함수를 사용 하는 방법을 보여 줍니다.

이 예제에서는 이전에 연결 하는 `philosopher` 클래스 대신 각 `critical_section` 사용 하 여 개체를 [concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) 개체 및 `join` 개체입니다. `join` 개체는 중재자 젓가락 철학자를 제공 하는 역할도 합니다.

이 예제에서는 합니다 `unbounded_buffer` 대상에서 메시지를 수신 하는 경우 하기 때문에 클래스를 `unbounded_buffer` 개체는 메시지가 메시지 큐에서 제거 됩니다. 그러면는 `unbounded_buffer` 에서 젓가락 나타내는 메시지를 보유 하는 개체를 사용할 수 있습니다. `unbounded_buffer` 없는 메시지를 보유 하는 개체에서 젓가락 사용 되 고 있음을 나타냅니다.

이 예제에서는 non-greedy `join` non-greedy 조인 하면 각 개체 `philosopher` 젓가락 모두에 대 한 액세스를 개체 경우에만 둘 다 `unbounded_buffer` 개체는 메시지를 포함 합니다. Greedy 조인 greedy 조인 가능 하 게 하는 즉시 메시지를 수락 하기 때문에 교착 상태를 방지 하지 못합니다. 모든 탐욕 적 경우 교착 상태가 발생할 수 있습니다 `join` 개체 메시지 중 하나가 수신 하지만 사용할 수 있으려면 다른 무기한 대기 합니다.

Greedy 및 non-greedy 조인 및 다양 한 메시지 버퍼 유형 간의 차이점에 대 한 자세한 내용은 참조 하세요. [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)합니다.

#### <a name="to-prevent-deadlock-in-this-example"></a>이 예제에서 교착 상태를 방지 하려면

1. 이 예제에서 다음 코드를 제거 합니다.

[!code-cpp[concrt-philosophers-deadlock#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_2.cpp)]

1. 형식을 변경 합니다 `_left` 및 `_right` 의 데이터 멤버는 `philosopher` 클래스를 `unbounded_buffer`입니다.

[!code-cpp[concrt-philosophers-join#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_3.cpp)]

1. 수정 된 `philosopher` 되려면 생성자 `unbounded_buffer` 개체를 매개 변수로 합니다.

[!code-cpp[concrt-philosophers-join#3](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_4.cpp)]

1. 수정 합니다 `pickup_chopsticks` 메서드를 사용 하 여 non-greedy `join` 젓가락 모두에 대 한 메시지 버퍼에서 메시지를 수신 하는 개체입니다.

[!code-cpp[concrt-philosophers-join#4](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_5.cpp)]

1. 수정 된 `putdown_chopsticks` 젓가락 모두에 대 한 메시지 버퍼에 메시지를 전송 하 여 젓가락에 대 한 액세스를 해제 하는 방법입니다.

[!code-cpp[concrt-philosophers-join#5](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_6.cpp)]

1. 수정 합니다 `run` 결과 저장 하는 방법을 `pickup_chopsticks` 메서드 및 해당 결과를 전달 하는 `putdown_chopsticks` 메서드.

[!code-cpp[concrt-philosophers-join#6](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_7.cpp)]

1. 선언을 수정 합니다 `chopsticks` 변수를 `wmain` 함수가 배열을 `unbounded_buffer` 하나의 메시지를 보관 하는 각 개체.

[!code-cpp[concrt-philosophers-join#7](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_8.cpp)]

## <a name="example"></a>예제

### <a name="description"></a>설명

다음은 완성 된 예제는 탐욕 적이 아닌 `join` 교착 상태의 위험이 제거 하는 개체입니다.

### <a name="code"></a>코드

[!code-cpp[concrt-philosophers-join#1](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_9.cpp)]

### <a name="comments"></a>설명

이 예제의 결과는 다음과 같습니다.

```Output
aristotle ate 50 times.
descartes ate 50 times.
hobbes ate 50 times.
socrates ate 50 times.
plato ate 50 times.
```

## <a name="compiling-the-code"></a>코드 컴파일

예제 코드를 복사하여 Visual Studio 프로젝트 또는 `philosophers-join.cpp` 파일에 붙여넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.

**cl.exe /EHsc philosophers-join.cpp**

[[맨 위로 이동](#top)]

## <a name="see-also"></a>참고자료

[동시성 런타임 연습](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[비동기 에이전트](../../parallel/concrt/asynchronous-agents.md)<br/>
[비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[메시지 전달 함수](../../parallel/concrt/message-passing-functions.md)<br/>
[동기화 데이터 구조](../../parallel/concrt/synchronization-data-structures.md)
