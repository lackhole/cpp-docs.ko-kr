---
title: Visual Studio의 CMake 프로젝트에서 clang/LLVM 지원
ms.date: 07/01/2019
ms.description: Configure a CMake project in Visual Studio to use the Clang/LLVM toolchain.
helpviewer_keywords:
- Clang support for C++
ms.openlocfilehash: 6773d9cdb076ef305ba635306f3bc9c6575d2203
ms.sourcegitcommit: b233f05adae607f75815111006a771c432df5a9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2019
ms.locfileid: "67517108"
---
# <a name="clangllvm-support-in-visual-studio-cmake-projects"></a>Visual Studio의 CMake 프로젝트에서 clang/LLVM 지원

::: moniker range="<=vs-2017"

Clang 지원은 Visual Studio 2019 사용할 수 있습니다.

::: moniker-end

::: moniker range="vs-2019"

편집 및 디버그를 Clang를 사용 하 여 Visual Studio를 사용할 수 있습니다 C++ 는 대상 Windows 또는 Linux CMake 프로젝트입니다.

**Windows**: Visual Studio 2019 16.1 버전에는 Windows를 대상으로 하는 CMake 프로젝트에서 Clang/LLVM을 사용 하 여 디버그 및 편집, 빌드에 대 한 지원이 포함 됩니다. 

**Linux**: Linux CMake 프로젝트 특별 Visual Studio 지원 없이 필요 합니다. Clang 배포판의 패키지 관리자를 사용 하 여 설치 하 고 CMakeLists.txt 파일에 적절 한 명령을 추가할 수 있습니다.

## <a name="install"></a>설치

Visual Studio에서 최상의 IDE 지원의 경우 Windows에 대 한 최신 Clang 컴파일러 도구를 사용 하는 것이 좋습니다. 아직 없는 것을 하는 경우 Visual Studio 설치 관리자를 열고 선택 하 여 설치할 수 있습니다 **Windows 용 Clang 컴파일러** 아래에서 **를 사용한 데스크톱 개발 C++**  선택적 구성 요소입니다.

![Clang 구성 요소 설치](media/clang-install-vs2019.png)

## <a name="create-a-new-configuration"></a>새 구성 만들기

CMake 프로젝트에 새 Clang 구성을 추가:

1. CMakeLists.txt를 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 선택한 **프로젝트에 대 한 CMake 설정**합니다.

1. 아래 **구성을**, 키를 눌러 합니다 **구성 추가** 단추:

   ![구성 추가](media/cmake-add-config-icon.png)

1. 선택 원하는 Clang 구성 (Windows 및 Linux에 대 한 별도 Clang 구성이 제공 되는 참고)을 누릅니다 **선택**:

   ![CMake Clang 구성](media/cmake-clang-configuration.png)

1. 이 구성을 수정 하려면 사용 합니다 **CMake 설정 편집기**합니다. 자세한 내용은 [CMake 사용자 지정 빌드 설정을 Visual Studio에서](customize-cmake-settings.md)합니다.

## <a name="modify-an-existing-configuration-to-use-clang"></a>Clang을 사용 하도록 기존 구성을 수정합니다

Clang을 사용 하는 기존 구성을 수정 하려면 다음이 단계를 수행 합니다.

1. CMakeLists.txt를 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 선택한 **프로젝트에 대 한 CMake 설정**합니다.

1. 아래 **일반** 선택 합니다 **도구 집합** 드롭다운에서 원하는 Clang 도구 집합을 선택 하 고:

   ![CMake Clang 도구 집합](media/cmake-clang-toolset.png)

## <a name="custom-clang-locations"></a>사용자 지정 Clang 위치

기본적으로 Visual Studio는 Clang 두 곳에서 찾습니다.

- (Windows) Visual Studio 설치 관리자를 함께 제공 되는 Clang/LLVM의 내부적으로 설치 된 복사본입니다.
- (Windows 및 Linux) PATH 환경 변수입니다.

설정 하 여 다른 위치를 지정할 수 있습니다 합니다 **CMAKE_C_COMPILER** 하 고 **CMAKE_CXX_COMPILER** CMake 변수 **CMake 설정**:

![CMake Clang 도구 집합](media/clang-location-cmake.png)

## <a name="clang-compatibility-modes"></a>Clang 호환성 모드

Windows 구성에 대 한 CMake 기본적으로 호출에서 Clang [clang-cl](https://llvm.org/devmtg/2014-04/PDFs/Talks/clang-cl.pdf) 모드 및 표준 라이브러리의 Microsoft 구현에 링크 합니다. 기본적으로 **clang cl.exe** 에 위치한 `C:\Program Files (x86)\Microsoft Visual Studio\2019\Common7\IDE\CommonExtensions\Microsoft\Llvm\bin`합니다.

 이러한 값을 수정할 수 있습니다 **CMake 설정** 아래에서 **CMake 변수 및 캐시**합니다. 클릭 **Show advanced 변수**합니다. 찾기 아래로 스크롤하여 **CMAKE_CXX_COMPILER**를 클릭 합니다 **찾아보기** 다른 컴파일러 경로 지정 하는 단추입니다.

## <a name="edit-build-and-debug"></a>편집, 빌드 및 디버그

Clang 구성을 설정한 후에 빌드 및 프로젝트를 디버깅할 수 있습니다. Visual Studio는 Clang 컴파일러를 사용 하는 IntelliSense, 강조, 탐색 및 다른 편집 기능을 제공 하는 검색 합니다. 오류 및 경고에 표시 되는 **출력 창**합니다.

디버그 시 중단점, 메모리 및 데이터 시각화 및 다른 대부분의 디버깅 기능을 사용할 수 있습니다. 편집 하며 계속 하기와 같은 일부 컴파일러 종속 기능 Clang 구성에 사용할 수 있습니다.

![CMake Clang 디버깅](media/clang-debug-visualize.png)

::: moniker-end
