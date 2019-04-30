---
title: 매니페스트 도구 구성 속성 (C++ 문서 주석)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCManifestTool.MergeRulesFile
- VC.Project.VCManifestTool.UseUnicodeResponseFiles
- VC.Project.VCManifestTool.SuppressStartupBanner
- VC.Project.VCManifestTool.UseFAT32Workaround
- VC.Project.VCManifestTool.VerboseOutput
- VC.Project.VCManifestTool.AssemblyIdentity
ms.assetid: b99368a5-6819-482c-a06e-f2409290cfd1
ms.openlocfilehash: 9acdb7f5c934a8cabdd1803074778ac9f01f4960
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62271032"
---
# <a name="general-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>일반, 매니페스트 도구, 구성 속성, &lt;Projectname&gt; 속성 페이지 대화 상자

이 대화 상자를 사용하여 [Mt.exe](https://msdn.microsoft.com/library/aa375649)에 대한 일반 옵션을 지정합니다.

이 속성 페이지 대화 상자에 액세스하려면 프로젝트 또는 속성 시트의 속성 페이지를 엽니다. **구성 속성**에서 **매니페스트 도구** 노드를 확장한 다음, **일반**을 선택합니다.

## <a name="uielement-list"></a>UI 요소 목록

- **시작 배너 표시 안 함**

   **예(/nologo)** 는 매니페스트 도구가 시작될 때 표준 Microsoft 저작권 데이터가 숨겨지도록 지정합니다. 빌드 프로세스의 일부 또는 빌드 환경에서 mt.exe를 실행할 때 로그 파일에서 원치 않는 출력이 표시되지 않도록 하려면 이 옵션을 사용합니다.

- **자세한 정보 출력**

   **예(/verbose)** 는 매니페스트 생성 중에 추가 빌드 정보가 표시되도록 지정합니다.

- **어셈블리 ID**

   /Identity 옵션을 사용하여 [\<assemblyIdentity> 요소](/visualstudio/deployment/assemblyidentity-element-clickonce-application)의 특성을 구성하는 ID 문자열을 지정합니다. ID 문자열은 `name` 특성 값으로 시작하고, *특성* = *값* 쌍이 뒤에 옵니다. ID 문자열의 특성은 쉼표로 구분됩니다.

   다음은 ID 문자열의 예입니다.

   `Microsoft.Windows.Common-Controls, processorArchitecture=x86, version=6.0.0.0, type=win32, publicKeyToken=6595b64144ccf1df`

## <a name="see-also"></a>참고자료

[ndptecclick](/visualstudio/deployment/clickonce-application-manifest)<br>
[매니페스트 도구 속성 페이지](manifest-tool-property-pages.md)<br>
[Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)
