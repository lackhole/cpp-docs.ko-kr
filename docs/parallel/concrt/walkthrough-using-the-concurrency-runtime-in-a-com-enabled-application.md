---
title: '연습: COM 사용 응용 프로그램에서 동시성 런타임 사용'
ms.date: 04/25/2019
helpviewer_keywords:
- Concurrency Runtime, use with COM
- COM, use with the Concurrency Runtime
ms.assetid: a7c798b8-0fc8-4bee-972f-22ef158f7f48
ms.openlocfilehash: 9d306377be4a000c54fb5556b15263a15b2d4618
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407786"
---
# <a name="walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application"></a>연습: COM 사용 응용 프로그램에서 동시성 런타임 사용

이 문서에는 구성 요소 개체 모델 (COM)를 사용 하는 응용 프로그램에서 동시성 런타임을 사용 하는 방법을 보여 줍니다.

## <a name="prerequisites"></a>전제 조건

이 연습을 시작 하기 전에 다음 문서를 읽어 보십시오.

- [작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)

- [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)

- [비동기 에이전트](../../parallel/concrt/asynchronous-agents.md)

- [예외 처리](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)

COM에 대 한 자세한 내용은 참조 하세요. [구성 요소 개체 모델 (COM)](/windows/desktop/com/component-object-model--com--portal)합니다.

## <a name="managing-the-lifetime-of-the-com-library"></a>COM 라이브러리의 수명 관리

동시성 런타임과 함께 COM 사용할 다른 동시성 메커니즘으로 동일한 원칙을 따릅니다를 있지만 효과적으로 이러한 라이브러리를 함께 사용 하 여 다음 지침 도움이 됩니다.

- 스레드에서 호출 해야 [CoInitializeEx](/windows/desktop/api/combaseapi/nf-combaseapi-coinitializeex) COM 라이브러리를 사용 하기 전에 합니다.

- 스레드에서 호출 수 `CoInitializeEx` 여러 번으로 모든 호출에 동일한 인수를 제공 합니다.

- 호출할 때마다 `CoInitializeEx`, 스레드도 호출 해야 합니다 [CoUninitialize](/windows/desktop/api/combaseapi/nf-combaseapi-couninitialize)합니다. 즉, 호출 `CoInitializeEx` 고 `CoUninitialize` 분산 되어야 합니다.

- 으로 전환 하려면 하나의 스레드 아파트에서 다른 스레드 완전히 해제 해야 COM 라이브러리를 호출 하기 전에 `CoInitializeEx` 새 사양을 스레딩 합니다.

다른 COM 원칙이 COM 동시성 런타임과 함께 사용 하는 경우에 적용 됩니다. 예를 들어, 응용 프로그램 (STA) 단일 스레드 아파트에서 개체를 만들고 다른 아파트에 개체를 마샬링하는 들어오는 메시지를 처리 하는 메시지 루프도 제공 해야 합니다. 또한 개체 간의 아파트 마샬링 성능이 저하 될 수 해야 합니다.

### <a name="using-com-with-the-parallel-patterns-library"></a>COM을 사용 하 여 병렬 패턴 라이브러리를 사용 하 여

COM 구성 요소에 라이브러리 PPL (병렬 패턴), 예를 들어 작업 그룹 또는 병렬 알고리즘을 사용 하는 경우 호출 `CoInitializeEx` 각 태스크 및 반복 호출 하는 동안 COM 라이브러리를 사용 하기 전에 `CoUninitialize` 각 태스크 나 반복 완료 되기 전에 . 다음 예제에서는 사용 하 여 COM 라이브러리의 수명을 관리 하는 방법을 보여 줍니다는 [concurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) 개체입니다.

