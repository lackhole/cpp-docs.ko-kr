---
title: /I (추가 포함 디렉터리)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.AdditionalIncludeDirectories
- VC.Project.VCCLCompilerTool.AdditionalIncludeDirectories
- /I
- VC.Project.VCNMakeTool.IncludeSearchPath
helpviewer_keywords:
- /I compiler option [C++]
- Additional Include Directories compiler option
- I compiler option [C++]
- -I compiler option [C++]
- set include directories
- include directories, compiler option [C++]
ms.assetid: 3e9add2a-5ed8-4d15-ad79-5b411e313a49
ms.openlocfilehash: 6ec8b15e77fec5214013c484e617904ed29e8197
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62270144"
---
# <a name="i-additional-include-directories"></a>/I (추가 포함 디렉터리)

포함 파일을 검색할 디렉터리 목록에 디렉터리를 추가 합니다.

## <a name="syntax"></a>구문

> **/I**[ ]*directory*

### <a name="arguments"></a>인수

*directory*<br/>
디렉터리 목록에 추가할 디렉터리는 include 파일 검색 합니다.

## <a name="remarks"></a>설명

둘 이상의 디렉터리를 추가 하려면이 옵션을 두 번 이상 사용 합니다. 지정된 된 include 파일을 찾을 때까지만 디렉터리가 검색 됩니다.

이 옵션을 사용할 수는 ([/X (표준 포함 경로 무시)](x-ignore-standard-include-paths.md)) 옵션입니다.

컴파일러는 다음 순서 대로 디렉터리를 검색합니다.

1. 사용 하 여 지정 된 [#include 지시문](../../preprocessor/hash-include-directive-c-cpp.md) 큰따옴표 형태로 먼저 로컬 디렉터리를 검색 합니다. 포함 된 파일과 동일한 디렉터리에서 검색을 시작 합니다 **#include** 문입니다. 검색 파일을 찾을 실패 하면 현재 열려의 디렉터리는 열린 반대 순서로 파일을 포함 합니다. 검색은 부모 include 파일의 디렉터리에서 시작하여 위쪽의 상위 부모 include 파일 디렉터리로 진행됩니다.

1. 사용 하 여 지정 하는 경우는 **#include** 각도 지시문 폼, 대괄호 또는 로컬 디렉터리 검색에 실패를 사용 하 여 지정 된 디렉터리를 검색 합니다 **/I** CL에서 하는 순서 대로 옵션을 명령을 입력 하십시오.

1. 에 지정 된 디렉터리를 **INCLUDE** 환경 변수입니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. 선택 된 **구성 속성** > **C/C++** > **일반** 속성 페이지.

1. 수정 된 **Additional Include Directories** 속성입니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalIncludeDirectories%2A>을 참조하세요.

## <a name="example"></a>예제

다음 명령은 다음과 같은 순서로 MAIN.c 요청한 포함 파일을 찾습니다. 첫째, 큰따옴표를 사용 하 여 지정 된, 로컬 파일 검색 됩니다. 다음으로, 검색 \INCLUDE 디렉터리에서 다음 \MY\INCLUDE 디렉터리에서 계속 되며 마지막 디렉터리에서 INCLUDE 환경 변수에 할당 됩니다.

```
CL /I \INCLUDE /I\MY\INCLUDE MAIN.C
```

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
