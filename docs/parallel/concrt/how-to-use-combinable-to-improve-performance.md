---
title: '방법: Combinable 성능 향상을 사용 하 여'
ms.date: 11/04/2016
helpviewer_keywords:
- combinable class, example
- improving parallel performance with combinable [Concurrency Runtime]
ms.assetid: fa730580-1c94-4b2d-8aec-57c91dc0497e
ms.openlocfilehash: c8f4c40be84b2204e5b5632fe6d3d5a5d22b8719
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410008"
---
# <a name="how-to-use-combinable-to-improve-performance"></a>방법: Combinable 성능 향상을 사용 하 여

사용 하는 방법을 보여 주는이 예제는 [concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) 클래스에 있는 숫자의 합계를 계산 하는 [std:: array](../../standard-library/array-class-stl.md) 는 개체입니다. `combinable` 클래스 공유 상태를 제거 하 여 성능이 향상 됩니다.

> [!TIP]
>  경우에 따라 병렬 매핑 ([concurrency:: parallel_transform](reference/concurrency-namespace-functions.md#parallel_transform))를 줄이고 ([concurrency:: parallel_reduce](reference/concurrency-namespace-functions.md#parallel_reduce))를 통해 성능 향상을 제공할 수 있습니다 `combinable`. 사용 하 여 맵 및이이 예제와 동일한 결과 생성 하는 작업 감소 하는 예제를 참조 하세요 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)합니다.

## <a name="example"></a>예제

다음 예제에서는 합니다 [std:: accumulate](../../standard-library/numeric-functions.md#accumulate) 함수는 배열에서 요소의 합계를 계산 합니다. 이 예제에서는 `a` 되는 `array` 개체 및 `is_prime` 함수 입력된 값 소수 인지 여부를 확인 합니다.

[!code-cpp[concrt-parallel-sum-of-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_1.cpp)]

## <a name="example"></a>예제

다음 예제에서는 이전 예제를 병렬화 하는 간단한 방법을 보여 줍니다. 이 예제에서는 합니다 [concurrency:: parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) 배열을 병렬로 처리 하는 알고리즘 및 [concurrency:: critical_section](../../parallel/concrt/reference/critical-section-class.md) 개체에 대 한 액세스를 동기화 하는 `prime_sum` 변수 . 이 예제에서는 각 스레드가 공유 리소스를 사용할 수 있게 기다려야 하므로 확장 되지 않습니다.

[!code-cpp[concrt-parallel-sum-of-primes#2](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_2.cpp)]

## <a name="example"></a>예제

다음 예제에서는 `combinable` 이전 예의 성능 향상을 위해 개체입니다. 이 예제에서는 동기화 개체에 대 한 필요를 하지 않습니다. 때문에 확장을 `combinable` 개체를 사용 하면 해당 작업을 독립적으로 수행 하는 각 스레드입니다.

`combinable` 개체는 일반적으로 두 단계에서 사용 됩니다. 먼저 병렬로 작업을 수행 하 여 일련의 세분화 된 계산을 생성 합니다. 다음으로, 결합 (또는 줄일) 최종 결과를 계산 합니다. 이 예제에서는 합니다 [concurrency::combinable::local](reference/combinable-class.md#local) 로컬 합계에 대 한 참조를 가져오는 방법입니다. 사용 하 여는 [concurrency::combinable::combine](reference/combinable-class.md#combine) 메서드 및 [std:: plus](../../standard-library/plus-struct.md) 로컬 계산 결과 최종 결과로 결합 하는 개체입니다.

[!code-cpp[concrt-parallel-sum-of-primes#3](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_3.cpp)]

## <a name="example"></a>예제

다음 전체 예제는 직렬 및 병렬로 소수 숫자의 합을 계산합니다. 예제는 두 계산을 수행 하는 데 필요한 시간을 콘솔에 인쇄 합니다.

[!code-cpp[concrt-parallel-sum-of-primes#4](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_4.cpp)]

다음 샘플은 프로세서가 4개인 컴퓨터에 대한 출력입니다.

```Output
1709600813
serial time: 6178 ms

1709600813
parallel time: 1638 ms
```

## <a name="compiling-the-code"></a>코드 컴파일

컴파일하려면 코드를 복사 하 고 다음 Visual Studio 프로젝트에 붙여 넣습니다와 라는 파일에 붙여 `parallel-sum-of-primes.cpp` Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.

**cl.exe /EHsc parallel-sum-of-primes.cpp**

## <a name="robust-programming"></a>강력한 프로그래밍

사용 하 여 맵 및이 동일한 결과 생성 하는 작업 감소 하는 예제를 참조 하세요 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)합니다.

## <a name="see-also"></a>참고자료

[병렬 컨테이너 및 개체](../../parallel/concrt/parallel-containers-and-objects.md)<br/>
[combinable 클래스](../../parallel/concrt/reference/combinable-class.md)<br/>
[critical_section 클래스](../../parallel/concrt/reference/critical-section-class.md)
