---
title: OpenMP 환경 변수
ms.date: 03/20/2019
f1_keywords:
- OpenMP environment variables
- OMP_DYNAMIC
- OMP_NESTED
- OMP_NUM_THREADS
- OMP_SCHEDULE
helpviewer_keywords:
- OpenMP environment variables
- OMP_DYNAMIC OpenMP environment variable
- OMP_NESTED OpenMP environment variable
- OMP_NUM_THREADS OpenMP environment variable
- OMP_SCHEDULE OpenMP environment variable
ms.assetid: 2178ce2b-ffa1-45ec-a455-64437711d15d
ms.openlocfilehash: 73fb11db14df22e5df95fdec556ccdfc16a935e5
ms.sourcegitcommit: 14b292596bc9b9b883a9c58cd3e366b282a1f7b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60124969"
---
# <a name="openmp-environment-variables"></a>OpenMP 환경 변수

OpenMP API에서 사용 되는 환경 변수를 제공 합니다.

시각적 개체 C++ OpenMP 표준의 구현을 다음 환경 변수를 포함 합니다. 이러한 환경 변수는 프로그램 시작 시 읽고 수정 값으로는 런타임 시 무시 됩니다 (예를 들어,를 사용 하 여 [_putenv, _wputenv](../../../c-runtime-library/reference/putenv-wputenv.md)).

|환경 변수|설명|
|--------------------|-----------|
|[OMP_SCHEDULE](#omp-schedule)|동작을 수정 합니다 [일정](openmp-clauses.md#schedule) 절 때 `schedule(runtime)` 에 지정 된을 `for` 또는 `parallel for` 지시문입니다.|
|[OMP_NUM_THREADS](#omp-num-threads)|의해 재정의 되지 않는 병렬 지역의 스레드의 최대 수를 설정 [omp_set_num_threads](openmp-functions.md#omp-set-num-threads) 하거나 [num_threads](openmp-clauses.md#num-threads)합니다.|
|[OMP_DYNAMIC](#omp-dynamic)|런타임에 OpenMP 병렬 영역에서 스레드 수를 조정할 수 있는지 여부를 지정 합니다.|
|[OMP_NESTED](#omp-nested)|중첩 된 병렬 처리 사용 하도록 설정 하거나 해제 되는 경우가 아니면 중첩 된 병렬 처리는 사용 여부를 지정 `omp_set_nested`합니다.|

## <a name="omp-dynamic"></a>OMP_DYNAMIC

런타임에 OpenMP 병렬 영역에서 스레드 수를 조정할 수 있는지 여부를 지정 합니다.

```
set OMP_DYNAMIC[=TRUE | =FALSE]
```

### <a name="remarks"></a>설명

합니다 `OMP_DYNAMIC` 환경 변수 재정의 될 수 있습니다 합니다 [omp_set_dynamic](openmp-functions.md#omp-set-dynamic) 함수입니다.

시각적 개체의 기본 값 C++ OpenMP 표준의 구현은 `OMP_DYNAMIC=FALSE`합니다.

자세한 내용은 [4.3 OMP_DYNAMIC](../../../parallel/openmp/4-3-omp-dynamic.md)합니다.

### <a name="example"></a>예제

다음 명령 집합을 `OMP_DYNAMIC` 로 환경 변수:

```
set OMP_DYNAMIC=TRUE
```

다음 명령은의 현재 설정을 표시는 `OMP_DYNAMIC` 환경 변수:

```
set OMP_DYNAMIC
```

## <a name="omp-nested"></a>OMP_NESTED

중첩 된 병렬 처리 사용 하도록 설정 하거나 해제 되는 경우가 아니면 중첩 된 병렬 처리는 사용 여부를 지정 `omp_set_nested`합니다.

```
set OMP_NESTED[=TRUE | =FALSE]
```

### <a name="remarks"></a>설명

합니다 `OMP_NESTED` 환경 변수 재정의 될 수 있습니다 합니다 [omp_set_nested](openmp-functions.md#omp-set-nested) 함수입니다.

시각적 개체의 기본 값 C++ OpenMP 표준의 구현은 `OMP_DYNAMIC=FALSE`합니다.

자세한 내용은 [4.4 OMP_NESTED](../../../parallel/openmp/4-4-omp-nested.md)합니다.

### <a name="example"></a>예제

다음 명령 집합을 `OMP_NESTED` 로 환경 변수:

```
set OMP_NESTED=TRUE
```

다음 명령은의 현재 설정을 표시는 `OMP_NESTED` 환경 변수:

```
set OMP_NESTED
```

## <a name="omp-num-threads"></a>OMP_NUM_THREADS

의해 재정의 되지 않는 병렬 지역의 스레드의 최대 수를 설정 [omp_set_num_threads](openmp-functions.md#omp-set-num-threads) 하거나 [num_threads](openmp-clauses.md#num-threads)합니다.

```
set OMP_NUM_THREADS[=num]
```

### <a name="parameters"></a>매개 변수

*num*<br/>
시각적 개체에서 64 최대 병렬 지역의 하려는 스레드의 최대 수 C++ 구현입니다.

### <a name="remarks"></a>설명

합니다 `OMP_NUM_THREADS` 환경 변수 재정의 될 수 있습니다 합니다 [omp_set_num_threads](openmp-functions.md#omp-set-num-threads) 함수 또는 [num_threads](openmp-clauses.md#num-threads)합니다.

기본값인 `num` 시각적 개체에서 C++ OpenMP 표준 구현의 하이퍼 스레딩을 Cpu를 포함 하 여 가상 프로세서의 수입니다.

자세한 내용은 [4.2 OMP_NUM_THREADS](../../../parallel/openmp/4-2-omp-num-threads.md)합니다.

### <a name="example"></a>예제

다음 명령 집합을 `OMP_NUM_THREADS` 환경 변수를 `16`:

```
set OMP_NUM_THREADS=16
```

다음 명령은의 현재 설정을 표시는 `OMP_NUM_THREADS` 환경 변수:

```
set OMP_NUM_THREADS
```

## <a name="omp-schedule"></a>OMP_SCHEDULE

동작을 수정 합니다 [일정](openmp-clauses.md#schedule) 절 때 `schedule(runtime)` 에 지정 된을 `for` 또는 `parallel for` 지시문입니다.

```
set OMP_SCHEDULE[=type[,size]]
```

### <a name="parameters"></a>매개 변수

*size*<br/>
(선택 사항) 반복의 크기를 지정합니다. *크기* 양의 정수 여야 합니다. 기본값은 `1`, 경우를 제외 하 고 *형식* 고정 됩니다. 유효 하지 않은 경우 *형식* 는 `runtime`합니다.

*type*<br/>
예약 하거나 종류가 `dynamic`, `guided`를 `runtime`, 또는 `static`합니다.

### <a name="remarks"></a>설명

시각적 개체의 기본 값 C++ OpenMP 표준의 구현은 `OMP_SCHEDULE=static,0`합니다.

자세한 내용은 [4.1 OMP_SCHEDULE](../../../parallel/openmp/4-1-omp-schedule.md)합니다.

### <a name="example"></a>예제

다음 명령 집합을 `OMP_SCHEDULE` 환경 변수:

```
set OMP_SCHEDULE="guided,2"
```

다음 명령은의 현재 설정을 표시는 `OMP_SCHEDULE` 환경 변수:

```
set OMP_SCHEDULE
```
