---
title: 예제 프로젝트 파일
ms.date: 10/09/2018
helpviewer_keywords:
- .vcxproj files
- C++ projects, project file format
ms.assetid: 5261cf45-3136-40a6-899e-dc1339551401
ms.openlocfilehash: cfe40d6520187212ab77607273c555f12012fd02
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319826"
---
# <a name="project-files"></a>프로젝트 파일

Visual C++ 프로젝트 파일은 .vcxproj 파일 이름 확장명을 가진 XML 기반 파일이며 Visual C++ 프로젝트를 빌드하는 데 필요한 정보를 포함합니다. 프로젝트 파일은 확장명이 *.props* 또는 *.targets*인 다양한 프로젝트 파일을 가져옵니다. 이러한 파일에는 추가 빌드 정보가 포함되어 있으며 다른 *.props* 또는 *.targets* 파일을 참조할 수도 있습니다. 파일 경로(예를 들면 `$(VCTargetsPath)`)의 매크로는 Visual Studio 설치에 따라 다릅니다. 이러한 매크로 대 한 자세한 내용은 및 *.props* 하 고 *.targets* 파일을 참조 하십시오 [VC + + Directories Property Page](vcpp-directories-property-page.md)를 [설정 C++ 컴파일러 및 빌드 Visual Studio에서 속성](../working-with-project-properties.md) 하 고 [에 대 한 일반 매크로 빌드 명령 및 속성](common-macros-for-build-commands-and-properties.md)합니다.

## <a name="example"></a>예제

다음 샘플.vcxproj 파일은 **새 프로젝트** 대화 상자에서 **Win32 콘솔 애플리케이션**을 지정하여 생성되었습니다. 프로젝트 파일을 처리하려면 명령줄에서 Msbuild.exe 도구를 사용하거나 IDE에서 **빌드** 명령을 사용합니다. (필요한 원본 및 헤더 파일이 제공되지 않았기 때문에 이 샘플을 처리할 수 없습니다.) 프로젝트 파일의 XML 요소에 대한 자세한 내용은 [프로젝트 파일 스키마 참조](/visualstudio/msbuild/msbuild-project-file-schema-reference)를 참조하세요.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Project DefaultTargets="Build" ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <ItemGroup Label="ProjectConfigurations">
    <ProjectConfiguration Include="Debug|Win32">
      <Configuration>Debug</Configuration>
      <Platform>Win32</Platform>
    </ProjectConfiguration>
    <ProjectConfiguration Include="Release|Win32">
      <Configuration>Release</Configuration>
      <Platform>Win32</Platform>
    </ProjectConfiguration>
  </ItemGroup>
  <PropertyGroup Label="Globals">
    <ProjectGuid>{96F21549-A7BF-4695-A1B1-B43625B91A14}</ProjectGuid>
    <Keyword>Win32Proj</Keyword>
    <RootNamespace>SomeProjName</RootNamespace>
  </PropertyGroup>
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.Default.props" />
  <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'" Label="Configuration">
    <ConfigurationType>Application</ConfigurationType>
    <CharacterSet>Unicode</CharacterSet>
  </PropertyGroup>
  <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|Win32'" Label="Configuration">
    <ConfigurationType>Application</ConfigurationType>
    <WholeProgramOptimization>true</WholeProgramOptimization>
    <CharacterSet>Unicode</CharacterSet>
  </PropertyGroup>
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
  <ImportGroup Label="ExtensionSettings">
  </ImportGroup>
  <ImportGroup Label="PropertySheets" Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">
    <Import Project="$(UserRootDir)\Microsoft.Cpp.$(Platform).user.props" Condition="exists('$(UserRootDir)\Microsoft.Cpp.$(Platform).user.props')" Label="LocalAppDataPlatform" />
  </ImportGroup>
  <ImportGroup Label="PropertySheets" Condition="'$(Configuration)|$(Platform)'=='Release|Win32'">
    <Import Project="$(UserRootDir)\Microsoft.Cpp.$(Platform).user.props" Condition="exists('$(UserRootDir)\Microsoft.Cpp.$(Platform).user.props')" Label="LocalAppDataPlatform" />
  </ImportGroup>
  <PropertyGroup Label="UserMacros" />
  <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">
    <LinkIncremental>true</LinkIncremental>
  </PropertyGroup>
  <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|Win32'">
    <LinkIncremental>false</LinkIncremental>
  </PropertyGroup>
  <ItemDefinitionGroup Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">
    <ClCompile>
      <PrecompiledHeader>Use</PrecompiledHeader>
      <WarningLevel>Level3</WarningLevel>
      <MinimalRebuild>true</MinimalRebuild>
      <DebugInformationFormat>EditAndContinue</DebugInformationFormat>
      <Optimization>Disabled</Optimization>
      <BasicRuntimeChecks>EnableFastChecks</BasicRuntimeChecks>
      <RuntimeLibrary>MultiThreadedDebugDLL</RuntimeLibrary>
      <PreprocessorDefinitions>WIN32;_DEBUG;_CONSOLE;%(PreprocessorDefinitions)</PreprocessorDefinitions>
    </ClCompile>
    <Link>
      <SubSystem>Console</SubSystem>
      <GenerateDebugInformation>true</GenerateDebugInformation>
    </Link>
  </ItemDefinitionGroup>
  <ItemDefinitionGroup Condition="'$(Configuration)|$(Platform)'=='Release|Win32'">
    <ClCompile>
      <WarningLevel>Level3</WarningLevel>
      <PrecompiledHeader>Use</PrecompiledHeader>
      <DebugInformationFormat>ProgramDatabase</DebugInformationFormat>
      <Optimization>MaxSpeed</Optimization>
      <RuntimeLibrary>MultiThreadedDLL</RuntimeLibrary>
      <FunctionLevelLinking>true</FunctionLevelLinking>
      <IntrinsicFunctions>true</IntrinsicFunctions>
      <PreprocessorDefinitions>WIN32;NDEBUG;_CONSOLE;%(PreprocessorDefinitions)</PreprocessorDefinitions>
    </ClCompile>
    <Link>
      <SubSystem>Console</SubSystem>
      <GenerateDebugInformation>true</GenerateDebugInformation>
      <EnableCOMDATFolding>true</EnableCOMDATFolding>
      <OptimizeReferences>true</OptimizeReferences>
    </Link>
  </ItemDefinitionGroup>
  <ItemGroup>
    <None Include="ReadMe.txt" />
  </ItemGroup>
  <ItemGroup>
    <ClInclude Include="stdafx.h" />
    <ClInclude Include="targetver.h" />
  </ItemGroup>
  <ItemGroup>
    <ClCompile Include="SomeProjName.cpp" />
    <ClCompile Include="stdafx.cpp">
      <PrecompiledHeader Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">Create</PrecompiledHeader>
      <PrecompiledHeader Condition="'$(Configuration)|$(Platform)'=='Release|Win32'">Create</PrecompiledHeader>
    </ClCompile>
  </ItemGroup>
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.targets" />
  <ImportGroup Label="ExtensionTargets">
  </ImportGroup>
</Project>
```

## <a name="see-also"></a>참고자료

[C++-Visual Studio 프로젝트](../creating-and-managing-visual-cpp-projects.md)<br>
[Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)
