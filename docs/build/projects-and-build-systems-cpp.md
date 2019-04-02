---
title: C/c + + 프로젝트 및 Visual Studio에서 빌드 시스템
ms.description: Use Visual Studio to compile and build C++ projects for Windows, ARM or Linux based on any project system.
ms.date: 12/08/2018
f1_keywords:
- vcbuilding
- buildingaprogramVC
helpviewer_keywords:
- builds [C++]
- Visual C++ projects, building
- projects [C++], building
- builds [C++], options
- Visual C++, build options
ms.assetid: fa6ed4ff-334a-4d99-b5e2-a1f83d2b3008
ms.openlocfilehash: 6a4048d741cf291d8d6173c1444b6933523c6851
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58775428"
---
# <a name="cc-projects-and-build-systems-in-visual-studio"></a>C/c + + 프로젝트 및 Visual Studio에서 빌드 시스템

편집, 컴파일 및 Visual Studio 프로젝트 또는 MSVC 도구 집합을 사용 하 여 컴파일하는 코드를 변경 하지 않고도 전체 IntelliSense 지원을 사용 하 여 기본 c + + 코드를 빌드하려면 Visual Studio 2017을 사용할 수 있습니다. 예를 들어, 원격 Linux 컴퓨터에서 g + +를 사용 하는 Linux에 대 한 컴파일 다음 Windows 컴퓨터에서 Visual Studio에서 플랫폼 간 CMake 프로젝트를 편집할 수 있습니다.

## <a name="c-compilation"></a>C + + 컴파일

하 *빌드* 하나 이상의 파일에서 소스 코드를 컴파일하고 다음 실행 파일 (.exe), 동적 부하 라이브러리 (.dll) 또는 정적 라이브러리 (.lib)에 해당 파일을 연결 하는 c + + 프로그램을 의미 합니다. 

기본 c + + 컴파일에서는 세 가지 주요 단계가 포함 됩니다.

- C + + 전처리기는 각 소스 파일에서 모든 #directives 및 매크로 정의 변환합니다. 이렇게 한 *변환 단위*합니다.
- C + + 컴파일러는 어떤 컴파일러 옵션을 설정한 적용 개체 (.obj) 파일에 각 변환 단위를 컴파일합니다.
- 합니다 *링커* 설정 된 링커 옵션을 적용 된 단일 실행 파일에 개체 파일을 병합 합니다. 

## <a name="the-msvc-toolset"></a>MSVC 도구 집합

Microsoft c + + 컴파일러, 링커, 표준 라이브러리 및 관련된 유틸리티 (도구 체인을 빌드하거나 "도구" 라고도 함)는 MSCV 컴파일러 도구 집합을 구성 합니다. 이러한 Visual Studio에 포함 됩니다. 또한 다운로드 하 고에서 독립 실행형 패키지로 도구 집합을 무료로 사용할 수 있습니다 합니다 [Visual Studio 2017 용 Build Tools 다운로드 위치](https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2017)합니다.

MSVC 컴파일러 (cl.exe) 직접 명령줄에서 호출 하 여 간단한 프로그램을 빌드할 수 있습니다. 다음 명령을 단일 소스 코드 파일을 받고 호출 하는 호출 하는 실행 파일을 빌드하는 cl.exe *hello.exe*: 

```cmd
cl /EHsc hello.cpp
```
여기서는 컴파일러 (cl.exe)를 사용 하는 c + + 전처리기 및 링커는 최종 출력 파일을 생성 하기 위해 자동으로 호출 note 합니다.  자세한 내용은 [명령줄에서 빌드](building-on-the-command-line.md)합니다.

## <a name="build-systems-and-projects"></a>시스템 및 프로젝트를 빌드하십시오

대부분의 실제 프로그램 종류의 일부를 사용 *빌드 시스템* 여러 구성에 대 한 여러 소스 파일의 복잡성을 관리 하려면 (즉, 디버그 및 릴리스), 여러 플랫폼 (x86, x64, ARM, 등), 사용자 지정 빌드 단계 및 특정 순서에 따라 컴파일해야 하는 여러 실행 파일입니다. 빌드 구성 파일에서 설정을 확인 하 고 컴파일러를 호출 하기 전에 빌드 시스템에서 입력으로 해당 파일을 허용 합니다. 소스 코드 파일 및 실행 파일을 빌드하는 데 필요한 빌드 구성 파일의 집합 이라고는 *프로젝트*합니다. 

다음은 c + +-Visual Studio 프로젝트에 대 한 다양 한 옵션을 보여 줍니다.

- Visual Studio IDE를 사용 하 여 Visual Studio 프로젝트를 만들고 속성 페이지를 사용 하 여 구성 합니다. Visual Studio 프로젝트는 Windows에서 실행 되는 프로그램을 생성 합니다. 개요를 보려면 [컴파일 및 빌드](/visualstudio/ide/compiling-and-building-in-visual-studio) Visual Studio 설명서에서.

