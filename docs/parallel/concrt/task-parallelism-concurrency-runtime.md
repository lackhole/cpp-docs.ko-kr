---
title: 작업 병렬 처리(동시성 런타임)
ms.date: 11/04/2016
helpviewer_keywords:
- structured task groups [Concurrency Runtime]
- structured tasks [Concurrency Runtime]
- task groups [Concurrency Runtime]
- task parallelism
- tasks [Concurrency Runtime]
ms.assetid: 42f05ac3-2098-494a-ba84-737fcdcad077
ms.openlocfilehash: c9f18dfd1498538ce3700fd73a27ce6f6088ee42
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180045"
---
# <a name="task-parallelism-concurrency-runtime"></a>작업 병렬 처리(동시성 런타임)

동시성 런타임에서 *태스크* 단위 특정 작업을 수행 하 고 일반적으로 다른 작업과 병렬로 실행 하는 작업입니다. 태스크로 구성 된 보다 세분화 된 추가 작업으로 분해할 수를 *작업 그룹*합니다.

비동기 코드를 작성할 때 비동기 작업이 완료된 후 일부 작업이 발생되도록 하려는 경우 작업을 사용합니다. 예를 들어 파일에서 비동기적으로 읽은 다음 다른 작업을 사용 하는 작업을 사용할 수 있습니다-를 *연속 작업*,이 문서의 뒷부분에 설명 되어 있는-사용할 수 있게 데이터를 처리 하는 데 있습니다. 반대로 작업 그룹을 사용하여 병렬 작업을 더 작은 부분으로 분해할 수 있습니다. 예를 들어 남은 작업을 두 파티션으로 분할하는 재귀 알고리즘이 있다고 가정합니다. 작업 그룹을 사용하여 이러한 파티션을 동시에 실행한 다음 분할된 작업이 완료될 때까지 기다릴 수 있습니다.

> [!TIP]
> 동시에 컬렉션의 모든 요소에 동일한 루틴을 적용 하려는 경우 병렬 알고리즘을 사용과 같은 [concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for), 작업 또는 작업 그룹을 대신 합니다. 병렬 알고리즘에 대 한 자세한 내용은 참조 하세요. [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)합니다.

## <a name="key-points"></a>주요 사항

- 변수를 참조로 람다 식에 전달하는 경우 작업이 완료될 때까지 해당 변수의 수명이 유지되도록 보장해야 합니다.

- 작업을 사용 하 여 (합니다 [concurrency:: task](../../parallel/concrt/reference/task-class.md) 클래스) 비동기 코드를 작성 하는 경우. 작업 클래스는 동시성 런타임이 아닌 Windows 스레드 풀을 해당 스케줄러로 사용합니다.

- 작업 그룹을 사용 하 여 (합니다 [concurrency:: task_group](reference/task-group-class.md) 클래스와 [concurrency:: parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) 알고리즘) 병렬 작업을 더 작은 부분으로 분해 하 고 다음 이러한 작은 대 한 대기 하려는 경우 부분이 완료 합니다.

