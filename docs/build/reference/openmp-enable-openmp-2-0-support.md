---
title: /openmp (OpenMP 지원 활성화)
ms.date: 04/15/2019
f1_keywords:
- /openmp
- VC.Project.VCCLCompilerTool.OpenMP
helpviewer_keywords:
- /openmp compiler option [C++]
- -openmp compiler option [C++]
ms.assetid: 9082b175-18d3-4378-86a7-c0eb95664e13
ms.openlocfilehash: caa06d89c590abd2b3a74a5a6b118d6ba4acd910
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/17/2019
ms.locfileid: "59674268"
---
# <a name="openmp-enable-openmp-support"></a>/openmp (OpenMP 지원 활성화)

컴파일러에서 처리 하도록 [ `#pragma omp` ](../../preprocessor/omp.md) OpenMP 지원 하기 위해 지시문입니다.

## <a name="syntax"></a>구문

::: moniker range=">= vs-2019"

> **/openmp**\[**:**__experimental__]

::: moniker-end

::: moniker range="<= vs-2017"

> **/openmp**

::: moniker-end

## <a name="remarks"></a>설명

`#pragma omp` 지정 하는 데 사용 됩니다 [지시문](../../parallel/openmp/reference/openmp-directives.md) 하 고 [절](../../parallel/openmp/reference/openmp-clauses.md)합니다. 하는 경우 **/openmp** 컴파일에서 지정 하지 않으면 컴파일러가 OpenMP 절 및 지시문을 무시 합니다. [OpenMP 함수](../../parallel/openmp/reference/openmp-functions.md) 경우에도 컴파일러에서 처리 하는 호출 **/openmp** 지정 되지 않습니다.

::: moniker range=">= vs-2019"

C++ 컴파일러에는 현재 OpenMP 2.0 표준을 지원 합니다. 그러나 Visual Studio 2019는 이제 SIMD 기능을 제공합니다. SIMD를 사용 하려면 사용 하 여 컴파일하는 **/openmp: 실험적** 옵션입니다. 이 옵션을 사용 하면 일반적인 OpenMP 기능 모두 및 추가 OpenMP SIMD 기능을 사용할 수 없는 사용 하는 경우는 **/openmp** 전환 합니다.

::: moniker-end

모두 사용 하 여 컴파일된 응용 프로그램 **/openmp** 하 고 **/clr** 단일 응용 프로그램 도메인 프로세스에서 실행할 수 있습니다. 여러 응용 프로그램 도메인은 지원 되지 않습니다. 즉, 모듈 생성자 (`.cctor`)는 프로세스를 사용 하 여 컴파일된 경우 검색 실행 **/openmp**, 앱이 기본이 아닌 런타임을 로드 하는 경우. 자세한 내용은 [appdomain](../../cpp/appdomain.md)를 [/clr (공용 언어 런타임 컴파일)](clr-common-language-runtime-compilation.md), 및 [혼합 어셈블리 초기화](../../dotnet/initialization-of-mixed-assemblies.md)합니다.

둘 다를 사용 하 여 컴파일한 앱을 로드 하려고 하면 **/openmp** 및 **/clr** 기본이 아닌 응용 프로그램 도메인에는 <xref:System.TypeInitializationException> 는 디버거 외부 예외가 및 `OpenMPWithMultipleAppdomainsException` 예외 디버거에서 throw 됩니다.

이러한 예외는 다음과 같은 경우에도 발생할 수 있습니다.

- 사용 하 여 응용 프로그램은 컴파일 **/clr** 있지만 **/openmp**, 프로세스에 사용 하 여 컴파일한 앱을 포함 하는 되는 기본이 아닌 응용 프로그램 도메인에 로드 되 고 **/openmp**.

- 전달 하는 경우에 **/clr** 유틸리티와 앱 같은 [regasm.exe](/dotnet/framework/tools/regasm-exe-assembly-registration-tool), 기본이 아닌 응용 프로그램 도메인으로 해당 대상 어셈블리를 로드 하는 합니다.

공용 언어 런타임 코드 액세스 보안은 OpenMP 지역에서 작동 하지 않습니다. 병렬 영역 외부 CLR 코드 액세스 보안 특성을 적용 하는 경우 병렬 영역에 적용 되지 않습니다.

Microsoft를 작성 하는 것을 권장 하지 않습니다 **/openmp** 신뢰할 수 있는 호출자를 부분적으로 허용 하는 앱입니다. 사용 하지 않는 <xref:System.Security.AllowPartiallyTrustedCallersAttribute>, 또는 모든 CLR 코드 액세스 보안 특성.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. 확장 된 **구성 속성** > **C /C++** > **언어** 속성 페이지.

1. 수정 된 **OpenMP 지원** 속성입니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OpenMP%2A>을 참조하세요.

## <a name="example"></a>예제

다음 샘플 시작 된 후 스레드 풀을 사용 하 여 스레드 풀 시작의 효과 중 일부를 보여 줍니다. 이중 프로세서, 단일 코어 x64를 가정 하면 스레드 풀 이동 약 16ms 시작. 그 후 약간 추가 비용은 스레드 풀에 대 한 합니다.

사용 하 여 컴파일하는 경우 **/openmp**, 두 번째 호출은 test2 사용 하 여 컴파일하는 경우 보다 더 이상 실행 되지 **/openmp-** 을 있는 그대로 스레드 풀 시작 되지 않습니다. 백만 반복에는 **/openmp** 버전 보다 빠릅니다. 합니다 **/openmp-** test2 두 번째 호출에 대 한 버전입니다. 25 반복에서 둘 다 **/openmp-** 하 고 **/openmp** 클록 세분성 보다 작은 버전 등록 합니다.

응용 프로그램에서 하나의 루프가 있고 15ms 미만 (컴퓨터에 대 한 대략적인 오버 헤드에 대 한 조정)에서 실행 하는 경우 **/openmp** 적합 하지 는지 않습니다. 사용 하려는 높은 경우 **/openmp**합니다.

```cpp
// cpp_compiler_options_openmp.cpp
#include <omp.h>
#include <stdio.h>
#include <stdlib.h>
#include <windows.h>

volatile DWORD dwStart;
volatile int global = 0;

double test2(int num_steps) {
   int i;
   global++;
   double x, pi, sum = 0.0, step;

   step = 1.0 / (double) num_steps;

   #pragma omp parallel for reduction(+:sum) private(x)
   for (i = 1; i <= num_steps; i++) {
      x = (i - 0.5) * step;
      sum = sum + 4.0 / (1.0 + x*x);
   }

   pi = step * sum;
   return pi;
}

int main(int argc, char* argv[]) {
   double   d;
   int n = 1000000;

   if (argc > 1)
      n = atoi(argv[1]);

   dwStart = GetTickCount();
   d = test2(n);
   printf_s("For %d steps, pi = %.15f, %d milliseconds\n", n, d, GetTickCount() - dwStart);

   dwStart = GetTickCount();
   d = test2(n);
   printf_s("For %d steps, pi = %.15f, %d milliseconds\n", n, d, GetTickCount() - dwStart);
}
```

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md) \
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md) \
[MSVC의 OpenMP](../../parallel/openmp/openmp-in-visual-cpp.md)
