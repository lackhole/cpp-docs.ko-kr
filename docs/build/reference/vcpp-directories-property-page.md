---
title: VC++ 디렉터리 속성 페이지
ms.date: 10/09/2018
f1_keywords:
- VC.Project.VCDirectories.IncludePath
- VC.Project.VCDirectories.ReferencePath
- VC.Project.VCDirectories.SourcePath
- VC.Project.VCDirectories.LibraryWPath
- VC.Project.VCDirectories.ExecutablePath
- VC.Project.VCDirectories.LibraryPath
- VS.ToolsOptionsPages.Projects.VCDirectories
- VC.Project.VCDirectories.ExcludePath
helpviewer_keywords:
- VC++ Directories Property Page
ms.assetid: 428eeef6-f127-4271-b3ea-0ae6f2c3d624
ms.openlocfilehash: 3822a3c751ac06154e4b13a12f449e7f0ff2cc07
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826902"
---
# <a name="vc-directories-property-page-windows"></a>VC++ 디렉터리 속성 페이지

이 속성 페이지를 사용하여 Visual Studio에서 현재 선택한 프로젝트를 빌드할 때 사용할 디렉터리를 지시합니다. 솔루션의 여러 프로젝트에 대 한 디렉터리를 설정 하려면 사용 하 여 사용자 지정 속성 시트에 설명 된 대로 [공유 또는 resuse Visual Studio c + + 프로젝트 설정](../create-reusable-property-configurations.md)합니다.

이 페이지의 Linux 버전은 [VC++ 디렉터리(Linux C++)](../../linux/prop-pages/directories-linux.md)를 참조하세요.

**VC++ 디렉터리** 속성 페이지에 액세스하려면:

1. **솔루션 탐색기** 창이 표시되지 않으면 기본 메뉴에서 **보기** > **솔루션 탐색기**를 선택합니다.
1. 프로젝트 노드(최상위 솔루션 아님)를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.
1. **속성 페이지** 대화 상자의 왼쪽 창에서 **구성 속성** > **VC++ 디렉터리**를 선택합니다.

VC++ 디렉터리 속성은 최상위 솔루션 노드가 아닌 프로젝트에 적용됩니다. **구성 속성**에서 **VC++ 디렉터리**가 표시되지 않으면 **솔루션 탐색기** 창에서 C++ 프로젝트 노드를 선택합니다.

![프로젝트 노드 선택](../media/vcppdir.png "VC++ 디렉터리 속성을 보려면 프로젝트 노드 선택")

플랫폼 간 프로젝트의 **VC++ 디렉터리** 속성 페이지가 다르게 표시됩니다. Linux C++ 프로젝트에 대한 정보는 [VC++ 디렉터리(Linux C++)](../../linux/prop-pages/directories-linux.md)를 참조하세요.

경우에 잘 알고 있다면 *프로젝트 속성* Visual Studio에서 유용할 수 있습니다이 첫 번째 읽기 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

**VC++ 디렉터리** 속성에 대한 기본 설정은 프로젝트 형식에 따라 달라집니다. 데스크톱 프로젝트의 경우 특정 플랫폼 도구 집합의 C++ 도구 위치 및 Windows SDK 위치가 포함됩니다. **구성 속성** > **일반** 페이지에서 **플랫폼 도구 집합** 및 **Windows SDK 버전**을 변경할 수 있습니다.

디렉터리에 대한 값을 보려면:

1. **VC++ 디렉터리** 페이지에서 속성 중 하나를 선택합니다. 예를 들어 **라이브러리 디렉터리**를 선택합니다.
1. 속성 값 필드의 끝에 있는 아래쪽 화살표 단추를 선택합니다.
1. 드롭다운 메뉴에서 **편집**을 선택합니다.

![라이브러리 디렉터리 편집](../media/vcppdir_libdir_edit.png "라이브러리 경로를 편집하는 대화 상자")

이제 다음과 같은 대화 상자가 표시됩니다.

![라이브러리 디렉터리 보기](../media/vcppdir_libdir.png "라이브러리 경로를 추가하거나 제거하는 대화 상자")

이 대화 상자를 사용하여 현재 디렉터리를 볼 수 있습니다. 그러나 디렉터리를 추가하거나 변경하려는 경우 **속성 관리자**를 사용하여 속성 시트를 만들거나 기본 사용자 속성 시트를 수정하는 것이 좋습니다. 자세한 내용은 [공유 또는 resuse Visual Studio c + + 프로젝트 설정](../create-reusable-property-configurations.md)합니다.

