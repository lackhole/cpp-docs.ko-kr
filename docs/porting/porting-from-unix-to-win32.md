---
title: UNIX에서 Win32로 이식
ms.date: 08/02/2018
helpviewer_keywords:
- APIs [C++], porting to Win32
- Windows API [C++], migrating from UNIX
- migration [C++]
- UNIX [C++], porting to Win32
- porting to Win32 [C++], from UNIX
- porting to Win32 [C++]
- Win32 applications [C++], migrating from UNIX
ms.assetid: 3837e4fe-3f96-4f24-b2a1-7be94718a881
ms.openlocfilehash: 3146c94879532a5c58208369bb6d131a3a027c33
ms.sourcegitcommit: 90817d9d78fbaed8ffacde63f3add334842e596f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2019
ms.locfileid: "58278478"
---
# <a name="porting-from-unix-to-win32"></a>UNIX에서 Win32로 이식

UNIX에서 Windows로 애플리케이션을 마이그레이션하는 경우 다음과 같은 여러 옵션이 있습니다.

- UNIX 라이브러리를 사용하여 UNIX에서 Win32로 애플리케이션 포팅

- 기본적으로 UNIX에서 Win32로 애플리케이션 포팅

- POSIX 하위 시스템을 사용하여 Windows에서 UNIX 애플리케이션 실행

## <a name="unix-libraries"></a>UNIX 라이브러리

UNIX 프로그래머가 일반적으로 고려하는 한 가지 옵션은 UNIX와 비슷한 타사 라이브러리를 사용하여 UNIX 코드가 Win32 실행 파일로 컴파일되도록 하는 것입니다. 여러 상업용(및 하나 이상의 공용 도메인) 라이브러리가 이 작업을 수행합니다. 이는 일부 애플리케이션에 대한 옵션입니다. 이러한 포팅 라이브러리의 장점은 초기 포팅 노력을 최소화한다는 것입니다. 경쟁력 있는 소프트웨어 제품에 비해 주요 단점은 애플리케이션의 네이티브 Win32 포트가 일반적으로 더 빠르고 필연적으로 더 많은 기능을 포함한다는 것입니다. 애플리케이션이 Windows를 더 많이 활용하기 위해 Win32 호출을 수행해야 하는 경우 UNIX 셸을 벗어나는 것은 불편할 수 있습니다.

다음 목록에서는 Visual C++로의 포팅 및 UNIX 마이그레이션을 지원하는 Microsoft 및 타사 리소스를 제공합니다.

### <a name="unix-migration-guides"></a>UNIX 마이그레이션 가이드

