---
title: OpenMP에서 동시성 런타임으로 마이그레이션
ms.date: 11/04/2016
helpviewer_keywords:
- Concurrency Runtime, migrating from OpenMP
- OpenMP, migrating to the Concurrency Runtime
ms.assetid: 9bab7bb1-e45d-44b2-8509-3b226be2c93b
ms.openlocfilehash: 16b0f175867e18e127997749098cce998674b3d2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412672"
---
# <a name="migrating-from-openmp-to-the-concurrency-runtime"></a>OpenMP에서 동시성 런타임으로 마이그레이션

동시성 런타임은 다양한 프로그래밍 모델을 사용합니다. 이러한 모델은 중복되거나 다른 라이브러리의 모델을 보완할 수 있습니다. 이 문서의 섹션 비교 [OpenMP](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md#openmp) 동시성 런타임으로 동시성 런타임을 사용 하도록 기존 OpenMP 코드를 마이그레이션하는 방법에 대 한 예제를 제공 합니다.

OpenMP 프로그래밍 모델은 공개 표준에 의해 정의되며, Fortran 및 C/C++ 프로그래밍 언어에 대한 잘 정의된 바인딩을 가지고 있습니다. OpenMP 버전 2.0 및 2.5 시각적 개체에서 지원 되는 C++ 컴파일러는 반복적인;는 병렬 알고리즘에 적합된 즉, 데이터의 배열에 대해 병렬 반복을 수행 합니다. OpenMP 3.0 반복적인 작업 외에 비 반복 작업을 지원합니다.

OpenMP는 병렬 처리 수준이 미리 결정되어 있고 시스템에서 사용 가능한 리소스와 일치할 때 가장 효율적입니다. OpenMP 모델은 대규모 컴퓨팅 문제가 한 컴퓨터의 처리 리소스 간에 분산 되어 있는 고성능 컴퓨팅, 특히 적합 합니다. 이 시나리오에서는 하드웨어 환경이 일반적으로 고정 되어 있고 개발자는 알고리즘이 실행 될 때 모든 컴퓨팅 리소스에 대 한 단독 액세스를 가질 수 있습니다.

그러나 제한 된 컴퓨팅 환경 덜 수 없습니다 OpenMP의 적합성이. 예를 들어 재귀적 문제 (예: 빠른 정렬 알고리즘 또는 데이터 트리 검색)는 OpenMP 2.0 및 2.5를 사용 하 여 구현 하기가 더 어렵습니다. 동시성 런타임에서 제공 하 여 OpenMP의 기능을 보완 합니다 [비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md) 하며 [병렬 패턴 라이브러리](../../parallel/concrt/parallel-patterns-library-ppl.md) (PPL). 비동기 에이전트 라이브러리는 정교 하지 않은 작업 병렬 처리; 지원 PPL 더 세분화 된 병렬 작업을 지원합니다. 동시성 런타임은 응용 프로그램의 논리에 집중할 수 있도록 병렬로 작업을 수행 하는 데 필요한 인프라를 제공 합니다. 그러나 동시성 런타임은 다양 한 프로그래밍 모델 때문에 예약 오버 헤드가 보다 클 수 OpenMP 등의 기타 동시성 라이브러리입니다. 따라서 성능을 테스트 하는 증분 방식으로 동시성 런타임을 사용 하도록 기존 OpenMP 코드를 변환 하는 것이 좋습니다.

## <a name="when-to-migrate-from-openmp-to-the-concurrency-runtime"></a>OpenMP에서 동시성 런타임으로 마이그레이션 시기

다음 경우에 동시성 런타임을 사용 하도록 기존 OpenMP 코드를 마이그레이션하는 것이 좋습니다 수도 있습니다.

|Cases|동시성 런타임의 이점|
|-----------|-------------------------------------------|
|확장 된 동시 프로그래밍 프레임 워크가 필요합니다.|동시성 런타임의 기능 중 다수는 확장 가능합니다. 기존 기능을 결합하여 새 기능을 구성할 수도 있습니다. OpenMP는 컴파일러 지시문을 사용 하기 쉽게 확장할 수 없습니다.|
|응용 프로그램에서 협조적 차단 도움이 되는 경우|아직 사용할 수 없는 리소스를 필요 하기 때문에 작업을 차단 하는 경우 동시성 런타임에서 리소스에 대 한 첫 번째 태스크 기다리면서 다른 작업을 수행할 수 있습니다.|
|응용 프로그램에 동적 부하 분산에서 도움이 됩니다.|동시성 런타임에서 작업 변화에 따라 컴퓨팅 리소스의 할당을 조정 하는 일정 알고리즘을 사용 합니다. Openmp에서는 스케줄러 병렬 영역에 컴퓨팅 리소스를 할당 하면 계산 전체적으로 해당 리소스 할당이 고정 됩니다.|
|예외 처리 지원 해야 합니다.|PPL 및 병렬 영역 또는 루프 외부에서 예외를 catch 수 있습니다. Openmp에서는 루프를 병렬 영역 내부 예외를 처리 해야 합니다.|
|취소 메커니즘이 필요합니다.|PPL 개별 태스크 및 작업의 병렬 트리 모두 취소 하는 응용 프로그램을 수 있습니다. OpenMP 자체 취소 메커니즘을 구현 하는 응용 프로그램에 필요 합니다.|
|병렬 코드를 시작 하는 다른 컨텍스트에서 완료 해야 합니다.|동시성 런타임 컨텍스트에서 작업을 시작 하 고 다음 대기 하거나 다른 컨텍스트에서 해당 작업을 취소할 수 있습니다. Openmp에서는 시작 하는 컨텍스트에서 모든 병렬 작업 완료 해야 합니다.|
|향상 된 디버깅 지원이 필요 합니다.|Visual Studio에서 제공 합니다 **병렬 스택** 하 고 **병렬 작업** windows 다중 스레드 응용 프로그램 보다 쉽게 디버깅할 수 있도록 합니다.<br /><br /> 동시성 런타임에 대 한 디버깅 지원에 대 한 자세한 내용은 참조 하세요. [작업 창 사용](/visualstudio/debugger/using-the-tasks-window)를 [병렬 스택 창 사용](/visualstudio/debugger/using-the-parallel-stacks-window), 및 [연습: 병렬 응용 프로그램을 디버깅](/visualstudio/debugger/walkthrough-debugging-a-parallel-application)합니다.|

## <a name="when-not-to-migrate-from-openmp-to-the-concurrency-runtime"></a>OpenMP에서 동시성 런타임으로 마이그레이션하 하지 않는 경우

동시성 런타임을 사용 하도록 기존 OpenMP 코드 마이그레이션에 적합 한 아닐 때 다음과 같은 경우에 설명 합니다.

|Cases|설명|
|-----------|-----------------|
|요구 사항을 충족 하는 응용 프로그램에 이미 있습니다.|응용 프로그램 성능 및 현재 디버깅 지원에 만족 하는 경우 마이그레이션을 적절 한 수 없습니다.|
|병렬 루프 본문이 약간의 작업을 수행합니다.|동시성 런타임 작업 scheduler의 오버 헤드가 루프 본문 상대적으로 적은 경우에 특히 병렬로 루프 본문을 실행 하는 이점이 크지 않을 수 있습니다.|
|C에서 작성 된 응용 프로그램|여러 동시성 런타임을 사용 하기 때문에 C++ 기능을이 적합 하지 않을 C 응용 프로그램을 완벽 하 게 사용할 수 있도록 하는 코드를 쓸 수 없는 경우.|

## <a name="related-topics"></a>관련 항목

[방법: 동시성 런타임을 사용하기 위해 OpenMP parallel for 루프 변환](../../parallel/concrt/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime.md)

OpenMP를 사용 하는 기본 루프가 지정 된 [병렬](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel) 하 고 [에 대 한](../../parallel/openmp/reference/for-openmp.md) 지시문을 동시성 런타임을 사용 하도록 변환 하는 방법을 보여 줍니다 [concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for) 알고리즘입니다.

[방법: 동시성 런타임을 사용하기 위해 취소를 사용하는 OpenMP 루프 변환](../../parallel/concrt/convert-an-openmp-loop-that-uses-cancellation.md)<br/>
OpenMP 주어진 [병렬](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[에 대 한](../../parallel/openmp/reference/for-openmp.md) 루프를 실행 하려면 모든 반복 하지 않아도 되는 동시성 런타임에서 취소 메커니즘을 사용 하도록 변환 하는 방법에 설명 합니다.

[방법: 동시성 런타임을 사용하기 위해 예외 처리를 사용하는 OpenMP 루프 변환](../../parallel/concrt/convert-an-openmp-loop-that-uses-exception-handling.md)<br/>
지정 OpenMP [병렬](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[에 대 한](../../parallel/openmp/reference/for-openmp.md) 예외 처리를 수행 하는 루프에는 동시성 런타임에서 예외 처리 메커니즘을 사용 하도록 변환 하는 방법을 보여 줍니다.

[방법: 동시성 런타임을 사용하기 위해 환산 변수를 사용하는 OpenMP 루프 변환](../../parallel/concrt/convert-an-openmp-loop-that-uses-a-reduction-variable.md)<br/>
OpenMP 지정 [병렬](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[에 대 한](../../parallel/openmp/reference/for-openmp.md) 사용 하는 루프를 [감소](../../parallel/openmp/reference/reduction.md) 절에는 동시성 런타임을 사용 하도록 변환 하는 방법을 보여 줍니다. 합니다.

## <a name="see-also"></a>참고자료

[동시성 런타임](../../parallel/concrt/concurrency-runtime.md)<br/>
[OpenMP](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md#openmp)<br/>
[PPL(병렬 패턴 라이브러리)](../../parallel/concrt/parallel-patterns-library-ppl.md)<br/>
[비동기 에이전트 라이브러리](../../parallel/concrt/asynchronous-agents-library.md)
