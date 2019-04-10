---
title: /Z7, /Zi, /ZI(디버깅 정보 형식)
ms.date: 04/08/2019
f1_keywords:
- VC.Project.VCCLCompilerTool.DebugInformationFormat
- /ZI
- /Zi
- /Z7
- VC.Project.VCCLWCECompilerTool.DebugInformationFormat
helpviewer_keywords:
- C7 compatible compiler option [C++]
- Debug Information Format compiler option
- ZI compiler option
- -Zi compiler option [C++]
- /ZI compiler option [C++]
- Z7 compiler option [C++]
- debugging [C++], debug information files
- Zi compiler option [C++]
- /Zi compiler option [C++]
- program database compiler option [C++]
- full symbolic debugging information
- /Z7 compiler option [C++]
- line numbers only compiler option [C++]
- cl.exe compiler, debugging options
- -Z7 compiler option [C++]
ms.openlocfilehash: e809c7af7465cde98db11eac8628b76d04f7e8b5
ms.sourcegitcommit: 39debf8c525c3951af6913ee5e514617658f8859
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59424081"
---
# <a name="z7-zi-zi-debug-information-format"></a>/Z7, /Zi, /ZI(디버깅 정보 형식)

프로그램 및 개체 파일 또는 프로그램 데이터베이스 (PDB) 파일에서이 정보는 유지 하는 여부에 대해 생성 하는 디버깅 정보의 형식을 지정 합니다.

## <a name="syntax"></a>구문

> **/Z**{**7**|**i**|**I**}

## <a name="remarks"></a>설명

코드를 컴파일 및 디버그 모드에서 작성 하는 경우 컴파일러는 함수 및 변수, 형식 정보를 디버거 사용에 대 한 줄 번호 위치에 대 한 기호 이름을 생성 합니다. 이 기호 디버깅 정보를 컴파일러에 의해 생성 된 개체 파일 (.obj 파일) 또는 실행 파일에 대 한 별도 PDB 파일 (.pdb 파일) 중 하나에 포함할 수 있습니다.  디버그 정보 형식 옵션은 다음 섹션에 설명 되어 있습니다.

### <a name="none"></a>없음

기본적으로 없는 디버그 정보 형식 옵션을 지정 하는 경우 컴파일러가 디버깅 정보를 생성 하지 않으므로 컴파일 속도가 빨라집니다.

### <a name="z7"></a>/Z7

합니다 **/z7** 옵션은 또한 디버거를 사용 하 여 사용에 대 한 전체 기호 디버깅 정보를 포함 하는 개체 파일을 생성 합니다. 이러한 개체 파일 및 빌드된 실행 파일이 없는 디버깅 정보가 있는 파일 보다 훨씬 클 수 있습니다. 기호 디버깅 정보에는 변수의 이름과 형식, 함수 및 줄 번호가 들어 있습니다. PDB 파일이 없는 생성 됩니다.

타사 라이브러리의 디버그 버전의 배포자의 경우이 점으로 손꼽을 PDB 파일을 사용할 필요가 있습니다. 그러나 미리 컴파일된 헤더에 대 한 개체 파일은 라이브러리 링크 단계에서는 및 디버깅을 위해 필요 합니다. 있으면.pch 개체 파일에 정보 (및 코드 없음)을 입력만 사용 해야 합니다 [/Yl (PCH 참조 삽입 디버그 라이브러리에 대 한)](yl-inject-pch-reference-for-debug-library.md) 라이브러리를 빌드할 때 기본적으로 사용 되는 옵션입니다.

사용 되지 않는 [/Gm (최소 다시 빌드 사용)](gm-enable-minimal-rebuild.md) 때 옵션이 제공 되지 않습니다 **/z7** 지정 됩니다.

### <a name="zi"></a>/ZI

합니다 **/Zi** 옵션은 모든 기호 디버깅 정보 사용에 대 한 디버거를 사용 하 여 포함 된 별도 PDB 파일을 생성 합니다. 디버깅 정보가 개체 파일에 포함 되지 않습니다 또는 실행 파일을 사용 하면 훨씬 더 작기 때문입니다.

이용 **/Zi** 최적화에 영향을 주지 않습니다. 그러나 **/Zi** 뜻하지는 **디버그**; 참조 [/DEBUG (디버그 정보 생성)](debug-generate-debug-info.md) 자세한 내용은 합니다.

