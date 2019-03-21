---
title: Visual Studio에서 CMake 빌드 설정 사용자 지정
ms.date: 03/05/2019
helpviewer_keywords:
- CMake build settings
ms.openlocfilehash: aa840dd41ee6843afae80343e42ba62741bbcd80
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826395"
---
# <a name="customize-cmake-build-settings"></a>CMake 빌드 설정 사용자 지정

Visual Studio는 CMake.exe를 호출하여 지정된 프로젝트에 대한 CMake 캐시를 만드는 방법을 정의하는 몇 가지 CMake 구성을 제공합니다. 새 구성을 추가하려면 도구 모음에서 구성 드롭다운을 클릭하고 **구성 관리**를 선택합니다.

   ![CMake 구성 관리](media/cmake-manage-configurations.png)

미리 정의된 구성 목록에서 다음을 선택할 수 있습니다.

   ![CMake 미리 정의된 구성](media/cmake-configurations.png)

처음 구성을 선택하면 Visual Studio가 프로젝트의 루트 폴더의 `CMakeSettings.json` 파일을 만듭니다. 이 파일은 예를 들어 **정리** 작업 후에 CMake 캐시 파일을 다시 만드는 데 사용됩니다. 

추가 구성을 추가하려면 `CMakeSettings.json`을 마우스 오른쪽 단추로 클릭하고 **구성 추가**를 선택합니다. 

   ![CMake 구성 추가](media/cmake-add-configuration.png "CMake 구성 추가")

JSON IntelliSense를 사용하면 `CMakeSettings.json` 파일을 편집할 수 있습니다.

   ![CMake JSON IntelliSense](media/cmake-json-intellisense.png "CMake JSON IntelliSense")

**CMake 설정 편집기**를 사용하여 파일을 편집할 수도 있습니다. **솔루션 탐색기**에서 `CMakeSettings.json`을 마우스 오른쪽 단추로 클릭하고 **CMake 설정 편집**을 선택합니다. 또는 편집기 창 상단의 구성 드롭다운에서 **구성 관리**를 선택합니다. 

`CMakeSettings.json`을 직접 편집하여 사용자 지정 구성을 만들 수도 있습니다. 다음 예제에서는 시작점으로 사용할 수 있는 샘플 구성을 보여줍니다.

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

- **name**: C++ 구성 드롭다운에 표시되는 이름입니다. `${name}` 매크로를 사용하면 경로처럼 다른 속성 값을 구성할 때 이 값을 사용할 수 있습니다. 예를 들어 `CMakeSettings.json`의 **buildRoot** 정의를 참조합니다.

- **generator**: CMake **-G** 스위치에 매핑되고 사용할 생성기를 지정합니다. 이 속성은 다른 속성 값을 구성할 때 매크로(`${generator}`)로 사용할 수도 있습니다. Visual Studio에서 현재 지원하는 CMake 생성기는 다음과 같습니다.

    - "Ninja"
    - "Visual Studio 14 2015"
    - "Visual Studio 14 2015 ARM"
    - "Visual Studio 14 2015 Win64"
    - "Visual Studio 15 2017"
    - "Visual Studio 15 2017 ARM"
    - "Visual Studio 15 2017 Win64"

    Ninja는 유연성과 기능 대신 빠른 속도로 빌드하도록 설계되었으므로 기본값으로 설정됩니다. 그러나 일부 CMake 프로젝트는 Ninja를 사용하여 올바르게 빌드하지 못할 수도 있습니다. 이 경우 CMake에서 Visual Studio 프로젝트를 대신 생성하도록 지시할 수 있습니다.

    Visual Studio 생성기를 지정하려면 주 메뉴에서 **CMake | CMake 설정 변경**을 선택하여 `CMakeSettings.json`을 엽니다. "Ninja"를 삭제하고 "V"를 입력합니다. 이렇게 하면 원하는 생성기를 선택할 수 있도록 IntelliSense가 활성화됩니다.

    활성 구성에서 Visual Studio 생성기를 지정하면 기본적으로 `-m -v:minimal` 인수를 사용하여 MSBuild.exe가 호출됩니다. `CMakeSettings.json` 파일 내에서 빌드를 사용자 지정하려면 `buildCommandArgs` 속성을 통해 빌드 시스템에 전달할 추가 [MSBuild 명령줄 인수](../build/msbuild-visual-cpp-overview.md)를 지정할 수 있습니다.
    
    ```json
    "buildCommandArgs": "-m:8 -v:minimal -p:PreferredToolArchitecture=x64"
    ```