[!code-cpp[concrt-parallel-scripts#1](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_1.cpp)]

작업 본문 예외를 throw 하면 작업 또는 병렬 알고리즘 취소 될 때 또는 COM 라이브러리 올바로 해제 확인 해야 합니다. 태스크 수 있도록 보장 하기 위해 호출 `CoUninitialize` 사용 하 여 종료 되기 전에 `try-finally` 블록 또는 *Resource Acquisition Is Initialization* (RAII) 패턴. 다음 예제에서는 `try-finally` 예외가 throw 되 면 작업이 완료 되거나 취소 될 때 또는 COM 라이브러리를 차단 합니다.

[!code-cpp[concrt-parallel-scripts#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_2.cpp)]

다음 예제에서는 RAII 패턴을 사용 하 여 정의 된 `CCoInitializer` 지정된 된 범위에서 COM 라이브러리의 수명을 관리 하는 클래스입니다.

[!code-cpp[concrt-parallel-scripts#3](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_3.cpp)]

사용할 수는 `CCoInitializer` 클래스를 COM 라이브러리는 다음과 같은 작업 종료 시에 자동으로 해제 합니다.

[!code-cpp[concrt-parallel-scripts#4](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_4.cpp)]

동시성 런타임에서 취소에 대 한 자세한 내용은 참조 하세요. [PPL에서의 취소](cancellation-in-the-ppl.md)합니다.

### <a name="using-com-with-asynchronous-agents"></a>비동기 에이전트를 사용 하 여 COM을 사용 하 여

비동기 에이전트를 사용 하 여 COM을 사용 하는 경우 호출 `CoInitializeEx` 에서 COM 라이브러리를 사용 하기 전에 [concurrency::agent::run](reference/agent-class.md#run) 에이전트에 대해 메서드. 다음 호출 `CoUninitialize` 하기 전에 `run` 메서드 반환 합니다. COM 관리 루틴을 생성자 또는 소멸자는 에이전트를 사용 하지 않으며 재정의 하지 않으면 합니다 [concurrency::agent::start](reference/agent-class.md#start) 또는 [concurrency:: agent:: 수행](reference/agent-class.md#done) 메서드 이러한 메서드는 때문에 보다 다른 스레드에서 호출을 `run` 메서드.

다음 예제에서는 명명 된 기본 에이전트 클래스 `CCoAgent`에서 COM 라이브러리를 관리 하는 `run` 메서드.

[!code-cpp[concrt-parallel-scripts#5](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_5.cpp)]

전체 예제는이 연습의 뒷부분에서 제공 됩니다.

### <a name="using-com-with-lightweight-tasks"></a>COM을 사용 하 여 간단한 작업을 사용 하 여

문서 [작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md) 동시성 런타임에서 간단한 작업의 역할을 설명 합니다. 에 전달 하는 모든 스레드 루틴을 사용 하 여는 것 처럼 간단한 작업을 사용 하 여 COM을 사용할 수 있습니다는 `CreateThread` Windows api에서 함수입니다. 다음 예제에서 이를 확인할 수 있습니다.

[!code-cpp[concrt-parallel-scripts#6](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_6.cpp)]

## <a name="an-example-of-a-com-enabled-application"></a>COM 사용 응용 프로그램의 예

이 섹션에서는 전체 COM 사용 응용 프로그램을 사용 하 여 `IScriptControl` n을 계산 하는 스크립트를 실행 하는 인터페이스<sup>번째</sup> 피보나치 수. 이 예제에서는 먼저 기본 스레드에서 스크립트를 호출 하 고 PPL 및 에이전트를 사용 하 여 스크립트를 동시에 호출 합니다.

다음 도우미 함수를 살펴보세요 `RunScriptProcedure`에 프로시저를 호출 하는 `IScriptControl` 개체입니다.

[!code-cpp[concrt-parallel-scripts#7](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_7.cpp)]

`wmain` 함수를 만듭니다를 `IScriptControl` 개체, n을 계산 하는 스크립트 코드를 추가<sup>번째</sup> 피보나치 수를 차례로 호출 합니다 `RunScriptProcedure` 해당 스크립트를 실행할 함수입니다.

[!code-cpp[concrt-parallel-scripts#8](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_8.cpp)]

### <a name="calling-the-script-from-the-ppl"></a>PPL에서 스크립트를 호출합니다.

다음 함수를 `ParallelFibonacci`를 사용 합니다 [concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for) 병렬로 스크립트를 호출 하는 알고리즘입니다. 이 함수를 사용 합니다 `CCoInitializer` 작업의 모든 반복 하는 동안 COM 라이브러리의 수명을 관리 하는 클래스입니다.

[!code-cpp[concrt-parallel-scripts#9](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_9.cpp)]

사용 하는 `ParallelFibonacci` 예제를 사용 하 여 함수를 추가 하기 전에 다음 코드는 `wmain` 함수에서 반환 합니다.

[!code-cpp[concrt-parallel-scripts#10](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_10.cpp)]

### <a name="calling-the-script-from-an-agent"></a>에이전트에서 스크립트를 호출합니다.

다음 예제에서는 합니다 `FibonacciScriptAgent` n 계산 스크립트 프로시저를 호출 하는 클래스<sup>번째</sup> 피보나치 수입니다. `FibonacciScriptAgent` 클래스는 스크립트 함수에 값을 입력 하는 주 프로그램에서 수신 하는 전달할 메시지를 사용 합니다. `run` 메서드는 작업 전반에 걸쳐 COM 라이브러리의 수명을 관리 합니다.

[!code-cpp[concrt-parallel-scripts#11](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_11.cpp)]

다음 함수 `AgentFibonacci`를 여러 개 만들어 `FibonacciScriptAgent` 개체 및 해당 개체에 값을 입력 하는 여러 전송에 전달 하는 메시지를 사용 합니다.

[!code-cpp[concrt-parallel-scripts#12](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_12.cpp)]

사용 하는 `AgentFibonacci` 예제를 사용 하 여 함수를 추가 하기 전에 다음 코드는 `wmain` 함수에서 반환 합니다.

[!code-cpp[concrt-parallel-scripts#13](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_13.cpp)]

### <a name="the-complete-example"></a>전체 예제

다음 코드는 피보나치 수를 계산 하는 스크립트 프로시저를 호출 하려면 병렬 알고리즘 및 비동기 에이전트를 사용 하는 전체 예제를 보여 줍니다.

[!code-cpp[concrt-parallel-scripts#14](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_14.cpp)]

이 예제에서는 다음 샘플 출력을 생성합니다.

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

**cl.exe /EHsc 병렬 scripts.cpp /link ole32.lib**

## <a name="see-also"></a>참고자료

[동시성 런타임 연습](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)<br/>
[비동기 에이전트](../../parallel/concrt/asynchronous-agents.md)<br/>
[예외 처리](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)<br/>
[PPL에서의 취소](cancellation-in-the-ppl.md)<br/>
[작업 스케줄러](../../parallel/concrt/task-scheduler-concurrency-runtime.md)
