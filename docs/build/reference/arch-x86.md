---
title: /arch(x86)
ms.date: 11/04/2016
ms.assetid: 9dd5a75d-06e4-4674-aade-33228486078d
ms.openlocfilehash: a429824a7c22aa9aba460481394785d31b92a5ef
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64341054"
---
# <a name="arch-x86"></a>/arch(x86)

x86에서 코드 생성 아키텍처를 지정합니다. [(x64) /arch](arch-x64.md)과 [/arch (ARM)](arch-arm.md)도 참조합니다.

## <a name="syntax"></a>구문

```
/arch:[IA32|SSE|SSE2|AVX|AVX2]
```

## <a name="arguments"></a>인수

**/arch:IA32**<br/>
고급 명령을 지정하지 않는 반면 부동 소수점 계산을 위해 x87도 지정합니다.

**/arch:SSE**<br/>
SSE 명령을 사용하도록 설정합니다.

**/arch:SSE2**<br/>
SSE2 명령을 사용하도록 설정합니다. 이 x86에서의 기본 명령 없으면 플랫폼 **/arch** 옵션을 지정 합니다.

**/arch:AVX**<br/>
Intel Advanced Vector Extensions 명령을 사용하도록 설정합니다.

**/arch:AVX2**<br/>
Intel 고급 벡터 확장명 2 명령을 사용하도록 설정합니다.

## <a name="remarks"></a>설명

SSE 및 SSE2 명령은 다양한 Intel 및 AMD 프로세서에 있습니다. AVX 명령은 Intel Sandy Bridge 프로세서와 AMD Bulldozer 프로세서에 있습니다. AVX2 명령은 Intel Haswell 및 Broadwell 프로세서와 AMD Excavator 기반 프로세서에서 지원합니다.

`_M_IX86_FP`, `__AVX__` 및 `__AVX2__` 매크로 표시 하는 경우 **/arch** 컴파일러 옵션이 사용 된 합니다. 자세한 내용은 [Predefined Macros](../../preprocessor/predefined-macros.md)을 참조하십시오. 합니다 **/arch:avx2** 옵션 및 `__AVX2__` 매크로 Visual Studio 2013 업데이트 2 버전 12.0.34567.1에서에서 도입 되었습니다.

최적화 될 때 및 SSE 및 sse2 명령을 사용 하는 방법을 때 **/arch** 지정 됩니다. x87 부동 소수점 레지스터 스택 대신 SSE/SSE2 명령 및 레지스터를 사용하는 게 더 빠르다고 판단하면 최적화 프로그램은 일부 스칼라 부동 소수점 계산에 SSE 및 SSE2 명령을 사용합니다. 따라서 코드에서는 부동 소수점 계산에 x87과 SSE/SSE2를 둘 다 혼합하여 사용할 수 있습니다. 또한 **/arch:sse2**, SSE2 명령을 일부 64 비트 정수 연산에 사용할 수 있습니다.

SSE 및 SSE2 명령을 사용하는 것 이외에 컴파일러는 SSE 및 SSE2를 지원하는 프로세서 수정 버전에 있는 다른 명령도 사용합니다. 이러한 예로 Intel 프로세서의 Pentium Pro 수정 버전에 처음으로 나타나는 CMOV 명령이 있습니다.

X86 컴파일러 생성 기본적으로 SSE2 명령을 사용 하는 코드를 지정 해야 합니다 **/arch:ia32** x86에 대 한 SSE 및 sse2 명령을 생성 하지 않으려면 프로세서.

**/arch** 만 코드를 네이티브 함수에 대 한 생성에 영향을 줍니다. 사용 하는 경우 [/clr](clr-common-language-runtime-compilation.md) 를 컴파일하려면 **/arch** 에 관리 되는 함수에 대 한 코드 생성에 영향을 주지 않습니다.

**/arch** 하 고 [/QIfist](qifist-suppress-ftol.md) 는 동일한 compiland에서 사용할 수 없습니다. 특히 FP 제어 단어를 수정하는 데 `_controlfp`를 사용하지 않으면 런타임 시작 코드는 x87 FPU 제어 단어 정밀도 제어 필드를 53비트로 설정합니다. 따라서 식의 모든 float 및 double 연산에서는 53비트 significand와 15비트 지수를 사용합니다. 그러나 SSE 단정밀도 연산에서는 24비트 significand와 8비트 지수를 사용하고 SSE2 배정밀도 연산에서는 53비트 significand 및 11비트 지수를 사용합니다. 자세한 내용은 [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)를 참조하세요. 이러한 차이점은 하나의 식 트리에서도 발생할 수 있지만 각 하위 식 이후 사용자 할당이 수행되는 경우에는 가능하지 않습니다. 다음을 살펴보세요.

```cpp
r = f1 * f2 + d;  // Different results are possible on SSE/SSE2.
```

비교:

```cpp
t = f1 * f2;   // Do f1 * f2, round to the type of t.
r = t + d;     // This should produce the same overall result
               // whether x87 stack is used or SSE/SSE2 is used.
```

### <a name="to-set-this-compiler-option-for-avx-avx2-ia32-sse-or-sse2-in-visual-studio"></a>Visual Studio에서 AVX, AVX2, IA32, SSE 또는 SSE2에 대한 컴파일러 옵션을 설정하려면 

1. 프로젝트에 대한 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성**, **C/C++** 폴더를 선택합니다.

1. 선택 된 **코드 생성** 속성 페이지.

1. 수정 된 **고급 명령 집합 사용** 속성입니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[/arch(최소 CPU 아키텍처)](arch-minimum-cpu-architecture.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
