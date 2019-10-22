---
title: Visual Studio에서 CMake 디버깅 세션 구성
ms.date: 03/21/2019
helpviewer_keywords:
- CMake debugging
ms.openlocfilehash: 41f53c0c3ea46a8a1aa11215968aaee6c13c2dea
ms.sourcegitcommit: e33126222c418daf977533ea9e2819d99e0d7b8d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72534110"
---
# <a name="configure-cmake-debugging-sessions"></a>CMake 디버깅 세션 구성

실행 가능한 모든 CMake 대상은 **일반** 도구 모음의 **시작 항목** 드롭다운에 표시됩니다. 디버깅 세션을 시작하려면 하나를 선택하고 디버거를 시작하기만 하면 됩니다.

![CMake 시작 항목 드롭다운](media/cmake-startup-item-dropdown.png "CMake 시작 항목 드롭다운")

솔루션 탐색기에서 디버그 세션을 시작할 수도 있습니다. 먼저 **솔루션 탐색기** 창의 **Cmake 대상 뷰로** 전환 합니다.

![CMake 대상 보기 단추](media/cmake-targets-view.png  "CMake 대상 보기 메뉴 항목")

그런 다음 실행 파일을 마우스 오른쪽 단추로 클릭 하 고 **디버그** 또는 **디버그 및 시작 설정**을 선택 합니다. **디버깅** 은 활성 구성에 따라 선택한 대상의 디버깅을 자동으로 시작 합니다. **디버그 및 시작 설정** 은 *시작. vs json* 파일을 열고 선택한 대상에 대 한 새 디버그 구성을 추가 합니다.

## <a name="customize-debugger-settings"></a>디버거 설정 사용자 지정

프로젝트의 실행 가능한 CMake 대상에 대한 디버거 설정을 사용자 지정하려면, 특정 CMakeLists.txt 파일을 마우스 오른쪽 단추로 클릭하고 **디버그 및 시작 설정**을 선택합니다. 또는 **솔루션 탐색기**의 대상 **보기** 에서 대상을 선택 합니다. 하위 메뉴에서 Ctotarget을 선택 하는 경우에는 **launch. vs. json** 이라는 파일이 만들어집니다. 이 파일은 선택한 CMake 대상에 대한 정보로 미리 채워져 있으며 프로그램 인수자 또는 디버거 형식과 같은 추가 매개 변수를 지정할 수 있습니다. **Cmakesettings. json** 파일의 모든 키를 참조 하려면 해당 파일 앞에 `cmake.` **시작 및 json**을 입력 합니다. 다음 예제에서는 현재 선택한 구성에 대 한 **Cmakesettings. json** 파일의 `remoteCopySources` 키 값을 가져오는 간단한 **시작 및 json** 파일을 보여 줍니다.

```json
{
  "version": "0.2.1",
  "defaults": {},
  "configurations": [
    {
      "type": "default",
      "project": "CMakeLists.txt",
      "projectTarget": "CMakeHelloWorld.exe (Debug\\CMakeHelloWorld.exe)",
      "name": "CMakeHelloWorld.exe (Debug\\CMakeHelloWorld.exe)",
      "args": ["${cmake.remoteCopySources}"]
    }
  ]
}
```

시작 **및 json** 파일을 저장 하는 즉시 **시작 항목** 드롭다운에서 새 이름을 사용 하 여 항목이 생성 됩니다. **Launch 및 json** 파일을 편집 하 여 원하는 수의 cmake 대상에 대해 원하는 수의 디버그 구성을 만들 수 있습니다.

## <a name="support-for-cmakesettings-variables"></a>CMakeSettings 변수 지원

 **시작. json과 json** 은 **cmakesettings. json** (아래 참조)에 선언 되 고 현재 선택 된 구성에 적용 되는 변수를 지원 합니다. 또한 로컬 프로젝트에 대해 시작 하는 앱의 현재 디렉터리를 설정 하는 `currentDir` 라는 키가 있습니다.

```json
{
  "type": "default",
  "project": "CMakeLists.txt",
  "projectTarget": "CMakeHelloWorld1.exe (C:\\Users\\satyan\\CMakeBuilds\\Test\\Debug\\CMakeHelloWorld1.exe)",
  "name": "CMakeHelloWorld1.exe (C:\\Users\\satyan\\CMakeBuilds\\Test\\Debug\\CMakeHelloWorld1.exe)",
  "currentDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}"
}
```

응용 프로그램을 실행할 때 `currentDir` 값은 다음과 비슷합니다.

```cmd
C:\Users\satyan\7f14809a-2626-873e-952e-cdf038211175\
```

' Cwd ' 키는 원격 프로젝트에 대해 시작 하는 앱의 현재 디렉터리를 설정 합니다. 기본값은로 계산 되는 ' $ {debugInfo. System.defaultworkingdirectory} '입니다. 

```cmd
/var/tmp/src/bfc6f7f4-4f0f-8b35-80d7-9198fa973fb9/Linux-Debug
```

## <a name="see-also"></a>참조

[Visual Studio의 CMake 프로젝트](cmake-projects-in-visual-studio.md)<br/>
[Linux CMake 프로젝트 구성](../linux/cmake-linux-project.md)<br/>
[원격 Linux 컴퓨터에 연결](../linux/connect-to-your-remote-linux-computer.md)<br/>
[CMake 빌드 설정 사용자 지정](customize-cmake-settings.md)<br/>
[CMake 디버깅 세션 구성](configure-cmake-debugging-sessions.md)<br/>
[Linux 프로젝트 배포, 실행 및 디버그](../linux/deploy-run-and-debug-your-linux-project.md)<br/>
[CMake 미리 정의된 구성 참조](cmake-predefined-configuration-reference.md)<br/>
