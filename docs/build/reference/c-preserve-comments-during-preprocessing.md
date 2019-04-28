---
title: /C(전처리 중에 주석 유지)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.KeepComments
- /c
- VC.Project.VCCLWCECompilerTool.KeepComments
helpviewer_keywords:
- comments, not stripping during preprocessing
- preserve comments during preprocessing
- -c compiler option [C++]
- c compiler option [C++]
- /c compiler option [C++]
ms.assetid: 944567ca-16bc-4728-befe-d414a7787f26
ms.openlocfilehash: c5854fd1255ab509d8778828de25638dd821d74b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62272834"
---
# <a name="c-preserve-comments-during-preprocessing"></a>/C(전처리 중에 주석 유지)

전처리하는 동안 주석을 유지합니다.

## <a name="syntax"></a>구문

```
/C
```

## <a name="remarks"></a>설명

**/E**, **/P**, 또는 **/EP**와 같은 컴파일러 옵션이 필요합니다.

다음 코드 샘플에는 소스 코드 주석이 표시 됩니다.

```
// C_compiler_option.cpp
// compile with: /E /C /c
int i;   // a variable
```

이 샘플에는 다음과 같은 출력이 생성 됩니다.

```
#line 1 "C_compiler_option.cpp"
int i;   // a variable
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [컴파일러 설정 및 빌드 속성](../working-with-project-properties.md)을 참조합니다.

1. **C/C++** 폴더를 클릭합니다.

1. **전처리기** 속성 페이지를 클릭합니다.

1. **주석 유지** 속성을 수정합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.KeepComments%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
[/E(stdout으로 전처리)](e-preprocess-to-stdout.md)<br/>
[/P(파일로 전처리)](p-preprocess-to-a-file.md)<br/>
[/EP(#line 지시문 없이 stdout으로 전처리)](ep-preprocess-to-stdout-without-hash-line-directives.md)