위와 같이 다양한 상속 경로가 매크로로 지정됩니다.  매크로의 현재 값을 검사하려면 대화 상자의 오른쪽 아래에 있는 **매크로** 단추를 선택합니다. 대부분의 매크로가 구성 형식에 따라 달라집니다. 디버그 빌드의 매크로는 릴리스 빌드의 동일한 매크로와 다른 경로로 평가할 수 있습니다.

편집 상자에서 일부 또는 전체 일치 항목을 검색할 수 있습니다. 다음 그림에서는 "WindowsSDK" 문자열이 포함된 모든 매크로 보여주고, 매크로가 계산하는 현재 경로도 보여줍니다.

![매크로 값 확인](../media/vcppdir_libdir_macros.png "매크로를 편집하는 대화 상자")

참고: 목록에 입력할 때 채워집니다. **Enter** 키를 누르지 않습니다.

매크로 및 이유는 가능 하면 하드 코드 된 경로 대신 사용 해야 하는 방법에 대 한 자세한 내용은 참조 하십시오 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

자주 사용 되는 매크로 목록에 대해서 [명령 및 속성에 대 한 일반 매크로 빌드](common-macros-for-build-commands-and-properties.md)합니다.

다음과 같은 두 가지 방법으로 고유한 매크로를 정의할 수 있습니다.

- 개발자 명령 프롬프트에서 환경 변수를 설정합니다. 모든 환경 변수는 MSBuild 속성/매크로로 처리됩니다.

- .props 파일에서 사용자 매크로를 정의합니다. 자세한 내용은 [속성 페이지 매크로](../working-with-project-properties.md)를 참조하세요.

자세한 내용은 다음 블로그 게시물을 참조 하세요. [VC + + 디렉터리](http://blogs.msdn.com/b/vsproject/archive/2009/07/07/vc-directories.aspx)하십시오 [상속 된 속성 및 속성 시트](http://blogs.msdn.com/b/vsproject/archive/2009/06/23/inherited-properties-and-property-sheets.aspx), 및 [Visual Studio 2010 c + + 프로젝트 업그레이드 가이드](http://blogs.msdn.com/b/vcblog/archive/2010/03/02/visual-studio-2010-c-project-upgrade-guide.aspx)합니다.

## <a name="directory-types"></a>디렉터리 형식

다음과 같이 다른 디렉터리를 지정할 수도 있습니다.

**실행 가능 디렉터리**<br/>
실행 파일을 검색할 디렉터리입니다. **PATH** 환경 변수에 해당합니다.

**포함 디렉터리**<br/>
소스 코드에서 참조되는 포함 파일을 검색할 디렉터리입니다. **INCLUDE** 환경 변수에 해당합니다.

**참조 디렉터리**<br/>
소스 코드에서 [#using](../../preprocessor/hash-using-directive-cpp.md) 지시문으로 참조되는 어셈블리 및 모듈(메타데이터) 파일을 검색할 디렉터리입니다. **LIBPATH** 환경 변수에 해당합니다.

**라이브러리 디렉터리**<br/>
라이브러리(.lib) 파일을 검색할 디렉터리입니다. 여기에는 런타임 라이브러리가 포함됩니다. **LIB** 환경 변수에 해당합니다. 이 설정은 .obj 파일에 적용되지 않습니다. .obj 파일에 연결하려면 **구성 속성** > **링커** > **일반** 속성 페이지에서 **추가 라이브러리 종속성**을 선택한 다음, 파일의 상대 경로를 지정합니다. 자세한 내용은 [링커 속성 페이지](linker-property-pages.md)를 참조하세요.

**라이브러리 WinRT 디렉터리**<br/>
UWP(유니버설 Windows 플랫폼) 앱에서 사용하기 위해 WinRT 라이브러리 파일을 검색할 디렉터리입니다.

**소스 디렉터리**<br/>
IntelliSense에 사용할 소스 파일을 검색할 디렉터리입니다.

**제외 디렉터리**<br/>
컴파일하기 전에 Visual Studio에서는 모든 파일에 대한 타임스탬프를 쿼리하여 이전 컴파일 이후에 수정되었는지 여부를 확인합니다. 프로젝트에 안정적인 대규모 라이브러리가 있는 경우 타임스탬프 검사에서 해당 디렉터리를 제외하여 빌드 시간을 잠재적으로 줄일 수 있습니다.

## <a name="sharing-the-settings"></a>설정 공유

프로젝트 속성을 다른 사용자 또는 여러 컴퓨터와 공유할 수 있습니다. 자세한 내용은 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.
