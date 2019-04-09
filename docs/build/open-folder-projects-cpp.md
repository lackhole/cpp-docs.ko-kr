---
title: Visual Studio에서 C++ 빌드 시스템에 대해 폴더 열기 지원
ms.date: 03/21/2019
helpviewer_keywords:
- Open Folder Projects in Visual C++
ms.assetid: abd1985e-3717-4338-9e80-869db5435175
ms.openlocfilehash: 380a96bcb1a119b2b6d4104d60936217d1350fbb
ms.sourcegitcommit: 35c4b3478f8cc310ebbd932a18963ad8ab846ed9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59237135"
---
# <a name="open-folder-projects-for-c"></a>C++의 폴더 열기 프로젝트

Visual Studio 2017 이상에서 "폴더 열기" 기능을 통해 소스 파일의 폴더를 열고 IntelliSense, 검색, 리팩터링, 디버깅 등의 지원을 통해 코딩을 즉시 시작할 수 있습니다. .sln 또는 .vcxproj 파일이 로드되지 않습니다. 필요한 경우 간단한 .json 파일을 통해 매개 변수를 작성하고 시작할 수 있을 뿐만 아니라 사용자 지정 작업을 지정할 수도 있습니다. 폴더 열기에 대한 일반적인 내용은 [프로젝트 또는 솔루션 없이 Visual Studio에서 코드 개발](/visualstudio/ide/develop-code-in-visual-studio-without-projects-or-solutions)을 참조하세요.

CMake는 C++ 데스크톱 워크로드의 구성 요소인 Visual Studio용 CMake 도구로 Visual Studio IDE에 통합되어 있습니다. 자세한 내용은 [Visual Studio의 CMake 프로젝트](cmake-projects-in-visual-studio.md)를 참조하세요. 다른 빌드 시스템에서 폴더 열기 기능을 사용할 수 있습니다. 폴더 열기는 빌드 시스템 및 컴파일러 도구 세트로부터 코드 편집기, 디버거 및 분석기를 효과적으로 분리합니다. CMake, Ninja, QMake(Qt 프로젝트의 경우), gyp, SCons, Gradle, Buck, make 등을 비롯한 거의 모든 빌드 시스템을 사용하여 다양한 IntelliSense 기능, 코드 분석기 및 Visual Studio 디버거에서 C++ 코드 편집기를 사용할 수 있습니다. 빌드 시스템이 없는 단일 파일 또는 느슨한 파일 컬렉션에서도 작동합니다.

폴더 열기를 사용하려면 주 메뉴에서 **파일 | 열기 | 폴더**를 차례대로 선택하거나 **Ctrl +Shift+Alt+O**를 누릅니다. 솔루션 탐색기에서 폴더의 모든 파일이 즉시 표시됩니다. 파일을 클릭하여 편집을 시작할 수 있습니다. 백그라운드에서 Visual Studio는 IntelliSense, 탐색 및 리팩터링 기능을 사용할 수 있도록 파일 인덱싱을 시작합니다. 파일을 편집, 생성, 이동 또는 삭제하면 Visual Studio는 변경 내용을 자동으로 추적하고 해당 IntelliSense 인덱스를 계속해서 업데이트합니다. 

## <a name="qmake-projects-that-target-the-qt-framework"></a>Qt 프레임워크를 대상으로 하는 QMake 프로젝트

