---
title: /Qspectre
ms.date: 10/12/2018
f1_keywords:
- /Qspectre
helpviewer_keywords:
- /Qspectre
ms.openlocfilehash: e44416a44a9f772c17bc734d26c62ff87be775c8
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837412"
---
# <a name="qspectre"></a>/Qspectre

특정 스펙터 변형 1 보안 취약성을 완화하기 위한 컴파일러 생성 지침을 지정합니다.

## <a name="syntax"></a>구문

> **/Qspectre**

## <a name="remarks"></a>주의

**/Qspectre** 옵션은 Visual Studio 2017 버전 15.5.5 이상, 그리고 [KB 4338871](https://support.microsoft.com/help/4338871/visual-studio-2015-update-3-spectre-variant-1-toolset-qspectre)을 통해 Visual Studio 2015 Update 3에서 사용할 수 있습니다. 이 옵션을 사용하면 컴파일러가 특정 [스펙터 보안 취약성](https://spectreattack.com/spectre.pdf)을 완화하는 지침을 삽입합니다. *예측 실행 부채널 공격*이라고 하는 이러한 취약성은 Intel, AMD, ARM 프로세서를 포함하여 여러 운영 체제와 최신 프로세서에 영향을 줍니다.

**/Qspectre** 옵션은 기본적으로 해제되어 있습니다.

초기 릴리스에서는 **/Qspectre** 옵션이 최적화된 코드에만 작동했습니다. Visual Studio 2017 버전 15.7 이상에서는 **/Qspectre** 옵션이 모든 최적화 수준에서 지원됩니다.

Microsoft Visual C++ 라이브러리도 스펙터 완화를 사용하는 버전에서 사용할 수 있습니다. Visual Studio 2017 이상의 스펙터 완화 라이브러리는 Visual Studio 설치 관리자에서 다운로드할 수 있습니다. **컴파일러, 빌드 도구 및 런타임** 아래의 **개별 구성 요소** 탭에서 찾을 수 있으며, "Libs for Spectre"라는 이름을 사용합니다. 완화가 적용된 DLL 및 정적 런타임 라이브러리는 C++ 런타임의 하위 집합인 VC++ 시작 코드, vcruntime140, msvcp140, concrt140 및 vcamp140에 사용할 수 있습니다. Dll은 애플리케이션-로컬 배포만 지원합니다. C++ 2017 이상 런타임 라이브러리 재배포 가능 패키지의 콘텐츠는 수정되지 않았습니다. **SDK, 라이브러리 및 프레임워크**의 **개별 구성 요소** 탭에서 찾을 수 있는 MFC 및 ATL용 스펙터 완화 라이브러리를 설치할 수도 있습니다.

### <a name="applicability"></a>적용 가능성

코드가 트러스트 경계를 넘나드는 데이터에서 작동하는 경우 최대한 신속하게 **/Qspectre** 옵션을 사용하여 이 이슈를 완화하도록 코드를 다시 빌드하고 재배포하는 것이 좋습니다. 트러스트 경계를 넘나드는 데이터에서 작동하는 코드의 예로는 원격 프로시저를 호출하거나, 신뢰할 수 없는 입력 또는 파일을 구문 분석하거나, 다른 로컬 IPC(프로세스 간 통신) 인터페이스를 사용하는 코드처럼 실행에 영향을 줄 수 있는 신뢰할 수 없는 입력을 로드하는 코드를 들 수 있습니다. 표준 샌드박싱 기술로 충분하지 않을 수 있습니다. 코드가 트러스트 경계를 넘나들지 않는지 확인하기 전에 샌드박스를 신중하게 조사해야 합니다.

### <a name="availability"></a>가용성

**/Qspectre** 옵션은 Visual Studio 2017 버전 15.5.5 및 2018년 1월 23일 이후에 업데이트된 모든 Microsoft MSVC 컴파일러(MSVC)에서 사용할 수 있습니다. Visual Studio 설치 관리자를 사용하여 컴파일러를 업데이트하고, 스펙터 완화 라이브러리를 개별 구성 요소로 설치하세요. **/Qspectre** 옵션은 패치를 통해 Visual Studio 2015 업데이트 3에서도 제공됩니다. 자세한 내용은 [KB 4338871](https://support.microsoft.com/help/4338871)을 참조하세요.

모든 Visual Studio 2017 버전 및 모든 15.5 및 모든 Visual Studio 2017 버전 15.6 미리 보기에는 문서화되지 않은 **/d2guardspecload** 옵션이 포함되어 있으며, 이 옵션은 **/Qspectre**의 초기 동작과 동일합니다. 이러한 컴파일러 버전에서 **/d2guardspecload** 옵션을 사용하여 코드에 동일한 완화를 적용할 수 있습니다. 이 옵션을 지원하는 컴파일러에서 **/Qspectre**를 사용하도록 빌드를 업데이트하세요. **/Qspectre** 옵션은 이후에 출시되는 컴파일러 버전에서 새 완화를 지원할 수도 있습니다.

### <a name="effect"></a>효과

**/Qspectre** 옵션은 스펙터 변형 1, 경계 검사 우회를 완화하는 [CVE 2017-5753](https://nvd.nist.gov/vuln/detail/CVE-2017-5753) 코드를 출력합니다. 이 코드는 추측 코드 실행의 장벽 역할을 하는 지침을 삽입하는 방식으로 작동합니다. 프로세서 추측을 완화하기 위해 사용되는 지침은 프로세서 및 해당 마이크로 아키텍처에 따라 결정되며, 향후 컴파일러 버전에서 변경될 수 있습니다.

**/Qspectre** 옵션을 사용하면 컴파일러는 추측 실행에서 경계 검사를 우회하는 인스턴스를 식별하여 장벽 지침을 삽입하려고 시도합니다. 컴파일러가 변형 1의 인스턴스를 식별하기 위해 수행할 수 있는 분석에는 제한이 있습니다. 따라서 변형 1의 모든 인스턴스가 **/Qspectre** 아래에서 계측된다는 보장이 없습니다.

### <a name="performance-impact"></a>성능에 미치는 영향

여러 거대한 코드 베이스에서는 **/Qspectre**가 성능에 미치는 영향을 무시해도 되는 수준이지만, **/Qspectre** 하에서 코드 성능이 그대로 유지된다는 보장은 없습니다. 코드를 벤치마크하여 이 옵션이 성능에 미치는 영향을 확인해야 합니다. 성능이 중요한 블록 또는 루프에서 완화가 필요 없다는 것을 알고 있는 경우 [__declspec(spectre(nomitigation))](../../cpp/spectre.md) 지시문을 사용하여 완화를 선별적으로 해제할 수 있습니다. **/d2guardspecload** 옵션만 지원하는 컴파일러에서는 이 지시문을 사용할 수 없습니다.

### <a name="required-libraries"></a>필요한 라이브러리

**/Qspectre** 컴파일러 옵션은 스펙터 완화를 제공하기 위해 빌드된 런타임 라이브러리 버전을 암시적으로 연결하는 코드를 생성합니다. 다음 라이브러리는 Visual Studio 설치 관리자를 사용하여 설치해야 하는 선택적 구성 요소입니다.

- \[(x86 및 x64) | (ARM) | (ARM64)]를 위한 MSVC 버전 *version_numbers* 스펙터용 라이브러리
- 스펙터 완화를 사용하는 \[(x86/x64) | ARM | ARM64]용 Visual C++ ATL
- 스펙터 완화를 사용하는 \[(x86/x64) | ARM | ARM64]용 Visual C++ MFC

**/Qspectre**를 사용하여 코드를 빌드하는데 이러한 라이브러리가 설치되지 않은 경우 빌드 시스템에서 **경고 MSB8038: 스펙터 완화가 사용하도록 설정되어 있지만 스펙터 완화된 라이브러리를 찾을 수 없습니다** 오류를 보고합니다. MFC 또는 ATL 코드가 빌드에 실패하고 링커가 **치명적인 오류 LNK1104: 'oldnames.lib' 파일을 열 수 없습니다** 같은 오류를 보고하는 경우 이러한 라이브러리가 누락된 것이 원인일 수 있습니다.

### <a name="additional-information"></a>추가 정보

자세한 내용은 공식 [Microsoft Security Advisory ADV180002, 예측 실행 부채널 취약성을 완화하기 위한 지침](https://portal.msrc.microsoft.com/en-US/security-guidance/advisory/ADV180002)을 참조하세요. 지침은 Intel의 [예측 실행 부채널 완화](https://software.intel.com/sites/default/files/managed/c5/63/336996-Speculative-Execution-Side-Channel-Mitigations.pdf) 및 ARM의 [캐시 예측 부채널](https://developer.arm.com/-/media/Files/pdf/Cache_Speculation_Side-channels.pdf)에서도 확인할 수 있습니다. Windows의 스펙터 및 멜트다운 완화에 대한 개념은 Microsoft 보안 블로그에서 [스펙터와 멜트다운 완화가 Windows 시스템 성능에 미치는 영향의 이해](https://cloudblogs.microsoft.com/microsoftsecure/2018/01/09/understanding-the-performance-impact-of-spectre-and-meltdown-mitigations-on-windows-systems/)를 참조하세요. MSVC 완화를 통해 해결되는 스펙터 취약성의 개요는 Visual C++ 팀 블로그의 [MSVC의 스펙터 완화](https://blogs.msdn.microsoft.com/vcblog/2018/01/15/spectre-mitigations-in-msvc./)를 참조하세요.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조하세요.

1. **구성 속성** > **C/C++** > **명령줄** 속성 페이지를 선택합니다.

1. **추가 옵션** 상자에 **/Qspectre** 컴파일러 옵션을 입력합니다. **확인**을 선택하여 변경 내용을 적용합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고 항목

[/Q 옵션(하위 수준 작업)](q-options-low-level-operations.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
