---
title: 속성 페이지 XML 규칙 파일
ms.date: 04/27/2017
helpviewer_keywords:
- property page XML files
ms.assetid: dd9d9734-4387-4098-8ba6-85b93507731d
ms.openlocfilehash: 17b89f00b2e51c960ed7d3219427b56d92851b81
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319478"
---
# <a name="property-page-xml-rule-files"></a>속성 페이지 XML 규칙 파일

IDE의 프로젝트 속성 페이지는 VCTargets 폴더의 XML 파일로 구성됩니다. 정확한 경로는 설치된 Visual Studio 버전 및 제품 언어에 따라 달라집니다. Visual Studio 2017 Enterprise Edition의 영어 버전 경로는 `%ProgramFiles%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets\1033`입니다. XML 파일은 규칙, 범주 및 개별 속성, 데이터 형식, 기본값의 이름 및 표시 방법을 설명합니다. IDE에서 속성을 설정하면 새 값이 프로젝트 파일에 저장됩니다.

이러한 파일과 Visual Studio IDE의 내부 작동 원리를 이해해야 하는 유일한 시나리오는 (a) 사용자 지정 속성 페이지를 만들거나, (b) Visual Studio IDE 이외의 다른 방법으로 프로젝트 속성을 사용자 지정하려고 하는 경우입니다.

먼저 프로젝트의 속성 페이지를 엽니다(**솔루션 탐색기**에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 속성 선택).

![Visual C++ 프로젝트 속성](../media/cpp-property-page-2017.png)

**구성 속성** 아래의 각 노드를 규칙이라고 합니다. 규칙은 때때로 컴파일러와 같은 단일 도구를 나타내는 경우도 있지만, 일반적으로 이 용어는 속성을 가지고 실행되며 출력을 생성할 수 있는 것을 나타냅니다. 각 규칙은 VCTargets 폴더의 xml 파일에서 채워집니다. 예를 들어 위에 표시된 C/C++ 규칙은 'cl.xml'로 채워집니다.

위에 표시된 것처럼, 각 규칙에는 범주로 구성된 속성 집합이 있습니다. 규칙 아래의 각 하위 노드는 범주를 나타냅니다. 예를 들어 C/C++ 아래의 최적화 노드에는 컴파일러 도구의 모든 최적화 관련 속성이 포함되어 있습니다. 속성 및 해당 값 자체는 오른쪽 창에 그리드 형식으로 렌더링됩니다.

메모장이나 XML 편집기에서 cl.xml을 열 수 있습니다(아래 스냅숏 참조). 추가 메타 데이터와 함께 UI에 표시되는 것과 동일한 속성 목록이 아래에 정의된 규칙이라는 루트 노드가 표시됩니다.

```xml
<?xml version="1.0" encoding="utf-8"?>
<!--Copyright, Microsoft Corporation, All rights reserved.-->
<Rule Name="CL" PageTemplate="tool" DisplayName="C/C++" SwitchPrefix="/" Order="10" xmlns="http://schemas.microsoft.com/build/2009/properties" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml" xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <Rule.Categories>
    <Category Name="General" DisplayName="General" />
    <Category Name="Optimization" DisplayName="Optimization" />
    <Category Name="Preprocessor" DisplayName="Preprocessor" />
    <Category Name="Code Generation" DisplayName="Code Generation" />
    <Category Name="Language" DisplayName="Language" />
    <Category Name="Precompiled Headers" DisplayName="Precompiled Headers" />
    <Category Name="Output Files" DisplayName="Output Files" />
    <Category Name="Browse Information" DisplayName="Browse Information" />
    <Category Name="Advanced" DisplayName="Advanced" />
    <Category Name="All Options" DisplayName="All Options" Subtype="Search" />
    <Category Name="Command Line" DisplayName="Command Line" Subtype="CommandLine" />
  </Rule.Categories>
...
```

속성 페이지 UI의 구성 속성 아래에는 모든 노드에 해당하는 XML 파일이 하나 있습니다. 프로젝트에서 해당 XML 파일에 대한 위치를 포함하거나 제거하여 UI에서 규칙을 추가하거나 제거할 수 있습니다. 예를 들어 다음은 Microsoft.CppBuild.targets(1033 폴더에서 한 단계 위로)에 cl.xml이 포함된 방법입니다.

