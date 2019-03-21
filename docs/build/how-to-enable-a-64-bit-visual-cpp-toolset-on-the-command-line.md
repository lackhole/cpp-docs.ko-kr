---
title: '방법: 명령줄에서 64 비트 MSVC 도구 집합을 사용 하도록 설정'
ms.date: 03/29/2018
helpviewer_keywords:
- x64 [C++]
- 64-bit compiler [C++], command line usage
- 64-bit compiler [C++], toolset enabling at command line
- command line [C++], 64-bit compiler
- Itanium [C++], command-line compiler
- IPF
- Itanium [C++]
- IPF, command-line compiler
- x64 [C++], command-line compiler
ms.assetid: 4da93a19-e20d-4778-902a-5eee9a6a90b5
ms.openlocfilehash: b30b831522016ce61f138f7e0521c42ff44e04d9
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57809771"
---
# <a name="how-to-enable-a-64-bit-x64-hosted-msvc-toolset-on-the-command-line"></a>방법: 64 비트, x64 호스트 명령줄에서 MSVC 도구 집합

Visual Studio는 c + + 컴파일러, 링커 및 32 비트, 64 비트 또는 ARM 기반 Windows 운영 체제에서 실행할 수 있는 앱의 플랫폼별 버전을 만드는 데 사용할 수 있는 도구도 포함 되어 있습니다. 다른 선택적 Visual Studio 워크 로드를 통해 c + + 도구를 사용 하 여 iOS, Android 및 Linux와 같은 다른 플랫폼을 대상으로 수 있습니다. 기본 빌드 아키텍처 32 비트, x86에 호스트 된 도구를 사용 하 여 32 비트, x86 네이티브 Windows 코드를 작성 합니다. 그러나 있을 것은 64 비트 컴퓨터입니다. X86, x64 또는 ARM 프로세서에 대 한 코드를 작성 하는 경우 64 비트, x64 호스트 도구 집합을 사용 하 여 프로세서 및 64 비트 코드에 사용 가능한 메모리 공간 활용을 걸릴 수 있습니다.

> [!NOTE]
> 각 Visual Studio 버전에 포함 된 특정 도구에 대 한 자세한 내용은 [Visual Studio 버전의 Visual c + + 도구 및 기능](../ide/visual-cpp-tools-and-features-in-visual-studio-editions.md)합니다.
>
> 64 비트 응용 프로그램을 만들려면 Visual Studio IDE를 사용 하는 방법에 대 한 정보를 참조 하세요. [방법: 64비트, x64 플랫폼을 대상으로 한 Visual C++ 프로젝트 구성](how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md)을 참조하세요.

C + + 워크 로드를 Visual Studio 설치 관리자에서를 설치 하면 항상 32 비트, x86에 호스트 된, 네이티브 및 크로스 컴파일러 도구를 빌드하는 x86 및 x64 코드를 설치 합니다. 유니버설 Windows 플랫폼 워크 로드를 포함 하는 경우 또한 ARM 코드를 빌드하려면 크로스 컴파일러 x86에 호스트 된 도구를 설치 합니다. 64 비트 x64에서 이러한 워크 로드를 설치 하는 경우 프로세서도 64 비트 네이티브를 얻고 코드 컴파일러 및 도구를 빌드 x86, x64, ARM 교차 합니다. 32 비트 및 64 비트 도구는 동일한 코드를 생성 하지만 64 비트 도구 미리 컴파일된 헤더 기호 및 전체 프로그램 최적화에 대 한 더 많은 메모리를 지원 합니다 ([/GL](reference/gl-whole-program-optimization.md) 하 고 [/LTCG](reference/ltcg-link-time-code-generation.md)) 옵션입니다. 32 비트 도구를 사용 하는 경우 실행 메모리 한계에 도달 하는 경우 64 비트 도구를 사용해 보세요.

## <a name="use-a-64-bit-hosted-developer-command-prompt-shortcut"></a>64 비트 호스트 개발자 명령 프롬프트 바로 가기를 사용 하 여

Visual Studio 64 비트 Windows 운영 체제에서 설치 될 때 64 비트, x64 호스트 네이티브 및 크로스 컴파일러 추가 개발자 명령 프롬프트 바로 가기를 사용할 수 있습니다. Windows 10에서 이러한 명령 프롬프트에 액세스 하려면 합니다 **시작** 메뉴에서 예를 들어 Visual Studio의 버전에 대 한 폴더를 열고 **Visual Studio 2017**, x64 네이티브 또는 크로스 도구 중 하나를 선택 하 고 개발자 명령 프롬프트입니다. Windows 8에서 이러한 명령 프롬프트에 액세스 하려면 합니다 **시작** 화면이 열리면서 **모든 앱**합니다. 설치 된 버전의 Visual Studio에 대 한 머리글 아래에서 엽니다는 **Visual Studio** 폴더 (Visual Studio의 이전 버전에서에 이름을 지정할 수 있습니다 **Visual Studio Tools**). 이전 버전의 Windows에서는 선택 **시작**, 확장 **프로그램도**, 버전에 대 한 폴더 **Visual Studio** (및 이전 버전의 Visual Studio  **Visual Studio Tools**). 자세한 내용은 [개발자 명령 프롬프트 바로 가기](building-on-the-command-line.md#developer_command_prompt_shortcuts)를 참조하세요.

## <a name="use-vcvarsallbat-to-set-a-64-bit-hosted-build-architecture"></a>Vcvarsall.bat를 사용 하 여 64 비트로 호스팅된 빌드 아키텍처를 설정 합니다.

파일을 명령 네이티브 또는 크로스 컴파일러 도구는 vcvarsall.bat를 실행 하 여 명령줄에서 빌드 구성을 사용할 수 있습니다. 이 명령 파일의 경로 구성 하 고 있는 특정 환경 변수 기존 명령 프롬프트 창에서 아키텍처를 빌드합니다. 특정 지침은 [개발자 명령 파일 위치](building-on-the-command-line.md#developer_command_file_locations)합니다.

## <a name="see-also"></a>참고자료

[64 비트 x64에 대 한 c + + 프로젝트 구성 대상](configuring-programs-for-64-bit-visual-cpp.md)<br/>
