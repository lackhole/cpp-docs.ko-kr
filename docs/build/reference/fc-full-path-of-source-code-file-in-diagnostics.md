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
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62271296"
---
# <a name="fc-full-path-of-source-code-file-in-diagnostics"></a>/FC(진단 소스 코드 파일의 전체 경로)

컴파일러가 진단 프로그램에서 컴파일러에 전달하는 소스 코드 파일의 전체 경로를 표시합니다.

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

**/FC**가 없다면 진단 텍스트는 다음의 진단 텍스트와 비슷하게 표시됩니다.

- compiler_option_FC.cpp(5) : error C2143: syntax error : missing ';' before '}'

**/FC**를 사용하면 진단 텍스트는 다음과 유사한 진단 텍스트로 표시됩니다.

- c:\test\compiler_option_fc.cpp(5) : error C2143: syntax error : missing ';' before '}'

__FILE__ 매크로를 사용할 때 파일 이름의 전체 경로를 확인하는 경우에도 **/FC**가 필요합니다. __FILE__에 대한 보다 자세한 내용은 [미리 정의된 매크로](../../preprocessor/predefined-macros.md)를 참조합니다.

**/FC** 옵션은 **/ZI**에 포함됩니다. **/ZI**에 대한 자세한 내용은 [/Z7, /Zi, /ZI (디버그 정보 형식)](z7-zi-zi-debug-information-format.md)을 참조합니다.

**/FC**는 소문자로 전체 경로를 출력합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** > **C/C++**  > **고급** 속성 페이지를 선택하세요.

1. **전체 경로 사용** 속성을 수정합니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UseFullPaths%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