- **buildRoot**: **-DCMAKE_BINARY_DIR** 스위치에 매핑하고 CMake 캐시가 만들어질 위치를 지정합니다. 폴더가 없으면 해당 폴더가 만들어집니다.

- **variables**: **-D** *_이름_=_값_* 으로 CMake에 전달되는 CMake 변수의 이름 값 쌍이 포함됩니다. CMake 프로젝트 빌드 지침에서 CMake 캐시 파일에 변수를 직접 추가하도록 지정하는 경우 여기에 대신 추가하는 것이 좋습니다. 다음 예제에서는 14.14.26428 MSVC 도구 세트에 대한 이름-값 쌍을 지정하는 방법을 보여줍니다.

```json
"variables": [
    {
      "name": "CMAKE_CXX_COMPILER",
      "value": "C:/Program Files (x86)/Microsoft Visual Studio/157/Enterprise/VC/Tools/MSVC/14.14.26428/bin/HostX86/x86/cl.exe"
    },
    {
      "name": "CMAKE_C_COMPILER",
      "value": "C:/Program Files (x86)/Microsoft Visual Studio/157/Enterprise/VC/Tools/MSVC/14.14.26428/bin/HostX86/x86/cl.exe"
    }
  ]
```

- **cmakeCommandArgs**: CMake.exe에 전달하려는 추가 스위치를 지정합니다.

- **configurationType**: 선택한 생성기에 대한 빌드 구성 형식을 정의합니다. 현재 지원되는 값은 "Debug", "MinSizeRel", "Release" 및 "RelWithDebInfo"입니다.

- **ctestCommandArgs**: 테스트 실행 시 CTest에 전달할 추가 스위치를 지정합니다.

- **buildCommandArgs**: 기본 빌드 시스템에 전달할 추가 스위치를 지정합니다. 예를 들어 Ninja 생성기를 사용하는 경우 -v를 전달하면 Ninja에서 명령줄을 출력하도록 강제합니다.

추가 설정은 CMake Linux 프로젝트에서 사용할 수 있습니다. [CMake Linux 프로젝트 구성](../linux/cmake-linux-project.md)을 참조하세요.

## <a name="environment-variables"></a>환경 변수

 `CMakeSettings.json`은 위에서 언급한 속성 중 하나에서 환경 변수를 사용하는 것도 지원합니다. 사용되는 구문은 %FOO% 환경 변수를 확장한 `${env.FOO}`입니다.
또한 이 파일에 기본 제공된 매크로에 액세스할 수 있습니다.

- `${workspaceRoot}` - 작업 영역 폴더의 전체 경로를 제공합니다.
- `${workspaceHash}` - 작업 영역 위치의 해시입니다. 현재 작업 영역에 대한 고유 식별자를 만드는 데 유용합니다(예: 폴더 경로에서 사용).
- `${projectFile}` - 루트 CMakeLists.txt 파일의 전체 경로
- `${projectDir}` - 루트 CMakeLists.txt 파일의 폴더에 대한 전체 경로
- `${thisFile}` – `CMakeSettings.json` 파일의 전체 경로입니다.
- `${name}` - 구성의 이름
- `${generator}` - 이 구성에 사용된 CMake 생성기의 이름

## <a name="ninja-command-line-arguments"></a>Ninja 명령줄 인수

대상이 지정되지 않으면 'default(기본)' 대상을 빌드합니다(설명서 참조).

```cmd
C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise>ninja -?
ninja: invalid option -- `-?'
usage: ninja [options] [targets...]
```

|옵션|설명|
|--------------|------------|
| --version  | Ninja 버전("1.7.1")을 출력합니다.|
|   -C DIR   | 다른 작업을 수행하기 전에 DIR로 변경합니다.|
|   -f FILE  | 입력 빌드 파일을 지정합니다(기본값 = build.ninja)|
|   -j N     | N개의 작업을 병렬로 실행합니다(기본값 = 14, 사용 가능한 CPU에서 파생됨).|
|   -k N     | N개의 작업이 실패할 때까지 계속 수행됩니다(기본값 = 1)|
|   -l N     | 부하 평균이 N보다 큰 경우 새 작업을 시작하지 않습니다.|
|   -n       | 시험 실행을 수행합니다(명령을 실행하지 않고 성공한 것처럼 작동함)|
|   -v       | 빌드하는 동안 모든 명령줄을 표시합니다.|
|   -d MODE  | 디버깅을 사용하도록 설정합니다(-d list를 사용하여 모드를 나열함).|
|   -t TOOL  | 하위 도구를 실행합니다(-t list를 사용하여 하위 도구를 나열함). 최상위 옵션을 종료합니다. 추가 플래그가 도구에 전달됩니다.|
|   -w FLAG  | 경고를 조정합니다(-w list를 사용하여 경고를 표시함).|

## <a name="inherited-environments"></a>상속된 환경

 `CMakeSettings.json`은 상속된 환경을 지원합니다. 이 기능을 사용하면 (1) 기본 환경을 상속하고, (2) 실행될 때 CMake.exe에 전달되는 사용자 지정 환경 변수를 만들 수 있습니다.

```json
  "inheritEnvironments": [ "msvc_x64_x64" ]
