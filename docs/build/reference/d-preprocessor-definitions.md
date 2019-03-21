---
title: /D(전처리기 정의)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCNMakeTool.PreprocessorDefinitions
- VC.Project.VCCLCompilerTool.PreprocessorDefinitions
- /d
helpviewer_keywords:
- preprocessor definition symbols
- constants, defining
- macros, compiling
- /D compiler option [C++]
- -D compiler option [C++]
- D compiler option [C++]
ms.assetid: b53fdda7-8da1-474f-8811-ba7cdcc66dba
ms.openlocfilehash: 18bbdb980c63b3c04b432602afb2402c5e2c42e7
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812085"
---
# <a name="d-preprocessor-definitions"></a>/D(전처리기 정의)

소스 파일에 대한 전처리 기호를 정의합니다.

## <a name="syntax"></a>구문

```
/Dname[= | # [{string | number}] ]
```

## <a name="remarks"></a>설명

이 기호를 `#if` 또는 `#ifdef`와 함께 사용하여 조건에 따라 소스 코드를 컴파일할 수 있습니다. 기호 정의는 코드에서 기호를 다시 정의하거나 `#undef` 지시문을 사용하여 코드에서 기호 정의를 해제할 때까지 유효합니다.

**/D** 것과 동일한 효과가 합니다 `#define` 한다는 점을 제외 하는 소스 코드 파일의 시작 부분에서 지시문 **/D** 명령줄에서 따옴표를 제거 및 `#define` 를 유지 합니다.

기호와 관련된 값은 기본적으로 1입니다. 예를 들어 **/D** `name` 동일 **/D**`name`**= 1**합니다. 이 문서에서는 정의의 끝에 예제에서 **테스트** 인쇄에 게 표시 되 `1`합니다.

사용 하 여 컴파일하면 **/D** `name` **=** 기호와 연결 된 값이 없어야 합니다. 기호를 사용해 조건에 따라 코드를 컴파일할 수 있지만 그렇지 않은 경우 기호가 어떤 값으로도 계산되지 않습니다. 예제를 사용 하 여 컴파일하는 경우 **/DTEST =**, 오류가 발생 합니다. 이 동작은 값을 사용하거나 사용하지 않을 때에도 `#define`을 사용할 때의 동작과 비슷합니다.

이 명령은 TEST.c에서 DEBUG 기호를 정의합니다.

**CL /DDEBUG  TEST.C**

이 명령은 TEST.c에 있는 모든 `__far` 키워드를 제거합니다.

**CL /D__far=  TEST.C**

합니다 **CL** 등호 기호를 포함 하는 문자열에 환경 변수를 설정할 수 없습니다. 사용 하도록 **/D** 함께 합니다 **CL** 환경 변수를 지정 해야 등호 대신 숫자 기호:

```
SET CL=/DTEST#0
```

명령 프롬프트에서 전처리 기호를 정의하면 컴파일러 구문 분석 규칙과 셸 구문 분석 규칙을 모두 수행하는 것이 좋습니다. 예를 들어, 백분율 기호 전처리 기호 (%)을 정의 하려면 프로그램에 두 개의 백분율 기호 문자 (%)를 지정 합니다. 명령 프롬프트: 하나만 지정 하면 구문 분석 오류가 내보내집니다.

```
CL /DTEST=%% TEST.C
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 설정 C++ 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 왼쪽된 창에서 선택 **구성 속성**, **C/C++** 하십시오 **전처리기**합니다.

1. 오른쪽 열에 있는 오른쪽 창에는 **전처리기 정의** 속성을 드롭다운 메뉴를 열고 선택 **편집**합니다.

1. 에 **전처리기 정의** 대화 상자 (줄에 하나씩)를 추가, 수정 또는 하나 이상의 정의 삭제 합니다. **확인**을 선택하여 변경 내용을 저장합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PreprocessorDefinitions%2A>을 참조하세요.

## <a name="example"></a>예제

```
// cpp_D_compiler_option.cpp
// compile with: /DTEST
#include <stdio.h>

int main( )
{
    #ifdef TEST
        printf_s("TEST defined %d\n", TEST);
    #else
        printf_s("TEST not defined\n");
    #endif
}
```

```Output
TEST defined 1
```

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
[/U, /u(기호 정의 해제)](u-u-undefine-symbols.md)<br/>
[#undef 지시문(C/C++)](../../preprocessor/hash-undef-directive-c-cpp.md)<br/>
[#define 지시문(C/C++)](../../preprocessor/hash-define-directive-c-cpp.md)
