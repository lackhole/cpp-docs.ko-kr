---
title: '방법: 대상 프레임 워크 및 플랫폼 도구 집합 수정'
ms.custom: conceptual
ms.date: 11/04/2016
f1_keywords:
- msbuild.cpp.howto.modifytargetframeworkandplatformtoolset
helpviewer_keywords:
- 'msbuild (c++), howto: modify target framework and platform toolset'
ms.assetid: 031b1d54-e6e1-4da7-9868-3e75a87d9ffe
ms.openlocfilehash: cf2078432f629a353e0c325b407db59681ffd9d3
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57820080"
---
# <a name="how-to-modify-the-target-framework-and-platform-toolset"></a>방법: 대상 프레임 워크 및 플랫폼 도구 집합 수정

다른 버전의.NET Framework를 대상으로 하는 다른 플랫폼 도구 집합을 사용 하 여 Visual C++ 프로젝트 설정을 변경할 수 있습니다. 기본적으로 프로젝트 시스템에는 프로젝트를 만드는 데 사용하는 Visual Studio 버전에 해당하는 .NET Framework 버전 및 도구 집합 버전이 사용됩니다. 프로젝트 속성을 수정하여 대상 플랫폼 도구 집합을 변경할 수 있습니다. 프로젝트 파일(.vcxproj)을 수정하여 대상 프레임워크를 변경할 수 있습니다. 각 컴파일 대상에 대해 별도의 코드베이스를 유지 관리할 필요는 없습니다.

> [!IMPORTANT]
>  일부 버전에서는 수정된 대상 프레임워크 또는 플랫폼 도구 집합을 지원하지 않습니다. 호환성 정보를 참조 하세요 [포트, 마이그레이션 및 Visual Studio 프로젝트 업그레이드](/visualstudio/porting/port-migrate-and-upgrade-visual-studio-projects)합니다.

대상 프레임워크를 변경하는 경우 플랫폼 도구 집합도 해당 프레임워크를 지원하는 버전으로 변경합니다. 예를 들어 .NET Framework 4.5를 대상으로 하려면 Visual Studio 2015(v140), Visual Studio 2013(v120) 또는 Visual Studio 2012(v110)와 같은 호환되는 플랫폼 도구 집합을 사용해야 합니다. .NET Framework 2.0, 3.0, 3.5, 4 및 x86, Itanium, x64 플랫폼을 대상으로 하는 **Windows7.1SDK** 플랫폼 도구 집합을 사용할 수 있습니다.

> [!NOTE]
>  대상 플랫폼 도구 집합을 변경하려면 연관된 버전의 Visual Studio 또는 Windows 플랫폼 SDK가 설치되어 있어야 합니다. 예를 들어 **Windows7.1SDK** 플랫폼 도구 집합이 있는 Itanium 플랫폼을 대상으로 하려면 [Windows 7용 Microsoft Windows SDK 및 .NET Framework 4 SP1](http://www.microsoft.com/download/details.aspx?id=8279) 이 설치되어 있어야 합니다. 그러나 올바른 Framework 버전 및 플랫폼 도구 집합을 대상으로 한 경우 Visual Studio의 다른 호환 버전을 사용하여 개발 작업을 수행할 수 있습니다.

사용자 지정 플랫폼 도구 집합을 만들어 대상 플랫폼을 추가로 확장할 수 있습니다. 자세한 내용은 Visual C++ 블로그의 [C++ Native Multi-Targeting](https://blogs.msdn.microsoft.com/vcblog/2009/12/08/c-native-multi-targeting/) 을 참조하세요.

### <a name="to-change-the-target-framework"></a>대상 프레임워크를 변경하려면

1. Visual Studio의 **솔루션 탐색기**에서 프로젝트를 선택합니다. 메뉴 모음에서 **프로젝트** 메뉴를 열고 **프로젝트 언로드**를 선택합니다. 프로젝트에 대한 프로젝트 파일(.vcxproj)을 언로드합니다.

    > [!NOTE]
    >  Visual Studio에서 프로젝트 파일을 수정하는 동안에는 C++ 프로젝트를 로드할 수 없습니다. 그러나 메모장 등의 다른 편집기를 사용하면 Visual Studio에서 프로젝트가 로드되는 동안 프로젝트 파일을 수정할 수 있습니다. Visual Studio가 프로젝트 파일이 변경된 것을 감지하고 프로젝트를 다시 로드하라고 요청합니다.

1. 메뉴 모음에서 **파일**, **열기**, **파일**을 차례로 선택합니다. **파일 열기** 대화 상자에서 해당 프로젝트 폴더를 탐색하고 프로젝트(.vcxproj) 파일을 엽니다.

1. 프로젝트 파일에서 대상 Framework 버전에 대한 항목을 찾습니다. 예를 들어, 프로젝트가 .NET Framework 4.5를 사용하도록 디자인된 경우 `<TargetFrameworkVersion>v4.5</TargetFrameworkVersion>` 의 `<PropertyGroup Label="Globals">` 요소에서 `<Project>` 을 찾습니다. `<TargetFrameworkVersion>` 요소가 없는 경우 프로젝트에 .NET Framework가 사용되지 않으므로 변경할 필요가 없습니다.

1. 값을 v3.5 또는 v4.6과 같은 원하는 프레임워크 버전으로 변경합니다.

1. 변경 내용을 저장하고 편집기를 닫습니다.

1. **솔루션 탐색기**에서 프로젝트의 바로 가기 메뉴를 열고 **프로젝트 다시 로드**를 선택합니다.

1. 변경 내용을 확인하려면 **솔루션 탐색기**에서 마우스 오른쪽 단추를 클릭하여 솔루션이 아닌 프로젝트의 바로 가기 메뉴를 열고 **속성** 을 선택하여 프로젝트 **속성 페이지** 대화 상자를 엽니다. 대화 상자의 왼쪽 창에서 **구성 속성** 을 확장하고 **일반**을 선택합니다. **.NET 대상 프레임워크 버전** 에 새 프레임워크 버전이 표시되는지 확인합니다.

### <a name="to-change-the-project-toolset"></a>프로젝트 도구 집합을 변경하려면

1. Visual Studio의 **솔루션 탐색기**에서 솔루션이 아닌 프로젝트의 바로 가기 메뉴를 열고 **속성** 을 선택하여 프로젝트 **속성 페이지** 대화 상자를 선택합니다.

1. **속성 페이지** 대화 상자에서 **구성** 드롭다운 목록을 열고 **모든 구성**을 선택합니다.

1. 대화 상자의 왼쪽 창에서 **구성 속성** 을 확장하고 **일반**을 선택합니다.

1. 오른쪽 창에서 **플랫폼 도구 집합** 을 선택하고 드롭다운 목록에서 원하는 도구 집합을 선택합니다. 예를 들어 Visual Studio 2010 도구를 설치한 후 선택할 **Visual Studio 2010 (v100)** 프로젝트에 대해 사용 하도록 합니다.

1. **확인** 단추를 선택합니다.

## <a name="see-also"></a>참고자료

[명령줄 c + +의 MSBuild](msbuild-visual-cpp.md)
