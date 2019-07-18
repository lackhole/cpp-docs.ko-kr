---
title: 고급 속성 페이지 (프로젝트)
ms.date: 07/19/2019
f1_keywords:
- VC.Project.VCConfiguration.VCToolsVersion
ms.description: Use the Advanced property page in Visual Studio 2019 to set various properties for C++ projects.
ms.openlocfilehash: fae3c76d4a62e3b0409664b3630ad76ab601c52b
ms.sourcegitcommit: 610751254a01cba6ad15fb1e1764ecb2e71f66bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/18/2019
ms.locfileid: "68315532"
---
# <a name="advanced-property-page"></a>고급 속성 페이지

고급 속성 페이지는 Visual Studio 2019 이상에서 사용할 수 있습니다.

::: moniker range="vs-2019"

## <a name="advanced-properties"></a>고급 속성

- **대상 파일 확장명**

   빌드 출력에 사용할 파일 확장명을 지정 합니다. 기본값은 응용 프로그램의 경우 **.exe** , 정적 라이브러리의 경우 **.lib** , dll의 경우 **.dll** 입니다.

- **정리할 때 삭제할 확장명**

   **정리** 옵션(**빌드** 메뉴)은 프로젝트 구성이 빌드되는 중간 디렉터리에서 파일을 삭제합니다. 이 속성을 통해 지정된 확장명을 가진 파일은 **정리**를 실행하거나 다시 빌드를 수행할 경우 삭제됩니다. 중간 디렉터리에 있는 이러한 확장명의 파일뿐 아니라 빌드 시스템은 위치에 관계없이 알려진 빌드 출력(.obj 파일과 같은 중간 출력 포함)도 삭제합니다. 와일드카드 문자를 지정할 수 있습니다.

   프로그래밍 방식으로 이 속성에 액세스하려면 <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.DeleteExtensionsOnClean%2A>을 참조하세요.

- **빌드 로그 파일**

   프로젝트를 빌드할 때마다 생성되는 로그 파일에 대해 기본값이 아닌 위치를 지정할 수 있습니다. 기본 위치는 매크로 $(IntDir)$(MSBuildProjectName).log에서 지정됩니다.

   프로젝트 매크로를 사용하여 디렉터리 위치를 변경할 수 있습니다. [빌드 명령 및 속성에 대 한 일반 매크로](common-macros-for-build-commands-and-properties.md)를 참조 하세요.

- **기본 설정 빌드 도구 아키텍처**

   X86 또는 x64 빌드 도구를 사용할지 여부를 지정 합니다.

- **디버그 라이브러리 사용**

   디버그 또는 릴리스 빌드를 만들지 여부를 지정 합니다.

- **Unity (점보) 빌드 사용**

   빌드 성능을 향상 시키기 위해 컴파일하기 C++ 전에 많은 소스 파일이 하나 이상의 "unity" 파일에 결합 된 빌드 프로세스를 사용 하도록 설정 합니다. Unity 게임 엔진과 관련이 없습니다.

- **MFC 사용**

   MFC 프로젝트가 MFC DLL에 정적 또는 동적으로 연결하는지를 지정합니다. 비 MFC 프로젝트는 **표준 Windows 라이브러리 사용**을 선택하여 MFC를 사용할 때 포함되는 다양한 Win32 라이브러리에 연결할 수 있습니다.

   프로그래밍 방식으로 이 속성에 액세스하려면 <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.useOfMfc%2A>을 참조하세요.

- **문자 집합**

   _UNICODE 또는 _MBCS를 설정해야 하는지를 정의합니다. 해당하는 경우 링커 진입점에도 영향을 줍니다.

   프로그래밍 방식으로 이 속성에 액세스하려면 <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.CharacterSet%2A>을 참조하세요.

- **전체 프로그램 최적화**

   [/GL](gl-whole-program-optimization.md) 컴파일러 옵션 및 [/LTCG](ltcg-link-time-code-generation.md) 링커 옵션을 지정합니다. 기본적으로 디버그 구성에 대해 비활성화되고 소매 구성에 대해 활성화됩니다.

- **MSVC 도구 집합 버전**

   프로젝트를 빌드하는 데 사용 되는 MSVC 도구 집합의 전체 버전을 지정 합니다. 여러 가지 업데이트 및 미리 보기 버전의 도구 집합을 설치한 경우 여기에서 사용할 항목을 지정할 수 있습니다.

## <a name="ccli-properties"></a>C++/CLI 속성

- **공용 언어 런타임 지원**

   [/clr](clr-common-language-runtime-compilation.md) 컴파일러 옵션을 사용하게 합니다.

   프로그래밍 방식으로 이 속성에 액세스하려면 <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.ManagedExtensions%2A>을 참조하세요.

- **.NET 대상 프레임워크 버전**

   관리 프로젝트에서 대상으로 지정할 .NET Framework 버전을 지정합니다.

- **관리 증분 빌드 사용**

   관리 프로젝트의 경우 이를 통해 어셈블리를 생성할 때 외부 표시 유형을 검색할 수 있습니다. 관리 프로젝트에 대한 변경 내용이 다른 프로젝트에 표시되지 않는 경우 종속 프로젝트가 다시 빌드되지 않습니다. 그러면 관리 프로젝트를 포함하는 솔루션에서 빌드 시간을 크게 개선할 수 있습니다.

::: moniker-end
