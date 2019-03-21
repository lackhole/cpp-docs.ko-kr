---
title: /openmp(OpenMP 2.0 지원 활성화)
ms.date: 11/04/2016
f1_keywords:
- /openmp
- VC.Project.VCCLCompilerTool.OpenMP
helpviewer_keywords:
- /openmp compiler option [C++]
- -openmp compiler option [C++]
ms.assetid: 9082b175-18d3-4378-86a7-c0eb95664e13
ms.openlocfilehash: f1edcc6d29a5b84106b3a5fd91d2446c34e0f7b9
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57807470"
---
# <a name="openmp-enable-openmp-20-support"></a>/openmp(OpenMP 2.0 지원 활성화)

컴파일러에서 처리 하도록 `#pragma` [omp](../../preprocessor/omp.md)합니다.

## <a name="syntax"></a>구문

```
/openmp
```

## <a name="remarks"></a>설명

`#pragma omp` 지정 하는 데 사용 됩니다 [지시문](../../parallel/openmp/reference/openmp-directives.md) 하 고 [절](../../parallel/openmp/reference/openmp-clauses.md)합니다. 하는 경우 **/openmp** 지정 하지 않으면 컴파일, 컴파일러는 OpenMP 절 및 지시문을 무시 합니다. [OpenMP 함수](../../parallel/openmp/reference/openmp-functions.md) 경우에도 컴파일러에서 처리 하는 호출 **/openmp** 지정 하지 않으면.

응용 프로그램을 컴파일하면 **/openmp** 하 고 **/clr** 여러 응용 프로그램 도메인을 지원 하지 않으므로 단일 응용 프로그램 도메인 프로세스에서 실행할 수 있습니다. 즉, 실행 되는 모듈 생성자 (.cctor) 감지 합니다 프로세스를 사용 하 여 컴파일된 **/openmp** 기본이 아닌 런타임에 응용 프로그램을 로드 하는 경우. 자세한 내용은 [appdomain](../../cpp/appdomain.md)를 [/clr (공용 언어 런타임 컴파일)](clr-common-language-runtime-compilation.md), 및 [혼합 어셈블리 초기화](../../dotnet/initialization-of-mixed-assemblies.md)합니다.

사용 하 여 컴파일된 응용 프로그램을 로드 하려고 하면 **/openmp** 하 고 **/clr** 기본이 아닌 응용 프로그램 도메인에는 <xref:System.TypeInitializationException> 디버거 외부에서 예외가 throw 됩니다 및 디버거에서 OpenMPWithMultipleAppdomainsException 예외가 throw 됩니다.

이러한 예외는 다음과 같은 경우에도 발생할 수 있습니다.

- 응용 프로그램 사용 하 여 컴파일한 **/clr**, 있지만 **/openmp**, 기본이 아닌 응용 프로그램 도메인에 있지만 프로세스 사용 하 여 컴파일된 응용 프로그램을 포함 하는 여기서 로드 되 **/ openmp**합니다.

- 전달 하는 경우에 **/clr** regasm.exe와 같은 유틸리티를 응용 프로그램 ([Regasm.exe (어셈블리 등록 도구)](/dotnet/framework/tools/regasm-exe-assembly-registration-tool)), 기본이 아닌 응용 프로그램 도메인으로 해당 대상 어셈블리를 로드 하는 합니다.

공용 언어 런타임 코드 액세스 보안은 OpenMP 지역에서 작동 하지 않습니다. 병렬 영역 외부 CLR 코드 액세스 보안 특성을 적용 하는 경우 병렬 영역에 적용 되지 않습니다.

Microsoft 작성 하지 않는 조언 **/openmp** 부분적으로 허용 하는 응용 프로그램 신뢰 호출자를 사용 하 여 <xref:System.Security.AllowPartiallyTrustedCallersAttribute>, 또는 모든 CLR 코드 액세스 보안 특성.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. **구성 속성** 노드를 확장합니다.

1. 확장 된 **C/c + +** 노드.

1. 선택 된 **언어** 속성 페이지.

1. 수정 된 **OpenMP 지원** 속성입니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OpenMP%2A>을 참조하세요.

## <a name="example"></a>예제

다음 샘플 시작 후 threadpool을 사용 하 여 threadpool 시작의 효과 중 일부를 보여 줍니다. 단일 코어, x64, 가정 하 고 이중 프로세서 threadpool 이동 약 되 시작. 그 후 하지만 비용은 거의 threadpool에 대 한 합니다.

로 컴파일할 때 **/openmp**, test2 두 번째 호출으로 컴파일하는 경우 보다 더 이상 실행 되지 **/openmp-** 을 있는 그대로 threadpool 시작 되지 않습니다. 백만 반복에는 **/openmp** 버전에 비해 빠릅니다를 **/openmp-** test2를 두 번째 호출에 대 한 버전 **/openmp-** 및 **/openmp** 클록 세분성 보다 작은 버전 등록 합니다.

응용 프로그램에서 하나의 루프가 있고 (컴퓨터에 대략적인 부하에 따라 조정) 미만인에서 실행 되는 경우 **/openmp** 적절 하 게 되지 않을 수 있습니다 를사용하여고려해야할필요할경우그이상의모든것 **/openmp**합니다.

```
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

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
