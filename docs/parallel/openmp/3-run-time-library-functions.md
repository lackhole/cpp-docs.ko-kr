---
title: 3. 런타임 라이브러리 함수
ms.date: 05/13/2019
ms.assetid: b226e512-6822-4cbe-a2ca-74cc2bb7e880
ms.openlocfilehash: 7ecb2a79ad61169cdeabc9bd4893147a5de6a210
ms.sourcegitcommit: 934cb53fa4cb59fea611bfeb9db110d8d6f7d165
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65611177"
---
# <a name="3-run-time-library-functions"></a>3. 런타임 라이브러리 함수

이 섹션에서는 설명 OpenMP C 및 C++ 런타임 라이브러리 함수입니다. 헤더  **\<omp.h >** 두 형식, 제어 및 병렬 실행 환경으로 쿼리 및 데이터에 대 한 액세스를 동기화 하는 함수를 잠글 수 있는 몇 가지 함수를 선언 합니다.

형식 `omp_lock_t` 잠금 수를 표현할 수 있는 되지 않는 개체 유형 또는 스레드가 잠금을 소유 하 고 있습니다. 이러한 잠금은 이라고 *간단한 잠금을*합니다.

형식 `omp_nest_lock_t` 는 개체 형식 중 하나는 표현할 수 있는 잠금 사용 가능 하거나 잠금을 소유 하는 스레드의 id 및 *개수 중첩* (아래 설명 참조). 이러한 잠금은 이라고 *중첩 가능 잠금*합니다.

라이브러리 함수는 "C" 링크를 사용 하 여 외부 함수입니다.

이 챕터의 설명에 다음 항목으로 나뉩니다.

