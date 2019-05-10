---
title: Visual Studio에서 CMake 빌드 설정 사용자 지정
ms.date: 04/25/2019
helpviewer_keywords:
- CMake build settings
ms.openlocfilehash: 20ed066f71a5c8c3acb00ef5923fa5c9f16ac229
ms.sourcegitcommit: 18d3b1e9cdb4fc3a76f7a650c31994bdbd2bde64
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2019
ms.locfileid: "64877151"
---
# <a name="customize-cmake-build-settings"></a>CMake 빌드 설정 사용자 지정

::: moniker range="vs-2019"

Visual Studio 2019 이상 버전에서는 구성을 추가 하 고 사용 하 여 해당 설정을 사용자 지정할 수는 **CMake 설정 편집기**합니다. CMakeSettings.json 파일을 수동으로 편집 하는 보다 간단한 대안 편집기를 사용 하지만 파일을 직접 편집 하려는 경우 클릭할 수는 **JSON 편집** 편집기의 오른쪽 위에 있는 링크입니다. 

편집기를 열려면 클릭 합니다 **구성** 드롭 다운 주 도구 모음에서 선택한 **구성 관리**합니다.

![CMake 구성 드롭다운](media/vs2019-cmake-manage-configurations.png)

이제는 **설정 편집기** 왼쪽에서 설치 된 구성으로 합니다. 

![CMake 설정 편집기](media/cmake-settings-editor.png)

Visual Studio는 기본적으로 두 가지 구성을 제공 합니다. `x64-Debug` 고 `x86-Debug`입니다. 녹색 더하기 기호를 클릭 하 여 추가 구성을 추가할 수 있습니다. 편집기에서 볼 수 있는 설정 구성이 선택 되었는지에 따라 달라질 수 있습니다.

편집기에서 선택한 옵션 CMakeSettings.json 라는 파일에 기록 됩니다. 이 파일은 프로젝트를 빌드할 때 CMake로 전달 되는 환경 변수와 명령줄 인수를 제공 합니다. Visual Studio 수정 하지는 않는 CMakeLists.txt CMakeSettings.json을 사용 하 여 사용 하는 모든 도구를 사용 하 여 사용할 수 있습니다 팀의 다른 있도록 CMake 프로젝트 파일을 그대로 유지 하면서 Visual Studio를 통해 빌드를 사용자 지정할 수 있습니다.

## <a name="cmake-general-settings"></a>CMake 일반 설정

다음 설정은 사용할 수 있습니다 합니다 **일반** 제목:

### <a name="configuration-name"></a>구성 이름

에 해당 하는 **이름을** 설정 합니다. 에 표시 되는 이름입니다는 C++ 구성 드롭다운 목록입니다. 사용할 수는 `${name}` 경로 등의 다른 속성 값을 작성 하는 매크로입니다.


### <a name="configuration-type"></a>구성 유형

에 해당 하는 **configurationType** 설정 합니다. 선택한 생성기에 대 한 빌드 구성 형식을 정의합니다. 현재 지원되는 값은 "Debug", "MinSizeRel", "Release" 및 "RelWithDebInfo"입니다.

### <a name="toolset"></a>도구 집합

에 해당 하는 **inheritedEnvironments** 설정 합니다. 선택한 구성을 작성 하는 데 사용할 컴파일러 환경을 정의 합니다. 지원 되는 값은 구성의 형식에 따라 달라 집니다. 사용자 지정 환경을 만들려면 클릭 합니다 **JSON 편집** 설정 편집기의 오른쪽 위 모퉁이에서 링크 및 CMakeSettings.json 파일을 직접 편집 합니다.

### <a name="cmake-toolchain-file"></a>CMake 도구 체인 파일

CMake 도구 체인 파일 경로입니다. Cmake로 전달 됩니다 "-DCMAKE_TOOLCHAIN_FILE = \<파일 경로 >"입니다.

### <a name="build-root"></a>루트 빌드

에 해당 **buildRoot**합니다. 매핑됩니다 **-DCMAKE_BINARY_DIR** 전환한 CMake 캐시 생성 되도록 지정 합니다. 폴더가 없으면 해당 폴더가 만들어집니다.

## <a name="command-arguments"></a>명령 인수

다음 설정은 사용할 수 있습니다 합니다 **명령 인수** 제목:

### <a name="cmake-command-arguments"></a>CMake 명령 인수

에 해당 **cmakeCommandArgs**합니다. CMake.exe을 전달 하려는 추가 스위치를 지정 합니다.

