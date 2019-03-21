---
title: /LTCG(링크 타임 코드 생성)
ms.date: 03/14/2018
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
ms.openlocfilehash: 40fb591952180735de3a2c226a3953a303c7d90f
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57810317"
---
# <a name="ltcg-link-time-code-generation"></a>/LTCG(링크 타임 코드 생성)

사용 하 여 **/LTCG** 전체 프로그램 최적화를 수행 하려면 또는 (PGO) 프로필 기반 최적화 계측, 훈련을 수행 만들고 프로필 기반에 빌드를 최적화 합니다.

## <a name="syntax"></a>구문

> **/LTCG**[**:**{**INCREMENTAL**|**NOSTATUS**|**STATUS**|**OFF**}]<br/>

이러한 옵션은 Visual Studio 2015부터 사용 되지 않음:

> **/LTCG:**{**PGINSTRUMENT**|**PGOPTIMIZE**|**PGUPDATE**}<br/>

### <a name="arguments"></a>인수

**INCREMENTAL**<br/>
(선택 사항) 링커가 전체 프로젝트 대신 편집의 영향을 받는 파일 집합에 전체 프로그램 최적화 또는 링크 타임 코드 생성 (LTCG)를만 적용 되도록 지정 합니다. 기본적으로이 플래그는 설정 하지 시기 **/LTCG** 를 지정 하면 전체 프로그램 최적화를 사용 하 여 전체 프로젝트가 연결 되 고 합니다.

**NOSTATUS** &AMP;#124; **상태**<br/>
(선택 사항) 완료 된 링크 비율을 표시 하는 진행률 표시기가 링커에 표시 여부를 지정 합니다. 기본적으로 이 상태 정보는 표시되지 않습니다.

**OFF**<br/>
(선택 사항) 링크 타임 코드 생성을 사용 하지 않도록 설정 합니다. 이 동작은 경우와 동일 **/LTCG** 명령줄에서 지정 하지 않으면.

**PGINSTRUMENT**<br/>
(선택 사항) 이 옵션은 Visual Studio 2015부터 사용 되지 않습니다. 대신 **/LTCG** 하 고 [/GENPROFILE 또는 /FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) 프로필 기반 최적화 계측된 된 빌드를 생성 합니다. 계측된 실행으로부터 수집되는 데이터는 최적화된 이미지를 만드는 데 사용됩니다. 자세한 내용은 [프로필 기반 최적화](../profile-guided-optimizations.md)합니다. 이 옵션의 약식 표현은 **/ltcg: pgi**합니다.

**PGOPTIMIZE**<br/>
(선택 사항) 이 옵션은 Visual Studio 2015부터 사용 되지 않습니다. 대신 **/LTCG** 하 고 [/USEPROFILE](useprofile.md) 최적화 된 이미지를 빌드합니다. 자세한 내용은 [프로필 기반 최적화](../profile-guided-optimizations.md)합니다. 이 옵션의 약식 표현은 **함수가 /ltcg: pgo**합니다.

**PGUPDATE**<br/>
(선택 사항) 이 옵션은 Visual Studio 2015부터 사용 되지 않습니다. 대신 **/LTCG** 하 고 **/USEPROFILE** 최적화 된 이미지를 다시 작성 해야 합니다. 자세한 내용은 [프로필 기반 최적화](../profile-guided-optimizations.md)합니다. 이 옵션의 약식 표현은 **/LTCG:PGU**합니다.

## <a name="remarks"></a>설명

합니다 **/LTCG** 옵션은 링커가 컴파일러를 호출 하 고 전체 프로그램 최적화를 수행 합니다. 프로필 기반 최적화를 수행할 수도 있습니다. 자세한 내용은 [프로필 기반 최적화](../profile-guided-optimizations.md)합니다.

다음과 같은 예외가 PGO 조합에 링커 옵션을 추가할 수 없습니다 **/LTCG** 하 고 **/USEPROFILE** 의 이전 PGO 초기화 조합에 지정 되지 않았습니다  **/LTCG** 하 고 **/GENPROFILE** 옵션:

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

와 함께 지정 된 링커 옵션을 **/LTCG** 하 고 **/GENPROFILE** PGO를 초기화 하는 옵션을 사용 하 여 작성 하는 경우를 지정 하지 않아도 **/LTCG** 및 **/USEPROFILE**;은 암시적입니다.

이 문서의 나머지 부분에 대해 설명 **/LTCG** 링크 타임 코드 생성 기준으로 합니다.

**/LTCG** 사용 하 여 암시적 [/GL](gl-whole-program-optimization.md)합니다.

링커를 사용 하 여 컴파일된 모듈이 전달 된 경우 링크 타임 코드 생성을 호출 **/GL** 또는 MSIL 모듈 (참조 [링커 입력으로.netmodule 파일](netmodule-files-as-linker-input.md)). 명시적으로 지정 하지 않는 경우 **/LTCG** 전달 하는 경우 **/GL** MSIL 모듈을 링커에 링커에서 결국이 검색 하 고 사용 하 여 링크를 다시 시작 하거나 **/LTCG**합니다. 명시적으로 지정할 **/LTCG** 전달 하는 경우 **/GL** 및 MSIL 모듈을 링커에 가능한 가장 빠른 빌드 성능을 합니다.

