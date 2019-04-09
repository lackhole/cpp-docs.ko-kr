---
title: Visual Studio에서 c + + 프로젝트에 대 한 MSBuild 참조
ms.date: 12/08/2018
helpviewer_keywords:
- MSBuild reference [C++]
ms.openlocfilehash: b6ec6b5d276cb7104cf61c229476596d2a2a7684
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59024701"
---
# <a name="msbuild-reference-for-c-projects"></a>C + + 프로젝트에 대 한 MSBuild 참조

MSBuild는 Visual studio에서 c + + 프로젝트를 포함 하 여 모든 프로젝트에 대 한 네이티브 빌드 시스템입니다. Visual Studio 통합된 개발 환경 (IDE)에서 프로젝트를 빌드할 때 다시.vcxproj 프로젝트 파일 및 다양 한.targets 및.props 파일을 사용 하는 msbuild.exe 도구를 호출 합니다. 일반적으로 Visual Studio IDE를 사용 하 여 프로젝트 속성을 설정 하 여 MSBuild를 호출 하는 것이 좋습니다. 프로젝트 파일을 수동으로 편집 제대로 수행 하지 않으면 심각한 문제가 발생할 수 있습니다.

어떤 이유로 MSBuild 명령줄에서 직접 사용 하려면를 참조 하세요 [명령줄에서 MSBuild를 사용 하 여](../msbuild-visual-cpp.md)입니다. MSBuild에 대 한 자세한 내용은 일반적으로 참조 [MSBuild](/visualstudio/msbuild/msbuild) Visual Studio 설명서에서.

## <a name="in-this-section"></a>단원 내용

[C + + 프로젝트에 대 한 MSBuild 내부](msbuild-visual-cpp-overview.md)<br/>
속성 및 대상을 저장 및 사용 하는 방법에 대 한 정보입니다.

[빌드 명령 및 속성에 대한 일반 매크로](common-macros-for-build-commands-and-properties.md)<br/>
경로 및 제품 버전 같은 속성을 정의 하는 매크로 (컴파일 시간 상수)에 대해 설명 합니다.

[C + + 프로젝트용으로 만들어지는 파일 형식](file-types-created-for-visual-cpp-projects.md)<br/>
다양 한 유형의 Visual Studio에서 만든 파일을 다른 프로젝트 형식에 대해 설명 합니다.

[Visual Studio c + + 프로젝트 템플릿](visual-cpp-project-types.md)<br>
C + +에 사용할 수 있는 프로젝트가 MSBuild 기반 프로젝트가 형식을 설명 합니다.

[C + + 새 항목 템플릿](using-visual-cpp-add-new-item-templates.md)<br>
소스 파일 및 Visual Studio 프로젝트에 추가할 수 있는 다른 항목에 설명 합니다.

[미리 컴파일된 헤더 파일](../creating-precompiled-header-files.md) 미리 컴파일된 코드 빌드 시간 속도를 사용자 고유의 사용자 지정을 만드는 방법과 미리 컴파일된 헤더 파일을 사용 하는 방법입니다.

[Visual Studio 프로젝트 속성 참조](property-pages-visual-cpp.md)<br/>
Visual Studio IDE에 설정 된 프로젝트 속성에 대 한 참조 설명서입니다.

## <a name="see-also"></a>참고자료

[C/C++ 빌드 참조](c-cpp-building-reference.md)