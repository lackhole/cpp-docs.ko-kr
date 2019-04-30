---
title: '연습: Future 구현'
ms.date: 04/25/2019
helpviewer_keywords:
- implementing futures [Concurrency Runtime]
- futures, implementing [Concurrency Runtime]
ms.assetid: 82ea75cc-aaec-4452-b10d-8abce0a87e5b
ms.openlocfilehash: 7164919d649751ac11fefa5be3cb2e5b7798ee4f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407850"
---
# <a name="walkthrough-implementing-futures"></a>연습: Future 구현

이 항목에서는 응용 프로그램에 future를 구현 하는 방법을 보여 줍니다. 항목에는 기존 기능으로 결합 하는 동시성 런타임에서 항목 많은 기능을 수행 하는 방법을 보여 줍니다.

> [!IMPORTANT]
>  이 항목에서는 이해를 돕기 위해 미래의 개념에 대해 설명합니다. 사용 하는 것이 좋습니다 [std:: future](../../standard-library/future-class.md) 하거나 [concurrency:: task](../../parallel/concrt/reference/task-class.md) 나중에 사용할 값을 계산 하는 비동기 작업을 해야 할 경우.

A *태스크* 은 추가, 보다 세분화 된 계산으로 분해할 수를 계산 합니다. A *향후* 은 나중에 사용할 값을 계산 하는 비동기 작업입니다.

이 항목에서는 미래를 구현 하려면 다음을 정의 합니다.는 `async_future` 클래스입니다. `async_future` 동시성 런타임의 구성이 요소를 사용 하는 클래스: 합니다 [concurrency:: task_group](reference/task-group-class.md) 클래스와 [concurrency:: single_assignment](../../parallel/concrt/reference/single-assignment-class.md) 클래스. 합니다 `async_future` 클래스가 사용 하는 `task_group` 값을 비동기적으로 계산 하는 클래스 및 `single_assignment` 계산의 결과 저장 하는 클래스입니다. 생성자는 `async_future` 결과 계산 하는 작업 함수를 사용 하는 클래스 및 `get` 메서드는 결과 검색 합니다.

### <a name="to-implement-the-asyncfuture-class"></a>async_future 클래스를 구현하려면

1. 명명 된 템플릿 클래스를 선언 `async_future` 결과 계산의 형식에 매개 변수가 있는 합니다. 추가 `public` 고 `private` 이 클래스에는 섹션입니다.

[!code-cpp[concrt-futures#2](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_1.cpp)]

1. 에 `private` 섹션을 `async_future` 클래스를 선언를 `task_group` 및 `single_assignment` 데이터 멤버.

[!code-cpp[concrt-futures#3](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_2.cpp)]

1. 에 `public` 부분을 `async_future` 클래스 생성자를 구현 합니다. 생성자는 결과 계산 하는 작업 함수에서 매개 변수화 된 템플릿입니다. 생성자의 작업 함수를 비동기적으로 실행 합니다 `task_group` 사용 하 여 데이터 멤버를 [concurrency:: send](reference/concurrency-namespace-functions.md#send) 결과를 작성 하는 함수는 `single_assignment` 데이터 멤버.

[!code-cpp[concrt-futures#4](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_3.cpp)]

1. 에 `public` 부분을 `async_future` 클래스 소멸자를 구현 합니다. 소멸자는 작업이 완료 되기를 기다립니다.

[!code-cpp[concrt-futures#5](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_4.cpp)]

1. 에 `public` 의 섹션을 `async_future` 클래스를 구현 합니다는 `get` 메서드. 이 메서드를 사용 합니다 [concurrency:: receive](reference/concurrency-namespace-functions.md#receive) 작업 함수의 결과 검색 하는 함수입니다.

[!code-cpp[concrt-futures#6](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_5.cpp)]

## <a name="example"></a>예제

### <a name="description"></a>설명

다음 예제에서는 전체 `async_future` 클래스 및 해당 사용법의 예입니다. 합니다 `wmain` 함수 만듭니다는 std::[벡터](../../standard-library/vector-class.md) 10,000 임의의 정수 값을 포함 하는 개체입니다. 사용 하 여 `async_future` 개체에 포함 된 최소 및 최대 값을 찾으려면는 `vector` 개체입니다.

### <a name="code"></a>코드

[!code-cpp[concrt-futures#1](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_6.cpp)]

### <a name="comments"></a>설명

이 예제는 다음과 같은 출력을 생성합니다.

```Output
smallest: 0
largest:  9999
average:  4981
```

이 예제에서는 사용 된 `async_future::get` 계산의 결과 검색 하는 방법입니다. `async_future::get` 메서드 계산 여전히 활성 상태 이면 끝날 때까지 기다립니다.

## <a name="robust-programming"></a>강력한 프로그래밍

확장 하는 `async_future` 수정, 작업 함수에서 throw 된 예외를 처리 하는 클래스를 `async_future::get` 메서드를 호출 합니다 [concurrency::task_group::wait](reference/task-group-class.md#wait) 메서드. `task_group::wait` 메서드 작업 함수에 의해 생성 된 모든 예외를 throw 합니다.

다음 예제에서는 수정 된 버전을 표시 합니다 `async_future` 클래스입니다. 합니다 `wmain` 함수는 `try` - `catch` 블록의 결과 인쇄 하는 `async_future` 개체 또는 작업 함수에 의해 생성 되는 예외 값을 인쇄 하려면.

[!code-cpp[concrt-futures-with-eh#1](../../parallel/concrt/codesnippet/cpp/walkthrough-implementing-futures_7.cpp)]

이 예제는 다음과 같은 출력을 생성합니다.

```Output
caught exception: error
```

동시성 런타임에서 예외 처리 모델에 대 한 자세한 내용은 참조 하세요. [예외 처리](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)합니다.

## <a name="compiling-the-code"></a>코드 컴파일

예제 코드를 복사하여 Visual Studio 프로젝트 또는 `futures.cpp` 파일에 붙여넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.

**cl.exe /EHsc futures.cpp**

## <a name="see-also"></a>참고자료

[동시성 런타임 연습](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[예외 처리](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)<br/>
[task_group 클래스](reference/task-group-class.md)<br/>
[single_assignment 클래스](../../parallel/concrt/reference/single-assignment-class.md)
