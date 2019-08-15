---
title: '연습: COM 사용 응용 프로그램에서 동시성 런타임 사용'
ms.date: 04/25/2019
helpviewer_keywords:
- Concurrency Runtime, use with COM
- COM, use with the Concurrency Runtime
ms.assetid: a7c798b8-0fc8-4bee-972f-22ef158f7f48
ms.openlocfilehash: 23488522287ab5767c88cd3a3e90c09392634f46
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69512105"
---
# <a name="walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application"></a>연습: COM 사용 응용 프로그램에서 동시성 런타임 사용

이 문서에서는 COM (구성 요소 개체 모델)을 사용 하는 응용 프로그램에서 동시성 런타임를 사용 하는 방법을 보여 줍니다.

## <a name="prerequisites"></a>전제 조건

이 연습을 시작 하기 전에 다음 문서를 읽어 보세요.

- [작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)

- [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)

- [비동기 에이전트](../../parallel/concrt/asynchronous-agents.md)

- [예외 처리](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)

COM에 대한 자세한 내용은 [구성 요소 개체 모델(COM)](/windows/win32/com/component-object-model--com--portal)을 참조합니다.

## <a name="managing-the-lifetime-of-the-com-library"></a>COM 라이브러리의 수명 관리

동시성 런타임와 함께 COM을 사용 하는 것은 다른 동시성 메커니즘과 동일한 원칙을 따르며 이러한 라이브러리를 효과적으로 사용 하는 데 도움이 될 수 있는 지침은 다음과 같습니다.

- 스레드는 COM 라이브러리를 사용 하기 전에 [CoInitializeEx](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex) 를 호출 해야 합니다.

- 스레드는 모든 호출 `CoInitializeEx` 에 동일한 인수를 제공 하는 한 여러 번 호출할 수 있습니다.

- 에 `CoInitializeEx`대 한 각 호출에 대해 스레드가 [CoUninitialize](/windows/win32/api/combaseapi/nf-combaseapi-couninitialize)도 호출 해야 합니다. 즉, 및에 대 `CoInitializeEx` 한 `CoUninitialize` 호출은 균형을 맞춰야 합니다.

- 스레드 아파트 간에 전환 하려면 스레드가 새 스레딩 사양을 사용 하 여를 호출 `CoInitializeEx` 하기 전에 COM 라이브러리를 완전히 해제 해야 합니다.

다른 COM 원칙은 동시성 런타임와 함께 COM을 사용 하는 경우에 적용 됩니다. 예를 들어 STA (단일 스레드 아파트)에서 개체를 만들고 해당 개체를 다른 아파트로 마샬링하는 응용 프로그램은 메시지 루프를 제공 하 여 들어오는 메시지를 처리 해야 합니다. 또한 아파트 간에 개체를 마샬링하면 성능이 저하 될 수 있습니다.

### <a name="using-com-with-the-parallel-patterns-library"></a>병렬 패턴 라이브러리와 함께 COM 사용

작업 그룹 또는 병렬 알고리즘과 같은 PPL (병렬 패턴 라이브러리)의 구성 요소와 함께 com을 사용 하는 경우 각 작업 또는 반복 `CoInitializeEx` 중에 com 라이브러리를 사용 하기 전에를 호출 `CoUninitialize` 하 고 각 작업이 나 반복이 완료 되기 전에를 호출 합니다. . 다음 예제에서는 [concurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) 개체를 사용 하 여 COM 라이브러리의 수명을 관리 하는 방법을 보여 줍니다.