Visual Studio용 CMake 도구를 사용하여 Qt를 대상으로 하는 Qt 프로젝트를 만들거나 Visual Studio 2015 또는 Visual Studio 2017에 [Qt Visual Studio 확장](https://download.qt.io/development_releases/vsaddin/)을 사용할 수 있습니다.

## <a name="gyp-cons-scons-buck-etc"></a>gyp, Cons, SCons, Buck 등

Visual Studio에서 모든 빌드 시스템을 사용할 수 있으며 C++ IDE 및 디버거의 장점을 활용할 수 있습니다. 프로젝트의 루트 폴더를 열면 C++ 코드 편집기에서는 추론을 사용하여 IntelliSense 및 검색 대상인 원본 파일을 인덱싱합니다. CppProperties.json 파일을 편집하여 코드 구조에 대한 힌트를 제공할 수 있습니다. 이와 비슷한 방식으로 launch.vs.json 파일을 편집하여 빌드 프로그램을 구성하고 호출할 수 있습니다.

## <a name="configuring-open-folder-projects"></a>폴더 열기 프로젝트 구성

3개의 JSON 파일을 통해 폴더 열기 프로젝트를 사용자 지정할 수 있습니다.

| | |
|-|-|
|CppProperties.json|검색에 대한 사용자 지정 구성 정보를 지정합니다. 필요한 경우 이 파일을 루트 프로젝트 폴더에 만듭니다. (CMake 프로젝트에서 사용되지 않습니다.)|
|tasks.vs.json|사용자 지정 빌드 명령 및 컴파일러 스위치를 지정합니다. **솔루션 탐색기**의 상황에 맞는 메뉴 항목 **작업 구성**을 통해 액세스합니다.|
|launch.vs.json|디버거의 명령줄 인수를 지정합니다. **솔루션 탐색기**의 상황에 맞는 메뉴 항목 **디버그 및 시작 설정**을 통해 액세스합니다.|

### <a name="configure-intellisense-and-browsing-hints-with-cpppropertiesjson"></a>CppProperties.json으로 IntelliSense 및 검색 힌트 구성

IntelliSense 및 검색 동작은 #include 경로, 컴파일러 스위치 및 다른 매개 변수를 정의하는 활성 빌드 구성에 따라 부분적으로 다릅니다. 기본적으로 Visual Studio는 디버그 및 릴리스 구성을 제공합니다. CMake 프로젝트는 이를 위해 CMakeSettings.json 파일 및 CMakeLists.txt 파일를 사용합니다. 다른 종류의 폴더 열기 프로젝트인 경우 IntelliSense 및 검색 기능에서 코드를 완전히 인식할 수 있도록 사용자 지정 구성을 만들어야 합니다. 새 구성을 정의하려면 루트 폴더에 CppProperties.json이라는 파일을 만듭니다. 예를 들면 다음과 같습니다.

```json
{
  "configurations": [
    {
      "name": "Windows x64",
      "includePath": [ "include" ],
      "defines": [ "_DEBUG" ],
      "compilerSwitches": "/std:c++17",
      "intelliSenseMode": "windows-msvc-x64",
      "forcedInclude": [ "pch.h" ],
      "undefines": []
    }
  ]
}
```
자세한 내용은 [CppProperties 스키마 참조](cppproperties-schema-reference.md)를 참조하세요.

### <a name="define-build-tasks-with-tasksvsjson"></a>tasks.vs.json으로 빌드 작업 정의

현재 작업 영역에 있는 파일에 대한 빌드 스크립트 또는 기타 외부 작업을 IDE에서 직접 작업으로 실행하여 자동화할 수 있습니다. 파일 또는 폴더를 마우스 오른쪽 단추로 클릭하고 **작업 구성**을 선택하여 새 작업을 구성할 수 있습니다.

![폴더 열기 구성 작업](media/open-folder-config-tasks.png)

이 만듭니다 (또는 열립니다)는 **tasks.vs.json** Visual Studio 루트 프로젝트 폴더에 만드는.vs 폴더의 파일입니다. 이 파일에서 임의의 작업을 정의한 다음, 상황에 맞는 **솔루션 탐색기** 메뉴에서 호출할 수 있습니다. 다음 예제에서는 단일 작업을 정의하는 tasks.vs.json 파일을 보여 줍니다. `taskName` 상황에 맞는 메뉴에 표시 되는 이름을 정의 합니다. `appliesTo` 명령에서 수행할 수 있는 파일을 정의 합니다. `command` 속성은 콘솔에 대한 경로(Windows의 경우 cmd.exe)를 식별하는 COMSPEC 환경 변수를 참조합니다. CppProperties.json 또는 CMakeSettings.json에 선언된 환경 변수를 참조할 수도 있습니다. `args` 속성은 호출할 명령줄을 지정합니다. `${file}` 매크로는 **솔루션 탐색기**에서 선택한 파일을 검색합니다. 다음 예제에서는 현재 선택된 .cpp 파일의 파일 이름을 표시합니다.

```json
{
  "version": "0.2.1",
  "tasks": [
    {
      "taskName": "Echo filename",
      "appliesTo": "*.cpp",
      "type": "command",
      "command": "${env.COMSPEC}",
      "args": ["echo ${file}"]
    }
  ]
}
```

tasks.vs.json이 저장되면 폴더의 .cpp 파일을 마우스 오른쪽 단추로 클릭하고, 상황에 맞는 메뉴에서 **Echo filename(파일 이름 화면 표시)** 을 선택하여 [출력 창]에 표시된 파일 이름을 확인할 수 있습니다.

자세한 내용은 [Tasks.vs.json 스키마 참조](tasks-vs-json-schema-reference-cpp.md)를 참조하세요.

### <a name="configure-debugging-parameters-with-launchvsjson"></a>launch.vs.json으로 디버깅 매개 변수 구성

프로그램의 명령줄 인수를 사용자 지정하려면 **솔루션 탐색기**에서 실행 파일을 마우스 오른쪽 단추로 클릭하고 **디버그 및 시작 설정**을 선택합니다. 기존 열립니다 **launch.vs.json** 파일에 없는 경우 선택한 프로그램에 대 한 정보를 사용 하 여 미리 채워진 새 파일을 만듭니다.

추가 인수를 지정하려면 다음 예제와 같이 `args` JSON 배열에 추가합니다.

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
