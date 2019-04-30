---
title: SIMD 확장
ms.date: 03/20/2019
helpviewer_keywords:
- SIMD
- OpenMP in Visual C++, new features
- explicit parallelization, new features
ms.openlocfilehash: 52402aa553c6d68d3073aba26ecac7b784522ee9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62363273"
---
# <a name="simd-extension"></a>SIMD 확장

하지만 Visual C++ Visual Studio 2019 이제 SIMD 기능을 제공 OpenMP 2.0 표준에는 현재 지원 합니다.

> [!NOTE]
> SIMD를 사용 하려면 사용 하 여 컴파일하는 `-openmp:experimental` 사용 하는 경우 사용할 수 없는 추가 OpenMP 기능을 사용 하도록 설정 하는 스위치를 `-openmp` 전환 합니다.
>
> 합니다 `-openmp:experimental` 전환 되기 `-openmp`, 즉 모든 OpenMP 2.0 기능을 사용 한다는 점에서 포함 됩니다.

자세한 내용은 [SIMD 확장 C++ Visual Studio에서 OpenMP](https://devblogs.microsoft.com/cppblog/simd-extension-to-c-openmp-in-visual-studio/)합니다.

## <a name="openmp-simd-in-visual-c"></a>시각적 개체에 대 한 OpenMP SIMDC++

OpenMP SIMD를 벡터에 게 친숙 한 루프를 수행 하는 대상 표준 OpenMP 4.0에 도입 합니다. 사용 하 여는 `simd` 루프 전에 지시문, 컴파일러 벡터 종속성을 무시할 루프와 벡터 친화적인 최대한를 동시에 실행 하는 여러 개의 루프 반복을 할 사용자의 의도 존중 합니다.

```c
    #pragma omp simd
    for (i = 0; i < count; i++)
    {
        a[i] = a[i-1] + 1;
        b[i] = *c + 1;
        bar(i);
    }
```

Visual C++ 유사한-OpenMP 루프 pragma와 같은 제공 `#pragma vector` 하 고 `#pragma ivdep`이지만 OpenMP SIMD를 사용 하 여 컴파일러 가능 자세한 같은:

- 항상 있는 벡터 종속성을 무시할 수 있습니다.
- `/fp:fast` 루프 내에서 사용 됩니다.
- 외부 루프 함수 호출을 사용 하 여 루프와 벡터 친화적입니다.
- 중첩 된 루프 하나의 루프에 병합 하 고 벡터 친화적인 수행 수 있습니다.
- 사용 하 여 하이브리드 가속 `#pragma omp for simd` 정교 하지 않은 다중 스레딩 및 세분화 된 벡터를 사용 하도록 설정 합니다.  

벡터에 게 친숙 한 루프에 대 한 컴파일러 지원 벡터 log 스위치를 사용 하지 않는 한 자동 됩니다.

```cmd
    cl -O2 -openmp:experimental -Qvec-report:2 mycode.cpp
```

```Output
    mycode.cpp(84) : info C5002: Omp simd loop not vectorized due to reason '1200'
    mycode.cpp(90) : info C5002: Omp simd loop not vectorized due to reason '1200'
    mycode.cpp(96) : info C5001: Omp simd loop vectorized
```

비-벡터-친숙 한 루프에 대 한 컴파일러가 각 메시지:

```cmd
    cl -O2 -openmp:experimental mycode.cpp
```

```Output
    mycode.cpp(84) : info C5002: Omp simd loop not vectorized due to reason '1200'
    mycode.cpp(90) : info C5002: Omp simd loop not vectorized due to reason '1200'
```

### <a name="clauses"></a>절

SIMD OpenMP 지시문 벡터 지원을 강화 하기 위해 다음 절을 사용할 수도 있습니다.

|지시문|설명|
|---|---|
|`simdlen(length)`|벡터 레인의 수를 지정 합니다.|
|`safelen(length)`|벡터 종속성 거리를 지정 합니다.|
|`linear(list[ : linear-step]`)|루프 유도 변수에서 배열 구독 선형 매핑|
|`aligned(list[ : alignment])`|데이터의 맞춤입니다.|
|`private(list)`|데이터 개인화를 지정 합니다.|
|`lastprivate(list)`|마지막 반복에서 최종 값을 사용 하 여 데이터 개인화를 지정 합니다.|
|`reduction(reduction-identifier:list)`|사용자 지정된 감소 작업을 지정 합니다.|
|`collapse(n)`|병합 루프 중첩 합니다.|

> [!NOTE]
> 비 효과적인 SIMD 절 구문 분석 하 고 경고를 사용 하 여 컴파일러에서 무시 됩니다.
>
> 예를 들어, 사용 하 여 다음 코드 문제의 경고:
>
> ```c
>    #pragma omp simd simdlen(8)
>    for (i = 0; i < count; i++)
>    {
>        a[i] = a[i-1] + 1;
>        b[i] = *c + 1;
>        bar(i);
>    }
> ```
>
> ```Output
>    warning C4849: OpenMP 'simdlen' clause ignored in 'simd' directive
> ```

### <a name="example"></a>예제
  
SIMD OpenMP 지시문은 사용자 지정 컴파일러 확인 루프 벡터-식별 하는 방법을 제공 합니다. SIMD OpenMP 지시문을 사용 하는 루프를 추가 하 여 사용자가 여러 개의 루프 반복을 동시에 실행 하 려 합니다.

예를 들어 다음 루프 SIMD OpenMP 지시문을 사용 하 여 주석 처리 됩니다. 이전 버전과 종속성 [i]에서 [i-1]에 있지만 컴파일러는 하나의 벡터 명령으로 첫 번째 문의 연속 반복 팩을 실행 하는 허용 됩니다 SIMD 지시문 때문 이므로 없는 완벽 한 병렬 루프 반복 간에 동시에 해당 합니다.

```c
    #pragma omp simd
    for (i = 0; i < count; i++)
    {
        a[i] = a[i-1] + 1;
        b[i] = *c + 1;
        bar(i);
    }
```

따라서 다음 변형 된 벡터 루프의 형식은 **법적** 컴파일러에서는 원래 각 루프 반복의 순차적 동작을 유지 하므로 합니다. 즉, `a[i]` 이후에 실행 됩니다 `a[-1]`를 `b[i]` 뒤 `a[i]` 를 호출 `bar` 마지막으로 발생 합니다.

```c
    for (i = 0; i < count; i+=4)
    {
        a[i:i+3] = a[i-1:i+2] + 1;
        b[i:i+3] = *c + 1;
        bar(i);
        bar(i+1);
        bar(i+2);
        bar(i+3);
    }
```

있기 **유효 하지 않은** 메모리 참조 이동할 `*c` 사용 하 여 별칭 수 하는 경우 루프 밖으로 `a[i]` 또는 `b[i]`합니다. 것도 하지 법적 순차 종속성을 중단 하는 경우 원래 1 회 반복 내의 문이 다시 정렬 합니다. 예를 들어, 다음 변환 된 루프는 법적 되지 않습니다.

```c
    c = b;
    t = *c;
    for (i = 0; i < count; i+=4)
    {
        a[i:i+3] = a[i-1:i+2] + 1;
        bar(i);            // illegal to reorder if bar[i] depends on b[i]
        b[i:i+3] = t + 1;  // illegal to move *c out of the loop
        bar(i+1);
        bar(i+2);
        bar(i+3);
    }
```

## <a name="see-also"></a>참고자료

[/openmp(OpenMP 2.0 지원 사용)](../../build/reference/openmp-enable-openmp-2-0-support.md)<br/>
