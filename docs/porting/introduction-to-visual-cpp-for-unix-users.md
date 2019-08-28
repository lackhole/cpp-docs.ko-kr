---
title: UNIX 사용자를 위한 Visual C++ 소개
ms.date: 09/01/2017
helpviewer_keywords:
- UNIX [C++]
ms.assetid: 36108b31-e7fa-49a8-a1f7-7077fcbec873
ms.openlocfilehash: 7f73e51e02eafe46c279a8f828803912d8cd190a
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2019
ms.locfileid: "69631692"
---
# <a name="introduction-to-visual-c-for-unix-users"></a>UNIX 사용자를 위한 Visual C++ 소개

이 항목에서는 Visual Studio를 처음 사용하고 C++ 및 Visual Studio IDE(통합 개발 환경)를 사용하여 생산성을 높이려는 UNIX 사용자에게 정보를 제공합니다.

## <a name="getting-started-on-the-command-line"></a>명령줄에서 시작

UNIX 명령줄 환경을 사용하는 것과 유사한 방식으로 명령줄에서 C++ 컴파일러를 사용할 수 있습니다. 명령줄 C 및 C++ 컴파일러(CL.EXE), 링커(LINK.EXE) 및 UNIX에서 만든 유틸리티의 Microsoft 버전인 NMAKE.EXE를 비롯한 기타 도구를 사용하여 명령 프롬프트에서 컴파일합니다.

UNIX에서는 /usr/bin 등의 공용 폴더에 명령이 설치됩니다. Visual Studio에서 명령줄 도구는 Visual Studio 설치 디렉터리의 VC\bin 하위 디렉터리 및 그 하위 디렉터리에 설치됩니다. UNIX와 달리 이러한 도구는 일반 명령 프롬프트 창에서 사용할 수 없습니다. 명령줄 도구를 사용하려면 개발자 명령 프롬프트 바로 가기를 사용하거나 vcvarsall.bat 같은 개발자 명령 파일을 실행하세요. 그러면 명령줄에서 C++ 프로그램을 컴파일하는 데 필요한 경로 및 기타 환경 변수가 설정됩니다. 자세한 내용은 [명령줄에서 C/C++ 코드 빌드](../build/building-on-the-command-line.md) 및 [연습: 명령줄에서 네이티브 C++ 프로그램 컴파일](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)을 참조하세요.

개발자 명령 프롬프트 바로 가기를 열려면 데스크톱 검색 컨트롤에서 *개발자 명령 프롬프트*를 입력하고 해당 버전의 Visual Studio에 대한 **개발자 명령 프롬프트** 결과를 선택합니다. 특정 호스트 및 대상 아키텍처에 대해 미리 구성된 개발자 명령 프롬프트를 선택하려면 **시작** 메뉴(바탕 화면 모서리의 Windows 아이콘)를 연 다음 해당 버전의 Visual Studio에 대한 폴더(예: **Visual Studio 2017**)로 스크롤합니다. 폴더를 열고 기본 호스트 및 대상 아키텍처에 대한 명령 프롬프트 바로 가기를 선택합니다.

Visual Studio 디버거, IntelliSense 코드 조회 및 명령문 완성, 비주얼 디자이너, 프로젝트 관리 등과 보다 강력한 기능을 활용하려면 Visual Studio IDE를 사용해야 합니다.

## <a name="debugging-your-code"></a>코드 디버그

명령줄을 사용하고 개발용 워크스테이션에서 애플리케이션을 실행하는 경우 코드에서 메모리 액세스 위반, 처리되지 않은 예외 또는 기타 복구할 수 없는 오류가 발생할 때 Visual Studio 디버거를 실행하는 대화 상자가 표시되는 것을 확인할 수 있습니다. **확인**을 클릭하면 Visual Studio 개발 환경이 시작되고 디버거가 오류 지점에서 열립니다. 이러한 방식으로 애플리케이션을 디버그할 수 있으며, 이 경우 [/Z7, /Zi, /ZI(디버그 정보 형식)](../build/reference/z7-zi-zi-debug-information-format.md) 스위치로 컴파일한 경우에만 소스 코드를 사용할 수 있습니다. 자세한 내용은 [네이티브 코드 디버그](/visualstudio/debugger/debugging-native-code) 및 [C++ 데스크톱 개발에 Visual Studio IDE 사용](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)을 참조하세요.

## <a name="using-the-development-environment"></a>개발 환경 사용

개발 환경을 사용하면 *프로젝트*의 소스 코드를 보다 쉽게 편집 및 빌드할 수 있습니다. 프로젝트는 라이브러리 또는 실행 파일과 같은 하나의 단위로 컴파일되는 소스 및 관련 파일의 컬렉션입니다. 또한 프로젝트에는 파일을 빌드하는 방법에 대한 정보도 들어 있습니다. 프로젝트 정보는 확장명이 .prj인 프로젝트 파일에 저장됩니다.

