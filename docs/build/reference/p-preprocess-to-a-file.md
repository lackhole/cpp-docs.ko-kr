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
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57813762"
---
# <a name="p-preprocess-to-a-file"></a>/P(파일 전처리)

C 및 c + + 소스 파일을 전처리 하 고 전처리 된 출력 파일을 씁니다.

## <a name="syntax"></a>구문

```
/P
```

## <a name="remarks"></a>설명

파일 이름이 같은 기본 소스 파일 및.i 확장 합니다. 프로세스에서 모든 전처리기 지시문이 실행 됩니다 하 고 매크로 확장을 수행 하는 주석이 제거 됩니다. 전처리 된 출력에서 메모를 유지 하려면 사용 합니다 [(유지 전처리 중에 주석)는 /C](c-preserve-comments-during-preprocessing.md) 옵션과 함께 **/P**.

**/ P** 추가 `#line` 시작과 끝에 조건부 컴파일 용 전처리기 지시문에 의해 제거 된 줄 그리고 포함된 된 파일의 출력에 대 한 지시문입니다. 이러한 지시어는 전처리 된 파일의 줄 번호 다시 매기기입니다. 결과적으로, 오류 처리의 이후 단계 중에 생성 된 전처리 된 파일의 줄이 아니라 원래 소스 파일의 줄 번호를 참조 하십시오. 생성 하지 않으려면 `#line` 지시문을 사용 하 여 [/EP (#line 지시문 없이 stdout로 전처리)](ep-preprocess-to-stdout-without-hash-line-directives.md) 뿐만 **/P**합니다.

합니다 **/P** 옵션은 컴파일을 억제 합니다. 사용 하는 경우에.obj 파일을 생성 되지 않습니다 [/Fo (개체 파일 이름)](fo-object-file-name.md)합니다. 컴파일에 대 한 전처리 된 파일을 다시 제출 해야 합니다. **/ P** 출력 파일을 표시 하지 합니다 **/FA**를 **/Fa**, 및 **/Fm** 옵션입니다. 자세한 내용은 [/FA, /Fa (목록 파일)](fa-fa-listing-file.md) 하 고 [/Fm (맵 파일 이름)](fm-name-mapfile.md)합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. **C/C++** 폴더를 클릭합니다.

1. 클릭 합니다 **전처리기** 속성 페이지.

1. 수정 된 **전처리 파일 생성** 속성입니다.

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
