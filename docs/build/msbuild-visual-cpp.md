---
title: 명령줄 c + +의 MSBuild
ms.date: 12/12/2018
f1_keywords:
- MSBuild
helpviewer_keywords:
- MSBuild
ms.assetid: 7a1be7ff-0312-4669-adf2-5f5bf507d560
ms.openlocfilehash: 565b1c47b4476fa7cb830e15b978b389f4344ee1
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57820474"
---
# <a name="msbuild-on-the-command-line---c"></a>명령줄 c + +의 MSBuild

일반적으로 Visual Studio를 사용 하 여 프로젝트 속성을 설정 하 여 MSBuild 시스템 호출을 하는 것이 좋습니다. 사용할 수 있습니다 합니다 **MSBuild** 도구 명령 프롬프트에서 직접. 빌드 프로세스 정보를 만들고 편집할 수 있는 프로젝트 파일 (.vcxproj)에 의해 제어 됩니다. 프로젝트 파일에 따라 빌드 옵션 빌드 단계, 조건 및 이벤트를 지정 합니다. 0을 지정할 수는 또한 이상의 명령줄 *옵션* 인수입니다.

> **msbuild.exe** [ *project_file* ] [ *options* ]

사용 된 **/대상** (또는 **/t**) 및 **/property** (또는 **/p**) 명령줄 옵션을 특정 속성 및 된 대상 재정의 프로젝트 파일에 지정 합니다.

프로젝트 파일의 필수 함수를 지정 하는 것을 *대상*, 프로젝트, 입력 및 출력 작업을 수행 하는 데 필요한에 적용 된 특정 작업 인 합니다. 프로젝트 파일을 기본 대상을 포함할 수 있는 하나 이상의 대상을 지정할 수 있습니다.

하나 이상의 시퀀스의 각 대상 구성 *작업*합니다. 각 작업은 하나의 실행 가능 명령이 포함 된.NET Framework 클래스로 표시 됩니다. 예를 들어,를 [CL 작업](/visualstudio/msbuild/cl-task) 포함 된 [cl.exe](reference/compiling-a-c-cpp-program.md) 명령입니다.

A *작업 매개 변수* 클래스 작업의 속성 이며 일반적으로 실행 가능 명령의 명령줄 옵션을 나타냅니다. 예를 들어를 `FavorSizeOrSpeed` 의 매개 변수를 `CL` 에 해당 하는 작업을 **/Os** 및 **/Ot** 컴파일러 옵션입니다.

추가 작업 매개 변수는 MSBuild 인프라를 지원 합니다. 예를 들어를 `Sources` 작업 매개 변수는 다른 작업에서 사용할 수 있는 작업 집합을 지정 합니다. MSBuild 작업에 대 한 자세한 내용은 참조 하세요. [작업 참조](/visualstudio/msbuild/msbuild-task-reference)합니다.

대부분의 작업 입력 및 출력 파일 이름, 경로 및 문자열, 숫자 또는 부울 매개 변수와 같은 필요 합니다. 예를 들어 일반적인 입력 컴파일할.cpp 소스 파일의 이름입니다. 중요 한 입력된 매개 변수가 예를 들어, 빌드 구성 및 플랫폼을 지정 하는 문자열 "디버그\|Win32"입니다. 하나 이상의 사용자 정의 XML에서 입력 및 출력이 지정 된 `Item` 에 포함 된 요소는 `ItemGroup` 요소입니다.

프로젝트 파일을 사용자 지정할 수도 있습니다 *속성* 하 고 `ItemDefinitionGroup` *항목*합니다. 속성 및 항목은 빌드에서 변수로 사용할 수 있는 이름/값 쌍을 형성 합니다. 쌍의 이름 구성 요소 정의 *매크로*, 값 구성 요소를 선언 하 고는 *매크로 값*합니다. 속성 매크로 $를 사용 하 여 액세스 하는 (*이름을*) 표기법 및 항목 매크로 %(를 사용 하 여 액세스할*이름*) 표기법입니다.

프로젝트 파일의 다른 XML 요소 수 매크로 테스트 하 고 그런 다음 조건부로 매크로의 값을 설정 하거나 빌드 실행을 제어. 매크로 이름과 리터럴 문자열 경로 및 파일 이름과 같은 구문을 생성할에 연결할 수 있습니다. 명령줄에는 **/property** 옵션을 설정 하거나 프로젝트 속성을 재정의 합니다. 명령줄에서 항목을 참조할 수 없습니다.