잠재적으로 각각 다른 컴파일러 옵션 집합이나 다른 언어로 빌드된 여러 라이브러리와 실행 파일로 구성된 애플리케이션은 단일 *솔루션*에 속하는 여러 프로젝트에 저장됩니다. 솔루션은 여러 프로젝트를 함께 그룹화하는 컨테이너에 대한 추상화입니다. 솔루션 정보는 확장명이 .sln 솔루션 파일에 저장됩니다. 자세한 내용은 [Visual Studio의 솔루션 및 프로젝트](/visualstudio/ide/solutions-and-projects-in-visual-studio) 및 [C++ 데스크톱 개발에 Visual Studio IDE 사용](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)을 참조하세요.

## <a name="importing-your-existing-code"></a>기존 코드 가져오기

C++ 컴파일러를 사용하여 메이크파일을 포함하거나 포함하지 않고 컴파일하도록 설정된 기존 코드를 빌드하고 Visual Studio 프로젝트에 배치할 수 있습니다. 자세한 내용은 [방법: 기존 코드에서 C++ 프로젝트 만들기](../build/how-to-create-a-cpp-project-from-existing-code.md)를 참조하세요.

## <a name="creating-a-new-project"></a>새 프로젝트 만들기

개발 환경에서 새 프로젝트를 만들 수 있습니다. Visual Studio에서는 여러 일반적인 프로젝트에 대한 표준 코드를 제공하는 다양한 템플릿을 제공합니다. 애플리케이션 마법사를 사용하여 다양한 애플리케이션 형식에 대한 코드 개요로 프로젝트를 생성할 수 있습니다.

**콘솔 애플리케이션(Win32) 마법사**를 사용하면 빈 프로젝트로 시작할 수 있습니다. **빈 프로젝트** 확인란을 선택합니다. 나중에 프로젝트에 새 파일과 기존 파일을 추가할 수 있습니다.

프로젝트를 만들 때 프로젝트에 이름을 지정해야 합니다. 기본적으로 프로젝트 이름은 프로젝트에서 빌드된 DLL(동적 연결 라이브러리) 또는 실행 파일의 이름과 같습니다. 자세한 내용은 [솔루션 및 프로젝트 만들기](/visualstudio/ide/creating-solutions-and-projects)를 참조하세요.

## <a name="microsoft-specific-modifiers"></a>Microsoft 전용 한정자

Microsoft C++ 컴파일러는 Windows 운영 체제에 대한 프로그래밍을 지원하기 위해 표준 C++ 프로그래밍 언어에 대한 몇 가지 확장을 구현합니다. 이러한 확장은 특히 스토리지 클래스 특성, 함수 호출 규칙 및 기본 주소를 지정하는 데 사용됩니다. 지원되는 C++ 확장의 전체 목록은 [Microsoft 전용 한정자](../cpp/microsoft-specific-modifiers.md)를 참조하세요.

`/Za` 컴파일러 옵션을 통해 C++에 대한 모든 Microsoft 전용 확장을 사용하지 않도록 설정할 수 있습니다. 이 옵션은 여러 플랫폼에서 실행할 코드를 작성하려는 경우에 권장됩니다. `/Za` 컴파일러 옵션에 대한 자세한 내용은 [/Za, /Ze(언어 확장명 사용 안 함)](../build/reference/za-ze-disable-language-extensions.md)를 참조하세요. C++ 컴파일러 규칙에 대한 자세한 내용은 [Visual C++ 언어 규칙](../overview/visual-cpp-language-conformance.md) 및 [비표준 동작](../cpp/nonstandard-behavior.md)을 참조하세요.

## <a name="precompiled-headers"></a>미리 컴파일된 헤더

Microsoft C 및 C++ 컴파일러는 인라인 코드를 포함하여 모든 C 또는 C++ 코드를 미리 컴파일하는 옵션을 제공합니다. 이 성능 기능을 사용하여 안정적인 코드 본문을 컴파일하고, 코드의 컴파일된 상태를 파일에 저장하고, 후속 컴파일 중 미리 컴파일된 코드와 아직 개발 중인 코드를 결합할 수 있습니다. 안정적인 코드는 다시 컴파일할 필요가 없기 때문에 각 후속 컴파일 속도가 향상됩니다.

기본적으로 미리 컴파일된 코드는 *pch.h* 및 *pch.cpp*(Visual Studio 2017 및 이전 버전에서 *stdafx.h* 및 *stdafx.cpp*) 파일에서 모두 지정됩니다. **미리 컴파일된 헤더** 옵션을 선택 취소하지 않으면 **새 프로젝트** 마법사가 자동으로 이러한 파일을 만듭니다. 미리 컴파일된 헤더에 대한 자세한 내용은 [미리 컴파일된 헤더 파일 만들기](../build/creating-precompiled-header-files.md)를 참조하세요.

## <a name="related-sections"></a>관련 단원

자세한 내용은 [UNIX에서 Win32로 이식](../porting/porting-from-unix-to-win32.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[프로젝트 및 빌드 시스템](../build/projects-and-build-systems-cpp.md)
