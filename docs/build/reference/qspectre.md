---
title: /Qspectre
ms.date: 10/12/2018
f1_keywords:
- /Qspectre
helpviewer_keywords:
- /Qspectre
ms.openlocfilehash: 42adff6564dc1c2ef47abffe9f9e6e630279ea7d
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812462"
---
# <a name="qspectre"></a>/Qspectre

특정 Spectre variant 1 보안 취약성을 완화 하기 위한 지침의 컴파일러 생성을 지정 합니다.

## <a name="syntax"></a>구문

> **/Qspectre**

## <a name="remarks"></a>설명

합니다 **/Qspectre** 옵션은 Visual Studio 2017 버전 15.5.5에서에서 사용할 수 있는 이상 및 Visual Studio 2015 업데이트 3- [KB 4338871](https://support.microsoft.com/help/4338871/visual-studio-2015-update-3-spectre-variant-1-toolset-qspectre)합니다. 컴파일러가 특정 완화 하는 지침을 삽입할 [스펙터 보안 취약점으로 인 한](https://spectreattack.com/spectre.pdf)합니다. 호출에 이러한 취약성 *투기적 실행 사이드 채널 공격*많은 운영 체제 및 Intel, AMD 프로세서를 포함 하 여 최신 프로세서에 영향을 줄 고 ARM입니다.

합니다 **/Qspectre** 옵션은 기본적으로 해제 되어 있습니다.

초기 릴리스에서는 **/Qspectre** 최적화 된 코드에만 작동 하는 옵션입니다. Visual Studio 2017 버전 15.7 이상의 경우에 **/Qspectre** 옵션은 모든 최적화 수준에서 지원 됩니다.

Microsoft Visual c + + 라이브러리 스펙터 완화를 사용 하 여 버전에서 사용할 수 있습니다. Visual Studio 설치 관리자에서 Visual Studio 2017에 대 한 스펙터 완화 라이브러리를 다운로드할 수 있습니다. 있는 합니다 **개별 구성 요소** 탭 **컴파일러, 빌드 도구 및 런타임**, 이름에 "라이브러리에 대 한 스펙터"를 포함 하 고 있습니다. DLL 및 정적 런타임 라이브러리 사용 하도록 설정 하는 완화를 사용 하 여 모두 Visual c + + 런타임의 하위 집합에 제공 됩니다. VC + + 시작 코드, vcruntime140, msvcp140, concrt140, 및 vcamp140 합니다. Dll 응용 프로그램 지역 배포만 지원 됩니다. Visual c + + 2017 런타임 라이브러리 재배포 가능 패키지의 내용은 수정 되지 않은 합니다. MFC 및 ATL에 대 한 스펙터 완화 라이브러리를 설치할 수도 있습니다는 **개별 구성 요소** 탭에서 **Sdk, 라이브러리 및 프레임 워크**합니다.

### <a name="applicability"></a>적용 대상

트러스트 경계를 교차 하는 데이터에서 작동 하는 코드를 사용 하는 것이 좋습니다 경우는 **/Qspectre** 다시 빌드하고 다시 가능한 한 빨리이 문제를 완화 하기 위해 코드를 배포 하는 옵션입니다. 트러스트 경계를 교차 하는 데이터에서 작동 하는 코드의 예로 실행에 영향을 줄 수 있는 신뢰할 수 없는 입력을 로드 하는 코드, 원격 프로시저는 코드를 호출, 신뢰할 수 없는 입력 또는 파일을 구문 분석 또는 다른 로컬 간 프로세스를 사용 하 여 예를 들어, 통신 (IPC) 인터페이스입니다. 표준 샌드 박싱 기술 충분 하지 않을 수 있습니다. 에 샌드박스 코드 트러스트 경계를 넘어서지 않는 결정 하기 전에 신중 하 게 조사 해야 합니다.

### <a name="availability"></a>가용성

합니다 **/Qspectre** 옵션은 2018 년 1 월 23 일 이후에 만든 모든 업데이트가 Microsoft MSVC 컴파일러 (MSVC) Visual Studio 2017 버전 15.5.5에 사용할 수 있습니다. Visual Studio 설치 관리자를 사용 하 여 컴파일러를 업데이트 하 고 개별 구성 요소로 스펙터 완화 라이브러리를 설치 합니다. 합니다 **/Qspectre** 옵션 패치를 통해 Visual Studio 2015 업데이트 3에서 제공 됩니다. 자세한 내용은 [KB 4338871](https://support.microsoft.com/help/4338871)합니다.

모든 버전의 Visual Studio 2017 버전 15.5 및 모든 미리 보기의 Visual Studio 2017 버전 15.6 문서화 되지 않은 옵션이 **/d2guardspecload**에 초기 동작에는 해당 **/Qspectre**. 사용할 수 있습니다 **/d2guardspecload** 이러한 버전의 컴파일러에서 코드를 동일한 완화를 적용 합니다. 사용 하 여 빌드를 업데이트 하세요 **/Qspectre** ; 옵션을 지 원하는 컴파일러에서는 **/Qspectre** 컴파일러의 이후 버전에서 새 완화 옵션을 지원할 수도 있습니다.

### <a name="effect"></a>효과

합니다 **/Qspectre** 맴도 변형 1 범위 확인 바이패스를 완화 하기 위해 코드를 출력 하는 옵션 [CVE 2017-5753](https://nvd.nist.gov/vuln/detail/CVE-2017-5753)합니다. 잘못 된 코드 실행 장벽으로 작동 하는 명령 삽입 하 여 작동 합니다. 프로세서 추론을 완화 하기 위해 사용 되는 특정 지침에는 변경 될 수 있습니다 이후 버전의 컴파일러 및 프로세서 및 해당 마이크로 아키텍처에 따라 달라 집니다.

경우는 **/Qspectre** 옵션을 설정 하면 컴파일러가 투기적 실행 범위 검사를 건너뛸 수 있습니다 및 장벽 지침 삽입 위치 인스턴스를 식별 하려고 합니다. 컴파일러는 variant 1의 인스턴스를 식별 하기 위해 수행할 수 있는 분석이 제한은 두는 것이 반드시 합니다. 따라서 보장이 없습니다에서 variant 1의 모든 가능한 인스턴스는 계측 되지 않은 **/Qspectre**합니다.

### <a name="performance-impact"></a>성능에 미치는 영향

성능에 미치는 **/Qspectre** 몇 가지 매우 큰 코드 베이스에서 무시할 수 나타났습니다 보장을 아래 코드의 성능에 주는 없습니다 있지만 **/Qspectre** 그대로 유지 됩니다. 성능 옵션의 효과 확인 하는 코드 벤치 마크 해야 합니다. 사용 하 여 완화를 선택적으로 사용할 수는 성능이 중요 한 블록 또는 루프에서 필요 하지 않습니다를 알고 있는 경우는 [__declspec(spectre(nomitigation))](../../cpp/spectre.md) 지시문입니다. 이 지시문에서에서 사용할 수 없는 지 원하는 컴파일러는 **/d2guardspecload** 옵션입니다.

### <a name="required-libraries"></a>필요한 라이브러리

합니다 **/Qspectre** 컴파일러 옵션 스펙터 완화를 위해 구축 된 런타임 라이브러리의 버전을 암시적으로 연결 하는 코드를 생성 합니다. 이러한 라이브러리는 Visual Studio 설치 관리자를 사용 하 여 설치 해야 하는 선택적 구성 요소:

- VC + + 2017 버전 *version_numbers* 스펙터 용 라이브러리 \[(x86 및 x64) | (ARM) | (ARM64)]
- 에 대 한 visual c + + ATL \[(x64 x86) | ARM | ARM64] 스펙터 완화를 사용 하 여
- 에 대 한 visual c + + MFC \[x86 x64 | ARM | ARM64] 스펙터 완화를 사용 하 여

사용 하 여 코드를 작성 하는 경우 **/Qspectre** 없는 이러한 라이브러리를 설치 하 고 빌드 시스템 보고서 **MSB8038 경고: 스펙터 완화 설정 되어 있지만 스펙터 완화 된 라이브러리를 찾을 수 없는**합니다. MFC 또는 ATL 코드 빌드가 실패 하 고 링커와 같은 오류를 보고 하는 경우 **심각한 오류 LNK1104: 'oldnames.lib' 파일을 열 수 없습니다.**, 이러한 누락 된 라이브러리를 일으킬 수 있습니다.

### <a name="additional-information"></a>추가 정보

자세한 내용을 참조 하세요. 공식 [투기적 실행 사이드 채널 취약성을 완화 하기 위해 Microsoft 보안 공지 ADV180002, 지침](https://portal.msrc.microsoft.com/en-US/security-guidance/advisory/ADV180002)합니다. 지침 Intel에서 제공 됩니다 [투기적 실행 쪽 채널 완화](https://software.intel.com/sites/default/files/managed/c5/63/336996-Speculative-Execution-Side-Channel-Mitigations.pdf), 및 ARM를 [캐시 추론 쪽 채널](https://developer.arm.com/-/media/Files/pdf/Cache_Speculation_Side-channels.pdf)합니다. 스펙터와 멜트다운 완화 기능이 Windows 관련 개요를 참조 하세요 [스펙터와 멜트다운 완화 Windows 시스템 성능에 영향을 이해](https://cloudblogs.microsoft.com/microsoftsecure/2018/01/09/understanding-the-performance-impact-of-spectre-and-meltdown-mitigations-on-windows-systems/) Microsoft 보안 블로그에서입니다. MSVC 완화에서 해결 된 스펙터 취약점의 개요를 보려면 [MSVC에 스펙터 완화](https://blogs.msdn.microsoft.com/vcblog/2018/01/15/spectre-mitigations-in-msvc./) Visual c + + 팀 블로그.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **C/c + +** > **명령줄** 속성 페이지.

1. 입력 된 **/Qspectre** 컴파일러 옵션을 **추가 옵션** 상자. 선택할 **확인** 에 변경 내용을 적용 합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[/Q 옵션(하위 수준 작업)](q-options-low-level-operations.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
