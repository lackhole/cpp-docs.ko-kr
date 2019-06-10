---
title: Visual Studio에서 Linux CMake 프로젝트 구성
description: Visual Studio에서 Linux CMake 프로젝트를 구성, 편집 및 컴파일하는 방법
ms.date: 05/21/2019
ms.assetid: f8707b32-f90d-494d-ae0b-1d44425fdc25
ms.openlocfilehash: e2cda5e9b942342cca035c48054aadb5425b69cf
ms.sourcegitcommit: bde3279f70432f819018df74923a8bb895636f81
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66182893"
---
# <a name="configure-a-linux-cmake-project"></a>Linux CMake 프로젝트 구성

CMake 프로젝트를 포함하는 폴더를 열면 Visual Studio에서는 CMake가 생성하는 메타데이터를 사용하여 IntelliSense를 구성하고 자동으로 빌드합니다. 필요에 따라 Visual Studio를 사용하는 다른 사용자와 공유할 수 있는 JSON 파일에 로컬 구성 및 디버깅 설정이 저장됩니다. 

Visual Studio에서는 동일한 프로젝트에서 작업하는 다른 사용자가 사용하는 모든 도구를 계속 사용할 수 있도록 CMakeLists.txt 파일이나 원래 CMake 캐시를 수정하지 않습니다.

Visual Studio의 CMake 지원에 관한 일반적인 내용은 [Visual Studio용 CMake 도구](../build/cmake-projects-in-visual-studio.md)를 참조하세요. 여기서 계속하기 전에 먼저 읽어보세요.

## <a name="before-you-begin"></a>시작하기 전에

먼저 CMake 구성 요소를 비롯한 **C++를 사용한 Linux 개발** 워크로드가 설치되었는지 확인합니다. [Visual Studio에서 C++ Linux 워크로드 설치](download-install-and-setup-the-linux-development-workload.md)를 참조하세요. 

Linux 머신에서 다음이 설치되어 있는지 확인합니다. 

- gcc
- gdb
- rsync
- zip 

::: moniker range="vs-2019"

CMake 프로젝트를 위한 Linux 지원에는 대상 머신에 CMake의 최신 버전이 설치되어 있어야 합니다. 배포의 기본 패키지 관리자가 제공하는 버전이 IDE의 모든 기능을 지원하기에 충분하지 않을 수 있습니다. Visual Studio 2019는 최신 버전의 CMake가 설치되지 않은 원격 Linux 머신에 CMake의 사용자 로컬 복사본을 자동으로 설치할 수 있습니다. 프로젝트를 처음 빌드할 때 CMake의 호환 버전이 검색되지 않으면 CMake를 설치하기 위한 정보 표시줄 오퍼링이 표시됩니다.

바이너리는 `~/.vs/cmake`에 설치됩니다. 바이너리를 배포하면 프로젝트가 자동으로 다시 생성됩니다. `CMakeSettings.json`의 `cmakeExecutable` 필드에 의해 지정된 CMake가 잘못되고(존재하지 않거나 지원되지 않는 버전인 경우) 미리 빌드된 바이너리가 있는 경우 Visual Studio는 `cmakeExecutable`을 무시하고 미리 빌드된 바이너리를 사용합니다.

::: moniker-end

::: moniker range="vs-2017"

