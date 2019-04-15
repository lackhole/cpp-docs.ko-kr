---
title: /fp (부동 소수점 동작 지정)
ms.date: 11/09/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.floatingPointModel
- VC.Project.VCCLWCECompilerTool.FloatingPointExceptions
- /fp
- VC.Project.VCCLWCECompilerTool.floatingPointModel
- VC.Project.VCCLCompilerTool.FloatingPointExceptions
helpviewer_keywords:
- -fp compiler option [C++]
- /fp compiler option [C++]
ms.assetid: 10469d6b-e68b-4268-8075-d073f4f5d57e
ms.openlocfilehash: 25b228c16f534ca227d50bfdf632fdacb5703cd9
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565440"
---
# <a name="fp-specify-floating-point-behavior"></a>/fp (부동 소수점 동작 지정)

컴파일러는 부동 소수점 식, 최적화 및 예외를 처리 하는 방법을 지정 합니다. 합니다 **/fp** 옵션 생성된 된 코드의 부동 소수점 환경을 변경 하 고 반올림 모드, 예외 마스크, subnormal 동작을 허용 하는지 여부 및 현재, 정확한 부동 소수점 상태 검사의 반환 여부를 지정 합니다. 결과입니다. 컴파일러에서 소스 작업 및 식 순서를 유지 관리 하 고 NaN 전파에 대 한 표준을 준수 하는 코드를 생성 하는 여부 또는 순서를 변경 또는 작업을 결합 및 단순화를 사용할 수 있는 보다 효율적인 코드 대신 생성 하는 경우 제어 표준에서 허용 되지 않는-변환 합니다.

## <a name="syntax"></a>구문

> **/fp:**[**precise** | **strict** | **fast** | **except**[**-**]]

### <a name="arguments"></a>인수

#### <a name="precise"></a>정확한

컴파일러는 기본적으로 다음을 사용 합니다. `/fp:precise` 동작 합니다.

아래 `/fp:precise` 컴파일러 소스 식은 순서 지정 및 부동 소수점 코드의 속성을 생성 하 고 대상 컴퓨터에 대 한 개체 코드를 최적화 하는 경우 반올림을 유지 합니다. 컴파일러가 식 평가 중 네 개의 특정 지점에서 소스 코드 정밀도로 반올림 합니다: 할당에 있는 포인터로 변환, 부동 소수점 값 및 부동 소수점 인수는 함수 호출에 전달 될 때 함수 호출에서 반환 됩니다. 컴퓨터 전체 자릿수에서 중간 계산을 수행할 수 있습니다. 대입문 명시적으로 중간 계산을 반올림 데 사용할 수 있습니다.

컴파일러가 변환은 항상 비트 동일한 결과 생성 하지 않는 한 다시 배포 등의 부동 소수점 식에 대 수 변환을 수행 하지 않습니다.
특수 값 (NaN, + infinity,-infinity,-0.0)를 포함 하는 식 IEEE-754 사양에 따라 처리 됩니다. 예를 들어 `x != x` 로 평가 **true** x가 NaN입니다. 부동 소수점 *축약*, 아래에서 부동 소수점 작업을 결합 하는 컴퓨터 명령이 생성 될 수 있습니다, `/fp:precise`합니다.

