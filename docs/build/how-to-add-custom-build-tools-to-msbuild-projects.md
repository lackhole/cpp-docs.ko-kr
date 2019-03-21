---
title: '방법: MSBuild 프로젝트에 사용자 지정 빌드 도구 추가'
ms.date: 11/04/2016
f1_keywords:
- msbuild.cpp.howto.addcustombuildtools
helpviewer_keywords:
- 'msbuild (c++), howto: add custom build tools'
ms.assetid: de03899a-371d-4396-9bf9-34f45a65e909
ms.openlocfilehash: 05f160e650c0dd717d7ce0f29259f866d751fdba
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57815270"
---
# <a name="how-to-add-custom-build-tools-to-msbuild-projects"></a>방법: MSBuild 프로젝트에 사용자 지정 빌드 도구 추가

사용자 지정 빌드 도구는 특정 파일을 사용 하 여 연결 된 사용자 정의 명령줄 도구입니다.

특정 파일을 실행 하려면 프로젝트 파일 (.vcxproj) 명령줄, 모든 추가 입력 또는 출력 파일 및 표시할 메시지를 지정 합니다. 하는 경우 **MSBuild** 출력 파일이 입력된 파일 보다 이전 버전임을 메시지를 표시 하 고 실행 명령줄 도구를 결정 합니다.

사용자 지정 빌드 도구를 실행 하는 경우를 지정 하려면 중 하나 또는 모두를 사용 합니다 `CustomBuildBeforeTargets` 고 `CustomBuildAfterTargets` 프로젝트 파일에서 XML 요소입니다. 예를 들어, 사용자 지정 빌드 도구 실행 MIDL 컴파일러와 C/C++ 컴파일러는 지정할 수 있습니다. 지정 된 `CustomBuildBeforeTargets` 특정 대상을 실행 하기 전에 도구를 실행 하는 요소는 `CustomBuildAfterTargets` 특정 대상; 후 도구를 실행 하는 요소 또는 두 요소 모두 두 대상 실행 간에 도구를 실행 하 합니다. 기본 위치를 앞에 사용자 지정 빌드 도구 실행 하지 않고 지정 된 경우는 **MIDL** 대상입니다.

사용자 지정 빌드 단계 및 사용자 지정 빌드 도구에 지정 된 정보를 공유 합니다 `CustomBuildBeforeTargets` 고 `CustomBuildAfterTargets` XML 요소입니다. 프로젝트 파일에서 해당 대상으로 한 번만 지정 합니다.

### <a name="to-add-a-custom-build-tool"></a>사용자 지정 빌드 도구 추가 하려면

1. 프로젝트 파일에 항목 그룹을 추가 하 고 각 입력된 파일에 대 한 항목을 추가 합니다. 다음과 같이 항목 메타 데이터로 명령, 추가 입력, 출력 및 메시지를 지정 합니다. 이 예제에서는 "faq.txt" 파일을 프로젝트와 동일한 디렉터리에 있다고 가정 합니다.

    ```
    <ItemGroup>
      <CustomBuild Include="faq.txt">
        <Message>Copying readme...</Message>
        <Command>copy %(Identity) $(OutDir)%(Identity)</Command>
        <Outputs>$(OutDir)%(Identity)</Outputs>
      </CustomBuild>
    </ItemGroup>
    ```

### <a name="to-define-where-in-the-build-the-custom-build-tools-will-execute"></a>빌드에 사용자 지정 빌드 도구를 실행할 위치를 정의 하려면

1. 프로젝트 파일에 다음 속성 그룹을 추가 합니다. 하나 이상의 대상을 지정할 수 있지만 빌드 단계가 (전후)를 실행 하려는 경우 다른를 생략할 수 있습니다 특정 대상입니다. 이 예제에서는 컴파일한 후 하지만 연결 하기 전에 사용자 지정 단계를 수행합니다.

    ```
    <PropertyGroup>
      <CustomBuildAfterTargets>ClCompile</CustomBuildAfterTargets>
      <CustomBuildBeforeTargets>Link</CustomBuildBeforeTargets>
    </PropertyGroup>
    ```

## <a name="see-also"></a>참고자료

[연습: MSBuild를 사용하여 Visual C++ 프로젝트 만들기](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)<br/>
[방법: MSBuild 프로젝트에서 빌드 이벤트 사용](how-to-use-build-events-in-msbuild-projects.md)<br/>
[방법: MSBuild 프로젝트에 사용자 지정 빌드 단계 추가](how-to-add-a-custom-build-step-to-msbuild-projects.md)
