---
title: '방법: OpenMP parallel for 루프 동시성 런타임을 사용 하 여 변환'
ms.date: 11/04/2016
helpviewer_keywords:
- converting from OpenMP to the Concurrency Runtime, parallel for loops
- converting from OpenMP to the Concurrency Runtime, parallel loops
- parallel for loops, converting from OpenMP to the Concurrency Runtime
- parallel loops, converting from OpenMP to the Concurrency Runtime
ms.assetid: d8a7b656-f86c-456e-9c5d-a7d52f94646e
ms.openlocfilehash: bc408465f34f0558e9f426ae35b83d4610898414
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413894"
---
# <a name="how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime"></a>방법: OpenMP parallel for 루프 동시성 런타임을 사용 하 여 변환

이 예제에는 OpenMP를 사용 하는 기본 루프를 변환 하는 방법을 보여 줍니다 [병렬](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel) 하 고 [에 대 한](../../parallel/openmp/reference/for-openmp.md) 동시성 런타임을 사용 하는 지시문 [concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for) 알고리즘입니다.

## <a name="example"></a>예제

이 예제에서는 OpenMP와 동시성 런타임을 난수 값의 배열에서 소수의 수를 계산 합니다.

[!code-cpp[concrt-openmp#1](../../parallel/concrt/codesnippet/cpp/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime_1.cpp)]

이 예제의 결과는 다음과 같습니다.

```Output
Using OpenMP...
found 107254 prime numbers.
Using the Concurrency Runtime...
found 107254 prime numbers.
```

`parallel_for` 알고리즘과 OpenMP 3.0 허용 인덱스 형식이 부호 있는 정수 계열 형식 또는 부호 없는 정수 계열 형식 이어야 합니다. `parallel_for` 알고리즘 또한 하면 지정된 된 범위는 부호 있는 형식이 오버플로 하지 않습니다. OpenMP 버전 2.0 및 2.5 부호 있는 정수 인덱스 유형의 경우에 허용합니다. 또한 OpenMP는 인덱스 범위를 확인 하지 않습니다.

동시성 런타임을 사용 하는이 예제의 버전도 사용을 [concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) 대신 개체를 [원자성](../../parallel/openmp/reference/atomic.md) 없이 카운터 값을 증가 시킬 지시문 동기화 합니다.

에 대 한 자세한 내용은 `parallel_for` 및 기타 병렬 알고리즘을 참조 하십시오 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)합니다. 에 대 한 자세한 내용은 합니다 `combinable` 클래스를 참조 하십시오 [병렬 컨테이너 및 개체](../../parallel/concrt/parallel-containers-and-objects.md)합니다.

## <a name="example"></a>예제

작업할 이전 것을 수정 하는이 예제는 [std:: array](../../standard-library/array-class-stl.md) 네이티브 배열 대신 개체입니다. OpenMP 버전 2.0 및 2.5 부호 있는 정수 인덱스 형식에만 허용 하기 때문에 `parallel_for` 구성 요소에 액세스 하는 데 반복기를 사용할 수 없습니다는 C++ 병렬로 표준 라이브러리 컨테이너입니다. PPL 병렬 패턴 라이브러리 ()를 제공 합니다 [concurrency:: parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) 동시에 제공한 것과 같은 반복 컨테이너에 작업을 수행 하는 알고리즘을는 C++ 표준 라이브러리입니다. 동일한 분할 논리를 사용 하는 `parallel_for` 알고리즘에서 사용 합니다. `parallel_for_each` 알고리즘 유사는 C++ 표준 라이브러리 [std:: for_each](../../standard-library/algorithm-functions.md#for_each) 알고리즘을 한다는 점을 제외 하는 `parallel_for_each` 알고리즘이 작업을 동시에 실행.

[!code-cpp[concrt-openmp#10](../../parallel/concrt/codesnippet/cpp/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime_2.cpp)]

## <a name="compiling-the-code"></a>코드 컴파일

예제 코드를 복사하여 Visual Studio 프로젝트 또는 `concrt-omp-count-primes.cpp` 파일에 붙여넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.

**cl.exe /EHsc /openmp concrt-omp-count-primes.cpp**

## <a name="see-also"></a>참고자료

[OpenMP에서 동시성 런타임으로 마이그레이션](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)<br/>
[병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)<br/>
[병렬 컨테이너 및 개체](../../parallel/concrt/parallel-containers-and-objects.md)
