---
title: CMakeSettings.json 스키마 참조
ms.date: 05/16/2019
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
ms.openlocfilehash: 0dcd05833af005807d874d71e8f6a07d4e738e8c
ms.sourcegitcommit: fde637f823494532314790602c2819f889706ff6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/13/2019
ms.locfileid: "67042595"
---
# <a name="cmakesettingsjson-schema-reference"></a>CMakeSettings.json 스키마 참조

**cmakesettings.json** 파일에는 Visual Studio가 CMake와 상호작용하여 지정된 플랫폼에 대한 프로젝트를 빌드하는 방법을 지정하는 정보가 포함되어 있습니다. 이 파일은 cmake.exe 환경에 대한 환경 변수 또는 인수와 같은 정보를 저장합니다. 직접 편집하거나 **CMake 설정 편집기**(Visual Studio 2019 이상)를 사용할 수 있습니다. 편집기에 대한 자세한 정보는 [Visual Studio에서 CMake 빌드 설정 사용자 지정](customize-cmake-settings.md)을 참조하세요.

## <a name="environments"></a>환경

`environments` 배열에는 컴파일러 도구 집합 "환경"을 정의하는 `object` 유형의 `items` 목록이 포함되어 있습니다. `configuration`에 변수 세트를 적용하기 위해 환경을 사용할 수 있습니다. `environments` 배열의 각 항목은 다음과 같이 구성되어 있습니다.

- `namespace`: `namespace.variable` 형식의 구성에서 해당 변수가 참조될 수 있도록 환경 이름을 지정합니다. 기본 환경 개체는 `env`라고 하며 `%USERPROFILE%`을 포함한 특정 시스템 환경 변수로 채워집니다.
- `environment`: 이 변수 그룹을 고유하게 식별합니다. 그룹이 나중에 `inheritEnvironments` 항목에 상속되도록 허용합니다.
- `groupPriority`: 이러한 변수를 평가할 때 우선순위를 지정하는 정수입니다. 숫자가 높은 항목이 먼저 계산됩니다.
- `inheritEnvironments`: 이 그룹에 상속되는 환경 세트를 지정하는 값의 배열입니다. 이 기능을 사용하면 기본 환경을 상속하고, 실행될 때 CMake.exe에 전달되는 사용자 지정 환경 변수를 만들 수 있습니다.

   ```json
   "inheritEnvironments": [ "msvc_x64_x64" ]
   ```

   위의 예제는 **VS 2017용 개발자 명령 프롬프트** 또는 **VS 2019용 개발자 명령 프롬프트**에서 **-arch=amd64 -host_arch=amd64** 인수를 사용하여 실행하는 것과 같습니다. 모든 사용자 지정 환경 또는 미리 정의된 환경을 사용할 수 있습니다.
 
  - linux_arm: 원격으로 ARM Linux를 대상으로 지정합니다.
  - linux_x64: 원격으로 x64 Linux를 대상으로 지정합니다.
  - linux_x86: 원격으로 x86 Linux를 대상으로 지정합니다.
  - msvc_arm: MSVC 컴파일러를 사용하는 ARM Windows를 대상으로 지정합니다.
  - msvc_arm_x64: 64비트 MSVC 컴파일러를 사용하는 ARM Windows를 대상으로 지정합니다.
  - msvc_arm64: MSVC 컴파일러를 사용하는 ARM64 Windows를 대상으로 지정합니다.
  - msvc_arm64_x64: 64비트 MSVC 컴파일러를 사용하는 ARM64 Windows를 대상으로 지정합니다.
  - msvc_x64: MSVC 컴파일러를 사용하는 x64 Windows를 대상으로 지정합니다.
  - msvc_x64_x64: 64비트 MSVC 컴파일러를 사용하는 x64 Windows를 대상으로 지정합니다.
  - msvc_x86: MSVC 컴파일러를 사용하는 x86 Windows를 대상으로 지정합니다.
  - msvc_x86_x64: 64비트 MSVC 컴파일러를 사용하는 x86 Windows를 대상으로 지정합니다.

## <a name="configurations"></a>구성

`configurations` 배열은 동일한 폴더의 CMakeLists.txt 파일에 적용되는 CMake 구성을 나타내는 개체로 구성됩니다. 이러한 개체를 사용하여 여러 빌드 구성을 정의하고 IDE에서 개체 사이를 편리하게 전환할 수 있습니다. 

`configuration`에는 다음과 같은 속성이 있습니다.
- `name`: 구성 이름을 지정합니다.
- `description`: 메뉴에 표시되는 이 구성의 설명입니다.
- `generator`: 이 구성에 사용할 CMake 생성기를 지정합니다. 다음 중 하나일 수 있습니다.
  
  **Visual Studio 2019만:**
  - Visual Studio 16 2019
  - Visual Studio 16 2019 Win64
  - Visual Studio 16 2019 ARM

  **Visual Studio 2017 이상**:
  - Visual Studio 15 2017
  - Visual Studio 15 2017 Win64
  - Visual Studio 15 2017 ARM
  - Visual Studio 14 2015
  - Visual Studio 14 2015 Win64
  - Visual Studio 14 2015 ARM
  - Unix 메이크파일
  - Ninja