```

위의 예제는 **-arch=amd64 -host_arch=amd64** 인수를 사용하여 **VS 2017용 개발자 명령 프롬프트**를 실행하는 것과 같습니다.

다음 표는 기본값을 보여줍니다.

|컨텍스트 이름|설명|
|-----------|-----------------|
|vsdev|기본 Visual Studio 환경|
|msvc_x86|x86 도구를 사용하여 x86용으로 컴파일|
|msvc_arm| x86 도구를 사용하여 ARM용으로 컴파일|
|msvc_arm64|x86 도구를 사용하여 ARM64용으로 컴파일|
|msvc_x86_x64|x86 도구를 사용하여 AMD64용으로 컴파일|
|msvc_x64_x64|64비트 도구를 사용하여 AMD64용으로 컴파일|
|msvc_arm_x64|64비트 도구를 사용하여 ARM용으로 컴파일|
|msvc_arm64_x64|64비트 도구를 사용하여 ARM64용으로 컴파일|

### <a name="custom-environment-variables"></a>사용자 지정 환경 변수

`CMakeSettings.json`에서는 **환경** 속성에서 전역적으로 또는 구성별로 사용자 지정 환경 변수를 정의할 수 있습니다. 다음 예제에서는 x86-Debug 및 x64-Debug 구성 모두에서 상속된 하나의 **BuildDir** 전역 변수를 정의합니다. 각 구성에서 변수를 사용하여 해당 구성에 대한 **buildRoot** 속성 값을 지정합니다. 또한 각 구성에서 **inheritEnvironments** 속성을 사용하여 해당 구성에만 적용되는 변수를 지정하는 방법도 참조하세요.

```json
{
  // The "environments" property is an array of key value pairs of the form
  // { "EnvVar1": "Value1", "EnvVar2": "Value2" }
  "environments": [
    {
      "BuildDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\build",
    }
  ],

  "configurations": [
    {
      "name": "x86-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      // Inherit the defaults for using the MSVC x86 compiler.
      "inheritEnvironments": [ "msvc_x86" ],
      "buildRoot": "${env.BuildDir}\\${name}"    },
    {
      "name": "x64-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      // Inherit the defaults for using the MSVC x64 compiler.
      "inheritEnvironments": [ "msvc_x64" ],
      "buildRoot": "${env.BuildDir}\\${name}"
    }
  ]
}
```

다음 예제에서 x86 디버그 구성은 **BuildDir** 속성에 대한 자체 값을 정의합니다. 이 값은 **BuildRoot**가 `D:\custom-builddir\x86-Debug`로 평가하도록 글로벌 **BuildDir** 속성이 설정한 값을 재정의합니다.

```json
{
  "environments": [
    {
      "BuildDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}",
    }
  ],

  "configurations": [
    {
      "name": "x86-Debug",

      // The syntax for this property is the same as the global one above.
      "environments": [
        {
          // Replace the global property entirely.
          "BuildDir": "D:\\custom-builddir",
        }
      ],

      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x86" ],
      // Evaluates to "D:\custom-builddir\x86-Debug"
      "buildRoot": "${env.BuildDir}\\${name}"
    },
    {
      "name": "x64-Debug",

      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x64" ],
      // Since this configuration doesn’t modify BuildDir, it inherits
      // from the one defined globally.
      "buildRoot": "${env.BuildDir}\\${name}"
    }
  ]
}
```

## <a name="see-also"></a>참고 항목

[Visual Studio의 CMake 프로젝트](cmake-projects-in-visual-studio.md)<br/>
[Linux CMake 프로젝트 구성](../linux/cmake-linux-project.md)<br/>
[원격 Linux 컴퓨터에 연결](../linux/connect-to-your-remote-linux-computer.md)<br/>
[CMake 디버깅 세션 구성](configure-cmake-debugging-sessions.md)<br/>
[Linux 프로젝트 배포, 실행 및 디버그](../linux/deploy-run-and-debug-your-linux-project.md)<br/>
[CMake 미리 정의된 구성 참조](cmake-predefined-configuration-reference.md)<br/>
