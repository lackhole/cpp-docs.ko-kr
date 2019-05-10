---
title: '연습: MSBuild를 사용 하 여 시각적 개체를 만들려면 C++ 프로젝트'
ms.date: 05/06/2019
helpviewer_keywords:
- 'msbuild (c++), walkthrough: create a project'
ms.assetid: 52350d1c-c373-4868-923c-5e8be6f67adb
ms.openlocfilehash: 8fb985cbf4e471589946e730e8bb09b43f0a5d84
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65446218"
---
# <a name="walkthrough-using-msbuild-to-create-a-visual-c-project"></a>연습: MSBuild를 사용 하 여 시각적 개체를 만들려면 C++ 프로젝트

이 연습에는 MSBuild 빌드는 Visual Studio를 사용 하는 방법을 보여 줍니다. C++ 명령 프롬프트에서 프로젝트입니다. C++ 소스 파일 및 Visual C++ 콘솔 응용 프로그램에 대 한 XML 기반 프로젝트 파일을 만드는 방법을 알아봅니다. 프로젝트를 빌드한 후 빌드 프로세스를 사용자 지정 하는 방법을 배웁니다.

이 연습에서는 다음 작업을 수행합니다.

- 프로젝트에 대 한 C++ 소스 파일을 만드는 중입니다.

- XML MSBuild 프로젝트 파일을 만드는 중입니다.

- MSBuild를 사용 하 여 프로젝트를 빌드해야 합니다.

- MSBuild를 사용 하 여 프로젝트를 사용자 지정할 수 있습니다.

## <a name="prerequisites"></a>전제 조건

이 연습을 진행하려면 먼저 다음 작업을 수행해야 합니다.

- Visual Studio의 복사본을 **C++를 사용한 데스크톱 개발** 워크 로드가 설치 합니다.

- MSBuild 시스템의 전체적으로 이해 합니다.

> [!NOTE]
> Visual Studio IDE를 사용 하 여 나중에 프로젝트 파일을 편집 하려는 경우에이 방법을 사용 하지 마십시오. .Vcxproj 파일을 수동으로 만든 프로젝트는 프로젝트 항목에 와일드 카드를 사용 하는 경우에 특히 Visual Studio IDE 편집 또는 로드 하 여 되지 않습니다.

> [!NOTE]
> 대부분의 하위 수준 빌드 지침에 포함 된 합니다 **.targets** 하 고 **.props** 속성에 저장 VCTargets 디렉터리에 정의 된 파일을 `$(VCTargetsPath)`. Visual Studio 2019 Enterprise Edition에서 이러한 파일에 대 한 기본 경로 C:\Program Files (x86) \Microsoft Visual Studio\2019\Enterprise\MSBuild\Microsoft\VC\v160\Microsoft.Cpp.Common.props 합니다.

## <a name="creating-the-c-source-files"></a>C++ 소스 파일 만들기

이 연습에서는 소스 파일 및 헤더 파일을 지정 된 프로젝트를 만들어야 합니다. 원본 파일 main.cpp에는 콘솔 응용 프로그램의 main 함수가 포함 되어 있습니다. 헤더 파일 main.h iostream 헤더 파일을 포함 하는 코드를 포함 합니다. 만들 수 있습니다 이러한 C++ 파일 Visual Studio 또는 텍스트를 사용 하 여 Visual Studio Code 같은 편집기.

### <a name="to-create-the-c-source-files-for-your-project"></a>프로젝트에 대 한 C++ 소스 파일을 만들려면

1. 프로젝트에 대 한 디렉터리를 만듭니다.

1. Main.cpp 라는 파일을 만들고이 파일에 다음 코드를 추가 합니다.

    ```cpp
    // main.cpp : the application source code.
    #include <iostream>
    #include "main.h"
    int main()
    {
       std::cout << "Hello, from MSBuild!\n";
       return 0;
    }
    ```

1. Main.h 라는 파일을 만들고이 파일에 다음 코드를 추가 합니다.

    ```cpp
    // main.h: the application header code.
    /* Additional source code to include. */
    ```

