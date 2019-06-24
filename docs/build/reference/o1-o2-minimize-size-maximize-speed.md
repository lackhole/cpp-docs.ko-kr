---
title: /O1, /O2(크기 최소화, 속도 최대화)
ms.date: 09/25/2017
f1_keywords:
- /o2
- /o1
helpviewer_keywords:
- maximize speed compiler option [C++]
- minimize size compiler option [C++]
- -O2 compiler option [C++]
- fast code
- small code
- O2 compiler option [C++]
- /O2 compiler option [C++]
- -O1 compiler option [C++]
- O1 compiler option [C++]
- /O1 compiler option [C++]
ms.assetid: 2d1423f5-53d9-44da-8908-b33a351656c2
ms.openlocfilehash: d33fe6bceae09267fd3f79ffe3dc26864e87c764
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320359"
---
# <a name="o1-o2-minimize-size-maximize-speed"></a>/O1, /O2(크기 최소화, 속도 최대화)

생성되는 코드의 크기와 속도에 영향을 주는 미리 정의된 옵션 집합을 선택합니다.

## <a name="syntax"></a>구문

> /O1 /O2

## <a name="remarks"></a>설명

**/O1**과 **/O2** 컴파일러 옵션은 몇가지 특정 최적화 옵션을 단번에 설정할 수 있는 신속한 방법입니다. **/O1** 옵션은 대부분의 경우 가장 작은 코드를 작성하는 개별 최적화 옵션을 설정합니다. **/O2** 옵션은 대부분의 경우 가장 빠른 코드를 만드는 옵션을 설정합니다. **/O2** 옵션이 릴리스 빌드에 대한 기본 옵션입니다. 이 표는 **/O1**과 **/O2**에 의해 설정되는 특정 옵션을 보여줍니다.

|옵션|에 해당|
|------------|-------------------|
|**/ O1** (크기 최소화)|[/Og](og-global-optimizations.md) [/Os](os-ot-favor-small-code-favor-fast-code.md) [/Oy](oy-frame-pointer-omission.md) [/Ob2](ob-inline-function-expansion.md) [/GF](gf-eliminate-duplicate-strings.md) [/Gy](gy-enable-function-level-linking.md)|
|**/ O2** (속도 최대화)|[/Og](og-global-optimizations.md) [/Oi](oi-generate-intrinsic-functions.md) [/Ot](os-ot-favor-small-code-favor-fast-code.md) [/Oy](oy-frame-pointer-omission.md) [/Ob2](ob-inline-function-expansion.md) [/GF](gf-eliminate-duplicate-strings.md) [/Gy](gy-enable-function-level-linking.md)|

**/O1**과 **/O2**는 함께 사용할 수 없습니다.

> [!NOTE]
> **x86 특정** 옵션은 프레임 포인터 생략([/Oy](oy-frame-pointer-omission.md))옵션의 사용을 의미합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성**에서 **C/C++**을 연 다음 **최적화** 속성 페이지를 선택합니다.

1. **최적화** 속성을 수정합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[/O 옵션(코드 최적화)](o-options-optimize-code.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
[/EH(예외 처리 모델)](eh-exception-handling-model.md)
