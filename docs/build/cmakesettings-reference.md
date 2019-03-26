---
title: CMakeSettings.json 스키마 참조
ms.date: 03/05/2019
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
ms.openlocfilehash: 893bc5c8efe3fdae80a4a0de8204d391baa63d07
ms.sourcegitcommit: 42e65c171aaa17a15c20b155d22e3378e27b4642
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58356116"
---
# <a name="cmakesettingsjson-schema-reference"></a>CMakeSettings.json 스키마 참조

합니다 **cmakesettings.json**' 파일에 지정된 된 플랫폼에 대 한 프로젝트를 빌드하려면 CMake를 사용 하 여 Visual Studio 작용 하는 방법을 지정 하는 정보가 포함 됩니다. 이 파일을 사용하여 cmake.exe 환경에 대한 환경 변수 또는 인수와 같은 정보를 저장합니다.

## <a name="environments"></a>환경

`environments` 배열에는 "환경"을 정의하는 `object` 유형의 `items` 목록이 포함되어 있습니다. `configuration`에 변수 세트를 적용하기 위해 환경을 사용할 수 있습니다. `environments` 배열의 각 항목은 다음과 같이 구성되어 있습니다.

- `namespace`: `namespace.variable` 형식의 구성에서 해당 변수가 참조될 수 있도록 환경 이름을 지정합니다. 기본 환경 개체는 `env`라고 하며 `%USERPROFILE%`을 포함한 특정 시스템 환경 변수로 채워집니다.
- `environment`: 이 변수 그룹을 고유하게 식별합니다. 그룹이 나중에 `inheritEnvironments` 항목에 상속되도록 허용합니다.
- `groupPriority`: 이러한 변수를 평가할 때 우선순위를 지정하는 정수입니다. 숫자가 높은 항목이 먼저 계산됩니다.
- `inheritEnvironments`: 이 그룹에 상속되는 환경 세트를 지정하는 값의 배열입니다. 모든 사용자 지정 환경 또는 미리 정의된 환경을 사용할 수 있습니다.
 
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

  - Visual Studio 15 2017
  - Visual Studio 15 2017 Win64
  - Visual Studio 15 2017 ARM
  - Visual Studio 14 2015
  - Visual Studio 14 2015 Win64
  - Visual Studio 14 2015 ARM
  - Unix 메이크파일
  - Ninja

- `configurationType`: 선택한 생성기의 빌드 형식 구성을 지정합니다. 다음 중 하나일 수 있습니다.
 
  - 디버그
  - Release
  - MinSizeRel
  - RelWithDebInfo
 
- `inheritEnvironments`: 이 구성을 사용하는 하나 이상의 환경을 지정합니다. 모든 사용자 지정 환경 또는 미리 정의된 환경 중 하나일 수 있습니다.
- `buildRoot`: CMake가 선택한 생성기에 대한 빌드 스크립트를 생성하는 디렉터리를 지정합니다. 지원되는 매크로에는 `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`이 포함됩니다."
- `installRoot`: CMake가 선택한 생성기에 대한 설치 대상을 생성하는 디렉터리를 지정합니다. 지원되는 매크로에는 `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`이 포함됩니다."
- `cmakeCommandArgs`: 캐시를 생성하기 위해 호출될 때 CMake로 전달되는 추가 명령줄 옵션을 지정합니다."
- `cmakeToolchain`: 도구 체인 파일을 지정합니다. 이는 -DCMAKE_TOOLCHAIN_FILE을 사용하여 CMake에 전달됩니다."
- `buildCommandArgs`: --빌드 -- 후 CMake로 전달되는 네이티브 빌드 스위치를 지정합니다."
- `ctestCommandArgs`: 테스트 실행 시 CTest에 전달되는 추가 명령줄 옵션을 지정합니다."
- `codeAnalysisRuleset`: 코드 분석을 실행할 때 사용할 규칙 집합을 지정합니다. 이는 Visual Studio에서 설치한 규칙 집합 파일의 전체 경로 또는 파일 이름이 될 수 있습니다."
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
- `remoteMachineName`: CMake, 빌드 및 디버거를 호스팅하는 원격 Linux 머신의 이름을 지정합니다. 새 Linux 머신을 추가하기 위해 연결 관리자를 사용합니다. 지원되는 매크로에는 `${defaultRemoteMachineName}`이 포함됩니다.
- `remoteCopySourcesOutputVerbosity`: 원격 머신에 대한 소스 복사 작업의 세부 정보 표시 수준을 지정합니다. ""Normal", "Verbose" 또는 "Diagnostic" 중 하나일 수 있습니다.
- `remoteCopySourcesConcurrentCopies`: 원격 머신에 소스를 동기화하는 동안 사용되는 동시 복사본의 수를 지정합니다.
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
- `variables`: CMake에 전달되는 변수를 -Dname1=value1 -Dname2=value2 등으로 지정하는 `array`입니다. 