```xml
<PropertyPageSchema Condition="'$(ConfigurationType)' != 'Utility'" Include="$(VCTargetsPath)$(LangID)\cl.xml"/>
```

Cl.xml의 모든 데이터를 제거하면 다음과 같은 구조로 끝납니다.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Rule>
  <Rule.DataSource />
  <Rule.Categories>
    <Category />
        ...
  </Rule.Categories>
  <BoolProperty />
  <EnumProperty />
  <IntProperty />
  <StringProperty />
  <StringListProperty />
</Rule>
```

다음 섹션에서는 각 주요 요소와 여기에 첨부할 수 있는 일부 메타데이터를 설명합니다.

1. **규칙:**  규칙은 일반적으로 xml 파일의 루트 노드 이 특성을 포함할 수 있습니다.

    ```xml
    <Rule Name="CL" PageTemplate="tool" SwitchPrefix="/" Order="10"
              xmlns="http://schemas.microsoft.com/build/2009/properties"
              xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
              xmlns:sys="clr-namespace:System;assembly=mscorlib">
      <Rule.DisplayName>
        <sys:String>C/C++</sys:String>
      </Rule.DisplayName>
    ```

   a. **이름:** Name 특성에는 규칙의 id입니다. 프로젝트의 모든 속성 페이지 xml 파일 중에서 고유해야 합니다.

   b. **PageTemplate:** 이 특성의 값은 UI 템플릿의 컬렉션을 선택할 UI를 통해 사용 됩니다. "tool" 템플릿은 속성을 표준 표 형식으로 렌더링합니다. 이 특성에 대한 다른 기본 제공 값은 "debugger" 및 "generic"입니다. 이러한 값을 지정하여 생성된 UI 형식을 보려면 각각 Debugging 노드 및 General 노드를 참조하세요. "debugger" 페이지 템플릿의 UI는 드롭다운 상자를 사용하여 여러 디버거 간의 속성을 전환하지만, "generic" 템플릿은 Rule 노드 아래에 여러 범주 하위 노드가 있는 것과 달리 여러 속성 범주를 모두 한 페이지에 표시합니다. 이 특성은 UI에 대한 제안일 뿐이며, xml 파일은 UI와 독립적으로 설계되었습니다. 다른 UI는 이 특성을 다른 용도로 사용할 수 있습니다.

   c. **SwitchPrefix:** 이것이 스위치에 대 한 명령줄에서 사용 된 접두사입니다. "/" 값은 /ZI, /nologo, /W3 등과 같은 스위치를 생성합니다.

   d. **배포 순서:** 이 시스템의 다른 모든 규칙에 비해이 규칙의 상대적 위치에 예상 UI 클라이언트에 있습니다.

   e. **xmlns:** 표준 XAML 요소입니다. 나열된 세 개의 네임스페이스를 볼 수 있습니다. 이들은 각각 XAML 역직렬화 클래스, XAML 스키마 및 시스템 네임스페이스에 해당됩니다.

   f. **DisplayName:** 규칙 노드 속성 페이지 UI에 표시 되는 이름입니다. 이 값은 지역화됩니다. DisplayName은 내부 지역화 도구 요구 사항 때문에 Name 또는 SwitchPrefix와 같은 특성이 아닌 Rule의 하위 요소로 생성되었습니다. XAML의 관점에서 보면 둘 다 동일합니다. 따라서 특성을 간단하게 표시하거나 그대로 둘 수 있습니다.

   g. **DataSource:** 프로젝트 시스템에서 읽고 쓸 속성 값을 해야 하는 위치 및 해당 그룹화 (아래 설명)이를 알려주는 매우 중요 한 속성입니다. Cl.xml의 경우 이러한 값은 다음과 같습니다.

      ```xml
      <DataSource Persistence="ProjectFile" ItemType="ClCompile" Label="" HasConfigurationCondition="true" />
      ```

   - `Persistence="ProjectFile`은 프로젝트 시스템에 Rule의 모든 속성을 프로젝트 파일 또는 속성 시트 파일에 기록해야 한다고 알립니다(속성 페이지를 생성하는 데 사용된 노드에 따라 다름). 다른 가능한 값은 "UserFile"이며, 이 값은 .user 파일에 기록됩니다.

   - `ItemType="ClCompile"`은 이 항목 형식의 ItemDefinition 메타데이터 또는 항목 메타데이터 (후자는 속성 페이지가 솔루션 탐색기의 파일 노드에서 생성된 경우에만 해당)로 저장된다는 것을 나타냅니다. 이 필드가 설정되어 있지 않으면 속성은 PropertyGroup의 공통 속성으로 기록됩니다.

   - `Label=""`은 속성이 `ItemDefinition` 메타데이터로 작성될 때 부모 ItemDefinitionGroup의 레이블이 비어 있음을 나타냅니다(모든 MSBuild 요소에 레이블이 있을 수 있음). Visual Studio 2017에서는 레이블이 지정된 그룹을 사용하여 .vcxproj 프로젝트 파일을 탐색합니다. 대부분의 Rule 속성을 포함하는 그룹에는 빈 문자열이 레이블로 지정되어 있습니다.

   - `HasConfigurationCondition="true"`는 현재 프로젝트 구성에만 적용되도록(조건이 부모 그룹 또는 값 자체에 연결될 수 있도록) 프로젝트 시스템에 구성 조건을 값에 첨부하도록 지시합니다. 예를 들어, 프로젝트 노드에서 속성 페이지를 열고 **구성 속성 > C/C++ 일반**에서 **경고를 오류로 처리** 속성 값을 "예"로 설정합니다. 다음 값이 프로젝트 파일에 기록됩니다. 부모 ItemDefinitionGroup에 연결된 구성 조건을 확인합니다.

      ```xml
      <ItemDefinitionGroup Condition="‘$(Configuration)|$(Platform)’==’Debug|Win32’">
        <ClCompile>
          <TreatWarningAsError>true</TreatWarningAsError>
        </ClCompile>
      </ItemDefinitionGroup>
      ```

      이 값이 stdafx.cpp와 같은 특정 파일의 속성 페이지에 설정된 경우, 속성 값은 아래와 같이 프로젝트 파일의 stdafx.cpp 항목 아래에 기록됩니다. 구성 조건이 메타데이터에 직접 연결되는 방법을 확인합니다.

      ```xml
      <ItemGroup>
        <ClCompile Include="stdafx.cpp">
          <TreatWarningAsError Condition="‘$(Configuration)|$(Platform)’==’Debug|Win32’">true</TreatWarningAsError>
        </ClCompile>
      </ItemGroup>
      ```

   위에 나열되지 않은 **DataSource**의 다른 특성은 **PersistedName**입니다. 이 특성을 사용하여 프로젝트 파일의 속성을 다른 이름으로 나타낼 수 있습니다. 기본적으로 이 특성은 속성의 **이름**으로 설정됩니다.

   개별 속성은 부모 Rule의 DataSource를 재정의할 수 있습니다. 이 경우 해당 속성 값의 위치는 Rule의 다른 속성과 다릅니다.

   h. 여기에 표시되지 않는 규칙에는 Description, SupportsFileBatching 등의 다른 Rule 특성이 있습니다. Rule 또는 다른 요소에 적용 가능한 특성의 전체 집합은 이러한 형식의 설명서를 탐색하면 얻을 수 있습니다. 또는 `Microsoft.Build.Framework .dll` 어셈블리의 `Microsoft.Build.Framework.XamlTypes` 네임스페이스에 있는 형식의 공용 속성을 살펴볼 수 있습니다.

   i. **DisplayName**, **PageTemplate** 및 **Order**는 UI와 관련 없는 기타 데이터 모델에 있는 UI 관련 속성입니다. 이러한 속성은 속성 페이지를 표시하는 데 사용되는 모든 UI에서 거의 사용됩니다. **DisplayName** 및 **Description**은 xml 파일의 거의 모든 요소에 있는 속성입니다. 그리고 지역화된 유일한 두 가지 속성입니다(이러한 문자열의 지역화는 이후에 설명함).

