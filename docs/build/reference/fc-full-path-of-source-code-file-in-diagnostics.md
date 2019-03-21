---
title: /FC(진단 소스 코드 파일의 전체 경로)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.UseFullPaths
- /FC
helpviewer_keywords:
- /FC compiler option [C++]
- -FC compiler option [C++]
ms.assetid: 1f11414e-cb42-421b-be68-9d369aab036b
ms.openlocfilehash: 190174e1e2ac4d160140ddc54f9cc1c3a1b31709
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57809030"
---
# <a name="fc-full-path-of-source-code-file-in-diagnostics"></a>/FC(진단 소스 코드 파일의 전체 경로)

컴파일러에서 진단에 컴파일러에 전달 하는 소스 코드 파일의 전체 경로 표시 합니다.

## <a name="syntax"></a>구문

> /FC

## <a name="remarks"></a>설명

다음 코드 예제를 고려해 야 합니다.

```cpp
// compiler_option_FC.cpp
int main( ) {
   int i   // C2143
}
```

없이 **/FC**, 진단 텍스트는 진단 텍스트와 비슷하게 표시 됩니다.

- compiler_option_FC.cpp(5): 오류 C2143: 구문 오류: 누락 된 ';' 이전 '을 (를) '

사용 하 여 **/FC**, 진단 텍스트는 진단 텍스트와 비슷하게 표시 됩니다.

- c:\test\compiler_option_fc.cpp(5) : error C2143: syntax error : missing ';' before '}'

**/FC** 사용 하는 경우 파일 이름의 전체 경로 표시 하려는 경우 필요 합니다 &#95; &#95;파일&#95; &#95; 매크로입니다. 참조 [미리 정의 된 매크로](../../preprocessor/predefined-macros.md) 대 한 자세한 내용은 &#95; &#95;파일&#95;&#95;합니다.

합니다 **/FC** 옵션은 권한에 포함 된 **/ZI**합니다. 에 대 한 자세한 내용은 **/ZI**를 참조 하십시오 [/z7, /Zi, /ZI (디버그 정보 형식)](z7-zi-zi-debug-information-format.md)합니다.

**/FC** 소문자의 전체 경로 출력 합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **C/c + +** > **고급** 속성 페이지.

1. 수정 된 **전체 경로 사용** 속성입니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UseFullPaths%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
