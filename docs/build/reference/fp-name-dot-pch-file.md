---
title: /Fp (이름 &period;pch 파일)
description: /Fp 컴파일러 옵션을 사용 하 여 미리 컴파일된 헤더 파일 이름을 지정 합니다.
ms.date: 05/31/2019
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
ms.openlocfilehash: 6e7faa934d14acb5d129173c5e0c7ee67d6caf2b
ms.sourcegitcommit: 540fa2f5015de1adfa7b6bf823f6eb4ed5a6a4bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2019
ms.locfileid: "66460879"
---
# <a name="fp-name-periodpch-file"></a>/Fp (이름 &period;pch 파일)

기본 경로 이름을 사용하는 대신 미리 컴파일된 헤더의 경로 이름을 제공합니다.

## <a name="syntax"></a>구문

> **/Fp**<em>pathname</em>

## <a name="remarks"></a>설명

사용 된 **/Fp** 옵션을 [/Yc (미리 컴파일된 헤더 파일 만들기)](yc-create-precompiled-header-file.md) 또는 [/Yu (미리 컴파일된 헤더 파일 사용)](yu-use-precompiled-header-file.md) 미리 컴파일된 헤더 (PCH) 파일 이름과 경로 지정 하려면 파일입니다. 기본적으로 **/Yc** 옵션은 소스 파일의 기본 이름을 사용 하 여 PCH 파일 이름을 만듭니다 및 *pch* 확장 합니다.

확장의 일부로 지정 하지 않으면 합니다 *pathname*의 확장인 *pch* 것으로 간주 됩니다. 디렉터리 이름에 슬래시를 사용 하 여 지정 되는 경우 ( **/** )의 끝 *pathname*, 기본 파일 이름은 vc*버전*0.pch, 여기서  *버전* 는 Visual Studio 도구 집합의 주 버전. 이 디렉터리가 존재 해야 합니다 또는 C1083 오류가 생성 됩니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. 엽니다는 **구성 속성** > **C /C++**  > **미리 컴파일된 헤더** 속성 페이지.

1. 수정 된 **미리 컴파일된 헤더 출력 파일** 속성입니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="examples"></a>예제

프로그램의 디버그 빌드에 대 한 미리 컴파일된 헤더 파일의 버전 이라는 별도 만들려면와 같은 명령을 지정할 수 있습니다.:

```CMD
CL /DDEBUG /Zi /Yc /FpDPROG.PCH PROG.CPP
```

다음 명령은 MYPCH.pch라는 미리 컴파일된 헤더 파일을 사용하도록 지정합니다. 컴파일러는 MYAPP.h, 끝날 때까지 PROG.cpp에서 소스 코드를 미리 컴파일한 MYPCH.pch에 미리 컴파일된 코드를 넣습니다. 그런 다음 MYPCH.pch의 콘텐츠를 사용 하 고.obj 파일을 만들려면 PROG.cpp의 나머지 부분을 컴파일합니다. 이 예제의 출력은 PROG.exe라는 파일입니다.

```CMD
CL /YuMYAPP.H /FpMYPCH.PCH PROG.CPP
```

## <a name="see-also"></a>참고자료

[출력 파일(/F) 옵션](output-file-f-options.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
[경로 이름 지정](specifying-the-pathname.md)
