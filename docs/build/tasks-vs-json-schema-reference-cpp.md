---
title: 작업 vs json 스키마 참조 (C++)
ms.date: 08/20/2019
helpviewer_keywords:
- tasks.vs.json file [C++]
ms.assetid: abd1985e-3717-4338-9e80-869db5435175
ms.openlocfilehash: 1e533babafad554e8f7413d2bc1a88933a6eca42
ms.sourcegitcommit: ace42fa67e704d56d03c03745b0b17d2a5afeba4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69975920"
---
# <a name="tasksvsjson-schema-reference-c"></a>작업 vs json 스키마 참조 (C++)

Visual Studio에서 열려 있는 폴더 프로젝트에서 소스 코드를 빌드하는 방법을 설명 하려면 *작업 및 json* 파일을 추가 합니다. 여기서 임의의 작업을 정의 하 고 **솔루션 탐색기** 상황에 맞는 메뉴에서 호출할 수 있습니다. Cmakeprojects는 모든 빌드 명령이 *Cmakelists .txt*에 지정 되어 있으므로이 파일을 사용 하지 않습니다. CMake 이외의 빌드 시스템의 경우, *작업 및 json* 을 사용 하 여 빌드 명령을 지정 하 고 빌드 스크립트를 호출할 수 있습니다. *작업 및 json*을 사용 하는 방법에 대 한 일반적인 내용은 ["폴더 열기" 개발에 대 한 빌드 및 디버그 작업 사용자 지정](/visualstudio/ide/customize-build-and-debug-tasks-in-visual-studio)을 참조 하세요.

작업 `type` 에는 `default`, `launch` ,또는`msbuild`의 네 가지 값 중 하나를 가질 수 있는 속성이 있습니다. `remote` 대부분의 작업은 `launch` 원격 연결이 필요한 경우가 아니면를 사용 해야 합니다.

## <a name="default-properties"></a>기본 속성

기본 속성은 모든 유형의 태스크에서 사용할 수 있습니다.

||||
|-|-|-|
|**Property**|**형식**|**설명**|
|`taskLabel`|string| (필수) 사용자 인터페이스에 사용 되는 작업 레이블을 지정 합니다.|
|`appliesTo`|string| (필수) 명령을 실행할 수 있는 파일을 지정 합니다. 와일드 카드 사용은 지원 됩니다 (예: " *", "* .cpp", "/* .txt").|
|`contextType`|string| 허용 되는 값: "custom", "build", "clean", "rebuild". 상황에 맞는 메뉴에서 작업이 표시 되는 위치를 결정 합니다. 기본값은 "custom"입니다.|
|`output`|string| 작업에 대 한 출력 태그를 지정 합니다.|
|`inheritEnvironments`|배열| 여러 원본에서 상속 되는 환경 변수 집합을 지정 합니다. *Cmakesettings. json* 또는 *cppproperties.json* 와 같은 파일에서 변수를 정의 하 고 작업 컨텍스트에 사용할 수 있도록 설정할 수 있습니다.|
|`passEnvVars`|boolean| 작업 컨텍스트에 추가 환경 변수를 포함할지 여부를 지정 합니다. 이러한 변수는 `envVars` 속성을 사용 하 여 정의 된 변수와 다릅니다. 기본값은 "true"입니다.|

## <a name="launch-properties"></a>시작 속성

작업 유형이 인 `launch`경우 다음 속성을 사용할 수 있습니다.

||||
|-|-|-|
|**Property**|**형식**|**설명**|
|`command`|string| 시작할 프로세스나 스크립트의 전체 경로를 지정 합니다.|
|`args`|배열| 명령에 전달 되는 쉼표로 구분 된 인수 목록을 지정 합니다.|
|`launchOption`|string| 허용되는 값은 다음과 같습니다. "None", "ContinueOnError", "IgnoreError" 오류가 있는 경우 명령을 사용 하 여 진행 하는 방법을 지정 합니다.|
|`workingDirectory`|string| 명령이 실행될 디렉터리를 지정합니다. 기본값은 프로젝트의 현재 작업 디렉터리입니다.|
|`customLaunchCommand`|string| 명령을 실행 하기 전에 적용할 전역 범위 사용자 지정을 지정 합니다. % PATH%와 같은 환경 변수를 설정 하는 데 유용 합니다.|
|`customLaunchCommandArgs`|string| CustomLaunchCommand에 대 한 인수를 지정 합니다. (가 `customLaunchCommand`필요 합니다.)|
 `env`| 사용자 지정 환경 변수의 키-값 목록을 지정 합니다. 예: "myEnv": "Myenv"|
|`commands`|배열| 순서 대로 호출할 명령의 목록을 지정 합니다.|

### <a name="example"></a>예제

