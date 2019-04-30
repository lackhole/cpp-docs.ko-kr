---
title: '방법: Parallel_invoke를 사용 하 여 병렬 정렬 루틴 작성'
ms.date: 11/04/2016
helpviewer_keywords:
- task_handle class, example
- task_group class, example
- make_task function, example
- structured_task_group class, example
- improving parallel performance with task groups [Concurrency Runtime]
ms.assetid: 53979a2a-525d-4437-8952-f1ff85b37673
ms.openlocfilehash: 329cf275f283ba7b57276d06e909905c9a900697
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62252934"
---
# <a name="how-to-use-parallelinvoke-to-write-a-parallel-sort-routine"></a>방법: Parallel_invoke를 사용 하 여 병렬 정렬 루틴 작성

이 문서를 사용 하는 방법에 설명 합니다 [parallel_invoke](../../parallel/concrt/parallel-algorithms.md#parallel_invoke) 바 이토 닉 정렬 알고리즘의 성능을 향상 하는 알고리즘입니다. 바 이토 닉 정렬 알고리즘 재귀적으로 입력된 시퀀스를 정렬 된 파티션을 보다 작은 나눕니다. 바 이토 닉 정렬 알고리즘은 각 파티션 작업이 다른 모든 작업과 독립적 이므로 병렬로 실행할 수 있습니다.

바 이토 닉 정렬의 예로 되어도 *정렬 네트워크* 입력된 시퀀스의 모든 조합의 정렬 하는,이 예에서는 길이가 2의 거듭제곱이 시퀀스를 정렬 합니다.

> [!NOTE]
>  이 예제에서는 이해를 돕기 위해 병렬 정렬 루틴을 사용합니다. PPL에서 제공 하는 기본 제공 정렬 알고리즘을 사용할 수도 있습니다: [concurrency:: parallel_sort](reference/concurrency-namespace-functions.md#parallel_sort)를 [concurrency:: parallel_buffered_sort](reference/concurrency-namespace-functions.md#parallel_buffered_sort), 및 [concurrency::parallel_ radixsort](reference/concurrency-namespace-functions.md#parallel_radixsort)합니다. 자세한 내용은 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)합니다.

##  <a name="top"></a> 섹션

이 문서에서는 다음 작업을 설명합니다.

- [바 이토 닉 정렬을 순차적으로 수행](#serial)

- [병렬로 수행 바 이토 닉 정렬 parallel_invoke를 사용 하 여](#parallel)

##  <a name="serial"></a> 바 이토 닉 정렬을 순차적으로 수행

다음 예제에서는 바 이토 닉 정렬 알고리즘의 직렬 버전을 나타냅니다. `bitonic_sort` 함수는 시퀀스를 두 개의 파티션으로 나누고 해당 파티션을 반대 방향으로 정렬 하 고 후 결과 병합 합니다. 각 파티션 정렬에 두 번 재귀적으로이 함수가 자신을 호출 합니다.

[!code-cpp[concrt-parallel-bitonic-sort#1](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_1.cpp)]

[[맨 위로 이동](#top)]

##  <a name="parallel"></a> 병렬로 수행 바 이토 닉 정렬 parallel_invoke를 사용 하 여

이 섹션에서는 사용 하는 방법을 설명 합니다 `parallel_invoke` 병렬로 바 이토 닉 정렬 알고리즘을 수행 하는 알고리즘입니다.

### <a name="procedures"></a>절차

##### <a name="to-perform-the-bitonic-sort-algorithm-in-parallel"></a>병렬로 여 바 이토 닉 정렬 알고리즘을 수행 하려면

1. 추가 된 `#include` 헤더 파일 ppl.h에 대 한 지시문입니다.

[!code-cpp[concrt-parallel-bitonic-sort#10](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_2.cpp)]

1. 추가 된 `using` 지시문에 대 한는 `concurrency` 네임 스페이스입니다.

[!code-cpp[concrt-parallel-bitonic-sort#11](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_3.cpp)]

1. 라는 새 함수를 만듭니다 `parallel_bitonic_mege`를 사용 하는 `parallel_invoke` 충분 한 양의 작업을 수행 하는 경우 병렬에서 시퀀스를 병합 하는 알고리즘입니다. 그렇지 않으면 호출 `bitonic_merge` 시퀀스를 순차적으로 병합 합니다.

[!code-cpp[concrt-parallel-bitonic-sort#2](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_4.cpp)]

1. 와 유사 하지만 이전 단계에서 프로세스를 수행 합니다 `bitonic_sort` 함수입니다.

[!code-cpp[concrt-parallel-bitonic-sort#3](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_5.cpp)]

1. 오버 로드 된 버전을 만들려면는 `parallel_bitonic_sort` 배열 오름차순으로 정렬 하는 함수입니다.

[!code-cpp[concrt-parallel-bitonic-sort#4](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_6.cpp)]

`parallel_invoke` 알고리즘 호출 컨텍스트에서 일련의 작업 중 마지막 작업을 수행 하 여 오버 헤드를 줄입니다. 예를 들어,는 `parallel_bitonic_sort` 함수에는 별도 컨텍스트에서 첫 번째 작업을 실행 및 두 번째 작업 호출 컨텍스트에서 실행 됩니다.

[!code-cpp[concrt-parallel-bitonic-sort#5](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_7.cpp)]

다음 전체 예제는 직렬 버전과 바 이토 닉 정렬 알고리즘의 병렬 버전을 모두 수행합니다. 예제도 콘솔에 출력의 각 계산을 수행 하는 데 필요한 시간.

[!code-cpp[concrt-parallel-bitonic-sort#8](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_8.cpp)]

다음 샘플은 프로세서가 4개인 컴퓨터에 대한 출력입니다.

```Output
serial time: 4353
parallel time: 1248
```

[[맨 위로 이동](#top)]

## <a name="compiling-the-code"></a>코드 컴파일

컴파일하려면 코드를 복사 하 고 다음 Visual Studio 프로젝트에 붙여 넣습니다와 라는 파일에 붙여 `parallel-bitonic-sort.cpp` Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.

**cl.exe /EHsc 병렬-바 이토 닉-sort.cpp**

## <a name="robust-programming"></a>강력한 프로그래밍

이 예제에서는 합니다 `parallel_invoke` 대신 알고리즘 합니다 [concurrency:: task_group](reference/task-group-class.md) 함수 보다 짧기 각 작업 그룹의 수명 동안 때문에 클래스. 사용 하는 것이 좋습니다 `parallel_invoke` 적은 보다 실행 오버 헤드가 있으므로 가능한 경우 `task group` 개체와 더 잘 수행 되는 코드를 작성할 수 있습니다.

일부 알고리즘의 병렬 버전은 충분 한 작업을 수행 하는 경우에 성능이 우수 합니다. 예를 들어 합니다 `parallel_bitonic_merge` 함수 호출은 직렬 버전과 `bitonic_merge`이면 시퀀스에 500 개 이하의 요소입니다. 또한 작업의 양에 따라 전체 정렬 전략을 계획할 수 있습니다. 예를 들어, 더 효율적으로 다음 예와에서 같이 500 개 미만의 항목을 포함 하는 경우 빠른 정렬 알고리즘은 직렬 버전과 사용할 수 있습니다.

[!code-cpp[concrt-parallel-bitonic-sort#9](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_9.cpp)]

모든 병렬 알고리즘에서와 마찬가지로 프로 파일링 하 고 적절 하 게 코드를 조정 하는 것이 좋습니다.

## <a name="see-also"></a>참고자료

[작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[parallel_invoke 함수](reference/concurrency-namespace-functions.md#parallel_invoke)