[UNIX Custom Application Migration Guide](https://technet.microsoft.com/library/bb656290.aspx)(UNIX 사용자 지정 애플리케이션 마이그레이션 가이드)에서는 UNIX에서 Win32 환경으로의 코드 마이그레이션에 대한 기술 도움말을 제공합니다.

[Unix Migration Project Guide](https://technet.microsoft.com/library/bb656287.aspx)(Unix 마이그레이션 프로젝트 가이드)에서는 UNIX에서 Win32로 많은 프로젝트를 마이그레이션하는 방법에 대한 개괄적인 도움말을 제공하여 UNIX 사용자 지정 애플리케이션 마이그레이션 가이드를 보완합니다. 이 가이드에서는 프로젝트 마이그레이션의 각 단계에서 고려해야 할 문제에 대해 조언합니다.

### <a name="interopsystemscom"></a>InteropSystems.com

[http://www.interopsystems.com/](http://www.interopsystems.com/)

UNIX에서 Win32로의 포팅을 지원하는 소프트웨어를 제공하는 회사를 위한 타사 사이트입니다.

### <a name="c-boost-web-site"></a>C++ Boost 웹 사이트

[http://boost.sourceforge.net/regression-logs/](http://boost.sourceforge.net/regression-logs/)

[http://boost.sourceforge.net/boost-build2/](http://boost.sourceforge.net/boost-build2/)

## <a name="porting-unix-applications-directly-to-win32"></a>Win32로 직접 UNIX 애플리케이션 포팅

다른 옵션은 Win32로 직접 UNIX 애플리케이션을 포팅하는 것입니다. ANSI C/C++ 라이브러리 및 상업용 C 컴파일러 라이브러리를 통해 UNIX 애플리케이션에서 사용하는 일반적인 시스템 호출을 Win32 애플리케이션에서 대부분 사용할 수 있습니다.

Win32 콘솔 API는 **stdio** 모델을 모방하며 Win32 콘솔 API를 사용하는 *curses* 버전이 있기 때문에 **stdio** 기반 애플리케이션의 출력 모델을 변경할 필요는 없습니다. 자세한 내용은 [SetConsoleCursorPosition](/windows/console/setconsolecursorposition)을 참조하세요.

Berkeley 소켓 기반 애플리케이션의 경우 Win32 애플리케이션으로 작동하기 위해 거의 변경할 필요가 없습니다. Windows 소켓 인터페이스는 WinSock 사양의 소개 단원에 설명된 최소한의 변경으로 BSD 소켓 포팅이 가능하도록 설계되었습니다.

Windows는 DCE 규격 RPC를 지원하므로 RPC 기반 애플리케이션을 쉽게 사용할 수 있습니다. [RPC 함수](/windows/desktop/Rpc/rpc-functions)를 참조하세요.

가장 큰 차이점 중 하나는 프로세스 모델입니다. UNIX에는 `fork`가 있고 Win32에는 없습니다. `fork` 및 코드베이스 사용에 따라 Win32에는 사용할 수 있는 두 개의 API(`CreateProcess` 및 `CreateThread`)가 있습니다. 자신의 여러 복사본을 분기하는 UNIX 애플리케이션을 여러 프로세스나 여러 스레드가 포함된 단일 프로세스를 사용하도록 Win32에서 다시 작업할 수 있습니다. 여러 프로세스를 사용하는 경우 프로세스 간에 통신하고, `fork`에서 제공하는 기능이 필요한 경우 새 프로세스의 코드 및 데이터를 부모처럼 업데이트하는 데 사용할 수 있는 IPC의 여러 메서드가 있습니다. IPC에 대한 자세한 내용은 [Interprocess Communications](/windows/desktop/ipc/interprocess-communications)(프로세스 간 통신)를 참조하세요.

Windows 및 UNIX 그래픽 모델은 매우 다릅니다. UNIX는 X 창 시스템 GUI를 사용하는 반면, Windows는 GDI를 사용합니다. 개념상 비슷하지만 X API와 GDI API 간의 단순 매핑은 없습니다. 그러나 UNIX OpenGL 기반 애플리케이션 마이그레이션을 위한 OpenGL 지원이 제공됩니다. 또한 Windows용 X 클라이언트 및 X 서버가 있습니다. GDI에 대한 자세한 내용은 [Device Contexts](/windows/desktop/gdi/device-contexts)(디바이스 컨텍스트)를 참조하세요.

많은 CGI 애플리케이션을 포함하여 기본 UNIX 애플리케이션은 Windows에서 실행되는 Visual C++로 쉽게 포팅되어야 합니다. `open`, `fopen`, `read`, `write` 등의 함수는 Visual C++ 런타임 라이브러리에서 사용할 수 있습니다. 또한 C UNIX API와 Win32 API 간에 일대일 매핑이 있습니다(`open`을 `CreateFile`로, `read`를 `ReadFile`로, `write`를 `WriteFile`로, `ioctl`을 `DeviceIOControl`로, `close`를 `CloseFile`로 매핑).

## <a name="windows-posix-subsystem"></a>Windows POSIX 하위 시스템

UNIX 프로그래머가 고려하는 또 다른 옵션은 Windows POSIX 하위 시스템입니다. 그러나 Windows NT를 만들 때 표준화된 유일한 POSIX 버전이었던 POSIX 1003.1만 지원합니다. 그 이후에는 대부분의 애플리케이션이 Win32로 변환되었기 때문에 이 하위 시스템을 확장할 필요가 거의 없었습니다. 1003.1 시스템은 1003.2의 기능, 네트워크 지원 등의 다양한 기능을 포함하지 않으므로 완전한 기능을 갖춘 애플리케이션에 대한 관심이 제한됩니다. Windows POSIX 하위 시스템에서 실행되는 완전한 기능을 갖춘 애플리케이션은 메모리 매핑된 파일, 네트워킹, 그래픽 등 Win32 애플리케이션에서 사용할 수 있는 Windows 기능에 액세스할 수 없습니다. VI, LS 및 GREP와 같은 애플리케이션이 Windows POSIX 하위 시스템의 주요 대상입니다.

## <a name="see-also"></a>참고 항목

[Visual C++ 포팅 및 업그레이드 가이드](visual-cpp-change-history-2003-2015.md)<br/>
[UNIX](../c-runtime-library/unix.md)<br/>
[유추 규칙](../build/reference/inference-rules.md)
