---
title: .vcxproj 및 .props 파일 구조
ms.date: 09/18/2018
helpviewer_keywords:
- .vcxproj file structure
ms.assetid: 14d0c552-29db-480e-80c1-7ea89d6d8e9c
ms.openlocfilehash: a1052d0a0eeeff177f0a22883fe06cd07d7b03f6
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65446496"
---
# <a name="vcxproj-and-props-file-structure"></a>.vcxproj 및 .props 파일 구조

[MSBuild](../msbuild-visual-cpp.md)는 Visual Studio의 기본 프로젝트 시스템입니다. Visual C++에서 **파일** > **새 프로젝트**를 차례로 선택하면 `.vcxproj` 확장명의 XML 프로젝트 파일에 설정이 저장되는 MSBuild 프로젝트를 만들 수 있습니다. 프로젝트 파일은 설정을 저장할 수 있는 .props 파일과 .targets 파일을 가져올 수도 있습니다. 대부분의 경우 프로젝트 파일을 수동으로 편집할 필요가 없으며, 실제로 MSBuild를 잘 알고 있지 않으면 수동으로 편집하지 않아야 합니다. 프로젝트 설정을 수정 하려면 Visual Studio 속성 페이지를 사용 해야 가능 (참조 [설정 C++ Visual Studio에서 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다. 그러나 경우에 따라 프로젝트 파일 또는 속성 시트를 수동으로 수정해야 할 수도 있습니다. 이 문서에는 이러한 시나리오의 파일 구조에 대한 기본 정보가 포함되어 있습니다.

**중요:**

.vcxproj 파일을 수동으로 편집하려면 다음 사실을 알고 있어야 합니다.

1. 파일의 구조는 이 문서에서 설명하는 규정된 양식을 따라야 합니다.

1. Visual Studio C++ 현재 프로젝트 시스템 프로젝트 항목에 와일드 카드를 지원 하지 않습니다. 예를 들어 다음 예제는 지원되지 않습니다.

   ```xml
   <ClCompile Include="*.cpp"/>
   ```

1. Visual Studio C++ 현재 프로젝트 시스템에서 프로젝트 항목 경로 매크로 지원 하지 않습니다. 예를 들어 다음 예제는 지원되지 않습니다.

   ```xml
   <ClCompile Include="$(IntDir)\generated.cpp"/>
   ```

   “지원 안 함”은 IDE의 모든 조작에 대해 매크로가 작동하도록 보장되지 않음을 의미합니다. 다른 구성에서 값을 변경하지 않는 매크로는 작동해야 하지만 항목을 다른 필터 또는 프로젝트로 이동해도 유지되지 않을 수 있습니다. IDE가 프로젝트 구성마다 다른 프로젝트 항목 경로를 예상하지 않으므로, 다른 구성에 대한 값을 변경하는 매크로로 인해 문제가 발생합니다.

1. **프로젝트 속성** 대화 상자에서 편집할 때 프로젝트 속성이 올바르게 추가, 제거 또는 수정되도록 하려면, 파일에 각 프로젝트 구성에 대한 별도의 그룹이 있어야 하며 조건이 다음과 같은 형식이어야 합니다.

   ```xml
   Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'"
   ```

1. 각 속성은 속성 규칙 파일에 지정된 대로 올바른 레이블이 있는 그룹에 지정되어야 합니다. 자세한 내용은 [속성 페이지 xml 규칙 파일](property-page-xml-files.md)을 참조하세요.

## <a name="vcxproj-file-elements"></a>.vcxproj 파일 요소

텍스트 또는 XML 편집기를 사용하여 .vcxproj 파일의 내용을 검사할 수 있습니다. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고, **프로젝트 언로드**를 선택한 다음, **Foo.vcxproj 편집**을 선택하여 Visual Studio에서 볼 수 있습니다.

가장 먼저 주목해야 할 것은 최상위 요소가 특정 순서로 표시된다는 것입니다. 예를 들어:

- 대부분의 속성 그룹 및 항목 정의 그룹은 Microsoft.Cpp.Default.props를 가져온 후에 표시됩니다.

- 모든 대상은 파일의 끝에서 가져옵니다.

- 각각 고유한 레이블이 있는 여러 속성 그룹이 있으며 특정 순서로 표시됩니다.

MSBuild는 순차적 평가 모델을 기반으로 하므로 프로젝트 파일에 있는 요소의 순서는 매우 중요합니다.  가져온 .props 및 .targets 파일을 모두 포함한 프로젝트 파일이 속성의 여러 정의로 구성되어 있으면 마지막 정의가 앞의 정의를 재정의합니다. 다음 예제에서는 "xyz" 값이 MSBUild 엔진에서 평가 중에 마지막으로 발생하기 때문에 컴파일하는 동안 설정됩니다.

```xml
  <MyProperty>abc</MyProperty>
  <MyProperty>xyz</MyProperty>
```

다음 코드 조각에서는 최소한의 .vcxproj 파일을 보여 줍니다. Visual Studio에서 생성된 모든 .vcxproj 파일에는 이러한 최상위 MSBuild 요소가 포함되며, 최상위 요소 각각의 여러 복사본이 포함될 수 있지만 여기에 적용된 순서 대로 표시됩니다. `Label` 특성은 편집을 위한 표지판으로 Visual Studio에서만 사용하는 임의의 태그이며 다른 기능이 없습니다.

```xml
<Project DefaultTargets="Build" ToolsVersion="4.0" xmlns='http://schemas.microsoft.com/developer/msbuild/2003'>
  <ItemGroup Label="ProjectConfigurations" />
  <PropertyGroup Label="Globals" />
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />
  <PropertyGroup Label="Configuration" />
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
  <ImportGroup Label="ExtensionSettings" />
  <ImportGroup Label="PropertySheets" />
  <PropertyGroup Label="UserMacros" />
  <PropertyGroup />
  <ItemDefinitionGroup />
  <ItemGroup />
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.targets" />
  <ImportGroup Label="ExtensionTargets" />
</Project>
```

다음 섹션에서는 이러한 각 요소의 용도와 해당 순서로 지정된 이유에 대해 설명합니다.

### <a name="project-element"></a>프로젝트 요소

```xml
<Project DefaultTargets="Build" ToolsVersion="4.0" xmlns='http://schemas.microsoft.com/developer/msbuild/2003' >
```

`Project`는 루트 노드입니다. 프로젝트 파일을 MSBuild.exe로 전달할 때 사용할 MSBuild 버전과 실행할 기본 대상을 지정합니다.

### <a name="projectconfigurations-itemgroup-element"></a>ProjectConfigurations ItemGroup 요소

```xml
<ItemGroup Label="ProjectConfigurations" />
```

`ProjectConfigurations`에는 프로젝트 구성 설명이 포함됩니다. 예를 들어 디버그|Win32, 릴리스|Win32, 디버그|ARM 등등입니다. 많은 프로젝트 설정은 지정된 구성에 따라 다릅니다. 예를 들어 릴리스 빌드에는 디버그 빌드가 아니라 최적화 속성을 설정하는 것이 좋습니다.

`ProjectConfigurations` 항목 그룹은 빌드 시간에 사용되지 않습니다. 이 항목 그룹은 Visual Studio IDE에서 프로젝트를 로드하는 데 필요하며, .props 파일로 이동하고 .vcxproj 파일로 가져올 수 있습니다. 그러나 이 경우 구성을 추가하거나 제거할 필요가 있으면 .props 파일을 수동으로 편집해야 하며, IDE는 사용할 수 없습니다.

### <a name="projectconfiguration-elements"></a>ProjectConfiguration 요소

다음 코드 조각에서는 프로젝트 구성을 보여 줍니다. 이 예제에서 'Debug|x64'는 구성 이름입니다. 프로젝트 구성 이름은 $(구성)|$(플랫폼) 형식이어야 합니다. 프로젝트 구성 노드를 두 개의 속성이 있을 수 있습니다. 구성 및 플랫폼입니다. 구성이 활성화되면 이러한 속성이 자동으로 여기에 지정된 값으로 설정됩니다.

```xml
<ProjectConfiguration Include="Debug|x64">
  <Configuration>Debug</Configuration>
  <Platform>x64</Platform>
</ProjectConfiguration>
```

IDE는 모든 ProjectConfiguration 항목에 사용된 구성 및 플랫폼 값의 조합에 대한 프로젝트 구성을 찾는 데 필요합니다. 이는 종종 프로젝트에서 이 요구 사항을 충족하기 위해 의미 없는 프로젝트 구성이 있을 수 있음을 의미합니다. 예를 들어 프로젝트에 다음 구성이 있는 경우가 있습니다.

- 디버그|Win32

- 소매|Win32

- 특별한 32비트 최적화|Win32

그렇다면 "특별한 32비트 최적화"가 x64에는 의미가 없더라도 다음과 같은 구성이 있어야 합니다.

- Debug|x64

- 소매|x64

- 특별한 32비트 최적화|x64

**솔루션 구성 관리자**에서 모든 구성에 대한 빌드 및 배포 명령을 사용하지 않도록 설정할 수 있습니다.

### <a name="globals-propertygroup-element"></a>Globals PropertyGroup 요소

```xml
<PropertyGroup Label="Globals" />
```

`Globals`에는 ProjectGuid, RootNamespace 및 ApplicationType/ ApplicationTypeRevision과 같은 프로젝트 수준 설정이 포함됩니다. 마지막 두 설정에서 대상 OS를 정의하는 경우가 있습니다. 현재 참조 및 프로젝트 항목에는 조건이 없으므로 프로젝트에서 단일 OS만을 대상으로 할 수 있습니다. 이러한 속성은 일반적으로 프로젝트 파일의 다른 위치에서 재정의되지 않습니다. 이 그룹은 구성에 종속되지 않으므로 일반적으로 프로젝트 파일에는 하나의 Globals 그룹만 있습니다.

### <a name="microsoftcppdefaultprops-import-element"></a>Microsoft.Cpp.default.props Import 요소

```xml
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />
```

**Microsoft.Cpp.default.props** 속성 시트는 Visual Studio와 함께 제공되며 수정할 수 없습니다. 여기에는 프로젝트에 대한 기본 설정이 포함됩니다. 기본값은 ApplicationType에 따라 달라질 수 있습니다.

### <a name="configuration-propertygroup-elements"></a>Configuration PropertyGroup 요소

```xml
<PropertyGroup Label="Configuration" />
```

`Configuration` 속성 그룹에는 연결된 구성 조건(예: `Condition=”'$(Configuration)|$(Platform)'=='Debug|Win32'”`)이 있으며 구성별로 하나씩 여러 복사본이 제공됩니다. 이 속성 그룹은 특정 구성에 대해 설정된 속성을 호스팅합니다. Configuration 속성에는 PlatformToolset이 포함되며, **Microsoft.Cpp.props**의 시스템 속성 시트 포함 여부를 제어합니다. 예를 들어 `<CharacterSet>Unicode</CharacterSet>` 속성을 정의하면 **microsoft.Cpp.unicodesupport.props** 시스템 속성 시트가 포함됩니다. **Microsoft.Cpp.props**를 검사하면 `<Import Condition=”'$(CharacterSet)' == 'Unicode'”   Project=”$(VCTargetsPath)\microsoft.Cpp.unicodesupport.props”/>` 줄이 표시됩니다.

### <a name="microsoftcppprops-import-element"></a>Microsoft.Cpp.props Import 요소

```xml
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
```

**Microsoft.Cpp.props** 속성 시트(직접 또는 가져오기를 통해)는 컴파일러의 Optimization(최적화) 및 Warning Level(경고 수준) 속성, MIDL 도구의 TypeLibraryName 속성 등과 같은 많은 도구 관련 속성에 대한 기본값을 정의합니다. 또한 바로 위의 속성 그룹에 정의된 구성 속성에 따라 다양한 시스템 속성 시트를 가져옵니다.

### <a name="extensionsettings-importgroup-element"></a>ExtensionSettings ImportGroup 요소

```xml
<ImportGroup Label="ExtensionSettings" />
```

`ExtensionSettings` 그룹에는 빌드 사용자 지정에 속한 속성 시트에 대한 가져오기가 포함됩니다. 빌드 사용자 지정은 대상 파일, .props 파일 및 .xml 파일의 세 가지 파일로 정의됩니다. 이 가져오기 그룹에는 .props 파일에 대한 가져오기가 포함되어 있습니다.

### <a name="propertysheets-importgroup-elements"></a>PropertySheets ImportGroup 요소

```xml
<ImportGroup Label="PropertySheets" />
```

`PropertySheets` 그룹에는 사용자 속성 시트에 대한 가져오기가 포함됩니다. 이러한 시트는 Visual Studio의 속성 관리자 뷰를 통해 추가하는 속성 시트입니다. 이러한 가져오기가 나열되는 순서는 중요하며 속성 관리자에 반영됩니다. 프로젝트 파일에는 일반적으로 각 프로젝트 구성마다 하나씩 이러한 종류의 가져오기 그룹에 대한 여러 인스턴스가 포함됩니다.

### <a name="usermacros-propertygroup-element"></a>UserMacros PropertyGroup 요소

```xml
<PropertyGroup Label="UserMacros" />
```

`UserMacros`에는 빌드 프로세스를 사용자 지정하는 데 사용되는 변수로 만든 속성이 포함됩니다. 예를 들어 사용자 지정 출력 경로를 $(CustomOutputPath)로 정의하는 사용자 매크로를 정의하고, 이를 사용하여 다른 변수를 정의할 수 있습니다. 이 속성 그룹에는 이러한 속성이 보관됩니다. Visual C++에서 구성에 대한 사용자 매크로를 지원하지 않기 때문에 Visual Studio에서는 이 그룹이 프로젝트 파일에 채워지지 않습니다. 사용자 매크로는 속성 시트에서 지원됩니다.

### <a name="per-configuration-propertygroup-elements"></a>구성별 PropertyGroup 요소

```xml
<PropertyGroup />
```

이 속성 그룹에는 모든 프로젝트 구성에 대해 구성별로 하나씩 여러 개의 인스턴스가 있습니다. 각 속성 그룹은 하나의 구성 조건에 연결되어야 합니다. 누락된 구성이 있으면 **프로젝트 속성** 대화 상자가 올바르게 작동하지 않습니다. 위의 속성 그룹과는 달리 이 속성 그룹에는 레이블이 없습니다. 이 그룹에는 프로젝트 구성 수준 설정이 포함됩니다. 이러한 설정은 지정된 항목 그룹에 속한 모든 파일에 적용됩니다. 빌드 사용자 지정 항목 정의 메타데이터는 여기서 초기화됩니다.

이 PropertyGroup은 `<Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />` 뒤에 나와야 하며, 앞에는 레이블이 없는 다른 PropertyGroup이 없어야 합니다. 그렇지 않으면 프로젝트 속성 편집이 올바르게 작동하지 않습니다.

### <a name="per-configuration-itemdefinitiongroup-elements"></a>구성별 ItemDefinitionGroup 요소

```xml
<ItemDefinitionGroup />
```

항목 정의가 포함됩니다. 이러한 요소는 레이블이 없는 구성별 PropertyGroup 요소와 동일한 조건 규칙을 따라야 합니다.

### <a name="itemgroup-elements"></a>ItemGroup 요소

```xml
<ItemGroup />
```

프로젝트의 항목(소스 파일 등)이 포함됩니다. 조건은 프로젝트 항목(즉, 규칙 정의에서 프로젝트 항목으로 처리되는 항목 형식)에 지원되지 않습니다.

메타데이터에는 모두 동일하더라도 각 구성에 대한 구성 조건이 있어야 합니다. 예를 들어:

```xml
<ItemGroup>
  <ClCompile Include="stdafx.cpp">
    <TreatWarningAsError Condition="‘$(Configuration)|$(Platform)’==’Debug|Win32’">true</TreatWarningAsError>
    <TreatWarningAsError Condition="‘$(Configuration)|$(Platform)’==’Debug|x64’">true</TreatWarningAsError>
  </ClCompile>
</ItemGroup>
```

Visual Studio C++ 현재 프로젝트 시스템 프로젝트 항목에 와일드 카드를 지원 하지 않습니다.

```xml
<ItemGroup>
  <ClCompile Include="*.cpp"> <!--Error-->
</ItemGroup>
```

Visual Studio C++ 현재 프로젝트 시스템에서 프로젝트 항목 매크로 지원 하지 않습니다.

```xml
<ItemGroup>
  <ClCompile Include="$(IntDir)\generated.cpp"> <!--not guaranteed to work in all scenarios-->
</ItemGroup>
```

참조는 ItemGroup에 지정되며, 제한 사항은 다음과 같습니다.

- 참조는 조건을 지원하지 않습니다.

- 참조 메타데이터는 조건을 지원하지 않습니다.

### <a name="microsoftcpptargets-import-element"></a>Microsoft.Cpp.targets Import 요소

```xml
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.targets" />
```

빌드, 정리 등과 같은 Visual C++ 대상을 직접 또는 가져오기를 통해 정의합니다.

### <a name="extensiontargets-importgroup-element"></a>ExtensionTargets ImportGroup 요소

```xml
<ImportGroup Label="ExtensionTargets" />
```

이 그룹에는 빌드 사용자 지정 대상 파일에 대한 가져오기가 포함됩니다.

## <a name="impact-of-incorrect-ordering"></a>잘못된 순서 지정의 영향

Visual Studio IDE는 위에서 설명한 순서가 있는 프로젝트 파일에 따라 달라집니다. 예를 들어 속성 페이지에서 속성 값을 정의하면 IDE는 일반적으로 빈 레이블이 있는 속성 그룹에 속성 정의를 배치합니다. 이렇게 하면 시스템 속성 시트에서 가져온 기본값이 사용자 정의 값으로 재정의됩니다. 마찬가지로, 대상 파일은 위에서 정의한 속성을 사용하고 일반적으로 속성 자체를 정의하지 않으므로 끝에 가져옵니다. 마찬가지로, 사용자 속성 시트도 **Microsoft.Cpp.props**를 통해 포함된 시스템 속성 시트 뒤에 가져옵니다. 이렇게 하면 사용자가 시스템 속성 시트에서 가져온 모든 기본값을 재정의할 수 있습니다.

.vcxproj 파일이 이 레이아웃을 따르지 않으면 빌드 결과가 예상과 다를 수 있습니다. 예를 들어 시스템 속성 시트를 실수로 사용자가 정의한 속성 시트 뒤에 가져오면 사용자 설정이 시스템 속성 시트로 재정의됩니다.

또한 IDE 디자인 타임 환경도 요소의 올바른 순서에 따라 어느 정도 달라집니다. 예를 들어 .vcxproj 파일에 `PropertySheets` 가져오기 그룹이 없으면 IDE에서 사용자가 **속성 관리자**에서 만든 새 속성 시트를 배치할 위치를 결정하지 못할 수 있습니다. 이로 인해 사용자 시트가 시스템 시트로 재정의될 수 있습니다. IDE에서 사용하는 추론은 .vcxproj 파일 레이아웃의 사소한 불일치를 허용할 수 있지만 이 문서 앞부분에 나와 있는 구조를 벗어나지 않는 것이 좋습니다.

## <a name="how-the-ide-uses-element-labels"></a>IDE에서 요소 레이블을 사용하는 방법

IDE의 일반 속성 페이지에서 **UseOfAtl** 속성을 설정하면, 프로젝트 파일의 Configuration 속성 그룹에 작성되고 동일한 속성 페이지에서 **TargetName** 속성이 레이블이 없는 구성별 속성 그룹에 작성됩니다. Visual Studio에서는 속성 페이지의 xml 파일에서 각 속성을 작성할 위치에 대한 정보를 찾습니다. **일반** 속성 페이지(영문 버전의 Visual Studio Enterprise Edition이 있다고 가정)의 경우 해당 파일은 `%ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets\1033\general.xml`입니다. 속성 페이지 XML 규칙 파일은 규칙 및 관련된 모든 속성에 대한 정적 정보를 정의합니다. 이러한 정보 중 하나는 대상 파일(해당 값이 작성된 파일)의 Rule 속성에 대한 기본 설정 위치입니다. 기본 설정 위치는 프로젝트 파일 요소의 Label 특성으로 지정됩니다.

## <a name="property-sheet-layout"></a>속성 시트 레이아웃

다음 XML 코드 조각은 최소한의 속성 시트(.props) 파일 레이아웃입니다. .vcxproj 파일과 비슷하며, .props 요소의 기능은 앞서의 토론에서 유추할 수 있습니다.

```xml
<Project ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <ImportGroup Label="PropertySheets" />
  <PropertyGroup Label="UserMacros" />
  <PropertyGroup />
  <ItemDefinitionGroup />
  <ItemGroup />
</Project>
```

사용자 고유의 속성 시트를 만들려면 VCTargets 폴더에 있는 .props 파일 중 하나를 복사하여 용도에 맞게 수정합니다. Visual Studio 2017 Enterprise 버전의 경우 기본 VCTargets 경로는 `%ProgramFiles%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets`입니다.

## <a name="see-also"></a>참고자료

[Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)<br/>
[속성 페이지 XML 파일](property-page-xml-files.md)
