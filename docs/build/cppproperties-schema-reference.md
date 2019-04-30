---
title: CppProperties.json 스키마 참조
ms.date: 03/21/2019
helpviewer_keywords:
- CMake in Visual C++
ms.openlocfilehash: 43ffa0e92649fe233c6a743d4b64a2749cb28f5a
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64341637"
---
# <a name="cpppropertiesjson-schema-reference"></a>CppProperties.json 스키마 참조

CMake를 사용하지 않는 폴더 열기 프로젝트는 `CppProperties.json` 파일에 구성 설정을 저장할 수 있습니다. (CMake 프로젝트는 [CMakeSettings.json](customize-cmake-settings.md) 파일을 사용합니다.) Visual Studio IDE는 IntelliSense 및 코드 탐색에 `CppProperties.json`을 사용합니다. 구성은 이름/값 쌍으로 구성되며 #include 경로, 컴파일러 스위치 및 기타 매개 변수를 정의합니다. 


## <a name="default-configurations"></a>기본 구성

Visual Studio는 x86 및 x64 디버그와 릴리스에 대해 미리 정의된 구성을 제공합니다. 기본적으로 프로젝트는 `CppProperties.json`에 x86-디버그 구성이 있습니다. 새 구성을 추가하려면 **솔루션 탐색기**에서 `CppProperties.json` 파일을 마우스 오른쪽 단추로 클릭하고 **구성 추가**를 선택합니다.

![폴더 열기 구성 추가](media/open-folder-add-config.png "폴더 열기 새 구성 추가")

기본 구성은 다음과 같습니다.

```json
{
  "configurations": [
    {
      "inheritEnvironments": [
        "msvc_x86"
      ],
      "name": "x86-Debug",
      "includePath": [
        "${env.INCLUDE}",
        "${workspaceRoot}\\**"
      ],
      "defines": [
        "WIN32",
        "_DEBUG",
        "UNICODE",
        "_UNICODE"
      ],
      "intelliSenseMode": "windows-msvc-x86"
    },
    {
      "inheritEnvironments": [
        "msvc_x86"
      ],
      "name": "x86-Release",
      "includePath": [
        "${env.INCLUDE}",
        "${workspaceRoot}\\**"
      ],
      "defines": [
        "WIN32",
        "NDEBUG",
        "UNICODE",
        "_UNICODE"
      ],
      "intelliSenseMode": "windows-msvc-x86"
    },
    {
      "inheritEnvironments": [
        "msvc_x64"
      ],
      "name": "x64-Debug",
      "includePath": [
        "${env.INCLUDE}",
        "${workspaceRoot}\\**"
      ],
      "defines": [
        "WIN32",
        "_DEBUG",
        "UNICODE",
        "_UNICODE"
      ],
      "intelliSenseMode": "windows-msvc-x64"
    },
    {
      "inheritEnvironments": [
        "msvc_x64"
      ],
      "name": "x64-Release",
      "includePath": [
        "${env.INCLUDE}",
        "${workspaceRoot}\\**"
      ],
      "defines": [
        "WIN32",
        "NDEBUG",
        "UNICODE",
        "_UNICODE"
      ],
      "intelliSenseMode": "windows-msvc-x64"
    }
  ]
}
```
허용되는 값 세트가 있는 속성의 경우 코드 편집기는 다음을 입력할 때 사용 가능한 옵션을 보여줍니다.

![폴더 열기 IntelliSense](media/open-folder-intellisense-mode.png "폴더 열기 IntelliSense")



## <a name="configuration-properties"></a>구성 속성

구성에는 다음 속성 중 하나가 있을 수 있습니다.

