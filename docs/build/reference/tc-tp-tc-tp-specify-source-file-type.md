---
title: /Tc, /Tp, /TC, /TP(소스 파일 형식 지정)
ms.date: 1/11/2018
f1_keywords:
- VC.Project.VCCLWCECompilerTool.CompileAs
- VC.Project.VCCLCompilerTool.CompileAs
- /Tp
- /tc
helpviewer_keywords:
- Tp compiler option [C++]
- /Tc compiler option [C++]
- -Tc compiler option [C++]
- source files, specifying to compiler
- Tc compiler option [C++]
- /Tp compiler option [C++]
- -Tp compiler option [C++]
ms.openlocfilehash: f7ee51c858c9f90440cf0c2b21799ef7473cf6da
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62317447"
---
# <a name="tc-tp-tc-tp-specify-source-file-type"></a>/Tc, /Tp, /TC, /TP(소스 파일 형식 지정)

합니다 **/Tc** 옵션 filename 인수는 C 소스 파일을.c 확장 되지 않은 경우에 지정 합니다. **/Tp** 옵션 filename 인수 임을 지정는 C++ 원본 파일,.cpp 또는.cxx 확장명 없는 경우에 합니다. 옵션 및 파일 이름 사이 공백을 선택 사항입니다. 각 옵션에는 하나의 파일 지정 추가 파일을 지정 하려면 옵션을 반복 합니다.

**/TC** 하 고 **/TP** 변형이 전역 **/Tc** 하 고 **/Tp**합니다. 모든 파일을 명령줄에서 C 소스 파일을 처리 하도록 컴파일러에 지정 하는 (**/TC**) 또는 C++ 소스 파일 (**/TP**), 명령줄 옵션을 기준으로 위치에 관계 없이 합니다. 이러한 전역 옵션을 이용 하 여 단일 파일에서 재정의할 수 있습니다 **/Tc** 하거나 **/Tp**합니다.

## <a name="syntax"></a>구문

> **/Tc** _filename_
>  **/Tp** _filename_
>  **/TC**
>  **/TP**

## <a name="arguments"></a>인수

*filename*<br/>
C 또는 C++ 소스 파일입니다.

## <a name="remarks"></a>설명

기본적으로 **CL** .c 확장명을 가진 파일은 C 소스 파일을.cpp 또는.cxx 확장명을 가진 파일 가정 C++ 소스 파일입니다.

때 중 하나를 **TC** 또는 **Tc** 옵션을 지정 하면 모든 사양의 [/zc: wchar_t (wchar_t는 네이티브 형식임)](zc-wchar-t-wchar-t-is-native-type.md) 옵션이 무시 됩니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 C++ 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **C/C++** > **고급** 속성 페이지.

1. 수정 된 **컴파일** 속성입니다. 선택할 **확인** 하거나 **적용** 변경 내용을 적용 하려면.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileAs%2A>을 참조하세요.

## <a name="examples"></a>예제

이 CL 명령줄 MAIN.c, TEST.prg, 및 COLLATE.prg는 모든 C 소스 파일을 지정 합니다. CL PRINT.prg 인식 되지 않습니다.

> CL MAIN.C /TcTEST.PRG /TcCOLLATE.PRG PRINT.PRG

CL 명령줄이 TEST1.c, TEST2.cxx, TEST3.huh, 및 TEST4.o는 컴파일되도록 지정으로 C++ 파일 및 TEST5.z C 파일로 컴파일됩니다.

> CL TEST1.C TEST2.CXX TEST3.HUH TEST4.O /Tc TEST5.Z /TP

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
