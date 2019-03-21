---
title: /X(표준 포함 경로 무시)
ms.date: 11/04/2016
f1_keywords:
- /x
- VC.Project.VCCLCompilerTool.OVERWRITEStandardIncludePath
- VC.Project.VCCLWCECompilerTool.OVERWRITEStandardIncludePath
helpviewer_keywords:
- /X compiler option [C++]
- include files, ignore standard path
- -X compiler option [C++]
- include directories, ignore standard
- X compiler option
- Ignore Standard Include Paths compiler option
ms.assetid: 16bdf2cc-c8dc-46e4-bdcc-f3caeba5e1ef
ms.openlocfilehash: dba7e49880307002a3dee983264e93666adfef17
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57818403"
---
# <a name="x-ignore-standard-include-paths"></a>/X(표준 포함 경로 무시)

컴파일러를 PATH 및 INCLUDE 환경 변수에 지정 된 디렉터리에서 포함 파일을 검색할 수 없습니다.

## <a name="syntax"></a>구문

```
/X
```

## <a name="remarks"></a>설명

이 옵션을 사용할 수는 [/I (추가 포함 디렉터리)](i-additional-include-directories.md) (**/I**`directory`) 옵션입니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. **C/C++** 폴더를 클릭합니다.

1. 클릭 합니다 **전처리기** 속성 페이지.

1. 수정 된 **표준 포함 경로 무시** 속성입니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.IgnoreStandardIncludePath%2A>을 참조하세요.

## <a name="example"></a>예제

다음 명령에서 `/X` PATH 및 INCLUDE 환경 변수에서 지정한 위치를 무시 하도록 컴파일러에 지시 하 고 `/I` 를 검색할 디렉터리를 지정 합니다. 포함 파일:

```
CL /X /I \ALT\INCLUDE MAIN.C
```

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