### <a name="build-command-arguments"></a>빌드 명령 인수

에 해당 **buildCommandArgs**: 내부에 전달할 추가 스위치 빌드 시스템을 지정 합니다. 예를 들어 Ninja 생성기를 사용하는 경우 -v를 전달하면 Ninja에서 명령줄을 출력하도록 강제합니다.


### <a name="ctest-command-arguments"></a>CTest 명령 인수

에 해당**ctestCommandArgs**: 테스트 실행 시 CTest에 전달할 추가 스위치를 지정 합니다.

## <a name="general-settings-for-remote-builds"></a>원격 빌드에 대 한 일반 설정

원격 빌드를 사용 하는 Linux와 같은 구성에 대해 다음 설정을 사용할 수도 있습니다.

### <a name="rsync-command-arguments"></a>rsync 명령 인수

Rsync 전달할 명령 인수를 제공 합니다. 

## <a name="cmake-variables-and-cache"></a>CMake 변수 및 캐시

이러한 설정을 통해 CMake 변수를 설정 하 고 CMakeSettings.json에 저장할 수 있습니다. 빌드 시 CMake로 전달 됩니다 않으며 재정의 값 CMakeLists.txt 파일에 있을 수 있습니다. 이 섹션은 CMakeGUI 편집할 수 있는 모든 CMake 변수 목록 보기를 사용할 수 있는 동일한 방식에 사용할 수 있습니다. 클릭 합니다 **저장 하 고 캐시 생성** (당 CMakeGUI) 고급 변수를 포함 하 여 편집을 사용할 수 있는 모든 CMake 변수 목록을 보려면 단추입니다. 목록 변수 이름으로 필터링 할 수 있습니다. 

에 해당 **변수**: CMake로 전달 되는 변수 이름-값 쌍이 포함 **-D** *_이름_ =  _값_* CMake로 합니다. CMake 프로젝트 빌드 지침에서 CMake 캐시 파일에 변수를 직접 추가하도록 지정하는 경우 여기에 대신 추가하는 것이 좋습니다.

## <a name="advanced-settings"></a>고급 설정

### <a name="cmake-generator"></a>CMake 생성기

에 해당 **생성기**: CMake 매핑됩니다 **-G** 전환한 데 생성기를 지정 합니다. 이 속성은 다른 속성 값을 구성할 때 매크로(`${generator}`)로 사용할 수도 있습니다. Visual Studio에서 현재 지원하는 CMake 생성기는 다음과 같습니다.

  - "Ninja"
  - "Unix 메이크파일"
  - "Visual Studio 16 2019"
  - "Visual Studio 16 2019 Win64"
  - - "Visual Studio 16 2019 ARM"
  - "Visual Studio 15 2017"
  - "Visual Studio 15 2017 Win64"
  - "Visual Studio 15 2017 ARM"
  - "Visual Studio 14 2015"
  - "Visual Studio 14 2015 Win64"
  - "Visual Studio 14 2015 ARM"
  
  Ninja는 유연성과 기능 대신 빠른 속도로 빌드하도록 설계되었으므로 기본값으로 설정됩니다. 그러나 일부 CMake 프로젝트는 Ninja를 사용하여 올바르게 빌드하지 못할 수도 있습니다. 이 경우 CMake에서 Visual Studio 프로젝트를 대신 생성하도록 지시할 수 있습니다.

### <a name="intellisense-mode"></a>IntelliSense 모드

정확한 IntelliSense에 대 한 프로젝트에 대 한 적절 한 값으로 설정 합니다.

### <a name="install-directory"></a>설치 디렉터리

CMake 빌드 대상을 설치 하는 디렉터리입니다.

### <a name="cmake-executable"></a>CMake 실행 파일

전체 경로 파일 이름 및 확장명을 포함 하 여 CMake 실행 파일입니다. 원격 빌드에 대 한 원격 컴퓨터에서 CMake 위치를 지정 합니다.

원격 빌드를 사용 하는 Linux와 같은 구성에 대해 다음 설정을 사용할 수도 있습니다.

### <a name="remote-cmakeliststxt-root"></a>원격 CMakeLists.txt 루트

원격 컴퓨터의 루트 CMakeLists.txt 파일이 포함 된 디렉터리입니다.

### <a name="remote-install-root"></a>원격 설치 루트

CMake 대상 설치는 원격 컴퓨터의 디렉터리입니다.

### <a name="remote-copy-sources"></a>원격 복사 원본

