---
title: /Za, /Ze(언어 확장명 사용 안 함)
ms.date: 02/19/2019
f1_keywords:
- VC.Project.VCCLWCECompilerTool.DisableLanguageExtensions
- /za
- /ze
- VC.Project.VCCLCompilerTool.DisableLanguageExtensions
helpviewer_keywords:
- -Za compiler option [C++]
- Za compiler option [C++]
- language extensions, disabling in compiler
- -Ze compiler option [C++]
- language extensions
- enable language extensions
- /Za compiler option [C++]
- /Ze compiler option [C++]
- Disable Language Extensions compiler option
- Ze compiler option [C++]
ms.assetid: 65e49258-7161-4289-a176-7c5c0656b1a2
ms.openlocfilehash: 1db1dbdba4829ccf939cdc4f07ccfefe2474a35d
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812306"
---
# <a name="za-ze-disable-language-extensions"></a>/Za, /Ze(언어 확장명 사용 안 함)

합니다 **/Za** 컴파일러 옵션 사용 하지 않도록 설정 하 고 c ANSI C89/ISO C90와 호환 되지 않는 Microsoft 확장에 대 한 오류를 내보냅니다. 사용 되지 않는 **/Ze** 컴파일러 옵션을 사용 하면 Microsoft 확장입니다. Microsoft 확장은 기본적으로 사용하도록 설정됩니다.

## <a name="syntax"></a>구문

> **/Za**<br/>
> **/Ze**

## <a name="remarks"></a>설명

> [!NOTE]
> 사용 **/Za** c + +는 좋지 않습니다으로 코드를 컴파일할 때. 합니다 **/Ze** 동작 기본적으로 켜져 있으므로 옵션은 사용 되지 않습니다. 사용 되지 않는 컴파일러 옵션의 목록을 참조 하세요 [제거 컴파일러 옵션과 사용 되지 않는](compiler-options-listed-by-category.md#deprecated-and-removed-compiler-options)합니다.

Microsoft C/c + + 컴파일러에는 두 가지 방법으로 C 코드의 컴파일을 지원합니다.

- 컴파일러는 소스 파일에 기본적으로 C 컴파일 모드를 사용을 *.c* 확장을 때나 합니다 [/Tc](tc-tp-tc-tp-specify-source-file-type.md) 또는 [/TC](tc-tp-tc-tp-specify-source-file-type.md) 옵션을 지정 합니다. C 컴파일러는 기본적으로 C 언어에 대 한 Microsoft 확장을 사용 하도록 설정 하는 C89/C90 컴파일러입니다. 특정 확장에 대 한 자세한 내용은 참조 하세요. [C 및 c + +에 대 한 Microsoft 확장](microsoft-extensions-to-c-and-cpp.md)합니다. 경우 모두 C 컴파일 및 **/Za** C89/C90 표준을 엄격 하 게 준수는 C 컴파일러 옵션이 지정 됩니다. 컴파일러가 Microsoft 확장 키워드 단순 식별자로 처리 다른 Microsoft 확장을 사용 하지 않도록 설정 하 고 자동으로 정의 된 [ \_ \_STDC\_ \_ ](../../preprocessor/predefined-macros.md) 미리 정의 된 C 프로그램에 대 한 매크로 제공 합니다.

- 컴파일러는 c + + 컴파일 모드에서 C 코드를 컴파일할 수 있습니다. 이 동작은 없는 소스 파일에 대 한 기본값을 *.c* 확장을 및 시기를 [/Tp](tc-tp-tc-tp-specify-source-file-type.md) 또는 [/TP](tc-tp-tc-tp-specify-source-file-type.md) 옵션을 지정 합니다. C + + 컴파일 모드에서 컴파일러는 ISO C99 및 C11 표준 c + + 표준에 통합 되었습니다에 부분을 지원 합니다. C 코드를 거의 모든 유효한 c + + 코드 이기도합니다. 적은 수의 C 키워드 및 코드 구문을 아닌 올바른 c + + 코드 또는 c + +에서 다르게 해석 됩니다. 컴파일러는 이러한 경우 표준 c + +에 따라 동작합니다. C + + 컴파일 모드에서를 **/Za** 옵션 예기치 않은 동작이 발생할 수 있습니다 및 권장 되지 않습니다.

다른 컴파일러 옵션은 컴파일러에서 표준 규칙을 준수 하는 방법을 달라질 수 있습니다. 특정 표준 C 및 c + + 동작 설정을 지정 하는 방법에 대해서는 [/Zc](zc-conformance.md) 컴파일러 옵션입니다. 추가 c + + 표준 준수 설정에 대 한 참조를 [관대 한 /-](permissive-standards-conformance.md) 하 고 [/std](std-specify-language-standard-version.md) 컴파일러 옵션입니다.

Visual c + +를 사용 하 여 규칙과 관련 된 문제에 대 한 자세한 내용은 참조 하세요. [비표준 동작](../../cpp/nonstandard-behavior.md)합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 탐색 창에서 선택 **구성 속성** > **C/c + +** > **언어**합니다.

1. 수정 된 **언어 확장 사용 안 함** 속성입니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableLanguageExtensions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[컴파일러 옵션](compiler-options.md)<br/>
[/Zc(규칙)](zc-conformance.md)<br/>
[/permissive-(표준 준수)](permissive-standards-conformance.md)<br/>
[/std(언어 표준 버전 지정)](std-specify-language-standard-version.md)<br/>
