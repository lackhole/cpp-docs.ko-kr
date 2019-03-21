---
title: Visual Studio에서 C++ Linux 프로젝트 배포, 실행 및 디버그
description: Visual Studio에 있는 C++ Linux 프로젝트 내의 원격 대상에서 코드를 컴파일하고, 실행하고, 디버그하는 방법을 설명합니다.
ms.date: 09/12/2018
ms.assetid: f7084cdb-17b1-4960-b522-f84981bea879
ms.openlocfilehash: cdafb064f8a6269c5ccae938e280b5f47bff3b00
ms.sourcegitcommit: b4645761ce5acf8c2fc7a662334dd5a471ea976d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/07/2019
ms.locfileid: "57562889"
---
# <a name="deploy-run-and-debug-your-linux-project"></a>Linux 프로젝트 배포, 실행 및 디버그

Visual Studio에서 Linux C++ 프로젝트를 만들고 [Linux 연결 관리자](connect-to-your-remote-linux-computer.md)를 사용하여 프로젝트에 연결하면 해당 프로젝트를 실행하고 디버그할 수 있습니다. 원격 대상에서 코드를 컴파일, 실행 및 디버그합니다.

Linux 프로젝트를 조작하고 디버그할 수 있는 여러 가지 방법이 있습니다.

- 중단점, 조사식 창과 같은 기존의 Visual Studio 기능을 사용하여 변수를 마우스 단추로 가리켜 디버그합니다. 이러한 메서드를 사용하여 다른 프로젝트 형식에 사용하는 일반적인 방법으로 디버그할 수 있습니다.

- 특별한 Linux 콘솔 창에서 대상 컴퓨터의 출력을 봅니다. 또한 콘솔을 사용하여 대상 컴퓨터에 입력을 보낼 수 있습니다.

## <a name="debug-your-linux-project"></a>Linux 프로젝트 디버그

1. **디버깅** 속성 페이지에서 디버깅 모드를 선택합니다.

   GDB는 Linux에서 실행되는 애플리케이션을 디버그하는 데 사용됩니다. GDB는 두 가지 모드에서 실행할 수 있고, 모드는 프로젝트의 **디버깅** 속성 페이지에 있는 **디버깅 모드**에서 선택할 수 있습니다.

   ![GDB 옵션](media/settings_debugger.png)

   - **gdbserver** 모드에서 원격 시스템의 gdbserver에 연결된 GDB는 로컬에서 실행됩니다.  Linux 콘솔 창이 지원하는 모드는 이 모드뿐입니다.

   - **gdb** 모드에서 Visual Studio 디버거는 원격 시스템에서 GDB를 구동합니다. GDB의 로컬 버전이 대상 컴퓨터에 설치된 버전과 호환되지 않을 경우 더 나은 옵션입니다. |

   > [!NOTE]
   > gdbserver 디버깅 모드에서 중단점에 도달할 수 없는 경우 gdb 모드를 시도해 보세요. 우선 원격 대상에 gdb가 [설치](download-install-and-setup-the-linux-development-workload.md)되어 있어야 합니다.

1. Visual Studio에서 표준 **디버그** 도구 모음을 사용하여 원격 대상을 선택합니다.

   사용할 수 있는 원격 대상은 목록에 이름 또는 IP 주소로 표시됩니다.

   ![원격 대상](media/remote_target.png)

   아직 원격 대상에 연결하지 않은 경우 [Linux 연결 관리자](connect-to-your-remote-linux-computer.md)를 사용하여 원격 대상에 연결하라는 지침이 표시됩니다.

   ![원격 아키텍처](media/architecture.png)

1. 실행될 것을 알고 있는 일부 코드의 왼쪽 여백을 클릭하여 중단점을 설정합니다.

   중단점을 설정한 코드 줄에 빨간 점이 표시됩니다.

1. **F5** 키(또는 **디버그 > 디버깅 시작**)를 눌러 디버깅을 시작합니다.

   디버깅을 시작하면 애플리케이션이 시작되기 전에 원격 대상에서 컴파일됩니다. 모든 컴파일 오류는 **오류 목록** 창에 표시됩니다.

   오류가 없는 경우 앱이 시작되고 디버거가 중단점에서 일시 중지됩니다.

   ![중단점 도달](media/hit_breakpoint.png)

   이제 **F10** 또는 **F11** 키와 같은 명령 키를 눌러 현재 상태의 애플리케이션과 상호작용하고, 변수를 보고, 코드를 단계별로 상호작용할 수 있습니다.

1. Linux 콘솔을 사용하여 앱과 상호 작용하려면 **디버그 > Linux 콘솔**을 선택합니다.

   ![Linux 콘솔 메뉴](media/consolemenu.png)

   이 콘솔에서는 대상 컴퓨터의 콘솔 출력을 표시하고 입력을 받아들이고 대상 컴퓨터로 보냅니다.

   ![Linux 콘솔 창](media/consolewindow.png)

## <a name="configure-other-debugging-options"></a>다른 디버깅 옵션 구성

- 프로젝트의 **디버깅** 속성 페이지에서 **프로그램 인수** 항목을 사용하여 명령줄 인수를 실행 파일에 전달할 수 있습니다.

   ![프로그램 인수](media/settings_programarguments.png)

- 특정 디버거 옵션은 **추가 디버거 명령** 항목을 통해 GDB에 전달될 수 있습니다.  예를 들어 SIGILL(잘못된 명령) 신호를 무시하고자 할 경우  **handle** 명령을 사용하여 신호를 무시할 수 있습니다.  위 그림처럼 **추가 디버거 명령** 항목에 다음 내용을 추가하면 됩니다.

   `handle SIGILL nostop noprint`

## <a name="next-steps"></a>다음 단계

- Linux에서 ARM 디바이스를 디버깅하려면 다음 블로그 게시물을 참조하세요. [Visual Studio에서 포함 ARM 디바이스 디버깅](https://blogs.msdn.microsoft.com/vcblog/2018/01/10/debugging-an-embedded-arm-device-in-visual-studio/).

- **프로세스에 연결** 명령을 사용하여 디버깅하려면 블로그 게시물을 참조하세요. [프로젝트 시스템에 대한 Linux C++ 워크로드 개선 사항, Linux 콘솔 창, rsync 및 프로세스에 연결](https://blogs.msdn.microsoft.com/vcblog/2018/03/13/linux-c-workload-improvements-to-the-project-system-linux-console-window-rsync-and-attach-to-process/).

## <a name="see-also"></a>참고 항목

[C++ 디버깅 속성(Linux C++)](prop-pages/debugging-linux.md)
