---
title: '방법: MSBuild 프로젝트에서 빌드 이벤트 사용'
ms.date: 11/04/2016
helpviewer_keywords:
- 'msbuild (c++), howto: use build events in projects'
ms.assetid: 2a58dc9d-3d50-4e49-97c1-86c5a05ce218
ms.openlocfilehash: 3fe205223b6cf381bbf3e2872b1a84f9d81a3cb7
ms.sourcegitcommit: 2da5c42928739ca8cd683a9002598f28d8ec5f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2019
ms.locfileid: "70060063"
---
# <a name="how-to-use-build-events-in-msbuild-projects"></a>방법: MSBuild 프로젝트에서 빌드 이벤트 사용

빌드 이벤트는 MSBuild가 빌드 프로세스의 특정 단계에서 수행 하는 명령입니다. 빌드 *전* 이벤트는 빌드가 시작 되기 전에 발생 합니다. 링크 *전* 이벤트는 링크 단계가 시작 되기 전에 발생 합니다. 빌드 *후* 이벤트는 빌드가 성공적으로 종료 된 후에 발생 합니다. 빌드 이벤트는 연관된 빌드 단계가 수행될 때만 발생합니다. 예를 들어 링크 단계가 실행 되지 않는 경우 링크 전 이벤트가 발생 하지 않습니다.

세 개의 빌드 이벤트는 모두 항목 정의 그룹에서 실행 되는 명령 요소 (`<Command>`) 및 **MSBuild** 가 빌드 이벤트를 수행할 때 표시 되는 메시지 요소 (`<Message>`)로 표시 됩니다. 각 요소는 선택 사항이 며 동일한 요소를 여러 번 지정 하면 마지막 항목이 우선적으로 적용 됩니다.

빌드 이벤트가 실행 되는지 여부를 나타내기 위해 속성`<`그룹에서 선택적 빌드 후 요소 (*빌드 이벤트*`UseInBuild>`)를 지정할 수 있습니다. *빌드에 사용* 되는 요소의 내용 값은 **true** 또는 **false**입니다. 기본적으로 해당 하는 *빌드-빌드* 요소가로 `false`설정 되어 있지 않으면 빌드 이벤트가 실행 됩니다.

다음 표에서는 각 빌드 이벤트 XML 요소를 보여 줍니다.

|XML 요소|설명|
|-----------------|-----------------|
|`PreBuildEvent`|이 이벤트는 빌드가 시작 되기 전에 실행 됩니다.|
|`PreLinkEvent`|이 이벤트는 링크 단계가 시작 되기 전에 실행 됩니다.|
|`PostBuildEvent`|이 이벤트는 빌드가 완료 된 후에 실행 됩니다.|

다음 표에는 각 *빌드* 후 요소가 나열 되어 있습니다.

|XML 요소|설명|
|-----------------|-----------------|
|`PreBuildEventUseInBuild`|*빌드 전* 이벤트를 실행할지 여부를 지정 합니다.|
|`PreLinkEventUseInBuild`|*링크 전* 이벤트를 실행할지 여부를 지정 합니다.|
|`PostBuildEventUseInBuild`|*빌드 후* 이벤트를 실행할지 여부를 지정 합니다.|

## <a name="example"></a>예제

다음 예제는 연습에서 [만든 myproject 파일의 Project 요소 내에 추가할 수 있습니다. MSBuild를 사용 하 여 C++ 프로젝트](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)만들기 *빌드 전* 이벤트는 기본 .cpp의 복사본을 만듭니다. *링크 전* 이벤트는 주 .obj의 복사본을 만듭니다. *빌드 후* 이벤트는 myproject의 복사본을 만듭니다. 릴리스 구성을 사용 하 여 프로젝트를 빌드하면 빌드 이벤트가 실행 됩니다. 디버그 구성을 사용 하 여 프로젝트를 빌드하면 빌드 이벤트가 실행 되지 않습니다.

``` xml
<ItemDefinitionGroup>
  <PreBuildEvent>
    <Command>copy $(ProjectDir)main.cpp $(ProjectDir)copyOfMain.cpp</Command>
    <Message>Making a copy of main.cpp </Message>
  </PreBuildEvent>
  <PreLinkEvent>
    <Command>copy $(ProjectDir)$(Configuration)\main.obj $(ProjectDir)$(Configuration)\copyOfMain.obj</Command>
    <Message>Making a copy of main.obj</Message>
  </PreLinkEvent>
  <PostBuildEvent>
    <Command>copy $(ProjectDir)$(Configuration)\$(TargetFileName) $(ProjectDir)$(Configuration)\copyOfMyproject.exe</Command>
    <Message>Making a copy of myproject.exe</Message>
  </PostBuildEvent>
</ItemDefinitionGroup>

<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|Win32'">
  <PreBuildEventUseInBuild>true</PreBuildEventUseInBuild>
  <PreLinkEventUseInBuild>true</PreLinkEventUseInBuild>
  <PostBuildEventUseInBuild>true</PostBuildEventUseInBuild>
</PropertyGroup>

<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">
  <PreBuildEventUseInBuild>false</PreBuildEventUseInBuild>
  <PreLinkEventUseInBuild>false</PreLinkEventUseInBuild>
  <PostBuildEventUseInBuild>false</PostBuildEventUseInBuild>
</PropertyGroup>
```

## <a name="see-also"></a>참고자료

[명령줄에서 MSBuild 사용 - C++](msbuild-visual-cpp.md)<br/>
[연습: MSBuild를 사용하여 C++ 프로젝트 만들기](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)