- CMakeLists.txt 파일이 포함 된 폴더를 엽니다. CMake 지원은 Visual Studio에 통합 됩니다. 편집, 테스트 및 어떤 방식으로든에서 CMake 파일을 수정 하지 않고 디버그 IDE를 사용할 수 있습니다. 이 옵션을 사용 하면 다른 편집기를 사용할 수 있는 다른 동일한 CMake 프로젝트에서 사용할 수 있습니다. CMake는 플랫폼 간 개발을 위한 권장된 방법입니다. 자세한 내용은 [CMake 프로젝트](cmake-projects-in-visual-studio.md)합니다.
 
- 프로젝트 파일이 없는 느슨한 원본 파일 폴더를 엽니다. Visual Studio는 빌드 파일을 추론을 사용 합니다. 이 컴파일 및 간단한 콘솔 응용 프로그램을 실행 하는 쉬운 방법. 자세한 내용은 [폴더 열기 프로젝트](open-folder-projects-cpp.md)합니다.

- 통해 메이크파일을 포함 하거나 다른 빌드 시스템 구성 파일을 포함 하는 폴더를 엽니다. 폴더에 JSON 파일을 추가 하 여 임의의 빌드 명령을 호출 하려면 Visual Studio를 구성할 수 있습니다. 자세한 내용은 [폴더 열기 프로젝트](open-folder-projects-cpp.md)합니다.
 
- Visual Studio에서 Windows 메이크파일을 엽니다. 자세한 내용은 [NMAKE 참조](reference/nmake-reference.md)합니다.

## <a name="msbuild-from-the-command-line"></a>명령줄에서 MSBuild 

명령줄 옵션과 함께.vcxproj 파일을 전달 하 여 명령줄에서 MSBuild를 호출할 수 있습니다. 이 방법의 MSBuild 잘 이해 해야 하 고 반드시 필요한 경우에 권장 됩니다. 자세한 내용은 [MSBuild](msbuild-visual-cpp.md)를 참조하세요.

## <a name="in-this-section"></a>섹션 내용

[Visual Studio 프로젝트](creating-and-managing-visual-cpp-projects.md) 해당 네이티브를 사용 하 여 Visual Studio에서 프로젝트 빌드 시스템 (MSBuild) 만들기, 구성 및 c + +를 작성 하는 방법입니다.

[CMake 프로젝트](cmake-projects-in-visual-studio.md) 코드, 빌드 및 Visual Studio의 CMake 프로젝트를 배포 하는 방법입니다.

[폴더 열기 프로젝트](open-folder-projects-cpp.md) 모든 임의의 빌드 시스템 또는 없습니다 빌드 시스템을 기반으로 Visual Studio를 사용 하 여 코딩, 빌드 및 c + + 프로젝트를 배포 하는 방법입니다. 전혀. 

[릴리스 빌드](release-builds.md) 만들고 최적화 된 릴리스 문제를 해결 하는 방법을 최종 사용자에 게 배포에 대 한 빌드합니다.

[명령줄에서 MSVC 도구 집합 사용](building-on-the-command-line.md)<br/>
C/c + + 컴파일러를 사용 하 여 Visual Studio IDE를 사용 하지 않고 명령줄에서 직접 도구를 구축 하는 방법을 설명 합니다.

[Visual Studio에서 Dll 빌드](dlls-in-visual-cpp.md) 만들고, 디버그 하 고 Visual Studio에서 C/c + + Dll (공유 라이브러리)을 배포 하는 방법입니다.

[연습: 정적 라이브러리 만들기 및 사용](walkthrough-creating-and-using-a-static-library-cpp.md) .lib 이진 파일을 만드는 방법.

[C/c + + 격리 된 응용 프로그램 및 side-by-side-어셈블리를 빌드](building-c-cpp-isolated-applications-and-side-by-side-assemblies.md) 격리 된 응용 프로그램 및 side-by-side-어셈블리 아이디어를 기반으로 Windows 데스크톱 응용 프로그램에 대 한 배포 모델을 설명 합니다.

[64 비트 x64에 대 한 c + + 프로젝트 구성 대상](configuring-programs-for-64-bit-visual-cpp.md) 어떻게 도구 빌드는 MSVC 하드웨어 64 비트 x64 대상으로 합니다.

[ARM 프로세서에 대 한 c + + 프로젝트 구성](configuring-programs-for-arm-processors-visual-cpp.md) MSVC 빌드 도구를 사용 하 여 ARM 하드웨어를 대상으로 하는 방법입니다.

[코드 최적화](optimizing-your-code.md) 단계별 프로그램 최적화를 비롯 한 다양 한 방법으로 코드를 최적화 하는 방법입니다.

[Windows XP 용 프로그램 구성](configuring-programs-for-windows-xp.md) 대상 Windows XP의 MSVC 도구를 구축 하는 방법입니다.

[C/C++ 빌드 참조](reference/c-cpp-building-reference.md)<br/>
C++, 컴파일러/링커 옵션 및 다양한 빌드 도구를 사용한 프로그램 빌드와 관련된 참조 문서의 링크를 제공합니다.
