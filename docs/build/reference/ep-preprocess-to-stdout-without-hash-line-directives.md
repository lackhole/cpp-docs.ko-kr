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
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57807340"
---
# <a name="ep-preprocess-to-stdout-without-line-directives"></a>/EP(#line 지시문 없이 stdout로 전처리)

C 및 c + + 소스 파일을 전처리 하 고 표준 출력 장치에 전처리 된 파일을 복사 합니다.

## <a name="syntax"></a>구문

```
/EP
```

## <a name="remarks"></a>설명

프로세스에서 모든 전처리기 지시문이 실행 됩니다 하 고 매크로 확장을 수행 하는 주석이 제거 됩니다. 전처리 된 출력에서 메모를 유지 하려면 사용 합니다 [(유지 전처리 중에 주석)는 /C](c-preserve-comments-during-preprocessing.md) 옵션을 **/EP**.

합니다 **/EP** 옵션은 컴파일을 억제 합니다. 컴파일에 대 한 전처리 된 파일을 다시 제출 해야 합니다. **/EP** 출력 파일을 표시 하지 합니다 **/FA**를 **/Fa**, 및 **/Fm** 옵션입니다. 자세한 내용은 [/FA, /Fa (목록 파일)](fa-fa-listing-file.md) 하 고 [/Fm (맵 파일 이름)](fm-name-mapfile.md)합니다.

오류 처리의 이후 단계 중에 생성 된 원래 원본 파일 보다는 전처리 된 파일의 줄 번호를 참조 하십시오. 줄 번호를 원래 소스 파일에 참조를 하려는 경우 사용할 [/E (stdout으로 전처리)](e-preprocess-to-stdout.md) 대신 합니다. 합니다 **/E** 옵션은 추가 `#line` 지시문이이 목적을 위해 출력을 합니다.

전처리 된 출력을 사용 하 여 보낼 `#line` 지시문을 파일에 사용 합니다 [/P (파일로 전처리)](p-preprocess-to-a-file.md) 옵션을 사용 합니다.

사용 하 여 stdout으로 전처리 된 출력을 보내도록 `#line` 지시문을 사용 하 여 **/P** 하 고 **/EP** 함께 합니다.

미리 컴파일된 헤더를 사용할 수 없습니다는 **/EP** 옵션입니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. **C/C++** 폴더를 클릭합니다.

1. 클릭 합니다 **전처리기** 속성 페이지.

1. 수정 된 **전처리 파일 생성** 속성입니다.

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