1. **범주:** 규칙 범주를 여러 개 있을 수 있습니다. xml 파일에 범주가 나열되는 순서는 UI에 동일한 순서로 범주를 표시할 것을 제안합니다. 예를 들어, UI에 표시되는 C/C++ 노드 아래의 범주 순서는 일반, 최적화, 전처리기 등  cl.xml과 동일합니다. 샘플 범주는 다음과 같습니다.

    ```xml
    <Category Name="Optimization">
      <Category.DisplayName>
        <sys:String>Optimization</sys:String>
      </Category.DisplayName>
    </Category>
    ```

   위의 코드 조각은 이전에 설명한 **Name** 및 **DisplayName** 특성을 보여 줍니다. 다시 말하지만, 위에서 사용되지 않은 **Category**가 가질 수 있는 다른 특성이 있습니다. 이러한 정보는 설명서를 읽거나 ildasm.exe를 사용하여 어셈블리를 살펴보면 알 수 있습니다.

1. **속성:** Xml 파일의 핵심 이며이 규칙의 모든 속성의 목록을 포함 합니다. 각 속성은 위의 XAML 구조에 표시된 5가지 가능한 형식 중 하나일 수 있습니다. 물론, 파일에 이러한 형식 중 일부만 있을 수 있습니다. 속성에는 속성을 충분히 설명할 수 있는 여러 특성이 있습니다. 여기서는 **StringProperty**만 설명합니다. 나머지는 매우 비슷합니다.

    ```xml
    <StringProperty Subtype="file" Name="ObjectFileName" Category="Output Files" Switch="Fo">
      <StringProperty.DisplayName>
        <sys:String>Object File Name</sys:String>
      </StringProperty.DisplayName>
      <StringProperty.Description>
        <sys:String>Specifies a name to override the default object file name; can be file or directory name.(/Fo[name])</sys:String>
      </StringProperty.Description>
    </StringProperty>
    ```

   코드 조각에 있는 대부분의 특성은 이전에 설명되었습니다. 새로운 형식은 Subtype, Category 및 Switch입니다.

   a. **Subtype**은 **StringProperty** 및 **StringListProperty**에 대해서만 사용할 수 있는 특성이며, 상황에 맞는 정보를 제공합니다. 예를 들어 "file" 값은 속성이 파일 경로를 나타냄을 의미합니다. 이러한 상황에 맞는 정보는 사용자가 파일을 시각적으로 선택할 수 있도록 하는 속성 편집기로 Windows 탐색기를 제공하여 편집 환경을 향상시키는 데 사용됩니다.

   b. **범주:** 이는이 속성이 속하는 범주를 선언 합니다. UI의 **출력 파일** 범주에서 이 속성을 찾아보세요.

   c. **Switch:** 규칙을 나타내는 도구 – 경우 컴파일러 도구와 같은-여기서 규칙의 대부분의 속성에 전달 됩니다 스위치로 도구 실행 빌드 시. 이 특성의 값은 사용할 스위치 리터럴을 나타냅니다. 위의 속성은 스위치가 **Fo**이어야 함을 지정합니다. 부모 Rule의 **SwitchPrefix** 특성과 결합된 이 속성은 실행 파일에 **/Fo"Debug\"** 로 전달됩니다(속성 페이지 UI에서 C/C++의 명령줄에 표시됨).

   기타 속성 특성은 다음과 같습니다.

   d. **표시:** 어떤 이유로 하지 못하도록 하려는 경우 속성 (여전히 사용할 수 있는 빌드 시간 중) 제외한 속성 페이지에 표시 하려면이 특성을 false로 설정 합니다.

   e. **ReadOnly:** 속성 페이지에서이 속성의이 값의 읽기 전용 보기를 제공 하려는 경우이 특성을 true로 설정 합니다.

   f. **IncludeInCommandLine:** 일부 속성 수 빌드 시 도구에 전달할 필요가 없습니다. 이 특성을 false로 설정하면 전달되지 않습니다.
