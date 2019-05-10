---
title: '방법: 프로젝트 속성에 사용자 지정 도구 통합'
ms.date: 04/27/2016
helpviewer_keywords:
- 'msbuild (c++), howto: integrate custom tools'
ms.assetid: f32d91a4-44e9-4de3-aa9a-1c7f709ad2ee
ms.openlocfilehash: e9f0758bbb2ab796bd60516ca5d57c605e36fb56
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220692"
---
# <a name="how-to-integrate-custom-tools-into-the-project-properties"></a>방법: 프로젝트 속성에 사용자 지정 도구 통합

Visual Studio를 사용자 지정 도구 옵션을 추가할 수 있습니다 **속성 페이지** 기본 XML 스키마 파일을 만들어 창입니다.

**구성 속성** 섹션을 **속성 페이지** 이라고 하는 설정 그룹 창에 표시 됩니다 *규칙*합니다. 모든 규칙에는 도구 또는 기능 그룹에 대 한 설정을 포함합니다. 예를 들어 합니다 **링커** 규칙 링커 도구에 대 한 설정을 포함 합니다. 규칙의 설정을 세분화할 수 *범주*합니다.

이 문서는 속성은 Visual Studio를 시작할 때 로드 되도록 사용자 지정 도구에 대 한 속성을 포함 하는 집합 디렉터리에서 파일을 만드는 방법을 설명 합니다. 파일을 수정 하는 방법에 대 한 정보를 참조 하세요 [플랫폼 확장성 2 부](https://blogs.msdn.microsoft.com/vsproject/2009/06/18/platform-extensibility-part-2/) Visual Studio Project Team 블로그에서입니다.

### <a name="to-add-or-change-project-properties"></a>추가 하거나 프로젝트 속성을 변경 하려면

1. XML 편집기에서 XML 파일을 만듭니다.

1. Visual Studio 2017에 파일을 저장 `VCTargets\1033` 폴더입니다. 설치 된 Visual Studio 2017의 각 버전 및 각 언어에 대해 다른 경로 해야 합니다. 예를 들어 영어에서 Visual Studio Enterprise edition의 폴더 경로 `%ProgramFiles%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets\1033`합니다. 언어 및 Visual Studio 버전에 대 한 경로 조정 합니다. 모든 규칙에는 **속성 페이지** 창이이 폴더에 XML 파일에 의해 표시 됩니다. 파일 폴더의 이름은 고유 해야 합니다.

1. 내용을 복사한 `%ProgramFiles%\Microsoft Visual Studio\2017\<VS Edition>\Common7\IDE\VC\VCTargets\<LCID>\cl.xml`, 변경 내용을 저장 하지 않고 닫 및 새 XML 파일의 콘텐츠를 붙여넣습니다. 모든 XML 스키마 파일을 사용할 수 있습니다-이 하나만 사용할 수 있으므로 템플릿을 사용 하 여 시작 합니다.

1. 새 XML 파일에서 요구 사항에 따라 콘텐츠를 수정 합니다. 변경 해야 합니다 **규칙 이름** 하 고 **Rule.DisplayName** 파일의 맨 위에 있는 합니다.

1. 변경 내용을 저장 하 고 파일을 닫습니다.

1. XML 파일 `%ProgramFiles%\Microsoft Visual Studio\2017\<VS Edition>\Common7\IDE\VC\VCTargets\<LCID>` Visual Studio 시작 될 때 로드 됩니다. 따라서 새 파일을 테스트 하려면 Visual Studio 다시 시작 합니다.

1. **솔루션 탐색기**프로젝트를 마우스 오른쪽 단추로 클릭 한 다음 클릭 **속성**합니다. 에 **속성 페이지** 창의 왼쪽된 창에서 규칙의 이름으로 새 노드에 있는지 확인 합니다.

## <a name="see-also"></a>참고자료

[명령줄에서 MSBuildC++](msbuild-visual-cpp.md)