- 사용 된 [concurrency::task::then](reference/task-class.md#then) 연속을 만드는 방법. A *연속* 다른 작업이 완료 된 후 비동기적으로 실행 되는 작업입니다. 많은 연속을 연결하여 비동기 작업의 체인을 구성할 수 있습니다.

- 작업 기반 연속은 선행 작업이 취소되거나 예외를 throw하는 경우에도 선행 작업이 완료되면 항상 실행되도록 예약됩니다.

- 사용 하 여 [concurrency:: when_all](reference/concurrency-namespace-functions.md#when_all) 작업 집합의 모든 멤버가 완료 된 후 완료 되는 작업을 만들려고 합니다. 사용 하 여 [concurrency:: when_any](reference/concurrency-namespace-functions.md#when_any) 작업 집합의 한 멤버가 완료 된 후 완료 되는 작업을 만들려고 합니다.

- 작업 및 작업 그룹은 PPL(병렬 패턴 라이브러리) 취소 메커니즘에 참여할 수 있습니다. 자세한 내용은 [PPL에서의 취소](cancellation-in-the-ppl.md)합니다.

- 런타임에서 작업 및 작업 그룹에서 throw 된 예외를 처리 하는 방법에 대해 알아보려면 [예외 처리](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)합니다.

## <a name="in-this-document"></a>이 문서에서 다루는 내용

- [람다 식 사용](#lambdas)

- [작업 클래스](#task-class)

- [연속 작업](#continuations)

- [값 기반 연속 작업을 기반으로 비교](#value-versus-task)

- [작업 작성](#composing-tasks)

    - [When_all 함수](#when-all)

    - [When_any 함수](#when-any)

- [지연 된 작업 실행](#delayed-tasks)

- [작업 그룹](#task-groups)

- [Task_group과 structured_task_group 비교](#comparing-groups)

- [예제](#example)

- [강력한 프로그래밍](#robust)

##  <a name="lambdas"></a> 람다 식 사용

간결한 구문으로 인해 람다 식은 작업 및 작업 그룹에서 수행하는 작업을 정의하는 일반적인 방법입니다. 다음은 몇 가지 사용 팁입니다.

- 작업은 일반적으로 백그라운드 스레드에서 실행되므로 람다 식에서 변수를 캡처할 때 개체 수명을 알아 두어야 합니다. 변수를 값으로 캡처하면 해당 변수의 복사본이 람다 본문에 생성됩니다. 참조로 캡처하면 복사본이 생성되지 않습니다. 따라서 참조로 캡처하는 모든 변수의 수명은 해당 변수를 사용하는 작업보다 길어야 합니다.

- 람다 식을 작업에 전달할 때는 스택에서 참조로 할당되는 변수를 캡처하지 마세요.

- 값으로 캡처하는 항목과 참조로 캡처하는 항목을 식별할 수 있도록 람다 식에서 캡처하는 변수를 명시적으로 지정해야 합니다. 이러한 이유로 람다 식에는 `[=]` 또는 `[&]` 옵션을 사용하지 않는 것이 좋습니다.

일반적인 패턴은 연속 체인의 한 작업이 변수에 할당되면 다른 작업에서 해당 변수를 읽는 것입니다. 각 연속 작업에는 변수의 다양한 복사본이 저장되므로 값으로 캡처할 수 없습니다. 스택 할당 변수의 경우 변수가 더 이상 유효하지 않으므로 참조로도 캡처할 수 없습니다.

이 문제를 해결 하기 위해 사용 하 여 스마트 포인터와 같은 [std:: shared_ptr](../../standard-library/shared-ptr-class.md)변수를 래핑하고 스마트 포인터 값별로 전달 하려면, 합니다. 이런 식으로 기본 개체는 할당되고 읽을 수 있으며 해당 개체를 사용하는 작업보다 수명이 깁니다. 변수가 Windows 런타임 개체에 대한 포인터 또는 참조 개수가 계산되는 핸들(`^`)인 경우에도 이 기술을 사용합니다. 기본 예제는 다음과 같습니다.

[!code-cpp[concrt-lambda-task-lifetime#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_1.cpp)]

람다 식에 대한 자세한 내용은 [람다 식](../../cpp/lambda-expressions-in-cpp.md)을 참조하세요.

##  <a name="task-class"></a> 작업 클래스

사용할 수는 [concurrency:: task](../../parallel/concrt/reference/task-class.md) 종속 작업의 집합으로 작업을 구성 하는 클래스입니다. 이 컴퍼지션 모델 개념에서 지원 됩니다 *연속*합니다. 될 때 실행할 코드를 연속 수 앞에서 설명한 또는 *선행*, 작업이 완료 합니다. 선행 작업의 결과는 하나 이상의 연속 작업에 대한 입력으로 전달됩니다. 선행 작업이 완료되면 대기 중인 모든 연속 작업이 실행되도록 예약됩니다. 각 연속 작업은 선행 작업 결과의 복사본을 받습니다. 그런 다음 해당 연속 작업은 다른 연속의 선행 작업이 되어 작업 체인을 만들 수도 있습니다. 연속에서는 작업 간에 특정 종속성이 있는 임의 길이의 작업 체인을 만들 수 있습니다. 또한 작업은 작업이 시작되기 전에나 작업이 실행되는 동안 공동 작업 방식으로 취소에 참여할 수 있습니다. 이 취소 모델에 대 한 자세한 내용은 참조 하세요. [PPL에서의 취소](cancellation-in-the-ppl.md)합니다.

`task`는 템플릿 클래스입니다. 형식 매개 변수 `T`는 작업에 의해 생성되는 결과의 형식입니다. 작업에서 값을 반환하지 않는 경우 이 형식은 `void`일 수 있습니다. `T`는 `const` 한정자를 사용할 수 없습니다.

작업을 만들 때 제공 된 *작업 함수* 작업 본문을 수행 하는 합니다. 이 작업 함수는 람다 함수, 함수 포인터 또는 함수 개체의 형태로 제공됩니다. 작업이 결과 얻지 않고 완료 될 때까지 기다려야를 호출 합니다 [concurrency::task::wait](reference/task-class.md#wait) 메서드. 합니다 `task::wait` 메서드가 반환 되는 [concurrency:: task_status](reference/concurrency-namespace-enums.md#task_group_status) 작업이 완료 되거나 취소 여부를 나타내는 값입니다. 작업의 결과 가져오려면 호출 합니다 [concurrency::task::get](reference/task-class.md#get) 메서드. 이 메서드는 `task::wait`를 호출하여 작업이 완료될 때까지 기다리므로 결과를 사용할 수 있을 때까지 현재 스레드의 실행을 차단합니다.

다음 예제에서는 작업을 만들고 결과를 기다린 후 해당 값을 표시하는 방법을 보여 줍니다. 이 설명서의 예제에서는 더 간결한 구문을 제공하는 람다 함수를 사용합니다. 그러나 작업을 사용할 때는 함수 포인터 및 함수 개체를 사용할 수도 있습니다.

[!code-cpp[concrt-basic-task#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_2.cpp)]

사용 하는 경우는 [concurrency:: create_task](reference/concurrency-namespace-functions.md#create_task) 함수를 사용할 수는 `auto` 형식을 선언 하는 대신 키워드입니다. 예를 들어 항등 행렬을 만들고 인쇄하는 다음 코드를 살펴보겠습니다.

[!code-cpp[concrt-create-task#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_3.cpp)]

`create_task` 함수를 사용하여 동일한 작업을 만들 수 있습니다.

[!code-cpp[concrt-create-task#2](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_4.cpp)]

작업을 실행하는 동안 예외가 throw되면 런타임은 `task::get`이나 `task::wait` 또는 작업 기반 연속에 대한 후속 호출에서 해당 예외를 마샬링합니다. 작업 예외 처리 메커니즘에 대 한 자세한 내용은 참조 하세요. [예외 처리](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)합니다.

사용 하는 예로 `task`, [concurrency:: task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md), 취소 참조 [연습: 작업 및 XML HTTP 요청을 사용 하 여 연결](../../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)합니다. `task_completion_event` 클래스는 이 문서의 뒷부분에 설명되어 있습니다.

> [!TIP]
>  UWP 앱에서 작업에 관련 된 세부 정보에 알아보려면 [의 비동기 프로그래밍 C++ ](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps) 하 고 [비동기 작업 만들기 C++ UWP 앱 용](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md).

##  <a name="continuations"></a> 연속 작업

비동기 프로그래밍에서는 한 비동기 작업이 완료 시 두 번째 작업을 호출하고 해당 작업에 데이터를 전달하는 것이 일반적입니다. 일반적으로 이 작업은 콜백 메서드를 통해 수행됩니다. 동일한 기능을 제공한 동시성 런타임에서 *연속 작업*합니다. (라고도 연속) 연속 작업은 이라고 하는 다른 작업에 의해 호출 되는 비동기 작업을 *선행*선행 작업이 완료 되 면, 합니다. 연속을 사용하여 다음을 수행할 수 있습니다.

- 선행 작업의 데이터를 연속 작업에 전달합니다.

- 연속 작업이 호출되거나 호출되지 않는 정확한 조건을 지정합니다.

- 시작되기 전이나 실행 중일 때 함께 연속 작업을 취소합니다.

- 연속 작업을 예약하는 방법에 대한 힌트를 제공합니다. (유니버설 Windows 플랫폼 (UWP) 앱에 적용 됩니다. 자세한 내용은 [비동기 작업 만들기 C++ UWP 앱 용](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md).)

- 동일한 선행 작업에서 여러 개의 연속 작업을 호출합니다.

- 여러 선행 작업 중 하나 또는 모두가 완료되면 하나의 연속 작업을 호출합니다.

- 연속 작업을 임의 길이까지 차례로 연결합니다.

- 연속 작업을 사용하여 선행 작업에서 throw된 예외를 처리합니다.

이러한 기능을 사용하여 첫 번째 작업이 완료될 때 하나 이상의 작업을 실행할 수 있습니다. 예를 들어 첫 번째 작업에서 디스크로부터 파일을 읽은 후 해당 파일을 압축하는 연속 작업을 만들 수 있습니다.

다음 예제에서는 이전 하나를 사용 하 여 수정 합니다 [concurrency::task::then](reference/task-class.md#then) 사용 가능한 경우 선행 작업의 값을 인쇄 되는 연속 작업을 예약 하는 방법입니다.

[!code-cpp[concrt-basic-continuation#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_5.cpp)]

작업을 임의 길이까지 연결하고 중첩할 수 있습니다. 또한 작업에 여러 연속 작업을 포함할 수 있습니다. 다음 예제에서는 이전 작업의 값을 세 번 증가시키는 기본 연속 체인을 보여 줍니다.

[!code-cpp[concrt-continuation-chain#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_6.cpp)]

연속 작업은 다른 작업을 반환할 수도 있습니다. 취소가 없을 경우 이 작업은 후속 연속 전에 실행됩니다. 이 기술은 이라고 *비동기 래핑 해제*합니다. 비동기 래핑 해제는 백그라운드에서 추가 작업을 수행하려고 하지만 현재 작업에서 현재 스레드를 차단하지 않도록 하려는 경우에 유용합니다. (이 UWP 앱에서 일반적으로 연속 UI 스레드에서 실행할 수 있는). 다음 예제에서는 세 가지 작업을 보여 줍니다. 첫 번째 작업에서는 연속 작업 전에 실행되는 다른 작업을 반환합니다.

[!code-cpp[concrt-async-unwrapping#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_7.cpp)]

> [!IMPORTANT]
>  작업의 연속에서 `N` 형식의 중첩된 작업을 반환하는 경우 결과 작업은 `task<N>`이 아니라 `N` 형식이며 중첩된 작업이 완료될 때 완료됩니다. 즉, 연속에서 중첩된 작업의 래핑 해제를 수행합니다.

##  <a name="value-versus-task"></a> 값 기반 연속 작업을 기반으로 비교

반환 형식이 `T`인 `task` 개체를 지정하면 `T` 또는 `task<T>` 형식의 값을 연속 작업에 제공할 수 있습니다. 형식을 사용 하는 연속 `T` 라고는 *값 기반 연속*합니다. 값 기반 연속은 선행 작업이 오류 없이 완료되고 취소되지 않으면 실행되도록 예약됩니다. 형식을 사용 하는 연속 `task<T>` 해당 매개 변수 라고 하는 대로 *작업 기반 연속*합니다. 작업 기반 연속은 선행 작업이 취소되거나 예외를 throw하는 경우에도 선행 작업이 완료되면 항상 실행되도록 예약됩니다. 그러면 `task::get`을 호출하여 선행 작업의 결과를 가져올 수 있습니다. 선행 작업이 취소 되었으면 `task::get` throw [concurrency:: task_canceled](../../parallel/concrt/reference/task-canceled-class.md)합니다. 선행 작업에서 예외가 throw되면 `task::get`에서 해당 예외를 다시 throw합니다. 작업 기반 연속은 선행 작업이 취소되어도 취소됨으로 표시되지 않습니다.

##  <a name="composing-tasks"></a> 작업 작성

이 섹션에 설명 합니다 [concurrency:: when_all](reference/concurrency-namespace-functions.md#when_all) 및 [concurrency:: when_any](reference/concurrency-namespace-functions.md#when_all) 일반적인 패턴을 구현 하는 여러 작업을 구성 하는 도움이 되는 함수입니다.

###  <a name="when-all"></a> When_all 함수

`when_all` 함수는 작업 집합이 완료된 후 완료되는 작업을 생성합니다. 이 함수가 반환는 std::[벡터](../../standard-library/vector-class.md) 집합의 각 작업의 결과 포함 하는 개체입니다. 다음 기본 예제에서는 `when_all`을 사용하여 다른 세 작업의 완료를 나타내는 작업을 만듭니다.

[!code-cpp[concrt-join-tasks#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_8.cpp)]

> [!NOTE]
>  `when_all`에 전달되는 작업은 균일해야 합니다. 즉, 모두 동일한 형식을 반환해야 합니다.

다음 예제와 같이 `&&` 구문을 사용하여 작업 집합이 완료된 후 완료되는 작업을 생성할 수도 있습니다.

`auto t = t1 && t2; // same as when_all`

일반적으로 작업 집합이 완료된 후 작업을 수행하려면 `when_all`과 함께 연속을 사용합니다. 다음 예제에서는 이전 예제를 수정하여 각각 `int` 결과를 생성하는 세 작업의 합계를 인쇄합니다.

[!code-cpp[concrt-join-tasks#2](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_9.cpp)]

이 예제에서는 `task<vector<int>>`를 지정하여 작업 기반 연속을 생성할 수도 있습니다.

작업 집합의 모든 작업이 취소되거나 예외를 throw하는 경우 `when_all`은 즉시 완료되며 나머지 작업이 완료될 때까지 기다리지 않습니다. 예외가 throw되는 경우 런타임은 `when_all`이 반환하는 작업 개체에서 `task::get` 또는 `task::wait`를 호출할 때 예외를 다시 throw합니다. 둘 이상의 작업에서 예외를 throw하는 경우 런타임은 그중 하나를 선택합니다. 따라서 모든 작업이 완료된 후 예외를 모두 관찰해야 합니다. 처리되지 않은 작업 예외로 인해 앱이 종료됩니다.

다음은 프로그램에서 모든 예외를 관찰하도록 하는 데 사용할 수 있는 유틸리티 함수입니다. 제공된 범위의 각 작업에 대해 `observe_all_exceptions`는 발생된 예외를 다시 throw되도록 트리거한 다음 해당 예외를 swallow합니다.

[!code-cpp[concrt-eh-when_all#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_10.cpp)]

UWP 앱을 사용 하는 것이 좋습니다 C++ 및 XAML 파일 집합을 디스크에 씁니다. 다음 예제에서는 `when_all` 및 `observe_all_exceptions`를 사용하여 프로그램에서 모든 예외를 관찰하도록 하는 방법을 보여 줍니다.

[!code-cpp[concrt-eh-when_all#2](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_11.cpp)]

##### <a name="to-run-this-example"></a>이 예제를 실행하려면

1. MainPage.xaml에서 `Button` 컨트롤을 추가합니다.

[!code-xml[concrt-eh-when_all#3](../../parallel/concrt/codesnippet/xaml/task-parallelism-concurrency-runtime_12.xaml)]

1. MainPage.xaml.h에서 다음과 같은 정방향 선언을 `MainPage` 클래스 선언의 `private` 섹션에 추가합니다.

[!code-cpp[concrt-eh-when_all#4](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_13.h)]

1. MainPage.xaml.cpp에서 `Button_Click` 이벤트 처리기를 구현합니다.

[!code-cpp[concrt-eh-when_all#5](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_14.cpp)]

1. MainPage.xaml.cpp에서 예제에 표시된 대로 `WriteFilesAsync`를 구현합니다.

> [!TIP]
> `when_all`은 `task`를 해당 결과로 생성하는 비블로킹 함수입니다. 와 달리 [task:: wait](reference/task-class.md#wait), ASTA (응용 프로그램 STA) 스레드에서 UWP 앱에서이 함수를 호출 해도 됩니다.

###  <a name="when-any"></a> When_any 함수

`when_any` 함수는 작업 집합의 첫 번째 작업이 완료되면 완료되는 작업을 생성합니다. 이 함수는 반환 된 [std:: pair](../../standard-library/pair-structure.md) 완료 된 작업의 결과 및 집합에서 해당 작업의 인덱스를 포함 하는 개체.

`when_any` 함수는 다음과 같은 시나리오에서 특히 유용합니다.

- 중복 작업입니다. 알고리즘 또는 여러 방법으로 수행할 수 있는 작업을 고려합니다. `when_any` 함수를 사용하여 먼저 완료되는 작업을 선택한 다음 나머지 작업을 취소할 수 있습니다.

- 인터리브 작업입니다. 모두 완료되어야 하는 여러 작업을 시작하고 `when_any` 함수를 사용하여 각 작업이 완료되면 결과를 처리할 수 있습니다. 하나의 작업이 완료되면 하나 이상의 추가 작업을 시작할 수 있습니다.

- 제한된 작업입니다. `when_any` 함수를 사용하여 동시 작업 수를 제한하여 이전 시나리오를 확장할 수 있습니다.

- 만료된 작업입니다. `when_any` 함수를 사용하여 하나 이상의 작업과 특정 시간 이후에 완료되는 작업 중에서 선택할 수 있습니다.

`when_all`과 마찬가지로 `when_any`가 포함된 연속을 사용하여 작업 집합의 첫 번째 작업이 완료되면 작업을 수행할 수 있습니다. 다음 기본 예제에서는 `when_any`를 사용하여 다른 세 작업 중 첫 번째 작업이 완료되면 완료되는 작업을 만듭니다.

[!code-cpp[concrt-select-task#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_15.cpp)]

이 예제에서는 `task<pair<int, size_t>>`를 지정하여 작업 기반 연속을 생성할 수도 있습니다.

> [!NOTE]
> `when_all`과 마찬가지로 `when_any`에 전달되는 작업은 모두 동일한 형식을 반환해야 합니다.

다음 예제와 같이 `||` 구문을 사용하여 작업 집합의 첫 번째 작업이 완료된 후 완료되는 작업을 생성할 수도 있습니다.

`auto t = t1 || t2; // same as when_any`

> [!TIP]
> 와 마찬가지로 `when_all`, `when_any` 는 비블로킹 이며 ASTA 스레드에서 UWP 앱에서 호출할 수 있습니다.

##  <a name="delayed-tasks"></a> 지연 된 작업 실행

경우에 따라 조건이 충족될 때까지 작업 실행을 지연하거나 외부 이벤트에 대한 응답으로 작업을 시작해야 할 수 있습니다. 예를 들어 비동기 프로그래밍에서 I/O 완료 이벤트에 대한 응답으로 작업을 시작해야 할 수 있습니다.

이렇게 하려면 연속을 사용하거나 작업을 시작하고 작업의 작업 함수 내에서 이벤트를 대기하는 두 가지 방법이 있습니다. 그러나 이러한 기술을 하나를 사용할 수 없는 경우가 있습니다. 예를 들어 연속을 만들려면 선행 작업이 있어야 합니다. 그러나 선행 작업이 없는 경우 만들 수 있습니다는 *작업 완료 이벤트가* 하며 나중에 사용할 수 있을 때 선행 작업 완료 이벤트를 연결 합니다. 또한 대기 중인 작업은 스레드도 차단하므로 작업 완료 이벤트를 사용하여 비동기 작업이 완료되면 작업을 수행함으로써 스레드를 해제할 수 있습니다.

합니다 [concurrency:: task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md) 클래스에 이러한 작업의 컴퍼지션을 간소화 하는 데 도움이 됩니다. `task` 클래스처럼 형식 매개 변수 `T`는 작업에 의해 생성되는 결과의 형식입니다. 작업에서 값을 반환하지 않는 경우 이 형식은 `void`일 수 있습니다. `T`는 `const` 한정자를 사용할 수 없습니다. 일반적으로 `task_completion_event` 개체는 값을 사용할 수 있을 때 신호를 보내는 작업이나 스레드에 제공됩니다. 동시에 하나 이상의 작업이 해당 이벤트의 수신기로 설정됩니다. 이벤트가 설정되면 수신기 작업이 완료되고 작업의 연속 실행이 예약됩니다.

사용 하는 예로 `task_completion_event` 지연 후 완료 되는 작업을 구현 하려면 참조 [방법: 지연 후 완료 되는 작업을 만드는](../../parallel/concrt/how-to-create-a-task-that-completes-after-a-delay.md)합니다.

##  <a name="task-groups"></a> 작업 그룹

A *작업 그룹* 작업 컬렉션을 구성 합니다. 작업 그룹은 작업 가로채기 큐에 작업을 넣습니다. 스케줄러는 이 큐에서 작업을 제거하고 사용 가능한 컴퓨팅 리소스에서 실행합니다. 작업 그룹에 작업을 추가한 후 모든 작업이 완료되거나 아직 시작되지 않은 작업이 취소될 때까지 기다릴 수 있습니다.

PPL을 사용 합니다 [concurrency:: task_group](reference/task-group-class.md) 및 [concurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) 작업 그룹을 나타내기 위해 클래스 및 [concurrency:: task_handle](../../parallel/concrt/reference/task-handle-class.md) 클래스 이러한 그룹에서 실행 되는 작업을 나타내려는 경우. `task_handle` 클래스는 작업을 수행하는 코드를 캡슐화합니다. `task` 클래스와 마찬가지로 작업 함수는 람다 함수, 함수 포인터 또는 함수 개체의 형태로 제공됩니다. 일반적으로 `task_handle` 개체에서 직접 작업할 필요가 없습니다. 대신 작업 그룹에 작업 함수를 전달하면 작업 그룹에서 `task_handle` 개체를 만들고 관리합니다.

PPL 작업 그룹을 이러한 두 가지 범주로 나눕니다: *구조화 되지 않은 작업 그룹* 하 고 *구조적 작업 그룹*합니다. PPL은 `task_group` 클래스를 사용하여 비구조적 작업 그룹을 나타내고 `structured_task_group` 클래스를 사용하여 구조적 작업 그룹을 나타냅니다.

> [!IMPORTANT]
> 또한 PPL이 정의 [concurrency:: parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) 알고리즘을 사용 하는 `structured_task_group` 작업 집합을 병렬로 실행 하는 클래스입니다. `parallel_invoke` 알고리즘에는 더 간결한 구문이 있으므로 가능한 경우 `structured_task_group` 클래스 대신 사용하는 것이 좋습니다. 항목 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md) 설명 `parallel_invoke` 에서 더 자세히 설명 합니다.

동시에 실행하려는 여러 독립된 작업이 있고 계속하려면 모든 작업이 완료될 때까지 기다려야 하는 경우 `parallel_invoke`를 사용합니다. 이 기술을 종종 이라고 *분기 및 조인* 병렬 처리 합니다. 동시에 실행하려는 여러 독립된 작업이 있지만 작업이 나중에 완료될 때까지 기다리려면 `task_group`을 사용합니다. 예를 들어 `task_group` 개체에 작업을 추가하고 작업이 다른 함수 또는 다른 스레드에서 완료될 때까지 기다릴 수 있습니다.

작업 그룹은 취소 개념을 지원합니다. 취소를 사용하면 전체 작업을 취소하려고 한다는 사실을 모든 활성 작업에 알릴 수 있습니다. 또한 취소를 사용하면 아직 시작되지 않은 작업이 시작되지 않도록 방지할 수 있습니다. 취소에 대 한 자세한 내용은 참조 하세요. [PPL에서의 취소](cancellation-in-the-ppl.md)합니다.

또한 런타임은 작업에서 예외를 throw하고 연결된 작업 그룹이 완료될 때까지 기다린 후 해당 예외를 처리할 수 있도록 하는 예외 처리 모델을 제공합니다. 이 예외 처리 모델에 대 한 자세한 내용은 참조 하세요. [예외 처리](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)합니다.

##  <a name="comparing-groups"></a> Task_group과 structured_task_group 비교

`structured_task_group` 클래스 대신 `task_group` 또는 `parallel_invoke`를 사용하는 것이 좋지만 다양한 작업을 수행하거나 취소를 지원해야 하는 병렬 알고리즘을 작성하는 경우처럼 `structured_task_group`을 사용해야 하는 경우가 있습니다. 이 섹션에서는 `task_group`과 `structured_task_group`의 차이점에 대해 설명합니다.

`task_group` 클래스는 스레드로부터 안전합니다. 따라서 여러 스레드에서 `task_group` 개체에 작업을 추가하고 여러 스레드에서 `task_group` 개체를 대기하거나 취소할 수 있습니다. `structured_task_group` 개체의 생성 및 소멸은 동일한 어휘 범위에서 발생해야 합니다. 또한 `structured_task_group` 개체의 모든 작업은 동일한 스레드에서 발생해야 합니다. 이 규칙의 예외는 [concurrency::structured_task_group::cancel](reference/structured-task-group-class.md#cancel) 하 고 [concurrency::structured_task_group::is_canceling](reference/structured-task-group-class.md#is_canceling) 메서드. 자식 작업은 언제든지 이러한 메서드를 호출하여 부모 작업 그룹을 취소하거나 취소를 확인할 수 있습니다.

추가 작업을 실행할 수 있습니다는 `task_group` 호출한 후 개체를 [concurrency::task_group::wait](reference/task-group-class.md#wait) 하거나 [run_and_wait](reference/task-group-class.md#run_and_wait) 메서드. 반대로, 시 추가 작업을 실행 하는 경우는 `structured_task_group` 호출한 후 개체를 [concurrency::structured_task_group::wait](reference/structured-task-group-class.md#wait) 하거나 [concurrency::structured_task_group::run_and_wait](reference/structured-task-group-class.md#run_and_wait) 메서드 를 다음 동작이 정의 되지 않습니다.

`structured_task_group` 클래스는 스레드에서 동기화되지 않으므로 `task_group` 클래스보다 실행 오버헤드가 적습니다. 따라서 문제가 여러 스레드에서 작업을 예약하도록 요구하지 않고 `parallel_invoke` 알고리즘을 사용할 수 없는 경우 `structured_task_group` 클래스를 사용하여 더 잘 수행되는 코드를 작성할 수 있습니다.

다른 `structured_task_group` 개체 내에서 `structured_task_group` 을 사용하는 경우 외부 개체가 완료되기 전에 내부 개체를 완료하고 삭제해야 합니다. `task_group` 클래스에서는 외부 그룹이 완료되기 전에 중첩된 작업 그룹이 완료될 필요가 없습니다.

비구조적 작업 그룹과 구조적 작업 그룹은 다양한 방법으로 작업 핸들에서 작동합니다. 작업 함수를 `task_group` 개체에 직접 전달할 수 있으며, `task_group` 개체에서 작업 핸들을 만들고 관리합니다. `structured_task_group` 클래스에서는 각 작업에 대해 `task_handle` 개체를 관리해야 합니다. 모든 `task_handle` 개체는 연결된 `structured_task_group` 개체의 수명 동안 내내 유효한 상태로 유지되어야 합니다. 사용 합니다 [concurrency:: make_task](reference/concurrency-namespace-functions.md#make_task) 만드는 함수를 `task_handle` 다음 기본 예제와 같이 개체:

[!code-cpp[concrt-make-task-structure#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_16.cpp)]

다양 한 작업을 할 수 있는 경우에 사용할 작업 핸들을 관리 하려면 사용 하 여 스택 할당 루틴을 같은 [_malloca](../../c-runtime-library/reference/malloca.md) 또는 std 같은 컨테이너 클래스::[벡터](../../standard-library/vector-class.md)입니다.

`task_group`과 `structured_task_group` 둘 다 취소를 지원합니다. 취소에 대 한 자세한 내용은 참조 하세요. [PPL에서의 취소](cancellation-in-the-ppl.md)합니다.

##  <a name="example"></a> 예제

다음 기본 예제에서는 작업 그룹을 사용하는 방법을 보여 줍니다. 이 예제에서는 `parallel_invoke` 알고리즘을 사용하여 두 작업을 동시에 수행합니다. 각 작업은 하위 작업을 `task_group` 개체에 추가합니다. `task_group` 클래스를 사용하면 여러 작업이 동시에 이 클래스에 작업을 추가할 수 있습니다.

[!code-cpp[concrt-using-task-groups#1](../../parallel/concrt/codesnippet/cpp/task-parallelism-concurrency-runtime_17.cpp)]

다음은 이 예제의 샘플 출력입니다.

```Output
Message from task: Hello
Message from task: 3.14
Message from task: 42
```

`parallel_invoke` 알고리즘은 작업을 동시에 실행하므로 출력 메시지의 순서가 다를 수 있습니다.

사용 하는 방법을 보여 주는 전체 예제는 `parallel_invoke` 알고리즘 참조 [방법: Parallel_invoke를 사용 하 여 병렬 정렬 루틴 작성](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md) 고 [방법: Parallel_invoke 병렬 작업 실행을 사용 하 여](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md)입니다. 사용 하는 전체 예제는 `task_group` 비동기 미래를 구현 하 여 참조를 클래스 [연습: Future 구현](../../parallel/concrt/walkthrough-implementing-futures.md)합니다.

##  <a name="robust"></a> 강력한 프로그래밍

작업, 작업 그룹 및 병렬 알고리즘을 사용하는 경우 취소 및 예외 처리의 역할을 이해하고 있어야 합니다. 예를 들어 병렬 작업 트리에서 취소되는 작업은 자식 작업이 실행되지 않도록 방지합니다. 따라서 자식 작업 중 하나가 리소스 해제와 같이 애플리케이션에 중요한 작업을 수행하는 경우 문제가 발생할 수 있습니다. 또한 자식 작업에서 예외를 throw하는 경우 해당 예외가 개체 소멸자를 통해 전파되어 애플리케이션에서 정의되지 않은 동작이 발생할 수 있습니다. 이러한 지점을 보여 주는 예제를 참조 하세요. 합니다 [이해 하는 방법을 취소 및 예외 처리에 영향을 줄 개체 소멸](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md#object-destruction) 병렬 패턴 라이브러리 문서에서 모범 사례에 대 한 섹션입니다. 취소 및 PPL에서의 예외 처리 모델에 대 한 자세한 내용은 참조 하세요. [취소가](../../parallel/concrt/cancellation-in-the-ppl.md) 하 고 [예외 처리](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)합니다.

## <a name="related-topics"></a>관련 항목

|제목|설명|
|-----------|-----------------|
|[방법: parallel_invoke를 사용하여 병렬 정렬 루틴 작성](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md)|`parallel_invoke` 알고리즘을 사용하여 바이토닉 정렬 알고리즘의 성능을 향상시키는 방법을 보여 줍니다.|
|[방법: parallel_invoke를 사용하여 병렬 작업 실행](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md)|`parallel_invoke` 알고리즘을 사용하여 공유 데이터 소스에서 여러 작업을 수행하는 프로그램의 성능을 향상시키는 방법을 보여 줍니다.|
|[방법: 지연 후 완료되는 작업 만들기](../../parallel/concrt/how-to-create-a-task-that-completes-after-a-delay.md)|사용 하는 방법을 보여 줍니다는 `task`, `cancellation_token_source`, `cancellation_token`, 및 `task_completion_event` 지연 후 완료 되는 작업을 만들기 위한 클래스입니다.|
|[연습: 미래 구현](../../parallel/concrt/walkthrough-implementing-futures.md)|동시성 런타임의 기존 기능을 더 많은 역할을 하는 기능과 결합하는 방법을 보여 줍니다.|
|[PPL(병렬 패턴 라이브러리)](../../parallel/concrt/parallel-patterns-library-ppl.md)|동시 애플리케이션 개발을 위해 명령적 프로그래밍 모델을 제공하는 PPL에 대해 설명합니다.|

## <a name="reference"></a>참조

[task 클래스(동시성 런타임)](../../parallel/concrt/reference/task-class.md)

[task_completion_event 클래스](../../parallel/concrt/reference/task-completion-event-class.md)

[when_all 함수](reference/concurrency-namespace-functions.md#when_all)

[when_any 함수](reference/concurrency-namespace-functions.md#when_any)

[task_group 클래스](reference/task-group-class.md)

[parallel_invoke 함수](reference/concurrency-namespace-functions.md#parallel_invoke)

[structured_task_group 클래스](../../parallel/concrt/reference/structured-task-group-class.md)