|||
|-|-|
|`name`|C++ 구성 드롭다운에 표시되는 구성 이름|
|`includePath`|include 경로에 지정해야 하는 폴더 목록(대부분의 컴파일러에서 /I에 매핑됨)|
|`defines`|정의해야 하는 매크로 목록(대부분의 컴파일러에서 /D에 매핑됨)|
|`compilerSwitches`|IntelliSense 동작에 영향을 줄 수 있는 하나 이상의 추가 스위치|
|`forcedInclude`|모든 컴파일 단위에 자동으로 포함될 헤더(MSVC에서 /FI에 매핑되거나 clang에서 -include에 매핑됨)|
|`undefines`|정의되지 않은 매크로 목록(MSVC에서 /U에 매핑됨)|
|`intelliSenseMode`|사용할 IntelliSense 엔진. MSVC, gcc 또는 Clang에 대한 아키텍처 특정 변형을 지정할 수 있습니다.<br/><br/>-windows-msvc-x86 (기본값)<br/>- windows-msvc-x64<br/>- msvc-arm<br/>- windows-clang-x86<br/>- windows-clang-x64<br/>- windows-clang-arm<br/>- Linux-x64<br/>- Linux-x86<br/>- Linux-arm<br/>- gccarm|

참고: 값 `msvc-x86` 고 `msvc-x64` 레거시의 이유로 지원 됩니다. 사용 하십시오는 `windows-msvc*` 변형 합니다.

## <a name="custom-configurations"></a>사용자 지정 구성


`CppProperties.json`의 기본 구성을 사용자 지정하거나 새 구성을 만들 수 있습니다. 각 구성은 드롭다운에 표시됩니다.

```json
{
  "configurations": [
    {
      "name": "Windows",
      ...
    },
    {
      "name": "with EXTERNAL_CODECS",
      ...
    }
  ]
}
```

## <a name="system-environment-variables"></a>시스템 환경 변수 

 `CppProperties.json`은 include 경로 및 다른 속성 값에 대한 시스템 환경 변수 확장을 지원합니다. 구문은 `%FOODIR%` 환경 변수를 확장하는 `${env.FOODIR}`입니다. 다음 시스템 정의 변수도 지원됩니다.

|변수 이름|설명|
|-----------|-----------------|
|vsdev|기본 Visual Studio 환경|
|msvc_x86|x86 도구를 사용하여 x86용으로 컴파일|
|msvc_arm|x86 도구를 사용하여 ARM용으로 컴파일|
|msvc_arm64|x86 도구를 사용하여 ARM64용으로 컴파일|
|msvc_x86_x64|x86 도구를 사용하여 AMD64용으로 컴파일|
|msvc_x64_x64|64비트 도구를 사용하여 AMD64용으로 컴파일|
|msvc_arm_x64|64비트 도구를 사용하여 ARM용으로 컴파일|
|msvc_arm64_x64|64비트 도구를 사용하여 ARM64용으로 컴파일|

Linux 워크로드가 설치되면 원격으로 Linux 및 WSL을 대상으로 지정하는 데 사용할 수 있는 환경은 다음과 같습니다.

|변수 이름|설명|
|-----------|-----------------|
|linux_x86|원격으로 x86 Linux를 대상 지정|
|linux_x64|원격으로 x64 Linux를 대상 지정|
|linux_arm|원격으로 ARM Linux를 대상 지정|

## <a name="custom-environment-variables"></a>사용자 지정 환경 변수

사용자 지정 환경 변수는 `CppProperties.json`에서 전역적으로 또는 구성별로 정의할 수 있습니다. 다음 예제에서는 기본 및 사용자 지정 환경 변수를 선언하고 사용하는 방법을 보여 줍니다. 전역 **environments** 속성은 모든 구성에서 사용할 수 있는 **INCLUDE**라는 변수를 선언합니다.

```json
{
  // The "environments" property is an array of key value pairs of the form
  // { "EnvVar1": "Value1", "EnvVar2": "Value2" }
  "environments": [
    {
      "INCLUDE": "${workspaceRoot}\src\includes"
    }
  ],

  "configurations": [
    {
      "inheritEnvironments": [
        // Inherit the MSVC 32-bit environment and toolchain.
        "msvc_x86"
      ],
      "name": "x86",
      "includePath": [
        // Use the include path defined above.
        "${env.INCLUDE}"
      ],
      "defines": [ "WIN32", "_DEBUG", "UNICODE", "_UNICODE" ],
      "intelliSenseMode": "windows-msvc-x86"
    },
    {
      "inheritEnvironments": [
        // Inherit the MSVC 64-bit environment and toolchain.
        "msvc_x64"
      ],
      "name": "x64",
      "includePath": [
        // Use the include path defined above.
        "${env.INCLUDE}"
      ],
      "defines": [ "WIN32", "_DEBUG", "UNICODE", "_UNICODE" ],
      "intelliSenseMode": "windows-msvc-x64"
    }
  ]
}
```
## <a name="per-configuration-environment-variables"></a>구성별 환경 변수

