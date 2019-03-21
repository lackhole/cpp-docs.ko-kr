---
title: C + +-Visual Studio 프로젝트에서 속성 상속
ms.date: 12/10/2018
helpviewer_keywords:
- Visual C++ projects, property inheritance
ms.openlocfilehash: edd6d3bf82f7a13cf6687abeba3758dcceca5e84
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57827272"
---
# <a name="property-inheritance-in-visual-studio-projects"></a>Visual Studio 프로젝트에서 속성 상속

Visual Studio 프로젝트 시스템은 파일 형식 및 모든 종류의 프로젝트 빌드에 대 한 규칙을 정의 하는 MSBuild를 기반으로 합니다. MSBuild가 여러 구성 및 플랫폼을 빌드하는 데 따르는 많은 복잡성을 관리하지만 작동 방식에 대해서는 약간의 이해가 필요합니다. 이는 사용자 지정 구성을 정의하거나 여러 프로젝트로 가져오고 공유할 수 있는 다시 사용할 수 있는 속성 집합을 만들 경우 특히 중요합니다.

## <a name="the-vcxproj-file-props-files-and-targets-files"></a>.Vcxproj 파일,.props 파일 및.targets 파일

프로젝트 속성은 프로젝트 파일 (*.vcxproj)에서 직접 또는 프로젝트 파일 가져오기 및는 기본값을 제공는 다른.props 또는.targets 파일에 저장 됩니다. Visual Studio 2015의 경우 이러한 파일은 **\Program Files (x86)\MSBuild\Microsoft.Cpp\v4.0\V140**에 있습니다. Visual Studio 2017의 경우 이러한 파일은 Visual Studio _버전_이 설치된 **\\Program Files(x86)\\Microsoft Visual Studio\\2017\\_edition_\\Common7\\IDE\\VC\\VCTargets**에 있습니다. 속성은 고유한 프로젝트에 추가할 수 있는 모든 사용자 지정.props 파일에도 저장됩니다. MSBuild에 대해 매우 뛰어나게 이해하고 있지 않은 경우 모든 속성, 특히 상속에 참여한 속성을 수정하려면 해당 파일을 수동으로 편집하지 말고 대신 IDE에서 속성 페이지를 사용하는 것이 좋습니다.

에서 설명한 것 처럼 동일한 구성 동일 속성과 이러한 서로 다른 파일에서 다른 값을 할당할 수 있습니다. 프로젝트를 빌드하면 MSBuild 엔진은 올바로 정의된 순서대로(아래 설명 참조) 프로젝트 파일 및 가져온 모든 파일을 평가합니다. 각 파일을 평가하기 때문에 해당 파일에서 정의된 모든 속성 값이 기존 값을 재정의합니다. 지정되지 않은 모든 값은 이전에 평가된 파일에서 상속됩니다. 따라서 속성 페이지를 사용하여 속성을 설정하면 설정하는 위치에도 주의해야 합니다. .props 파일에서 "X"로 속성을 설정하지만 프로젝트 파일에서 속성이 "Y"로 설정되는 경우 해당 프로젝트는 속성을 "Y"로 설정하여 빌드하게 됩니다. .cpp 파일처럼 프로젝트 항목에서 동일한 속성이 "z"로 설정되는 경우 MSBuild 엔진은 "Z" 값을 사용하게 됩니다. 

다음은 기본 상속 트리입니다.

1. MSBuild CPP 도구 집합의 기본 설정(.vcxproj 파일에서 가져온 ..\Program Files\MSBuild\Microsoft.Cpp\v4.0\Microsoft.Cpp.Default.props)

2. 속성 시트

3. .vcxproj 파일. 기본 및 속성 시트 설정을 재정의할 수 있습니다.

4. 항목 메타데이터

> [!TIP]
> 속성 페이지에서 현재 컨텍스트에 `bold`의 속성이 정의됩니다. 일반 글꼴의 속성이 상속됩니다.

