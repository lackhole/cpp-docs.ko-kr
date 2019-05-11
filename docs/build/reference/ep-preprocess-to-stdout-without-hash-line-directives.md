---
title: /EP(#line 지시문 없이 stdout로 전처리)
ms.date: 11/04/2016
f1_keywords:
- /ep
- VC.Project.VCCLCompilerTool.GeneratePreprocessedFileNoLines
helpviewer_keywords:
- copy preprocessor output to stdout
- preprocessor output, copy to stdout
- -EP compiler option [C++]
- EP compiler option [C++]
- /EP compiler option [C++]
ms.assetid: 6ec411ae-e33d-4ef5-956e-0054635eabea
ms.openlocfilehash: 49745b644234c0e5ce92661f14304531aaca5c69
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62293253"
---
# <a name="ep-preprocess-to-stdout-without-line-directives"></a>/EP(#line 지시문 없이 stdout로 전처리)

C 및 C++ 소스 파일을 전처리하고 표준 출력 장치에 전처리된 파일을 복사합니다.

## <a name="syntax"></a>구문

```
/EP
```

## <a name="remarks"></a>설명

프로세스에서 모든 전처리기 지시문이 실행되고 매크로 확장이 수행되며 주석이 제거됩니다. 전처리된 출력에 주석을 유지하려면 **/EP** 옵션과 함께 [/C(전처리 중 주석 유지)](c-preserve-comments-during-preprocessing.md) 옵션을 사용합니다.

**/EP** 옵션은 컴파일을 억제합니다. 컴파일을 위해 전처리된 파일을 다시 제출해야 합니다. **/EP**는 또한 **/FA**, **/Fa** 및 **/Fm** 옵션으로부터의 출력 파일을 억제합니다. 자세한 내용은 [/FA, /Fa (목록 파일)](fa-fa-listing-file.md)와 [/Fm(맵 파일 이름)](fm-name-mapfile.md)을 참조합니다.

이후 단계 중에 생성된 오류 정보는 원래 원본 파일보다는 전처리된 파일의 줄 번호를 참조합니다. 줄 번호가 원래 원본 파일에 대해 참조하게 하려는 경우 [/E(stdout으로 전처리)](e-preprocess-to-stdout.md)를 대신 사용합니다. **/E** 옵션은 이 목적을 위해 `#line` 지시문을 출력에 추가합니다.

`#line` 지시문을 사용하여 전처리된 출력을 파일에 보내려면 [/P (파일로 전처리)](p-preprocess-to-a-file.md) 옵션을 대신 사용합니다.

`#line` 지시문을 사용하여 전처리된 출력을 stdout으로 보내려면 **/P**와 **/EP**를 함께 사용합니다.

미리 컴파일된 헤더에는 **/EP** 옵션을 사용할 수 없습니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **C/C++** 폴더를 클릭합니다.

1. **전처리기** 속성 페이지를 클릭합니다.

1. **전처리 파일 생성** 속성을 수정합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>을 참조하세요.

## <a name="example"></a>예제

다음 명령줄을 실행 하면 `ADD.C`, 주석, 유지 및 표준 출력 장치에서 결과 표시 합니다.

```
CL /EP /C ADD.C
```

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