## <a name="creating-the-xml-msbuild-project-file"></a>XML MSBuild 프로젝트 파일 만들기

MSBuild 프로젝트 파일은 프로젝트 루트 요소를 포함 하는 XML 파일 (`<Project>`). 다음 예제에서는 프로젝트에서는 `<Project>` 요소에 자식 요소가 7 개 포함 되어 있습니다.

- 세 개의 항목 그룹 태그 (`<ItemGroup>`) 프로젝트 구성 및 플랫폼, 소스 파일 이름 및 헤더 파일 이름을 지정 하는 합니다.

- 3 개의 가져오기 태그 (`<Import>`)는 Microsoft Visual C++ 설정의 위치를 지정 합니다.

- 속성 그룹 태그 (`<PropertyGroup>`)는 프로젝트 설정을 지정 합니다.

### <a name="to-create-the-msbuild-project-file"></a>MSBuild 프로젝트 파일을 만들려면

1. 텍스트 편집기를 사용 하 여 명명 된 프로젝트 파일을 만듭니다 `myproject.vcxproj`를 추가한 다음 루트 `<Project>` 요소입니다. 루트 간에 다음 절차의 단계에 요소를 삽입 `<Project>` 태그입니다. (ToolsVersion을 사용 하 여 Visual Studio 2017을 사용 하는 경우 "15.0" =.)

    ```xml
    <Project DefaultTargets="Build" ToolsVersion="16.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
    </Project>
    ```

1. 다음 두 개의 추가 `<ProjectConfiguration>` 자식 요소에는 `<ItemGroup>` 요소입니다. 자식 요소 지정 디버그 및 릴리스 구성을 32 비트 Windows 운영 체제:

    ```xml
    <ItemGroup>
      <ProjectConfiguration Include="Debug|Win32">
        <Configuration>Debug</Configuration>
        <Platform>Win32</Platform>
      </ProjectConfiguration>
      <ProjectConfiguration Include="Release|Win32">
        <Configuration>Release</Configuration>
        <Platform>Win32</Platform>
      </ProjectConfiguration>
    </ItemGroup>
    ```

1. 다음 추가 `<Import>` 이 프로젝트에 대 한 기본 C++ 설정의 경로 지정 하는 요소:

    ```xml
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />
    ```

1. 다음 속성 그룹 요소 추가 (`<PropertyGroup>`)를 지정 하는 두 개의 프로젝트 속성입니다. (Visual Studio 2017을 사용 하는 경우 v141 사용 합니다.)

    ```xml
    <PropertyGroup>
      <ConfigurationType>Application</ConfigurationType>
      <PlatformToolset>v142</PlatformToolset>
    </PropertyGroup>
    ```

1. 다음 추가 `<Import>` 이 프로젝트에 대 한 현재 C++ 설정의 경로 지정 하는 요소:

    ```xml
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
    ```

1. 다음을 추가 합니다 `<ClCompile>` 자식 요소는 `<ItemGroup>` 요소입니다. 자식 요소에는 컴파일할 C/C++ 소스 파일의 이름을 지정 합니다.

    ```xml
    <ItemGroup>
      <ClCompile Include="main.cpp" />
    </ItemGroup>
    ```

   > [!NOTE]
   > `<ClCompile>` *빌드 대상을* 에 정의 된를 **VCTargets** 디렉터리입니다.

1. 다음을 추가 합니다 `<ClInclude>` 자식 요소는 `<ItemGroup>` 요소입니다. C/C++ 소스 파일에 대 한 헤더 파일의 이름을 지정 하는 자식 요소:

    ```xml
    <ItemGroup>
      <ClInclude Include="main.h" />
    </ItemGroup>
    ```

1. 다음 추가 `<Import>` 이 프로젝트의 대상을 정의 하는 파일의 경로 지정 하는 요소:

    ```xml
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.Targets" />
    ```

