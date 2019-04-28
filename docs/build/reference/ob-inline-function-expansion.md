---
title: /Ob(인라인 함수 확장)
ms.date: 09/25/2017
f1_keywords:
- VC.Project.VCCLWCECompilerTool.InlineFunctionExpansion
- VC.Project.VCCLCompilerTool.InlineFunctionExpansion
- /ob
helpviewer_keywords:
- inline functions, function expansion compiler option [C++]
- -Ob1 compiler option [C++]
- -Ob0 compiler option [C++]
- /Ob0 compiler option [C++]
- /Ob1 compiler option [C++]
- any suitable compiler option [C++]
- Ob2 compiler option [C++]
- Ob1 compiler option [C++]
- /Ob2 compiler option [C++]
- Ob compiler option [C++]
- -Ob2 compiler option [C++]
- disable compiler option [C++]
- -Ob compiler option [C++]
- /Ob compiler option [C++]
- only __inline compiler option [C++]
- Ob0 compiler option [C++]
- inline expansion, compiler option
ms.assetid: f134e6df-e939-4980-a01d-47425dbc562a
ms.openlocfilehash: 6bf16e5725916e81e64d80c0a1f96bf502c8826c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320229"
---
# <a name="ob-inline-function-expansion"></a>/Ob(인라인 함수 확장)

함수의 인라인 확장을 제어합니다.

## <a name="syntax"></a>구문

> /Ob{0|1|2}

## <a name="arguments"></a>인수

**0**<br/>
인라인 확장을 사용하지 않도록 설정합니다. 기본적으로 모든 함수에서 컴파일러의 판단에 따라 확장 발생 라고도 *자동 인라인*합니다.

**1**<br/>
표시 된 확장 [인라인](../../cpp/inline-functions-cpp.md)를 `__inline`, 또는 `__forceinline`, 또는 C++ 클래스 선언에 정의 된 멤버 함수입니다.

**2**<br/>
기본값입니다. `inline`, `__inline` 또는 `__forceinline`으로 표시된 함수와 컴파일러에서 선택한 기타 함수를 확장합니다.

**/ Ob2** 때 적용 됩니다 [/o1, / o2 (크기 최소화, 속도 최대화)](o1-o2-minimize-size-maximize-speed.md) 하거나 [/Ox (사용 가장 속도 최적화)](ox-full-optimization.md) 사용 됩니다.

이 옵션을 사용 하려면 사용 하 여 최적화를 활성화 **/o1**를 **/o2**를 **/Ox**, 또는 **/Og**합니다.

## <a name="remarks"></a>설명

컴파일러는 인라인 확장 옵션과 키워드를 제안으로 처리합니다. 함수가 인라인 확장된다는 보장은 없습니다. 인라인 확장을 사용하지 않을 수 있으나 `__forceinline` 키워드를 사용하는 경우에도 컴파일러가 강제로 특정 함수를 인라인 확장하도록 할 수는 없습니다.

사용할 수는 `#pragma` [auto_inline](../../preprocessor/auto-inline.md) 함수를 인라인 확장 후보 고려 대상에서 제외할 지시문입니다. 또한 참조를 `#pragma` [내장](../../preprocessor/intrinsic.md) 지시문입니다.

> [!NOTE]
> 프로 파일링 테스트 실행에서 수집 되는 정보를 지정 하는 경우 적용에서 되는 최적화를 재정의 **/Ob**하십시오 **/Os**, 또는 **/Ot**합니다. 자세한 내용은 [프로필 기반 최적화](../profile-guided-optimizations.md)합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. 확장 **구성 속성**를 **C /C++** 를 선택 하 고 **최적화**.

1. 수정 된 **인라인 함수 확장** 속성입니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.InlineFunctionExpansion%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[/O 옵션(코드 최적화)](o-options-optimize-code.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
