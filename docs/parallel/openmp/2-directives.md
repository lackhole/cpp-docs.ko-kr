---
title: 2. 지시문
ms.date: 01/18/2019
ms.assetid: d1a69374-6c03-45fb-8c86-e91cea8adae8
ms.openlocfilehash: 125d2d83b277e62d007e3a208e426ea717d52790
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62363715"
---
# <a name="2-directives"></a>2. 지시문

지시문에 기반한 `#pragma` 지시문은 C로 정의 된 하 고 C++ 표준입니다.  OpenMP C를 지 원하는 컴파일러 및 C++ API를 활성화 하 고 모든 OpenMP 컴파일러 지시문의 해석을 허용 하는 명령줄 옵션에 포함 됩니다.

## <a name="21-directive-format"></a>2.1 지시문 형식

OpenMP 지시문의 구문은 문법을 공식적으로 지정 된 [부록 C](c-openmp-c-and-cpp-grammar.md)에서 같이 비공식적으로:

```cpp
#pragma omp directive-name  [clause[ [,] clause]...] new-line
```

각 지시문 시작 `#pragma omp`를 같은 이름의 다른 (openmp-OpenMP 또는 공급 업체 확장) pragma 지시문을 사용 하 여 충돌을 방지 합니다. 지시문의 나머지 부분에는 C의 규칙을 따릅니다 및 C++ 컴파일러 지시문에 대 한 표준입니다. 특히 공백을 사용할 수 앞과 뒤는 `#`, 경우에 따라 공백을 해야 하는 데 사용할 지시문에서 단어를 구분 합니다. 다음 토큰을 전처리 합니다 `#pragma omp` 매크로 대체 될 수 있습니다.

지시문 대/소문자를 구분 하지 않습니다. 지시문의 절이 표시 되는 순서는 중요 하지. 각 절에 대 한 설명을에 나열 된 제한이 필요에 따라 지시문에 절을 반복 될 수 있습니다. 하는 경우 *변수 목록* 절에만 변수를 지정 해야 표시 됩니다. 하나만 *지시문 이름* 지시문에 따라 지정할 수 있습니다.  예를 들어 다음 지시문이 허용 되지 않습니다.

```cpp
/* ERROR - multiple directive names not allowed */
#pragma omp parallel barrier
```

최대 하나의 후속 문, 구조화 된 블록 이어야 하는 OpenMP 지시문에 적용 됩니다.

## <a name="22-conditional-compilation"></a>2.2 조 건 부 컴파일

`_OPENMP` 10 진 상수와 매크로 이름이 OpenMP 규격 구현에서 정의 된 *yyyymm*, 연도 및 월의 승인 된 사양을 수 있습니다. 이 매크로는의 주체를 사용 해야 합니다.는 `#define` 또는 `#undef` 전처리 지시문입니다.

```cpp
#ifdef _OPENMP
iam = omp_get_thread_num() + index;
#endif
```

공급 업체 확장 openmp를 정의 하는 경우 추가 미리 정의 된 매크로 지정할 수 있습니다.

## <a name="23-parallel-construct"></a>2.3 parallel 구문

다음 지시문을 동시에 여러 스레드에서 실행할 프로그램의 영역인 병렬 영역을 정의 합니다. 이 지시문에는 병렬 실행을 시작 하는 기본 구문입니다.

```cpp
#pragma omp parallel [clause[ [, ]clause] ...] new-line   structured-block
```

합니다 *절* 다음 중 하나입니다.

- `if(` *scalar-expression* `)`
- `private(` *variable-list* `)`
- `firstprivate(` *variable-list* `)`
- `default(shared | none)`
- `shared(` *variable-list* `)`
- `copyin(` *variable-list* `)`
- `reduction(` *operator* `:`  *variable-list* `)`
- `num_threads(` *integer-expression* `)`

병렬 구문에 대 한 스레드를 가져오면 다음과 같은 경우 중 하나가 참인 경우 스레드 팀이 만들어집니다.

- 이상 `if` 절이 있습니다.
- `if` 식이 0이 아닌 값입니다.

이 스레드가 마스터 스레드는 스레드 번호 0 사용 하 여 팀의 되며 마스터 스레드를 포함 하 여 팀의 모든 스레드 지역을 병렬로 실행 합니다. 경우 값은 `if` 식이 0 이면, 지역 serialize 됩니다.

요청 된 스레드의 수를 확인 하려면 다음 규칙 순서로 간주 됩니다. 조건이 충족 될 첫 번째 규칙이 적용 됩니다.

1. 경우는 `num_threads` 절을 사용할 수 있으면 다음 정수 식의 값을 요청 하는 스레드입니다.

1. 경우는 `omp_set_num_threads` 라이브러리 함수를 호출한 다음 가장 최근에 실행된 한 호출의 인수 값은 요청 스레드의 수입니다.

1. 경우 환경 변수 `OMP_NUM_THREADS` 이 환경 변수의 값은 요청 하는 스레드 수가 정의 됩니다.

1. 위의 메서드는 요청 스레드 수가 경우 구현 시 정의 합니다.

경우는 `num_threads` 절이 있으면 다음 요청한 스레드의 개수를 대체 합니다 `omp_set_num_threads` 라이브러리 함수 또는 `OMP_NUM_THREADS` 적용할 때 병렬 영역에 대해서만 환경 변수입니다. 병렬 영역 나중에 의해 영향을 받지 않습니다.

병렬 영역을 실행 하는 스레드 수가 스레드 수를 동적으로 조정을 사용할지 결정 됩니다. 동적으로 조정 하지 않으면 스레드 수가 요청 된 병렬 영역을 실행 됩니다. 이상을 사용 하는 경우 요청 된 스레드 수는 병렬 영역을 실행할 수 있는 스레드의 최대 수입니다.

병렬 영역 스레드 수를 동적으로 조정 하지 않으면 병렬 영역에 대 한 요청 스레드의 수를 사용 하면 런타임 시스템에서 제공할 수 있는 수보다 더 하는 동안 발생 하는 경우 프로그램의 동작은 구현 시 정의 합니다. 구현을 프로그램의 실행을 중단할 예를 들어 수 또는 병렬 영역을 serialize 될 수 있습니다.

합니다 `omp_set_dynamic` 라이브러리 함수 및 `OMP_DYNAMIC` 설정 및 해제 스레드 수를 동적으로 조정 하는 환경 변수를 사용할 수 있습니다.

스레드가 지정된 된 시간에 실제로 호스팅하는 실제 프로세서 수가 구현 시 정의 됩니다. 만들어지면 팀의 스레드 수는 병렬 영역 기간에 대 한 상수 유지 됩니다. 다른 하나의 병렬 영역에서 런타임 시스템에서 사용자가 명시적으로 또는 자동으로 변경할 수 있습니다.

병렬 영역 동적 범위 내에 포함 된 문은 각 스레드에 의해 실행 됩니다 하 고 각 스레드가 다른 스레드에서 다른 문의 경로 실행할 수 있습니다. 병렬 영역 어휘 범위 외부에서 발생 하는 지시문 분리 된 지시문으로 참조 됩니다.

병렬 영역 끝에는 묵시적된 장벽이 있습니다. 팀의 마스터 스레드만 병렬 영역 끝에 실행을 계속합니다.

