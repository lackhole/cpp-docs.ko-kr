---
title: /Qspectre
ms.date: 10/12/2018
f1_keywords:
- /Qspectre
helpviewer_keywords:
- /Qspectre
ms.openlocfilehash: e0d3af50015b77af297cbee22f439cd17d803de9
ms.sourcegitcommit: 6cf0c67acce633b07ff31b56cebd5de3218fd733
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2019
ms.locfileid: "67344159"
---
# <a name="qspectre"></a>/Qspectre

특정 스펙터 변형 1 보안 취약성을 완화하기 위한 컴파일러 생성 지침을 지정합니다.

## <a name="syntax"></a>구문

> **/Qspectre**

## <a name="remarks"></a>설명

**/Qspectre** 옵션은 Visual Studio 2017 버전 15.5.5 이상, 그리고 [KB 4338871](https://support.microsoft.com/help/4338871/visual-studio-2015-update-3-spectre-variant-1-toolset-qspectre)을 통해 Visual Studio 2015 Update 3에서 사용할 수 있습니다. 이 옵션을 사용하면 컴파일러가 특정 [스펙터 보안 취약성](https://spectreattack.com/spectre.pdf)을 완화하는 지침을 삽입합니다. 이러한 취약점 이라고 *투기적 실행 사이드 채널 공격*합니다. 많은 운영 체제 및 Intel, AMD 및 ARM 프로세서를 포함 하 여 최신 프로세서에 영향을 합니다.

**/Qspectre** 옵션은 기본적으로 해제되어 있습니다.

초기 릴리스에서는 **/Qspectre** 옵션이 최적화된 코드에만 작동했습니다. Visual Studio 2017 버전 15.7 이상에서는 **/Qspectre** 옵션이 모든 최적화 수준에서 지원됩니다.

Microsoft Visual C++ 라이브러리도 스펙터 완화를 사용하는 버전에서 사용할 수 있습니다. Visual Studio 2017 이상의 스펙터 완화 라이브러리는 Visual Studio 설치 관리자에서 다운로드할 수 있습니다. 발견 될 합니다 **개별 구성 요소** 탭 **컴파일러, 빌드 도구 및 런타임**, 이름에 "라이브러리에 대 한 스펙터"를 포함 하 고 있습니다. 완화가 적용된 DLL 및 정적 런타임 라이브러리는 C++ 런타임의 하위 집합인 VC++ 시작 코드, vcruntime140, msvcp140, concrt140 및 vcamp140에 사용할 수 있습니다. Dll 응용 프로그램 지역 배포만 지원 됩니다. 시각적 개체의 내용을 C++ 2017 이상 런타임 라이브러리 재배포 가능 하지 않은 수정 되었습니다.

MFC 및 ATL. 라이브러리 스펙터 완화를 설치할 수도 있습니다. 발견 될 합니다 **개별 구성 요소** 탭에서 **Sdk, 라이브러리 및 프레임 워크**합니다.

### <a name="applicability"></a>적용 가능성

트러스트 경계를 교차 하는 데이터에서 작동 하는 코드를 사용 하는 것이 좋습니다 경우는 **/Qspectre** 다시 빌드하고 다시 가능한 한 빨리이 문제를 완화 하기 위해 코드를 배포 하는 옵션입니다. 이러한 코드 예가 실행에 영향을 줄 수 있는 신뢰할 수 없는 입력을 로드 하는 코드입니다. 예를 들어, 원격 프로시저는 코드를 호출 신뢰할 수 없는 입력 또는 파일을 구문 분석 하거나 다른 로컬 프로세스 간 통신 (IPC) 인터페이스를 사용 합니다. 표준 샌드박싱 기술로 충분하지 않을 수 있습니다. 코드는 트러스트 경계를 벗어나지 않습니다 결정 하기 전에 신중 하 게 여 샌드박스를 조사 합니다.

### <a name="availability"></a>가용성

합니다 **/Qspectre** 옵션은 Visual Studio 2017 버전 15.5.5, 및 microsoft 업데이트를 모두 사용할 수 있습니다 C++ 컴파일러 (MSVC)은 2018 년 1 월 23 일 후에 변경 합니다. Visual Studio 설치 관리자를 사용하여 컴파일러를 업데이트하고, 스펙터 완화 라이브러리를 개별 구성 요소로 설치하세요. **/Qspectre** 옵션은 패치를 통해 Visual Studio 2015 업데이트 3에서도 제공됩니다. 자세한 내용은 [KB 4338871](https://support.microsoft.com/help/4338871)을 참조하세요.

Visual Studio 2017 버전 15.5 및 모든 미리 보기의 Visual Studio 2017 버전 15.6의 모든 버전. 문서화 되지 않은 옵션을 포함할 **/d2guardspecload**합니다. 초기 동작에 해당 하는 것 **/Qspectre**합니다. 이러한 컴파일러 버전에서 **/d2guardspecload** 옵션을 사용하여 코드에 동일한 완화를 적용할 수 있습니다. 사용 하 여 빌드를 업데이트 하는 것이 좋습니다 **/Qspectre** 컴파일러 옵션을 지원 합니다. 합니다 **/Qspectre** 컴파일러의 이후 버전에서 새 완화 옵션을 지원할 수도 있습니다.

### <a name="effect"></a>효과

**/Qspectre** 옵션은 스펙터 변형 1, 경계 검사 우회를 완화하는 [CVE 2017-5753](https://nvd.nist.gov/vuln/detail/CVE-2017-5753) 코드를 출력합니다. 이 코드는 추측 코드 실행의 장벽 역할을 하는 지침을 삽입하는 방식으로 작동합니다. 프로세서 추측을 완화하기 위해 사용되는 지침은 프로세서 및 해당 마이크로 아키텍처에 따라 결정되며, 향후 컴파일러 버전에서 변경될 수 있습니다.

사용 하도록 설정한 경우 합니다 **/Qspectre** 옵션, 컴파일러가 투기적 실행 범위 검사를 무시 될 수 있는 인스턴스를 식별 하려고 시도 합니다. 장벽 지침 삽입 위치입니다. Variant 1의 인스턴스를 식별 하는 컴파일러 작업을 수행할 수 있는 분석이 제한을 알아두어야 하는 것이 반드시 합니다. 따라서 보장이 없습니다에서 variant 1의 모든 가능한 인스턴스는 계측 되지 않은 **/Qspectre**합니다.

### <a name="performance-impact"></a>성능에 미치는 영향

성능에 미치는 **/Qspectre** 여러 많은 코드 베이스에서 무시할 수를 표시 합니다. 그러나 보장은 없습니다 아래 코드의 성능에 주는 **/Qspectre** 그대로 유지 됩니다. 코드를 벤치마크하여 이 옵션이 성능에 미치는 영향을 확인해야 합니다. 사용 하 여 완화를 선택적으로 해제할 수 완화는 성능이 중요 한 블록 또는 루프에서는 필요 하지 않습니다는 알고 있는 경우는 [__declspec(spectre(nomitigation))](../../cpp/spectre.md) 지시문입니다. 이 지시문만 지 원하는 컴파일러에서 사용할 수 없는 합니다 **/d2guardspecload** 옵션입니다.

### <a name="required-libraries"></a>필요한 라이브러리

합니다 **/Qspectre** 컴파일러 옵션 스펙터 완화를 제공 하도록 빌드된 런타임 라이브러리의 버전을 암시적으로 연결 하는 코드를 생성 합니다. 다음 라이브러리는 Visual Studio 설치 관리자를 사용하여 설치해야 하는 선택적 구성 요소입니다.

- \[(x86 및 x64) | (ARM) | (ARM64)]를 위한 MSVC 버전 *version_numbers* 스펙터용 라이브러리
- 스펙터 완화를 사용하는 \[(x86/x64) | ARM | ARM64]용 Visual C++ ATL
- 스펙터 완화를 사용하는 \[(x86/x64) | ARM | ARM64]용 Visual C++ MFC

사용 하 여 코드를 작성 하는 경우 **/Qspectre** 와 같은 이러한 라이브러리에 나타나지 않으며 설치, 빌드 시스템 보고서 **MSB8038 경고: 스펙터 완화가 사용하도록 설정되어 있지만 스펙터 완화된 라이브러리를 찾을 수 없습니다** 오류를 보고합니다. MFC 또는 ATL 코드를 작성 하려면 실패 하 고 링커와 같은 오류를 보고 하는 경우 **심각한 오류 LNK1104: 'oldnames.lib' 파일을 열 수 없습니다.** , 이러한 누락 된 라이브러리를 일으킬 수 있습니다.

### <a name="additional-information"></a>추가 정보

자세한 내용은 참조는 공식 [투기적 실행 사이드 채널 취약성을 완화 하기 위해 Microsoft 보안 공지 ADV180002, 지침](https://portal.msrc.microsoft.com/en-US/security-guidance/advisory/ADV180002)합니다. 지침은 Intel의 [예측 실행 부채널 완화](https://software.intel.com/sites/default/files/managed/c5/63/336996-Speculative-Execution-Side-Channel-Mitigations.pdf) 및 ARM의 [캐시 예측 부채널](https://developer.arm.com/-/media/Files/pdf/Cache_Speculation_Side-channels.pdf)에서도 확인할 수 있습니다. 스펙터와 멜트다운 완화 기능이 Windows 관련 개요를 참조 하세요 [스펙터와 멜트다운 완화 Windows 시스템 성능에 영향을 이해](https://www.microsoft.com/security/blog/2018/01/09/understanding-the-performance-impact-of-spectre-and-meltdown-mitigations-on-windows-systems/)합니다. 스펙터에서 다루는 취약점을 MSVC 완화의 개요를 보려면 [MSVC에 스펙터 완화](https://devblogs.microsoft.com/cppblog/spectre-mitigations-in-msvc./) 에 C++ 팀 블로그.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** > **C/C++**  > **명령줄** 속성 페이지를 선택합니다.

1. **추가 옵션** 상자에 **/Qspectre** 컴파일러 옵션을 입력합니다. **확인**을 선택하여 변경 내용을 적용합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[/Q 옵션(하위 수준 작업)](q-options-low-level-operations.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