### <a name="complete-project-file"></a>전체 프로젝트 파일

다음 코드는 이전 절차에서 만든 전체 프로젝트 파일을 보여 줍니다. (Use ToolsVersion="15.0" for Visual Studio 2017.)

```xml
<Project DefaultTargets="Build" ToolsVersion="16.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <ItemGroup>
    <ProjectConfiguration Include="Debug|Win32">
      <Configuration>Debug</Configuration>
      <Platform>Win32</Platform>
    </ProjectConfiguration>
    <ProjectConfiguration Include="Release|Win32">
      <Configuration>Release</Configuration>
      <Platform>Win32</Platform>
    </ProjectConfiguration>
  </ItemGroup>
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />
  <PropertyGroup>
    <ConfigurationType>Application</ConfigurationType>
    <PlatformToolset>v142</PlatformToolset>
  </PropertyGroup>
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
  <ItemGroup>
    <ClCompile Include="main.cpp" />
  </ItemGroup>
  <ItemGroup>
    <ClInclude Include="main.h" />
  </ItemGroup>
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.Targets" />
</Project>
```

## <a name="using-msbuild-to-build-your-project"></a>MSBuild를 사용 하 여 프로젝트를 빌드

콘솔 응용 프로그램을 빌드하려면 명령 프롬프트에서 다음 명령을 입력 합니다.

`msbuild myproject.vcxproj /p:configuration=debug`

MSBuild 출력 파일에 대 한 디렉터리를 만듭니다 및를 컴파일하고 Myproject.exe 프로그램을 생성 하도록 프로젝트를 연결 합니다. 빌드 프로세스가 완료 되 면 다음 명령을 사용 하 여 디버그 폴더에서 응용 프로그램을 실행 하려면:

`myproject`

응용 프로그램에는 "Hello, from MSBuild!" 표시 됩니다. 콘솔 창에 표시합니다.

## <a name="customizing-your-project"></a>프로젝트 사용자 지정

MSBuild를 사용 하면 미리 정의 된 빌드 대상을 실행, 사용자 정의 속성을 적용 하 고 사용자 지정 도구, 이벤트를 사용 하 여 및 빌드 단계 수 있습니다. 이 섹션에서는 다음 작업을 보여 줍니다.

- 빌드 대상과 함께 MSBuild를 사용 합니다.

- 빌드 속성과 함께 MSBuild를 사용 합니다.

- 64 비트 컴파일러 및 도구를 사용 하 여 MSBuild를 사용 합니다.

- 다른 도구 집합과 함께 MSBuild를 사용 합니다.

- MSBuild 사용자 지정을 추가 합니다.

### <a name="using-msbuild-with-build-targets"></a>빌드 대상과 함께 MSBuild 사용

A *빌드 대상을* 는 명명 된 집합 빌드하는 동안 실행 될 수 있는 미리 정의 되거나 사용자 정의 명령입니다. 대상 명령줄 옵션을 사용 하 여 (`/t`) 빌드 대상을 지정 합니다. 에 대 한 합니다 `myproject` 예제 프로젝트, 미리 정의 된 **정리** 대상 debug 폴더의 모든 파일을 삭제 하 고 새 로그 파일을 만듭니다.

명령 프롬프트에서 정리 하려면 다음 명령을 입력 `myproject`합니다.

`msbuild myproject.vcxproj /t:clean`

### <a name="using-msbuild-with-build-properties"></a>빌드 속성과 함께 MSBuild 사용

속성 명령줄 옵션 (`/p`) 프로젝트 빌드 파일에서 속성을 재정의할 수 있습니다. 에 `myproject` 으로 예제 프로젝트, 릴리스 또는 디버그 빌드 구성을 지정 합니다 `Configuration` 속성입니다. 빌드한 응용 프로그램을 실행 하 게 되는 운영 체제에서 지정 된 된 `Platform` 속성입니다.

명령 프롬프트에서의 디버그 빌드를 만들려면 다음 명령을 입력 하 여 `myproject` 32 비트 Windows에서 실행 되도록 응용 프로그램입니다.