Ninja는 유연성과 기능 대신 빠른 속도로 빌드하도록 설계되었으므로 기본값으로 설정됩니다. 그러나 일부 CMake 프로젝트는 Ninja를 사용하여 올바르게 빌드하지 못할 수도 있습니다. 이 경우 CMake에서 Visual Studio 프로젝트를 대신 생성하도록 지시할 수 있습니다.

Visual Studio 2017에서 Visual Studio 생성기를 지정하려면 주 메뉴에서 **CMake | CMake 설정 변경**을 선택하여 `CMakeSettings.json`을 엽니다. "Ninja"를 삭제하고 "V"를 입력합니다. 이렇게 하면 원하는 생성기를 선택할 수 있도록 IntelliSense가 활성화됩니다.

Visual Studio 2019에서 Visual Studio 생성기를 지정하려면 **솔루션 탐색기**에서 CMakeLists.txt 파일을 마우스 오른쪽 단추로 클릭하고 **프로젝트에 대한 CMake 설정** > **고급 설정 표시** > **CMake 생성기**를 선택합니다.

활성 구성에서 Visual Studio 생성기를 지정하면 기본적으로 `-m -v:minimal` 인수를 사용하여 MSBuild.exe가 호출됩니다. `CMakeSettings.json` 파일 내에서 빌드를 사용자 지정하려면 `buildCommandArgs` 속성을 통해 빌드 시스템에 전달할 추가 [MSBuild 명령줄 인수](../build/reference/msbuild-visual-cpp-overview.md)를 지정할 수 있습니다.

   ```json
   "buildCommandArgs": "-m:8 -v:minimal -p:PreferredToolArchitecture=x64"
   ```

- `configurationType`: 선택한 생성기의 빌드 형식 구성을 지정합니다. 다음 중 하나일 수 있습니다.
 
  - 디버그
  - Release
  - MinSizeRel
  - RelWithDebInfo
 