## <a name="view-an-expanded-project-file-with-all-imported-values"></a>모든 가져온된 값을 사용 하 여 확장 된 프로젝트 파일을 보려면

확장된 파일을 보고 지정된 속성 값의 상속 방법을 결정하는 것이 유용한 경우도 있습니다. 확장 버전을 보려면 Visual Studio 명령 프롬프트에서 다음 명령을 입력합니다. 자리 표시자 파일 이름을 사용할 이름으로 변경합니다.

**msbuild /pp:** *temp* **.txt** *myapp* **.vcxproj**

확장된 프로젝트 파일은 클 수 있으며 MSBuild를 잘 알고 있지 않은 한 이해하기 어렵습니다. 프로젝트 파일의 기본 구조는 다음과 같음:

1. IDE에 노출되지 않는 기본 프로젝트 속성입니다.

2. 일부 기본 toolset-independent 속성을 정의하는 Microsoft.cpp.default.props의 가져오기.

3. **구성 일반** 페이지에서 **PlatformToolset** 및 **프로젝트** 기본 속성으로 노출된 전역 구성 속성입니다. 이러한 속성은 다음 단계에서 어떤 도구 집합 및 내장 속성 시트를 Microsoft.cpp.props로 가져오게 하는지를 결정합니다.

4. 대부분의 프로젝트 기본값을 설정하는 Microsoft.cpp.props의 가져오기.

5. .user 파일을 포함하여 모든 속성 시트를 가져옵니다. 등록 정보 시트는 **PlatformToolset** 및 **프로젝트** 기본 속성을 제외한 모든 항목을 재정의할 수 있습니다.

6. 프로젝트 구성 속성의 나머지입니다. 이러한 값은 속성 시트에서 설정된 것을 재정의할 수 있습니다.

7. 메타데이터와 함께 있는 항목(파일)입니다. 이러한 값이 다른 속성과 가져오기보다 앞에 있더라도 항상 MSBuild 실행 규칙의 마지막 단어입니다.

자세한 내용은 [MSBuild 속성](/visualstudio/msbuild/msbuild-properties)을 참조하세요.

## <a name="build-configurations"></a>빌드 구성

구성은 이름이 지정된 속성의 임의의 그룹입니다. Visual Studio는 디버그 및 릴리스 구성을 제공하며 각각은 디버그 빌드 또는 릴리스 빌드에 대해 다양한 속성을 적절하게 설정합니다. **Configuration Manager**를 사용하여 빌드의 특정 버전에 대한 속성을 그룹화하기에 편리한 방법으로 사용자 지정 구성을 정의할 수 있습니다. 

빌드 구성이 보다 명확히 파악할를 열고 **속성 관리자** 를 선택 하 여 **보기 &#124; 속성 관리자** 하거나 **보기 &#124; 다른 Windows &#124; 속성 관리자**  설정에 따라 합니다. **속성 관리자** 프로젝트의 각 구성/플랫폼 쌍에 대 한 노드가 있습니다. 이러한 노드 각각에 해당 구성에 대한 일부 특정 속성을 설정하는 속성 시트(.props 파일)에 대한 노드가 있습니다.

![속성 관리자](media/property-manager.png "속성 관리자")

문자 집합 속성 "설정 안 함" 대신 "Unicode 사용"을 설정 하 고 클릭 일반 속성 페이지에서 창으로 이동 하는 경우 **확인**, 속성 관리자에 표시 됩니다 없습니다 **유니코드 지원** 에 대 한 속성 시트 다른 구성에 대 한 현재 구성 하지만 여전히 수 있습니다.

속성 관리자 및 속성 시트에 대 한 자세한 내용은 참조 하세요. [공유 또는 resuse Visual Studio c + + 프로젝트 설정](create-reusable-property-configurations.md)합니다.

> [!TIP]
> .user 파일은 레거시 기능입니다. 구성/플랫폼에 따라 속성을 올바르게 그룹화된 상태로 유지하기 위해 이 파일을 삭제하는 것이 좋습니다.



