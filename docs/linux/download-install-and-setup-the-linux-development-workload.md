---
title: Visual Studio에서 C++ Linux 워크로드 설치
description: Visual Studio에서 C++에 대한 Linux 워크로드를 다운로드하고, 설치하고, 설정하는 방법을 설명합니다.
ms.date: 03/05/2019
ms.assetid: e11b40b2-f3a4-4f06-b788-73334d58dfd9
ms.openlocfilehash: 74155724abb3a0e02cc27dd8a8d144f142ee4b6f
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57747724"
---
# <a name="download-install-and-set-up-the-linux-workload"></a>Linux 워크로드 다운로드, 설치 및 설정

Windows에서 Visual Studio 2017 IDE를 사용하여 Linux 물리적 컴퓨터, 가상 머신 또는 [Linux용 Windows 하위 시스템](/windows/wsl/about)에서 실행되는 C++ 프로젝트를 만들고, 편집하고, 디버그할 수 있습니다. 

CMake 또는 다른 빌드 시스템을 Visual Studio 프로젝트로 변환할 필요 없이 해당 시스템을 사용하는 기존 코드 베이스에서 작업할 수 있습니다. 코드 베이스가 플랫폼 간 기반인 경우 Visual Studio 내에서 Windows와 Linux를 모두 대상으로 할 수 있습니다. 예를 들어 Visual Studio를 사용하여 Windows에서 코드를 편집하고, 디버그하고, 프로파일링한 다음, 신속하게 Linux에서 프로젝트의 대상을 변경하여 추가 테스트를 수행할 수 있습니다. Linux 헤더 파일은 Visual Studio에서 전체 IntelliSense를 지원하기 위해 해당 파일을 사용하는 로컬 머신에 자동으로 복사됩니다(문 완성, 정의로 이동 등).
 
이러한 시나리오에서는 **C++를 사용한 Linux 개발** 워크로드가 필요합니다. 

## <a name="visual-studio-setup"></a>Visual Studio 설치

1. Windows 검색 상자: ![Windows 검색 상자](media/visual-studio-installer-search.png)에 "Visual Studio 설치 관리자"를 입력합니다.
2. **앱** 결과에서 설치 관리자를 찾아 두 번 클릭합니다. 설치 프로그램이 열리면 **수정**을 선택한 다음, **워크로드** 탭을 클릭합니다. **기타 도구 집합**으로 아래로 스크롤하여 **C++를 사용한 Linux 개발** 워크로드를 선을 선택합니다.

   ![Linux 개발용 Visual C++ 워크로드](media/linuxworkload.png)

1. CMake를 사용하거나 IoT 또는 임베디드 플랫폼을 대상으로 하는 경우 오른쪽의 **설치 세부 정보** 창으로 이동하고 **C++를 사용한 Linux 개발** 아래의 **옵션 구성 요소** 확장한 후 필요한 구성 요소를 선택합니다.

    **Visual Studio 2017 버전 15.4 이상**<br/>: Visual Studio에 대한 Linux C++ 워크로드를 설치하면 Linux용 CMake 지원이 기본적으로 선택됩니다.

1. **수정**을 클릭하여 설치를 계속합니다.

## <a name="options-for-creating-a-linux-environment"></a>Linux 환경 만들기 옵션

아직 Linux 머신이 없는 경우 Azure에서 Linux 가상 머신을 만들 수 있습니다. 자세한 내용은 [빠른 시작: Azure Portal에서 Linux 가상 머신 만들기](/azure/virtual-machines/linux/quick-create-portal)를 참조하세요.

Windows 10에서 다른 옵션은 Linux용 Windows 하위 시스템을 활성화하는 것입니다. 자세한 내용은 [Windows 10 설치 가이드](/windows/wsl/install-win10)를 참조하세요.

## <a name="linux-setup-ubuntu"></a>Linux 설정: Ubuntu

대상 Linux 컴퓨터에 **openssh-server**, **g++**, **gdb** 및 **gdbserver**가 설치되어 있고 ssh 데몬이 실행되고 있어야 합니다. IntelliSense 지원을 위해 로컬 머신과 원격 헤더를 자동 동기화하려면 **zip**이 필요합니다. 이러한 애플리케이션이 없다면 다음과 같이 설치할 수 있습니다.

1. Linux 컴퓨터의 셸 프롬프트에서 다음을 실행합니다.

   `sudo apt-get install openssh-server g++ gdb gdbserver zip`

   sudo 명령 때문에 루트 암호를 입력하라는 메시지가 표시될 수 있습니다.  메시지가 표시되면 루트 암호를 입력하고 계속합니다. 완료되면 필수 서비스 및 도구가 설치됩니다.

1. 다음을 실행하여 ssh 서비스가 Linux 컴퓨터에서 실행되고 있는지 확인합니다.

   `sudo service ssh start`

   그러면 서비스가 시작되고 백그라운드에서 실행되므로 연결을 허용할 준비가 됩니다.

## <a name="linux-setup-fedora"></a>Linux 설정: Fedora

Fedora를 실행하는 대상 시스템은 **dnf** 패키지 설치 프로그램을 사용합니다. **openssh-server**, **g++**, **gdb**, **gdbserver** 및 **zip**을 다운로드하고 ssh 디먼을 다운로드하려면 다음 지침을 따르세요.

1. Linux 컴퓨터의 셸 프롬프트에서 다음을 실행합니다.

   `sudo dnf install openssh-server gcc-g++ gdb gdb-gdbserver zip`

   sudo 명령 때문에 루트 암호를 입력하라는 메시지가 표시될 수 있습니다.  메시지가 표시되면 루트 암호를 입력하고 계속합니다. 완료되면 필수 서비스 및 도구가 설치됩니다.

1. 다음을 실행하여 ssh 서비스가 Linux 컴퓨터에서 실행되고 있는지 확인합니다.

   `sudo systemctl start sshd`

   그러면 서비스가 시작되고 백그라운드에서 실행되므로 연결을 허용할 준비가 됩니다.

## <a name="ensure-you-have-cmake-38-on-the-remote-linux-machine"></a>원격 Linux 머신에서 CMake 3.8을 설치했는지 확인합니다.

Linux distro에 이전 버전의 CMake가 있을 수 있습니다. Visual Studio에서 CMake가 지원되려면 CMake 3.8에 도입된 서버 모드 지원이 필요합니다. Microsoft 제공 CMake 변형의 경우 [https://github.com/Microsoft/CMake/releases](https://github.com/Microsoft/CMake/releases)에서 미리 빌드된 최신 바이너리를 Linux 머신에 다운로드합니다.