원격 컴퓨터에 소스 파일을 복사할지 여부를 지정 하 고 지정할 수 있도록 경우 rsync 또는 sftp를 합니다. 

## <a name="directly-edit-cmakesettingsjson"></a>CMakeSettings.json을 직접 편집

또한 직접 편집할 수 있습니다 `CMakeSettings.json` 사용자 지정 구성을 만들 수 있습니다. 합니다 **설정 편집기** 에 **JSON 편집** 파일 편집을 위해 열리는 오른쪽 위에 있는 단추입니다. 

다음 예제에서는 시작 지점으로 사용할 수 있는 샘플 구성을 보여 줍니다.

```json
    {
      "name": "x86-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x86" ],
      "buildRoot": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\build\\${name}",
      "installRoot": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\install\\${name}",
      "cmakeCommandArgs": "",
      "buildCommandArgs": "-v",
      "ctestCommandArgs": ""
    },

```

JSON IntelliSense를 사용 하면 편집 된 `CMakeSettings.json` 파일:

   ![CMake JSON IntelliSense](media/cmake-json-intellisense.png "CMake JSON IntelliSense")

JSON 편집기도 알려줍니다 호환 되지 않는 설정을 선택 하는 경우.

각 파일의 속성에 대 한 자세한 내용은 참조 하세요. [CMakeSettings.json 스키마 참조](cmakesettings-reference.md)합니다.

::: moniker-end

::: moniker range="<=vs-2017"

Visual Studio 2017에는 지정된 된 프로젝트에 대 한 CMake 캐시를 만드는 CMake.exe 호출 하는 방법을 정의 하는 몇 가지 CMake 구성을 제공 합니다. 새 구성을 추가하려면 도구 모음에서 구성 드롭다운을 클릭하고 **구성 관리**를 선택합니다.

   ![CMake 구성 관리](media/cmake-manage-configurations.png)

미리 정의된 구성 목록에서 다음을 선택할 수 있습니다.

   ![CMake 미리 정의된 구성](media/cmake-configurations.png)

처음 구성을 선택하면 Visual Studio가 프로젝트의 루트 폴더의 `CMakeSettings.json` 파일을 만듭니다. 이 파일은 예를 들어 **정리** 작업 후에 CMake 캐시 파일을 다시 만드는 데 사용됩니다. 

추가 구성을 추가하려면 `CMakeSettings.json`을 마우스 오른쪽 단추로 클릭하고 **구성 추가**를 선택합니다. 

   ![CMake 구성 추가](media/cmake-add-configuration.png "CMake 구성 추가")

**CMake 설정 편집기**를 사용하여 파일을 편집할 수도 있습니다. **솔루션 탐색기**에서 `CMakeSettings.json`을 마우스 오른쪽 단추로 클릭하고 **CMake 설정 편집**을 선택합니다. 또는 편집기 창 상단의 구성 드롭다운에서 **구성 관리**를 선택합니다. 

또한 직접 편집할 수 있습니다 `CMakeSettings.json` 다음 예제에서는 사용자 지정 구성을 만드는 데 시작 점으로 사용할 수 있는 샘플 구성을 보여 줍니다.

```json
    {
      "name": "x86-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x86" ],
      "buildRoot": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\build\\${name}",
      "installRoot": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\install\\${name}",
      "cmakeCommandArgs": "",
      "buildCommandArgs": "-v",
      "ctestCommandArgs": ""
    },

```

JSON IntelliSense를 사용하면 `CMakeSettings.json` 파일을 편집할 수 있습니다.

   ![CMake JSON IntelliSense](media/cmake-json-intellisense.png "CMake JSON IntelliSense")

각 파일의 속성에 대 한 자세한 내용은 참조 하세요. [CMakeSettings.json 스키마 참조](cmakesettings-reference.md)합니다.

::: moniker-end

## <a name="see-also"></a>참고자료

[Visual Studio의 CMake 프로젝트](cmake-projects-in-visual-studio.md)<br/>
[Linux CMake 프로젝트 구성](../linux/cmake-linux-project.md)<br/>
[원격 Linux 컴퓨터에 연결](../linux/connect-to-your-remote-linux-computer.md)<br/>
[CMake 디버깅 세션 구성](configure-cmake-debugging-sessions.md)<br/>
[Linux 프로젝트 배포, 실행 및 디버그](../linux/deploy-run-and-debug-your-linux-project.md)<br/>
[CMake 미리 정의된 구성 참조](cmake-predefined-configuration-reference.md)<br/>
