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
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57807522"
---
# <a name="fu-name-forced-using-file"></a>/FU(강제 #using 파일 이름 지정)

파일 이름을 전달 하는 대신 사용할 수 있는 컴파일러 옵션 [#using 지시문](../../preprocessor/hash-using-directive-cpp.md) 소스 코드에서입니다.

## <a name="syntax"></a>구문

> **/FU** *file*

## <a name="arguments"></a>인수

*file*<br/>
이 컴파일에서 참조 메타 데이터 파일을 지정 합니다.

## <a name="remarks"></a>설명

/FU 스위치는 파일 이름을 하나만 사용합니다. 여러 파일을 지정하려면 각 항목에 대해 /FU를 사용합니다.

사용할 C + + CLI 및 메타 데이터를 사용 하 여 참조 되는 [Friend 어셈블리](../../dotnet/friend-assemblies-cpp.md) 기능을 사용할 수 없습니다 **/FU**합니다. 
  `#using` 특성과 함께 `[as friend]`을 사용해서 코드에서 메타데이터를 참조해야 합니다. Friend 어셈블리는 Visual c + + 구성 요소 확장의 C +에서 지원 되지 않는 + CX 합니다.

어셈블리 또는 CLR (공용 언어 런타임)에 대 한 모듈을 만드는 방법에 대 한 정보를 참조 하세요 [/clr (공용 언어 런타임 컴파일)](clr-common-language-runtime-compilation.md)합니다. C + 빌드하는 방법에 대 한 자세한 + /CX를 참조 하세요 [앱 및 라이브러리 빌드](../../cppcx/building-apps-and-libraries-c-cx.md)합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **C/c + +** > **고급** 속성 페이지.

1. 수정 된 **강제 #using** 속성입니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedUsingFiles%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[출력 파일(/F) 옵션](output-file-f-options.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
