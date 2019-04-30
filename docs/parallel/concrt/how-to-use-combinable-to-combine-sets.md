---
title: '방법: Combinable 집합 결합을 사용 하 여'
ms.date: 11/04/2016
helpviewer_keywords:
- combinable class, example
- combining sets with combinable [Concurrency Runtime]
ms.assetid: 66ffe8e3-6bbb-4e9f-b790-b612922a68a7
ms.openlocfilehash: bf8a5bee65ea0ba1718c1d4d436b6af3e0b95961
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62345580"
---
# <a name="how-to-use-combinable-to-combine-sets"></a>방법: Combinable 집합 결합을 사용 하 여

이 항목에서는 [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) 클래스를 사용하여 소수 집합을 계산하는 방법을 보여 줍니다.

## <a name="example"></a>예제

다음 예제에서는 소수 집합을 두 번 계산합니다. 각 계산 결과는 [std::bitset](../../standard-library/bitset-class.md) 개체에 저장됩니다. 이 예제에서는 먼저 직렬로 집합을 계산한 후 병렬로 집합을 계산합니다. 또한 두 계산을 모두 수행하는 데 필요한 시간을 콘솔에 출력합니다.

이 예제에서는 [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) 알고리즘과 `combinable` 개체를 사용하여 스레드 로컬 집합을 생성합니다. 그런 다음 [concurrency::combinable::combine_each](reference/combinable-class.md#combine_each) 메서드를 사용하여 스레드 로컬 집합을 최종 집합으로 결합합니다.

[!code-cpp[concrt-parallel-combine-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-combine-sets_1.cpp)]

다음 샘플은 프로세서가 4개인 컴퓨터에 대한 출력입니다.

```Output
serial time: 312 ms

parallel time: 78 ms
```

## <a name="compiling-the-code"></a>코드 컴파일

예제 코드를 복사하여 Visual Studio 프로젝트 또는 `parallel-combine-primes.cpp` 파일에 붙여넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.

**cl.exe /EHsc parallel-combine-primes.cpp**

## <a name="see-also"></a>참고자료

[병렬 컨테이너 및 개체](../../parallel/concrt/parallel-containers-and-objects.md)<br/>
[combinable 클래스](../../parallel/concrt/reference/combinable-class.md)<br/>
[combinable::combine_each 메서드](reference/combinable-class.md#combine_each)
