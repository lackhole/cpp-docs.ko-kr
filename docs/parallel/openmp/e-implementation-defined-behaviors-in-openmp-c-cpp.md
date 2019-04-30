---
title: E. 구현 정의 동작 OpenMP c에서 /C++
ms.date: 01/22/2019
ms.assetid: b8d660ca-9bb3-4b6b-87af-45c67d43a731
ms.openlocfilehash: 3d8e9493cad1fce02e5d482cd5e612afb44bb37b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62362759"
---
# <a name="e-implementation-defined-behaviors-in-openmp-cc"></a>E. 구현 정의 동작 OpenMP c에서 /C++

이 부록에는 "구현 시 정의 된"이 api에서를 설명 하는 동작이 요약 되어 있습니다.  각 동작은 다시 상호 참조 하도록 기본 사양에 설명 합니다.

## <a name="remarks"></a>설명

구현을 정의 하 고 해당 동작의 경우 이러한 문서에 필요 하지만이 목록이 불완전할 수 있습니다.

- **스레드 수:** 병렬 영역 스레드 수를 동적으로 조정 하지 않으면 병렬 영역에 대 한 요청 스레드의 수를 사용 하면 런타임 시스템에서 제공할 수 있는 수보다 더 하는 동안 발생 하는 경우 프로그램의 동작은 구현 시 정의 된 (9 페이지 참조).

   시각적 개체의 C++에 중첩 되지 않은 병렬 영역에 대 한 64 개 스레드 (최대) 제공 됩니다.

- **프로세서 수:** 스레드가 지정된 된 시간에 실제로 호스팅하는 실제 프로세서 수는 구현 시 정의 (10 페이지 참조).

   시각적 개체의 C++,이 숫자 상수, 아니며 운영 체제에 의해 제어 됩니다.

- **스레드는 팀을 만듭니다.** 중첩 된 병렬 영역을 실행 하는 팀에서 스레드 수는 구현 시 정의 (10 페이지 참조).

   시각적 개체의 C++을이 수는 운영 체제에 의해 결정 됩니다.

- **schedule (runtime):** 예약에 대 한 결정은 런타임까지 지연 됩니다. 일정 유형 및 청크 크기를 설정 하 여 런타임 시 선택할 수 있습니다는 `OMP_SCHEDULE` 환경 변수입니다. 이 환경 변수 설정 하지 않으면 결과 일정은 구현 시 정의 (13 페이지 참조).

   시각적 개체의 C++, 일정 유형이 `static` 청크 크기를 사용 하 여 합니다.

- **기본 일정:** Schedule 절의 없는 경우, 기본 일정은 구현 시 정의 (13 페이지 참조).

   시각적 개체의 C++를 기본 일정 유형은 `static` 청크 크기를 사용 하 여 합니다.

- **ATOMIC:** 것이 구현에서 정의 된 구현을 모두 대체 여부 `atomic` 지시문으로 `critical` 지시문 이름이 동일한 고유 (20 페이지 참조).

   시각적 개체의 C++에서 데이터를 수정 하는 경우 [원자성](reference/openmp-directives.md#atomic) 자연 맞춤에 없는 해당 속성을 만족 하는 모든 원자성 작업 한 중요 한 섹션을 사용할 경우 하나 이상의 바이트 long입니다. 그렇지 않으면 임계 섹션 사용 되지 않습니다.

- **[omp_get_num_threads](3-run-time-library-functions.md#312-omp_get_num_threads-function):** 사용자가 스레드 수를 명시적으로 설정 되지 않은, 기본값은 구현 시 정의 (9 페이지 참조).

   시각적 개체의 C++, 기본 스레드 수는 프로세서의 수와 같습니다.

- **[omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function):** 동적 스레드 조정에 대 한 기본 구현 시 정의 됩니다.

   시각적 개체의 C++을 기본값인 `FALSE`합니다.

- **[omp_set_nested](3-run-time-library-functions.md#319-omp_set_nested-function):** 중첩 된 병렬 처리를 사용 하는 경우 중첩 된 병렬 영역을 실행 하는 데 사용 되는 스레드 수가 구현이 정의 됩니다.

   시각적 개체의 C++, 운영 체제에서 스레드 수가 결정 됩니다.

- [OMP_SCHEDULE](4-environment-variables.md#41-omp_schedule) 환경 변수: 이 환경 변수에 대 한 기본값은 구현 시 정의 합니다.

   시각적 개체의 C++, 일정 유형이 `static` 청크 크기를 사용 하 여 합니다.

- [OMP_NUM_THREADS](4-environment-variables.md#42-omp_num_threads) 환경 변수: 없는 값을 지정 하는 경우는 `OMP_NUM_THREADS` 환경 변수를 지정 된 값이 아닌 양의 정수 또는 값 보다 크면 시스템에서 지원할 수 스레드의 최대 수를 사용 하는 스레드 수는 구현 시 정의 합니다.

   시각적 개체의 C++이면 지정 된 값이 0 이거나, 스레드 수는 프로세서의 수와 같습니다.  값이 64 보다 크면 스레드 수가 64입니다.

- [OMP_DYNAMIC](4-environment-variables.md#43-omp_dynamic) 환경 변수: 기본값은 구현 시 정의 합니다.

   시각적 개체의 C++을 기본값인 `FALSE`합니다.