- `inheritEnvironments`: 이 구성을 사용하는 하나 이상의 컴파일러 환경을 지정합니다. 모든 사용자 지정 환경 또는 미리 정의된 환경 중 하나일 수 있습니다.
- `buildRoot`: CMake가 선택한 생성기에 대한 빌드 스크립트를 생성하는 디렉터리를 지정합니다.  **-DCMAKE_BINARY_DIR** 스위치에 매핑하고 CMake 캐시가 만들어질 위치를 지정합니다. 폴더가 없으면 만듭니다. 지원되는 매크로는 `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`입니다.
- `installRoot`: CMake가 선택한 생성기에 대한 설치 대상을 생성하는 디렉터리를 지정합니다. 지원되는 매크로에는 `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`이 포함됩니다.
- `cmakeCommandArgs`: 캐시를 생성하기 위해 호출될 때 CMake로 전달되는 추가 명령줄 옵션을 지정합니다.
- `cmakeToolchain`: 도구 체인 파일을 지정합니다. 이는 -DCMAKE_TOOLCHAIN_FILE을 사용하여 CMake에 전달됩니다."
- `buildCommandArgs`: --빌드 -- 후 CMake로 전달되는 네이티브 빌드 스위치를 지정합니다. 예를 들어 Ninja 생성기를 사용하는 경우 -v를 전달하면 Ninja에서 명령줄을 출력하도록 강제합니다. Ninja 명령에 대한 자세한 정보는 [Ninja 명령줄 인수](#ninja)를 참조하세요.
- `ctestCommandArgs`: 테스트 실행 시 CTest에 전달되는 추가 명령줄 옵션을 지정합니다."
- `codeAnalysisRuleset`: 코드 분석을 실행할 때 사용할 규칙 집합을 지정합니다. 이는 Visual Studio에서 설치한 규칙 집합 파일의 전체 경로 또는 파일 이름이 될 수 있습니다.
- `intelliSenseMode`: intellisense 정보 컴퓨팅에 사용되는 모드를 지정합니다." 다음 중 하나일 수 있습니다.
 
  - windows-msvc-x86
  - windows-msvc-x64
  - windows-msvc-arm
  - windows-msvc-arm64
  - android-clang-x86
  - android-clang-x64
  - android-clang-arm
  - android-clang-arm64
  - ios-clang-x86
  - ios-clang-x64
  - ios-clang-arm
  - ios-clang-arm64
  - windows-clang-x86
  - windows-clang-x64
  - windows-clang-arm
  - windows-clang-arm64
  - linux-gcc-x86
  - linux-gcc-x64
  - linux-gcc-arm"

- `cacheRoot`: CMake 캐시의 경로를 지정합니다. 이 디렉터리에는 기존 CMakeCache.txt 파일이 포함되어야 합니다.

### <a name="additional-settings-for-cmake-linux-projects"></a>CMake Linux 프로젝트에 대한 추가 설정 

- `remoteMachineName`: CMake, 빌드 및 디버거를 호스팅하는 원격 Linux 머신의 이름을 지정합니다. 새 Linux 머신을 추가하기 위해 연결 관리자를 사용합니다. 지원되는 매크로에는 `${defaultRemoteMachineName}`이 포함됩니다.
- `remoteCopySourcesOutputVerbosity`: 원격 머신에 대한 소스 복사 작업의 세부 정보 표시 수준을 지정합니다. ""Normal", "Verbose" 또는 "Diagnostic" 중 하나일 수 있습니다.
- `remoteCopySourcesConcurrentCopies`: 소스 (sftp에만 해당) 원격 컴퓨터를 동기화 할 때 사용 되는 동시 복사본 수를 지정 합니다.
- `remoteCopySourcesMethod`: 원격 머신에 파일을 복사하는 방법을 지정합니다. "rsync" 또는 "sftp"일 수 있습니다.
- `remoteCMakeListsRoot`: CMake 프로젝트를 포함하는 원격 머신의 디렉터리를 지정합니다. 지원되는 매크로에는 `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`이 포함됩니다.
- `remoteBuildRoot`: CMake가 선택한 생성기에 대한 빌드 스크립트를 생성하는 원격 머신의 디렉터리를 지정합니다. 지원되는 매크로에는 `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`이 포함됩니다.
- `remoteInstallRoot`: CMake가 선택한 생성기에 대한 설치 대상을 생성하는 원격 머신의 디렉터리를 지정합니다. 지원되는 매크로에는 `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}` 및 `${env.VARIABLE}`이 포함됩니다. 여기서 `VARIABLE`은 시스템, 사용자 또는 세션 수준에서 정의된 환경 변수입니다.
- `remoteCopySources`: Visual Studio가 원격 머신에 소스 파일을 복사해야 하는지 여부를 지정하는 `boolean`입니다. 기본값은 true입니다. 파일 동기화를 직접 관리하는 경우 false로 설정합니다.
- `remoteCopyBuildOutput`: 원격 시스템에서 빌드 출력 파일을 복사할지 여부를 지정하는 `boolean`입니다.
- `rsyncCommandArgs`: rsync에 전달되는 추가 명령줄 옵션 세트를 지정합니다.
- `remoteCopySourcesExclusionList`: 소스 파일을 복사할 때 제외할 경로 목록을 지정하는 `array`입니다. 경로는 파일/디렉터리의 이름이거나 복사본의 루트와 관련된 경로일 수 있습니다. 와일드 카드 \\\"*\\\" 및 \\\"?\\\"은 glob 패턴 일치에 사용할 수 있습니다.
- `cmakeExecutable`: 파일 이름과 확장명이 포함된 CMake 프로그램 실행 파일의 전체 경로를 지정합니다.
- `remotePreGenerateCommand`: CMakeLists.txt 파일을 구문 분석하기 위해 CMake를 실행하기 전에 실행할 명령을 지정합니다.
- `remotePrebuildCommand`: 빌드 전 원격 머신에서 실행하는 명령을 지정합니다.
- `remotePostbuildCommand`: 빌드 후 원격 머신에서 실행하는 명령을 지정합니다.
- `variables`: **-D** *_이름_=_값_* 으로 CMake에 전달되는 CMake 변수의 이름 값 쌍이 포함됩니다. CMake 프로젝트 빌드 지침에서 CMake 캐시 파일에 변수를 직접 추가하도록 지정하는 경우 여기에 대신 추가하는 것이 좋습니다. 다음 예제에서는 14.14.26428 MSVC 도구 세트에 대한 이름-값 쌍을 지정하는 방법을 보여줍니다.

```json
"variables": [
    {
      "name": "CMAKE_CXX_COMPILER",
      "value": "C:/Program Files (x86)/Microsoft Visual Studio/157/Enterprise/VC/Tools/MSVC/14.14.26428/bin/HostX86/x86/cl.exe",
      "type": "FILEPATH"
    },
    {
      "name": "CMAKE_C_COMPILER",
      "value": "C:/Program Files (x86)/Microsoft Visual Studio/157/Enterprise/VC/Tools/MSVC/14.14.26428/bin/HostX86/x86/cl.exe",
      "type": "FILEPATH"
    }
  ]
```

`"type"`을 정의하지 않으면 기본적으로 "STRING" 형식을 가정합니다.

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
          "BuildDir": "D:\\custom-builddir"
          // This environment does not specify a namespace, hence by default "env" will be assumed.
          // "namespace" : "name" would require that this variable be referenced with "${name.BuildDir}".
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

## <a name="ninja"></a> Ninja 명령줄 인수

대상이 지정되지 않으면 'default(기본)' 대상을 빌드합니다.

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




