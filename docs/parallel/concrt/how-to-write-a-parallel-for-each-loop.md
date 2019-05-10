---
title: '방법: Parallel_for_each 루프 작성'
ms.date: 11/04/2016
helpviewer_keywords:
- writing a parallel_for_each loop [Concurrency Runtime]
- parallel_for_each function, example
ms.assetid: fa9c0ba6-ace0-4f88-8681-c7c1f52aff20
ms.openlocfilehash: 19af9be8ef6d9c38a0942e7c85caa0a8bc4e6813
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62375563"
---
# <a name="how-to-write-a-parallelforeach-loop"></a>방법: Parallel_for_each 루프 작성

사용 하는 방법을 보여 주는이 예제는 [concurrency:: parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) 알고리즘에서 소수의 수를 계산 하는 [std:: array](../../standard-library/array-class-stl.md) 병렬로 개체입니다.

## <a name="example"></a>예제

다음 예제에서는 두 번 배열에서 소수의 수를 계산합니다. 이 예제에서는 먼저 사용 합니다 [std:: for_each](../../standard-library/algorithm-functions.md#for_each) 순차적으로 수를 계산 하는 알고리즘입니다. 이 예제에서는 다음 사용을 `parallel_for_each` 동시에 동일한 작업을 수행 하는 알고리즘입니다. 또한 두 계산을 모두 수행하는 데 필요한 시간을 콘솔에 출력합니다.

[!code-cpp[concrt-parallel-count-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-each-loop_1.cpp)]

다음 샘플은 프로세서가 4개인 컴퓨터에 대한 출력입니다.

```Output
serial version:
found 17984 prime numbers
took 6115 ms

parallel version:
found 17984 prime numbers
took 1653 ms
```

## <a name="compiling-the-code"></a>코드 컴파일

컴파일하려면 코드를 복사 하 고 다음 Visual Studio 프로젝트에 붙여 넣습니다와 라는 파일에 붙여 `parallel-count-primes.cpp` Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.

**cl.exe /EHsc 병렬-수-primes.cpp**

## <a name="robust-programming"></a>강력한 프로그래밍

에 전달 된 람다 식의 `parallel_for_each` 알고리즘에서 사용 하는 `InterlockedIncrement` 카운터를 동시에 증가 하는 루프의 병렬 반복을 사용 하도록 설정 하는 함수. 와 같은 함수를 사용 하는 경우 `InterlockedIncrement` 공유 리소스에 대 한 액세스를 동기화 하려면 코드에서 성능 병목 상태를 제공할 수 있습니다. 예를 들어 잠금 해제 동기화 메커니즘을 사용할 수 있습니다, [concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) 클래스, 공유 리소스에 대 한 동시 액세스를 제거 합니다. 사용 하는 예는 `combinable` 이 방식으로 클래스를 참조 하십시오 [방법: Combinable 성능 향상을 사용 하 여](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)입니다.

## <a name="see-also"></a>참고자료

[병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)<br/>
[parallel_for_each 함수](reference/concurrency-namespace-functions.md#parallel_for_each)