또한 구성 내에 **environments** 속성을 정의하여 해당 구성에만 적용하고 동일한 이름의 전역 변수를 재정의할 수 있습니다. 다음 예제에서 x64 구성은 전역 값을 재정의하는 지역 **INCLUDE** 변수를 정의합니다.

```json
{
  "environments": [
    {
      "INCLUDE": "${workspaceRoot}\src\includes"
    }
  ],

  "configurations": [
    {
      "inheritEnvironments": [
        "msvc_x86"
      ],
      "name": "x86",
      "includePath": [
        // Use the include path defined in the global environments property.
        "${env.INCLUDE}"
      ],
      "defines": [ "WIN32", "_DEBUG", "UNICODE", "_UNICODE" ],
      "intelliSenseMode": "windows-msvc-x86"
    },
    {
      "environments": [
        {
          // Append 64-bit specific include path to env.INCLUDE.
          "INCLUDE": "${env.INCLUDE};${workspaceRoot}\src\includes64"
        }
      ],

      "inheritEnvironments": [
        "msvc_x64"
      ],
      "name": "x64",
      "includePath": [
        // Use the include path defined in the local environments property.
        "${env.INCLUDE}"
      ],
      "defines": [ "WIN32", "_DEBUG", "UNICODE", "_UNICODE" ],
      "intelliSenseMode": "windows-msvc-x64"
    }
  ]
}
```

모든 사용자 지정 및 기본 환경 변수는 `tasks.vs.json` 및 `launch.vs.json`에서도 사용할 수 있습니다.

#### <a name="build-in-macros"></a>기본 제공 매크로

`CppProperties.json` 내에서 액세스할 수 있는 기본 제공 매크로는 다음과 같습니다.

|||
|-|-|
|`${workspaceRoot}`| 작업 영역 폴더의 전체 경로|
|`${projectRoot}`| `CppProperties.json`이 있는 폴더의 전체 경로|
|`${vsInstallDir}`| 실행되는 VS 2017 인스턴스가 설치된 폴더의 전체 경로|

예를 들어 프로젝트에 include 폴더가 있고 windows.h 및 Windows SDK의 다른 일반 헤더가 포함되어 있으면, `CppProperties.json` 구성 파일을 다음과 같은 include로 업데이트할 수 있습니다.

```json
{
  "configurations": [
    {
      "name": "Windows",
      "includePath": [
        // local include folder
        "${workspaceRoot}\include",
        // Windows SDK and CRT headers
        "${env.WindowsSdkDir}\include\${env.WindowsSDKVersion}\ucrt",
        "${env.NETFXSDKDir}\include\um",
        "${env.WindowsSdkDir}\include\${env.WindowsSDKVersion}\um",
        "${env.WindowsSdkDir}\include\${env.WindowsSDKVersion}\shared",
        "${env.VCToolsInstallDir}\include"
      ]
    }
  ]
}
```

> [!Note]
> `%WindowsSdkDir%` 및 `%VCToolsInstallDir%`은 전역 환경 변수로 설정되지 않으므로 devenv.exe는 이러한 변수를 정의하는 “VS 2017용 개발자 명령 프롬프트”에서 시작해야 합니다.

## <a name="troubleshoot-intellisense-errors"></a>IntelliSense 오류 문제 해결

include 경로 누락으로 인한 IntelliSense 오류 문제를 해결하려면, **오류 목록**을 열고, 출력을 "IntelliSense 전용" 및 E1696 오류 코드("소스 파일을 열 수 없습니다. ...")로 필터링합니다.