둘 다를 지정 하는 경우 **/Zi** 하 고 **/clr**는 <xref:System.Diagnostics.DebuggableAttribute> 특성은 어셈블리 메타 데이터에 저장 되지 않습니다. 이 작업을 하려는 경우 소스 코드에서 지정 해야 합니다. 이 특성은 응용 프로그램의 런타임 성능에 영향을 줄 수 있습니다. 방법에 대 한 자세한 내용은 **Debuggable** 특성을 성능 및 성능에 미치는 영향을 수정할 수 있습니다, 참조 [디버그 이미지 쉽게 만들기](/dotnet/framework/debug-trace-profile/making-an-image-easier-to-debug)합니다.

컴파일러는 PDB 파일의 이름이 *프로젝트*.pdb. 프로젝트 외부에서 파일을 컴파일하는 경우 컴파일러가 VC 라는 PDB 파일을 만듭니다*x*.pdb 위치 *x* 사용 중인 컴파일러 버전의 주 및 부 버전 번호의 연결 됩니다. 컴파일러는 디버거 기호 및 줄 번호 정보의 위치를 가리키도록 하는이 옵션을 사용 하 여 만든 각 개체 파일의 이름 PDB 및 식별 된 타임 스탬프가 지정 된 시그니처를 포함 합니다. 이름 및 PDB 파일에 서명 디버거에서 로드할 기호에 대 한 실행 파일을 일치 해야 합니다. WinDBG 디버거를 사용 하 여 일치 하지 않는 기호를 로드할 수는 `.symopt+0x40` 명령입니다. Visual Studio에는 일치 하지 않는 기호를 로드 하려면 이와 비슷한 옵션이 없습니다.

사용 하 여 컴파일된 개체에서 라이브러리를 만드는 경우 **/Zi**, 라이브러리가 프로그램에 연결 된 경우 연관 된.pdb 파일을 사용할 수 있어야 합니다. 따라서 라이브러리를 배포 하는 경우 PDB 파일을 배포 해야 합니다. PDB 파일을 사용 하지 않고 디버깅 정보가 포함 된 라이브러리를 만들려면 선택 해야 합니다 **/z7** 옵션입니다. 미리 컴파일된 헤더 옵션을 사용 하는 경우 PDB 파일에 배치 됩니다 미리 컴파일된 헤더와 소스 코드의 나머지 부분에 대 한 정보를 디버깅 합니다.

### <a name="zi"></a>/ZI

**/ZI** 옵션은 비슷합니다 **/Zi**를 지 원하는 형식에 PDB 파일을 생성 하지만 합니다 [편집 하며 계속 하기](/visualstudio/debugger/edit-and-continue-visual-cpp) 기능입니다. 편집 하며 계속 하기 디버깅 기능을 사용 하려면이 옵션을 사용 해야 합니다. 편집 하며 계속 하기 기능을 개발자 생산성에 유용 하지만 코드 크기, 성능 및 컴파일러 규칙에서 문제가 발생할 수 있습니다. 사용 하 여 대부분의 최적화 편집 하며 계속 하기와 호환 되지 않으므로 **/ZI** 하나를 사용 하지 않도록 설정 `#pragma optimize` 코드의 문입니다. 합니다 **/ZI** 옵션은 또한 사용 하 여 호환 합니다 [ &#95; &#95;줄&#95; &#95; 미리 정의 된 매크로](../../preprocessor/predefined-macros.md);로 컴파일된 코드 **/ZI** 를사용할수없습니다 **&#95; &#95;줄&#95; &#95;** 비형식 템플릿 인수로 있지만 **&#95; &#95;줄&#95; &#95;** 매크로 확장에서 사용할 수 있습니다.

**/ZI** 옵션을 모두 사용 하면 합니다 [/Gy (함수 수준 링크 사용)](gy-enable-function-level-linking.md) 하 고 [/FC (전체 경로의 소스 코드 파일에서 진단)](fc-full-path-of-source-code-file-in-diagnostics.md) 컴파일에 사용할 옵션을 합니다.

**/ZI** 와 호환 되지 [/clr (공용 언어 런타임 컴파일)](clr-common-language-runtime-compilation.md)합니다.

> [!NOTE]
> 합니다 **/ZI** 옵션은 x86 및 x64 프로세서를 대상으로 한 컴파일러에서 사용할 수 있습니다만;이 컴파일러 옵션은 ARM 프로세서를 대상으로 한 컴파일러에서 사용할 수 없습니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 C++ 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 엽니다는 **구성 속성** > **C /C++** > **일반** 속성 페이지.

1. 수정 된 **디버그 정보 형식** 속성입니다. **확인**을 선택하여 변경 내용을 저장합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DebugInformationFormat%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)

