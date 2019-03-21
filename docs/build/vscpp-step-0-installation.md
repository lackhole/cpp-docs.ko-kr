---
title: Visual Studio 2017에서 c + + 지원 설치
description: Visual Studio의 Visual c + + 지원 설치
ms.custom: mvc
ms.date: 11/19/2018
ms.topic: tutorial
ms.devlang: cpp
ms.assetid: 45138d70-719d-42dc-90d7-1d0ca31a2f54
ms.openlocfilehash: 6c5adac9bb31287693b7d53c1fa8ff10263f4367
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57815855"
---
# <a name="install-c-support-in-visual-studio"></a>Visual Studio에서 c + + 지원 설치

Visual Studio 2017 및 Visual c++ 도구를 아직 설치하지 않은 경우 시작하는 방법은 다음과 같습니다.

## <a name="prerequisites"></a>전제 조건

- 광대역 인터넷 연결 합니다. Visual Studio 설치 관리자를 여러 기가바이트 단위의 데이터를 다운로드할 수 있습니다.

- Microsoft Windows 7 이상을 실행 하는 컴퓨터입니다. 최상의 개발 환경을 위해 Windows 10이 좋습니다. Visual Studio를 설치 하기 전에 시스템에 최신 업데이트가 적용 되 고 있는지 확인 합니다.

- 사용 가능한 디스크 공간이 충분 합니다. Visual Studio는 7GB 이상 디스크 공간이 필요 하 고 다양 한 일반 옵션 설치 된 경우 50GB 이상 걸릴 수 있습니다. C: 드라이브에 설치 하는 것이 좋습니다.

디스크 공간 및 운영 체제 요구 사항에 대 한 자세한 내용은 참조 하세요. [Visual Studio 제품군 시스템 요구 사항](/visualstudio/productinfo/vs2017-system-requirements-vs)합니다. 설치 관리자에서 선택한 옵션에 대 한 필요한 디스크 공간을 보고 합니다.

## <a name="visual-studio-2015-installation"></a>Visual Studio 2015 Installation

Visual Studio 2015를 설치하려면 [이전 버전의 Visual Studio 다운로드](https://www.visualstudio.com/vs/older-downloads/)로 이동합니다. 설치 프로그램을 실행하고 **사용자 지정 설치**를 선택한 다음, C++ 구성 요소를 선택합니다. 기존 Visual Studio 2015 설치에 c + + 지원을 추가 하려면 Windows 시작 단추 및 유형에 따라 클릭 **프로그램 추가 / 제거**합니다. 결과 목록에서 프로그램을 열고 설치 된 프로그램 목록에서 Visual Studio 2015 설치를 찾습니다. 두 번 클릭 한 다음 선택 **수정** 설치할 Visual c + + 구성 요소를 선택 합니다.

일반적으로 Visual Studio 2015 컴파일러를 사용하여 코드를 컴파일해야 하는 경우에도 Visual Studio 2017을 사용하는 것이 좋습니다. 자세한 내용은 [Visual Studio의 네이티브 멀티 타기팅을 사용하여 이전 프로젝트 빌드](../porting/use-native-multi-targeting.md)를 참조하세요.

## <a name="visual-studio-2017-installation"></a>Visual Studio 2017 Installation

1. Windows에 대 한 최신 Visual Studio 2017 설치 관리자를 다운로드 합니다.

   > [!div class="nextstepaction"]
   > [Visual Studio 2017 Community 설치](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)

   >[!Tip]
   > 커뮤니티 에디션은 개인 개발자, 교실 학습, 학술 연구 및 오픈 소스 개발용입니다. 다른 용도의 경우 [Visual Studio 2017 Professional](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) 또는 [Visual Studio 2017 Enterprise](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)를 설치합니다.

1. 다운로드 하 고 실행 하면 설치 관리자 파일을 찾습니다. 브라우저에서 표시 될 수 있습니다 또는 다운로드 폴더에서 찾을 수 있습니다. 설치 관리자를 실행 하려면 관리자 권한이 필요 합니다. 표시 될 수 있습니다는 **사용자 계정 컨트롤** 설치 프로그램에서 시스템 변경; 선택 권한을 부여 하려면 묻는 대화 상자 **예**합니다. 문제가 있는 경우 파일 탐색기에서 다운로드 한 파일을 찾을 설치 관리자 아이콘을 마우스 오른쪽 단추로 클릭 선택할 **관리자 권한으로 실행** 상황에 맞는 메뉴입니다.

   ![다운로드 하 여 Visual Studio 설치 관리자 설치](media/vscpp-concierge-run-installer.gif "다운로드 하 여 Visual Studio 설치 관리자를 설치 합니다.")

1. 설치 관리자는 특정 개발 영역에 대한 관련 옵션의 그룹인 워크로드 목록을 제공합니다. C + +에 대 한 지원은 이제 기본적으로 설치 되지 않은 선택적 워크 로드의 일부입니다.

   ![C + + 워크 로드를 사용한 데스크톱 개발](media/desktop-development-with-cpp.png "c + +를 사용한 데스크톱 개발")

   C + +를 선택 합니다 **c + +를 사용한 데스크톱 개발** 워크 로드를 선택한 후 **설치**합니다.

   ![C + + 워크 로드를 사용 하 여 데스크톱 개발을 설치](media/vscpp-concierge-choose-workload.gif "c + + 워크 로드를 사용 하 여 데스크톱 개발을 설치 합니다.")

1. 설치가 완료 되 면 선택 합니다 **시작** Visual Studio를 시작 하는 단추입니다.

   처음 Visual Studio를 실행 하면 Microsoft 계정으로 로그인 하 라는 메시지가 표시 됩니다. 사용자 계정이 없는 경우 무료로 만들 수 있습니다. 테마를 선택 해야 합니다. 작업을 하려는 경우 나중에 변경할 수 있습니다.

   Visual Studio 여러 걸릴 수 있습니다 분을 처음 실행 하면 사용 합니다. 모양을 빠른 시간 경과에 다음과 같습니다.

   ![Visual Studio 2017에 로그인](media/vscpp-quickstart-first-run.gif "Visual Studio 2017에 로그인")

   Visual Studio는 다시 실행 하면 훨씬 더 빠르게 시작 합니다.

1. Visual Studio가 열리면 제목 표시줄에서 플래그 아이콘을 강조 표시 된 경우를 확인 합니다.

   ![Visual Studio 2017의 알림 플래그](media/vscpp-first-start-page-flag.png "Visual Studio 2017 알림 플래그")

   이 강조 표시 하는 경우 선택 하 여 엽니다는 **알림을** 창입니다. Visual Studio에 대 한 사용 가능한 모든 업데이트가 있는 경우 지금 설치 하는 것이 좋습니다. 설치가 완료 되 면 Visual Studio를 다시 시작 합니다.

Visual Studio를 실행 하는 경우 다음 단계를 계속 준비가 되었습니다.

## <a name="next-steps"></a>다음 단계

> [!div class="nextstepaction"]
> [C + + 프로젝트 만들기](vscpp-step-1-create.md)

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
