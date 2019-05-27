---
title: /LTCG(링크 타임 코드 생성)
ms.date: 05/16/2019
f1_keywords:
- VC.Project.VCLinkerTool.LinkTimeCodeGeneration
- VC.Project.VCConfiguration.WholeProgramOptimization
- VC.Project.VCCLWCECompilerTool.WholeProgramOptimization
- /ltcg
- VC.Project.VCCLCompilerTool.WholeProgramOptimization
helpviewer_keywords:
- link-time code generation in C++ linker
- /LTCG linker option
- -LTCG linker option
- LTCG linker option
ms.assetid: 788c6f52-fdb8-40c2-90af-4026ea2cf2e2
ms.openlocfilehash: a8f13c32593d1cfef690d63d506faf14490de02d
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837262"
---
# <a name="ltcg-link-time-code-generation"></a>/LTCG(링크 타임 코드 생성)

**/LTCG**를 사용하여 전체 프로그램 최적화를 수행하거나, PGO(프로필 기반 최적화) 계측을 만들고 학습을 수행하며 프로필 기반으로 최적화된 빌드를 만듭니다.

## <a name="syntax"></a>구문

> **/LTCG**[ **:** {**INCREMENTAL**|**NOSTATUS**|**STATUS**|**OFF**}]<br/>

이 옵션은 Visual Studio 2015부터 더 이상 사용되지 않습니다.

> **/LTCG:** {**PGINSTRUMENT**|**PGOPTIMIZE**|**PGUPDATE**}<br/>

### <a name="arguments"></a>인수

**INCREMENTAL**<br/>
(선택 사항) 링커가 전체 프로젝트 대신 편집의 영향을 받는 파일 집합에만 전체 프로그램 최적화 또는 LTCG(링크 타임 코드 생성)를 적용하도록 지정합니다. 기본적으로 이 플래그는 **/LTCG**를 지정했을 때 설정되지 않으며, 전체 프로젝트가 전체 프로그램 최적화를 통해 연결됩니다.

**NOSTATUS** &#124; **STATUS**<br/>
(선택 사항) 완료된 링크 비율을 표시하는 진행률 표시기가 링커에 표시되는지 여부를 지정합니다. 기본적으로 이 상태 정보는 표시되지 않습니다.

**OFF**<br/>
(선택 사항) 링크 시간 코드 생성을 사용하지 않습니다. 이 동작은 명령줄에서 **/LTCG**를 지정하지 않은 경우와 동일합니다.

**PGINSTRUMENT**<br/>
(선택 사항) 이 옵션은 Visual Studio 2015부터 더 이상 사용되지 않습니다. 대신 **/LTCG** 및 [/GENPROFILE 또는 /FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)을 사용하여 프로필 기반 최적화에 대해 계측된 빌드를 생성합니다. 계측된 실행으로부터 수집되는 데이터는 최적화된 이미지를 만드는 데 사용됩니다. 자세한 내용은 [프로필 기반 최적화](../profile-guided-optimizations.md)를 참조하세요. 이 옵션의 약식 표현은 **/LTCG:PGI**입니다.

**PGOPTIMIZE**<br/>
(선택 사항) 이 옵션은 Visual Studio 2015부터 더 이상 사용되지 않습니다. 대신 **/LTCG** 및 [/USEPROFILE](useprofile.md)을 사용하여 최적화된 이미지를 빌드합니다. 자세한 내용은 [프로필 기반 최적화](../profile-guided-optimizations.md)를 참조하세요. 이 옵션의 약식 표현은 **/LTCG:PGO**입니다.

**PGUPDATE**<br/>
(선택 사항) 이 옵션은 Visual Studio 2015부터 더 이상 사용되지 않습니다. 대신 **/LTCG** 및 **/USEPROFILE**을 사용하여 최적화된 이미지를 다시 빌드합니다. 자세한 내용은 [프로필 기반 최적화](../profile-guided-optimizations.md)를 참조하세요. 이 옵션의 약식 표현은 **/LTCG:PGU**입니다.

## <a name="remarks"></a>주의

**/LTCG** 옵션은 링커가 컴파일러를 호출하고 전체 프로그램 최적화를 수행하도록 지정합니다. 프로필 기반 최적화를 수행할 수도 있습니다. 자세한 내용은 [프로필 기반 최적화](../profile-guided-optimizations.md)를 참조하세요.

다음과 같은 경우를 제외하고 **/LTCG** 및 **/GENPROFILE** 옵션의 이전 PGO 초기화 조합에 지정되지 않은 **/LTCG** 및 **/USEPROFILE**의 PGO 조합에 링커 옵션을 추가할 수 없습니다.

- [/BASE](base-base-address.md)

- [/FIXED](fixed-fixed-base-address.md)

- **/LTCG**

- [/MAP](map-generate-mapfile.md)

- [/MAPINFO](mapinfo-include-information-in-mapfile.md)

- [/NOLOGO](nologo-suppress-startup-banner-linker.md)

- [/OUT](out-output-file-name.md)

- [/PGD](pgd-specify-database-for-profile-guided-optimizations.md)

- [/PDB](pdb-use-program-database.md)

- [/PDBSTRIPPED](pdbstripped-strip-private-symbols.md)

- [/STUB](stub-ms-dos-stub-file-name.md)

- [/VERBOSE](verbose-print-progress-messages.md)

PGO를 초기화하기 위해 **/LTCG** 및 **/GENPROFILE** 옵션과 함께 지정된 링커 옵션은 암시적으로 지정되므로 **/LTCG** 및 **/USEPROFILE**을 사용하여 빌드할 때 지정할 필요가 없습니다.

이 문서의 나머지 부분에서는 링크-시간 코드 생성의 관점에서 **/LTCG**에 대해 설명합니다.

