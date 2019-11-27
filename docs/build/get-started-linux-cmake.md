---
title: Visual Studio에서 C++ 플랫폼 간 프로젝트 만들기
description: Visual Studio에서 Linux 및 Windows를 대상으로 하 C++ 는 오픈 소스 cmake 프로젝트를 설정, 컴파일 및 디버그 하는 방법입니다.
author: mikeblome
ms.topic: tutorial
ms.date: 11/08/2019
ms.openlocfilehash: 269c9e88133a492f66df7c7f81ab35424aff125d
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303251"
---
# <a name="tutorial-create-c-cross-platform-projects-in-visual-studio"></a>자습서: Visual C++ Studio에서 플랫폼 간 프로젝트 만들기

Windows에서는 더 이상 Visual Studio C 및 C++ 개발을 지원하지 않습니다. 이 자습서에서는 Windows 및 Linux에서 플랫폼 간 C++ 개발에 Visual Studio를 사용 하는 방법을 보여 줍니다. CMake를 기반으로 하기 때문에 Visual Studio 프로젝트를 만들거나 생성할 필요가 없습니다. CMakeLists 파일이 포함 된 폴더를 열면 Visual Studio에서 IntelliSense 및 빌드 설정을 자동으로 구성 합니다. Windows에서 코드를 로컬로 편집, 빌드 및 디버깅 하는 과정을 신속 하 게 시작할 수 있습니다. 그런 다음 Visual Studio 내에서 Linux에 대해 동일한 작업을 수행 하도록 구성을 전환 합니다.

이 자습서에서는 다음 방법을 학습합니다.

> [!div class="checklist"]
> * GitHub에서 오픈 소스 CMake 프로젝트 복제
> * Visual Studio에서 프로젝트 열기
> * Windows에서 실행 파일 대상 빌드 및 디버그
> * Linux 머신에 대한 연결 추가
> * Linux에서 동일한 대상 빌드 및 디버그

## <a name="prerequisites"></a>필수 조건

