---
title: Visual Studio에서 대상 Linux 시스템에 연결
description: Visual Studio C++ 프로젝트 내에서 원격 Linux 머신 또는 WSL에 연결하는 방법입니다.
ms.date: 09/04/2019
ms.assetid: 5eeaa683-4e63-4c46-99ef-2d5f294040d4
ms.openlocfilehash: 3d91faa7aa83c86e8c2f3544ee61c16f75f8c346
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626760"
---
# <a name="connect-to-your-target-linux-system-in-visual-studio"></a>Visual Studio에서 대상 Linux 시스템에 연결

::: moniker range="vs-2015"

Linux 지원은 Visual Studio 2017 이상에서 사용할 수 있습니다.

::: moniker-end

::: moniker range=">=vs-2017"

원격 머신 또는 WSL(Linux용 Windows 하위 시스템)을 대상으로 하도록 Linux 프로젝트를 구성할 수 있습니다. 원격 머신 및 Visual Studio 2017의 WSL에 대해 원격 연결을 설정해야 합니다. 

## <a name="connect-to-a-remote-linux-computer"></a>원격 Linux 컴퓨터에 연결

원격 Linux 시스템(VM 또는 물리적 컴퓨터)에 대해 C++ Linux 프로젝트를 빌드할 때 Linux 소스 코드가 원격 Linux 컴퓨터에 복사된 다음, Visual Studio 설정에 따라 컴파일됩니다.

이 원격 연결을 설정하려면:

1. 처음으로 프로젝트를 빌드하거나 **도구 > 옵션**을 선택한 다음 **플랫폼 간 > 연결 관리자** 노드를 열고 **추가** 단추를 클릭하여 수동으로 새 항목을 만듭니다.

   ![연결 관리자](media/settings_connectionmanager.png)

   두 경우 모두에, **원격 시스템에 연결** 창이 표시됩니다.

   ![원격 시스템에 연결](media/connect.png)

