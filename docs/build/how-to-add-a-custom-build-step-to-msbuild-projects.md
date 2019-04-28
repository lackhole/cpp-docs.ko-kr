---
title: '방법: MSBuild 프로젝트에 사용자 지정 빌드 단계 추가'
ms.date: 11/04/2016
f1_keywords:
- msbuild.cpp.howto.addcustombuildstep
helpviewer_keywords:
- 'msbuild (c++), howto: add a custom build step'
ms.assetid: a20a0c47-4df4-4754-a1f0-a94a99958916
ms.openlocfilehash: 4c64c6875d82000d6a0ac880b103b5e220015cb3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188927"
---
# <a name="how-to-add-a-custom-build-step-to-msbuild-projects"></a>방법: MSBuild 프로젝트에 사용자 지정 빌드 단계 추가

사용자 지정 빌드 단계는 빌드를 사용자 정의 단계입니다. 사용자 지정 빌드 단계는 다른 처럼 *명령 도구* 표준 컴파일 또는 링크 도구 단계와 같은 단계입니다.

프로젝트 파일 (.vcxproj)에서 사용자 지정 빌드 단계를 지정 합니다. 단계 추가 입력 또는 출력 파일 및 메시지 표시를 실행 하려면 명령줄을 지정할 수 있습니다. 하는 경우 **MSBuild** 결정 파일에 입력된 파일과 관련 된 오래 된 출력 파일에 메시지를 표시 하 고 명령을 실행 합니다.

빌드 대상 시퀀스에서 위치의 사용자 지정 빌드 단계를 지정 하려면 중 하나 또는 모두를 사용 합니다 `CustomBuildAfterTargets` 및 `CustomBuildBeforeTargets` 프로젝트 파일에서 XML 요소입니다. 예를 들어, 사용자 지정 빌드 단계 링크 도구 대상 후 매니페스트 도구, 대상 보다 먼저 실행 되도록 지정할 수 있습니다. 실제 사용 가능한 대상 집합이 특정 빌드에 따라 달라 집니다.

지정 된 `CustomBuildBeforeTargets` 특정 대상이 실행 되기 전에 사용자 지정 빌드 단계를 실행 하는 요소는 `CustomBuildAfterTargets` 특정 대상이 실행 된 후의 단계를 실행 하는 요소 또는 인접 한 두 대상 간에 단계를 실행 하려면 두 요소입니다. 사용자 지정 빌드 도구 실행 후에 기본 위치를 모두 요소를 지정 합니다 **링크** 대상입니다.

사용자 지정 빌드 단계 및 사용자 지정 빌드 도구에 지정 된 정보를 공유 합니다 `CustomBuildBeforeTargets` 고 `CustomBuildAfterTargets` XML 요소입니다. 따라서 프로젝트 파일의 해당 대상만 한 번만 지정 합니다.

### <a name="to-define-what-is-executed-by-the-custom-build-step"></a>사용자 지정 빌드 단계에서 실행 될 작업을 정의 하려면

1. 프로젝트 파일에 속성 그룹을 추가 합니다. 이 속성 그룹의 다음 예제에서와 같이 명령, 해당 입력 및 출력 및 메시지를 지정 합니다. 이 예제에서 만든 main.cpp 파일에서.cab 파일을 만듭니다 [연습: MSBuild를 사용 하 여 시각적 개체를 만들려면 C++ 프로젝트](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)합니다.

    ```
    <ItemDefinitionGroup>
      <CustomBuildStep>
        <Command>makecab.exe $(ProjectDir)main.cpp $(TargetName).cab</Command>
        <Outputs>$(TargetName).cab</Outputs>
        <Inputs>$(TargetFileName)</Inputs>
      </CustomBuildStep>
    </ItemDefinitionGroup>
    ```

### <a name="to-define-where-in-the-build-the-custom-build-step-will-execute"></a>빌드에 사용자 지정 빌드 단계를 실행할 위치를 정의 하려면

1. 프로젝트 파일에 다음 속성 그룹을 추가 합니다. 두 대상을 지정할 수 있습니다 또는 특정 대상 전후를 실행 하는 사용자 지정 단계를 하려는 경우 하나를 생략할 수 있습니다. 이 예제에서는 **MSBuild** 컴파일 단계가 끝나고 링크 단계가 시작 되기 전에 사용자 지정 단계를 수행 합니다.

    ```
    <PropertyGroup>
      <CustomBuildAfterTargets>ClCompile</CustomBuildAfterTargets>
      <CustomBuildBeforeTargets>Link</CustomBuildBeforeTargets>
    </PropertyGroup>
    ```

## <a name="see-also"></a>참고자료

[연습: MSBuild를 사용하여 Visual C++ 프로젝트 만들기](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)<br/>
[방법: MSBuild 프로젝트에서 빌드 이벤트 사용](how-to-use-build-events-in-msbuild-projects.md)<br/>
[방법: MSBuild 프로젝트에 사용자 지정 빌드 도구 추가](how-to-add-custom-build-tools-to-msbuild-projects.md)