`msbuild myproject.vcxproj /p:configuration=debug /p:platform=win32`

가정 합니다 `myproject` 프로젝트 라는 사용자 지정 운영 체제 다른 구성과 64 비트 Windows에 대 한 구성을 정의 하는 예제 `myplatform`합니다.

명령 프롬프트 형식 릴리스를 만드는 데 다음 명령을 작성 하는 64 비트 Windows에서 실행 됩니다.

`msbuild myproject.vcxproj /p:configuration=release /p:platform=x64`

명령 프롬프트에 대 한 릴리스 빌드를 만들려면 다음 명령을 입력 `myplatform`합니다.

`msbuild myproject.vcxproj /p:configuration=release /p:platform=myplatform`

### <a name="using-msbuild-with-the-64-bit-compiler-and-tools"></a>64 비트 컴파일러 및 도구를 사용 하 여 MSBuild를 사용 하 여

기본적으로 64 비트 Windows에서 Visual Studio를 설치한, 64 비트 x64 네이티브 및 cross tools 설치 됩니다. 64 비트 컴파일러 및 도구를 설정 하 여 응용 프로그램을 빌드하는 데 MSBuild를 구성할 수 있습니다는 `PreferredToolArchitecture` 속성입니다. 이 속성은 프로젝트 구성 또는 플랫폼 속성에 영향을 주지 않습니다. 도구의 32 비트 버전은 기본적으로 사용 됩니다. 64 비트 버전의 컴파일러 및 도구를 지정 하려면 다음 속성 그룹 요소를 Myproject.vcxproj 프로젝트 파일에 추가 합니다 `Microsoft.Cpp.default.props` \<가져오기 / > 요소:

```xml
<PropertyGroup>
    <PreferredToolArchitecture>x64</PreferredToolArchitecture>
</PropertyGroup>
```

명령 프롬프트에서 64 비트 도구를 사용 하 여 응용 프로그램을 빌드하려면 다음 명령을 입력 합니다.

`msbuild myproject.vcxproj /p:PreferredToolArchitecture=x64`

### <a name="using-msbuild-with-a-different-toolset"></a>다른 도구 집합과 함께 MSBuild 사용

도구 집합과 라이브러리가 다른 버전의 Visual C++ 설치 된 경우 MSBuild는 현재 Visual C++ 버전 또는 설치 된 다른 버전에 대 한 응용 프로그램을 빌드할 수 있습니다. 예를 들어, Windows XP 용 Visual C++ 11.0 도구 집합을 지정 하려면 Visual Studio 2012를 설치한 경우 추가한 다음 속성 그룹 요소를 Myproject.vcxproj 프로젝트 파일을 `Microsoft.Cpp.props` \<가져오기 / > 요소:

```xml
<PropertyGroup>
    <PlatformToolset>v110_xp</PlatformToolset>
</PropertyGroup>
```

Visual C++ 11.0 Windows XP 도구 집합을 사용 하 여 프로젝트를 다시 작성 하려면 다음 명령을 입력 합니다.

`msbuild myproject.vcxproj /p:PlatformToolset=v110_xp /t:rebuild`

### <a name="adding-msbuild-customizations"></a>MSBuild 사용자 지정 추가

MSBuild는 빌드 프로세스에 맞게 다양 한 방법을 제공 합니다. 다음 항목에는 MSBuild 프로젝트에 사용자 지정 빌드 단계, 도구 및 이벤트를 추가 하는 방법을 보여 줍니다.

- [방법: MSBuild 프로젝트에 사용자 지정 빌드 단계 추가](how-to-add-a-custom-build-step-to-msbuild-projects.md)

- [방법: MSBuild 프로젝트에 사용자 지정 빌드 도구 추가](how-to-add-custom-build-tools-to-msbuild-projects.md)

- [방법: MSBuild 프로젝트에서 빌드 이벤트 사용](how-to-use-build-events-in-msbuild-projects.md)
