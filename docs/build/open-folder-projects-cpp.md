---
title: Visual Studio에서 C++ 빌드 시스템에 대해 폴더 열기 지원
ms.date: 12/02/2019
helpviewer_keywords:
- Open Folder Projects in Visual Studio
ms.assetid: abd1985e-3717-4338-9e80-869db5435175
ms.openlocfilehash: 8342060e7286c1089312874199bf341ec36bed62
ms.sourcegitcommit: 6c1960089b92d007fc28c32af1e4bef0f85fdf0c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/31/2019
ms.locfileid: "75556701"
---
# <a name="open-folder-support-for-c-build-systems-in-visual-studio"></a>Visual Studio에서 C++ 빌드 시스템에 대해 폴더 열기 지원

::: moniker range="vs-2015"

폴더 열기 기능은 Visual Studio 2017 이상에서 사용할 수 있습니다.

::: moniker-end

::: moniker range=">=vs-2017"

Visual Studio 2017 이상에서 "폴더 열기" 기능을 통해 소스 파일의 폴더를 열고 IntelliSense, 검색, 리팩터링, 디버깅 등의 지원을 통해 코딩을 즉시 시작할 수 있습니다. 파일을 편집, 생성, 이동 또는 삭제하면 Visual Studio는 변경 내용을 자동으로 추적하고 해당 IntelliSense 인덱스를 계속해서 업데이트합니다. .sln 또는 .vcxproj 파일이 로드되지 않습니다. 필요한 경우 간단한 .json 파일을 통해 매개 변수를 작성하고 시작할 수 있을 뿐만 아니라 사용자 지정 작업을 지정할 수도 있습니다. 이 기능을 사용 하면 모든 타사 빌드 시스템을 Visual Studio에 통합할 수 있습니다. 폴더 열기에 대한 일반적인 내용은 [프로젝트 또는 솔루션 없이 Visual Studio에서 코드 개발](/visualstudio/ide/develop-code-in-visual-studio-without-projects-or-solutions)을 참조하세요.

## <a name="cmake-and-qt"></a>CMake 및 Qt

