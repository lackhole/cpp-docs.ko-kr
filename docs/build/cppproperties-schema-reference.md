---
title: CppProperties.json 스키마 참조
ms.date: 08/09/2019
helpviewer_keywords:
- CppProperties.json file [C++]
ms.openlocfilehash: 06029157b4b3826bc9c34a4434ab390f3eaa5a44
ms.sourcegitcommit: ace42fa67e704d56d03c03745b0b17d2a5afeba4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69975936"
---
# <a name="cpppropertiesjson-schema-reference"></a>CppProperties.json 스키마 참조

CMake를 사용 하지 않는 Open Folder 프로젝트는 *cppproperties.json* 파일에 IntelliSense의 프로젝트 구성 설정을 저장할 수 있습니다. (CMake 프로젝트는 [CMakeSettings.json](customize-cmake-settings.md) 파일을 사용합니다.) 구성은 이름/값 쌍으로 구성되며 #include 경로, 컴파일러 스위치 및 기타 매개 변수를 정의합니다. 열린 폴더 프로젝트에 구성을 추가 하는 방법에 대 한 자세한 내용은 [를 C++ ](open-folder-projects-cpp.md) 참조 하십시오.

## <a name="configuration-properties"></a>구성 속성

구성에는 다음 속성 중 하나가 있을 수 있습니다.

|||
|-|-|
|`inheritEnvironments`| 이 구성에 적용 되는 환경을 지정 합니다.|
|`name`|C++ 구성 드롭다운에서 표시 되는 구성 이름입니다.|
|`includePath`|포함 경로에 지정 되어야 하는 쉼표로 구분 된 폴더 목록 (대부분의 컴파일러에 대해/I에 매핑됨)|
|`defines`|정의해야 하는 매크로 목록(대부분의 컴파일러에서 /D에 매핑됨)|
|`compilerSwitches`|IntelliSense 동작에 영향을 줄 수 있는 하나 이상의 추가 스위치|
|`forcedInclude`|모든 컴파일 단위에 자동으로 포함될 헤더(MSVC에서 /FI에 매핑되거나 clang에서 -include에 매핑됨)|
|`undefines`|정의되지 않은 매크로 목록(MSVC에서 /U에 매핑됨)|
|`intelliSenseMode`|사용할 IntelliSense 엔진. MSVC, gcc 또는 Clang에 대해 미리 정의 된 아키텍처 관련 변형 중 하나를 지정할 수 있습니다.|
|`environments`|명령 프롬프트에서 환경 변수 처럼 동작 하 고 $ {env.<VARIABLE>}를 사용 하 여 액세스 하는 사용자 정의 변수 집합 매크로나.|

### <a name="intellisensemode-values"></a>intelliSenseMode 값

코드 편집기는 입력을 시작할 때 사용할 수 있는 옵션을 보여 줍니다.

![폴더 열기 IntelliSense](media/open-folder-intellisense-mode.png "폴더 열기 IntelliSense")

지원 되는 값은 다음과 같습니다.

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
- linux-gcc-arm

참고: `msvc-x86` 및 `msvc-x64` 값은 레거시의 목적으로만 지원됩니다. 대신 variant `windows-msvc-*` 를 사용 하십시오.

## <a name="pre-defined-environments"></a>미리 정의 된 환경

Visual Studio에서는 해당 개발자 명령 프롬프트에 매핑되는 다음과 C++ 같은 미리 정의 된 환경을 Microsoft에 제공 합니다. 이러한 환경 중 하나를 상속 하는 경우 전역 속성 `env` 을 사용 하 여 모든 환경 변수를 참조할 수 있습니다. $ {env.\< 변수 >}.

|변수 이름|Description|
|-----------|-----------------|
|vsdev|기본 Visual Studio 환경|
|msvc_x86|x86 도구를 사용하여 x86용으로 컴파일|
|msvc_x64|64비트 도구를 사용하여 AMD64용으로 컴파일|
|msvc_arm|x86 도구를 사용하여 ARM용으로 컴파일|
|msvc_arm64|x86 도구를 사용하여 ARM64용으로 컴파일|
|msvc_x86_x64|x86 도구를 사용하여 AMD64용으로 컴파일|
|msvc_arm_x64|64비트 도구를 사용하여 ARM용으로 컴파일|
|msvc_arm64_x64|64비트 도구를 사용하여 ARM64용으로 컴파일|

Linux 워크로드가 설치되면 원격으로 Linux 및 WSL을 대상으로 지정하는 데 사용할 수 있는 환경은 다음과 같습니다.

|변수 이름|Description|
|-----------|-----------------|
|linux_x86|원격으로 x86 Linux를 대상 지정|
|linux_x64|원격으로 x64 Linux를 대상 지정|
|linux_arm|원격으로 ARM Linux를 대상 지정|

## <a name="user_defined_environments"></a>사용자 정의 환경