사용 하 여 성능을 더욱 향상 시키려면 **/LTCG: 증분**합니다. 이 옵션은 전체 프로젝트 대신 소스 파일 변경의 영향을 받는 파일 집합만 다시 최적화하도록 링커에 지시합니다. 이렇게 하면 필요한 링크 타임을 상당히 줄일 수 있습니다. 증분 링크와 동일한 옵션이 아닙니다.

**/LTCG** 는 [/INCREMENTAL](incremental-link-incrementally.md)를 참조하세요.

때 **/LTCG** 사용해 서 컴파일된 모듈에 연결 하는 데 사용 됩니다 [/Og](og-global-optimizations.md)합니다 [/o1](o1-o2-minimize-size-maximize-speed.md)를 [/o2](o1-o2-minimize-size-maximize-speed.md), 또는 [/Ox](ox-full-optimization.md), 다음 최적화가 수행 됩니다.

- 모듈 간 인라인 처리

- 프로시저 간 레지스터 할당(64비트 운영 체제만 해당)

- 사용자 지정 호출 규칙(x86만 해당)

- 작은 TLS 치환(x86만 해당)

- 스택 이중 맞춤(x86만 해당)

- 향상된 메모리 명확성(전역 변수 및 입력 매개 변수에 대한 보다 효율적인 간섭 정보)

> [!NOTE]
> 링커는 각 함수를 컴파일하는 데 사용된 최적화를 확인하고 링크 타임에 동일한 최적화를 적용합니다.

사용 하 여 **/LTCG** 하 고 **/Ogt** 하면 이중 할당 최적화 합니다.

하는 경우 **/LTCG** 하 고 **/Ogs** 이중 할당이 수행 되지 않습니다 지정 됩니다. 크기에 대 한 일부 함수를 사용 하 여 속도 대 한 대부분의 응용 프로그램에서 함수는 컴파일한 (사용 하 여 예를 들어 합니다 [최적화](../../preprocessor/optimize.md) pragma), 컴파일러가 이중 맞춤 호출 하는 경우 크기에 대 한 최적화 된 함수 이중 할당이 필요한 함수입니다.

컴파일러가 함수의 모든 호출 사이트를 식별할 수 있는 경우 컴파일러는 함수의 명시적 호출 규칙 한정자를 무시하고 함수의 호출 규칙을 최적화하려고 합니다.

- 레지스터의 매개 변수 전달

- 맞춤을 위해 매개 변수 다시 정렬

- 사용하지 않는 매개 변수 제거

함수 포인터를 통해 함수를 호출 하거나 함수를 사용해 서 컴파일된 모듈 외부에서 호출 하는 경우 **/GL**, 컴파일러는 함수의 호출 규칙을 최적화 하려고 시도 하지 않습니다.

> [!NOTE]
> 사용 하는 경우 **/LTCG** 재정의 및 `mainCRTStartup`, 응용 프로그램 전역 개체가 초기화 되기 전에 실행 되는 사용자 코드에 연결 하는 예기치 않은 동작이 있을 수 있습니다. 이 문제를 해결 하는 방법은 세 가지가 있습니다: 다시 정의 하지 `mainCRTStartup`, 포함 된 파일을 컴파일되지 않습니다 `mainCRTStartup` 를 사용 하 여 **/LTCG**, 또는 전역 변수 및 개체를 정적으로 초기화 합니다.

### <a name="ltcg-and-msil-modules"></a>/LTCG 및 MSIL 모듈

[/GL](gl-whole-program-optimization.md) 및 [/clr](clr-common-language-runtime-compilation.md) 을 사용해서 컴파일된 모듈은 **/LTCG** 가 지정된 경우 링커에 대한 입력으로 사용될 수 있습니다.

- **/LTCG** 네이티브 개체 파일을 받아들이고 혼합 네이티브/관리 개체 파일 (사용 하 여 컴파일된 **/clr**). **/clr: pure** 및 **/clr: safe** Visual Studio 2015에서 사용 되지 않고 Visual Studio 2017에서 지원 되지 않는 컴파일러 옵션입니다.

- **/Ltcg: pgi** 사용해 서 컴파일된 네이티브 모듈을 사용할 수 없습니다 **/GL** 고 **/clr**

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트 **속성 페이지** 대화 상자를 엽니다. 참조 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **일반** 속성 페이지.

1. **전체 프로그램 최적화** 속성을 수정합니다.

적용할 수도 있습니다 **/LTCG** 을 선택 하 여 특정 빌드 **빌드** > **프로필 기반 최적화** 프로필 중 하나를 선택 하거나 메뉴 모음에서 프로젝트에 대 한 바로 가기 메뉴에서 최적화 옵션을 안내 합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LinkTimeCodeGeneration%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

- [MSVC 링커 참조](linking.md)
- [MSVC 링커 옵션](linker-options.md)