[!code-cpp[concrt-parallel-scripts#1](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_1.cpp)]

작업 또는 병렬 알고리즘이 취소 되거나 작업 본문에서 예외를 throw 하는 경우 COM 라이브러리가 올바르게 해제 되었는지 확인 해야 합니다. 태스크가 종료 되기 전에 호출 `CoUninitialize` 되도록 하려면 `try-finally` 블록 또는 RAII ( *리소스 획득 시 초기화* ) 패턴을 사용 합니다. 다음 예제에서는 `try-finally` 블록을 사용 하 여 작업이 완료 되거나 취소 되거나 예외가 throw 될 때 COM 라이브러리를 해제 합니다.

[!code-cpp[concrt-parallel-scripts#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_2.cpp)]

다음 예제에서는 RAII 패턴을 사용 하 여 지정 `CCoInitializer` 된 범위에서 COM 라이브러리의 수명을 관리 하는 클래스를 정의 합니다.

[!code-cpp[concrt-parallel-scripts#3](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_3.cpp)]

다음과 같이 `CCoInitializer` 클래스를 사용 하 여 태스크가 종료 될 때 자동으로 COM 라이브러리를 해제할 수 있습니다.

[!code-cpp[concrt-parallel-scripts#4](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_4.cpp)]

동시성 런타임 취소에 대 한 자세한 내용은 [PPL에서의 취소](cancellation-in-the-ppl.md)를 참조 하세요.

### <a name="using-com-with-asynchronous-agents"></a>비동기 에이전트와 함께 COM 사용

비동기 에이전트와 함께 com을 사용 하는 `CoInitializeEx` 경우 에이전트에 대 한 [concurrency:: agent:: run](reference/agent-class.md#run) 메서드에서 com 라이브러리를 사용 하기 전에를 호출 합니다. 그런 다음 `CoUninitialize` `run` 메서드가 반환 되기 전에를 호출 합니다. 에이전트의 생성자 또는 소멸자에서 COM 관리 루틴을 사용 하지 말고, [concurrency:: agent:: start](reference/agent-class.md#start) 또는 [concurrency:: agent::d 한](reference/agent-class.md#done) 메서드 를재정의하지마십시오.`run` 메서드.

다음 예제에서는 `run` 메서드의 COM 라이브러리를 관리 하는 `CCoAgent`이라는 기본 에이전트 클래스를 보여 줍니다.

[!code-cpp[concrt-parallel-scripts#5](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_5.cpp)]

전체 예제는이 연습의 뒷부분에서 제공 됩니다.

### <a name="using-com-with-lightweight-tasks"></a>간단한 작업에서 COM 사용

문서 [작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md) 동시성 런타임에서 간단한 작업의 역할을 설명 합니다. Windows API에서 `CreateThread` 함수에 전달 하는 스레드 루틴의 경우와 마찬가지로 간단한 작업으로 COM을 사용할 수 있습니다. 다음 예제에서 이를 확인할 수 있습니다.

[!code-cpp[concrt-parallel-scripts#6](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_6.cpp)]

## <a name="an-example-of-a-com-enabled-application"></a>COM 사용 응용 프로그램의 예

이 섹션에서는 인터페이스를 `IScriptControl` 사용 하 여 n<sup>번째</sup> 피보나치 수를 계산 하는 스크립트를 실행 하는 전체 COM 사용 응용 프로그램을 보여 줍니다. 이 예에서는 먼저 주 스레드에서 스크립트를 호출한 다음 PPL 및 에이전트를 사용 하 여 스크립트를 동시에 호출 합니다.

개체의 프로시저를 호출 하 `RunScriptProcedure`는 다음과 같은 도우미 함수를 살펴보겠습니다. `IScriptControl`

[!code-cpp[concrt-parallel-scripts#7](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_7.cpp)]

함수 `wmain` `IScriptControl` 는 개체를 만들고 n<sup>번째</sup> `RunScriptProcedure` 피보나치 수를 계산 하는 스크립트 코드를 추가한 다음 함수를 호출 하 여 해당 스크립트를 실행 합니다.

[!code-cpp[concrt-parallel-scripts#8](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_8.cpp)]

### <a name="calling-the-script-from-the-ppl"></a>PPL에서 스크립트 호출

다음 함수 `ParallelFibonacci`는 [동시성::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) 알고리즘을 사용 하 여 스크립트를 병렬로 호출 합니다. 이 함수는 `CCoInitializer` 클래스를 사용 하 여 작업을 반복할 때마다 COM 라이브러리의 수명을 관리 합니다.

[!code-cpp[concrt-parallel-scripts#9](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_9.cpp)]

예제에서 `ParallelFibonacci` 함수를 사용 하려면 함수에서 `wmain` 를 반환 하기 전에 다음 코드를 추가 합니다.

[!code-cpp[concrt-parallel-scripts#10](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_10.cpp)]

### <a name="calling-the-script-from-an-agent"></a>에이전트에서 스크립트 호출

다음 예에서는 n `FibonacciScriptAgent` <sup>번째</sup> 피보나치 수를 계산 하는 스크립트 프로시저를 호출 하는 클래스를 보여 줍니다. 클래스 `FibonacciScriptAgent` 는 메시지 전달을 사용 하 여 주 프로그램에서 스크립트 함수에 대 한 입력 값을 받습니다. 메서드 `run` 는 작업 전체에서 COM 라이브러리의 수명을 관리 합니다.

[!code-cpp[concrt-parallel-scripts#11](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_11.cpp)]

다음 함수 `AgentFibonacci`는 여러 `FibonacciScriptAgent` 개체를 만들고 메시지 전달을 사용 하 여 이러한 개체에 여러 입력 값을 보냅니다.

[!code-cpp[concrt-parallel-scripts#12](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_12.cpp)]

예제에서 `AgentFibonacci` 함수를 사용 하려면 함수에서 `wmain` 를 반환 하기 전에 다음 코드를 추가 합니다.

[!code-cpp[concrt-parallel-scripts#13](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_13.cpp)]

### <a name="the-complete-example"></a>전체 예제

다음 코드에서는 병렬 알고리즘과 비동기 에이전트를 사용 하 여 피보나치 숫자를 계산 하는 스크립트 프로시저를 호출 하는 전체 예제를 보여 줍니다.

[!code-cpp[concrt-parallel-scripts#14](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_14.cpp)]

예제에서는 다음과 같은 샘플 출력을 생성 합니다.

```Output
Main Thread:
fib(15) = 610

Parallel Fibonacci:
fib(15) = 610
fib(10) = 55
fib(16) = 987
fib(18) = 2584
fib(11) = 89
fib(17) = 1597
fib(19) = 4181
fib(12) = 144
fib(13) = 233
fib(14) = 377

Agent Fibonacci:
fib(30) = 832040
fib(22) = 17711
fib(10) = 55
fib(12) = 144
```

## <a name="compiling-the-code"></a>코드 컴파일

예제 코드를 복사하여 Visual Studio 프로젝트 또는 `parallel-scripts.cpp` 파일에 붙여넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.

**cl.exe/EHsc parallel-scripts/link ole32.lib**

## <a name="see-also"></a>참고자료

[동시성 런타임 연습](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)<br/>
[비동기 에이전트](../../parallel/concrt/asynchronous-agents.md)<br/>
[예외 처리](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)<br/>
[PPL에서의 취소](cancellation-in-the-ppl.md)<br/>
[작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)