- [실행 환경 함수](#31-execution-environment-functions)
- [Lock 함수](#32-lock-functions)
- [타이밍 루틴](#33-timing-routines)

## <a name="31-execution-environment-functions"></a>3.1 실행 환경 함수

이 섹션에 설명 된 함수에 영향을 줄 및 스레드, 프로세서 및 병렬 환경 모니터링:

- [omp_set_num_threads](#311-omp_set_num_threads-function)
- [omp_get_num_threads](#312-omp_get_num_threads-function)
- [omp_get_max_threads](#313-omp_get_max_threads-function)
- [omp_get_thread_num](#314-omp_get_thread_num-function)
- [omp_get_num_procs](#315-omp_get_num_procs-function)
- [omp_in_parallel](#316-omp_in_parallel-function)
- [omp_set_dynamic](#317-omp_set_dynamic-function)
- [omp_get_dynamic](#318-omp_get_dynamic-function)
- [omp_set_nested](#319-omp_set_nested-function)
- [omp_get_nested](#3110-omp_get_nested-function)

### <a name="311-omp_set_num_threads-function"></a>3.1.1 omp_set_num_threads 함수

합니다 `omp_set_num_threads` 기본 개수를 지정 하지 않은 병렬 영역 나중에 사용할 스레드를 설정 하는 함수를 `num_threads` 절. 형식은 다음과 같습니다.

```cpp
#include <omp.h>
void omp_set_num_threads(int num_threads);
```

매개 변수의 *num_threads* 양의 정수 여야 합니다. 미치는은 스레드 수를 동적으로 조정 활성화 되어 있는지 여부에 따라 다릅니다. 포괄적인 간의 상호 작용에 대 한 규칙에 대 한 합니다 `omp_set_num_threads` 함수 및 스레드, 동적으로 조정 참조 [2.3 섹션](2-directives.md#23-parallel-construct)합니다.

이 함수는 프로그램의 부분에서 호출 하는 경우 위에서 설명한 효과가 있는 `omp_in_parallel` 함수가 0을 반환 합니다. 프로그램의 부분에서 호출 되 면 여기서는 `omp_in_parallel` 0이 아닌 값을 반환 하는 함수,이 함수의 동작이 정의 되지 않습니다.

이 호출 보다 우선 합니다 `OMP_NUM_THREADS` 환경 변수입니다. 호출 하 여 설정할 수 있는 스레드의 수에 대 한 기본값 `omp_set_num_threads` 하거나 설정 하는 `OMP_NUM_THREADS` 단일 환경 변수를 명시적으로 재정의할 수 있습니다 `parallel` 지시문을 지정 하 여는 `num_threads` 절.

자세한 내용은 [omp_set_dynamic](#317-omp_set_dynamic-function)합니다.

#### <a name="cross-references"></a>상호 참조

- [omp_set_dynamic](#317-omp_set_dynamic-function) function
- [omp_get_dynamic](#318-omp_get_dynamic-function) function
- [OMP_NUM_THREADS](4-environment-variables.md#42-omp_num_threads) 환경 변수
- [num_threads](2-directives.md#23-parallel-construct) 절

### <a name="312-omp_get_num_threads-function"></a>3.1.2 omp_get_num_threads 함수

`omp_get_num_threads` 함수의 수를 반환 스레드의 현재 호출 하는 병렬 영역을 실행 하는 팀에서. 형식은 다음과 같습니다.

```cpp
#include <omp.h>
int omp_get_num_threads(void);
```

`num_threads` 절을 `omp_set_num_threads` 함수 및 `OMP_NUM_THREADS` 팀의 스레드 수를 제어 하는 환경 변수입니다.

스레드 수는 사용자가 명시적으로 설정 되지 않은, 기본 구현이 정의 됩니다. 이 함수에서 가장 가까운 바깥쪽 바인딩할 `parallel` 지시문입니다. Serialize 되는 중첩 된 병렬 영역 또는 프로그램의 직렬 부분에서 호출 되 면이 함수는 1을 반환 합니다.

자세한 내용은 [omp_set_dynamic](#317-omp_set_dynamic-function)합니다.

#### <a name="cross-references"></a>상호 참조

- [OMP_NUM_THREADS](4-environment-variables.md#42-omp_num_threads)
- [num_threads](2-directives.md#23-parallel-construct)
- [parallel](2-directives.md#23-parallel-construct)

### <a name="313-omp_get_max_threads-function"></a>3.1.3 omp_get_max_threads 함수

`omp_get_max_threads` 하는 경우 병렬 영역 없이 팀을 구성 하는 데 사용 하는 스레드의 수 이상이 되도록 보장에 정수를 반환 하는 함수를 `num_threads` 코드의 경우 이때 표시 된 절. 형식은 다음과 같습니다.

```cpp
#include <omp.h>
int omp_get_max_threads(void);
```

다음 값의 하한값을 표현 `omp_get_max_threads`:

```

threads-used-for-next-team
<= omp_get_max_threads
```

또 다른 병렬 영역 사용 합니다 `num_threads` 특정 개수의 스레드를 결과 대 한 하한값 대 한 보장을 요청 하는 절 `omp_get_max_threads` 긴 포함 되지 않습니다.

`omp_get_max_threads` 다음 병렬 영역에서 형성 된 팀의 모든 스레드에 대 한 충분 한 저장소를 동적으로 할당할 함수의 반환 값을 사용할 수 있습니다.

#### <a name="cross-references"></a>상호 참조

- [omp_get_num_threads](#312-omp_get_num_threads-function)
- [omp_set_num_threads](#311-omp_set_num_threads-function)
- [omp_set_dynamic](#317-omp_set_dynamic-function)
- [num_threads](2-directives.md#23-parallel-construct)

### <a name="314-omp_get_thread_num-function"></a>3.1.4 omp_get_thread_num 함수

`omp_get_thread_num` 함수를 실행 하는 스레드의 해당 팀 내에서 스레드 수를 반환 합니다. 스레드 번호 힘은 0 및 `omp_get_num_threads()`-1을 포함 합니다. 팀의 마스터 스레드는 스레드 0입니다.

형식은 다음과 같습니다.

```cpp
#include <omp.h>
int omp_get_thread_num(void);
```

직렬 지역에서 호출 된 경우 `omp_get_thread_num` 0을 반환 합니다. Serialize 되는 중첩 된 병렬 영역 내부에서 호출 하는 경우이 함수는 0을 반환 합니다.

#### <a name="cross-references"></a>상호 참조

- [omp_get_num_threads](#312-omp_get_num_threads-function) 함수

### <a name="315-omp_get_num_procs-function"></a>3.1.5 omp_get_num_procs 함수

`omp_get_num_procs` 함수의 함수 호출 시 프로그램에 사용할 수 있는 프로세서의 수를 반환 합니다. 형식은 다음과 같습니다.

```cpp
#include <omp.h>
int omp_get_num_procs(void);
```

### <a name="316-omp_in_parallel-function"></a>3.1.6 omp_in_parallel 함수

`omp_in_parallel` 병렬로 실행 하는 병렬 영역 동적 범위 내에서 호출 되 면 함수는 0이 아닌 값을 반환, 그렇지 않으면 0을 반환 합니다. 형식은 다음과 같습니다.

```cpp
#include <omp.h>
int omp_in_parallel(void);
```

이 함수에는 serialize 되는 중첩 된 영역을 포함 하 여 병렬로 실행 하는 지역 내에서 호출 될 경우 0이 아닌 값을 반환 합니다.

### <a name="317-omp_set_dynamic-function"></a>3.1.7 omp_set_dynamic 함수

`omp_set_dynamic` 함수를 사용할지 지역 병렬 실행에 사용 가능한 스레드 수를 동적으로 조정 합니다. 형식은 다음과 같습니다.

```cpp
#include <omp.h>
void omp_set_dynamic(int dynamic_threads);
```

하는 경우 *dynamic_threads* 평가 0이 아닌 값으로 예정 된 병렬 영역을 실행 하는 데 사용 되는 스레드 수가 조정 될 수 있습니다 자동으로 시스템 리소스를 최대한 활용 하려면 런타임 환경에서. 결과적으로 사용자가 지정 된 스레드 수가 최대 스레드 수입니다. 병렬 영역을 실행 하는 팀의 스레드 수가 병렬 영역은 해당 기간에 대 한 고정 됩니다 및에서 보고 되는 `omp_get_num_threads` 함수입니다.

하는 경우 *dynamic_threads* 평가를 0으로 동적으로 조정 하는 사용 하지 않도록 설정 합니다.

이 함수는 프로그램의 부분에서 호출 하는 경우 위에서 설명한 효과가 있는 `omp_in_parallel` 함수가 0을 반환 합니다. 프로그램의 부분에서 호출 되 면 여기서는 `omp_in_parallel` 0이 아닌 값을 반환 하는 함수,이 함수의 동작이 정의 되지 않습니다.

에 대 한 호출 `omp_set_dynamic` 보다 우선 합니다 `OMP_DYNAMIC` 환경 변수입니다.

스레드를 동적으로 조정 해야 하는 항목에 대 한 기본 구현 시 정의 됩니다. 결과적으로, 특정 수의 올바른 실행에 대 한 스레드를에 의존 하는 사용자 코드는 동적 스레드 명시적으로 해제 해야 합니다. 구현에서는 스레드 수를 동적으로 조정 하는 기능을 제공 하는 데 필요한 되지 않습니다 하지만 모든 플랫폼 이식성을 지 원하는 인터페이스를 제공 해야 합니다.

#### <a name="microsoft-specific"></a>Microsoft 전용

현재 지원은 `omp_get_dynamic` 고 `omp_set_dynamic` 는 다음과 같습니다. 

입력된 매개 변수를 `omp_set_dynamic` 스레딩 정책의 영향을 주지 않습니다 및 스레드 수를 변경 되지 않습니다. `omp_get_num_threads` 항상 사용자 수, 설정 된 경우 또는 기본 스레드 수를 반환 합니다. 현재 Microsoft 구현에서 `omp_set_dynamic(0)` 다음 병렬 영역에 대 한 기존 스레드의 집합을 다시 사용할 수 있도록 동적 스레드를 해제 합니다. `omp_set_dynamic(1)` 기존 스레드 집합을 삭제 하 고 예정 된 병렬 영역에 대 한 새 집합을 만들어 동적 스레딩을 켭니다. 새로운 집합의 스레드 수가 이전 집합 동일 및 반환 값에 기반 `omp_get_num_threads`입니다. 따라서 최상의 성능을 위해 사용 하 여 `omp_set_dynamic(0)` 기존 스레드를 다시 사용 합니다.

#### <a name="cross-references"></a>상호 참조

- [omp_get_num_threads](#312-omp_get_num_threads-function)
- [OMP_DYNAMIC](4-environment-variables.md#43-omp_dynamic)
- [omp_in_parallel](#316-omp_in_parallel-function)

### <a name="318-omp_get_dynamic-function"></a>3.1.8 omp_get_dynamic 함수

`omp_get_dynamic` 스레드를 동적으로 조정 사용 하 고 그렇지 않으면 0을 반환 하는 경우 함수는 0이 아닌 값을 반환 합니다. 형식은 다음과 같습니다.

```cpp
#include <omp.h>
int omp_get_dynamic(void);
```

구현에는 스레드 수를 동적으로 조정 구현 하지 않는, 경우이 함수는 항상 0을 반환 합니다. 자세한 내용은 [omp_set_dynamic](#317-omp_set_dynamic-function)합니다.

#### <a name="cross-references"></a>상호 참조

- 동적 스레드 조정에 대 한 참조 [omp_set_dynamic](#317-omp_set_dynamic-function)합니다.

### <a name="319-omp_set_nested-function"></a>3.1.9 omp_set_nested 함수

`omp_set_nested` 함수 하거나 중첩 된 병렬 처리를 사용 하지 않도록 설정 합니다. 형식은 다음과 같습니다.

```cpp
#include <omp.h>
void omp_set_nested(int nested);
```

경우 *중첩 된* 중첩 0으로 계산 되는 기본적으로 병렬 처리 해제 되 고 중첩 된 병렬 영역은 직렬화 되 고 현재 스레드에서 실행 합니다. 그렇지 않으면 중첩 된 병렬 처리를 사용 하 고 중첩 된 병렬 영역 중첩된 팀을 구성 하기 위한 추가 스레드도 배포할 수 있습니다.

이 함수는 프로그램의 부분에서 호출 하는 경우 위에서 설명한 효과가 있는 `omp_in_parallel` 함수가 0을 반환 합니다. 프로그램의 부분에서 호출 되 면 여기서는 `omp_in_parallel` 0이 아닌 값을 반환 하는 함수,이 함수의 동작이 정의 되지 않습니다.

이 호출 보다 우선 합니다 `OMP_NESTED` 환경 변수입니다.

중첩 된 병렬 처리를 사용 하는 경우 중첩 된 병렬 영역을 실행 하는 데 사용 되는 스레드 수가 구현이 정의 됩니다. 결과적으로, OpenMP 규격 구현 중첩 된 병렬 처리 사용 하도록 설정 하는 경우에 중첩 된 병렬 영역을 serialize 할 수 있습니다.

#### <a name="cross-references"></a>상호 참조

- [OMP_NESTED](4-environment-variables.md#44-omp_nested)
- [omp_in_parallel](#316-omp_in_parallel-function)

### <a name="3110-omp_get_nested-function"></a>3.1.10 omp_get_nested 함수

`omp_get_nested` 비활성화 된 경우 함수는 중첩 된 병렬 처리를 사용 하는 경우 0이 아닌 값 및 0 반환 합니다. 중첩 된 병렬 처리에 대 한 자세한 내용은 참조 하세요. [omp_set_nested](#319-omp_set_nested-function)합니다. 형식은 다음과 같습니다.

```cpp
#include <omp.h>
int omp_get_nested(void);
```

구현 하지 않습니다 중첩 된 병렬 처리를 구현 하는 경우이 함수는 항상 0을 반환 합니다.

## <a name="32-lock-functions"></a>3.2 lock 함수

이 섹션에 설명 된 함수에는 동기화에 사용 되는 잠금 조작 합니다.

다음 함수에 대 한 잠금 변수의 형식이 있어야 `omp_lock_t`합니다. 이 변수는 이러한 함수를 통해만 액세스 해야 합니다. 모든 잠금 함수에 대 한 포인터를 인수로 필요 `omp_lock_t` 형식입니다.

- 합니다 [omp_init_lock](#321-omp_init_lock-and-omp_init_nest_lock-functions) 함수 간단한 잠금을 초기화 합니다.
- 합니다 [omp_destroy_lock](#322-omp_destroy_lock-and-omp_destroy_nest_lock-functions) 함수는 간단한 잠금을 제거 합니다.
- 합니다 [omp_set_lock](#323-omp_set_lock-and-omp_set_nest_lock-functions) 함수 간단한 잠금 제공 될 때까지 대기 합니다.
- 합니다 [omp_unset_lock](#324-omp_unset_lock-and-omp_unset_nest_lock-functions) 함수에는 간단한 잠금을 해제 합니다.
- 합니다 [omp_test_lock](#325-omp_test_lock-and-omp_test_nest_lock-functions) 함수 간단한 잠금 테스트 합니다.

다음 함수에 대 한 잠금 변수의 형식이 있어야 `omp_nest_lock_t`합니다.  이 변수는 이러한 함수를 통해만 액세스 해야 합니다. 모든 중첩 가능 잠금을 함수에 대 한 포인터를 인수로 필요 `omp_nest_lock_t` 형식입니다.

- 합니다 [omp_init_nest_lock](#321-omp_init_lock-and-omp_init_nest_lock-functions) 함수를 중첩 가능 잠금을 초기화 합니다.
- 합니다 [omp_destroy_nest_lock](#322-omp_destroy_lock-and-omp_destroy_nest_lock-functions) 함수를 중첩 가능 잠금을 제거 합니다.
- 합니다 [omp_set_nest_lock](#323-omp_set_lock-and-omp_set_nest_lock-functions) 함수를 중첩 가능 잠금 사용 가능할 때까지 대기 합니다.
- 합니다 [omp_unset_nest_lock](#324-omp_unset_lock-and-omp_unset_nest_lock-functions) 함수 중첩 가능 잠금을 해제 합니다.
- 합니다 [omp_test_nest_lock](#325-omp_test_lock-and-omp_test_nest_lock-functions) 함수를 중첩 가능 잠금 테스트 합니다.

OpenMP lock 함수에는 항상 읽기 하며 최신 잠금 변수의 값을 업데이트 하는 방식으로 잠금을 변수에 액세스 합니다. OpenMP 프로그램 명시적 포함할 필요는 없습니다 따라서 `flush` 지시문을 잠금 변수의 값 다른 스레드 간에 일관 되는지 확인 합니다. (에 대 한 요구가 있을 `flush` 지시문을 다른 변수 값을 일관 되 게 합니다.)

### <a name="321-omp_init_lock-and-omp_init_nest_lock-functions"></a>3.2.1 omp_init_lock and omp_init_nest_lock 함수

이러한 함수에는 잠금을 초기화 하는 유일한 수단을 제공 합니다. 각 함수 초기화 매개 변수를 사용 하 여 연결 된 잠금을 *잠금* 예정 된 호출에 사용 합니다. 형식은 다음과 같습니다.

```cpp
#include <omp.h>
void omp_init_lock(omp_lock_t *lock);
void omp_init_nest_lock(omp_nest_lock_t *lock);
```

초기 상태를 잠긴 아닙니다 (즉, 스레드가 소유 하지 않는 잠금). 중첩 가능 잠금을 초기 중첩 개수는 0입니다. 비규격 이미 초기화 된 잠금 변수를 사용 하 여 이러한 루틴 중 하나를 호출 하는 것입니다.

### <a name="322-omp_destroy_lock-and-omp_destroy_nest_lock-functions"></a>3.2.2 omp_destroy_lock and omp_destroy_nest_lock 함수

이러한 기능을 확인 변수 뾰족한 *잠금* 초기화 되지 않았습니다. 형식은 다음과 같습니다.

```cpp
#include <omp.h>
void omp_destroy_lock(omp_lock_t *lock);
void omp_destroy_nest_lock(omp_nest_lock_t *lock);
```

가 초기화 되지 않은 잠금 변수를 사용 하 여 이러한 루틴 중 하나를 호출 하는 정책을 준수 하지 않는 또는 잠금 해제입니다.

### <a name="323-omp_set_lock-and-omp_set_nest_lock-functions"></a>3.2.3 omp_set_lock and omp_set_nest_lock 함수

이러한 각 함수는 지정 된 잠금을 사용할 수 있고 잠금이 설정 될 때까지 함수를 실행 하는 스레드를 차단 합니다. 간단한 잠겨 있으면 사용 가능한 잠금 해제 합니다. 있으면 중첩 가능 잠금 수 잠금이 해제 된 스레드가 함수를 실행 하 여 이미 소유 하는 경우. 형식은 다음과 같습니다.

```cpp
#include <omp.h>
void omp_set_lock(omp_lock_t *lock);
void omp_set_nest_lock(omp_nest_lock_t *lock);
```

간단한 잠금에 대 한 인수에 대 한는 `omp_set_lock` 함수 초기화 잠금 변수를 가리켜야 합니다. 함수를 실행 하는 스레드 잠금 소유권 부여 됩니다.

인수에서 중첩 가능 잠금는 `omp_set_nest_lock` 함수 초기화 잠금 변수를 가리켜야 합니다. 중첩 수 증가 하 고 스레드 부여 또는 잠금 소유권을 유지 합니다.

### <a name="324-omp_unset_lock-and-omp_unset_nest_lock-functions"></a>3.2.4 omp_unset_lock and omp_unset_nest_lock 함수

이러한 함수는 잠금 소유권을 해제 하는 수단을 제공 합니다. 형식은 다음과 같습니다.

```cpp
#include <omp.h>
void omp_unset_lock(omp_lock_t *lock);
void omp_unset_nest_lock(omp_nest_lock_t *lock);
```

이러한 각 함수에 대 한 인수는 함수를 실행 하는 스레드를 소유 하는 초기화 잠금 변수를 가리키도록 해야 합니다. 스레드는 잠금을 소유 하지 않는 경우 동작이 정의 되지 않습니다.

간단한 잠금에 대 한는 `omp_unset_lock` 함수 잠금 소유권에서 함수를 실행 하는 스레드를 해제 합니다.

중첩 가능 잠금는 `omp_unset_nest_lock` 함수는 중첩 개수 및 릴리스 결과 횟수가 0 이면 잠금 소유권에서 함수를 실행 하는 스레드입니다.

### <a name="325-omp_test_lock-and-omp_test_nest_lock-functions"></a>3.2.5 omp_test_lock and omp_test_nest_lock 함수

이러한 함수 잠금을 설정 하려고 하지만 스레드 실행을 차단 하지 않습니다. 형식은 다음과 같습니다.

```cpp
#include <omp.h>
int omp_test_lock(omp_lock_t *lock);
int omp_test_nest_lock(omp_nest_lock_t *lock);
```

인수는 초기화 잠금 변수를 가리켜야 합니다. 이러한 함수를 동일한 방식으로 잠금을 설정 하려고 `omp_set_lock` 고 `omp_set_nest_lock`한다는 점을 제외 하는 스레드 실행을 차단 하지 않습니다.

간단한 잠금에 대 한는 `omp_test_lock` 잠금을 성공적으로 설정 된 경우 함수는 0이 아닌 값을 반환, 그렇지 않으면 0을 반환 합니다.

중첩 가능 잠금는 `omp_test_nest_lock` 함수 잠금을 성공적으로 설정 된 경우 새 중첩 수를 반환, 그렇지 않으면 0을 반환 합니다.

## <a name="33-timing-routines"></a>3.3 타이밍 루틴

이 섹션에서 설명 하는 기능은 이식 가능한 벽 시계 타이머를 지원 합니다.

- 합니다 [omp_get_wtime](#331-omp_get_wtime-function) 함수 경과 된 벽 시계 시간을 반환 합니다.
- 합니다 [omp_get_wtick](#332-omp_get_wtick-function) 연속 클록 틱 간 시간 (초)을 반환 합니다.

### <a name="331-omp_get_wtime-function"></a>3.3.1 omp_get_wtime 함수

`omp_get_wtime` 함수 반환 배정밀도 부동 소수점 값 경과 된 벽 시계 시간을 몇 가지 "과거의 지정 시간" 이후의 초 단위입니다.  실제 "시간 이전에" 임의적 이지만 응용 프로그램의 실행 하는 동안 변경 되지 않도록 보장에 해당 합니다. 형식은 다음과 같습니다.

```cpp
#include <omp.h>
double omp_get_wtime(void);
```

다음 예제에서와 같이 경과 시간을 측정 하는 함수를 사용할 수는 것으로 예상 됩니다.

```cpp
double start;
double end;
start = omp_get_wtime();
... work to be timed ...
end = omp_get_wtime();
printf_s("Work took %f sec. time.\n", end-start);
```

반환 된 시간은 응용 프로그램에 참여 하는 모든 스레드에서 전역적으로 일관 되 게 필요가 있는 것으로 "스레드별 times" 이며

### <a name="332-omp_get_wtick-function"></a>3.3.2 omp_get_wtick 함수

`omp_get_wtick` 반환 배정밀도 부동 소수점 값 시간 (초) 수와 같은 연속 클록 틱 간입니다. 형식은 다음과 같습니다.

```cpp
#include <omp.h>
double omp_get_wtick(void);
```