병렬 영역을 실행 하는 팀의 스레드가 다른 병렬 구문을 발견 하면, 새 팀을 만들면 및 새 팀에 마스터 서버가 됩니다. 중첩 된 병렬 영역은 기본적으로 serialize 됩니다. 결과적으로, 기본적으로 중첩 된 병렬 영역 중 하나의 구성 하는 팀에서 실행 됩니다. 런타임 라이브러리 함수를 사용 하 여 기본 동작을 변경할 수 있습니다 `omp_set_nested` 환경 변수 또는 `OMP_NESTED`합니다. 그러나 중첩 된 병렬 영역을 실행 하는 팀의 스레드 수가 구현이 정의 됩니다.

에 대 한 제한 된 `parallel` 지시문은 다음과 같습니다.

- 최대 하나 `if` 지시문에 절에 나타날 수 있습니다.

- If 내 효과 쪽 하나라도 있는지 여부를 지정 하지 않으면에 식 또는 `num_threads` 식 발생 합니다.

- `throw` 실행 병렬 영역 내에서 같은 구조화 된 블록의 동적 범위 내에서 다시 시작 하려면 실행을 수행 해야 하 고 예외를 발생 시킨 동일한 스레드에서 찾아내야 합니다.

- 단일 `num_threads` 지시문에 절에 나타날 수 있습니다. `num_threads` 식 병렬 영역의 컨텍스트 외부에서 평가 되 고 양의 정수 값으로 계산 되어야 합니다.

- 계산 순서를 `if` 고 `num_threads` 절이 지정 되지 않습니다.

### <a name="cross-references"></a>상호 참조

