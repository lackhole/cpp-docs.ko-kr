---
title: F. 버전 2.0에서에서 새 기능 및 설명
ms.date: 01/22/2019
ms.assetid: 0d4beb66-f2d5-468c-8cd3-4b00dcbab061
ms.openlocfilehash: 2e186bbc82f4f43e831dd05cdded2a9e946d1dd2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62362716"
---
# <a name="f-new-features-and-clarifications-in-version-20"></a>F. 버전 2.0에서에서 새 기능 및 설명

이 부록 요약 OpenMP C에 대 한 주요 변경 사항 /C++ 사양 버전 1.0에서에서 2.0 버전으로 이동 합니다. 다음 항목은 사양에 추가 하는 새로운 기능:

- Openmp에서 쉼표 수 [지시문](2-directives.md#21-directive-format)합니다.

- 추가 된 `num_threads` 절. 이 절을 사용 하면 사용자에 대 한 스레드 수는 특정 요청을 [병렬 구문](2-directives.md#23-parallel-construct)합니다.

- 합니다 [threadprivate](2-directives.md#271-threadprivate-directive) 지시문 정적 블록 범위 변수를 허용 하도록 확장 되었습니다.

- C99 가변 길이 배열 완전 한 형식이 및 지정할 수 있습니다 어디서 나 전체 형식은 허용 등에서 목록의 `private`, `firstprivate`, 및 `lastprivate` 절 (참조 [2.7.2 섹션](2-directives.md#272-data-sharing-attribute-clauses)).

- 병렬 영역에서 전용 변수를 표시할 수 있습니다 [개인](2-directives.md#2721-private) 중첩 된 지시문에서 다시 합니다.

- `copyprivate` 절이 추가 되었습니다. 다른 구성원에 게 팀의 한 멤버에서 값을 브로드캐스트 개인 변수를 사용 하는 메커니즘을 제공 합니다. 경우에 공유 변수를 제공 (예를 들어, 각 수준에서 서로 다른 변수를 요구 하는 재귀)에서 어려운 값에 대 한 공유 변수를 사용 하는 대신 것입니다. 합니다 [copyprivate](2-directives.md#2728-copyprivate) 절 에서만 나타날 수 있습니다는 `single` 지시문입니다.

- 또한 타이밍 루틴 [omp_get_wtick](3-run-time-library-functions.md#332-omp_get_wtick-function) 및 [omp_get_wtime](3-run-time-library-functions.md#331-omp_get_wtime-function) MPI 루틴 비슷합니다. 이러한 함수는 클록 타이밍 벽 수행 해야 합니다.

- 목록이 포함 된 부록도 [구현에서 정의 된 동작](e-implementation-defined-behaviors-in-openmp-c-cpp.md) OpenMP c에서 /C++ 추가 되었습니다. 구현을 정의 하 고 이러한 경우 해당 동작을 문서에 필요 합니다.

- 다음과 같이 변경 명확 하거나 C에 대 한 이전 OpenMP API 사양에 기능을 수정 하는 역할 /C++:

  - 된다고의 동작 [omp_set_nested](3-run-time-library-functions.md#319-omp_set_nested-function) 하 고 [omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function) 때 `omp_in_parallel` 0이 아닌 반환이 정의 되지 않습니다.

  - 설명이 명시 되었습니다 [지시문 중첩](2-directives.md#29-directive-nesting) 중첩 된 병렬을 사용 하는 경우.

  - 합니다 [초기화 잠금](3-run-time-library-functions.md#321-omp_init_lock-and-omp_init_nest_lock-functions) 하 고 [소멸 잠금](3-run-time-library-functions.md#322-omp_destroy_lock-and-omp_destroy_nest_lock-functions) 병렬 영역에서 함수를 호출할 수 있습니다.

  - 새 예제에 추가 되었습니다 [부록 A](a-examples.md)합니다.