* 플랫폼 간 C++ 개발용 Visual Studio 설정
  * 먼저 [Visual Studio를 설치](https://visualstudio.microsoft.com/vs/) 하 고 **워크 로드를 C++** 사용 하 여 **데스크톱 개발 C++**  및 Linux 개발을 선택 합니다. 이 최소 설치는 3gb에 불과합니다. 다운로드 속도에 따라 설치는 10 분 이상 소요 되어서는 안 됩니다.

* 플랫폼 간 C++ 개발용 Linux 머신 설정
  * Visual Studio에는 특정 버전의 Linux가 필요하지 않습니다. OS는 물리적 컴퓨터, VM 또는 클라우드에서 실행 될 수 있습니다. 또한 Linux 용 Windows 하위 시스템 (WSL)을 사용할 수 있습니다. 그러나이 자습서에서는 그래픽 환경이 필요 합니다. 여기서는 명령줄 작업에 주로 사용 되기 때문에 WSL을 사용 하지 않는 것이 좋습니다.
  * Visual Studio를 사용 하려면 Linux 컴퓨터에 C++ 컴파일러, gdb, ssh, rsync 및 zip 도구가 필요 합니다. Debian 기반 시스템에서 다음 명령을 사용 하 여 이러한 종속성을 설치할 수 있습니다.

    ```cmd
    sudo apt install -y openssh-server build-essential gdb rsync zip
    ```

  * Visual Studio를 사용 하려면 서버 모드를 사용 하는 Linux 컴퓨터에서 최신 버전의 CMake이 있어야 합니다 (최소 3.8). Microsoft에서는 모든 Linux 배포판에 설치할 수 있는 CMake의 유니버설 빌드를 제공합니다. 이 빌드를 사용 하 여 최신 기능이 있는지 확인 하는 것이 좋습니다. GitHub의 [CMake 리포지토리의 Microsoft 포크](https://github.com/Microsoft/CMake/releases)에서 CMake 이진 파일을 가져올 수 있습니다. 해당 페이지로 이동 하 여 Linux 컴퓨터의 시스템 아키텍처와 일치 하는 버전을 다운로드 한 다음 실행 파일로 표시 합니다.

    ```cmd
    wget <path to binary>
    chmod +x cmake-3.11.18033000-MSVC_2-Linux-x86_64.sh
    ```

  * `-–help`를 사용하여 스크립트를 실행하는 옵션을 확인할 수 있습니다. **/Usr/local** 경로에 설치를 지정 하는 `–prefix` 옵션을 사용 하는 것이 좋습니다 .이 위치는 Visual Studio에서 cmake를 검색 하는 기본 위치 이기 때문입니다. 다음 예제에서는 Linux-x86_64 스크립트를 보여줍니다. 다른 대상 플랫폼을 사용 하는 경우 필요에 따라 변경 합니다.

    ```cmd
    sudo ./cmake-3.11.18033000-MSVC_2-Linux-x86_64.sh --skip-license --prefix=/usr/local
    ```

* Windows 머신에 설치된 Windows용 Git
* GitHub 계정

## <a name="clone-an-open-source-cmake-project-from-github"></a>GitHub에서 오픈 소스 CMake 프로젝트 복제

이 자습서에서는 GitHub의 글머리 기호 물리학 SDK를 사용 합니다. 여러 응용 프로그램에 대 한 충돌 감지 및 물리학 시뮬레이션을 제공 합니다. SDK에는 추가 코드를 작성할 필요 없이 컴파일 및 실행 되는 샘플 실행 프로그램이 포함 되어 있습니다. 이 자습서에서는 소스 코드 또는 빌드 스크립트를 수정 하지 않습니다. 시작 하려면 Visual Studio가 설치 된 컴퓨터의 GitHub에서 *bullet3* 리포지토리를 복제 합니다.

```cmd
git clone https://github.com/bulletphysics/bullet3.git
```

1. Visual Studio 주 메뉴에서 **파일 > 열기 > cmake**를 선택 합니다. 방금 다운로드 한 bullet3 리포지토리의 루트에서 CMakeLists .txt 파일로 이동 합니다.

    ![파일 > 열기 > CMake의 Visual Studio 메뉴](media/cmake-open-cmake.png)

    폴더를 열면 바로 폴더 구조가 **솔루션 탐색기**표시 됩니다.

    ![Visual Studio 솔루션 탐색기 폴더 보기](media/cmake-bullet3-solution-explorer.png)

    이 보기에서는 논리적 보기 또는 필터링된 보기가 아니라 디스크에 표시된 내용을 정확하게 보여줍니다. 기본적으로 숨겨진 파일을 표시하지 않습니다.

1. **모든 파일 표시** 단추를 선택 하 여 폴더의 모든 파일을 표시 합니다.

    ![Visual Studio 솔루션 탐색기 모든 파일 표시 단추](media/cmake-bullet3-show-all-files.png)

## <a name="switch-to-targets-view"></a>대상 보기로 전환

CMake를 사용하는 폴더를 열 때 Visual Studio에서는 자동으로 CMake 캐시를 생성합니다. 프로젝트의 크기에 따라 이 작업은 몇 분 정도가 걸릴 수 있습니다.

1. **출력 창**에서 **출력 보기 대상**을 선택한 다음, **CMake**를 선택하여 캐시 생성 프로세스의 상태를 모니터링합니다. 작업이 완료되면 "대상 정보 추출 완료"라는 메시지가 표시됩니다.

   ![CMake의 출력을 보여주는 Visual Studio 출력 창](media/cmake-bullet3-output-window.png)

   이 작업이 완료 되 면 IntelliSense가 구성 됩니다. 프로젝트를 빌드하고 응용 프로그램을 디버그할 수 있습니다. 이제 Visual Studio는 CMakeLists 파일에 지정 된 대상에 따라 솔루션의 논리적 뷰를 표시 합니다.

1. **솔루션 탐색기**에서 **솔루션 및 폴더** 단추를 사용하여 CMake 대상 보기로 전환합니다.

   ![CMake 대상 보기를 보여주는 솔루션 탐색기의 솔루션 및 폴더 단추](media/cmake-bullet3-show-targets.png)

   글머리 기호 SDK에서 해당 보기가 표시된 내용은 다음과 같습니다.

   ![솔루션 탐색기 CMake 대상 보기](media/cmake-bullet3-targets-view.png)

   대상 보기는 이 원본 자료에 포함된 내용보다 직관적인 보기를 제공합니다. 일부 대상은 라이브러리이고 다른 대상은 실행 파일임을 확인할 수 있습니다.

1. 해당 파일이 디스크의 어디에 있든지에 관계 없이 CMake 대상 보기에서 노드를 확장하여 해당 소스 코드 파일을 확인하세요.

## <a name="add-an-explicit-windows-x64-debug-configuration"></a>명시적 Windows x64-Debug 구성 추가

Visual Studio는 Windows 용 기본 **X64 디버그** 구성을 만듭니다. 구성을 통해 Visual Studio가 CMake에서 사용하려는 대상 플랫폼을 이해할 수 있습니다. 기본 구성은 디스크에 표시되지 않습니다. 구성을 명시적으로 추가 하는 경우 Visual Studio는 *Cmakesettings. json*이라는 파일을 만듭니다. 지정 하는 모든 구성에 대 한 설정으로 채워집니다.

1. 새 구성을 추가 합니다. 도구 모음에서 **구성** 드롭다운을 열고 **구성 관리**를 선택 합니다.

   ![구성 관리 드롭다운](media/cmake-bullet3-manage-configurations.png)

   [Cmake 설정 편집기](customize-cmake-settings.md) 가 열립니다. 편집기의 왼쪽에 있는 녹색 더하기 기호를 선택 하 여 새 구성을 추가 합니다. **CMakeSettings에 구성 추가** 대화 상자가 나타납니다.

   ![CMakeSettings에 구성 추가 대화 상자](media/cmake-bullet3-add-configuration-x64-debug.png)

   이 대화 상자에는 Visual Studio에 포함 된 모든 구성 및 사용자가 만드는 모든 사용자 지정 구성이 표시 됩니다. **X64 디버그** 구성을 계속 사용 하려는 경우에는 먼저 추가 해야 합니다. **X64-Debug**를 선택 하 고 **선택** 단추를 선택 합니다. Visual Studio에서 **x64-Debug**구성을 사용 하 여 CMakeSettings. json 파일을 만들고 디스크에 저장 합니다. CMakeSettings.json에서 직접 이름 매개 변수를 변경하여 구성에 대해 원하는 이름을 사용할 수 있습니다.

## <a name="set-a-breakpoint-build-and-run-on-windows"></a>Windows에서 중단점 설정, 빌드 및 실행

이 단계에서는 글머리 기호 물리학 라이브러리를 보여주는 예제 프로그램을 디버깅합니다.
  
1. **솔루션 탐색기**에서 AppBasicExampleGui를 선택하고 확장합니다.

1. `BasicExample.cpp` 파일을 엽니다.

1. 실행 중인 응용 프로그램을 클릭할 때 적중 되는 중단점을 설정 합니다. 클릭 이벤트는 도우미 클래스 내의 메서드에서 처리됩니다. 신속하게 수행하려면:

   1. 구조체 `BasicExample` 파생 된 `CommonRigidBodyBase` 선택 합니다. 30 줄을 기준으로 합니다.

   1. **정의로 이동**을 마우스 오른쪽 단추로 클릭하고 선택합니다. 이제 CommonRigidBodyBase 헤더에 있습니다.

   1. 소스 위의 브라우저 보기에서 사용자가 `CommonRigidBodyBase`에 있음을 확인 해야 합니다. 오른쪽에서 검사할 멤버를 선택할 수 있습니다. 드롭다운을 열고 `mouseButtonCallback`를 선택 하 여 헤더에서 해당 함수의 정의로 이동 합니다.

      ![Visual Studio 멤버 목록 도구 모음](media/cmake-bullet3-member-list-toolbar.png)

1. 이 함수의 첫 번째 줄에 중단점을 배치합니다. 응용 프로그램 창에서 마우스 단추를 클릭 하면 Visual Studio 디버거에서 실행 될 때 적중 됩니다.

1. 응용 프로그램을 시작 하려면 도구 모음에서 시작 드롭다운을 선택 합니다. "시작 항목 선택" 이라는 녹색 재생 아이콘이 있는 것입니다. 드롭다운에서 AppBasicExampleGui를 선택 합니다. 이제 실행 파일 이름이 시작 단추에 표시됩니다.

   ![시작 항목 선택의 Visual Studio 도구 모음 시작 드롭다운](media/cmake-bullet3-launch-button.png)

1. 시작 단추를 선택 하 여 응용 프로그램 및 필요한 종속성을 빌드하고 Visual Studio 디버거를 연결 하 여 시작 합니다. 몇 분 후에 실행 중인 애플리케이션이 다음과 같이 표시됩니다.

   ![Windows 애플리케이션을 디버깅하는 Visual Studio](media/cmake-bullet3-launched.png)

1. 애플리케이션 창으로 마우스를 이동시킨 다음, 중단점을 트리거하는 단추를 클릭하세요. 중단점은 Visual Studio를 전경으로 다시 가져오고, 편집기는 실행이 일시 중지 된 줄을 표시 합니다. 응용 프로그램 변수, 개체, 스레드 및 메모리를 검사 하거나 코드를 대화형으로 단계별로 수행할 수 있습니다. **계속** 을 선택 하 여 응용 프로그램을 다시 시작 하 고 정상적으로 종료 합니다. 또는 중지 단추를 사용 하 여 Visual Studio 내에서 실행을 중단 합니다.

## <a name="add-a-linux-configuration-and-connect-to-the-remote-machine"></a>Linux 구성 추가 및 원격 머신에 연결

1. Linux 구성을 추가 합니다. **솔루션 탐색기** 보기에서 CMakeSettings.json 파일을 마우스 오른쪽 단추로 클릭하고 **구성 추가**를 선택합니다. 이전과 동일한 CMakeSettings에 구성 추가 대화 상자가 표시됩니다. **Linux-Debug** this time을 선택 하 고 CMakeSettings. json 파일을 저장 합니다 (ctrl + s).

1. 구성 드롭다운에서 **Linux-Debug** 를 선택 합니다.

   ![X64-Debug 및 Linux-Debug 옵션을 포함한 구성 시작 드롭다운](media/cmake-bullet3-linux-configuration-item.png)

   Linux 시스템에 처음 연결 하는 경우 **원격 시스템에 연결** 대화 상자가 나타납니다.

   ![Visual Studio 원격 시스템에 연결 대화 상자](media/cmake-bullet3-connection-manager.png)

   원격 연결을 이미 추가한 경우 **플랫폼 간 > 연결 관리자 > 도구 > 옵션**으로 이동 하 여이 창을 열 수 있습니다.

1. [Linux 컴퓨터에 대 한 연결 정보](/cpp/linux/connect-to-your-remote-linux-computer) 를 제공 하 고 **연결**을 선택 합니다. Visual Studio는 **Linux 디버그**에 대 한 기본 연결로 CMakeSettings에 해당 컴퓨터를 추가 합니다. 또한 원격 컴퓨터에서 헤더를 축소 하 여 [해당 원격 연결과 관련 된 IntelliSense](/cpp/linux/configure-a-linux-project?view=vs-2019#remote_intellisense)를 가져옵니다. 그런 다음, Visual Studio는 원격 컴퓨터에 파일을 보내고 원격 시스템에 CMake cache를 생성 합니다. 이러한 단계는 네트워크 속도 및 원격 컴퓨터의 성능에 따라 다소 시간이 걸릴 수 있습니다. CMake 출력 창에 "대상 정보 추출 완료" 라는 메시지가 표시 되 면 완료 된 것을 알 수 있습니다.

## <a name="set-a-breakpoint-build-and-run-on-linux"></a>Linux에서 중단점 설정, 빌드 및 실행

데스크톱 응용 프로그램 이므로 디버그 구성에 몇 가지 추가 구성 정보를 제공 해야 합니다.

1. CMake 대상 뷰에서 AppBasicExampleGui를 마우스 오른쪽 단추로 클릭 하 고 **디버그 및 시작 설정** 을 선택 하 여 **숨김과 하위 폴더** 에 있는 시작 및 json 파일을 엽니다. 이 파일은 개발 환경에서 로컬에 위치합니다. 팀에서 파일을 확인하고 저장하려는 경우 프로젝트의 루트로 이동시킬 수 있습니다. 이 파일에서는 AppBasicExampleGui에 대 한 구성이 추가 되었습니다. 이러한 기본 설정은 대부분의 경우 작동 하지만 여기서는 작동 하지 않습니다. 데스크톱 응용 프로그램 이기 때문에 Linux 컴퓨터에서 볼 수 있도록 프로그램을 시작 하기 위해 몇 가지 추가 정보를 제공 해야 합니다.

1. Linux 컴퓨터에서 `DISPLAY` 환경 변수의 값을 찾으려면 다음 명령을 실행 합니다.

   ```cmd
   echo $DISPLAY
   ```

   AppBasicExampleGui에 대 한 구성에는 "pipeArgs" 매개 변수 배열이 있습니다. "$ {DebuggerCommand}" 줄이 포함 되어 있습니다. 원격 컴퓨터에서 gdb를 실행 하는 명령입니다. Visual Studio는 명령을 실행 하기 전에 표시를이 컨텍스트로 내보내야 합니다. 예를 들어, 표시 값이 `:1`경우 다음과 같이 해당 줄을 수정 합니다.

   ```cmd
   "export DISPLAY=:1;${debuggerCommand}",
   ```

1. 응용 프로그램을 시작 하 고 디버그 합니다. 도구 모음에서 **시작 항목 선택** 드롭다운을 열고 **AppBasicExampleGui**를 선택 합니다. 그런 다음 도구 모음에서 녹색 재생 아이콘을 선택 하거나 **f5**키를 누릅니다. 응용 프로그램 및 해당 종속성은 원격 Linux 컴퓨터에서 작성 된 후 Visual Studio 디버거를 연결 하 여 시작 됩니다. 원격 Linux 머신에 애플리케이션 창이 표시됩니다.

1. 응용 프로그램 창으로 마우스를 이동 하 고 단추를 클릭 합니다. 중단점이 적중 됩니다. 프로그램 실행이 일시 중지 되 고 Visual Studio가 포그라운드로 돌아가고 중단점이 표시 됩니다. Linux 콘솔 창도 Visual Studio에 나타납니다. 창은 원격 Linux 컴퓨터의 출력을 제공 하며, `stdin`에 대 한 입력을 받을 수도 있습니다. Visual Studio 창과 마찬가지로 원하는 위치에 도킹할 수 있습니다. 해당 위치는 이후 세션에서 유지 됩니다.

   ![Visual Studio Linux 콘솔 창](media/cmake-bullet3-linux-console.png)

1. Visual Studio를 사용하여 대화형으로 코드를 통해 애플리케이션 변수, 개체, 스레드, 메모리 및 단계를 검사할 수 있습니다. 그러나 이번에는 로컬 Windows 환경이 아닌 원격 Linux 컴퓨터에서이 작업을 수행 하는 것이 좋습니다. **계속** 을 선택 하 여 응용 프로그램이 정상적으로 다시 시작 및 종료 되도록 하거나 로컬 실행과 마찬가지로 중지 단추를 선택할 수 있습니다.

1. Visual Studio가 Linux에서 애플리케이션을 시작한 이후에 호출 스택 창을 살펴보고 `x11OpenGLWindow`에 대한 호출을 보세요.

   ![Linux 호출 스택을 보여주는 호출 스택 창](media/cmake-bullet3-linux-callstack.png)

## <a name="what-you-learned"></a>학습 내용

이 자습서에서는 GitHub에서 직접 코드 베이스를 복제 했습니다. Windows에서 수정 하지 않고 빌드하고 실행 하 고 디버그 했습니다. 그런 다음, 사소한 구성 변경 내용으로 동일한 코드 베이스를 사용 하 여 원격 Linux 컴퓨터에서 빌드, 실행 및 디버그 합니다.

## <a name="next-steps"></a>다음 단계

Visual Studio에서 CMake 프로젝트를 구성하고 디버깅하는 방법을 자세히 알아봅니다.

> [!div class="nextstepaction"]
> [Visual Studio의 CMake 프로젝트](cmake-projects-in-visual-studio.md)<br/><br/>
> [Linux CMake 프로젝트 구성](../linux/cmake-linux-project.md)<br/><br/>
> [원격 Linux 컴퓨터에 연결](../linux/connect-to-your-remote-linux-computer.md)<br/><br/>
> [CMake 빌드 설정 사용자 지정](customize-cmake-settings.md)<br/><br/>
> [CMake 디버깅 세션 구성](configure-cmake-debugging-sessions.md)<br/><br/>
> [Linux 프로젝트 배포, 실행 및 디버그](../linux/deploy-run-and-debug-your-linux-project.md)<br/><br/>
> [CMake 미리 정의된 구성 참조](cmake-predefined-configuration-reference.md)
>