다음 작업은 메이크파일 이 폴더에 제공 되 고 `Mingw64` 환경이 *cppproperties.json*에서 정의 된 경우 [cppproperties.json 스키마 참조](cppproperties-schema-reference.md#user_defined_environments)에 표시 되는 것 처럼를 호출 합니다.

```json
 {
  "version": "0.2.1",
  "tasks": [
    {
      "taskLabel": "gcc make",
      "appliesTo": "*.cpp",
      "type": "launch",
      "contextType": "custom",
      "inheritEnvironments": [
        "Mingw64"
      ],
      "command": "make"
    },
    {
      "taskLabel": "gcc clean",
      "appliesTo": "*.cpp",
      "type": "launch",
      "contextType": "custom",
      "inheritEnvironments": [
        "Mingw64"
      ],
      "command": "make",
      "args": ["clean"]
    }
  ]
}
```

**솔루션 탐색기**에서 *.cpp* 파일을 마우스 오른쪽 단추로 클릭 하면 상황에 맞는 메뉴에서 이러한 작업을 호출할 수 있습니다.

## <a name="remote-properties"></a>원격 속성

C++ 워크 로드를 사용 하 여 Linux 개발을 설치 하 고 Visual Studio 연결 관리자를 사용 하 여 원격 컴퓨터에 연결을 추가 하면 원격 작업이 활성화 됩니다. 원격 작업은 원격 시스템에서 명령을 실행 하 고 여기에 파일을 복사할 수도 있습니다.

작업 유형이 인 `remote`경우 다음 속성을 사용할 수 있습니다.

||||
|-|-|-|
|**Property**|**형식**|**설명**|
|`remoteMachineName`|string|원격 컴퓨터의 이름입니다. **연결 관리자**의 컴퓨터 이름과 일치 해야 합니다.|
|`command`|string|원격 컴퓨터에 보낼 명령입니다. 기본적으로 명령은 원격 시스템의 $HOME 디렉터리에서 실행 됩니다.|
|`remoteWorkingDirectory`|string|원격 컴퓨터의 현재 작업 디렉터리입니다.|
|`localCopyDirectory`|string|원격 컴퓨터에 복사할 로컬 디렉터리입니다. 기본값은 현재 작업 디렉터리입니다.|
|`remoteCopyDirectory`|string|`localCopyDirectory` 가 복사 되는 원격 컴퓨터의 디렉터리입니다.|
|`remoteCopyMethod`|string| 복사에 사용할 메서드입니다. 허용 되는 값: "none", "sftp", "rsync". 대량 프로젝트에는 rsync를 권장 합니다.|
|`remoteCopySourcesOutputVerbosity`|string| 허용되는 값은 다음과 같습니다. "Normal", "Verbose", "진단"입니다.|
|`rsyncCommandArgs`|string|기본값은 "-t--delete"입니다.|
|`remoteCopyExclusionList`|배열|복사 작업에서 제외할 파일 `localCopyDirectory` 의 쉼표로 구분 된 목록입니다.|

### <a name="example"></a>예제

**솔루션 탐색기**에서 *기본 .cpp* 를 마우스 오른쪽 단추로 클릭 하면 상황에 맞는 메뉴에 다음 작업이 표시 됩니다. 이는 `ubuntu` **연결 관리자**에서 호출 된 원격 컴퓨터에 따라 다릅니다. 작업은 Visual Studio에서 현재 열려 있는 폴더를 원격 컴퓨터 `sample` 의 디렉터리에 복사한 다음 g + +를 호출 하 여 프로그램을 빌드합니다.

```json
{
  "version": "0.2.1",
  "tasks": [
    {
      "taskLabel": "Build",
      "appliesTo": "main.cpp",
      "type": "remote",
      "contextType": "build",
      "command": "g++ main.cpp",
      "remoteMachineName": "ubuntu",
      "remoteCopyDirectory": "~/sample",
      "remoteCopyMethod": "sftp",
      "remoteWorkingDirectory": "~/sample/hello",
      "remoteCopySourcesOutputVerbosity": "Verbose"
    }
  ]
}
```

## <a name="msbuild-properties"></a>MSBuild 속성

작업 유형이 인 `msbuild`경우 다음 속성을 사용할 수 있습니다.

||||
|-|-|-|
|**Property**|**형식**|**설명**|
|`verbosity`|string| MSBuild 프로젝트 빌드 출력 verbosityAllowed 값을 지정 합니다. "Quiet", "최소", "보통", "상세", "진단"입니다.|
|`toolsVersion`|string| 프로젝트를 빌드할 도구 집합 버전을 지정 합니다 (예: "2.0", "3.5", "4.0", "Current"). 기본값은 "Current"입니다.|
|`globalProperties`|개체(object)|프로젝트에 전달할 전역 속성의 키-값 목록을 지정 합니다 (예: "Configuration": "Release").|
|`properties`|개체(object)| 추가 프로젝트 전용 속성의 키-값 목록을 지정 합니다.|
|`targets`|배열| 프로젝트에서 순서 대로 호출할 대상 목록을 지정 합니다. 아무것도 지정 하지 않으면 프로젝트의 기본 대상이 사용 됩니다.|