컴파일러 실행 되도록 코드를 생성 합니다 [기본 부동 소수점 환경을](#the-default-floating-point-environment) 하며 부동 소수점 환경을 액세스 또는 런타임에 수정 하지는 것으로 가정 합니다. 즉,는 코드는 부동 소수점 예외를 마스크 해제, 읽기 또는 부동 소수점 상태 레지스터를 작성 하거나 변경 하지 반올림 모드 가정 합니다.

작업 및 부동 소수점 문의 식 순서 부동 소수점 코드를 받지 않습니다 하는 경우 (중요 하지 않은 경우에 예를 들어 있는지 여부를 `a * b + a * c` 로 계산 됩니다 `(b + c) * a` 또는 `2 * a` 으로 `a + a`)를 고려 합니다 [/fp:fast](#fast) 옵션을 보다 빠르고 보다 효율적인 코드를 생성할 수 있습니다. 코드 모두 작업 및 식 순서에 따라 및 액세스 또는 변경 (예: 반올림 모드를 변경 하거나 부동 소수점 예외를 트래핑 하) 부동 소수점 환경을 경우 사용 하 여 [/fp: strict](#strict)합니다.

#### <a name="strict"></a>strict

`/fp:strict` 동작이 비슷합니다 `/fp:precise`, 즉, 컴파일러가 소스 순서를 유지 및 대상 컴퓨터에 대 한 코드를 개체 및 특수 한 값을 처리 하는 경우 표준 준수 속성 부동 소수점 코드를 생성 하 고 최적화 하는 경우 반올림 합니다. 또한 프로그램 있습니다 안전 하 게 액세스 하거나 런타임에 부동 소수점 환경을 수정 합니다.

아래 `/fp:strict`, 컴파일러는 프로그램을 안전 하 게 부동 소수점 예외를 마스크 해제, 읽기 또는 쓰기 부동 소수점 상태 레지스터 또는 반올림 모드를 변경할 수 있도록 코드를 생성 합니다. 식 평가 중 네 개의 특정 지점에서 원본 코드의 전체 자릿수 반올림 합니다: 할당에 있는 포인터로 변환, 부동 소수점 값 및 부동 소수점 인수는 함수 호출에 전달 될 때 함수 호출에서 반환 됩니다. 컴퓨터 전체 자릿수에서 중간 계산을 수행할 수 있습니다. 대입문 명시적으로 중간 계산을 반올림 데 사용할 수 있습니다. 컴파일러가 변환은 항상 비트 동일한 결과 생성 하지 않는 한 다시 배포 등의 부동 소수점 식에 대 수 변환을 수행 하지 않습니다. 특수 값 (NaN, + infinity,-infinity,-0.0)를 포함 하는 식 IEEE-754 사양에 따라 처리 됩니다. 예를 들어 `x != x` 로 평가 **true** x가 NaN입니다. 부동 소수점 축약에서 생성 되지 않습니다 `/fp:strict`합니다.

`/fp:strict` 계산 보다 비용이 더 높은 `/fp:precise` 하므로 컴파일러 예외를 트래핑 하 고 액세스 하거나 런타임에 부동 소수점 환경을 수정 프로그램에 추가 지침을 삽입 해야 합니다. 코드는이 기능을 사용 하지 않습니다 하지만 소스 코드 순서 지정 및 반올림 필요, 특수 값을 사용 하는 경우 사용 하 여 `/fp:precise`입니다. 그렇지 않은 경우 사용 하는 것이 좋습니다 `/fp:fast`, 빠르고 작은 코드를 생성할 수 있습니다.

#### <a name="fast"></a>빠른

`/fp:fast` 옵션을 사용 하면 컴파일러를 다시 정렬, 결합, 아니면 속도 및 공간에 대 한 부동 소수점 코드를 최적화 하는 부동 소수점 작업을 간소화 합니다. 컴파일러는 대입문에서 반올림을 생략할 수, 대입문 또는 함수 호출 합니다. 작업 순서를 변경 또는 이러한 변형을 만들 띄는 다른 반올림 동작을 수행 하는 경우에 연관 및 분배 법칙을 사용 하 여 예를 들어, 대 수 변형을 수행할 수 있습니다. 이러한 향상 된 최적화 때문에 일부 부동 소수점 계산의 결과에서 다른 생성 된 달라질 `/fp` 옵션입니다. 특수 값 (NaN, + infinity,-infinity,-0.0) 전파할 수 없습니다 또는 IEEE-754 표준에 따라 엄격 하 게 동작 합니다. 부동 소수점 축약에서 생성 될 수 있습니다 `/fp:fast`합니다. 컴파일러에서 기본 아키텍처를 기준으로 여전히 바인딩되어 `/fp:fast`, 추가 최적화를 사용 하 여 사용할 수는 [/arch](arch-minimum-cpu-architecture.md) 옵션입니다.

아래 `/fp:fast`, 컴파일러는 기본 부동 소수점 환경에서 실행 되도록 코드를 생성 하 고 부동 소수점 환경을 액세스할 수 없거나 런타임에 수정 가정 합니다. 즉,는 코드는 부동 소수점 예외를 마스크 해제, 읽기 또는 부동 소수점 상태 레지스터를 작성 하거나 변경 하지 반올림 모드 가정 합니다.

`/fp:fast` 순서 지정 및 부동 소수점 식의 반올림 엄격 하 게 소스 코드가 필요 없는 및 NaN 같은 특수 한 값을 처리 하기 위한 표준 규칙에 의존 하지 마십시오는 프로그램에 대 한 것입니다. 부동 소수점 코드 순서 지정 및 반올림, 소스 코드를 유지 해야 하거나 특수 한 값을 사용 하 여의 표준 동작에 의존 하는 경우 [/fp: 정확한](#precise)합니다. 코드에 액세스 또는 부동 소수점 반올림 모드를 변경할 환경을 수정 하는 경우 부동 소수점 예외를 마스크 해제 또는 부동 소수점 상태를 확인, 사용 하 여 [/fp: strict](#strict)합니다.

#### <a name="except"></a>except

`/fp:except` 옵션 마스킹되 지 않은 부동 소수점 예외는 발생 하는, 정확한 지점에서 발생 하 고 추가 부동 소수점 예외가 발생 하는 코드를 생성 합니다. 기본적으로 `/fp:strict` 옵션을 사용 하면 `/fp:except`, 및 `/fp:precise` 하지 않습니다. 합니다 `/fp:except` 옵션이 호환 되지 않습니다. `/fp:fast`합니다. 가 귀하의 옵션을 명시적으로 비활성화할 수 있습니다 `/fp:except-`합니다.

`/fp:except` 부동 소수점 예외를 자체적으로 사용 되지 않습니다 이지만 부동 소수점 예외를 사용 하도록 설정 하려면 프로그램에 필요 합니다. 참조 [_controlfp](../../c-runtime-library/reference/control87-controlfp-control87-2.md) 부동 소수점 예외를 사용 하는 방법에 대 한 정보에 대 한 합니다.

## <a name="remarks"></a>설명

여러 `/fp` 동일한 컴파일러 명령줄 옵션을 지정할 수 있습니다. 중 하나만 `/fp:strict`하십시오 `/fp:fast`, 및 `/fp:precise` 옵션은 한 번에 적용할 수 있습니다. 명령줄에서 다음이 옵션 중 하나 이상 지정은 뒷부분에 나오는 옵션이 우선 하 고 컴파일러 경고를 생성 합니다. 합니다 `/fp:strict` 하 고 `/fp:except` 옵션이 호환 되지 않습니다. `/clr`합니다.

합니다 [/Za](za-ze-disable-language-extensions.md) 옵션 (ANSI 호환성)와 호환 되지 않습니다. `/fp`합니다.

### <a name="using-compiler-directives-to-control-floating-point-behavior"></a>컴파일러 지시문을 사용하여 부동 소수점 동작 제어

컴파일러 명령줄에 지정 된 부동 소수점 동작을 재정의 하려면 세 가지 pragma 지시문을 제공 합니다. [float_control](../../preprocessor/float-control.md)를 [fenv_access](../../preprocessor/fenv-access.md), 및 [fp_contract](../../preprocessor/fp-contract.md). 수준 함수는 함수 내에 있지 부동 소수점 동작을 제어 하려면 이러한 지시문을 사용할 수 있습니다. 이러한 지시문에 직접 해당 하지 않는 참고는 `/fp` 옵션입니다. 이 테이블에 표시 하는 방법을 `/fp` 옵션 및 pragma 지시문이 서로 매핑됩니다. 자세한 내용은 개별 옵션과 pragma 지시문에 대 한 설명서를 참조 합니다.

||float_control(precise)|float_control(except)|fenv_access|fp_contract|
|-|-|-|-|-|
|`/fp:fast`|해제|해제|해제|On|
|`/fp:precise`|On|해제|해제|On|
|`/fp:strict`|On|On|On|해제|

### <a name="the-default-floating-point-environment"></a>기본 부동 소수점 환경

프로세스 초기화 될 때 합니다 *부동 소수점 환경의 기본* 설정 됩니다. 이 환경의 모든 부동 소수점 예외를 마스크, 가장 가까운 반올림 하려면 반올림 모드를 설정 (`FE_TONEAREST`), subnormal 유지 (비정상) 값에 대 한 유효 (가) 기본 전체 자릿수를 사용 하 여 **float**합니다 **이중**, 및 **long double** 값 하 고, 지원 되는 경우 무한대 제어는 기본 모드를 설정 합니다.

### <a name="floating-point-environment-access-and-modification"></a>부동 소수점 환경 액세스 및 수정

Microsoft Visual c + + 런타임 액세스 부동 소수점 환경을 수정 하는 여러 함수를 제공 합니다. 여기에 포함 됩니다 [_controlfp](../../c-runtime-library/reference/control87-controlfp-control87-2.md)를 [_clearfp](../../c-runtime-library/reference/clear87-clearfp.md), 및 [_statusfp](../../c-runtime-library/reference/status87-statusfp-statusfp2.md) 및 변형 합니다. 코드에 액세스 하거나 부동 소수점 환경을 수정 하는 경우 올바른 프로그램 동작을 보장 하기 위해 `fenv_access` 을 사용 해야 하거나 하 여는 `/fp:strict` 옵션 또는 사용 하 여는 `fenv_access` pragma를 적용 하려면 이러한 함수에 대 한 합니다. 때 `fenv_access` 는 사용 하지 않는 액세스 또는 부동 소수점 환경의 수정 예기치 않은 프로그램 동작이 발생할: 코드 수 부동 소수점 환경에 요청한 변경 내용을 인식 하지 않으면 부동 소수점 상태 레지스터를 보고 하지 않을 수 있습니다 현재 또는 예상 결과 예기치 않은 부동 소수점 예외가 발생할 수 있습니다 하거나 예상 되는 부동 소수점 예외 발생 하지 않을 수 있습니다.

코드에 액세스 또는 부동 소수점 환경을 수정 하는 경우 주의 해야 코드를 결합 하는 경우 여기서 `fenv_access` 하지 않은 코드를 사용 하 여 사용 하도록 설정할지 `fenv_access` 사용 하도록 설정 합니다. 코드에서 있는 `fenv_access` 을 설정 하지 않으면 컴파일러는 부동 소수점 상태 액세스 되거나 수정 되지 하 고 플랫폼 기본 부동 소수점 환경에 적용 되는 합니다. 저장 하 고 제어 되지 않은 함수에 전송 되기 전에 로컬 부동 소수점 환경을 기본 상태로 복원 하는 것이 좋습니다 `fenv_access` 사용 하도록 설정 합니다. 이 예제에서는 방법을 `float_control` pragma를 설정 하 고 복원할 수 있습니다.

```cpp
#pragma float_control(strict, on, push)
// Code that uses /fp:strict mode
#pragma float_control(pop)
```

### <a name="floating-point-rounding-modes"></a>부동 소수점 반올림 모드

아래에 모두 `/fp:precise` 고 `/fp:fast` 컴파일러 기본 부동 소수점 환경에서 실행 하기 위해 코드를 생성 하 고 환경에 액세스할 수 없거나 런타임에 수정 가정 합니다. 즉,는 코드는 부동 소수점 예외를 마스크 해제, 읽기 또는 부동 소수점 상태 레지스터를 작성 하거나 변경 하지 반올림 모드 가정 합니다.  그러나 일부 프로그램 부동 소수점 환경을 변경 해야 합니다. 예를 들어이 샘플 부동 소수점 반올림 모드를 변경 하 여 부동 소수점 곱셈의 오류 범위를 계산 합니다.

```cpp
// fp_error_bounds.cpp
#include <iostream>
#include <limits>
using namespace std;

int main(void)
{
    float a = std::<float>::max();
    float b = -1.1;
    float cLower = 0.0;
    float cUpper = 0.0;
    unsigned int control_word = 0;
    int err = 0;

    // compute lower error bound.
    // set rounding mode to -infinity.
    err = _controlfp_s(&control_word, _RC_DOWN, _MCW_RC);
    if (err)
    {
        cout << "_controlfp_s(&control_word, _RC_DOWN, _MCW_RC) failed with error:" << err << endl;
    }  
    cLower = a * b;

    // compute upper error bound.
    // set rounding mode to +infinity.
    err = _controlfp_s(&control_word, _RC_UP, _MCW_RC);
    if (err)
    {
        cout << "_controlfp_s(&control_word, _RC_UP, _MCW_RC) failed with error:" << err << endl;
    }
    cUpper = a * b;

    // restore default rounding mode.
    err = _controlfp_s(&control_word, _CW_DEFAULT, _MCW_RC);
    if (err)
    {
        cout << "_controlfp_s(&control_word, _CW_DEFAULT, _MCW_RC) failed with error:" << err << endl;
    }
    // display error bounds.
    cout << "cLower = " << cLower << endl;
    cout << "cUpper = " << cUpper << endl;
    return 0;
}
```

컴파일러가 부동 소수점 환경의에서 기본값을 가정 하므로 `/fp:fast` 하 고 `/fp:precise` 에 대 한 호출을 무시 하는 것이 없으면 `_controlfp_s`합니다. 예를 들어, 둘 다를 사용 하 여 컴파일하면 `/O2` 고 `/fp:precise` x86 아키텍처 경계 계산 되지 않는 및 샘플 프로그램 출력:

```Output
cLower = -inf
cUpper = -inf
```

x86 아키텍처에 대해 `/O2` 및 `/fp:strict` 둘 다를 사용하여 컴파일하면, 샘플 프로그램 출력은 다음과 같습니다.

```Output
cLower = -inf
cUpper = -3.40282e+38
```

### <a name="floating-point-special-values"></a>특수 부동 소수점 값

아래 `/fp:precise` 및 `/fp:strict`, 특수 값 (NaN, + infinity,-infinity,-0.0)를 포함 하는 식 IEEE-754 사양에 따라 동작 합니다. 아래 `/fp:fast`, 이러한 특수 한 값의 동작 IEEE-754와 일치 하지 않을 수 있습니다.

이 샘플에서 특수 한 값의 다른 동작을 보여 줍니다 `/fp:precise`하십시오 `/fp:strict` 고 `/fp:fast`:

```cpp
// fp_special_values.cpp
#include <stdio.h>
#include <cmath>

float gf0 = -0.0;

int main()
{
    float f1 = INFINITY;
    float f2 = NAN;
    float f3 = -INFINITY;
    bool a, b;
    float c, d, e;
    a = (f1 == f1);
    b = (f2 == f2);
    c = (f1 - f1);
    d = (f2 - f2);
    printf("INFINITY == INFINITY : %d\n", a);
    printf("NAN == NAN           : %d\n", b);
    printf("INFINITY - INFINITY  : %f\n", c);
    printf("NAN - NAN            : %f\n", d);

    e = gf0 / abs(f3);
    printf("std::signbit(-0.0/-INFINITY): %d\n", std::signbit(c));
    return 0;
}
```

사용 하 여 컴파일하면 `/O2` `/fp:precise` 또는 `/O2` `/fp:strict` x86 아키텍처, 출력은 IEEE-754 사양과 일치:

```Output
INFINITY == INFINITY : 1
NAN == NAN           : 0
INFINITY - INFINITY  : -nan(ind)
NAN - NAN            : -nan(ind)
std::signbit(-0.0/-INFINITY): 1
```

사용 하 여 컴파일하면 `/O2` `/fp:fast` x86 아키텍처 출력 IEEE-754와 일치 하지 않습니다.:

```Output
INFINITY == INFINITY : 1
NAN == NAN           : 1
INFINITY - INFINITY  : 0.000000
NAN - NAN            : 0.000000
std::signbit(-0.0/-INFINITY): 0
```

### <a name="floating-point-algebraic-transformations"></a>대 수 부동 소수점 변환

아래 `/fp:precise` 고 `/fp:strict`, 컴파일러 변환은 항상 비트 동일한 결과 생성 하지 않는 한 수학 변환을 수행 하지 않습니다. 컴파일러에서 이러한 변환을 수행할 수 있습니다 `/fp:fast`합니다. 예를 들어 식 `a * b + a * c` 샘플 함수에서 `algebraic_transformation` 컴파일될 수 있습니다 `a * (b + c)` 에서 `/fp:fast`합니다. 이러한 변환에서 수행 되지 않습니다 `/fp:precise` 나 `/fp:strict`, 컴파일러에서 생성 및 `a * b + a * c`합니다.

```cpp
float algebraic_transformation (float a, float b, float c)
{
    return a * b + a * c;
}
```

### <a name="floating-point-explicit-casting-points"></a>부동 소수점 명시적 캐스팅 지점

아래 `/fp:precise` 및 `/fp:strict`, 컴파일러가 식 평가 중 네 개의 특정 지점에서 소스 코드 정밀도로 반올림: 할당에서에서 포인터로 변환, 부동 소수점 인수는 함수 호출에 전달 되 면 시점과 부동 소수점 함수 호출에서 반환 됩니다. 대입문 명시적으로 중간 계산을 반올림 데 사용할 수 있습니다. 아래 `/fp:fast`, 컴파일러는 소스 코드의 전체 자릿수를 보장 하기 위해이 지점에서 명시적 캐스트를 생성 하지 않습니다. 이 샘플에서 다른 동작을 보여 줍니다. `/fp` 옵션:

```cpp
float casting(float a, float b)
{
    return 5.0*((double)(a+b));
}
```

사용 하 여 컴파일하면 `/O2` `/fp:precise` 하거나 `/O2` `/fp:strict`, 명시적 형식 캐스트 typecast를 및 x64에 대 한 생성된 된 코드에서 함수 반환 점에서 삽입 되는 것을 볼 수 있습니다 아키텍처:

```asm
        addss    xmm0, xmm1
        cvtss2sd xmm0, xmm0
        mulsd    xmm0, QWORD PTR __real@4014000000000000
        cvtsd2ss xmm0, xmm0
        ret      0
```

아래 `/O2` `/fp:fast` 모든 캐스트는 최적화할 때문에 생성 된 코드를 간소화 됩니다.

```asm
        addss    xmm0, xmm1
        mulss    xmm0, DWORD PTR __real@40a00000
        ret      0
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 C++ 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. **구성 속성** > **C/C++** > **코드 생성** 속성 페이지를 선택합니다.

1. 수정 된 **부동 소수점 모델** 속성입니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.floatingPointModel%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