조건에 따라 MSBuild 시스템은 이전 또는 다른 대상 이후에 대상을 실행할 수 있습니다. 또한 시스템에 파일 대상을 사용 하는 내보내는 파일 보다 최신 인지에 따라 대상을 빌드할 수 있습니다.

MSBuild에 대 한 자세한 내용은 다음을 참조 하세요.

- [MSBuild](/visualstudio/msbuild/msbuild) 개요의 MSBuild 개념입니다.

- [MSBuild 참조](/visualstudio/msbuild/msbuild-reference) MSBuild 시스템에 대 한 정보를 참조 합니다.

- [프로젝트 파일 스키마 참조](/visualstudio/msbuild/msbuild-project-file-schema-reference) 해당 특성과 부모 및 자식 요소와 함께 MSBuild XML 스키마 요소를 나열 합니다. 특히 유의 합니다 [ItemGroup](/visualstudio/msbuild/itemgroup-element-msbuild), [PropertyGroup](/visualstudio/msbuild/propertygroup-element-msbuild), [대상](/visualstudio/msbuild/target-element-msbuild), 및 [태스크](/visualstudio/msbuild/task-element-msbuild) 요소입니다.

- [명령줄 참조](/visualstudio/msbuild/msbuild-command-line-reference) 명령줄 인수 및 msbuild.exe와 함께 사용할 수 있는 옵션을 설명 합니다.

- [작업 참조](/visualstudio/msbuild/msbuild-task-reference) 에 대해 설명 하는 MSBuild 작업입니다. 특히 Visual c + + 관련 된 이러한 작업을 note: [BscMake 작업](/visualstudio/msbuild/bscmake-task), [CL 작업](/visualstudio/msbuild/cl-task)를 [CPPClean 작업](/visualstudio/msbuild/cppclean-task)를 [LIB 작업](/visualstudio/msbuild/lib-task)를 [링크 작업](/visualstudio/msbuild/link-task), [MIDL 작업](/visualstudio/msbuild/midl-task), [MT 작업](/visualstudio/msbuild/mt-task)를 [RC 작업](/visualstudio/msbuild/rc-task)하십시오 [SetEnv 작업](/visualstudio/msbuild/setenv-task), [VCMessage 작업](/visualstudio/msbuild/vcmessage-task)

## <a name="in-this-section"></a>섹션 내용

|용어|정의|
|----------|----------------|
|[연습: MSBuild를 사용하여 Visual C++ 프로젝트 만들기](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)|사용 하 여 Visual C++ 프로젝트를 만드는 방법을 보여 줍니다 **MSBuild**합니다.|
|[방법: MSBuild 프로젝트에서 빌드 이벤트 사용](how-to-use-build-events-in-msbuild-projects.md)|빌드에서 particuler 단계에서 발생 하는 동작을 지정 하는 방법에 설명 합니다: 빌드를 시작할; 링크 단계가 시작 하기 전에 빌드가 끝난 후 또는 합니다.|
|[방법: MSBuild 프로젝트에 사용자 지정 빌드 단계 추가](how-to-add-a-custom-build-step-to-msbuild-projects.md)|빌드 순서에 사용자 정의 단계를 추가 하는 방법에 설명 합니다.|
|[방법: MSBuild 프로젝트에 사용자 지정 빌드 도구 추가](how-to-add-custom-build-tools-to-msbuild-projects.md)|특정 파일을 사용 하 여 빌드 도구를 연결 하는 방법에 설명 합니다.|
|[방법: 사용자 지정 도구를 프로젝트 속성에 통합](how-to-integrate-custom-tools-into-the-project-properties.md)|프로젝트 속성에 사용자 지정 도구에 대 한 옵션을 추가 하는 방법에 설명 합니다.|
|[방법: 대상 프레임워크 및 플랫폼 도구 세트 수정](how-to-modify-the-target-framework-and-platform-toolset.md)|여러 프레임 워크 또는 도구 집합에 대 한 프로젝트를 컴파일하는 방법을 보여 줍니다.|

## <a name="see-also"></a>참고자료

[명령줄에서 MSVC 도구 집합을 사용 하 여](building-on-the-command-line.md)