Visual Studio에서 CMake가 지원되려면 CMake 3.8에 도입된 서버 모드 지원이 필요합니다. Microsoft 제공 CMake 변형의 경우 [https://github.com/Microsoft/CMake/releases](https://github.com/Microsoft/CMake/releases)에서 미리 빌드된 최신 이진 파일을 다운로드합니다.

:::moniker-end

## <a name="open-a-folder"></a>폴더 열기

시작하려면 주 메뉴에서 **파일** > **열기** > **폴더**를 선택하거나 명령줄에서 `devenv.exe <foldername>`을 입력합니다. 열린 폴더에는 소스 코드와 함께 CMakeLists.txt 파일이 있어야 합니다.
다음 예제에서는 간단한 CMakeLists.txt 파일과 .cpp 파일을 보여 줍니다.

```cpp
// hello.cpp

#include <iostream>

int main(int argc, char* argv[])
{
    std::cout << "Hello from Linux CMake" << std::endl;
}
```

CMakeLists.txt:

```cmd
project (hello-cmake)
add_executable(hello-cmake hello.cpp)
```

## <a name="choose-a-linux-target"></a>Linux 대상 선택

폴더를 여는 즉시 Visual Studio에서 CMakeLists.txt 파일을 구문 분석하고 **x86-Debug**의 Windows 대상을 지정합니다. Linux를 대상으로 지정하려면 프로젝트 설정을 **Linux-Debug** 또는 **Linux-Release**로 변경합니다.

기본적으로 Visual Studio는 **도구** > **옵션** > **플랫폼 간** > **연결 관리자** 아래에 있는 목록에서 첫 번째 원격 시스템을 선택합니다. 원격 연결이 발견되지 않으면 만들라는 메시지가 표시됩니다. 자세한 내용은 [원격 Linux 컴퓨터에 연결](connect-to-your-remote-linux-computer.md)을 참조하세요.

Linux 대상을 지정하면 Linux 컴퓨터에 소스가 복사됩니다. 그런 다음 Linux 컴퓨터에서 CMake가 실행되어 프로젝트에 대한 CMake 캐시가 생성됩니다.

![Linux에서 CMake 캐시 생성](media/cmake-linux-1.png "Linux에서 CMake 캐시 생성")

원격 헤더에 IntelliSense 지원을 제공하기 위해 Visual Studio는 Linux 머신에서 로컬 Windows 머신의 디렉터리에 IntelliSense를 자동으로 복사합니다. 자세한 내용은 [원격 헤더를 위한 IntelliSense](configure-a-linux-project.md#remote_intellisense)를 참조하세요.

## <a name="debug-the-project"></a>프로젝트 디버그

원격 시스템에서 코드를 디버그하려면 중단점을 설정하고, 프로젝트 설정 옆의 도구 모음 메뉴에서 CMake 대상을 시작 항목으로 선택하고, 도구 모음에서 **&#x23f5; 시작**을 선택하거나 F5 키를 누릅니다.

프로그램의 명령줄 인수를 사용자 지정하려면 **솔루션 탐색기**에서 실행 파일을 마우스 오른쪽 단추로 클릭하고 **디버그 및 시작 설정**을 선택합니다. 그러면 프로그램에 대한 정보가 들어 있는 launch.vs.json 구성 파일이 열리거나 만들어집니다. 추가 인수를 지정하려면 `args` JSON 배열에 추가합니다. 자세한 내용은 [C++용 폴더 열기 프로젝트](../build/open-folder-projects-cpp.md) 및 [CMake 디버깅 세션 구성](../build/configure-cmake-debugging-sessions.md)을 참조하세요.

## <a name="configure-cmake-settings-for-linux"></a>Linux용 CMake 설정 구성

CMake Linux 프로젝트에 있는 CMakeSettings.json 파일은 [CMake 사용자 지정 설정](../build/customize-cmake-settings.md)에 나열된 모든 속성 및 원격 Linux 머신의 빌드 설정을 제어하는 추가 속성도 지정할 수 있습니다. 

::: moniker range="vs-2019"

Visual Studio 2019의 기본 CMake 설정을 변경하려면 주 도구 모음에서 **구성** 드롭다운을 열고 **구성 관리**를 선택합니다. 

   ![CMake 구성 관리](../build/media/vs2019-cmake-manage-configurations.png "CMake 구성 드롭다운")

이렇게 하면 루트 프로젝트 폴더의 `CMakeSettings.json` 파일을 편집하는 데 사용할 수 있는 **CMake 설정 편집기**가 나타납니다. 편집기에서 **JSON 편집** 단추를 클릭하여 파일을 직접 열 수도 있습니다. 자세한 내용은 [CMake 설정 사용자 지정](../build/customize-cmake-settings.md)을 참조하세요.

::: moniker-end

::: moniker range="vs-2017"

Visual Studio 2017에서 기본 CMake 설정을 변경하려면 주 메뉴에서 **CMake | CMake 설정 변경 | CMakeLists.txt**를 선택하거나 **솔루션 탐색기**에서 CMakeSettings.txt를 마우스 오른쪽 단추로 클릭하고 **CMake 설정 변경**을 선택합니다. 그런 다음, Visual Studio는 루트 프로젝트 폴더에서 새 `CMakeSettings.json` 파일을 만듭니다. **CMake 설정** 편집기를 사용하여 파일을 열거나 파일을 직접 수정할 수 있습니다. 자세한 내용은 [CMake 설정 사용자 지정](../build/customize-cmake-settings.md)을 참조하세요.

::: moniker-end

다음 예제에서는 이전 코드 예제에 기반을 둔 Linux-Debug에 대한 기본 구성을 보여 줍니다.

```json
{
      "name": "Linux-Debug",
      "generator": "Unix Makefiles",
      "remoteMachineName": "${defaultRemoteMachineName}",
      "configurationType": "Debug",
      "remoteCMakeListsRoot": "/var/tmp/src/${workspaceHash}/${name}",
      "cmakeExecutable": "/usr/local/bin/cmake",
      "buildRoot": "${env.LOCALAPPDATA}\\CMakeBuilds\\${workspaceHash}\\build\\${name}",
      "installRoot": "${env.LOCALAPPDATA}\\CMakeBuilds\\${workspaceHash}\\install\\${name}",
      "remoteBuildRoot": "/var/tmp/build/${workspaceHash}/build/${name}",
      "remoteInstallRoot": "/var/tmp/build/${workspaceHash}/install/${name}",
      "remoteCopySources": true,
      "remoteCopySourcesOutputVerbosity": "Normal",
      "remoteCopySourcesConcurrentCopies": "10",
      "remoteCopySourcesMethod": "rsync",
      "remoteCopySourcesExclusionList": [".vs", ".git"],
      "rsyncCommandArgs" : "-t --delete --delete-excluded",
      "remoteCopyBuildOutput" : "false",
      "cmakeCommandArgs": "",
      "buildCommandArgs": "",
      "ctestCommandArgs": "",
      "inheritEnvironments": [ "linux-x64" ]
}
```
다음 표에서는 해당 설정을 요약하여 보여줍니다.

|설정|설명|
|-----------|-----------------|
|`name`|이 값을 원하는 값으로 설정할 수 있습니다.|
|`remoteMachineName`|원격 시스템이 여러 개 있을 경우 대상으로 지정할 항목을 지정합니다. 이 필드에는 올바른 시스템을 선택할 수 있도록 IntelliSense가 활성화됩니다.|
|`remoteCMakeListsRoot`|원격 시스템에서 프로젝트 원본이 복사될 위치를 지정합니다.|
|`remoteBuildRoot`|원격 시스템에서 빌드 출력이 생성될 위치를 지정합니다. 또한 해당 출력은 `buildRoot`로 지정된 위치에 로컬로 복사됩니다.|
|`remoteInstallRoot` 및 `installRoot`| CMake 설치를 수행하는 경우 적용되는 것을 제외하고 `remoteBuildRoot` 및 `buildRoot`와 비슷합니다.|
|`remoteCopySources`|로컬 원본이 원격 머신에 복사되는지 여부를 지정합니다. 파일이 많이 있고 이미 원본과 직접 동기화한 경우 이 항목을 false로 설정할 수 있습니다.|
|`remoteCopyOutputVerbosity`| 오류를 진단해야 하는 경우 복사 단계의 자세한 정도를 지정합니다.|
|`remoteCopySourcesConcurrentCopies`| 복사를 수행하기 위해 생성된 프로세스 수를 지정합니다.|
|`remoteCopySourcesMethod`| `rsync` 또는 `sftp` 중 하나일 수 있습니다.|
|`remoteCopySourcesExclusionList`| 원격 머신에 복사할 파일을 지정합니다.|
|`rsyncCommandArgs`|복사의 rsync 메서드를 제어합니다.|
|`remoteCopyBuildOutput`| 원격 빌드 출력이 로컬 빌드 폴더에 복사되는지 여부를 제어합니다.|

추가 컨트롤에서 다음과 같은 선택적 설정을 사용할 수 있습니다.

```json
{
      "remotePrebuildCommand": "",
      "remotePreGenerateCommand": "",
      "remotePostbuildCommand": "",
}
```

이러한 옵션을 사용하면 빌드하기 전후 및 CMake 생성 전에 원격 시스템에서 명령을 실행할 수 있습니다. 값은 원격 시스템에서 유효한 모든 명령일 수 있습니다. 출력은 Visual Studio로 다시 파이핑됩니다.

::: moniker range="vs-2019"

Visual Studio 2019에서는 **CMake 설정 편집기**에서 이러한 모든 설정을 편집할 수 있습니다.

::: moniker-end

## <a name="see-also"></a>참고 항목

[프로젝트 속성 사용](../build/working-with-project-properties.md)<br/>
[Visual Studio의 CMake 프로젝트](../build/cmake-projects-in-visual-studio.md)<br/>
[원격 Linux 컴퓨터에 연결](connect-to-your-remote-linux-computer.md)<br/>
[CMake 사용자 지정 설정](../build/customize-cmake-settings.md)<br/>
[CMake 디버깅 세션 구성](../build/configure-cmake-debugging-sessions.md)<br/>
[Linux 프로젝트 배포, 실행 및 디버그](deploy-run-and-debug-your-linux-project.md)<br/>
[CMake 미리 정의된 구성 참조](../build/cmake-predefined-configuration-reference.md)<br/>
