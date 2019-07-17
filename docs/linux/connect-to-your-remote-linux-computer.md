---
title: Visual Studio에서 대상 Linux 시스템에 연결
description: Visual Studio C++ 프로젝트 내에서 원격 Linux 머신 또는 WSL에 연결하는 방법입니다.
ms.date: 06/19/2019
ms.assetid: 5eeaa683-4e63-4c46-99ef-2d5f294040d4
ms.openlocfilehash: 00d7facca2857efb0b8b43b5aaf38edce348a511
ms.sourcegitcommit: 0e3da5cea44437c132b5c2ea522bd229ea000a10
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2019
ms.locfileid: "67861143"
---
# <a name="connect-to-your-target-linux-system-in-visual-studio"></a>Visual Studio에서 대상 Linux 시스템에 연결

::: moniker range="vs-2015"

Linux 지원은 Visual Studio 2017 이상에서 사용할 수 있습니다.

::: moniker-end

::: moniker range=">=vs-2017"

원격 머신 또는 WSL(Linux용 Windows 하위 시스템)을 대상으로 하도록 Linux 프로젝트를 구성할 수 있습니다. 원격 머신 및 Visual Studio 2017의 WSL에 대해 연결을 설정해야 합니다. 

## <a name="connect-to-a-remote-linux-computer"></a>원격 Linux 컴퓨터에 연결

원격 Linux 시스템(VM 또는 물리적 머신)에 대해 C++ Linux 프로젝트를 빌드할 때 Linux 코드가 원격 Linux 컴퓨터에 복사된 다음, Visual Studio 설정에 따라 컴파일됩니다.

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
   | **인증 형식** | 암호 또는 개인 키가 모두 지원됨
   | **암호**            | 입력한 사용자 이름의 암호
   | **개인 키 파일**    | SSH 연결을 위해 생성된 개인 키 파일
   | **암호**          | 위에서 선택한 개인 키와 함께 사용된 암호

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

   ::: moniker-end

## <a name="connect-to-wsl"></a>WSL에 연결

::: moniker range="vs-2017"

Visual Studio 2017에서는, 이 문서의 앞부분에 설명된 대로 원격 Linux 머신에 연결할 때와 동일한 단계를 사용하여 WSL에 연결합니다. **호스트 이름**으로 **localhost**를 사용합니다.

::: moniker-end

::: moniker range="vs-2019"

Visual Studio 2019 버전 16.1에서는 WSL을 대상으로 지정할 때 SSH를 구성하거나 원격 연결을 추가하지 않아도 됩니다. Linux 시스템에 필요한 것은 gcc, gdb, make, rsync, zip뿐입니다. rsync 및 zip은 Visual Studio에서 WSL 인스턴스의 헤더 파일을 처음 사용할 때 IntelliSense에 사용할 Windows 파일 시스템으로 추출하기 위한 용도로만 필요합니다. Visual Studio 2019 버전 16.1에서는 WSL 지원이 Windows 버전 1809를 기반으로 합니다. 이후 버전의 Windows를 실행할 수는 있지만, Visual Studio에서 새 WSL 기능을 아직 활용하지 않습니다.

배포판이 apt를 지원하는 경우, 다음 명령을 사용하여 필수 패키지를 설치할 수 있습니다.

```bash
sudo apt install g++ gdb make rsync zip
```

WSL에 대해 프로젝트를 구성하려면 프로젝트 종류에 따라 [Linux 프로젝트 구성](configure-a-linux-project.md) 또는 [Linux CMake 프로젝트 구성](cmake-linux-project.md)을 참조하세요.

::: moniker-end

## <a name="see-also"></a>참고 항목

[Linux 프로젝트 구성](configure-a-linux-project.md)<br />
[Linux CMake 프로젝트 구성](cmake-linux-project.md)<br />
[Linux 프로젝트 배포, 실행 및 디버그](deploy-run-and-debug-your-linux-project.md)<br />




