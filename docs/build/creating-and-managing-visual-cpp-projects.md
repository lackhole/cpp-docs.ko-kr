---
title: C++-visual Studio 프로젝트
ms.date: 12/12/2018
f1_keywords:
- vcprojects
- creatingmanagingVC
helpviewer_keywords:
- ATL projects, creating
- Visual C++ projects, creating
- projects [C++], creating
- Visual C++ projects
- ATL projects
ms.assetid: 11003cd8-9046-4630-a189-a32bf3b88047
ms.openlocfilehash: b4772b9bd625a542a18039386fefe42840ab65b1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62195731"
---
# <a name="visual-studio-projects---c"></a>Visual Studio 프로젝트-C++

A *Visual Studio 프로젝트* 프로젝트를 MSBuild 빌드 시스템에 기반 합니다. MSBuild는 Visual Studio 용 네이티브 빌드 시스템 이며 일반적으로 MFC 또는 ATL 라이브러리, COM 구성 요소 및 기타 Windows 전용 프로그램을 사용 하는 데스크톱 응용 프로그램 뿐만 아니라 UWP 앱에 대 한 사용 하는 시스템을 구축 하는 가장 합니다. MSBuild는 Visual studio에 긴밀 하 게 통합 되지만 명령줄에서도 사용할 수 있습니다. 

## <a name="create-a-project"></a>프로젝트 만들기

선택 하 여 C++ 프로젝트를 만들 수 있습니다 **파일 &#124; 새로 만들기 &#124; 프로젝트**, 왼쪽된 창에서 Visual C++를 선택 합니다. 가운데 창에서 프로젝트 템플릿 목록을 표시 합니다. 

   ![프로젝트 템플릿](../overview/media/vs2017-new-project.png " Visual Studio 2017 새 프로젝트 대화 상자")

Visual Studio에 포함 된 모든 기본 프로젝트 템플릿에 대 한 자세한 내용은 참조 하세요. [Visual Studio에서 C++ 프로젝트 템플릿](reference/visual-cpp-project-types.md)합니다. 사용자 고유의 프로젝트 템플릿을 만들 수 있습니다. 자세한 내용은 [방법: 프로젝트 템플릿 만들기](/visualstudio/ide/how-to-create-project-templates)합니다.

프로젝트를 만든 후에 저장 되는 [솔루션 탐색기](/visualstudio/ide/solutions-and-projects-in-visual-studio) 창:

   ![솔루션 탐색기](media/mathlibrary-solution-explorer-153.png)

새 프로젝트를 만들면 솔루션 파일 (.sln) 만들어집니다. 마우스 오른쪽 단추로 클릭 하 여 솔루션에 추가 프로젝트를 추가할 수 있습니다 **솔루션 탐색기**합니다. 솔루션 파일을 여러 개의 관련된 프로젝트를 갖지만 보다 훨씬 더 하지 하는 경우 빌드 종속성을 조정 하기 위해 사용 됩니다. 모든 컴파일러 옵션이 프로젝트 수준에서 설정 됩니다.

## <a name="add-items"></a>항목 추가

프로젝트를 마우스 오른쪽 단추로 클릭 하 여 프로젝트에 소스 코드 파일, 아이콘 또는 다른 모든 항목을 추가 **솔루션 탐색기** 선택 하 고 **추가 > 새로 만들기** 하거나 **추가 > 기존**합니다.

## <a name="add-third-party-libraries"></a>타사 라이브러리를 추가 합니다.

타사 라이브러리를 추가 하려면 사용 합니다 [vcpkg](vcpkg.md) 패키지 관리자입니다. 모든 Visual Studio 프로젝트에서 참조 하는 경우 해당 라이브러리에 대 한 경로 설정 하는 Visual Studio 통합 단계를 실행 합니다. 

## <a name="set-compiler-options-and-other-build-properties"></a>컴파일러 옵션 및 기타 빌드 속성 설정

프로젝트를 마우스 오른쪽 단추로 프로젝트의 빌드 설정을 구성 하려면 **솔루션 탐색기** 선택한 **속성**합니다. 자세한 내용은 [Visual Studio에서 설정 C++ 컴파일러 및 빌드 속성](working-with-project-properties.md)합니다.

## <a name="compile-and-run"></a>컴파일 및 실행

를 컴파일하고 새 프로젝트를 실행 하려면 키를 누릅니다 **F5** 누르거나 합니다 *디버그 드롭다운* 주 도구 모음에서 녹색 화살표가 있는 합니다. *구성 드롭다운 목록* 수행할지 여부를 선택 하는 위치를 *디버그* 또는 *릴리스* 빌드 (또는 일부 다른 사용자 지정 구성).

새 프로젝트를 오류 없이 컴파일합니다. 사용자 고유의 코드를 추가할 때 경우에 따라 오류가 발생할 수도 있습니다 경고를 트리거합니다. 오류가 완료; 빌드 방지 경고 하지 않습니다. 모든 오류 및 경고 나타납니다 오류 목록에서 및 출력 창에 프로젝트를 빌드할 때. 

   ![출력 창과 오류 목록](../overview/media/vs2017-output-error-list.png)

오류 목록에서 눌러도 **F1** 해당 설명서 항목으로 이동 하려면 강조 표시 된 오류입니다.

## <a name="in-this-section"></a>섹션 내용

[Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](working-with-project-properties.md)<br/>
프로젝트 설정을 지정 하려면 속성 페이지 및 속성 시트를 사용 하는 방법입니다.

[빌드 시 참조 라이브러리 및 구성 요소](adding-references-in-visual-cpp-projects.md)<br/>
프로젝트에 라이브러리를 Dll에 COM 및.NET 구성 요소를 포함 하는 방법.
 
[프로젝트 출력 파일 구성](how-to-organize-project-output-files-for-builds.md)<br/>
빌드 프로세스에서 만든 실행 파일의 위치를 사용자 지정 하는 방법입니다.

[사용자 지정 빌드 단계 및 빌드 이벤트](understanding-custom-build-steps-and-build-events.md)<br/>
지정 된 지점에서 빌드 프로세스에 임의의 명령을 추가 하는 방법입니다.

[기존 코드로 프로젝트 만들기](how-to-create-a-cpp-project-from-existing-code.md)<br/>
소스 파일의 느슨한 컬렉션에서 새 Visual Studio 프로젝트를 만드는 방법입니다.

## <a name="see-also"></a>참고자료

[프로젝트 및 빌드 시스템](projects-and-build-systems-cpp.md)<br>