선택적으로 `environments` 속성을 사용 하 여 전역적으로 또는 구성 별로 *cppproperties.json* 의 변수 집합을 정의할 수 있습니다. 이러한 변수는 열린 폴더 프로젝트의 컨텍스트에서 환경 변수 처럼 동작 하며 $ {env를 사용 하 여 액세스할 수 있습니다.\< *작업. json* 및 시작과 *json* 의 변수 >} 구문 (여기서 정의 된 경우). 그러나 Visual Studio에서 내부적으로 사용 하는 명령 프롬프트에서 실제 환경 변수로 반드시 설정 해야 하는 것은 아닙니다.

환경을 사용 하는 경우 환경이 동일한 구성의 일부로 정의 된 경우에 `inheritsEnvironments` 도 속성에서 지정 해야 합니다. 속성은 `environment` 환경 이름을 지정 합니다. 다음 예제에서는 MSYS2 설치에서 GCC에 대해 IntelliSense를 사용 하도록 설정 하는 샘플 구성을 보여 줍니다. 구성에서 `mingw_64` 환경을 정의 하 고 상속 하는 방법 및 속성에서 `includePath` `INCLUDE` 변수에 액세스할 수 있는 방법을 확인 합니다.

```json
"configurations": [
    {

      "inheritEnvironments": [
        "mingw_64"
      ],
      "name": "Mingw64",
      "includePath ,": [
        "${env.INCLUDE}",
        "${workspaceRoot}\\**",
      ],
      "intelliSenseMode": "linux-gcc-x64",
      "environments": [
        {
          "MINGW64_ROOT": "C:\\msys64\\mingw64",
          "BIN_ROOT": "${env.MINGW64_ROOT}\\bin",
          "FLAVOR": "x86_64-w64-mingw32",
          "TOOLSET_VERSION": "9.1.0",
          "PATH": "${env.MINGW64_ROOT}\\bin;${env.MINGW64_ROOT}\\..\\usr\\local\\bin;${env.MINGW64_ROOT}\\..\\usr\\bin;${env.MINGW64_ROOT}\\..\\bin;${env.PATH}",
          "INCLUDE": "${env.MINGW64_ROOT}\\include\\c++\\${env.TOOLSET_VERSION};${env.MINGW64_ROOT}\\include\\c++\\${env.TOOLSET_VERSION}\\tr1;${env.MINGW64_ROOT}\\include\\c++\\${env.TOOLSET_VERSION}\\${env.FLAVOR};",
          "environment": "mingw_64"
        }
      ]
    }
  ]
```

구성 내에서 **환경** 속성을 정의 하는 경우 동일한 이름의 모든 전역 변수를 재정의 합니다.

## <a name="built-in-macros"></a>기본 제공 매크로

*Cppproperties.json*내에서 다음 기본 제공 매크로에 액세스할 수 있습니다.

|||
|-|-|
|`${workspaceRoot}`| 작업 영역 폴더의 전체 경로입니다.|
|`${projectRoot}`| Cppproperties.json가 배치 되는 폴더의 전체 경로입니다 *.*|
|`${env.vsInstallDir}`| 실행 중인 Visual Studio 인스턴스가 설치 된 폴더의 전체 경로입니다.|

### <a name="example"></a>예제

프로젝트에 포함 폴더가 있고 Windows SDK의 다른 공용 헤더 도 포함 하는 경우 다음과 같은 내용을 포함 하는 *cppproperties.json* 구성 파일을 업데이트할 수 있습니다.

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
> `%WindowsSdkDir%` 및 `%VCToolsInstallDir%`은 글로벌 환경 변수로 설정되지 않으므로 devenv.exe는 이러한 변수를 정의하는 개발자 명령 프롬프트에서 시작해야 합니다. (Windows 시작 메뉴에 "개발자" 입력)

## <a name="troubleshoot-intellisense-errors"></a>IntelliSense 오류 문제 해결

원하는 IntelliSense가 표시 되지 않으면 **도구** > **옵션** > **텍스트 편집기** >  > **C/C++** **고급** 으로 이동 하 여 문제를 해결할 수 있습니다. **로깅 사용** 을 **true**로 설정 합니다. 먼저 **로깅 수준을** 5로 설정 하 고 **필터** 를 8로 설정 해 봅니다.

![진단 로깅](media/diagnostic-logging.png)

출력은 **출력 창** 로 파이프 되며 다음에서 출력 표시를 선택할 **때 표시 됩니다. 표시 C++** 출력에는 IntelliSense에서 사용 하려는 실제 포함 경로 목록이 포함 됩니다. 경로가 *cppproperties.json*의 경로와 일치 하지 않으면 폴더를 닫고 캐시 된 검색 데이터를 포함 하는 vs 하위 폴더를 삭제 하십시오 *.*

include 경로 누락으로 인한 IntelliSense 오류 문제를 해결하려면, **오류 목록**을 열고, 출력을 "IntelliSense 전용" 및 E1696 오류 코드("소스 파일을 열 수 없습니다. ...")로 필터링합니다.