Cto는 C++ 데스크톱 워크 로드의 구성 요소로 VISUAL Studio IDE에 통합 됩니다. CMake의 워크플로는이 문서에 설명 된 워크플로와 동일 하지 않습니다. CMake를 사용 하는 경우 [Visual Studio의 cmake 프로젝트](cmake-projects-in-visual-studio.md)를 참조 하세요. 또한 CMake를 사용 하 여 Qt 프로젝트를 빌드하거나 Visual Studio 2015 또는 Visual Studio 2017 용 [Qt Visual Studio 확장](https://download.qt.io/development_releases/vsaddin/) 을 사용할 수 있습니다.

## <a name="other-build-systems"></a>기타 빌드 시스템

주 메뉴에서 직접 지원 되지 않는 빌드 시스템 또는 컴파일러 도구 집합을 사용 하 여 Visual Studio IDE를 사용 하려면 파일을 선택 합니다. **| 열기 | 폴더** 또는 **Ctrl + Shift + Alt + O**를 누릅니다. 소스 코드 파일이 포함 된 폴더로 이동 합니다. 프로젝트를 빌드하고 IntelliSense를 구성 하 고 디버깅 매개 변수를 설정 하려면 다음과 같은 세 가지 JSON 파일을 추가 합니다.

| | |
|-|-|
|CppProperties.json|검색에 대한 사용자 지정 구성 정보를 지정합니다. 필요한 경우 이 파일을 루트 프로젝트 폴더에 만듭니다. (CMake 프로젝트에서 사용되지 않습니다.)|
|tasks.vs.json|사용자 지정 빌드 명령을 지정 합니다. **솔루션 탐색기**의 상황에 맞는 메뉴 항목 **작업 구성**을 통해 액세스합니다.|
|launch.vs.json|디버거의 명령줄 인수를 지정합니다. **솔루션 탐색기**의 상황에 맞는 메뉴 항목 **디버그 및 시작 설정**을 통해 액세스합니다.|

## <a name="configure-code-navigation-with-cpppropertiesjson"></a>Cppproperties.json를 사용 하 여 코드 탐색 구성

**정의로 이동** 이 제대로 작동 하는 것과 같은 IntelliSense 및 탐색 동작의 경우, Visual Studio에서 사용 중인 컴파일러, 시스템 헤더가 있는 위치 및 사용자가 연 폴더 (작업 영역 폴더)에 직접 포함 되지 않은 경우 추가 포함 파일이 있는지 알고 있어야 합니다. 구성을 지정 하려면 기본 도구 모음의 드롭다운 목록에서 구성 **관리** 를 선택할 수 있습니다.

![구성 관리 드롭다운](media/manage-configurations-dropdown.png)

Visual Studio는 다음과 같은 기본 구성을 제공 합니다.

![기본 구성](media/default-configurations.png)

예를 들어, **x64-Debug**를 선택 하는 경우 Visual Studio는 루트 프로젝트 폴더에 *cppproperties.json* 라는 파일을 만듭니다.

```json
{
  "configurations": [
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
    }
  ]
}
```

이 구성은 Visual Studio [x64 개발자 명령 프롬프트](building-on-the-command-line.md)의 환경 변수를 상속 합니다. 이러한 변수 중 하나가 `INCLUDE` 되며, `${env.INCLUDE}` 매크로를 사용 하 여 여기에서 참조할 수 있습니다. `includePath` 속성은 Visual Studio에 IntelliSense에 필요한 모든 원본을 찾을 수 있는 위치를 알려 줍니다. 이 경우 "INCLUDE 환경 변수에 지정 된 모든 디렉터리와 현재 작업 폴더 트리의 모든 디렉터리를 확인 합니다." 라고 표시 됩니다. `name` 속성은 드롭다운에 표시 되는 이름이 며 원하는 모든 이름이 될 수 있습니다. `defines` 속성은 조건부 컴파일 블록이 발견 될 때 IntelliSense에 힌트를 제공 합니다. `intelliSenseMode` 속성은 컴파일러 유형에 따라 몇 가지 힌트를 추가로 제공 합니다. MSVC, GCC 및 Clang에 대 한 몇 가지 옵션을 사용할 수 있습니다.

> [!NOTE]
> Visual Studio가 *cppproperties.json*에서 설정을 무시 하는 것으로 보이면 `!/CppProperties.json`다음과 같이 *.gitignore* 파일에 예외를 추가 해 보세요.

## <a name="default-configuration-for-mingw-w64"></a>MinGW에 대 한 기본 구성-전환 하거나 mingw-w64

MinGW-전환 하거나 mingw-w64 구성을 추가 하는 경우 JSON은 다음과 같이 표시 됩니다.

```json
{
  {
      "inheritEnvironments": [
        "mingw_64"
      ],
      "name": "Mingw64",
      "includePath": [
        "${env.INCLUDE}",
        "${workspaceRoot}\\**"
      ],
      "intelliSenseMode": "linux-gcc-x64",
      "environments": [
        {
          "MINGW64_ROOT": "C:\\msys64\\mingw64",
          "BIN_ROOT": "${env.MINGW64_ROOT}\\bin",
          "FLAVOR": "x86_64-w64-mingw32",
          "TOOLSET_VERSION": "9.1.0",
          "PATH": "${env.BIN_ROOT};${env.MINGW64_ROOT}\\..\\usr\\local\\bin;${env.MINGW64_ROOT}\\..\\usr\\bin;${env.MINGW64_ROOT}\\..\\bin;${env.PATH}",
          "INCLUDE": "${env.MINGW64_ROOT}\\include\\c++\\${env.TOOLSET_VERSION};${env.MINGW64_ROOT}\\include\\c++\\${env.TOOLSET_VERSION}\\tr1;${env.MINGW64_ROOT}\\include\\c++\\${env.TOOLSET_VERSION}\\${env.FLAVOR}",
          "environment": "mingw_64"
        }
      ]
    }
}
```

`environments` 블록을 확인 합니다. 이 클래스는 환경 변수 처럼 동작 하는 속성을 정의 하 고 *cppproperties.json* 파일 뿐만 아니라 다른 구성 파일 *작업 (json* 및 *시작*및 json) 에서도 사용할 수 있습니다. `Mingw64` 구성은 `mingw_w64` 환경을 상속 하 고 `INCLUDE` 속성을 사용 하 여 `includePath`에 대 한 값을 지정 합니다. 필요에 따라이 배열 속성에 다른 경로를 추가할 수 있습니다.

`intelliSenseMode` 속성은 GCC에 적절 한 값으로 설정 됩니다. 이러한 속성에 대 한 자세한 내용은 [cppproperties.json 스키마 참조](cppproperties-schema-reference.md)를 참조 하세요.

모든 것이 제대로 작동 하는 경우 형식 위로 마우스를 가져가면 GCC 헤더에서 IntelliSense가 표시 됩니다.

![GCC IntelliSense](media/gcc-intellisense.png)

## <a name="enable-intellisense-diagnostics"></a>IntelliSense 진단 사용

원하는 IntelliSense가 표시 되지 않는 경우 **도구** > **옵션** > **텍스트 편집기** > **C++ C/**  > **고급** 으로 이동 하 고 **로깅 사용** 을 **true**로 설정 하 여 문제를 해결할 수 있습니다. 먼저 **로깅 수준을** 5로 설정 하 고 **필터** 를 8로 설정 해 봅니다.

![진단 로깅](media/diagnostic-logging.png)

출력은 **출력 창** 로 파이프 되며, **출력에서 표시: Visual C++ Log*를 선택 하면 표시 됩니다. 출력에는 IntelliSense에서 사용 하려는 실제 포함 경로 목록이 포함 됩니다. 경로가 *cppproperties.json*의 경로와 일치 하지 않으면 폴더를 닫고 캐시 된 검색 데이터를 포함 하는 *vs* 하위 폴더를 삭제 합니다.

### <a name="define-build-tasks-with-tasksvsjson"></a>tasks.vs.json으로 빌드 작업 정의

현재 작업 영역에 있는 파일에 대한 빌드 스크립트 또는 기타 외부 작업을 IDE에서 직접 작업으로 실행하여 자동화할 수 있습니다. 파일 또는 폴더를 마우스 오른쪽 단추로 클릭하고 **작업 구성**을 선택하여 새 작업을 구성할 수 있습니다.

![폴더 열기 구성 작업](media/configure-tasks.png)

그러면 Visual Studio에서 루트 프로젝트 폴더에 만드는 vs 폴더에 *작업 vs json* 파일이 생성 되거나 열립니다. 이 파일에서 임의의 작업을 정의한 다음, 상황에 맞는 **솔루션 탐색기** 메뉴에서 호출할 수 있습니다. GCC 예제를 계속 하기 위해 다음 코드 조각은 *g + + .exe* 를 호출 하 여 프로젝트를 빌드하기 위한 단일 작업으로 전체 *작업 및 json* 파일을 보여 줍니다. 프로젝트에 *hello.exe*라는 단일 파일이 포함 되어 있다고 가정 합니다.

```json
{
  "version": "0.2.1",
  "tasks": [
    {
      "taskLabel": "build hello",
      "appliesTo": "/",
      "type": "default",
      "command": "g++",
      "args": [
        "-g",
        "-o",
        "hello",
        "hello.cpp"
      ]
    }
  ]
}

```

JSON 파일은 *vs* 하위 폴더에 배치 됩니다. 해당 폴더를 보려면 **솔루션 탐색기**위쪽의 **모든 파일 표시** 단추를 클릭 합니다. **솔루션 탐색기** 에서 루트 노드를 마우스 오른쪽 단추로 클릭 하 고 **hello 빌드**를 선택 하 여이 작업을 실행할 수 있습니다. 작업이 완료 되 면 **솔루션 탐색기**에서 *hello.exe* 라는 새 파일이 표시 됩니다.

여러 종류의 작업을 정의할 수 있습니다. 다음 예제에서는 단일 작업을 정의 하는 *작업 및 json 파일* 을 보여 줍니다. `taskLabel`은 상황에 맞는 메뉴에 표시되는 이름을 정의합니다. `appliesTo`는 명령을 수행할 수 있는 파일을 정의합니다. `command` 속성은 콘솔 (Windows의 경우*cmd.exe* )의 경로를 식별 하는 COMSPEC 환경 변수를 참조 합니다. CppProperties.json 또는 CMakeSettings.json에 선언된 환경 변수를 참조할 수도 있습니다. `args` 속성은 호출할 명령줄을 지정합니다. `${file}` 매크로는 **솔루션 탐색기**에서 선택한 파일을 검색합니다. 다음 예제에서는 현재 선택된 .cpp 파일의 파일 이름을 표시합니다.

```json
{
  "version": "0.2.1",
  "tasks": [
    {
      "taskLabel": "Echo filename",
      "appliesTo": "*.cpp",
      "type": "command",
      "command": "${env.COMSPEC}",
      "args": ["echo ${file}"]
    }
  ]
}
```

*작업 vs. json*을 저장 한 후 폴더에서 *.cpp* 파일을 마우스 오른쪽 단추로 클릭 하 고 상황에 맞는 메뉴에서 **Echo Filename** 을 선택 하 고 출력 창에 표시 되는 파일 이름을 확인할 수 있습니다.

자세한 내용은 [Tasks.vs.json 스키마 참조](tasks-vs-json-schema-reference-cpp.md)를 참조하세요.

### <a name="configure-debugging-parameters-with-launchvsjson"></a>launch.vs.json으로 디버깅 매개 변수 구성

프로그램의 명령줄 인수 및 디버깅 지침을 사용자 지정 하려면 **솔루션 탐색기** 에서 실행 파일을 마우스 오른쪽 단추로 클릭 하 고 **디버그 및 시작 설정**을 선택 합니다. 이렇게 하면 기존 *시작 및 json* 파일이 열리며, 없는 경우에는 최소 시작 설정 집합을 사용 하 여 새 파일을 만듭니다. 먼저 구성 하려는 디버그 세션의 종류를 선택할 수 있습니다. MinGw-전환 하거나 mingw-w64 프로젝트를 디버깅 하는 경우 **MinGw/CygwinC++ (gdb)에 대해 C/Launch**를 선택 합니다. 이렇게 하면 기본 값에 대 한 몇 가지 추측을 *gdb* 사용 하기 위한 시작 구성이 생성 됩니다. 이러한 기본값 중 하나는 `MINGW_PREFIX`입니다. 다음과 같이 리터럴 경로를 대체 하거나 *cppproperties.json*에서 `MINGW_PREFIX` 속성을 정의할 수 있습니다.

```json
{
  "version": "0.2.1",
  "defaults": {},
  "configurations": [
    {
      "type": "cppdbg",
      "name": "hello.exe",
      "project": "hello.exe",
      "cwd": "${workspaceRoot}",
      "program": "${debugInfo.target}",
      "MIMode": "gdb",
      "miDebuggerPath": "c:\\msys64\\usr\\bin\\gdb.exe",
      "externalConsole": true
    }
  ]
}

```

디버깅을 시작 하려면 디버그 드롭다운에서 실행 파일을 선택 하 고 녹색 화살표를 클릭 합니다.

![디버거 시작](media/launch-debugger-gdb.png)

**디버거 초기화** 대화 상자와 프로그램을 실행 하는 외부 콘솔 창이 표시 됩니다.

자세한 내용은 [시작 및 json 스키마 참조](launch-vs-schema-reference-cpp.md)를 참조 하세요.

## <a name="launching-other-executables"></a>다른 실행 파일 시작

컴퓨터의 모든 실행 파일에 대 한 시작 설정을 정의할 수 있습니다. 다음 예제에서는 *7za* 를 시작 하 고 추가 인수를 `args` JSON 배열에 추가 하 여 지정 합니다.

```json
{
  "version": "0.2.1",
  "defaults": {},
  "configurations": [
    {
      "type": "default",
      "project": "CPP\\7zip\\Bundles\\Alone\\O\\7za.exe",
      "name": "7za.exe list content of helloworld.zip",
      "args": [ "l", "d:\\sources\\helloworld.zip" ]
    }
  ]
}
```

이 파일을 저장하면 [디버그 대상] 드롭다운에 새 구성이 표시되고 이 구성을 선택하여 디버거를 시작할 수 있습니다. 실행 파일의 개수에 관계없이 원하는 만큼 많은 수의 디버그 구성을 만들 수 있습니다. 이제 **F5** 키를 누르면 디버거가 시작되고 이미 설정한 모든 중단점에 적중됩니다. 그리고 친숙한 모든 디버거 창과 해당 기능을 사용할 수 있습니다.

::: moniker-end
