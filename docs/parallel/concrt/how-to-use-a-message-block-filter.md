---
title: '방법: 메시지 블록 필터 사용'
ms.date: 11/04/2016
helpviewer_keywords:
- message-block filters, using [Concurrency Runtime]
- using message-block filters [Concurrency Runtime]
ms.assetid: db6b99fb-288d-4477-96dc-b9751772ebb2
ms.openlocfilehash: 1bfa11953d27dc7e013e715b3f58111f124caeaf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62321944"
---
# <a name="how-to-use-a-message-block-filter"></a>방법: 메시지 블록 필터 사용

이 문서에 허용 하거나 해당 메시지의 페이로드를 기준으로 메시지를 거부 하는 비동기 메시지 블록을 사용 하도록 설정 하려면 필터 함수를 사용 하는 방법을 보여 줍니다.

와 같은 메시지 블록 개체를 만들 때를 [concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md), [concurrency:: call](../../parallel/concrt/reference/call-class.md), 또는 [concurrency:: transformer](../../parallel/concrt/reference/transformer-class.md)합니다 를제공할수있습니다*filter 함수* 메시지 블록을 허용 하거나 메시지를 거부 하는지 여부를 결정 하는 합니다. 필터 함수에는 메시지 블록에 특정 값만 수신 하는지 보장 하는 유용한 방법입니다.

필터 함수는 메시지 블록을 연결할 수 있도록 하므로 중요 *데이터 흐름 네트워크*합니다. 데이터 흐름 네트워크에서 메시지 블록 특정 조건을 충족 하는 메시지만 처리 하 여 데이터의 흐름을 제어 합니다. 조건문, 루프와 같은 제어 구조를 사용 하 여 데이터 흐름을 규제 되는 제어 흐름 모델과 비교 등에입니다.

이 문서에서는 메시지 필터를 사용 하는 방법의 기본적인 예를 제공 합니다. 메시지 필터 및 데이터 흐름 모델을 사용 하 여 메시지 블록을 연결 하는 추가 예제를 보려면 [연습: 데이터 흐름 에이전트 만들기](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md) 고 [연습: 이미지 처리 네트워크 만들기](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)합니다.

## <a name="example"></a>예제

다음 함수를 살펴보세요 `count_primes`, 들어오는 메시지를 필터링 하지 않는 메시지 블록의 기본 사용법을 보여 주는 합니다. 메시지 블록에 소수 추가 된 [std:: vector](../../standard-library/vector-class.md) 개체입니다. `count_primes` 함수 여러 숫자를 메시지 블록이, 메시지 블록에서 출력 값을 받습니다 보내고 콘솔에는 해당 번호를 인쇄 합니다.

[!code-cpp[concrt-primes-filter#1](../../parallel/concrt/codesnippet/cpp/how-to-use-a-message-block-filter_1.cpp)]

`transformer` 모든 입력된 값을 처리 하는 개체;는 해당 값만 필요 합니다. 메시지 보낸 사람 소수만 보내도록 되도록 응용 프로그램을 작성할 수 있습니다, 있지만 메시지 수신자의 요구 사항은 항상 알 수 없습니다.

## <a name="example"></a>예제

다음 함수 `count_primes_filter`와 동일한 작업을 수행 합니다 `count_primes` 함수입니다. 그러나는 `transformer` 이 버전의 개체는 값만을 허용 하도록 필터 함수를 사용 합니다. 작업을 수행 하는 함수에 받기만 소수; 따라서 없기를 호출 하 여 `is_prime` 함수입니다.

때문에 합니다 `transformer` 소수 숫자만 수신 하는 개체는 `transformer` 개체 자체는 소수를 포함할 수 있습니다. 즉, 합니다 `transformer` 이 예제에서 개체를 소수를 추가할 필요가 없습니다를 `vector` 개체입니다.

[!code-cpp[concrt-primes-filter#2](../../parallel/concrt/codesnippet/cpp/how-to-use-a-message-block-filter_2.cpp)]

`transformer` 개체는 이제는 해당 값만 처리 합니다. 이전 예에서 `transformer` 모든 메시지를 처리 하는 개체입니다. 따라서 앞의 예제 수가 보내는 메시지를 받아야 합니다. 이 예제에서는 결과 [concurrency:: send](reference/concurrency-namespace-functions.md#send) 메시지에서 수신 하도록 결정 하는 함수는 `transformer` 개체입니다. 합니다 `send` 함수에서 반환 **true** 메시지 버퍼에서 메시지를 수락 하는 경우 및 **false** 메시지 버퍼는 메시지를 거부 하는 경우. 따라서 메시지 버퍼에서 메시지를 수락 하는 횟수에는 소수의 수와 일치 합니다.

## <a name="example"></a>예제

다음 코드에서는 전체 예제를 보여 줍니다. 이 예제에서는 둘 다를 호출 합니다 `count_primes` 함수 및 `count_primes_filter` 함수.

[!code-cpp[concrt-primes-filter#3](../../parallel/concrt/codesnippet/cpp/how-to-use-a-message-block-filter_3.cpp)]

## <a name="compiling-the-code"></a>코드 컴파일

예제 코드를 복사하여 Visual Studio 프로젝트 또는 `primes-filter.cpp` 파일에 붙여넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.

**cl.exe /EHsc prime filter.cpp**

## <a name="robust-programming"></a>강력한 프로그래밍

필터 함수는 람다 함수, 함수 포인터 또는 함수 개체를 수 있습니다. 모든 필터 함수를 사용 하는 다음 중 하나:

```Output
bool (T)
bool (T const &)
```

데이터의 불필요 한 복사를 제거 하려면 집합체 형식 값으로 전송 되는 경우 두 번째 형태를 사용 합니다.

## <a name="see-also"></a>참고자료

[비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[연습: 데이터 흐름 에이전트 만들기](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)<br/>
[연습: 이미지 처리 네트워크 만들기](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)<br/>
[transformer 클래스](../../parallel/concrt/reference/transformer-class.md)
