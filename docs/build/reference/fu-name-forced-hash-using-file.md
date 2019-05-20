---
title: '/FU(강제 #using 파일 이름 지정)'
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.ForcedUsingFiles
- /FU
- VC.Project.VCNMakeTool.ForcedUsingAssemblies
helpviewer_keywords:
- -FU compiler option [C++]
- FU compiler option [C++]
- /FU compiler option [C++]
ms.assetid: 698f8603-457f-435a-baff-5ac9243d6ca1
ms.openlocfilehash: c47a45208ac5b5c7e0000516ed114c008feda7ca
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62292291"
---
# <a name="fu-name-forced-using-file"></a>/FU(강제 #using 파일 이름 지정)

소스코드 안에서 [#using 지시문](../../preprocessor/hash-using-directive-cpp.md)을 이용해 파일 이름을 전달하는 방법을 대신할 수 있는 컴파일러 옵션입니다.

## <a name="syntax"></a>구문

> **/FU** *file*

## <a name="arguments"></a>인수

*file*<br/>
컴파일 과정에서 참조할 메타데이터 파일을 지정합니다.

## <a name="remarks"></a>설명

/FU 옵션은 파일 이름을 하나만을 인자로 받습니다. 여러 파일을 지정하려면 각 이름에 대해 /FU를 사용합니다.

C++ CLI를 사용하거나 [Friend 어셈블리](../../dotnet/friend-assemblies-cpp.md) 기능을 사용하기 위하여 메타데이터를 참조하는 경우 **/FU** 옵션을 사용할 수 없습니다. 코드에서 `[as friend]`특성과 함께 `#using`을 사용해서 메타데이터를 참조해야 합니다. Friend 어셈블리는 Visual C++ 구성 요소 C++/CX 확장에서는 지원되지 않습니다.

어셈블리 또는 CLR (공용 언어 런타임) 모듈을 만드는 방법에 대한 정보는 [/clr (공용 언어 런타임 컴파일)](clr-common-language-runtime-compilation.md)을 참조합니다. C++/CX에서 빌드하는 방법에 대한 내용은 [앱 및 라이브러리 빌드](../../cppcx/building-apps-and-libraries-c-cx.md)를 참조합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 설정 C++ 컴파일러 및 빌드 속성](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** > **C/C++** > **고급** 속성 페이지를 선택합니다.

1. **강제 #using** 속성을 수정합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedUsingFiles%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[출력 파일(/F) 옵션](output-file-f-options.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