- `private`를 `firstprivate`, `default`, `shared`합니다 `copyin`, 및 `reduction` 절 ([2.7.2 섹션](#272-data-sharing-attribute-clauses))
- [OMP_NUM_THREADS](4-environment-variables.md#42-omp_num_threads) 환경 변수
- [omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function) 라이브러리 함수
- [OMP_DYNAMIC](4-environment-variables.md#43-omp_dynamic) 환경 변수
- [omp_set_nested](3-run-time-library-functions.md#319-omp_set_nested-function) function
- [OMP_NESTED](4-environment-variables.md#44-omp_nested) 환경 변수
- [omp_set_num_threads](3-run-time-library-functions.md#311-omp_set_num_threads-function) 라이브러리 함수

## <a name="24-work-sharing-constructs"></a>2.4 작업 공유 구문

작업 공유 구문이 발생 하는 팀 구성원 중에서 연결된 된 문 실행을 배포 합니다. 작업 공유 지시문에는 새 스레드를 시작 하지 않음 및 작업 공유 구문에 대 한 항목에는 묵시적된 장벽이 없습니다.

작업 공유 시퀀스를 생성 하 고 `barrier` 팀의 모든 스레드에 대해 발생 하는 지시문 같아야 합니다.

OpenMP 다음 작업 공유 생성자를 정의 하 고 이러한 구문 섹션에 설명 되어 있습니다.

- [에 대 한](#241-for-construct) 지시문
- [섹션](#242-sections-construct) 지시문
- [단일](#243-single-construct) 지시문

### <a name="241-for-construct"></a>2.4.1 for 구문

`for` 지시문에 병렬로 연결된 루프의 반복을 실행할지를 지정 하는 반복 작업 공유 생성자를 식별 합니다. 반복 된 `for` 루프 바인딩되기는 병렬 구문을 실행 하는 팀에서 이미 존재 하는 스레드 간에 분산 됩니다. 구문의 `for` 구문은 다음과 같습니다.

```cpp
#pragma omp for [clause[[,] clause] ... ] new-line for-loop
```

절은 다음 중 하나입니다.

- `private(` *variable-list* `)`
- `firstprivate(` *variable-list* `)`
- `lastprivate(` *variable-list* `)`
- `reduction(` *operator* `:` *variable-list* `)`
- `ordered`
- `schedule(` *kind* [`,` *chunk_size*] `)`
- `nowait`

합니다 `for` 지시문의 해당 구조에 제한을 배치 `for` 루프입니다. 특히, 해당 `for` 루프 정식 셰이프 있어야 합니다.

`for (` *init-expr* `;` *var  logical-op  b* `;` *incr-expr* `)`

*init-expr*<br/>
다음 중 하나:

- *var* = *lb*
- *integer-type var* = *lb*

*incr-expr*<br/>
다음 중 하나:

- `++` *var*
- *var* `++`
- `--` *var*
- *var* `--`
- *var* `+=` *incr*
- *var* `-=` *incr*
- *var* `=` *var* `+` *incr*
- *var* `=` *incr* `+` *var*
- *var* `=` *var* `-` *incr*

*var*<br/>
부호 있는 정수 변수입니다. 이 변수를 공유 그렇지 않은 경우 암시적으로 만들어질 개인 기간을 `for`입니다. 본문 내에서이 변수를 수정 하지 마십시오는 `for` 문입니다. 변수를 지정 하지 않으면 `lastprivate`, 루프 되지 않으며 후 해당 값입니다.

*logical-op*<br/>
다음 중 하나:

- `<`
- `<=`
- `>`
- `>=`

*lb*하십시오 *b*, 및 *incr*<br>
루프 고정 정수 식입니다. 동기화가 없는지 이러한 식의 평가 하는 동안 평가 부작용 불확실 한 결과 생성 하도록 합니다.

정규 형식 루프 반복 루프에 진입 시 계산할 수가 있습니다. 형식의 값을 사용 하 여이 계산 됩니다 *var*, 정수 계열 확장 후 합니다. 경우에 특히에 값 *b* `-` *lb* `+` *incr* 형식 결과 확정적이 지에 나타낼 수 없습니다. 또한 경우 *op 논리* 는 `<` 또는 `<=`, 한 다음 *incr expr* 수행 해야 하는 *var* 루프가 반복 될 때마다 증가 하 합니다.   경우 *논리 op* 은 `>` 또는 `>=`, 다음 *incr expr* 수행 해야 하는 *var* 루프가 반복 될 때마다 작은 가져오려고 합니다.

`schedule` 절을 지정 하는 방법의 반복을 `for` 루프 팀의 스레드 분할 됩니다. 프로그램의 정확성 스레드 실행은 특정 반복에 종속 되지 않아야 합니다. 변수의 *chunk_size*지정한 경우 양수 값을 사용 하 여 루프 고정 정수 식 이어야 합니다. 동기화가 없는지이 식의 평가 하는 동안 평가 부작용 불확실 한 결과 생성 하도록 합니다. 일정 *종류* 다음 값 중 하나일 수 있습니다.

1-테이블 2: `schedule` 절 *종류* 값

|||
|-|-|
|정적|때 `schedule(static,` *chunk_size* `)` 지정 된 경우 반복 하 여 지정 된 크기의 청크로 나뉩니다 *chunk_size*합니다. 청크는 스레드는 스레드 번호 순으로 라운드 로빈 방식으로 팀에 정적으로 할당 됩니다. 없는 경우 *chunk_size* 지정 된 경우 반복 공간이 하나의 청크로 각 스레드에 할당 된 크기에 거의 동일한 청크로 분할 됩니다.|
|dynamic|때 `schedule(dynamic,` *chunk_size* `)` 지정 된 경우 반복은 일련의 청크를 포함 하는 각 나뉩니다 *chunk_size* 반복 합니다. 각 청크는 할당에 대 한 대기 중인 스레드에 할당 됩니다. 스레드 반복의 청크를 실행 하 고 할당할 청크가 없습니다 남을 때까지 해당 다음 할당을 기다립니다. 할당할 마지막 청크 적은 개수의 반복 있을 수 있습니다. 없는 경우 *chunk_size* 지정 된 경우 기본값은 1입니다.|
|문제 해결|때 `schedule(guided,` *chunk_size* `)` 지정 된 경우 반복 청크 크기를 줄이면와에서 스레드에 할당 됩니다. 반복의 할당 된 해당 청크는 스레드가 완료 되어도 그대로 none 될 때까지 다른 청크를 동적으로 할당 했습니다 것입니다. 에 *chunk_size* 1의 각 청크 크기가 약 반복 횟수를 지정 하지 않은 스레드 수로 나눈 값입니다. 이러한 크기는 1로 거의 기하급수적으로 줄입니다. 에 대 한는 *chunk_size* 값을 사용 하 여 *k* 1 보다 큰 크기에 거의 기하급수적으로 감소 *k*단 있을 마지막 청크 미만, *k* 반복 합니다. 없는 경우 *chunk_size* 지정 된 경우 기본값은 1입니다.|
|런타임|때 `schedule(runtime)` 지정 된 경우 런타임 시까지 지연 됩니다에 관한 일정 결정 합니다. 일정 *종류* 환경 변수를 설정 하 여 런타임 시 청크 크기를 선택할 수 있습니다 및 `OMP_SCHEDULE`합니다. 이 환경 변수 설정 하지 않으면 결과 일정 구현 시 정의 됩니다. 때 `schedule(runtime)` 지정 된 *chunk_size* 지정 하면 안 됩니다.|

명시적으로 정의 된 없으면에서 `schedule` 절, 기본 `schedule` 구현 시 정의 됩니다.

OpenMP 규격 프로그램을 올바르게 실행에 대 한 특정 일정 의존해 서는 안 됩니다. 프로그램을 일정에 의존해 서는 안 *종류* 동일한 일정에는 변형 이름이 있을 수 있기 때문에 위에서 지정 된 설명의을 정확 하 게 준수 *종류* 에서 다른 컴파일러입니다. 특정 상황에 적절 한 일정을 선택할 수는 설명은 사용할 수 있습니다.

합니다 `ordered` 절 있어야 시기 `ordered` 지시문에 바인딩할를 `for` 생성 합니다.

끝에 암시적 장벽 방법이 `for` 하지 않는 경우 생성할는 `nowait` 절을 지정 합니다.

에 대 한 제한 된 `for` 지시문은 다음과 같습니다.

- 합니다 `for` 루프는 구조화 된 블록 이어야 합니다 하 고 해당 실행을 하 여 종료 되지 해야 또한는 `break` 문입니다.

- 루프의 값을 제어 식의 합니다 `for` 연관 루프를 `for` 지시문 팀의 모든 스레드에 대해 동일 해야 합니다.

- `for` 루프 반복 변수 부호 있는 정수 형식 이어야 합니다.

- 단일 `schedule` 절에 나타날 수 있습니다는 `for` 지시문입니다.

- 단일 `ordered` 절에 나타날 수 있습니다는 `for` 지시문입니다.

- 단일 `nowait` 절에 나타날 수 있습니다는 `for` 지시문입니다.

- 지정 되지 않은 경우 또는 내 모든 측면에 영향을 얼마나 자주 합니다 *chunk_size*, *lb*를 *b*, 또는 *incr* 식은 발생 합니다.

- 값을 *chunk_size* 식 팀의 모든 스레드에 대해 동일 해야 합니다.

#### <a name="cross-references"></a>상호 참조

- `private`를 `firstprivate`하십시오 `lastprivate`, 및 `reduction` 절 ([2.7.2 섹션](#272-data-sharing-attribute-clauses))
- [OMP_SCHEDULE](4-environment-variables.md#41-omp_schedule) 환경 변수
- [정렬](#266-ordered-construct) 생성
- [일정](d-using-the-schedule-clause.md) 절

### <a name="242-sections-construct"></a>2.4.2 섹션 구문

`sections` 지시문 팀에서 스레드로 분배 하는 구문 집합을 지정 하는 noniterative 작업 공유 구문으로 식별 합니다. 각 섹션은 팀의 스레드에 의해 한 번 실행 됩니다. 구문의 `sections` 지시문은 다음과 같습니다.

```cpp
#pragma omp sections [clause[[,] clause] ...] new-line
   {
   [#pragma omp section new-line]
      structured-block
   [#pragma omp section new-linestructured-block ]
...
}
```

절은 다음 중 하나입니다.

- `private(` *variable-list* `)`
- `firstprivate(` *variable-list* `)`
- `lastprivate(` *variable-list* `)`
- `reduction(` *operator* `:`  *variable-list* `)`
- `nowait`

각 섹션 앞에 `section` 지시문을 있지만 `section` 지시문은 첫 번째 섹션에 대 한 선택 사항입니다. 합니다 `section` 어휘 범위 내에 지시문이 나타나야 합니다는 `sections` 지시문입니다. 끝에는 암시적 장벽이를 `sections` 하지 않는 경우 생성할를 `nowait` 지정 됩니다.

에 대 한 제한 된 `sections` 지시문은 다음과 같습니다.

- A `section` 지시문의 어휘 범위 외부에 나타나지 않아야 합니다 `sections` 지시문입니다.

- 단일 `nowait` 절에 나타날 수 있습니다는 `sections` 지시문입니다.

#### <a name="cross-references"></a>상호 참조

- `private`를 `firstprivate`하십시오 `lastprivate`, 및 `reduction` 절 ([2.7.2 섹션](#272-data-sharing-attribute-clauses))

### <a name="243-single-construct"></a>2.4.3 single 구문

`single` 지시문 연결된 된 구조화 된 블록 (반드시 마스터 스레드) 팀에서 하나의 스레드에 의해 실행 되도록 지정 하는 구문으로 식별 합니다. 구문의 `single` 지시문은 다음과 같습니다.

```cpp
#pragma omp single [clause[[,] clause] ...] new-linestructured-block
```

절은 다음 중 하나입니다.

- `private(` *variable-list* `)`
- `firstprivate(` *variable-list* `)`
- `copyprivate(` *variable-list* `)`
- `nowait`

암시적 장벽 후는 `single` 하지 않는 경우 생성할를 `nowait` 절을 지정 합니다.

에 대 한 제한 된 `single` 지시문은 다음과 같습니다.

- 단일 `nowait` 절에 나타날 수 있습니다는 `single` 지시문입니다.
- 합니다 `copyprivate` 절을 함께 사용 되어야 합니다는 `nowait` 절.

#### <a name="cross-references"></a>상호 참조

- `private`하십시오 `firstprivate`, 및 `copyprivate` 절 ([2.7.2 섹션](#272-data-sharing-attribute-clauses))

## <a name="25-combined-parallel-work-sharing-constructs"></a>2.5 결합 된 병렬 작업 공유 구문

결합 된 병렬 작업 공유 구문은 하나의 작업 공유 생성자를 가진 병렬 영역을 지정 하기 위한 바로 가기입니다. 이러한 지시문의 의미 체계는 명시적으로 지정 하는 것과 `parallel` 는 단일 작업 공유 구문 뒤에 지시문입니다.

다음 섹션에서는 결합 된 병렬 작업 공유 구문에 설명 합니다.

- [에 대 한 병렬](#251-parallel-for-construct) 지시문
- [섹션에서는 병렬](#252-parallel-sections-construct) 지시문

### <a name="251-parallel-for-construct"></a>2.5.1 parallel for 구문

합니다 `parallel for` 지시문에 대 한 바로 가기입니다를 `parallel` 하나만 포함 하는 영역 `for` 지시문입니다. 구문의 `parallel for` 지시문은 다음과 같습니다.

```cpp
#pragma omp parallel for [clause[[,] clause] ...] new-linefor-loop
```

이 지시문의 절을 사용 합니다 `parallel` 지시문 및 `for` 지시문을 제외 하 고는 `nowait` 동일한 의미 및 제한 사항으로 절. 의미 체계가 같습니다 명시적으로 지정 하는 `parallel` 지시문 바로 뒤에 `for` 지시문입니다.

#### <a name="cross-references"></a>상호 참조

- [parallel](#23-parallel-construct) directive
- [에 대 한](#241-for-construct) 지시문
- [데이터 특성 절](#272-data-sharing-attribute-clauses)

### <a name="252-parallel-sections-construct"></a>2.5.2 parallel 섹션 구문

`parallel sections` 지시어를 지정 하기 위한 바로 가기 양식을 제공을 `parallel` 지역 하나만 있는 `sections` 지시문입니다. 의미 체계가 같습니다 명시적으로 지정 하는 `parallel` 지시문 바로 뒤에 `sections` 지시문입니다. 구문의 `parallel sections` 지시문은 다음과 같습니다.

```cpp
#pragma omp parallel sections  [clause[[,] clause] ...] new-line
   {
   [#pragma omp section new-line]
      structured-block
   [#pragma omp section new-linestructured-block  ]
   ...
}
```

*절* 수락한 절 중 하나일 수 있습니다 합니다 `parallel` 및 `sections` 지시문을 제외 하 고는 `nowait` 절.

#### <a name="cross-references"></a>상호 참조

- [parallel](#23-parallel-construct) directive
- [섹션](#242-sections-construct) 지시문

## <a name="26-master-and-synchronization-directives"></a>2.6 Master 및 동기화 지시문

다음 섹션에 설명합니다.

- [마스터](#261-master-construct) 생성
- [중요 한](#262-critical-construct) 생성
- [barrier](#263-barrier-directive) directive
- [원자성](#264-atomic-construct) 생성
- [flush](#265-flush-directive) directive
- [정렬](#266-ordered-construct) 생성

### <a name="261-master-construct"></a>2.6.1 master 구문

`master` 지시문 팀의 마스터 스레드에 의해 실행 되는 구조화 된 블록을 지정 하는 구문으로 식별 합니다. 구문의 `master` 지시문은 다음과 같습니다.

```cpp
#pragma omp master new-linestructured-block
```

팀의 다른 스레드에 연결된 된 구조화 된 블록을 실행 하지 않습니다. 항목 또는 종료 master 구문에서 암시적된 장벽이 없습니다 있습니다.

### <a name="262-critical-construct"></a>2.6.2 critical 구문

`critical` 지시문 식별 한 번에 단일 스레드에 연결된 된 구조화 된 블록 실행을 제한 하는 구문입니다. 구문의 `critical` 지시문은 다음과 같습니다.

```cpp
#pragma omp critical [(name)]  new-linestructured-block
```

선택적인 *이름을* 중요 영역을 식별할 수 있습니다. 중요 영역을 식별 하는 데 사용 되는 식별자에 외부 링크가 있으며 레이블, 태그, 멤버 및 일반 식별자에서 사용 하는 네임 스페이스와 별개인 네임 스페이스입니다.

스레드가 다른 스레드가 동일한 이름 가진 (프로그램)에서 아무 곳 이나 중요 영역 실행 될 때까지 중요 영역 맨 앞에 대기 합니다. 모든 명명 되지 않은 `critical` 지시문 이름이 지정 되지 않은 매핑됩니다.

### <a name="263-barrier-directive"></a>2.6.3 barrier 지시문

`barrier` 지시문 팀의 모든 스레드를 동기화 합니다. 발생 하면 팀의 각 스레드가 다른 모든 것이 점에 도달할 때까지 기다립니다. 구문의 `barrier` 지시문은 다음과 같습니다.

```cpp
#pragma omp barrier new-line
```

팀의 모든 스레드가 장애물, 발생 한 후 팀에서 각 스레드는 병렬에서 barrier 지시문 다음 문을 실행을 시작 합니다. 때문에 `barrier` 지시문에는 해당 구문의 일부로 C 언어 문이 없는, 프로그램에서의 위치에 몇 가지 제한이 있습니다. 정식 문법에 대 한 자세한 내용은 참조 하세요. [부록 C](c-openmp-c-and-cpp-grammar.md)합니다. 아래 예제에서는 이러한 제한 사항을 보여 줍니다.

```cpp
/* ERROR - The barrier directive cannot be the immediate
*          substatement of an if statement
*/
if (x!=0)
   #pragma omp barrier
...

/* OK - The barrier directive is enclosed in a
*      compound statement.
*/
if (x!=0) {
   #pragma omp barrier
}
```

### <a name="264-atomic-construct"></a>2.6.4 atomic 구문

`atomic` 지시문 하면 다 수의 가능성에 노출 하는 대신 특정 메모리 위치를 개별적으로 업데이트 되는 동시 스레드를 작성 합니다. 구문의 `atomic` 지시문은 다음과 같습니다.

```cpp
#pragma omp atomic new-lineexpression-stmt
```

식 문에 다음 형식 중 하나가 있어야 합니다.

- *x binop* `=` *expr*
- *x* `++`
- `++` *x*
- *x* `--`
- `--` *x*

이전 식:

- *x* 스칼라 형식의 lvalue 식입니다.

- *expr* 스칼라 형식이 있는 식을 이며 지정 된 개체 참조 하지 않는 *x*합니다.

- *binop* 오버 로드 된 연산자가 아니고 중 하나인 `+`, `*`, `-`, `/`를 `&`, `^`를 `|`, `<<`, 또는 `>>`합니다.

이지만 구현 시 정의 된 구현을 모두 대체 여부 `atomic` 사용 하 여 지시문 `critical` 동일한 고유 지시문 *이름*의 `atomic` 허용 최적화를 개선 하는 지시문 . 하드웨어 관련 지침은 종종 오버 헤드가 가장을 사용 하 여 원자성 업데이트를 수행할 수 있는 합니다.

부하 및 지정 된 개체의 저장소 *x* 은; 평가 *expr* 원자성이 아니므로 합니다. 경합 상황을 방지 하려면 사용 하 여 병렬로 위치의 모든 업데이트를 보호 합니다 `atomic` 경합의 사용 가능한 것으로 알려진 제외한 지시문입니다.

에 대 한 제한 된 `atomic` 지시문은 다음과 같습니다.

- 프로그램 전체에서 저장소 위치 x에 대 한 모든 원자성 참조 형식이 호환 해야 합니다.

#### <a name="examples"></a>예제

```cpp
extern float a[], *p = a, b;
/* Protect against races among multiple updates. */
#pragma omp atomic
a[index[i]] += b;
/* Protect against races with updates through a. */
#pragma omp atomic
p[i] -= 1.0f;

extern union {int n; float x;} u;
/* ERROR - References through incompatible types. */
#pragma omp atomic
u.n++;
#pragma omp atomic
u.x -= 1.0f;
```

### <a name="265-flush-directive"></a>2.6.5 flush 지시문

`flush` 지시문 명시적 또는 묵시적 지정 "크로스 스레드" 시퀀스 위치는 구현 팀의 모든 스레드 (아래) memory에 지정 된 특정 개체의 일관 된 뷰를 갖도록 하려면 필요 합니다. 이 개체만 참조 하는 식에 대 한 이전 평가 완료 하 고 이후 평가 아직 시작 하지 않은 것을 의미 합니다. 예를 들어, 컴파일러 메모리, 레지스터에서 개체의 값에 복원 해야 및 하드웨어 쓰기 버퍼 메모리를 플러시하고 메모리에서 개체의 값을 다시 로드 해야 할 수 있습니다.

구문의 `flush` 지시문은 다음과 같습니다.

```cpp
#pragma omp flush [(variable-list)]  new-line
```

동기화가 필요한 개체 모두 지정할 수 있습니다 변수인 경우 선택 사항인 이러한 변수를 지정할 수 있습니다 *변수 목록*합니다. 에 대 한 포인터 있으면 합니다 *변수 목록*포인터 자체 플러시, 개체가 아닌 포인터를 참조 합니다.

A `flush` 없이 지시문을 *변수 목록* 자동 저장 기간이 있는 액세스할 수 없는 개체를 제외 하 고 모든 공유 개체를 동기화 합니다. (이 경우 보다 더 많은 오버 헤드가 발생할 수 있습니다는 `flush` 사용 하 여는 *변수 목록*.) `flush` 없이 지시문을 *변수 목록* 다음 지시문 것을 의미 합니다.

- `barrier`
- 항목 및 종료 `critical`
- 항목 및 종료 `ordered`
- 항목 및 종료 `parallel`
- 종료 시 `for`
- 종료 시 `sections`
- 종료 시 `single`
- 항목 및 종료 `parallel for`
- 항목 및 종료 `parallel sections`

지시문 경우 암시 되지 않습니다는 `nowait` 절이 있습니다. 유의 해야 하는 `flush` 지시문 다음에 대 한 암시 되지 않습니다.

- 항목에서 `for`
- 항목 또는 종료 `master`
- 항목에서 `sections`
- 항목에서 `single`

Volatile 한정 형식의 개체의 값에 액세스 하는 참조 처럼 동작을 `flush` 이전 시퀀스 지점에서 해당 개체를 지정 하는 지시문입니다. Volatile 한정 형식의 개체의 값을 수정 하는 참조 처럼 동작을 `flush` 후속 시퀀스 위치에서 해당 개체를 지정 하는 지시문입니다.

때문에 `flush` 지시문에는 해당 구문의 일부로 C 언어 문이 없는, 프로그램에서의 위치에 몇 가지 제한이 있습니다. 정식 문법에 대 한 자세한 내용은 참조 하세요. [부록 C](c-openmp-c-and-cpp-grammar.md)합니다. 아래 예제에서는 이러한 제한 사항을 보여 줍니다.

```cpp
/* ERROR - The flush directive cannot be the immediate
*          substatement of an if statement.
*/
if (x!=0)
   #pragma omp flush (x)
...

/* OK - The flush directive is enclosed in a
*      compound statement
*/
if (x!=0) {
   #pragma omp flush (x)
}
```

에 대 한 제한 된 `flush` 지시문은 다음과 같습니다.

- 에 지정 된 변수는 `flush` 지시문 참조 형식에 없어야 합니다.

### <a name="266-ordered-construct"></a>2.6.6 정렬 된 구조체

구조화 된 블록 다음은 `ordered` 지시문 순차 루프에서 반복 실행할 수는 있는 순서 대로 실행 됩니다. 구문의 `ordered` 지시문은 다음과 같습니다.

```cpp
#pragma omp ordered new-linestructured-block
```

`ordered` 지시문은 동적 범위 내에 있어야 합니다.는 `for` 또는 `parallel for` 생성 합니다. `for` 또는 `parallel for` 는 지시문을 `ordered` 구문을 바인딩합니다 있어야는 `ordered` 에 설명 된 대로 지정 된 절 [2.4.1 섹션](#241-for-construct). 실행 중에 `for` 또는 `parallel for` 사용 하 여 생성는 `ordered` 절 `ordered` 구문 이러한는 실행할 수 있는 순차 루프 실행에서 순서에서 엄격 하 게 실행 됩니다.

에 대 한 제한 된 `ordered` 지시문은 다음과 같습니다.

- 사용 하는 루프의 반복을 `for` 구문이 동일한 순서가 지정 된 지시문을 두 번 이상 실행 해서는 안을 둘 이상 실행 하지 해야 `ordered` 지시문입니다.

## <a name="27-data-environment"></a>2.7 데이터 환경

이 섹션에서는 지시문 및 다음과 같은 병렬 영역을 실행 하는 동안 데이터 환경 제어에 대 한 여러 절을 제공 합니다.

- A [threadprivate](#271-threadprivate-directive) 지시문 파일 범위, 네임 스페이스 범위, 또는 정적 블록 범위 변수를 스레드에 로컬 확인 하기 위해 제공 됩니다.

- 설명 하는 기간 또는 병렬 작업 공유 구문에 대 한 변수 공유 특성을 제어 하는 지시문에 지정 될 수 있는 절 [2.7.2 섹션](#272-data-sharing-attribute-clauses)합니다.

### <a name="271-threadprivate-directive"></a>2.7.1 threadprivate 지시문

`threadprivate` 명명 된 파일 범위, 네임 스페이스 범위, 또는 정적 블록 범위 변수에서 지정 된 지시문을 사용 하면 합니다 *변수 목록* 전용 스레드입니다. *변수 목록* 은 불완전 한 형식 없는 변수의 쉼표로 구분 된 목록입니다. 구문의 `threadprivate` 지시문은 다음과 같습니다.

```cpp
#pragma omp threadprivate(variable-list) new-line
```

각 복사본을 `threadprivate` 변수가 초기화 한 번 해당 복사본에 대 한 첫 번째 참조 하기 전에 프로그램에서 일반적인 방식으로 지정 되지 않은 시점 (즉, 대로 직렬 실행 프로그램의 마스터 복사본을 초기화할 수는). 개체의 명시적 이니셜라이저에서 참조할 경우는 `threadprivate` 변수와 개체의 값은 변수의 복사본에 대 한 첫 번째 참조 하기 전에 수정 될 다음 동작이 지정 되지 않습니다.

모든 개인 변수를 사용 하 여 스레드가 다른 스레드의 복사본 참조 하지 않아야 하는 대로 `threadprivate` 개체입니다. 직렬 지역 및 프로그램의 마스터 지역 중 개체의 마스터 스레드 복사본 참조 됩니다.

첫 번째 병렬 지역을 실행 한 후의 데이터는 `threadprivate` 개체 동적 스레드 메커니즘 경우 비활성화 된만 사용 하며 모든 병렬 영역에 대 한 스레드 수를 그대로 유지 하도록 보장 됩니다.

제한 된 `threadprivate` 지시문은 다음과 같습니다.

- `threadprivate` 지시문 파일 범위 또는 네임 스페이스 범위 변수에 대 한 모든 정의 또는 선언, 외부 나타나야 하며 앞에 변수 중 하나에 대 한 모든 참조 목록에서 어휘와 야 합니다.

- 각 변수에 *변수 목록* 의 `threadprivate` 어휘 지시문 앞에 있는 파일이 나 네임 스페이스 범위에서 변수 선언에 지시문 파일이 나 네임 스페이스 범위에서 참조 해야 합니다.

- `threadprivate` 변수의 범위에 중첩된 된 범위에 없는 고정 블록 범위 변수에 대 한 지시문이 나타나야 합니다. 지시문 목록에 변수 중 하나에 대 한 모든 참조 앞에 어휘 적으로 해야 합니다.

- 각 변수에 *변수 목록* 의 `threadprivate` 어휘 지시문 앞에 있는 동일한 범위에서 변수 선언에 지시문 블록 범위에서 참조 해야 합니다. 변수 선언에는 정적 저장소 클래스 지정자를 사용 해야 합니다.

- 변수에서 지정 된 경우는 `threadprivate` 하나의 변환 단위에서 지시문이 지정 해야 합니다는 `threadprivate` 선언 되는 각 변환 단위에서 지시문입니다.

- `threadprivate` 변수를 제외한 모든 절에 나타나지 않아야 합니다 `copyin`, `copyprivate`, `schedule`를 `num_threads`, 또는 `if` 절.

- 주소는 `threadprivate` 변수 주소 상수를 하지 않습니다.

- `threadprivate` 불완전 한 형식 이거나 참조 형식 변수 없어야 합니다.

- `threadprivate` 비 POD 클래스 형식의 변수에 명시적 이니셜라이저를 사용 하 여 선언 된 액세스 가능 하며 명확한 복사 생성자가 있어야 합니다.

다음 예제에서는 어떻게 이니셜라이저에 표시 되는 변수를 수정 하면 알 수 없는 동작 및 보조 개체 및 복사 생성자를 사용 하 여이 문제를 방지 하는 방법을 보여 줍니다.

```cpp
int x = 1;
T a(x);
const T b_aux(x); /* Capture value of x = 1 */
T b(b_aux);
#pragma omp threadprivate(a, b)

void f(int n) {
   x++;
   #pragma omp parallel for
   /* In each thread:
   * Object a is constructed from x (with value 1 or 2?)
   * Object b is copy-constructed from b_aux
   */
   for (int i=0; i<n; i++) {
      g(a, b); /* Value of a is unspecified. */
   }
}
```

#### <a name="cross-references"></a>상호 참조

- [동적 스레드](3-run-time-library-functions.md#317-omp_set_dynamic-function)
- [OMP_DYNAMIC](4-environment-variables.md#43-omp_dynamic) 환경 변수

### <a name="272-data-sharing-attribute-clauses"></a>2.7.2 데이터 공유 특성 절

여러 지시문 영역의 기간에 대 한 변수 공유 특성을 제어 하는 사용자를 허용 하는 절을 적용 합니다. 공유 특성 절 절은 표시 되는 지시문의 어휘 범위에서 변수에 적용 됩니다. 다음 절 중 일부만 모든 지시문에 허용 됩니다. 지시문을 사용 하 여 특정 지시문에서 사용할 수 있는 절 목록 설명 되어 있습니다.

변수 경우 병렬 표시 되는 작업 공유 생성자가 발견 되 면 변수 공유 특성 절을 지정 하지 않으면 경우 또는 `threadprivate` 지시문에 다음 변수 공유 됩니다. 병렬 영역 동적 범위 내에 선언 된 정적 변수 공유 됩니다. 힙 메모리를 할당 (예를 들어,를 사용 하 여 `malloc()` c에서 또는 C++ 또는 `new` 연산자 C++)를 공유 합니다. 그러나이 메모리에 대 한 포인터 일 수 있습니다 전용 또는 공유 합니다. 병렬 영역 동적 범위 내에 선언 된 자동 저장 기간이 있는 변수는 private입니다.

절의 대부분 동의 *변수 목록* 쉼표로 구분 된 목록이 표시 되는 변수는 인수입니다. 변수가 참조 하는 경우 데이터 공유 특성 절에 템플릿에서 파생 된 형식 및 다른 프로그램에서 해당 변수 참조가, 동작이 정의 되지 않습니다.

지시문 절 내에 나타나는 모든 변수 표시 되어야 합니다. 필요에 따라 절을 반복 될 수 있습니다 하지만 변수가 없기 변수 둘 다 지정할 수 있습니다 한다는 점을 제외 하면 둘 이상의 절에 지정할 수 있습니다는 `firstprivate` 및 `lastprivate` 절.

다음 섹션에서는 데이터 공유 특성 절을 설명합니다.

- [private](#2721-private)
- [firstprivate](#2722-firstprivate)
- [lastprivate](#2723-lastprivate)
- [shared](#2724-shared)
- [default](#2725-default)
- [reduction](#2726-reduction)
- [copyin](#2727-copyin)
- [copyprivate](#2728-copyprivate)

#### <a name="2721-private"></a>2.7.2.1 private

`private` 절은 팀에서 각 스레드에 private 일 변수 목록에서 변수를 선언 합니다. 구문의 `private` 절은 다음과 같습니다.

```cpp
private(variable-list)
```

에 지정 된 변수 동작을 `private` 절은 다음과 같습니다. 구문에 대 한 자동 저장 기간이 있는 새 개체를 할당 됩니다. 크기 및 새 개체의 맞춤 변수 유형에 의해 결정 됩니다. 이 할당이 팀의 각 스레드에 대해 한 번 발생 하 고 기본 생성자가 호출 하 고 필요한 경우 클래스 개체에 대 한 그렇지 않은 경우 초기 값 확정적이 지 않습니다.  변수에서 참조 하는 원래 개체 구문에 진입할 때 비활성화 상태 값, 해당 구문의 동적 범위 내에서 수정 해서는 안 및 구문에서 종료 시 비활성화 상태 값입니다.

지시문 구문의 어휘 범위 내에서 변수는 스레드에 의해 할당 된 새 개인 개체를 참조 합니다.

제한 된 `private` 절은 다음과 같습니다.

- 에 지정 된 클래스 형식의 변수에 `private` 절에는 액세스 가능 하며 명확한 기본 생성자가 있어야 합니다.

- 에 지정 된 변수를 `private` 절이 없어야 합니다는 `const`-유형과 클래스에 없는 경우 형식 정규화를 `mutable` 멤버입니다.

- 에 지정 된 변수는 `private` 불완전 한 형식 이거나 참조 형식 절이 없어야 합니다.

- 에 표시 되는 변수를 `reduction` 절을 `parallel` 지시문에 지정할 수는 `private` 병렬 구문에 바인딩하는 작업 공유 지시문의 절.

#### <a name="2722-firstprivate"></a>2.7.2.2 firstprivate

합니다 `firstprivate` 절에서 제공 하는 기능의 상위 집합을 제공 합니다 `private` 절. 구문의 `firstprivate` 절은 다음과 같습니다.

```cpp
firstprivate(variable-list)
```

에 지정 된 변수 *변수 목록* 있어야 `private` 절의 의미 체계를에 설명 된 대로 [2.7.2.1 섹션](#2721-private)합니다. 초기화 또는 생성 구문 스레드의 실행 전에 스레드당 한 번 수행 하는 것 처럼 발생 합니다. 에 대 한는 `firstprivate` 병렬 구문에서 절 새 개인 개체의 초기 값은이 발생 하는 스레드에 대 한 병렬 구문 직전 존재 하는 원래 개체의 값입니다. 에 대 한는 `firstprivate` 절 작업 공유 구문에서 작업 공유 생성자를 실행 하는 각 스레드에 대 한 새 개인 개체의 초기 값은 동일한 스레드 발생할은 특정 시점 이전에 존재 하는 원래 개체의 값을 작업 공유 구문입니다. 또한 C++ 개체의 경우 각 스레드에 대 한 새 개인 개체는 원래 개체에서 복사 생성 합니다.

제한 된 `firstprivate` 절은 다음과 같습니다.

- 에 지정 된 변수는 `firstprivate` 불완전 한 형식 이거나 참조 형식 절이 없어야 합니다.

- 으로 지정 된 클래스 형식의 변수에 `firstprivate` 는 액세스 가능 하며 명확한 복사 생성자가 있어야 합니다.

- 병렬 영역 내부에서는 개인 기능은에 나타나는 변수를 `reduction` 절을 `parallel` 지시문에 지정할 수는 `firstprivate` 병렬 구문에 바인딩하는 작업 공유 지시문의 절.

#### <a name="2723-lastprivate"></a>2.7.2.3 lastprivate

합니다 `lastprivate` 절에서 제공 하는 기능의 상위 집합을 제공 합니다 `private` 절. 구문의 `lastprivate` 절은 다음과 같습니다.

```cpp
lastprivate(variable-list)
```

에 지정 된 변수를 *변수 목록* 가 `private` 절 의미 체계. 경우는 `lastprivate` 에서 작업 공유 구문에 각 값을 식별 하는 지시문의 절이 나타납니다 `lastprivate` 변수가 연결된 루프 또는 어휘 적으로 마지막 섹션 지시문을 순차적으로 마지막 반복에서 할당 되는 변수의 원본 개체입니다. 에 값의 마지막 반복 하 여 할당 된 변수를 `for` 또는 `parallel for`, 또는 어휘 적으로 마지막 섹션에서는 `sections` 또는 `parallel sections` 지시문 구문 비활성화 상태 값 후. 할당 되지 않은 하위 개체는 구문이 후 비활성화 상태 값을 수도 있습니다.

제한 된 `lastprivate` 절은 다음과 같습니다.

- 에 대 한 모든 제한 `private` 적용 합니다.

- 으로 지정 된 클래스 형식의 변수에 `lastprivate` 액세스 가능 하며 명확한 복사 할당 연산자가 있어야 합니다.

- 병렬 영역 내부에서는 개인 기능은에 나타나는 변수를 `reduction` 절을 `parallel` 지시문에 지정할 수는 `lastprivate` 병렬 구문에 바인딩하는 작업 공유 지시문의 절.

#### <a name="2724-shared"></a>2.7.2.4 공유됨

이 절에 표시 되는 변수를 공유 합니다 *변수 목록* 팀의 모든 스레드 간에 합니다. 팀 내에서 모든 스레드는 동일한 저장소 영역에 대 한 액세스 `shared` 변수입니다.

구문의 `shared` 절은 다음과 같습니다.

```cpp
shared(variable-list)
```

#### <a name="2725-default"></a>2.7.2.5 기본값

`default` 절 변수의 데이터 공유 특성에 영향을 줄 수 있습니다. 구문의 `default` 절은 다음과 같습니다.

```cpp
default(shared | none)
```

지정 `default(shared)` 에서 현재 표시 된 각 변수를 명시적으로 나열 하는 것과 같습니다는 `shared` 절 경우가 `threadprivate` 또는 `const`-정규화 된 합니다. 명시적인 없을 경우 `default` 절을 기본 동작은 동일 경우 `default(shared)` 지정 되었습니다.

지정 `default(none)` 병렬 구문 어휘 범위에서 변수를 참조할 때마다 충족 해야 다음 중 하나 이상이 필요 합니다.

- 변수 참조를 포함 하는 구문의 데이터 공유 특성 절에 명시적으로 나열 됩니다.

- 변수는 병렬 구문 내에서 선언 됩니다.

- 변수가 `threadprivate`합니다.

- 변수가 한 `const`-형식을 정규화 합니다.

- 변수는에 대 한 루프 제어 변수를 `for` 바로 뒤에 오는 루프를 `for` 또는 `parallel for` 지시문 및 변수 참조는 루프 내에서 표시 됩니다.

변수를 지정 하는 `firstprivate`, `lastprivate`, 또는 `reduction` 는 괄호로 묶인된 지시문의 절 변수에 대 한 암시적 참조가 바깥쪽 컨텍스트에서 발생 합니다. 이러한 암시적 참조 위에 나열 된 요구 사항이 적용 됩니다.

단일 `default` 절에서 지정할 수는 `parallel` 지시문입니다.

변수의 기본 데이터 공유 특성을 사용 하 여 재정의할 수 있습니다는 `private`, `firstprivate`, `lastprivate`, `reduction`, 및 `shared` 다음 예제에서 볼 수 있듯이 절:

```cpp
#pragma  omp  parallel  for  default(shared)  firstprivate(i)\
   private(x)  private(r)  lastprivate(i)
```

#### <a name="2726-reduction"></a>2.7.2.6 reduction

이 절에 표시 되는 스칼라 변수에서 감소를 수행 *변수 목록*, 연산자로 *op*합니다. 구문의 `reduction` 절은 다음과 같습니다.

`reduction(` *op* `:` *variable-list* `)`

감소는 다음 형식 중 하나를 사용 하 여 문에 대 한 일반적으로 지정 됩니다.

- *x* `=` *x* *op* *expr*
- *x* *binop* `=` *expr*
- *x* `=` *expr* *op* *x* (빼기) 제외
- *x* `++`
- `++` *x*
- *x* `--`
- `--` *x*

다음은 각 문자에 대한 설명입니다.

*x*<br/>
목록에 지정 된 환산 변수 중 하나입니다.

*variable-list*<br/>
스칼라 감소가 변수의 쉼표로 구분 된 목록입니다.

*expr*<br/>
참조 하지 않는 스칼라 형식이 있는 식을 *x*합니다.

*op*<br/>
Not 오버 로드 된 연산자를 하나만 `+`, `*`, `-`, `&`를 `^`를 `|`, `&&`, 또는 `||`합니다.

*binop*<br/>
Not 오버 로드 된 연산자를 하나만 `+`, `*`를 `-`를 `&`를 `^`, 또는 `|`합니다.

다음은의 예로 `reduction` 절:

```cpp
#pragma omp parallel for reduction(+: a, y) reduction(||: am)
for (i=0; i<n; i++) {
   a += b[i];
   y = sum(y, c[i]);
   am = am || b[i] == c[i];
}
```

예제와 같이 연산자는 함수 호출 내부 숨겨질 수 있습니다. 사용자는 연산자에 지정 된 주의 해야 합니다.는 `reduction` 절 감소 작업과 일치 합니다.

하지만의 오른쪽 피연산자는 `||` 연산자이 예제에 대 한 부작용이 없으며, 허용 하 고 있지만 주의 해 서 사용 해야 합니다. 이 컨텍스트에서 루프의 순차 실행 중에 발생 되지 않도록 보장 하는 부작용 병렬 실행 하는 동안 발생할 수 있습니다. 이러한 차이 반복의 실행 순서는 확정적이 지 없기 때문에 발생할 수 있습니다.

연산자는 감소에 대 한 컴파일러에서 사용 된 모든 개인 변수의 초기 값을 확인 하 고 종료 연산자를 확인 하려면 사용 됩니다. 연산자를 명시적으로 지정 하면 감소 문을 구문 어휘 범위 외부에 있을 수 있습니다. 임의 개수의 `reduction` 지시문에 절을 지정할 수는 있지만 변수 하나만에 나타날 수 있습니다 `reduction` 지시문 절.

각 변수의 개인 복사본 *변수 목록* 만들어지면 각 스레드에 대해 하나 처럼는 `private` 절을 사용한 합니다. 개인 복사본 연산자에 따라 초기화 됩니다 (다음 표 참조).

영역의 끝을 `reduction` 절이 지정 되어, 원래 개체의 각 지정한 연산자를 사용 하 여 개인 복사본의 최종 값을 사용 하 여 원래 값을 조합한 결과 반영 하도록 업데이트 됩니다. 감소 연산자 (빼기), 제외 하 고 모든 연관 되며 컴파일러 계산 최종 값을 다시 연결 자유롭게 수 있습니다. (빼기 감소의 부분 결과 최종 값은 폼에 추가 됩니다.)

첫 번째 스레드가 포함 하는 절에 도달 하 고 감소 계산이 완료 될 때까지 유지 하도록 원래 개체의 값이 비활성화 됩니다.  일반적으로 계산; 구문의 끝에 완료 됩니다. 그러나 경우 합니다 `reduction` 절을 사용 하는 구문에서 `nowait` 는 적용 원래 개체의 값까지 결정 되지 않은 모든 스레드는 가완료되었는지에장벽동기화를수행한`reduction`절.

다음 표에서 사용할 수 있는 연산자 및 해당 정식 초기화 값을 나열 합니다. 실제 초기화 값을는 환산 변수 데이터 형식과 일치 됩니다.

|연산자|초기화|
|--------------|--------------------|
|`+`|0|
|`*`|1|
|`-`|0|
|`&`|~0|
|`|`|0|
|`^`|0|
|`&&`|1|
|`||`|0|

제한 된 `reduction` 절은 다음과 같습니다.

- 형식의 변수는 `reduction` 포인터 형식과 참조 형식은 허용 되지 않습니다 한다는 절 reduction 연산자에 대해 유효 해야 합니다.

- 에 지정 된 변수를 `reduction` 절이 아니어야 `const`-정규화 합니다.

- 병렬 영역 내부에서는 개인 기능은에 나타나는 변수를 `reduction` 절을 `parallel` 지시문에 지정할 수는 `reduction` 병렬 구문에 바인딩하는 작업 공유 지시문의 절.

   ```cpp
   #pragma omp parallel private(y)
   { /* ERROR - private variable y cannot be specified
                in a reduction clause */
      #pragma omp for reduction(+: y)
      for (i=0; i<n; i++)
         y += b[i];
   }

   /* ERROR - variable x cannot be specified in both
              a shared and a reduction clause */
   #pragma omp parallel for shared(x) reduction(+: x)
   ```

#### <a name="2727-copyin"></a>2.7.2.7 copyin

합니다 `copyin` 절에 동일한 값을 할당 하는 메커니즘을 제공 `threadprivate` 병렬 영역을 실행 하는 팀에서 각 스레드에 대 한 변수입니다. 에 지정 된 각 변수에 대해는 `copyin` 병렬 영역 부분에 스레드 전용 복사본에 할당 하 여 처럼 절, 팀의 마스터 스레드에의 변수 값 복사 됩니다. 구문의 `copyin` 절은 다음과 같습니다.

```cpp

copyin(
variable-list
)
```

제한 된 `copyin` 절은 다음과 같습니다.

- 에 지정 된 변수는 `copyin` 절에는 액세스 가능 하며 명확한 복사 할당 연산자는 있어야 합니다.

- 에 지정 된 변수를 `copyin` 절은 되어야 합니다는 `threadprivate` 변수입니다.

#### <a name="2728-copyprivate"></a>2.7.2.8 copyprivate

`copyprivate` 절 개인 변수를 사용 하 여 다른 구성원에 게 팀의 한 멤버에서 값을 브로드캐스트 메커니즘을 제공 합니다. 경우에 공유 변수를 제공 (예를 들어, 각 수준에서 서로 다른 변수를 요구 하는 재귀)에서 어려운 값에 대 한 공유 변수를 사용 하는 대신 것입니다. 합니다 `copyprivate` 절 에서만 나타날 수 있습니다는 `single` 지시문입니다.

구문의 `copyprivate` 절은 다음과 같습니다.

```cpp

copyprivate(
variable-list
)
```

효과 `copyprivate` 해당 변수 목록에서 변수에서 절을 연관 구조화 된 블록으로 실행 된 후 발생는 `single` 생성, 끝에 구문 장벽에 남아 있는 팀의 다른 스레드가 전에. 그런 다음, 각 변수에 대 한 팀의 다른 모든 스레드는 *변수 목록*, 해당 변수가 정의한 (처럼 할당) 해당 값을 사용 하 여 구조적 구문을 실행 하는 스레드에서 변수 블록입니다.

에 대 한 제한 된 `copyprivate` 절은 다음과 같습니다.

- 에 지정 된 변수를 `copyprivate` 절에 나타나지 않아야를 `private` 하거나 `firstprivate` 동일한 절 `single` 지시문입니다.

- 경우는 `single` 지시문에 `copyprivate` 절 동적 병렬 영역 범위에서 발생 하면에 지정 된 모든 변수는 `copyprivate` 절은 바깥쪽 컨텍스트에서 private 이어야 합니다.

- 에 지정 된 변수는 `copyprivate` 절에는 액세스할 수 있는 명확한 복사 할당 연산자는 있어야 합니다.

## <a name="28-directive-binding"></a>2.8 지시문 바인딩

지시문의 동적으로 바인딩하는 다음 규칙을 준수 해야 합니다.

- 합니다 `for`, `sections`를 `single`, `master`, 및 `barrier` 지시문 바인딩할 동적으로 바깥쪽 `parallel`의 값이 있는 경우, `if` 절에 나타날 수 있는 지시문입니다. 병렬 영역 없음 현재 실행 중인 경우 지시문은 마스터 스레드만 이루어진 팀에서 실행 됩니다.

- 합니다 `ordered` 지시문에 바인딩한 동적으로 바깥쪽 `for`합니다.

- 합니다 `atomic` 지시문에 대하여 배타적 액세스를 적용 `atomic` 모든 스레드를 통해 현재 팀 뿐 아니라 지시문입니다.

- 합니다 `critical` 지시문에 대하여 배타적 액세스를 적용 `critical` 모든 스레드를 통해 현재 팀 뿐 아니라 지시문입니다.

- 지시문 수를 가장 가까운 바깥쪽 모든 지시문에 동적으로 바인딩하지 않도록 바깥쪽 `parallel`합니다.

## <a name="29-directive-nesting"></a>2.9 지시문 중첩

지시문의 동적 중첩은 다음 규칙을 준수 해야 합니다.

- A `parallel` 동적으로 안에 다른 지시문 `parallel` 논리적으로 구성 된 현재 스레드의 새 팀을 병렬 처리를 중첩 된 경우가 아니면 사용 하도록 설정할지를 설정 합니다.

- `for`를 `sections`, 및 `single` 동일 하 게 바인딩하는 지시문 `parallel` 서로의 내부에 중첩 될 수 없습니다.

- `critical` 동일한 이름의 지시문 서로의 내부에 중첩 될 수 없습니다. 이 제한은 교착 상태를 방지 하기에 충분 하지는 참고 합니다.

- `for`를 `sections`, 및 `single` 지시문의 동적 범위에서 허용 되지 않습니다 `critical`를 `ordered`, 및 `master` 지시문은 동일 하 게 바인딩할 경우 지역 `parallel` 지역으로 합니다.

- `barrier` 지시문의 동적 범위에서 허용 되지 않습니다 `for`, `ordered`를 `sections`를 `single`를 `master`, 및 `critical` 지시문은 동일 하 게 바인딩할 경우 지역 `parallel` 지역으로 합니다.

- `master` 지시문의 동적 범위에서 허용 되지 않습니다 `for`, `sections`, 및 `single` 지시문 경우 합니다 `master` 지시문 동일한 바인딩 `parallel` 작업 공유 지시문으로 합니다.

- `ordered` 지시문의 동적 범위에서 허용 되지 않습니다 `critical` 지시문은 동일 하 게 바인딩할 경우 지역 `parallel` 지역으로 합니다.

- 병렬 영역 내부에서 동적으로 실행 하는 경우 허용 되는 모든 지시문 병렬 영역 외부에서 실행 하는 경우에 허용 됩니다. 를 실행 하면 동적으로 사용자 지정 병렬 지역 외부 지시문 마스터 스레드만 이루어진 팀에서 실행 됩니다.
