---
title: 4. 환경 변수
ms.date: 01/16/2019
ms.assetid: 4ec7ed81-e9ca-46a1-84f8-8f9ce4587346
ms.openlocfilehash: b41829fd9cf2f90312f669ef991f56dda02947f7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62363195"
---
# <a name="4-environment-variables"></a>4. 환경 변수

이 장에서 설명 OpenMP C 및 C++ API 환경 변수 (또는 비슷한 플랫폼별 메커니즘)는 병렬 코드의 실행을 제어 합니다.  환경 변수 이름이 대문자 여야 합니다. 에 할당 된 값은 대/소문자 구분 되며 선행 및 후행 공백은 있을 수 있습니다.  수정 프로그램을 시작한 후 값은 무시 됩니다.

환경 변수는 다음과 같습니다.

- [OMP_SCHEDULE](#41-omp_schedule) 런타임 일정 유형 및 청크 크기를 설정 합니다.
- [OMP_NUM_THREADS](#42-omp_num_threads) 실행 하는 동안 사용할 스레드 수를 설정 합니다.
- [OMP_DYNAMIC](#43-omp_dynamic) 하거나 스레드 수를 동적으로 조정 해야 하는 항목을 사용 하지 않도록 설정 합니다.
- [OMP_NESTED](#44-omp_nested) 하거나 중첩 된 병렬 처리를 사용 하지 않도록 설정 합니다.

이 챕터에 예제만 Unix C 셸 (csh) 환경에서 이러한 변수를 설정할 수 있습니다 하는 방법을 보여 줍니다. Korn 셸 및 DOS 환경에서 작업은 유사 합니다.

csh:  
`setenv OMP_SCHEDULE "dynamic"`

ksh:  
`export OMP_SCHEDULE="dynamic"`

DOS:  
`set OMP_SCHEDULE="dynamic"`

## <a name="41-omp_schedule"></a>4.1 OMP_SCHEDULE

`OMP_SCHEDULE` 에 적용 됩니다 `for` 하 고 `parallel for` 일정 유형을 가진 지시문 `runtime`합니다. 런타임 시 이러한 모든 루프에 대 한 일정 유형 및 청크 크기를 설정할 수 있습니다. 모든 인식된 일정 유형을 선택적으로이 환경 변수를 설정 *chunk_size*합니다.

에 대 한 `for` 하 고 `parallel for` 이외의 일정 유형에 있는 지시문 `runtime`, `OMP_SCHEDULE` 무시 됩니다. 이 환경 변수에 대 한 기본값은 구현 시 정의 합니다. 경우 선택적 *chunk_size* 설정, 값은 양수 여야 합니다. 하는 경우 *chunk_size* 설정, 일정 인 경우 제외, 값이 1으로 간주 되지 않습니다 `static`합니다. 에 대 한는 `static` 일정을 기본 청크 크기 루프 반복 공간 루프에 적용 되는 스레드의 수로 나눈 값에 설정 됩니다.

예제:

```csh
setenv OMP_SCHEDULE "guided,4"
setenv OMP_SCHEDULE "dynamic"
```

### <a name="cross-references"></a>상호 참조

- [에 대 한](2-directives.md#241-for-construct) 지시문
- [에 대 한 병렬](2-directives.md#251-parallel-for-construct) 지시문

## <a name="42-omp_num_threads"></a>4.2 OMP_NUM_THREADS

`OMP_NUM_THREADS` 기본 실행 하는 동안 사용할 스레드 수를 설정 하는 환경 변수입니다. `OMP_NUM_THREADS` 해당 숫자를 호출 하 여 명시적으로 변경 하는 경우 무시 됩니다는 `omp_set_num_threads` 라이브러리 루틴입니다. 명시적인 없는 경우에이 무시 됩니다 됩니다 `num_threads` 절을 `parallel` 지시문입니다.

값을 `OMP_NUM_THREADS` 환경 변수는 양의 정수 여야 합니다. 미치는은 스레드 수를 동적으로 조정 활성화 되어 있는지 여부에 따라 다릅니다. 포괄적인 간의 상호 작용에 대 한 규칙에 대 한 합니다 `OMP_NUM_THREADS` 환경 변수 및 동적 조정 하는 스레드를 참조 하세요 [2.3 섹션](2-directives.md#23-parallel-construct)합니다.

사용할 스레드 수는 구현 시 정의 하는 경우:

- `OMP_NUM_THREADS` 환경 변수를 지정 하지 않으면
- 지정 된 값이 아닌 양의 정수 또는
- 값을 시스템에서 지원할 수 있는 스레드의 최대 수보다 큽니다.

예제:

```csh
setenv OMP_NUM_THREADS 16
```

### <a name="cross-references"></a>상호 참조

- [num_threads](2-directives.md#23-parallel-construct) 절
- [omp_set_num_threads](3-run-time-library-functions.md#311-omp_set_num_threads-function) function
- [omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function) function

## <a name="43-omp_dynamic"></a>4.3 OMP_DYNAMIC

`OMP_DYNAMIC` 환경 변수를 사용할지 지역 병렬 실행을 위해 사용할 수 있는 스레드 수를 동적으로 조정 합니다. `OMP_DYNAMIC` 동적으로 조정 하는 명시적으로 사용할지를 호출 하 여 사용 하지 않도록 설정 하는 경우 무시 됩니다는 `omp_set_dynamic` 라이브러리 루틴입니다. 해당 값 이어야 합니다 `TRUE` 또는 `FALSE`합니다.

하는 경우 `OMP_DYNAMIC` 로 설정 된 `TRUE`, 시스템 리소스를 최대한 활용 하려면 런타임 환경에서 병렬 영역을 실행 하는 데 사용 되는 스레드 수가 조정 될 수 있습니다.  하는 경우 `OMP_DYNAMIC` 로 설정 된 `FALSE`를 동적으로 조정 하는 사용 하지 않도록 설정 합니다. 기본 조건을 구현 시 정의 됩니다.

예제:

```csh
setenv OMP_DYNAMIC TRUE
```

### <a name="cross-references"></a>상호 참조

- [병렬 영역](2-directives.md#23-parallel-construct)
- [omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function) function

## <a name="44-omp_nested"></a>4.4 OMP_NESTED

`OMP_NESTED` 환경 변수 사용 하거나 중첩 된 병렬 처리는 사용 하도록 설정 하거나 호출 하 여 사용 하지 않도록 설정 하지 않는 한 중첩 된 병렬 처리를 사용 하지 않도록 설정 된 `omp_set_nested` 라이브러리 루틴입니다. 하는 경우 `OMP_NESTED` 로 설정 된 `TRUE`, 중첩 된 병렬 처리 사용 하도록 설정 합니다. 하는 경우 `OMP_NESTED` 로 설정 된 `FALSE`중첩 된 병렬 처리를 사용 하지 않도록 설정 합니다. 기본값은 `FALSE`입니다.

예제:

```csh
setenv OMP_NESTED TRUE
```

### <a name="cross-reference"></a>상호 참조

- [omp_set_nested](3-run-time-library-functions.md#319-omp_set_nested-function) function
