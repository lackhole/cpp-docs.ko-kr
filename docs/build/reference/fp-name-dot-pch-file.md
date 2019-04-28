---
title: /Fp(.PCH 파일 이름 지정)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.PrecompiledHeaderFile
- /fp
- VC.Project.VCCLWCECompilerTool.PrecompiledHeaderFile
helpviewer_keywords:
- Fp compiler option [C++]
- -Fp compiler option [C++]
- naming precompiler header files
- PCH files, naming
- names [C++], PCH
- .pch files, naming
- precompiled header files, naming
- /Fp compiler option [C++]
ms.assetid: 0fcd9cbd-e09f-44d3-9715-b41efb5d0be2
ms.openlocfilehash: 95506e17dff47e51cb7a3d83b629880f63422d26
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62270994"
---
# <a name="fp-name-pch-file"></a>/Fp(.PCH 파일 이름 지정)

기본 경로 이름을 사용 하는 대신 미리 컴파일된 헤더에 대 한 경로 이름을 제공 합니다.

## <a name="syntax"></a>구문

> **/Fp**<em>pathname</em>

## <a name="remarks"></a>설명

이 옵션을 사용 하 여 [/Yc (미리 컴파일된 헤더 파일 만들기)](yc-create-precompiled-header-file.md) 하거나 [/Yu (미리 컴파일된 헤더 파일 사용)](yu-use-precompiled-header-file.md) 기본 경로 이름을 사용 하는 대신 미리 컴파일된 헤더에 대 한 경로 이름을 제공 합니다. 사용할 수도 있습니다 **/Fp** 사용 하 여 **/Yc** 다르게 미리 컴파일된 헤더 파일의 사용을 지정 하는 **/Yc**<em>filename</em> 인수 및 소스 파일의 기본 이름입니다.

경로 이름의 일부로 확장을 지정 하지 않으면 경우는 확장명을.pch로 간주 됩니다. 파일 이름 없이 디렉터리를 지정 하는 경우 기본 파일 이름은 VC*x*0.pch, 여기서 *x* 사용 하 여 Visual C++의 주 버전입니다.

사용할 수도 있습니다는 **/Fp** 옵션을 **/Yu**합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **C/C++** 폴더를 클릭합니다.

1. 클릭 합니다 **미리 컴파일된 헤더** 속성 페이지.

1. 수정 된 **미리 컴파일된 헤더 파일** 속성입니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderFile%2A>을 참조하세요.

## <a name="example"></a>예제

프로그램의 디버깅 버전에 대 한 미리 컴파일된 헤더 파일을 만들려면 하려는 헤더 파일 및 소스 코드를 컴파일하는 경우와 같은 명령을 지정할 수 있습니다.

```
CL /DDEBUG /Zi /Yc /FpDPROG.PCH PROG.CPP
```

## <a name="example"></a>예제

다음 명령을 MYPCH.pch 라는 미리 컴파일된 헤더 파일을 사용 하도록 지정 합니다. 컴파일러는 PROG.cpp에서 소스 코드를 통해 MYAPP.h 미리 컴파일된 되었습니다 및 MYPCH.pch에 미리 컴파일된 코드를 가정 합니다. MYPCH.pch의 콘텐츠를 사용 하 고.obj 파일을 만들려면 PROG.cpp의 나머지 부분을 컴파일합니다. 이 예제의 출력은 PROG.exe 라는 파일.

```
CL /YuMYAPP.H /FpMYPCH.PCH PROG.CPP
```

## <a name="see-also"></a>참고자료

[출력 파일(/F) 옵션](output-file-f-options.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
[경로 이름 지정](specifying-the-pathname.md)
