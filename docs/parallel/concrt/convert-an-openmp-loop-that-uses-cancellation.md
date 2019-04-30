---
title: '방법: 동시성 런타임을 사용 하 여 취소를 사용 하는 OpenMP 루프 변환'
ms.date: 11/04/2016
helpviewer_keywords:
- converting from OpenMP to the Concurrency Runtime, cancellation
- cancellation, converting from OpenMP to the Concurrency Runtime
ms.assetid: 4b0b3c33-bfa9-4e96-ae08-aef245a39cbb
ms.openlocfilehash: 618e93c18173bfe3e5f5b5f3058a8bb3d61e98ec
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413946"
---
# <a name="how-to-convert-an-openmp-loop-that-uses-cancellation-to-use-the-concurrency-runtime"></a>방법: 동시성 런타임을 사용 하 여 취소를 사용 하는 OpenMP 루프 변환

병렬 루프는 모든 반복 실행할 필요가 없습니다. 예를 들어, 값을 검색 하는 알고리즘은 값을 찾은 후 종료할 수 있습니다. OpenMP는 병렬 루프를 중단 하는 메커니즘을 제공 하지 않습니다. 그러나 솔루션을 찾았습니다를 나타내기 위해 루프의 반복을 사용 하도록 설정 하려면 부울 값 또는 플래그를 사용할 수 있습니다. 동시성 런타임에서 아직 시작 되지 않은 다른 작업을 취소 하는 하나 이상의 태스크를 사용 하도록 설정 하는 기능을 제공 합니다.

이 예제에는 OpenMP를 변환 하는 방법을 보여 줍니다 [병렬](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[에 대 한](../../parallel/openmp/reference/for-openmp.md) 루프 않아도 되는 모든 반복을 실행에 대 한 동시성 런타임에서 취소 메커니즘을 사용 하도록 합니다.

## <a name="example"></a>예제

이 예제에서는 OpenMP와 동시성 런타임에서의 병렬 버전을 구현 합니다 [std::any_of](../../standard-library/algorithm-functions.md#any_of) 알고리즘입니다. 이 예제에서는 OpenMP 버전 플래그를 사용 하 여 조건에 도달 하는 모든 병렬 루프 반복 간에 조정. 동시성 런타임을 사용 하는 버전을 사용 합니다 [concurrency::structured_task_group::cancel](reference/structured-task-group-class.md#cancel) 조건이 충족 될 경우 전체 작업을 중지 하는 방법입니다.

[!code-cpp[concrt-openmp#2](../../parallel/concrt/codesnippet/cpp/convert-an-openmp-loop-that-uses-cancellation_1.cpp)]

이 예제의 결과는 다음과 같습니다.

```Output
Using OpenMP...
9114046 is in the array.
Using the Concurrency Runtime...
9114046 is in the array.
```

루프의 모든 반복 실행을 사용 하 여 OpenMP의 버전에서는 플래그를 설정 하는 경우에 합니다. 또한 작업을 자식 작업이 있는 경우, 플래그도 것 해당 자식 작업 취소를 전달할 수입니다. 동시성 런타임에서 작업 그룹이 취소 되 면 런타임이 전체 트리의 자식 작업을 포함 하 여 작업을 취소 합니다. 합니다 [concurrency:: parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) 알고리즘 태스크를 사용 하 여 작업을 수행 합니다. 따라서 루트 작업을 취소 하는 루프의 반복 하나를 계산의 전체 트리도 취소 됩니다. 작업 트리에서 취소 되 면 런타임에 새 작업을 시작 하지 않습니다. 그러나 런타임에서 완료 이미 시작 된 작업을 허용 합니다. 따라서의 경우는 `parallel_for_each` 알고리즘인 active 루프 반복 해당 리소스를 정리할 수 있습니다.

이 예의 두 버전에 둘 이상의 복사본을 검색할 값을 포함 하는 경우 여러 개의 루프 반복 결과 동시에 지정할 각 수 및 전체 작업을 취소 합니다. 문제는 조건이 충족 되 면 한 태스크만 작업을 수행 해야 하는 경우 중요 섹션과 같이 동기화 기본 형식에 사용할 수 있습니다.

또한 PPL을 사용 하는 작업을 취소 하는 예외 처리를 사용할 수 있습니다. 취소에 대 한 자세한 내용은 참조 하세요. [PPL에서의 취소](cancellation-in-the-ppl.md)합니다.

에 대 한 자세한 내용은 `parallel_for_each` 및 기타 병렬 알고리즘을 참조 하십시오 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)합니다.

## <a name="compiling-the-code"></a>코드 컴파일

예제 코드를 복사하여 Visual Studio 프로젝트 또는 `concrt-omp-parallel-any-of.cpp` 파일에 붙여넣고 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행합니다.

**cl.exe /EHsc /openmp concrt-omp-parallel-any-of.cpp**

## <a name="see-also"></a>참고자료

[OpenMP에서 동시성 런타임으로 마이그레이션](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)<br/>
[PPL에서의 취소](cancellation-in-the-ppl.md)<br/>
[병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)
