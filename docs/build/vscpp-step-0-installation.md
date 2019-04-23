---
title: Visual Studio에 C++ 지원 설치
description: 시각적 개체에 대 한 Visual Studio 지원 설치C++
ms.custom: mvc
ms.date: 04/02/2019
ms.topic: tutorial
ms.devlang: cpp
ms.assetid: 45138d70-719d-42dc-90d7-1d0ca31a2f54
ms.openlocfilehash: 2c2bed4063194bdc3c0f3fbc405be6bf9a4031e7
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58870782"
---
# <a name="install-c-support-in-visual-studio"></a>Visual Studio에 C++ 지원 설치

다운로드 하 고 Visual Studio 및 시각적 개체를 설치 하지 않은 경우 C++ 도구를 아직 여기의 시작 하는 방법입니다.

::: moniker range="vs-2019"

## <a name="visual-studio-2019-installation"></a>Visual Studio 2019 Installation

시작 하려면 Visual Studio 2019! 이 버전에서 선택 하 고 필요한 기능만 설치 하기 쉽습니다. 고 감소는 최소 사용 공간도 때문이 빠르고 적은 시스템에 미치는 영향을 설치 합니다.

> [!NOTE]
> 이 항목에서는 Windows에서 Visual Studio의 설치에 적용 됩니다. [Visual Studio Code](https://code.visualstudio.com/) Windows, Mac 및 Linux 시스템에서 실행 되는 경량, 플랫폼 간 개발 환경입니다. Microsoft [C /C++ for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools) 확장 프로그램은 IntelliSense, 디버깅, 코드 서식 지정, 자동 완성을 지원 합니다. Mac 용 visual Studio에서 Microsoft를 지원 하지 않습니다 C++에.NET 언어 및 플랫폼 간 개발 지원 하지만 합니다. 설치 지침은 [Mac 용 Visual Studio 설치](/visualstudio/mac/installation/)합니다.

이 버전의 다른 새로운 기능에 대해 자세히 알고 싶으세요? Visual Studio를 참조 하세요 [릴리스](/visualstudio/releases/2019/release-notes/)합니다.

설치할 준비가 되었나요? 설치 과정을 단계별로 안내합니다.

### <a name="step-1---make-sure-your-computer-is-ready-for-visual-studio"></a>1단계 - Visual Studio에 대해 컴퓨터가 준비되었는지 확인

Visual Studio 설치를 시작하기 전에

1. [시스템 요구 사항](/visualstudio/releases/2019/system-requirements)을 확인합니다. 이러한 요구 사항을 컴퓨터에 Visual Studio 2019 지원 하는지 여부를 알 수 있습니다.

1. 최신 Windows 업데이트를 적용합니다. 이러한 업데이트는 컴퓨터에 최신 보안 업데이트와 Visual Studio에 필요한 시스템 구성 요소가 모두 설치되어 있는지 확인합니다.

1. 다시 부팅합니다. 다시 부팅하면 보류 중인 설치 또는 업데이트가 Visual Studio 설치를 방해하지 않습니다.

1. 공간을 확보합니다. 예를 들어 디스크 정리 앱을 실행하여 %SystemDrive%에서 불필요한 파일 및 애플리케이션을 제거합니다.

Visual Studio 2019를 사용 하 여 이전 버전의 Visual Studio 나란히 실행 하는 방법에 대 한 질문에 대 한 참조를 [Visual Studio 2019 플랫폼 대상 지정 및 호환성](/visualstudio/releases/2019/compatibility/) 페이지입니다.

### <a name="step-2---download-visual-studio"></a>2단계 - Visual Studio 다운로드

다음으로 Visual Studio 부트스트래퍼 파일을 다운로드합니다. 이렇게 하려면 다음 단추를 선택 하 고 선택 하려는 Visual Studio의 버전 **저장할**를 선택한 후 **폴더 열기**.

 > [!div class="button"]
 > [Visual Studio 다운로드](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019+rc)

### <a name="step-3---install-the-visual-studio-installer"></a>3단계 - Visual Studio 설치 관리자 설치

Visual Studio 설치 관리자를 설치 하려면 부트스트래퍼 파일을 실행 합니다. 이 새 경량 설치 관리자를 설치 하 고 Visual Studio 사용자 지정 하는 데 필요한 모든 포함 합니다.

1. **다운로드** 폴더에서 다음 파일 중 하나와 일치하거나 비슷한 부트스트래퍼 파일을 두 번 클릭합니다.

   * Visual Studio Community용 **vs_community.exe**
   * Visual Studio Professional용 **vs_professional.exe**
   * Visual Studio Enterprise용 **vs_enterprise.exe**

   사용자 계정 컨트롤 알림을 받으면, 선택 **예**합니다.

1. Microsoft [사용 약관](https://visualstudio.microsoft.com/license-terms/) 및 Microsoft [개인정보처리방침](https://privacy.microsoft.com/privacystatement)에 동의하도록 요청하는 메시지가 표시됩니다. 선택할 **계속**합니다.

### <a name="step-4---choose-workloads"></a>4 단계-워크 로드를 선택 합니다.

설치 관리자를 설치한 후 설치를 선택 하 여 사용자 지정에 사용할 수 있습니다 합니다 *워크 로드*, 또는 집합을 기능입니다. 방법은 다음과 같습니다.

1. **Visual Studio 설치** 화면에서 원하는 작업을 찾습니다.

   ![Visual Studio 2019: 워크 로드를 설치 합니다.](../get-started/media/vs-installer-workloads.png)

   Core에 대 한 C++ 지원을 선택 합니다 "를 사용한 데스크톱 개발 C++" 워크 로드. 20개가 넘는 언어에 대한 기본 코드 편집 기능, 프로젝트 없이도 폴더에서 코드를 열어 편집할 수 있는 기능 및 통합 소스 코드 제어 기능이 포함된 기본 핵심 편집기가 제공됩니다.

   추가 워크 로드 지원 다른 종류의 C++ 개발 합니다. 예를 들어 Microsoft Store 대 한 Windows 런타임을 사용 하는 앱을 만들려면 "유니버설 Windows 플랫폼 개발" 워크 로드를 선택 합니다. 선택 "를 사용한 게임 개발 C++" DirectX, Unreal, Cocos2d 사용 되는 게임을 만들려고 합니다. 선택 "를 사용한 Linux 개발 C++" 플랫폼을 대상으로 Linux, IoT 개발을 포함 합니다.

   합니다 **설치 세부 정보** 창 각 워크 로드에 따라 설치에 포함 및 선택적 구성 요소를 나열 합니다. 선택 하거나이 목록에 선택적 구성 요소를 선택 취소 수 있습니다. 예를 들어, Visual Studio 2017 또는 2015 컴파일러 도구 집합을 사용 하 여 개발을 지원 하려면 MSVC v141 또는 MSVC v140 선택적 구성 요소를 선택 합니다. MFC, 실험적 모듈 언어 확장, IncrediBuild 등에 대 한 지원을 추가할 수 있습니다.

1. 워크 로드와 원하는 선택적 구성 요소를 선택한 다음 선택할 **설치**합니다.

    다음으로 Visual Studio 설치 진행률을 보여 주는 상태 화면이 나타납니다.

> [!TIP]
> 설치 후에 언제든지 초기에 설치하지 않은 워크로드 또는 구성 요소를 설치할 수 있습니다. Visual Studio가 열려 있으면 **도구** > **도구 및 기능 가져오기...** 로 이동하여 Visual Studio 설치 관리자를 엽니다. 또는 [시작] 메뉴에서 **Visual Studio 설치 관리자**를 엽니다. 여기에서 워크 로드를 설치 하려는 구성 요소를 선택할 수 있습니다. 그런 다음 선택할 **수정**합니다.

## <a name="step-5---choose-individual-components-optional"></a>5 단계-개별 구성 요소 (선택 사항)를 선택 합니다.

Visual Studio 설치에 맞게 워크 로드 기능을 사용 하지 않으려는 경우 워크 로드를 설치 하는 보다 자세한 구성 요소를 추가할 수 있습니다 이렇게 하면 설치 하거나 개별 구성 요소를 추가 하 여는 **개별구성요소** 탭 합니다. 선택 내용을 지정 하 고 다음 표시 되는 메시지입니다.

  ![Visual Studio 2019-개별 구성 요소 설치](../get-started/media/vs-installer-individual-components.png "Visual Studio 설치 개별 구성 요소")

## <a name="step-6---install-language-packs-optional"></a>6단계 - 언어 팩 설치(선택 사항)

기본적으로 설치 관리자 프로그램은 처음 실행될 때 운영 체제의 언어와 일치시키려고 합니다. 선택한 언어로 Visual Studio를 설치 하려면 선택 합니다 **언어 팩** 에서 Visual Studio 설치 관리자를 탭 한 다음 지시를 따릅니다.

  ![Visual Studio 2019-언어 팩 설치](../get-started/media/vs-installer-language-packs.png "Visual Studio 설치 언어 팩")

### <a name="change-the-installer-language-from-the-command-line"></a>명령줄에서 설치 관리자 언어 변경

기본 언어를 변경할 수 있는 다른 방법은 명령줄에서 설치 관리자를 실행하는 것입니다. 예를 들어 `vs_installer.exe --locale en-US` 명령을 사용하여 설치 관리자를 영어로 강제 실행할 수 있습니다. 설치 관리자는 다음에 실행 하는 경우이 설정은 저장 됩니다. 설치 관리자는 zh-cn, zh-tw, cs-cz, en-us, es-es, fr-fr, de-de, it-it, ja-jp, ko-kr, pl-pl, pt-br, ru-ru, and tr-tr과 같은 언어 토큰을 지원합니다.

### <a name="step-7---change-the-installation-location-optional"></a>7단계 - 설치 위치 변경(선택 사항)

시스템 드라이브에 Visual Studio의 설치 공간을 줄일 수 있습니다. 다운로드 캐시, 공유 구성 요소, SDK 및 도구를 다른 드라이브로 이동하고 Visual Studio를 가장 빠르게 실행되는 드라이브에 유지하도록 선택할 수 있습니다.

  ![Visual Studio 2019-설치 위치 변경](../get-started/media/vs-installer-installation-locations.png "설치 위치 변경")

> [!IMPORTANT]
> Visual Studio를 처음 설치할 때에 다른 드라이브를 선택할 수 있습니다. 이미 설치 했으면 하 고 드라이브를 변경 하려는 경우 Visual Studio를 제거 하 고 다시 설치 해야 합니다.

## <a name="step-8---start-developing"></a>8단계 - 개발 시작

1. Visual Studio 설치를 완료 한 후 선택 합니다 **시작** 단추 Visual Studio를 사용 하 여 개발을 시작 합니다.

1. 시작 창에서 **새 프로젝트 만들기**를 선택합니다.

1. 검색 상자에서 사용 가능한 템플릿 목록을 보려면 만들려는 앱의 유형을 입력 합니다. 템플릿 목록 설치 도중에 선택한 워크 로드에 따라 달라 집니다. 다른 템플릿을 보려면 다양 한 워크 로드를 선택 합니다.

   사용 하 여 특정 프로그래밍 언어에 대 한 검색어를 필터링 할 수도 있습니다는 **언어** 드롭 다운 목록. 사용 하 여 필터링 할 수 있습니다는 **플랫폼** 목록 및 **프로젝트 형식을** 너무을 나열 합니다.

1. Visual Studio 새 프로젝트를 열고 코드 준비가!

::: moniker-end

::: moniker range="<=vs-2017"

## <a name="visual-studio-2017-installation"></a>Visual Studio 2017 Installation

Visual Studio 2017에서 선택 하 고 필요한 기능만 설치 하기 쉽습니다. 고 감소는 최소 사용 공간도 때문이 빠르고 적은 시스템에 미치는 영향을 설치 합니다.

### <a name="prerequisites"></a>전제 조건

- 광대역 인터넷 연결 합니다. Visual Studio 설치 관리자를 여러 기가바이트 단위의 데이터를 다운로드할 수 있습니다.

- Microsoft Windows 7 이상을 실행 하는 컴퓨터입니다. 최상의 개발 환경을 위해 Windows 10이 좋습니다. Visual Studio를 설치 하기 전에 시스템에 최신 업데이트가 적용 되 고 있는지 확인 합니다.

- 사용 가능한 디스크 공간이 충분 합니다. Visual Studio는 7GB 이상 디스크 공간이 필요 하 고 다양 한 일반 옵션 설치 된 경우 50GB 이상 걸릴 수 있습니다. C: 드라이브에 설치 하는 것이 좋습니다.

디스크 공간 및 운영 체제 요구 사항에 대 한 자세한 내용은 참조 하세요. [Visual Studio 제품군 시스템 요구 사항](/visualstudio/productinfo/vs2017-system-requirements-vs)합니다. 설치 관리자에서 선택한 옵션에 대 한 필요한 디스크 공간을 보고 합니다.

### <a name="download-and-install"></a>다운로드 및 설치

1. Windows에 대 한 최신 Visual Studio 2017 설치 관리자를 다운로드 합니다.

   > [!div class="nextstepaction"]
   > [Visual Studio 2017 Community 설치](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)

   >[!Tip]
   > 커뮤니티 에디션은 개인 개발자, 교실 학습, 학술 연구 및 오픈 소스 개발용입니다. 다른 용도의 경우 [Visual Studio 2017 Professional](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) 또는 [Visual Studio 2017 Enterprise](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)를 설치합니다.

1. 다운로드 하 고 실행 하면 설치 관리자 파일을 찾습니다. 브라우저에서 표시 될 수 있습니다 또는 다운로드 폴더에서 찾을 수 있습니다. 설치 관리자를 실행 하려면 관리자 권한이 필요 합니다. 표시 될 수 있습니다는 **사용자 계정 컨트롤** 설치 프로그램에서 시스템 변경; 선택 권한을 부여 하려면 묻는 대화 상자 **예**합니다. 문제가 있는 경우 파일 탐색기에서 다운로드 한 파일을 찾을 설치 관리자 아이콘을 마우스 오른쪽 단추로 클릭 선택할 **관리자 권한으로 실행** 상황에 맞는 메뉴입니다.

   ![다운로드 하 여 Visual Studio 설치 관리자 설치](media/vscpp-concierge-run-installer.gif "다운로드 하 여 Visual Studio 설치 관리자를 설치 합니다.")

1. 설치 관리자는 특정 개발 영역에 대한 관련 옵션의 그룹인 워크로드 목록을 제공합니다. 에 대 한 지원 C++ 는 이제 기본적으로 설치 되지 않은 선택적 워크 로드의 일부입니다.

   ![사용한 데스크톱 개발 C++ 워크 로드](media/desktop-development-with-cpp.png "를 사용한 데스크톱 개발C++")

   에 대 한 C++을 선택 합니다 **를 사용한 데스크톱 개발 C++**  워크 로드를 선택한 후 **설치**.

   ![설치를 사용한 데스크톱 개발 C++ 워크 로드](media/vscpp-concierge-choose-workload.gif "설치를 사용한 데스크톱 개발 C++ 작업")

1. 설치가 완료 되 면 선택 합니다 **시작** Visual Studio를 시작 하는 단추입니다.

   처음으로 Visual Studio를 실행 하 여 메시지를 Microsoft 계정으로 로그인 합니다. 사용자 계정이 없는 경우 무료로 만들 수 있습니다. 테마를 선택 해야 합니다. 작업을 하려는 경우 나중에 변경할 수 있습니다.

   Visual Studio 여러 걸릴 수 있습니다 분을 처음 실행 하면 사용 합니다. 모양을 빠른 시간 경과에 다음과 같습니다.

   ![Visual Studio 2017에 로그인](media/vscpp-quickstart-first-run.gif "Visual Studio 2017에 로그인")

   Visual Studio는 다시 실행 하면 훨씬 더 빠르게 시작 합니다.

1. Visual Studio가 열리면 제목 표시줄에서 플래그 아이콘을 강조 표시 된 경우를 확인 합니다.

   ![Visual Studio 2017의 알림 플래그](media/vscpp-first-start-page-flag.png "Visual Studio 2017 알림 플래그")

   이 강조 표시 하는 경우 선택 하 여 엽니다는 **알림을** 창입니다. Visual Studio에 대 한 사용 가능한 모든 업데이트가 있는 경우 지금 설치 하는 것이 좋습니다. 설치가 완료 되 면 Visual Studio를 다시 시작 합니다.

::: moniker-end

::: moniker range="<vs-2017"

## <a name="visual-studio-2015-installation"></a>Visual Studio 2015 Installation

Visual Studio 2015를 설치하려면 [이전 버전의 Visual Studio 다운로드](https://www.visualstudio.com/vs/older-downloads/)로 이동합니다. 설치 프로그램을 실행하고 **사용자 지정 설치**를 선택한 다음, C++ 구성 요소를 선택합니다. 추가할 C++ 기존 Visual Studio 2015 설치에 지원, 입력 하 고 Windows 시작 단추를 클릭할 **프로그램 추가 / 제거**합니다. 결과 목록에서 프로그램을 열고 설치 된 프로그램 목록에서 Visual Studio 2015 설치를 찾습니다. 두 번 클릭 한 다음 선택 **수정** 시각적 개체를 선택 하 고 C++ 설치할 구성 요소입니다.

일반적으로 Visual Studio 2015 컴파일러를 사용하여 코드를 컴파일해야 하는 경우에도 Visual Studio 2017을 사용하는 것이 좋습니다. 자세한 내용은 [Visual Studio의 네이티브 멀티 타기팅을 사용하여 이전 프로젝트 빌드](../porting/use-native-multi-targeting.md)를 참조하세요.

::: moniker-end

Visual Studio를 실행 하는 경우 다음 단계를 계속 준비가 되었습니다.

## <a name="next-steps"></a>다음 단계

> [!div class="nextstepaction"]
> [만들기는 C++ 프로젝트](vscpp-step-1-create.md)

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
