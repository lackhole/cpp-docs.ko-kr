---
title: Visual Studio의 CMake 프로젝트
ms.date: 03/05/2019
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
ms.openlocfilehash: 84511c0712fffcacc1f90d4bde808620e0a0ab0f
ms.sourcegitcommit: 42e65c171aaa17a15c20b155d22e3378e27b4642
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58356143"
---
# <a name="cmake-projects-in-visual-studio"></a>Visual Studio의 CMake 프로젝트

CMake는 여러 플랫폼에서 실행되는 빌드 프로세스를 정의하는 플랫폼 간 오픈 소스 도구입니다. 이 문서에서는 CMake에 익숙하다고 가정합니다. [CMake로 소프트웨어 빌드, 테스트 및 패키징](https://cmake.org/)에서 자세히 알아볼 수 있습니다.

Visual Studio 2015에서 Visual Studio 사용자는 [CMake 생성기](https://cmake.org/cmake/help/latest/manual/cmake-generators.7.html)를 사용하여 MSBuild 프로젝트 파일을 생성합니다. 그러면 IDE에서는 IntelliSense, 검색 및 컴파일에 사용합니다.

Visual Studio 2017에서는 [플랫폼 간 CMake 프로젝트](../linux/cmake-linux-project.md)를 포함하여 CMake에 대한 풍부한 지원을 제공합니다. **CMake용 Visual C++ 도구** 구성 요소에서 **폴더 열기** 기능을 사용하여 IDE에서 IntelliSense 및 검색을 수행하는 데 CMake 프로젝트 파일(예: CMakeLists.txt)을 직접 사용할 수 있습니다. Ninja 및 Visual Studio 생성기 모두 지원됩니다. Visual Studio 생성기를 사용하는 경우 임시 프로젝트 파일이 생성되어 msbuild.exe에 전달되지만 IntelliSense 또는 검색을 위해 로드되지는 않습니다. 기존 CMake 캐시를 가져올 수 있습니다. Visual Studio에서 자동으로 사용자 지정된 변수를 추출 하 고 미리 채워진 만듭니다 **CMakeSettings.json** 파일입니다. 

## <a name="installation"></a>설치

**CMake용 Visual C++ 도구**는 기본적으로 **C++를 사용한 데스크톱 개발** 워크로드의 일부 및 **C++를 사용한 Linux 개발** 워크로드의 일부로 설치됩니다.

![C++ 데스크톱 워크로드의 CMake 구성 요소](media/cmake-install.png)

자세한 내용은 [Visual Studio에서 C++ Linux 워크로드 설치](../linux/download-install-and-setup-the-linux-development-workload.md)를 참조하세요.

## <a name="ide-integration"></a>IDE 통합

**파일 | 열기 | 폴더**를 차례로 사용하여 CMakeLists.txt 파일이 포함된 폴더를 열면 다음과 같이 수행됩니다.

- Visual Studio에서 CMake 스크립트를 보고 편집하는 명령이 있는 **CMake** 메뉴 항목이 주 메뉴에 추가됩니다.

- **솔루션 탐색기**에서 폴더 구조와 파일이 표시됩니다.

- Visual Studio에서 CMake.exe를 실행하고 선택적으로 x86 디버그인 기본 *구성*에 대한 CMake 캐시를 생성합니다. CMake 명령줄이 CMake의 추가 출력과 함께 **출력 창**에 표시됩니다.

- IntelliSense, 검색 정보, 리팩터링 등을 사용할 수 있도록 하기 위해 Visual Studio에서 백그라운드로 소스 파일을 인덱싱합니다. 작업하는 동안 Visual Studio에서 편집기와 디스크의 변경 내용을 모니터링하여 인덱스가 소스와 동기화되도록 유지합니다.

여러 CMake 프로젝트가 포함된 폴더를 열 수 있습니다. Visual Studio에서는 작업 영역의 모든 "루트" CMakeLists.txt 파일을 검색하고 구성합니다. C++ IntelliSense 및 검색뿐만 아니라 CMake 작업(구성, 빌드, 디버그)도 작업 영역의 모든 CMake 프로젝트에서 사용할 수 있습니다.

![여러 루트가 있는 CMake 프로젝트](media/cmake-multiple-roots.png)

대상별로 논리적으로 구성된 프로젝트를 볼 수도 있습니다. **솔루션 탐색기** 도구 모음의 드롭다운 목록에서 **대상 보기**를 선택합니다.

![CMake 대상 보기 단추](media/cmake-targets-view.png)

라는 파일을 사용 하 여 visual Studio **CMakeSettings.json** Cmake.exe 위한 명령줄 옵션 또는 환경 변수를 저장 합니다. **CMakeSettings.json** 또한 정의 여러 CMake를 저장 하 여 빌드 구성 및 편리 하 게 ide에서 사이 전환 합니다. 

그렇지 않은 경우 사용 합니다 **CMakeLists.txt** 하는 소스 파일 지정, 라이브러리를 검색, 컴파일러 및 링커 옵션을 설정 및 다른 빌드 시스템을 지정 하려면 CMake 프로젝트에서 관련 정보 마찬가지로 합니다.

디버그 시 실행 파일에 인수를 전달 해야 하는 경우에 호출 하는 다른 파일을 사용할 수 있습니다 **launch.vs.json**합니다. 일부 시나리오에서는 Visual Studio에서 자동으로 이러한 파일을 생성합니다. 이는 수동으로 편집할 수 있습니다. 파일을 직접 만들 수도 있습니다.

> [!NOTE]
> 다른 종류의 폴더 열기 프로젝트에 대 한 두 개의 추가 JSON 파일이 사용 됩니다. **CppProperties.json** 하 고 **tasks.vs.json**합니다. 이 두 가지 모두 CMake 프로젝트와 관련이 없습니다.

## <a name="import-an-existing-cache"></a>기존 캐시 가져오기

기존 CMakeCache.txt 파일을 가져올 때 Visual Studio 자동으로 사용자 지정된 변수를 추출 하 고 미리 채워진 만듭니다 [ **CMakeSettings.json** ](#cmake_settings) 파일 기반으로 합니다. 원래 캐시는 어떤 방식으로든 수정되지 않으며, 명령줄 또는 생성하는 데 사용된 도구 또는 IDE를 통해 계속 사용할 수 있습니다. 새 **CMakeSettings.json** 파일은 프로젝트의 루트 CMakeLists.txt와 함께 배치 됩니다. Visual Studio에서는 설정 파일을 기반으로 하여 새 캐시를 생성합니다. **도구 | 옵션 | CMake | 일반** 대화 상자에서 자동 캐시 생성을 재정의할 수 있습니다.

캐시의 모든 항목을 가져오지는 않습니다.  생성기 및 컴파일러 위치와 같은 속성은 IDE에서 제대로 작동하는 것으로 알려진 기본값으로 대체됩니다.

### <a name="to-import-an-existing-cache"></a>기존 캐시를 가져오려면

1. 주 메뉴에서 **파일 | 열기 | CMake**를 차례로 선택합니다.

   ![CMake 열기](media/cmake-file-open.png "파일, 열기, CMake")

   **캐시에서 CMake 가져오기** 마법사가 표시됩니다.

2. 가져오려는 CMakeCache.txt 파일로 이동한 다음, **확인**을 클릭합니다. **캐시에서 CMake 프로젝트 가져오기** 마법사가 표시됩니다.

   ![CMake 캐시 가져오기](media/cmake-import-wizard.png "캐시에서 CMake 프로젝트 가져오기 마법사 열기")

   마법사가 완료되면 프로젝트의 루트 CMakeLists.txt 파일 옆에 있는 **솔루션 탐색기**에서 새 CMakeCache.txt 파일이 표시됩니다.

## <a name="building-cmake-projects"></a>CMake 프로젝트 빌드

CMake 프로젝트를 빌드하려면 다음과 같이 선택할 수 있습니다.

1. 일반 도구 모음에서 찾을 합니다 **구성을** 드롭다운; 것은 아마도 "Linux-Debug" 또는 "x64-Debug" 기본적으로 표시 합니다. 선택 하 고 원하는 구성 키를 눌러 **F5**, 클릭 또는 합니다 **실행** 도구 모음에서 단추 (녹색 삼각형). Visual Studio 솔루션과 마찬가지로 프로젝트가 자동으로 먼저 빌드됩니다.

1. CMakeLists.txt를 마우스 오른쪽 단추로 클릭하고, 상황에 맞는 메뉴에서 **빌드**를 선택합니다. 폴더 구조에 여러 대상이 있는 경우 모든 대상 또는 특정 대상만 빌드하도록 선택할 수 있습니다.

1. 주 메뉴에서 **빌드 | 솔루션 빌드**(**F7** 또는 **Ctrl+Shift+B**)를 선택합니다. **일반** 도구 모음의 **시작 항목** 드롭다운에서 CMake 대상이 이미 선택되어 있는지 확인합니다.

![CMake 빌드 메뉴 명령](media/cmake-build-menu.png "CMake 빌드 명령 메뉴")

사용자 지정할 수 있습니다 빌드 구성, 환경 변수, 명령줄 인수 및 기타 설정을 사용 하 여 CMakeLists.txt 파일을 수정 하지 않고 합니다 **CMakeSettings.json** 파일입니다. 자세한 내용은 [CMake 설정 사용자 지정](customize-cmake-settings.md)을 참조하세요.

빌드 결과가 예상한 대로 **출력 창** 및 **오류 목록**에 표시됩니다.

![CMake 빌드 오류](media/cmake-build-errors.png "CMake 빌드 오류")

여러 빌드 대상이 있는 폴더의 **CMake** 메뉴 또는 상황에 맞는 **CMakeLists.txt** 메뉴에서 **빌드** 항목을 선택하여 빌드할 CMake 대상을 지정할 수 있습니다. CMake 프로젝트에서 **Ctrl+Shift+B**를 누르면 현재 활성 문서가 빌드됩니다.

## <a name="debugging-cmake-projects"></a>CMake 프로젝트 디버깅

CMake 프로젝트를 디버그하려면 원하는 구성을 선택하고 **F5** 키를 누르거나 도구 모음에서 **실행** 단추를 누릅니다. **실행** 단추에서 "시작 항목 선택"이라고 표시되면 드롭다운 화살표를 선택하고 실행할 대상을 선택합니다. (CMake 프로젝트에서 "현재 문서" 옵션은 .cpp 파일에만 유효합니다.)

![CMake 실행 단추](media/cmake-run-button.png "CMake 실행 단추")

**실행** 또는 **F5** 명령은 이전 빌드 이후 변경된 경우 프로젝트를 먼저 빌드합니다.

속성을 설정 하 여 디버깅 세션을 CMake를 사용자 지정할 수 있습니다 합니다 **launch.vs.json** 파일입니다. 자세한 내용은 [CMake 디버깅 세션 구성](configure-cmake-debugging-sessions.md)을 참조하세요.


## <a name="editing-cmakeliststxt-files"></a>CMakeLists.txt 파일 편집

CMakeLists.txt 파일을 편집하려면 **솔루션 탐색기**에서 파일을 마우스 오른쪽 단추로 클릭하고 **열기**를 선택합니다. 파일을 변경하면 노란색 상태 표시줄이 표시되고, IntelliSense가 업데이트됨을 알리고, 업데이트 작업을 취소할 수 있는 기회를 제공합니다. CMakeLists.txt에 대한 자세한 내용은 [CMake 설명서](https://cmake.org/documentation/)를 참조하세요.

   ![CMakeLists.txt 파일 편집](media/cmake-cmakelists.png "CMakeLists.txt 파일 편집")

파일을 저장하는 즉시 구성 단계가 자동으로 다시 실행되고 **출력** 창에 정보가 표시됩니다. 오류와 경고가 **오류 목록** 또는 **출력** 창에 표시됩니다. **오류 목록**에서 오류를 두 번 클릭하여 CMakeLists.txt에서 잘못된 줄로 이동합니다.

   ![CMakeLists.txt 파일 오류](media/cmake-cmakelists-error.png "CMakeLists.txt 파일 오류")


## <a name="cmake-configure-step"></a>CMake 구성 단계

때 중요 한 변경에는 **CMakeSettings.json** CMakeLists.txt 파일에 Visual Studio 자동으로 다시 실행 된 CMake 또는 단계를 구성 합니다. 구성 단계가 오류 없이 완료되는 경우 수집된 정보는 C++ IntelliSense 및 언어 서비스와 빌드/디버그 작업에서 사용할 수 있습니다.

여러 CMake 프로젝트에서 동일한 CMake 구성 이름(예: x86-Debug)을 사용하는 경우, 해당 구성을 선택할 때 해당 CMake 프로젝트 모두가 자체 빌드 루트 폴더에 빌드되고 구성됩니다. 해당 CMake 구성에 참여하는 모든 CMake 프로젝트에서 대상을 디버그할 수 있습니다.

   ![CMake 빌드 전용 메뉴 항목](media/cmake-build-only.png "CMake 빌드 전용 메뉴 항목")

빌드 제한 디버그 세션을 작업 영역에 있는 프로젝트의 하위 집합을 고유한 이름으로 새 구성을 만들려면 합니다 **CMakeSettings.json** 파일과 해당 프로젝트에만 적용 합니다. 해당 구성을 선택하면 지정된 프로젝트에 대해서만 IntelliSense 및 빌드/디버그 명령이 사용됩니다.

## <a name="troubleshooting-cmake-cache-errors"></a>CMake 캐시 오류 문제 해결

문제를 진단하는 데 CMake 캐시의 상태에 대한 추가 정보가 필요하면, **CMake** 주 메뉴 또는 **솔루션 탐색기**의 상황에 맞는 **CMakeLists.txt** 메뉴를 열어 다음 명령 중 하나를 실행합니다.

- **캐시 보기**는 편집기의 빌드 루트 폴더에서 CMakeCache.txt 파일을 엽니다. 캐시를 정리하면 CMakeCache.txt에 대해 여기서 편집한 내용이 모두 지워집니다. 캐시를 정리한 후에도 계속 변경하려면 이 문서의 앞부분에 나오는 [CMake 설정 및 사용자 지정 구성](#cmake_settings)을 참조하세요.

- **캐시 폴더 열기**는 빌드 루트 폴더에 대한 탐색기 창을 엽니다.

- **캐시 정리**는 다음 CMake 구성 단계를 정리된 캐시에서 시작하도록 빌드 루트 폴더를 삭제합니다.

- **캐시 생성**은 Visual Studio에서 최신 환경으로 간주하는 경우에도 생성 단계를 강제로 수행합니다.

자동 캐시 생성은 **도구 | 옵션 | CMake | 일반** 대화 상자에서 비활성화할 수 있습니다.

## <a name="single-file-compilation"></a>단일 파일 컴파일

CMake 프로젝트에서 단일 파일을 빌드하려면 **솔루션 탐색기**의 파일을 마우스 오른쪽 단추로 클릭하고 **컴파일**을 선택합니다. 또한 기본 CMake 메뉴를 사용하여 편집기에서 현재 열려 있는 파일을 빌드할 수 있습니다.

![CMake 단일 파일 컴파일](media/cmake-single-file-compile.png)

## <a name="run-cmake-from-the-command-line"></a>명령줄에서 CMake 실행

Visual Studio 설치 관리자에서 CMake를 설치한 경우 다음 단계에 따라 명령줄에서 이를 실행할 수 있습니다.

1. 해당하는 vsdevcmd.bat(x86/x64)를 실행합니다. 자세한 내용은 [명령줄에서 빌드](building-on-the-command-line.md)를 참조하세요.

1. 출력 폴더로 전환합니다.

1. CMake를 실행하여 앱을 빌드/구성합니다.
  
## <a name="see-also"></a>참고 항목

[자습서: Visual Studio에서 C++ 플랫폼 간 프로젝트 만들기](get-started-linux-cmake.md)<br/>
[Linux CMake 프로젝트 구성](../linux/cmake-linux-project.md)<br/>
[원격 Linux 컴퓨터에 연결](../linux/connect-to-your-remote-linux-computer.md)<br/>
[CMake 빌드 설정 사용자 지정](customize-cmake-settings.md)<br/>
[CMakeSettings.json 참조](cmakesettings-reference.md)<br/>
[CMake 디버깅 세션 구성](configure-cmake-debugging-sessions.md)<br/>
[Linux 프로젝트 배포, 실행 및 디버그](../linux/deploy-run-and-debug-your-linux-project.md)<br/>
[CMake 미리 정의된 구성 참조](cmake-predefined-configuration-reference.md)<br/>