1. 다음 정보를 입력합니다.

   | 입력 | 설명
   | ----- | ---
   | **호스트 이름**           | 대상 디바이스의 이름 또는 IP 주소
   | **포트**                | SSH 서비스가 실행되는 포트(일반적으로 22)
   | **사용자 이름**           | 인증할 사용자
   | **인증 형식** | 암호 또는 프라이빗 키가 모두 지원됨
   | **암호**            | 입력한 사용자 이름의 암호
   | **프라이빗 키 파일**    | SSH 연결을 위해 생성된 프라이빗 키 파일
   | **암호**          | 위에서 선택한 프라이빗 키와 함께 사용된 암호

   인증을 위해 암호 또는 키 파일과 암호를 사용할 수 있습니다. 대부분의 개발 시나리오에서는 암호 인증으로 충분합니다. 퍼블릭/프라이빗 키 파일을 사용하려는 경우 새로 만들거나 [기존 파일을 재사용](https://security.stackexchange.com/questions/10203/reusing-private-public-keys)할 수 있습니다. 현재, RSA 및 DSA 키만 지원됩니다. 
   
   다음 단계에 따라 프라이빗 RSA 키 파일을 만들 수 있습니다.

    1. Windows 머신에서 `ssh-keygen -t rsa`를 사용하여 ssh 키 쌍을 만듭니다. 퍼블릭 키와 프라이빗 키가 생성됩니다. 기본적으로 키는 `id_rsa.pub` 및 `id_rsa`라는 이름으로 `C:\Users\%USERNAME%\.ssh` 아래에 배치됩니다.

    1. Windows에서 Linux 머신으로 퍼블릭 키를 복사합니다. `scp -p C:\Users\%USERNAME%\.ssh\id_rsa.pub user@hostname`

    1. Linux 시스템에서 권한 있는 키 목록에 키를 추가하고 파일에 올바른 권한이 있는지 확인합니다. `cat ~/id_rsa.pub >> ~/.ssh/authorized_keys; chmod 600 ~/.ssh/authorized_keys`

1. **연결** 단추를 클릭하여 원격 컴퓨터에 대한 연결을 시도합니다. 

   연결에 성공하면 Visual Studio에서 원격 헤더를 사용하도록 IntelliSense를 구성하기 시작합니다. 자세한 내용은 [원격 시스템의 헤더에 대한 IntelliSense](configure-a-linux-project.md#remote_intellisense)를 참조하세요.

   연결이 실패하면 변경해야 하는 입력 상자에 빨간색 윤곽선이 표시됩니다.

   ![연결 관리자 오류](media/settings_connectionmanagererror.png)

   인증을 위해 키 파일을 사용하는 경우 대상 머신의 SSH 서버가 실행 중이며 올바르게 구성되었는지 확인합니다.

   ::: moniker-end

   ::: moniker range="vs-2019"

   연결 문제 해결을 지원하기 위해 **도구 > 옵션 > 플랫폼 간 > 로깅**으로 이동하여 로깅을 사용하도록 설정합니다.

   ![원격 로깅](media/remote-logging-vs2019.png)

   로그에는 연결, 원격 머신으로 전송되는 모든 명령(해당 텍스트, 종료 코드, 실행 시간), Visual Studio에서 셸로 전송되는 모든 출력이 포함됩니다. 로깅은 Visual Studio의 모든 플랫폼 간 CMake 프로젝트 또는 MSBuild 기반 Linux 프로젝트에 대해 작동합니다.

   파일 또는 출력 창의 **플랫폼 간 로깅** 창에 출력되도록 구성할 수 있습니다. MSBuild 기반 Linux 프로젝트의 경우 MSBuild에서 원격 머신에 실행한 명령이 **출력 창**으로 라우팅되지 않습니다. Out Of Process로 명령을 내보내기 때문입니다. 대신, “msbuild_” 접두사를 사용하여 파일에 기록됩니다.
   
## <a name="tcp-port-forwarding"></a>TCP 포트 전달

Visual Studio의 Linux 지원에는 TCP 포트 전달에 대한 종속성이 있습니다. 원격 시스템에 TCP 포트 전달이 사용하지 않도록 설정되어 있는 경우 **Rsync** 및 **gdbserver**가 영향을 받습니다. 

Rsync는 MSBuild 기반 Linux 프로젝트 및 CMake 프로젝트 모두에서 [IntelliSense에 사용할 원격 시스템의 헤더를 Windows에 복사](configure-a-linux-project.md#remote_intellisense)하는 데 사용됩니다. TCP 포트 전달을 사용하도록 설정할 수 없는 경우 [도구] > [옵션] > [플랫폼 간] > [연결 관리자] > [원격 헤더 IntelliSense 관리자]를 통해 원격 헤더의 자동 다운로드를 사용하지 않도록 설정할 수 있습니다. 연결하려는 원격 시스템에 TCP 포트 전달이 사용하도록 설정되어 있지 않은 경우 IntelliSense의 원격 헤더 다운로드가 시작되면 다음과 같은 오류가 표시됩니다.

![헤더 오류](media/port-forwarding-headers-error.png)

Rsync는 원격 시스템에 소스 파일을 복사하기 위한 Visual Studio의 CMake 지원에도 사용됩니다. TCP 포트 전달을 사용하도록 설정할 수 없는 경우 sftp를 원격 소스 복사 방법으로 사용할 수 있습니다. sftp는 일반적으로 rsync보다 느리지만, TCP 포트 전달에 대한 종속성이 없습니다. [CMake 설정 편집기](../build/cmakesettings-reference.md#additional-settings-for-cmake-linux-projects)에서 remoteCopySourcesMethod 속성을 사용하여 원격 소스 복사 방법을 관리할 수 있습니다. 원격 시스템에 TCP 포트 전달이 사용하지 않도록 설정된 경우 처음 rsync를 호출하면 CMake 출력 창에 오류가 표시됩니다.

![Rsync 오류](media/port-forwarding-copy-error.png)

gdbserver는 임베디드 디바이스에서 디버그하는 데 사용할 수 있습니다. TCP 포트 전달을 사용하도록 설정할 수 없는 경우 모든 원격 디버깅 시나리오에 gdb를 사용해야 합니다. gdb는 원격 시스템에서 프로젝트를 디버그할 때 기본적으로 사용됩니다. 

   ::: moniker-end

## <a name="connect-to-wsl"></a>WSL에 연결

::: moniker range="vs-2017"

Visual Studio 2017에서는, 이 문서의 앞부분에 설명된 대로 원격 Linux 머신에 연결할 때와 동일한 단계를 사용하여 WSL에 연결합니다. **호스트 이름**으로 **localhost**를 사용합니다.

::: moniker-end

::: moniker range="vs-2019"

Visual Studio 2019 버전 16.1에서는 [WSL(Linux용 Windows 하위 시스템)](https://docs.microsoft.com/windows/wsl/about)과 함께 C++를 사용하기 위한 기본 지원을 추가했습니다.  즉, 로컬 WSL 설치에서 빌드하고 디버그하기 위해 더 이상 원격 연결을 추가하거나 SSH를 구성할 필요가 없습니다. 자세한 내용은 여기서 [WSL 설치 방법](https://docs.microsoft.com/windows/wsl/install-win10)을 참조하세요.

Visual Studio에서 작동하도록 WSL 설치를 구성하려면 gcc 또는 clang, gdb, make, rsync 및 zip 도구를 설치해야 합니다. g++ 컴파일러도 설치하는 이 명령을 사용하여 APT를 사용하는 배포판에 설치할 수 있습니다. 

```bash
sudo apt install g++ gdb make rsync zip
```
자세한 내용은 [Linux 작업 다운로드, 설치, 설정](download-install-and-setup-the-linux-development-workload.md)을 참조하세요.

WSL에 대해 프로젝트를 구성하려면 프로젝트 종류에 따라 [Linux 프로젝트 구성](configure-a-linux-project.md) 또는 [Linux CMake 프로젝트 구성](cmake-linux-project.md)을 참조하세요. WSL을 사용하여 간단한 콘솔 애플리케이션을 만드는 단계별 지침을 따르려면 [Visual Studio 2019 및 WSL(Linux용 Windows 하위 시스템)의 C++](https://devblogs.microsoft.com/cppblog/c-with-visual-studio-2019-and-windows-subsystem-for-linux-wsl/)에 대한 소개 블로그 게시물을 참조하세요.

::: moniker-end

## <a name="see-also"></a>참고 항목

[Linux 프로젝트 구성](configure-a-linux-project.md)<br />
[Linux CMake 프로젝트 구성](cmake-linux-project.md)<br />
[Linux 프로젝트 배포, 실행 및 디버그](deploy-run-and-debug-your-linux-project.md)<br />
[CMake 디버깅 세션 구성](../build/configure-cmake-debugging-sessions.md)
