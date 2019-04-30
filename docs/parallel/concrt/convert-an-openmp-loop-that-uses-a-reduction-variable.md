---
title: '방법: 동시성 런타임을 사용 하기 위해 환산 변수를 사용 하는 OpenMP 루프 변환'
ms.date: 11/04/2016
helpviewer_keywords:
- converting from OpenMP to the Concurrency Runtime, reduction variables
- reduction variables, converting from OpenMP to the Concurrency Runtime
ms.assetid: 96623f36-5e57-4d3f-8c13-669e6cd535b1
ms.openlocfilehash: d75e115bdb1d13c9e8f45ed67d0f3993eac1b387
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413959"
---
# <a name="how-to-convert-an-openmp-loop-that-uses-a-reduction-variable-to-use-the-concurrency-runtime"></a>방법: 동시성 런타임을 사용 하기 위해 환산 변수를 사용 하는 OpenMP 루프 변환

이 예제에는 OpenMP를 변환 하는 방법을 보여 줍니다 [병렬](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[에 대 한](../../parallel/openmp/reference/for-openmp.md) 사용 하는 루프를 [감소](../../parallel/openmp/reference/reduction.md) 동시성 런타임을 사용 하는 절.

OpenMP `reduction` 절 끝의 병렬 영역 감소 작업에 적용 된 하나 이상의 스레드 전용 변수를 지정할 수 있습니다. OpenMP 미리 감소 연산자 집합을 정의 합니다. 각 환산 변수는 스칼라 여야 합니다 (예를 들어 `int`하십시오 `long`, 및 `float`). OpenMP에서 병렬 영역 감소 변수를 사용 하는 방법에 몇 가지 제한 사항을 정의 합니다.

병렬 패턴 라이브러리 (PPL)을 제공 합니다 [concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) 세분화 된 계산을 수행 하 고 다음 최종에 이러한 계산을 병합할 수 있는 재사용 가능한, 스레드 로컬 저장소를 제공 하는 클래스 결과입니다. `combinable` 클래스는 스칼라 및 복합 형식에 사용 되는 템플릿입니다. 사용 하는 `combinable` 클래스는 병렬 구문 본문에 하위 계산을 수행 하 고, 호출 하는 [concurrency::combinable::combine](reference/combinable-class.md#combine) 하거나 [concurrency::combinable::combine_each](reference/combinable-class.md#combine_each) 최종 결과 생성 하는 메서드. `combine` 하 고 `combine_each` 메서드는 각각을 *함수를 결합* 의 각 요소 쌍을 결합 하는 방법을 지정 하는 합니다. 따라서는 `combinable` 클래스 감소 연산자의 고정된 된 집합으로 제한 되지 않습니다.

## <a name="example"></a>예제

이 예제에서는 먼저 35 피보나치 숫자의 합계를 계산 하 OpenMP와 동시성 런타임을 사용 합니다.

[!code-cpp[concrt-openmp#7](../../parallel/concrt/codesnippet/cpp/convert-an-openmp-loop-that-uses-a-reduction-variable_1.cpp)]

이 예제의 결과는 다음과 같습니다.

```Output
Using OpenMP...
The sum of the first 35 Fibonacci numbers is 14930351.
Using the Concurrency Runtime...
The sum of the first 35 Fibonacci numbers is 14930351.
```

에 대 한 자세한 내용은 합니다 `combinable` 클래스를 참조 하십시오 [병렬 컨테이너 및 개체](../../parallel/concrt/parallel-containers-and-objects.md)합니다.

## <a name="compiling-the-code"></a>코드 컴파일

예제 코드를 복사하여 Visual Studio 프로젝트 또는 `concrt-omp-fibonacci-reduction.cpp` 파일에 붙여넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.

**cl.exe /EHsc /openmp concrt-omp-fibonacci-reduction.cpp**

## <a name="see-also"></a>참고자료

[OpenMP에서 동시성 런타임으로 마이그레이션](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)<br/>
[병렬 컨테이너 및 개체](../../parallel/concrt/parallel-containers-and-objects.md)
