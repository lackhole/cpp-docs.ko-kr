---
title: '대답: 예제'
ms.date: 01/18/2019
ms.assetid: c0f6192f-a205-449b-b84c-cb30dbcc8b8f
ms.openlocfilehash: 061490d34829175bfbdcd84d6208aa396bb19671
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62362974"
---
# <a name="a-examples"></a>대답: 예제

이 문서에 정의 된 구문 예제는 다음과 같습니다. 지시문을 다음 문이 필요한 경우에 복합 이며 아닌 복합 문 앞에 지시문에서 들여쓰기 됩니다.

## <a name="a1-a-simple-loop-in-parallel"></a>A.1 병렬로 간단한 루프

다음 예제에서는 사용 하 여 루프를 병렬화 하는 방법에 설명 합니다 [에 대 한 병렬](2-directives.md#251-parallel-for-construct) 지시문입니다. 루프 반복 변수 기본적으로 비공개 이므로 개인 절에 명시적으로 지정할 필요가 없습니다.

```cpp
#pragma omp parallel for
    for (i=1; i<n; i++)
        b[i] = (a[i] + a[i-1]) / 2.0;
```

## <a name="a2-conditional-compilation"></a>A.2 조건부 컴파일

다음 예제에서는 OpenMP 매크로 사용 하 여 조건부 컴파일 사용법을 보여 줍니다 [_OPENMP](2-directives.md#22-conditional-compilation)합니다. OpenMP 컴파일으로는 `_OPENMP` 매크로가 정의 됩니다.

```cpp
# ifdef _OPENMP
    printf_s("Compiled by an OpenMP-compliant implementation.\n");
# endif
```

정의 된 전처리기 연산자에는 둘 이상의 매크로 단일 지시문에서 테스트할 수 있습니다.

```cpp
# if defined(_OPENMP) && defined(VERBOSE)
    printf_s("Compiled by an OpenMP-compliant implementation.\n");
# endif
```

## <a name="a3-parallel-regions"></a>A.3 병렬 영역

합니다 [병렬](2-directives.md#23-parallel-construct) 지시문 조립 (coarse-grain) 병렬 프로그램에서 사용할 수 있습니다. 병렬 영역에서 각 스레드를 다음 예에서 전역 배열의 부분을 결정 `x` 작업할 스레드 수를 기준으로 합니다.

```cpp
#pragma omp parallel shared(x, npoints) private(iam, np, ipoints)
{
    iam = omp_get_thread_num();
    np =  omp_get_num_threads();
    ipoints = npoints / np;
    subdomain(x, iam, ipoints);
}
```

## <a name="a4-the-nowait-clause"></a>A.4 nowait 절

병렬 영역 내부에서는 여러 독립적인 루프의 경우 사용할 수는 [nowait](2-directives.md#241-for-construct) 절 끝에 암시적된 장벽을 사용 하지 않으려면는 `for` 다음과 같은 지시문:

```cpp
#pragma omp parallel
{
    #pragma omp for nowait
        for (i=1; i<n; i++)
             b[i] = (a[i] + a[i-1]) / 2.0;
    #pragma omp for nowait
        for (i=0; i<m; i++)
            y[i] = sqrt(z[i]);
}
```

## <a name="a5-the-critical-directive"></a>A.5 critical 지시문

다음 예제에서는 몇 개의 [중요 한](2-directives.md#262-critical-construct) 지시문입니다. 이 예제에서는 태스크를 큐에서 제거 되 고 작업 큐 모델을 보여 줍니다. 많은 스레드를 동일한 작업을 큐에 대 한 보호를 큐 작업 수에 `critical` 섹션입니다. 보호 된이 예제에서 두 개의 큐 독립적 이기 때문에 `critical` 다른 이름으로 지시문 *x 축* 및 *yaxis*합니다.

```cpp
#pragma omp parallel shared(x, y) private(x_next, y_next)
{
    #pragma omp critical ( xaxis )
        x_next = dequeue(x);
    work(x_next);
    #pragma omp critical ( yaxis )
        y_next = dequeue(y);
    work(y_next);
}
```

## <a name="a6-the-lastprivate-clause"></a>A.6 lastprivate 절

경우에 따라 올바른 실행 루프의 마지막 반복을 변수에 할당 되는 값에 따라 달라 집니다. 이러한 프로그램에 대 한 인수로 이러한 모든 변수를 나열 해야 합니다는 [lastprivate](2-directives.md#2723-lastprivate) 절 되도록 변수의 값은 루프가 순차적으로 실행 될 때와 동일 합니다.

```cpp
#pragma omp parallel
{
   #pragma omp for lastprivate(i)
      for (i=0; i<n-1; i++)
         a[i] = b[i] + b[i+1];
}
a[i]=b[i];
```

이전 예제에서는 변수의 `i` 병렬 영역의 끝은 같습니다 `n-1`, 순차적 경우에서.

## <a name="a7-the-reduction-clause"></a>A.7 reduction 절

다음 예제는 [감소](2-directives.md#2726-reduction) 절:

```cpp
#pragma omp parallel for private(i) shared(x, y, n) \
                         reduction(+: a, b)
    for (i=0; i<n; i++) {
        a = a + x[i];
        b = b + y[i];
    }
```

## <a name="a8-parallel-sections"></a>A.8 Parallel sections

다음 예제에서 (에 대 한 [2.4.2 섹션](2-directives.md#242-sections-construct))를 함수 *x 축*에 *yaxis*, 및 *zaxis* 동시에 실행할 수 있습니다. 첫 번째 `section` 지시문은 선택 사항입니다.  모든 `section` 지시문의 어휘 범위에 표시 되어야 합니다 `parallel sections` 생성 합니다.

```cpp
#pragma omp parallel sections
{
    #pragma omp section
        xaxis();
    #pragma omp section
        yaxis();
    #pragma omp section
        zaxis();
}
```

## <a name="a9-single-directives"></a>A.9 Single 지시문

다음 예제는 [단일](2-directives.md#243-single-construct) 지시문입니다. 예제에서는 하나의 스레드만 (발생 하는 첫 번째 스레드는 일반적으로 `single` 지시문) 진행률 메시지를 출력 합니다. 사용자는 스레드를 실행 하도록 어떠한가 정도 해서는 `single` 섹션입니다. 다른 모든 스레드가 건너뜁니다 합니다 `single` 섹션 및 끝의 장애물에 중지를 `single` 생성 합니다. 다른 스레드가 실행 중인 스레드에 기다리지 않고 계속 진행할 수 있습니다는 `single` 섹션을 `nowait` 절에 지정할 수 있습니다는 `single` 지시문입니다.

```cpp
#pragma omp parallel
{
    #pragma omp single
        printf_s("Beginning work1.\n");
    work1();
    #pragma omp single
        printf_s("Finishing work1.\n");
    #pragma omp single nowait
        printf_s("Finished work1 and beginning work2.\n");
    work2();
}
```

## <a name="a10-sequential-ordering"></a>A.10 순차적 정렬 지정

[섹션에서는 정렬](2-directives.md#266-ordered-construct) 순차적으로 병렬로 수행 되는 작업의 출력을 정렬 하는 데 유용 합니다. 다음 프로그램 순차적에서 인덱스를 출력 합니다.

```cpp
#pragma omp for ordered schedule(dynamic)
    for (i=lb; i<ub; i+=st)
        work(i);
void work(int k)
{
    #pragma omp ordered
        printf_s(" %d", k);
}
```

## <a name="a11-a-fixed-number-of-threads"></a>A.11 고정는 스레드 수

일부 프로그램 고정, 미리 지정한 수의 스레드를 정확 하 게 실행을 사용 합니다.  구현 시 정의 된 스레드 수를 동적으로 조정 해야 하는 항목에 대 한 기본 설정 이기 때문에 이러한 프로그램 동적 스레드는 기능을 해제 하 고 이식성을 유지 하는 명시적으로 스레드 수를 설정할 수 있습니다. 다음 예제에서는 사용 하는 방법을 보여 줍니다 [omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function), 및 [omp_set_num_threads](3-run-time-library-functions.md#311-omp_set_num_threads-function):

```cpp
omp_set_dynamic(0);
omp_set_num_threads(16);
#pragma omp parallel shared(x, npoints) private(iam, ipoints)
{
    if (omp_get_num_threads() != 16)
      abort();
    iam = omp_get_thread_num();
    ipoints = npoints/16;
    do_by_16(x, iam, ipoints);
}
```

이 예제에서는 프로그램 16 스레드에 의해 실행 된 경우에 올바르게를 실행 합니다. 구현 스레드는 16을 지원할 수 없으면이 예제의 동작은 구현 시 정의 합니다.

동적 스레드 설정에 관계 없이, 병렬 영역 중 병렬 영역을 실행 하는 스레드 수 유지 합니다. 병렬 영역의 시작 부분에 사용할 스레드 수를 결정 하 고 지역 기간에 대 한 상수 유지 하는 동적 스레드 메커니즘을 합니다.

## <a name="a12-the-atomic-directive"></a>A.12 atomic 지시문

다음 예제에서는 경합 상태를 방지 (요소의 동시 업데이트 *x* 여러 스레드에 의해)를 사용 하 여 합니다 [원자성](2-directives.md#264-atomic-construct) 지시문:

```cpp
#pragma omp parallel for shared(x, y, index, n)
    for (i=0; i<n; i++)
    {
        #pragma omp atomic
            x[index[i]] += work1(i);
        y[i] += work2(i);
    }
```

사용 하는 이점은 `atomic` 지시문이이 예제에서 두 개의 다른 요소의 병렬로 발생할 수 x 업데이트 수 있다는 점입니다. 경우는 [중요](2-directives.md#262-critical-construct) 지시문은 모든 요소에 업데이트를 대신 사용 됩니다 *x* 순차적으로 (하지만 아닌 순서를 보장) 실행 됩니다.

합니다 `atomic` 지시문은 C에만 적용 됩니다. 또는 C++ 바로 다음 문입니다.  결과적으로 요소의 *y* 이 예제에서 원자 단위로 업데이트 되지 않습니다.

## <a name="a13-a-flush-directive-with-a-list"></a>A.13 목록이 있는 flush 지시문

다음 예제에서는 `flush` 스레드의 쌍 간의 특정 개체의 지점 간 동기화에 대 한 지시문:

```cpp
int   sync[NUMBER_OF_THREADS];
float work[NUMBER_OF_THREADS];
#pragma omp parallel private(iam,neighbor) shared(work,sync)
{
    iam = omp_get_thread_num();
    sync[iam] = 0;
    #pragma omp barrier

    // Do computation into my portion of work array
    work[iam] = ...;

    //  Announce that I am done with my work
    // The first flush ensures that my work is
    // made visible before sync.
    // The second flush ensures that sync is made visible.
    #pragma omp flush(work)
    sync[iam] = 1;
    #pragma omp flush(sync)

    // Wait for neighbor
    neighbor = (iam>0 ? iam : omp_get_num_threads()) - 1;
    while (sync[neighbor]==0)
    {
        #pragma omp flush(sync)
    }

    // Read neighbor's values of work array
    ... = work[neighbor];
}
```

## <a name="a14-a-flush-directive-without-a-list"></a>A.14 목록이 없는 flush 지시문

다음 예제에서는 (에 대 한 [2.6.5 섹션](2-directives.md#265-flush-directive)) 영향을 받는 공유 개체를 구별을 `flush` 지시문에 영향을 주지 않으므로 공유 개체와에서 목록이 없습니다.

```cpp
// omp_flush_without_list.c
#include <omp.h>

int x, *p = &x;

void f1(int *q)
{
    *q = 1;
    #pragma omp flush
    // x, p, and *q are flushed
    //   because they are shared and accessible
    // q is not flushed because it is not shared.
}

void f2(int *q)
{
    #pragma omp barrier
    *q = 2;

    #pragma omp barrier
    // a barrier implies a flush
    // x, p, and *q are flushed
    //   because they are shared and accessible
    // q is not flushed because it is not shared.
}

int g(int n)
{
    int i = 1, j, sum = 0;
    *p = 1;

    #pragma omp parallel reduction(+: sum) num_threads(10)
    {
        f1(&j);
        // i, n and sum were not flushed
        //   because they were not accessible in f1
        // j was flushed because it was accessible
        sum += j;
        f2(&j);
        // i, n, and sum were not flushed
        //   because they were not accessible in f2
        // j was flushed because it was accessible
        sum += i + j + *p + n;
    }
    return sum;
}

int main()
{
}
```

## <a name="a15-the-number-of-threads-used"></a>A.15 사용 되는 스레드 수

다음 예제에서는 잘못 된 것이 좋습니다 (에 대 한 [단원 3.1.2](3-run-time-library-functions.md#312-omp_get_num_threads-function)):

```cpp
np = omp_get_num_threads(); // misplaced
#pragma omp parallel for schedule(static)
    for (i=0; i<np; i++)
        work(i);
```

`omp_get_num_threads()` 하므로 코드의 직렬 섹션에서 1을 반환 호출 *np* 항상 앞의 예제에서 1와 같게 됩니다. 병렬 영역에 대 한 배포 될 스레드의 수를 확인 하려면 병렬 영역 내에서 호출 해야 합니다.

다음 예제에서는 스레드 수에 대 한 쿼리를 포함 하지 않고이 프로그램을 다시 작성 하는 방법을 보여 줍니다.

```cpp
#pragma omp parallel private(i)
{
    i = omp_get_thread_num();
    work(i);
}
```

## <a name="a16-locks"></a>A.16 Locks

다음 예제에서 (에 대 한 [3.2 섹션](3-run-time-library-functions.md#32-lock-functions)), lock 함수 인수 형식이 `omp_lock_t`를 하 고 있는 플러시 필요가 없습니다.  Lock 함수 인해 스레드가 첫 번째 중요 한 섹션에서 항목을 기다리는 동안 유휴 상태 여야 하지만 두 번째 항목을 기다리는 동안 다른 작업을 수행 합니다.  `omp_set_lock` 함수 블록 이지만 `omp_test_lock` 함수 하지 않는 작업을 허용 `skip()` 수행 합니다.

```cpp
// omp_using_locks.c
// compile with: /openmp /c
#include <stdio.h>
#include <omp.h>

void work(int);
void skip(int);

int main() {
   omp_lock_t lck;
   int id;

   omp_init_lock(&lck);
   #pragma omp parallel shared(lck) private(id)
   {
      id = omp_get_thread_num();

      omp_set_lock(&lck);
      printf_s("My thread id is %d.\n", id);

      // only one thread at a time can execute this printf
      omp_unset_lock(&lck);

      while (! omp_test_lock(&lck)) {
         skip(id);   // we do not yet have the lock,
                     // so we must do something else
      }
      work(id);     // we now have the lock
                    // and can do the work
      omp_unset_lock(&lck);
   }
   omp_destroy_lock(&lck);
}
```

## <a name="a17-nestable-locks"></a>A.17 중첩 가능 잠금

다음 예제에서는 (에 대 한 [3.2 섹션](3-run-time-library-functions.md#32-lock-functions)) 전체 구조와 해당 멤버 중 하나에 업데이트를 동기화 하는 중첩 가능 잠금을 사용할 수 있는 방법을 보여 줍니다.

```cpp
#include <omp.h>
typedef struct {int a,b; omp_nest_lock_t lck;} pair;

void incr_a(pair *p, int a)
{
    // Called only from incr_pair, no need to lock.
    p->a += a;
}

void incr_b(pair *p, int b)
{
    // Called both from incr_pair and elsewhere,
    // so need a nestable lock.

    omp_set_nest_lock(&p->lck);
    p->b += b;
    omp_unset_nest_lock(&p->lck);
}

void incr_pair(pair *p, int a, int b)
{
    omp_set_nest_lock(&p->lck);
    incr_a(p, a);
    incr_b(p, b);
    omp_unset_nest_lock(&p->lck);
}

void f(pair *p)
{
    extern int work1(), work2(), work3();
    #pragma omp parallel sections
    {
        #pragma omp section
            incr_pair(p, work1(), work2());
        #pragma omp section
            incr_b(p, work3());
    }
}
```

## <a name="a18-nested-for-directives"></a>A.18 지시문에는 중첩

다음 예제에서는 `for` [지시문 중첩](2-directives.md#29-directive-nesting) 준수 때문에 내부 및 외부 `for` 병렬 서로 다른 지역에 지시문 바인딩:

```cpp
#pragma omp parallel default(shared)
{
    #pragma omp for
        for (i=0; i<n; i++)
        {
            #pragma omp parallel shared(i, n)
            {
                #pragma omp for
                    for (j=0; j<n; j++)
                        work(i, j);
            }
        }
}
```

앞의 예제는 다음 변형은 규격 이기도합니다.

```cpp
#pragma omp parallel default(shared)
{
    #pragma omp for
        for (i=0; i<n; i++)
            work1(i, n);
}

void work1(int i, int n)
{
    int j;
    #pragma omp parallel default(shared)
    {
        #pragma omp for
            for (j=0; j<n; j++)
                work2(i, j);
    }
    return;
}
```

## <a name="a19-examples-showing-incorrect-nesting-of-work-sharing-directives"></a>A.19 작업 공유의 잘못 된 중첩을 보여 주는 예제 지시문

이 섹션의 예제를 설명 합니다 [지시문 중첩](2-directives.md#29-directive-nesting) 규칙입니다.

다음 예제는 비규격 때문에 내부 및 외부 `for` 지시문은 중첩 되어 있고 동일한 바인딩 `parallel` 지시문:

```cpp
void wrong1(int n)
{
  #pragma omp parallel default(shared)
  {
      int i, j;
      #pragma omp for
      for (i=0; i<n; i++) {
          #pragma omp for
              for (j=0; j<n; j++)
                 work(i, j);
     }
   }
}
```

위 예의 동적으로 중첩 된 다음 버전 비규격 이기도합니다.

```cpp
void wrong2(int n)
{
  #pragma omp parallel default(shared)
  {
    int i;
    #pragma omp for
      for (i=0; i<n; i++)
        work1(i, n);
  }
}

void work1(int i, int n)
{
  int j;
  #pragma omp for
    for (j=0; j<n; j++)
      work2(i, j);
}
```

다음 예제는 비규격 때문에 합니다 `for` 및 `single` 지시문 중첩 되어 있고 동일한 병렬 영역을 바인딩할 때:

```cpp
void wrong3(int n)
{
  #pragma omp parallel default(shared)
  {
    int i;
    #pragma omp for
      for (i=0; i<n; i++) {
        #pragma omp single
          work(i);
      }
  }
}
```

다음 예제는 비규격 때문에 `barrier` 내에서 지시문을 `for` 교착 상태가 발생할 수 있습니다:

```cpp
void wrong4(int n)
{
  #pragma omp parallel default(shared)
  {
    int i;
    #pragma omp for
      for (i=0; i<n; i++) {
        work1(i);
        #pragma omp barrier
        work2(i);
      }
  }
}
```

다음 예제는 비규격 때문에 `barrier` 때문에 한 번에 하나의 스레드만 중요 섹션에 입력할 수 교착 상태에서 결과:

```cpp
void wrong5()
{
  #pragma omp parallel
  {
    #pragma omp critical
    {
       work1();
       #pragma omp barrier
       work2();
    }
  }
}
```

다음 예제는 비규격 때문에 합니다 `barrier` 때문에 하나의 스레드만 실행 교착 상태에서 결과 `single` 섹션:

```cpp
void wrong6()
{
  #pragma omp parallel
  {
    setup();
    #pragma omp single
    {
      work1();
      #pragma omp barrier
      work2();
    }
    finish();
  }
}
```

## <a name="a20-bind-barrier-directives"></a>A.20 바인딩 barrier 지시문

지시문 바인딩 규칙에 대 한 호출을 `barrier` 지시문에 가장 가까운 바깥쪽 바인딩할 `parallel` 지시문입니다. 지시문 바인딩에 대 한 자세한 내용은 참조 하세요. [2.8 섹션](2-directives.md#28-directive-binding)합니다.

다음 예제에서는 식에서 호출 *주* 에 *sub2* 규격이 때문에 `barrier` (에서 *sub3*)에서 병렬 지역으로 바인딩합니다 *sub2* . 호출 *주* 하 *sub1* 규격이 때문에 `barrier` 서브루틴의 병렬 영역에 바인딩합니다 *sub2*합니다.  호출 *주* 하 *sub3* 준수 때문에 `barrier` 모든 병렬 영역에 바인딩되지 않습니다 및 무시 됩니다. 또한 합니다 `barrier` 팀에서 만든 모든 스레드 및 바깥쪽 병렬 영역에서 스레드 동기화 *sub1*합니다.

```cpp
int main()
{
    sub1(2);
    sub2(2);
    sub3(2);
}

void sub1(int n)
{
    int i;
    #pragma omp parallel private(i) shared(n)
    {
        #pragma omp for
        for (i=0; i<n; i++)
            sub2(i);
    }
}

void sub2(int k)
{
     #pragma omp parallel shared(k)
     sub3(k);
}

void sub3(int n)
{
    work(n);
    #pragma omp barrier
    work(n);
}
```

## <a name="a21-scope-variables-with-the-private-clause"></a>A.21 private 절을 사용 하 여 범위

값 `i` 고 `j` 다음 예제에서는 정의 되지 않은 병렬 영역에서 종료 시:

```cpp
int i, j;
i = 1;
j = 2;
#pragma omp parallel private(i) firstprivate(j)
{
  i = 3;
  j = j + 2;
}
printf_s("%d %d\n", i, j);
```

에 대 한 자세한 합니다 `private` 절을 참조 하세요 [2.7.2.1 섹션](2-directives.md#2721-private)합니다.

## <a name="a22-the-defaultnone-clause"></a>A.22 default (none) 절

다음 예제에서는 영향을 받는 변수를 구별 합니다 `default(none)` 없는 변수에서 절:

```cpp
// openmp_using_clausedefault.c
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int x, y, z[1000];
#pragma omp threadprivate(x)

void fun(int a) {
   const int c = 1;
   int i = 0;

   #pragma omp parallel default(none) private(a) shared(z)
   {
      int j = omp_get_num_thread();
             //O.K.  - j is declared within parallel region
      a = z[j];       // O.K.  - a is listed in private clause
                      //      - z is listed in shared clause
      x = c;          // O.K.  - x is threadprivate
                      //      - c has const-qualified type
      z[i] = y;       // C3052 error - cannot reference i or y here

      #pragma omp for firstprivate(y)
         for (i=0; i<10 ; i++) {
            z[i] = y;  // O.K. - i is the loop control variable
                       // - y is listed in firstprivate clause
          }
       z[i] = y;   // Error - cannot reference i or y here
   }
}
```

에 대 한 자세한 합니다 `default` 절을 참조 하세요 [2.7.2.5 섹션](2-directives.md#2725-default)합니다.

## <a name="a23-examples-of-the-ordered-directive"></a>A.23 ordered 지시문 예제

많은 순서가 지정 된 섹션을 사용 하 여 포함할 수 있기를 `for` 지정 된 된 `ordered` 절. 첫 번째 예제에서는 비규격 이므로 API는 다음 규칙을 지정 합니다.

"사용 하는 루프의 반복을 `for` 구문을 실행 해서는 안 동일 `ordered` 지시문 보다 하며 한 번 실행 하면 안 둘 이상의 `ordered` 지시문입니다." (참조 [2.6.6 섹션](2-directives.md#266-ordered-construct).)

모든 반복이 호환 되지 않는 예제에서는 두 개의 정렬 된 섹션을 실행합니다.

```cpp
#pragma omp for ordered
for (i=0; i<n; i++)
{
    ...
    #pragma omp ordered
    { ... }
    ...
    #pragma omp ordered
    { ... }
    ...
}
```

에서는 다음 준수 예제는 `for` 개를 사용 하 여 순서가 지정 된 섹션:

```cpp
#pragma omp for ordered
for (i=0; i<n; i++)
{
    ...
    if (i <= 10)
    {
        ...
        #pragma omp ordered
        { ... }
    }
    ...
    (i > 10)
    {
        ...
        #pragma omp ordered
        { ... }
    }
    ...
}
```

## <a name="a24-example-of-the-private-clause"></a>A.24 private 절 예제

합니다 [개인](2-directives.md#2721-private) 병렬 영역의 절에만 동적 범위 영역의 아닌 어휘 범위의 지역에 적용 됩니다.  사용 하 여, 모든 변수의 예와 따라서 *는* 내에서 `for` 루틴에 루프 *f* 의 전용 복사본을 가리킵니다 *는*에서 사용 하는 동안 루틴 *g* 전역 가리킵니다 *는*합니다.

```cpp
int a;

void f(int n)
{
    a = 0;

    #pragma omp parallel for private(a)
    for (int i=1; i<n; i++)
    {
        a = i;
        g(i, n);
        d(a);     // Private copy of "a"
        ...
    }
    ...

void g(int k, int n)
{
    h(k,a); // The global "a", not the private "a" in f
}
```

## <a name="a25-examples-of-the-copyprivate-data-attribute-clause"></a>A.25 copyprivate 데이터 특성 절 예제

**예제 1:** 합니다 [copyprivate](2-directives.md#2728-copyprivate) 절 브로드캐스트를 다른 스레드에서 개인 변수의 모든 인스턴스에 직접 단일 스레드에 의해 획득 되는 값을 사용할 수 있습니다.

```cpp
float x, y;
#pragma omp threadprivate(x, y)

void init( )
{
    float a;
    float b;

    #pragma omp single copyprivate(a,b,x,y)
    {
        get_values(a,b,x,y);
    }

    use_values(a, b, x, y);
}
```

경우 일상적인 *init* 라고 직렬 지역에서 해당 동작 지시문의 현재 상태에 영향을 받지 않습니다. 호출한 후 합니다 *get_values* 루틴 한 스레드에 의해 실행 된, 스레드가 없는 개인 개체에서 지정 될 때까지 구문을 유지 *는*, *b*, *x*, 및 *y* 읽은 값을 사용 하 여 모든 스레드에서 정의 됩니다.

**예제 2:** 이전 예제와 달리 읽기 마스터 스레드 예를 들어, 특정 스레드에서 수행 해야 합니다를 가정 합니다. 이 경우에 `copyprivate` 브로드캐스트를 직접 할 절을 사용할 수 없습니다 하지만 임시 공유 개체에 대 한 액세스를 위해 사용할 수 있습니다.

```cpp
float read_next( )
{
    float * tmp;
    float return_val;

    #pragma omp single copyprivate(tmp)
    {
        tmp = (float *) malloc(sizeof(float));
    }

    #pragma omp master
    {
        get_float( tmp );
    }

    #pragma omp barrier
    return_val = *tmp;
    #pragma omp barrier

    #pragma omp single
    {
       free(tmp);
    }

    return return_val;
}
```

**예제 3:** 병렬 영역 내부에서는 필요한 잠금 개체의 수에 입력 하기 전에 쉽게 확인할 수 없는 경우 `copyprivate` 병렬 해당 영역 내에서 할당 된 공유 잠금 개체에 대 한 액세스를 제공 하려면 절을 사용할 수 있습니다.

```cpp
#include <omp.h>

omp_lock_t *new_lock()
{
    omp_lock_t *lock_ptr;

    #pragma omp single copyprivate(lock_ptr)
    {
        lock_ptr = (omp_lock_t *) malloc(sizeof(omp_lock_t));
        omp_init_lock( lock_ptr );
    }

    return lock_ptr;
}
```

## <a name="a26-the-threadprivate-directive"></a>A.26 threadprivate 지시문

다음 예제에 사용 하는 방법을 보여 줍니다 합니다 [threadprivate](2-directives.md#271-threadprivate-directive) 지시문을 각 스레드에 별도 카운터를 제공 합니다.

### <a name="example-1"></a>예제 1

```cpp
int counter = 0;
#pragma omp threadprivate(counter)

int sub()
{
    counter++;
    return(counter);
}
```

### <a name="example-2"></a>예제 2

```cpp
int sub()
{
    static int counter = 0;
    #pragma omp threadprivate(counter)
    counter++;
    return(counter);
}
```

## <a name="a27-c99-variable-length-arrays"></a>A.27 C99 가변 길이 배열 사용

다음 예제에서 C99 가변 길이 배열 (Vla)를 사용 하는 방법에 설명 된 [firstprivate](2-directives.md#2722-firstprivate) 지시문입니다.

> [!NOTE]
> 가변 길이 배열 시각적 개체의 현재 지원 되지 않습니다 C++입니다.

```cpp
void f(int m, int C[m][m])
{
    double v1[m];
    ...
    #pragma omp parallel firstprivate(C, v1)
    ...
}
```

## <a name="a28-the-numthreads-clause"></a>A.28 num_threads 절

다음 예제는 [num_threads](2-directives.md#23-parallel-construct) 절. 병렬 영역을 최대 10 개 스레드를 사용 하 여 실행 됩니다.

```cpp
#include <omp.h>
main()
{
    omp_set_dynamic(1);
    ...
    #pragma omp parallel num_threads(10)
    {
        ... parallel region ...
    }
}
```

## <a name="a29-work-sharing-constructs-inside-a-critical-construct"></a>A.29 critical 구문 내 작업 공유 구문

다음 예제에서는 내 작업 공유 구문을 사용 하는 `critical` 생성 합니다. 이 예제는 규격 상태가 생성 작업 공유 및 `critical` 구문을 병렬 동일한 지역에 연결 하지.

```cpp
void f()
{
  int i = 1;
  #pragma omp parallel sections
  {
    #pragma omp section
    {
      #pragma omp critical (name)
      {
        #pragma omp parallel
        {
          #pragma omp single
          {
            i++;
          }
        }
      }
    }
  }
}
```

## <a name="a30-reprivatization"></a>A.30 재 전용 화

다음 예제에서는 변수의 재 전용 화는 방법을 보여 줍니다. Private 변수를 표시할 수 있습니다 `private` 중첩 된 지시문에서 다시 합니다. 병렬 영역 바깥쪽에 있는 해당 변수를 공유할 필요가 없습니다.

```cpp
int i, a;
...
#pragma omp parallel private(a)
{
  ...
  #pragma omp parallel for private(a)
  for (i=0; i<10; i++)
     {
       ...
     }
}
```

## <a name="a31-thread-safe-lock-functions"></a>A.31 스레드로부터 안전한 lock 함수

다음 C++ 예제를 사용 하 여 병렬 영역에 있는 잠금의 배열을 초기화 하는 방법을 보여 줍니다 [omp_init_lock](3-run-time-library-functions.md#321-omp_init_lock-and-omp_init_nest_lock-functions)합니다.

```cpp
// A_13_omp_init_lock.cpp
// compile with: /openmp
#include <omp.h>

omp_lock_t *new_locks() {
   int i;
   omp_lock_t *lock = new omp_lock_t[1000];
   #pragma omp parallel for private(i)
   for (i = 0 ; i < 1000 ; i++)
      omp_init_lock(&lock[i]);

   return lock;
}

int main () {}
```