**/LTCG**는 [/GL](gl-whole-program-optimization.md)을 통한 암시적 작업입니다.

**/GL** 또는 MSIL 모듈을 사용해서 컴파일된 모듈이 전달된 경우에는 링커가 링크-시간 코드 생성을 호출합니다(링커 입력으로 [.netmodule 파일 참조](netmodule-files-as-linker-input.md)). **/GL** 또는 MSIL 모듈을 링커에 전달할 때 **/LTCG**를 명시적으로 지정하지 않으면 링커에서 결국 이 상태가 감지되고 **/LTCG**를 사용해서 링크를 다시 시작합니다. 가능한 가장 빠른 빌드 성능을 위해서는 **/GL** 및 MSIL 모듈을 링커에 전달할 때 **/LTCG**를 명시적으로 지정합니다.

더 빠른 성능을 내려면 **/LTCG:INCREMENTAL**을 사용합니다. 이 옵션은 전체 프로젝트 대신 소스 파일 변경의 영향을 받는 파일 집합만 다시 최적화하도록 링커에 지시합니다. 이렇게 하면 필요한 링크 타임을 상당히 줄일 수 있습니다. 증분 연결과 동일한 옵션이 아닙니다.

**/LTCG** 는 [/INCREMENTAL](incremental-link-incrementally.md)를 참조하세요.

[/Og](og-global-optimizations.md), [/O1](o1-o2-minimize-size-maximize-speed.md), [/O2](o1-o2-minimize-size-maximize-speed.md) 또는 [/Ox](ox-full-optimization.md)를 사용해서 컴파일된 모듈을 링크하도록 **/LTCG**가 사용된 경우 다음 최적화가 수행됩니다.

- 모듈 간 인라인 처리

- 프로시저 간 레지스터 할당(64비트 운영 체제만 해당)

- 사용자 지정 호출 규칙(x86만 해당)

- 작은 TLS 치환(x86만 해당)

- 스택 이중 맞춤(x86만 해당)

- 향상된 메모리 명확성(전역 변수 및 입력 매개 변수에 대한 보다 효율적인 간섭 정보)

> [!NOTE]
> 링커는 각 함수를 컴파일하는 데 사용된 최적화를 확인하고 링크 타임에 동일한 최적화를 적용합니다.

**/LTCG** 및 **/Ogt**를 사용하면 이중 할당 최적화가 수행됩니다.

**/LTCG** 및 **/Ogs**가 지정된 경우에는 이중 할당이 수행되지 않습니다. 애플리케이션에서 대부분의 함수가 속도용으로 컴파일되고 크기용으로 컴파일된 함수는 일부만 있는 경우(예: [optimize](../../preprocessor/optimize.md) pragma 사용), 이중 할당이 필요한 함수를 호출하면 컴파일러가 크기용으로 최적화된 함수를 이중 할당합니다.

컴파일러가 함수의 모든 호출 사이트를 식별할 수 있는 경우 컴파일러는 함수의 명시적 호출 규칙 한정자를 무시하고 함수의 호출 규칙을 최적화하려고 합니다.

- 레지스터의 매개 변수 전달

- 맞춤을 위해 매개 변수 다시 정렬

- 사용하지 않는 매개 변수 제거

함수가 함수 포인터를 통해 호출되거나, **/GL**을 사용해서 컴파일된 모듈 외부에서 make 함수가 호출되는 경우, 컴파일러는 함수의 호출 규칙을 최적화하려고 시도하지 않습니다.

> [!NOTE]
> **/LTCG**를 사용하고 `mainCRTStartup`을 다시 정의할 경우, 애플리케이션은 글로벌 개체가 초기화되기 전에 실행되는 사용자 코드와 연관된 예측할 수 없는 동작을 포함할 수 있습니다. 이 문제를 해결하는 방법은 세 가지입니다. `mainCRTStartup`을 다시 정의하지 않거나, **/LTCG**를 사용해서 `mainCRTStartup`이 포함된 파일을 컴파일하지 않거나, 글로벌 변수 및 개체를 정적으로 초기화해야 합니다.

### <a name="ltcg-and-msil-modules"></a>/LTCG 및 MSIL 모듈

[/GL](gl-whole-program-optimization.md) 및 [/clr](clr-common-language-runtime-compilation.md) 을 사용해서 컴파일된 모듈은 **/LTCG** 가 지정된 경우 링커에 대한 입력으로 사용될 수 있습니다.

- **/LTCG**는 네이티브 개체 파일과 혼합 네이티브/관리 개체 파일( **/clr**을 사용하여 컴파일)을 수락할 수 있습니다. **/clr:pure** 및 **/clr:safe** 컴파일러 옵션은 Visual Studio 2015에서는 더 이상 사용되지 않으며 Visual Studio 2017 이상에서는 지원되지 않습니다.

- **/LTCG:PGI**는 **/GL** 및 **/clr**을 사용하여 컴파일된 네이티브 모듈을 수락하지 않습니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트 **속성 페이지** 대화 상자를 엽니다. [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조하세요.

1. **구성 속성** > **일반** 속성 페이지를 선택합니다.

1. **전체 프로그램 최적화** 속성을 수정합니다.

또한 메뉴 모음에서 **빌드** > **프로필 기반 최적화**를 선택하거나 프로젝트의 바로 가기 메뉴에서 프로필 기반 최적화 옵션 중 하나를 선택해서 특정 빌드에 **/LTCG**를 적용할 수도 있습니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LinkTimeCodeGeneration%2A>을 참조하세요.

## <a name="see-also"></a>참고 항목

- [MSVC 링커 참조](linking.md)
- [MSVC 링커 옵션](linker-options.md)
