---
title: OpenMP 함수
ms.date: 03/20/2019
f1_keywords:
- OpenMP functions
- omp_destroy_lock
- omp_destroy_nest_lock
- omp_get_dynamic
- omp_get_max_threads
- omp_get_nested
- omp_get_num_procs
- omp_get_num_threads
- omp_get_thread_num
- omp_get_wtick
- omp_get_wtime
- omp_in_parallel
- omp_init_lock
- omp_init_nest_lock
- omp_set_dynamic
- omp_set_lock
- omp_set_nest_lock
- omp_set_nested
- omp_set_num_threads
- omp_test_lock
- omp_test_nest_lock
- omp_unset_lock
- omp_unset_nest_lock
helpviewer_keywords:
- OpenMP functions
- omp_destroy_lock OpenMP function
- omp_destroy_nest_lock OpenMP function
- omp_get_dynamic OpenMP function
- omp_get_max_threads OpenMP function
- omp_get_nested OpenMP function
- omp_get_num_procs OpenMP function
- omp_get_num_threads OpenMP function
- omp_get_thread_num OpenMP function
- omp_get_wtick OpenMP function
- omp_get_wtime OpenMP function
- omp_in_parallel OpenMP function
- omp_init_lock OpenMP function
- omp_init_nest_lock OpenMP function
- omp_set_dynamic OpenMP function
- omp_set_lock OpenMP function
- omp_set_nest_lock OpenMP function
- omp_set_nested OpenMP function
- omp_set_num_threads OpenMP function
- omp_test_lock OpenMP function
- omp_test_nest_lock OpenMP function
- omp_unset_lock OpenMP function
- omp_unset_nest_lock OpenMP function
ms.assetid: a55a2e5c-a260-44ee-bbd6-de7e2351b384
ms.openlocfilehash: 1bf0e08f3b28368d9aea5438b3036ac8a0283735
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62363091"
---
# <a name="openmp-functions"></a>OpenMP 함수

OpenMP API에서 사용 되는 함수에 대 한 링크를 제공 합니다.

시각적 개체 C++ OpenMP 표준의 구현에는 다음 함수 및 데이터 형식이 포함 됩니다.

환경 실행:

|함수|설명|
|--------|-----------|
|[omp_set_num_threads](#omp-set-num-threads)|의해 재정의 되지 않는 예정 된 병렬 지역의 스레드 수가 설정 된 [num_threads](openmp-clauses.md#num-threads) 절.|
|[omp_get_num_threads](#omp-get-num-threads)|병렬 영역에서 스레드 수를 반환합니다.|
|[omp_get_max_threads](#omp-get-max-threads)|있는 경우 병렬 영역 없이 사용할 수 있는 스레드 수보다 크거나 같은 정수를 반환 [num_threads](openmp-clauses.md#num-threads) 코드에서 해당 지점에서 정의 되었습니다.|
|[omp_get_thread_num](#omp-get-thread-num)|해당 스레드 팀 내에서 실행 중인 스레드의 스레드 수를 반환 합니다.|
|[omp_get_num_procs](#omp-get-num-procs)|함수를 호출할 때 사용할 수 있는 프로세서 수를 반환 합니다.|
|[omp_in_parallel](#omp-in-parallel)|병렬 영역 내부에서 호출 된 경우 0이 아닌 값을 반환 합니다.|
|[omp_set_dynamic](#omp-set-dynamic)|런타임에서 예정 된 병렬 지역에서 사용할 수 있는 스레드 수를 조정할 수 있는지를 나타냅니다.|
|[omp_get_dynamic](#omp-get-dynamic)|실행된 시간을 기준으로 향후 병렬 지역에서 사용할 수 있는 스레드 수를 조정할 수 하는 경우를 나타내는 값을 반환 합니다.|
|[omp_set_nested](#omp-set-nested)|중첩 된 병렬 처리가 가능 합니다.|
|[omp_get_nested](#omp-get-nested)|중첩 된 병렬 처리를 설정할지 여부를 나타내는 값을 반환 합니다.|

잠금:

|함수|설명|
|--------|-----------|
|[omp_init_lock](#omp-init-lock)|간단한 잠금을 초기화합니다.|
|[omp_init_nest_lock](#omp-init-nest-lock)|잠금을 초기화합니다.|
|[omp_destroy_lock](#omp-destroy-lock)|잠금을 초기화를 취소 합니다.|
|[omp_destroy_nest_lock](#omp-destroy-nest-lock)|중첩 가능 잠금을 초기화를 취소 합니다.|
|[omp_set_lock](#omp-set-lock)|블록 스레드 잠금을 제공 될 때까지 실행 합니다.|
|[omp_set_nest_lock](#omp-set-nest-lock)|블록 스레드 잠금을 제공 될 때까지 실행 합니다.|
|[omp_unset_lock](#omp-unset-lock)|잠금을 해제합니다.|
|[omp_unset_nest_lock](#omp-unset-nest-lock)|중첩 가능 잠금을 해제합니다.|
|[omp_test_lock](#omp-test-lock)|잠금을 설정 하려고 시도 하지만 스레드 실행을 차단 하지 않습니다.|
|[omp_test_nest_lock](#omp-test-nest-lock)|중첩 가능 잠금을 설정 하려고 시도 하지만 스레드 실행을 차단 하지 않습니다.|

|데이터 형식|설명|
|---------|-----------|
|`omp_lock_t`|잠금, 잠금을 사용할 수 있는지 또는 스레드가 잠금을 소유 하는 경우의 상태를 보유 하는 형식입니다.|
|`omp_nest_lock_t`|잠금에 대 한 정보는 다음과 같은 부분 중 하나를 포함 하는 형식: 잠금을 사용할 수는 스레드의 id를 소유 하는 잠금 및 중첩 수 있는지 여부를 합니다.|

타이밍 루틴의 경우:

|함수|설명|
|--------|-----------|
|[omp_get_wtime](#omp-get-wtime)|어느 시점에서 경과 된 시간의 초 값을 반환 합니다.|
|[omp_get_wtick](#omp-get-wtick)|프로세서 클록 틱 사이의 시간 (초) 수를 반환합니다.|

## <a name="omp-destroy-lock"></a>omp_destroy_lock

잠금을 초기화를 취소 합니다.

```
void omp_destroy_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>매개 변수

*lock*<br/>
형식 변수의 `omp_lock_t` 사용 하 여 초기화 된 [omp_init_lock](#omp-init-lock)합니다.

### <a name="remarks"></a>설명

자세한 내용은 [3.2.2 omp_destroy_lock and omp_destroy_nest_lock 함수](../../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md)합니다.

### <a name="example"></a>예제

참조 [omp_init_lock](#omp-init-lock) 사용 하는 예제에 대 한 `omp_destroy_lock`합니다.

## <a name="omp-destroy-nest-lock"></a>omp_destroy_nest_lock

중첩 가능 잠금을 초기화를 취소 합니다.

```
void omp_destroy_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>매개 변수

*lock*<br/>
형식 변수의 `omp_nest_lock_t` 사용 하 여 초기화 된 [omp_init_nest_lock](#omp-init-nest-lock)합니다.

### <a name="remarks"></a>설명

자세한 내용은 [3.2.2 omp_destroy_lock and omp_destroy_nest_lock 함수](../../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md)합니다.

### <a name="example"></a>예제

참조 [omp_init_nest_lock](#omp-init-nest-lock) 사용 하는 예제에 대 한 `omp_destroy_nest_lock`합니다.

## <a name="omp-get-dynamic"></a>omp_get_dynamic

실행된 시간을 기준으로 향후 병렬 지역에서 사용할 수 있는 스레드 수를 조정할 수 하는 경우를 나타내는 값을 반환 합니다.

```
int omp_get_dynamic();
```

### <a name="return-value"></a>반환 값

0이 아닌 값 스레드 동적으로 조정 될 것을 의미 합니다.

### <a name="remarks"></a>설명

지정 된 스레드를 동적으로 조정 [omp_set_dynamic](#omp-set-dynamic) 하 고 [OMP_DYNAMIC](openmp-environment-variables.md#omp-dynamic)합니다.

자세한 내용은 [3.1.7 omp_set_dynamic 함수](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md)합니다.

### <a name="example"></a>예제

참조 [omp_set_dynamic](#omp-set-dynamic) 사용 하는 예제에 대 한 `omp_get_dynamic`합니다.

## <a name="omp-get-max-threads"></a>omp_get_max_threads

있는 경우 병렬 영역 없이 사용할 수 있는 스레드 수보다 크거나 같은 정수를 반환 [num_threads](openmp-clauses.md#num-threads) 코드에서 해당 지점에서 정의 되었습니다.

```
int omp_get_max_threads( )
```

### <a name="remarks"></a>설명

자세한 내용은 [3.1.3 omp_get_max_threads 함수](../../../parallel/openmp/3-1-3-omp-get-max-threads-function.md)합니다.

### <a name="example"></a>예제

```cpp
// omp_get_max_threads.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main( )
{
    omp_set_num_threads(8);
    printf_s("%d\n", omp_get_max_threads( ));
    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_get_max_threads( ));
        }

    printf_s("%d\n", omp_get_max_threads( ));

    #pragma omp parallel num_threads(3)
        #pragma omp master
        {
            printf_s("%d\n", omp_get_max_threads( ));
        }

    printf_s("%d\n", omp_get_max_threads( ));
}
```

```Output
8
8
8
8
8
```

## <a name="omp-get-nested"></a>omp_get_nested

중첩 된 병렬 처리를 설정할지 여부를 나타내는 값을 반환 합니다.

```
int omp_get_nested( );
```

### <a name="return-value"></a>반환 값

0이 아닌 값은 중첩 된 병렬 처리 활성화 됨을 의미 합니다.

### <a name="remarks"></a>설명

중첩 된 병렬 처리 수준 지정 된 [omp_set_nested](#omp-set-nested) 하 고 [OMP_NESTED](openmp-environment-variables.md#omp-nested)합니다.

자세한 내용은 [3.1.10 omp_get_nested 함수](../../../parallel/openmp/3-1-10-omp-get-nested-function.md)합니다.

### <a name="example"></a>예제

참조 [omp_set_nested](#omp-set-nested) 사용 하는 예제에 대 한 `omp_get_nested`합니다.

## <a name="omp-get-num-procs"></a>omp_get_num_procs

함수를 호출할 때 사용할 수 있는 프로세서 수를 반환 합니다.

```
int omp_get_num_procs();
```

### <a name="remarks"></a>설명

자세한 내용은 [3.1.5 omp_get_num_procs 함수](../../../parallel/openmp/3-1-5-omp-get-num-procs-function.md)합니다.

### <a name="example"></a>예제

```cpp
// omp_get_num_procs.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main( )
{
    printf_s("%d\n", omp_get_num_procs( ));
    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_get_num_procs( ));
        }
}
```

```Output
// Expect the following output when the example is run on a two-processor machine:
2
2
```

## <a name="omp-get-num-threads"></a>omp_get_num_threads

병렬 영역에서 스레드 수를 반환합니다.

```
int omp_get_num_threads( );
```

### <a name="remarks"></a>설명

자세한 내용은 [3.1.2 omp_get_num_threads 함수](../../../parallel/openmp/3-1-2-omp-get-num-threads-function.md)합니다.

### <a name="example"></a>예제

```cpp
// omp_get_num_threads.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main()
{
    omp_set_num_threads(4);
    printf_s("%d\n", omp_get_num_threads( ));
    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_get_num_threads( ));
        }

    printf_s("%d\n", omp_get_num_threads( ));

    #pragma omp parallel num_threads(3)
        #pragma omp master
        {
            printf_s("%d\n", omp_get_num_threads( ));
        }

    printf_s("%d\n", omp_get_num_threads( ));
}
```

```Output
1
4
1
3
1
```

## <a name="omp-get-thread-num"></a>omp_get_thread_num

해당 스레드 팀 내에서 실행 중인 스레드의 스레드 수를 반환 합니다.

```
int omp_get_thread_num( );
```

### <a name="remarks"></a>설명

자세한 내용은 [3.1.4 omp_get_thread_num 함수](../../../parallel/openmp/3-1-4-omp-get-thread-num-function.md)합니다.

### <a name="example"></a>예제

참조 [병렬](openmp-directives.md#parallel) 사용 하는 예제에 대 한 `omp_get_thread_num`합니다.

## <a name="omp-get-wtick"></a>omp_get_wtick

프로세서 클록 틱 사이의 시간 (초) 수를 반환합니다.

```
double omp_get_wtick( );
```

### <a name="remarks"></a>설명

자세한 내용은 [3.3.2 omp_get_wtick 함수](../../../parallel/openmp/3-3-2-omp-get-wtick-function.md)합니다.

### <a name="example"></a>예제

참조 [omp_get_wtime](#omp-get-wtime) 사용 하는 예제에 대 한 `omp_get_wtick`합니다.

## <a name="omp-get-wtime"></a>omp_get_wtime

어느 시점에서 경과 된 시간의 초 값을 반환 합니다.

```
double omp_get_wtime( );
```

### <a name="return-value"></a>반환 값

일부 임의 이지만 일관 된 지점에서 경과 된 시간의 초 값을 반환 합니다.

### <a name="remarks"></a>설명

프로그램 실행 가능한 예정 된 비교를 수행 하는 동안 해당 지점 일관 된 상태로 유지 됩니다.

자세한 내용은 [3.3.1 omp_get_wtime 함수](../../../parallel/openmp/3-3-1-omp-get-wtime-function.md)합니다.

### <a name="example"></a>예제

```cpp
// omp_get_wtime.cpp
// compile with: /openmp
#include "omp.h"
#include <stdio.h>
#include <windows.h>

int main() {
    double start = omp_get_wtime( );
    Sleep(1000);
    double end = omp_get_wtime( );
    double wtick = omp_get_wtick( );

    printf_s("start = %.16g\nend = %.16g\ndiff = %.16g\n",
             start, end, end - start);

    printf_s("wtick = %.16g\n1/wtick = %.16g\n",
             wtick, 1.0 / wtick);
}
```

```Output
start = 594255.3671159324
end = 594256.3664474116
diff = 0.9993314791936427
wtick = 2.793651148400146e-007
1/wtick = 3579545
```

## <a name="omp-in-parallel"></a>omp_in_parallel

병렬 영역 내부에서 호출 된 경우 0이 아닌 값을 반환 합니다.

```
int omp_in_parallel( );
```

### <a name="remarks"></a>설명

자세한 내용은 [3.1.6 omp_in_parallel 함수](../../../parallel/openmp/3-1-6-omp-in-parallel-function.md)합니다.

### <a name="example"></a>예제

```cpp
// omp_in_parallel.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main( )
{
    omp_set_num_threads(4);
    printf_s("%d\n", omp_in_parallel( ));

    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_in_parallel( ));
        }
}
```

```Output
0
1
```

## <a name="omp-init-lock"></a>omp_init_lock

간단한 잠금을 초기화합니다.

```
void omp_init_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>매개 변수

*lock*<br/>
`omp_lock_t` 형식의 변수입니다.

### <a name="remarks"></a>설명

자세한 내용은 [3.2.1 omp_init_lock and omp_init_nest_lock 함수](../../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md)합니다.

### <a name="example"></a>예제

```cpp
// omp_init_lock.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

omp_lock_t my_lock;

int main() {
   omp_init_lock(&my_lock);

   #pragma omp parallel num_threads(4)
   {
      int tid = omp_get_thread_num( );
      int i, j;

      for (i = 0; i < 5; ++i) {
         omp_set_lock(&my_lock);
         printf_s("Thread %d - starting locked region\n", tid);
         printf_s("Thread %d - ending locked region\n", tid);
         omp_unset_lock(&my_lock);
      }
   }

   omp_destroy_lock(&my_lock);
}
```

```Output
Thread 0 - starting locked region
Thread 0 - ending locked region
Thread 0 - starting locked region
Thread 0 - ending locked region
Thread 0 - starting locked region
Thread 0 - ending locked region
Thread 0 - starting locked region
Thread 0 - ending locked region
Thread 0 - starting locked region
Thread 0 - ending locked region
Thread 1 - starting locked region
Thread 1 - ending locked region
Thread 1 - starting locked region
Thread 1 - ending locked region
Thread 1 - starting locked region
Thread 1 - ending locked region
Thread 1 - starting locked region
Thread 1 - ending locked region
Thread 1 - starting locked region
Thread 1 - ending locked region
Thread 2 - starting locked region
Thread 2 - ending locked region
Thread 2 - starting locked region
Thread 2 - ending locked region
Thread 2 - starting locked region
Thread 2 - ending locked region
Thread 2 - starting locked region
Thread 2 - ending locked region
Thread 2 - starting locked region
Thread 2 - ending locked region
Thread 3 - starting locked region
Thread 3 - ending locked region
Thread 3 - starting locked region
Thread 3 - ending locked region
Thread 3 - starting locked region
Thread 3 - ending locked region
Thread 3 - starting locked region
Thread 3 - ending locked region
Thread 3 - starting locked region
Thread 3 - ending locked region
```

## <a name="omp-init-nest-lock"></a>omp_init_nest_lock

잠금을 초기화합니다.

```
void omp_init_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>매개 변수

*lock*<br/>
`omp_nest_lock_t` 형식의 변수입니다.

### <a name="remarks"></a>설명

초기 중첩 카운트는 0입니다.

자세한 내용은 [3.2.1 omp_init_lock and omp_init_nest_lock 함수](../../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md)합니다.

### <a name="example"></a>예제

```cpp
// omp_init_nest_lock.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

omp_nest_lock_t my_lock;

void Test() {
   int tid = omp_get_thread_num( );
   omp_set_nest_lock(&my_lock);
   printf_s("Thread %d - starting nested locked region\n", tid);
   printf_s("Thread %d - ending nested locked region\n", tid);
   omp_unset_nest_lock(&my_lock);
}

int main() {
   omp_init_nest_lock(&my_lock);

   #pragma omp parallel num_threads(4)
   {
      int i, j;

      for (i = 0; i < 5; ++i) {
         omp_set_nest_lock(&my_lock);
            if (i % 3)
               Test();
            omp_unset_nest_lock(&my_lock);
        }
    }

    omp_destroy_nest_lock(&my_lock);
}
```

```Output
Thread 0 - starting nested locked region
Thread 0 - ending nested locked region
Thread 0 - starting nested locked region
Thread 0 - ending nested locked region
Thread 3 - starting nested locked region
Thread 3 - ending nested locked region
Thread 3 - starting nested locked region
Thread 3 - ending nested locked region
Thread 3 - starting nested locked region
Thread 3 - ending nested locked region
Thread 2 - starting nested locked region
Thread 2 - ending nested locked region
Thread 2 - starting nested locked region
Thread 2 - ending nested locked region
Thread 2 - starting nested locked region
Thread 2 - ending nested locked region
Thread 1 - starting nested locked region
Thread 1 - ending nested locked region
Thread 1 - starting nested locked region
Thread 1 - ending nested locked region
Thread 1 - starting nested locked region
Thread 1 - ending nested locked region
Thread 0 - starting nested locked region
Thread 0 - ending nested locked region
```

## <a name="omp-set-dynamic"></a>omp_set_dynamic

런타임에서 예정 된 병렬 지역에서 사용할 수 있는 스레드 수를 조정할 수 있는지를 나타냅니다.

```
void omp_set_dynamic(
   int val
);
```

### <a name="parameters"></a>매개 변수

*val*<br/>
런타임에서 예정 된 병렬 지역에서 사용할 수 있는 스레드 수를 조정할 수 있으면 여부를 나타내는 값입니다. 0이 아니면 0 이면 런타임에서 스레드 수를 조정할 수, 런타임에서 스레드 수를 동적으로 조정 되지 않습니다.

### <a name="remarks"></a>설명

스레드 수는 설정한 값을 초과할 수 없습니다 [omp_set_num_threads](#omp-set-num-threads) 하거나 [OMP_NUM_THREADS](openmp-environment-variables.md#omp-num-threads)합니다.

사용 하 여 [omp_get_dynamic](#omp-get-dynamic) 의 현재 설정을 표시 하려면 `omp_set_dynamic`합니다.

에 대 한 설정을 `omp_set_dynamic` 의 설정을 재정의 합니다 [OMP_DYNAMIC](openmp-environment-variables.md#omp-dynamic) 환경 변수입니다.

자세한 내용은 [3.1.7 omp_set_dynamic 함수](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md)합니다.

### <a name="example"></a>예제

```cpp
// omp_set_dynamic.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main()
{
    omp_set_dynamic(9);
    omp_set_num_threads(4);
    printf_s("%d\n", omp_get_dynamic( ));
    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_get_dynamic( ));
        }
}
```

```Output
1
1
```

## <a name="omp-set-lock"></a>omp_set_lock

블록 스레드 잠금을 제공 될 때까지 실행 합니다.

```
void omp_set_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>매개 변수

*lock*<br/>
형식 변수의 `omp_lock_t` 사용 하 여 초기화 된 [omp_init_lock](#omp-init-lock)합니다.

### <a name="remarks"></a>설명

자세한 내용은 [3.2.3 omp_set_lock and omp_set_nest_lock 함수](../../../parallel/openmp/3-2-3-omp-set-lock-and-omp-set-nest-lock-functions.md)합니다.

### <a name="examples"></a>예제

참조 [omp_init_lock](#omp-init-lock) 사용 하는 예제에 대 한 `omp_set_lock`합니다.

## <a name="omp-set-nest-lock"></a>omp_set_nest_lock

블록 스레드 잠금을 제공 될 때까지 실행 합니다.

```
void omp_set_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>매개 변수

*lock*<br/>
형식 변수의 `omp_nest_lock_t` 사용 하 여 초기화 된 [omp_init_nest_lock](#omp-init-nest-lock)합니다.

### <a name="remarks"></a>설명

자세한 내용은 [3.2.3 omp_set_lock and omp_set_nest_lock 함수](../../../parallel/openmp/3-2-3-omp-set-lock-and-omp-set-nest-lock-functions.md)합니다.

### <a name="examples"></a>예제

참조 [omp_init_nest_lock](#omp-init-nest-lock) 사용 하는 예제에 대 한 `omp_set_nest_lock`합니다.

## <a name="omp-set-nested"></a>omp_set_nested

중첩 된 병렬 처리가 가능 합니다.

```
void omp_set_nested(
   int val
);
```

### <a name="parameters"></a>매개 변수

*val*<br/>
0이 아닌 값 0은 중첩 된 병렬 처리 하는 동안 중첩 된 병렬 처리를 수 있습니다.

### <a name="remarks"></a>설명

OMP 중첩 사용 하 여 병렬 처리를 켤 수 있습니다 `omp_set_nested`, 하거나 설정 하는 [OMP_NESTED](openmp-environment-variables.md#omp-nested) 환경 변수입니다.

에 대 한 설정을 `omp_set_nested` 의 설정 재정의 `OMP_NESTED` 환경 변수입니다.

환경 변수를 사용 하도록 설정 하면 병렬 영역을 중첩 하는 경우 스레드 수가 기하급수적으로 증가 하기 때문에 그렇지 않은 경우 운영 프로그램을 끊어질 수 있습니다. 6 배 4로 설정 하는 OMP 스레드 수를 사용 하 여 재귀 함수 (6의 4) 4,096를 필요로 하는 예를 들어 스레드입니다. 제외 하 고 O 바인딩된 응용 프로그램을 사용 하 여 응용 프로그램의 성능을 일반적으로 저하 프로세서 보다 많은 스레드가 있는 경우.

사용 하 여 [omp_get_nested](#omp-get-nested) 의 현재 설정을 표시 하려면 `omp_set_nested`합니다.

자세한 내용은 [3.1.9 omp_set_nested 함수](../../../parallel/openmp/3-1-9-omp-set-nested-function.md)합니다.

### <a name="example"></a>예제

```cpp
// omp_set_nested.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main( )
{
    omp_set_nested(1);
    omp_set_num_threads(4);
    printf_s("%d\n", omp_get_nested( ));
    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_get_nested( ));
        }
}
```

```Output
1
1
```

## <a name="omp-set-num-threads"></a>omp_set_num_threads

의해 재정의 되지 않는 예정 된 병렬 지역의 스레드 수가 설정 된 [num_threads](openmp-clauses.md#num-threads) 절.

```
void omp_set_num_threads(
   int num_threads
);
```

### <a name="parameters"></a>매개 변수

*num_threads*<br/>
병렬 영역에 있는 스레드의 수입니다.

### <a name="remarks"></a>설명

자세한 내용은 [3.1.1 omp_set_num_threads 함수](../../../parallel/openmp/3-1-1-omp-set-num-threads-function.md)합니다.

### <a name="example"></a>예제

참조 [omp_get_num_threads](#omp-get-num-threads) 사용 하는 예제에 대 한 `omp_set_num_threads`합니다.

## <a name="omp-test-lock"></a>omp_test_lock

잠금을 설정 하려고 시도 하지만 스레드 실행을 차단 하지 않습니다.

```
int omp_test_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>매개 변수

*lock*<br/>
형식 변수의 `omp_lock_t` 사용 하 여 초기화 된 [omp_init_lock](#omp-init-lock)합니다.

### <a name="remarks"></a>설명

자세한 내용은 [3.2.5 omp_test_lock and omp_test_nest_lock 함수](../../../parallel/openmp/3-2-5-omp-test-lock-and-omp-test-nest-lock-functions.md)합니다.

### <a name="example"></a>예제

```cpp
// omp_test_lock.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

omp_lock_t simple_lock;

int main() {
    omp_init_lock(&simple_lock);

    #pragma omp parallel num_threads(4)
    {
        int tid = omp_get_thread_num();

        while (!omp_test_lock(&simple_lock))
            printf_s("Thread %d - failed to acquire simple_lock\n",
                     tid);

        printf_s("Thread %d - acquired simple_lock\n", tid);

        printf_s("Thread %d - released simple_lock\n", tid);
        omp_unset_lock(&simple_lock);
    }

    omp_destroy_lock(&simple_lock);
}
```

```Output
Thread 1 - acquired simple_lock
Thread 1 - released simple_lock
Thread 0 - failed to acquire simple_lock
Thread 3 - failed to acquire simple_lock
Thread 0 - failed to acquire simple_lock
Thread 3 - failed to acquire simple_lock
Thread 2 - acquired simple_lock
Thread 0 - failed to acquire simple_lock
Thread 3 - failed to acquire simple_lock
Thread 0 - failed to acquire simple_lock
Thread 3 - failed to acquire simple_lock
Thread 2 - released simple_lock
Thread 0 - failed to acquire simple_lock
Thread 3 - failed to acquire simple_lock
Thread 0 - acquired simple_lock
Thread 3 - failed to acquire simple_lock
Thread 0 - released simple_lock
Thread 3 - failed to acquire simple_lock
Thread 3 - acquired simple_lock
Thread 3 - released simple_lock
```

## <a name="omp-test-nest-lock"></a>omp_test_nest_lock

중첩 가능 잠금을 설정 하려고 시도 하지만 스레드 실행을 차단 하지 않습니다.

```
int omp_test_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>매개 변수

*lock*<br/>
형식 변수의 `omp_nest_lock_t` 사용 하 여 초기화 된 [omp_init_nest_lock](#omp-init-nest-lock)합니다.

### <a name="remarks"></a>설명

자세한 내용은 [3.2.5 omp_test_lock and omp_test_nest_lock 함수](../../../parallel/openmp/3-2-5-omp-test-lock-and-omp-test-nest-lock-functions.md)합니다.

### <a name="example"></a>예제

```cpp
// omp_test_nest_lock.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

omp_nest_lock_t nestable_lock;

int main() {
   omp_init_nest_lock(&nestable_lock);

   #pragma omp parallel num_threads(4)
   {
      int tid = omp_get_thread_num();
      while (!omp_test_nest_lock(&nestable_lock))
         printf_s("Thread %d - failed to acquire nestable_lock\n",
                tid);

      printf_s("Thread %d - acquired nestable_lock\n", tid);

      if (omp_test_nest_lock(&nestable_lock)) {
         printf_s("Thread %d - acquired nestable_lock again\n",
                tid);
         printf_s("Thread %d - released nestable_lock\n",
                tid);
         omp_unset_nest_lock(&nestable_lock);
      }

      printf_s("Thread %d - released nestable_lock\n", tid);
      omp_unset_nest_lock(&nestable_lock);
   }

   omp_destroy_nest_lock(&nestable_lock);
}
```

```Output
Thread 1 - acquired nestable_lock
Thread 0 - failed to acquire nestable_lock
Thread 1 - acquired nestable_lock again
Thread 0 - failed to acquire nestable_lock
Thread 1 - released nestable_lock
Thread 0 - failed to acquire nestable_lock
Thread 1 - released nestable_lock
Thread 0 - failed to acquire nestable_lock
Thread 3 - acquired nestable_lock
Thread 0 - failed to acquire nestable_lock
Thread 3 - acquired nestable_lock again
Thread 0 - failed to acquire nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 3 - released nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 3 - released nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 0 - acquired nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 0 - acquired nestable_lock again
Thread 2 - failed to acquire nestable_lock
Thread 0 - released nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 0 - released nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 2 - acquired nestable_lock
Thread 2 - acquired nestable_lock again
Thread 2 - released nestable_lock
Thread 2 - released nestable_lock
```

## <a name="omp-unset-lock"></a>omp_unset_lock

잠금을 해제합니다.

```
void omp_unset_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>매개 변수

*lock*<br/>
형식 변수의 `omp_lock_t` 사용 하 여 초기화 된 [omp_init_lock](#omp-init-lock), 스레드에 의해 소유 및 함수에서 실행 합니다.

### <a name="remarks"></a>설명

자세한 내용은 [3.2.4 omp_unset_lock and omp_unset_nest_lock 함수](../../../parallel/openmp/3-2-4-omp-unset-lock-and-omp-unset-nest-lock-functions.md)합니다.

### <a name="example"></a>예제

참조 [omp_init_lock](#omp-init-lock) 사용 하는 예제에 대 한 `omp_unset_lock`합니다.

## <a name="omp-unset-nest-lock"></a>omp_unset_nest_lock

중첩 가능 잠금을 해제합니다.

```
void omp_unset_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>매개 변수

*lock*<br/>
형식 변수의 `omp_nest_lock_t` 사용 하 여 초기화 된 [omp_init_nest_lock](#omp-init-nest-lock), 스레드에 의해 소유 및 함수에서 실행 합니다.

### <a name="remarks"></a>설명

자세한 내용은 [3.2.4 omp_unset_lock and omp_unset_nest_lock 함수](../../../parallel/openmp/3-2-4-omp-unset-lock-and-omp-unset-nest-lock-functions.md)합니다.

### <a name="example"></a>예제

참조 [omp_init_nest_lock](#omp-init-nest-lock) 사용 하는 예제에 대 한 `omp_unset_nest_lock`합니다.
