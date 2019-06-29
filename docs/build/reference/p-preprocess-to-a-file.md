---
title: /P(파일 전처리)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.GeneratePreprocessedFile
- /p
- VC.Project.VCCLWCECompilerTool.GeneratePreprocessedFile
helpviewer_keywords:
- /P compiler option [C++]
- -P compiler option [C++]
- P compiler option [C++]
- output files, preprocessor
- preprocessing output files
ms.assetid: 123ee54f-8219-4a6f-9876-4227023d83fc
ms.openlocfilehash: 5e6302d90647bce7e37c47a619e814cab300aaee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319982"
---
# <a name="p-preprocess-to-a-file"></a>/P(파일 전처리)

C와 C++ 소스파일을 전처리 하고, 그 결과를 출력하여 파일에 씁니다.

## <a name="syntax"></a>구문

```
/P
```

## <a name="remarks"></a>설명

파일은 소스 파일과 .i 확장자와 같은 기본 이름을 갖습니다. 이 프로세스에서 모든 사전 처리기 지시문이 수행되고 매크로 확장이 수행되며 주석이 제거됩니다. 전처리 된 출력에서 주석을 유지하려면 **/P** 옵션과 함께 [/C (전처리 중에 주석 유지)](c-preserve-comments-during-preprocessing.md) 옵션을 사용합니다.

**/P**는 `#line` 지시문을 출력에 포함하고 포함된 파일의 시작과 끝에 조건부 컴파일용 전처리기 지시문에 의해 제거 된 줄을 추가합니다. 이러한 지시어는 전처리된 파일의 줄 번호 다시 매깁니다. 결과적으로 오류 처리의 이후 단계 중에 생성된 오류는 전처리된 파일의 줄이 아니라 원래 소스 파일의 줄 번호를 의미합니다. `#line` 지시문의 생성을 사용하지 않기 위해서는 **/P** 뿐만 아니라 [/EP (#line 지시문 없이 stdout로 전처리)](ep-preprocess-to-stdout-without-hash-line-directives.md)도 사용합니다.

**/P** 옵션은 컴파일을 억제 합니다. [/Fo (개체 파일 이름)](fo-object-file-name.md)를 사용하더라도 .obj 파일은 생성하지 않습니다. 컴파일을 위해 전처리된 파일을 다시 제출해야 합니다. **/ P**는 **/FA**, **/Fa** 및 **/Fm** 옵션의 출력파일도 표시하지 않습니다. 자세한 내용은 [/FA, /Fa (목록 파일)](fa-fa-listing-file.md)과 [/Fm (맵 파일 이름 지정)](fm-name-mapfile.md)을 참조합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **C/C++** 폴더를 클릭합니다.

1. **전처리기** 속성 페이지를 클릭합니다

1. **전처리 파일 생성** 속성을 수정합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>을 참조하세요.

## <a name="example"></a>예제

다음 명령줄을 전처리 `ADD.C`주석을 유지, 추가 `#line` 지시문을 파일에 결과 기록 `ADD.I`:

```
CL /P /C ADD.C
```

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
[/Fi(출력 파일 이름 전처리)](fi-preprocess-output-file-name.md)
