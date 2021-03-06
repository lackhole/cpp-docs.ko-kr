﻿---
title: '방법: MSBuild 프로젝트에 사용자 지정 빌드 단계 추가'
ms.date: 10/16/2019
helpviewer_keywords:
- 'msbuild (c++), howto: add a custom build step'
ms.assetid: a20a0c47-4df4-4754-a1f0-a94a99958916
ms.openlocfilehash: 78d40a5b4a02fe9b065bbbdde33afc6180d75381
ms.sourcegitcommit: 9aab425662a66825772f091112986952f341f7c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72444922"
---
# <a name="how-to-add-a-custom-build-step-to-msbuild-projects"></a>방법: MSBuild 프로젝트에 사용자 지정 빌드 단계 추가

사용자 지정 빌드 단계는 빌드의 사용자 정의 단계입니다. 사용자 지정 빌드 단계는 표준 컴파일 또는 링크 도구 단계와 같은 다른 *명령 도구* 단계 처럼 동작 합니다.

프로젝트 파일 (.vcxproj)에서 사용자 지정 빌드 단계를 지정 합니다. 단계에서는 실행할 명령줄, 추가 입력 또는 출력 파일, 표시할 메시지를 지정할 수 있습니다. **MSBuild** 에서 입력 파일과 관련 하 여 출력 파일이 최신 상태가 아닌 것으로 확인 되 면 메시지를 표시 하 고 명령을 실행 합니다.

빌드 대상 시퀀스에서 사용자 지정 빌드 단계의 위치를 지정 하려면 프로젝트 파일의 `CustomBuildAfterTargets` 및 `CustomBuildBeforeTargets` XML 요소 중 하나 또는 둘 모두를 사용 합니다. 예를 들어 사용자 지정 빌드 단계가 링크 도구 대상 이후에 실행 되도록 지정 하 고 매니페스트 도구를 대상으로 지정할 수 있습니다. 사용 가능한 대상의 실제 집합은 특정 빌드에 따라 다릅니다.

특정 대상이 실행 되기 전에 사용자 지정 빌드 단계를 실행 하려면 `CustomBuildBeforeTargets` 요소를 지정 하 고, 특정 대상 실행 후 단계를 실행 하는 `CustomBuildAfterTargets` 요소를 지정 하거나, 두 요소 모두 인접 한 두 대상 간의 단계를 실행 합니다. 두 요소를 모두 지정 하지 않으면 사용자 지정 빌드 도구가 기본 위치인 **링크** 대상 뒤에 실행 됩니다.

사용자 지정 빌드 단계 및 사용자 지정 빌드 도구는 `CustomBuildBeforeTargets` 및 `CustomBuildAfterTargets` XML 요소에 지정 된 정보를 공유 합니다. 따라서 프로젝트 파일에서 해당 대상을 한 번만 지정 합니다.

### <a name="to-define-what-is-executed-by-the-custom-build-step"></a>사용자 지정 빌드 단계에서 실행할 작업을 정의 하려면

1. 프로젝트 파일에 속성 그룹을 추가 합니다. 이 속성 그룹에서 다음 예제와 같이 명령을 지정 하 고, 해당 입력 및 출력을 지정 하 고, 메시지를 지정 합니다. 이 예제에서는 [연습: MSBuild를 사용 하 여 C++ 프로젝트 만들기](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)에서 만든 기본 .cpp 파일을 사용 하 여 .cab 파일을 만듭니다.

    ```
    <ItemDefinitionGroup>
      <CustomBuildStep>
        <Command>makecab.exe $(ProjectDir)main.cpp $(TargetName).cab</Command>
        <Outputs>$(TargetName).cab</Outputs>
        <Inputs>$(ProjectDir)main.cpp</Inputs>
      </CustomBuildStep>
    </ItemDefinitionGroup>
    ```

### <a name="to-define-where-in-the-build-the-custom-build-step-will-execute"></a>빌드에서 사용자 지정 빌드 단계가 실행 되는 위치를 정의 하려면

1. 프로젝트 파일에 다음 속성 그룹을 추가 합니다. 두 대상을 모두 지정 하거나 특정 대상 전후에 사용자 지정 단계를 실행 하려는 경우 하나를 생략할 수 있습니다. 이 예제에서는 컴파일 단계 후 링크 단계 전에 사용자 지정 단계를 수행 하도록 **MSBuild** 에 지시 합니다.

    ```
    <PropertyGroup>
      <CustomBuildAfterTargets>ClCompile</CustomBuildAfterTargets>
      <CustomBuildBeforeTargets>Link</CustomBuildBeforeTargets>
    </PropertyGroup>
    ```

## <a name="see-also"></a>참조

[연습: MSBuild를 사용 하 여 C++ 프로젝트 만들기](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)<br/>
[방법: MSBuild 프로젝트에서 빌드 이벤트 사용](how-to-use-build-events-in-msbuild-projects.md)<br/>
[방법: MSBuild 프로젝트에 사용자 지정 빌드 도구 추가](how-to-add-custom-build-tools-to-msbuild-projects.md)
