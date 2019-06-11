---
title: Visual C++ 포팅 및 업그레이드 가이드
ms.date: 09/18/2018
ms.assetid: f5fbcc3d-aa72-41a6-ad9a-a706af2166fb
ms.openlocfilehash: 5659ca362204c62ab8fb21a74dccf8e29f33912c
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66450383"
---
# <a name="visual-c-porting-and-upgrading-guide"></a>Visual C++ 포팅 및 업그레이드 가이드

이 항목에서는 Visual C++ 코드를 업그레이드하기 위한 가이드를 제공합니다. 여기에는 최신 릴리스의 도구에서 코드가 올바르게 컴파일 및 실행되도록 하고 새로운 언어와 Visual Studio 기능을 활용하는 방법이 포함됩니다. 또한 이 항목에는 레거시 앱을 최신 플랫폼으로 마이그레이션하는 방법에 대한 정보가 포함되어 있습니다.

## <a name="reasons-to-upgrade-visual-c-code"></a>Visual C++ 코드를 업그레이드하는 이유

코드 업그레이드를 고려해야 하는 이유는 다음과 같습니다.

- 향상된 컴파일러 최적화로 인한 코드 속도 향상

- 컴파일러 자체의 성능 향상으로 인한 빌드 속도 향상

- 향상된 표준 준수 이제 Visual C++에서 최신 C++ 표준의 많은 기능을 구현합니다.

- 보안 강화. 보호 검사와 같은 보안 기능입니다.

### <a name="porting-your-code"></a>코드 포팅

업그레이드하는 경우 먼저 애플리케이션의 코드와 프로젝트를 고려합니다. 애플리케이션이 Visual Studio를 사용하여 빌드되었나요? 이 경우 관련된 프로젝트를 식별합니다.  사용자 지정 빌드 스크립트가 있나요? Visual Studio의 빌드 시스템을 사용하는 대신 사용자 지정 빌드 스크립트가 있는 경우 Visual Studio에서 프로젝트 파일 및 빌드 설정을 업데이트하도록 하여 시간을 절약할 수 없기 때문에 업그레이드할 때 더 많은 작업을 수행해야 합니다.

Visual Studio의 빌드 시스템 및 프로젝트 파일 형식은 Visual Studio 2008까지 버전의 vcbuild에서 Visual Studio 2010 이후 버전의 MSBuild로 변경되었습니다. 2010 이전 버전에서 업그레이드하고 사용자 지정 빌드 시스템이 있는 경우 업그레이드하려면 더 많은 작업을 수행해야 할 수 있습니다. Visual Studio 2010 이상에서 업그레이드하는 경우 프로젝트에서 이미 MSBuild를 사용 중이므로 애플리케이션에 대한 프로젝트 및 빌드 업그레이드가 훨씬 용이합니다.

Visual Studio의 빌드 시스템을 사용하지 않는 경우 MSBuild를 사용하도록 업그레이드하는 것이 좋습니다. MSBuild를 사용하도록 업그레이드하면 이후 업그레이드가 훨씬 쉬워지며 Visual Studio Online과 같은 서비스를 쉽게 사용할 수 있습니다. MSBuild는 Visual Studio에서 지원하는 모든 대상 플랫폼을 지원합니다.

### <a name="porting-visual-studio-projects"></a>Visual Studio 프로젝트 포팅

프로젝트 또는 솔루션 업그레이드를 시작하려면 새 버전의 Visual Studio에서 솔루션을 열고 지시에 따라 업그레이드를 시작합니다.  프로젝트를 업그레이드하면 업그레이드 보고서가 표시되며, UpgradeLog.htm으로 프로젝트 폴더에 저장됩니다. 업그레이드 보고서는 업그레이드 프로세스 중 발생한 문제에 대한 요약과 변경 내용 또는 자동으로 해결할 수 없는 문제에 대한 일부 정보를 보여 줍니다.

1. 프로젝트 속성

2. 포함 파일

3. 표준의 컴파일러 규칙 향상 또는 변경으로 인해 더 이상 오류 없이 컴파일되지 않는 코드

4. 더 이상 사용할 수 없는 Visual Studio 또는 Windows 기능 또는 Visual Studio 기본 설치에 포함되지 않거나 제품에서 제거된 헤더 파일을 사용하는 코드

5. 이름이 바뀐 API, 변경된 함수 서명 또는 사용되지 않는 함수와 같은 API 변경 내용으로 인해 더 이상 컴파일되지 않는 코드

6. 경고가 오류로 바뀌는 경우 등 진단 변경 내용으로 인해 더 이상 컴파일되지 않는 코드

7. 특히 /NODEFAULTLIB가 사용되는 경우 변경된 라이브러리로 인한 링커 오류

8. 동작 변경 내용으로 인한 런타임 오류 또는 예기치 않은 결과

9. 도구에 도입된 오류로 인한 오류 문제가 발생하는 경우 일반적인 지원 채널을 통해 또는 [Visual Studio C++ 개발자 커뮤니티](https://developercommunity.visualstudio.com/spaces/62/index.html) 페이지를 사용하여 Visual C++ 팀에 보고합니다.

컴파일러 오류로 인한 필연적인 변경 내용 외에도 다음과 같은 일부 변경 내용은 업그레이드 프로세스에서 선택 사항입니다.

1. 새 경고에서 코드를 정리하도록 의미할 수 있습니다. 특정 진단에 따라 이 작업은 코드의 포팅 가능성, 표준 준수 및 보안을 향상시킬 수 있습니다.

2. 승인되지 않은 코드 실행에 대한 검사를 추가하는 [/guard:cf(흐름 제어 보호 사용)](../build/reference/guard-enable-control-flow-guard.md) 컴파일러 옵션과 같은 새로운 컴파일러 기능을 활용하는 것이 좋습니다.

3. 코드를 간소화하는 새로운 언어 기능을 사용하거나, 프로그램의 성능을 향상시키거나, 최신 라이브러리를 사용하고 최신 표준 및 모범 사례를 준수하도록 일부 코드를 업데이트할 수 있습니다.

프로젝트를 업그레이드하고 테스트한 후 코드를 추가로 개선하거나 코드의 이후 방향을 계획하거나 프로젝트의 아키텍처를 다시 고려할 수도 있습니다. 진행 중인 개발 작업을 받게 되나요? 코드가 다른 플랫폼에서 실행되는 것이 중요한가요?  중요하다면 어떤 플랫폼인가요?  C++는 포팅 가능성과 플랫폼 간 개발을 염두에 두고 설계된 표준화된 언어이지만 많은 Windows 애플리케이션의 코드는 여전히 Windows 플랫폼에 긴밀히 연결되어 있습니다. 코드를 리팩터링하여 Windows 플랫폼에 연결된 부분을 분리하고 싶으세요?

사용자 인터페이스는 어떤가요? MFC를 사용하는 경우 UI를 업데이트하는 것이 좋습니다. 2008에서 기능 팩으로 도입된 최신 MFC 기능을 사용 중인가요? 전체 앱을 다시 작성하지 않고 앱에 최신 모양과 느낌을 제공하려는 경우 MFC의 리본 API를 사용하거나 MFC의 새로운 기능 중 일부를 사용할 수 있습니다.

프로그램에 XAML 사용자 인터페이스를 제공하려 하지만 UWP 앱을 만들지 않으려는 경우, WPF와 함께 C#을 사용하여 UI 레이어를 만들고 표준 C++ 논리를 DLL로 리팩터링할 수 있습니다. C++/CLI에서 상호 운용성 레이어를 만들어 C#을 네이티브 코드에 연결합니다. 또 다른 옵션은 [C++/CX](https://msdn.microsoft.com/library/windows/apps/xaml/hh699871.aspx) 또는 [C++/WinRT](https://github.com/microsoft/cppwinrt)를 사용하여 UWP 앱을 만드는 것입니다. Windows 10에서는 [Desktop App Converter](https://msdn.microsoft.com/windows/uwp/porting/desktop-to-uwp-run-desktop-app-converter)를 사용하여 코드를 수정하지 않고도 기존 데스크톱 애플리케이션을 UWP 앱으로 패키징할 수 있습니다.

또는 이제 새로운 요구 사항이 있거나, Windows Phone 또는 Android 디바이스와 같은 Windows 데스크톱 이외의 플랫폼을 대상으로 지정해야 할 필요성을 예상할 수 있습니다. 사용자 인터페이스 코드를 플랫폼 간 UI 라이브러리로 포팅할 수 있습니다. 이러한 UI 프레임워크를 사용하면 여러 디바이스를 대상으로 지정하고 여전히 Visual Studio 및 Visual Studio 디버거를 개발 환경으로 사용할 수 있습니다.

## <a name="related-topics"></a>관련 항목

|제목|설명|
|-----------|-----------------|
|[이전 버전의 Visual C++에서 프로젝트 업그레이드](upgrading-projects-from-earlier-versions-of-visual-cpp.md)|이전 버전의 Visual Studio에서 만든 프로젝트를 사용하는 방법을 설명합니다.|
|[Visual Studio에서 C++ 컴파일러의 새로운 기능](../overview/what-s-new-for-visual-cpp-in-visual-studio.md)|IDE 및 도구를 현재 버전의 Visual Studio로 변경|
|[Visual Studio의 C++ 규칙 향상](../overview/cpp-conformance-improvements.md)|Visual Studio 2015에서 Visual Studio로 표준 준수 향상|
|[Visual C++ 변경 기록 2003 - 2015](visual-cpp-change-history-2003-2015.md)|코드 변경이 필요할 수 있는 Visual Studio 2003과 2015 간 Visual C++ 라이브러리 및 빌드 도구의 모든 변경 내용 목록입니다.|
|[Visual C++ 2003 ~ 2015의 새로운 기능](visual-cpp-what-s-new-2003-through-2015.md)|Visual Studio 2003과 Visual Studio 2015 간의 Visual C++에 대한 모든 "새로운 기능" 정보입니다.|
|[타사 라이브러리 포팅](porting-third-party-libraries.md)|**vcpkg** 명령줄 도구를 사용하여 이전 오픈 소스 라이브러리를 최신 Visual C++ 도구 집합으로 컴파일된 버전으로 포팅하는 방법입니다.|
|[이식 및 업그레이드: 예제 및 사례 연구](porting-and-upgrading-examples-and-case-studies.md)|이 섹션에서는 여러 가지 샘플 및 애플리케이션을 포팅 및 업그레이드하고 경험과 결과를 설명했습니다. 이러한 내용을 읽으면 포팅 및 업그레이드 프로세스와 관련된 사항을 이해하는 데 도움이 될 수 있습니다. 프로세스 전반에 걸쳐 업그레이드를 위한 팁과 트릭을 설명하고 특정 오류를 수정한 방법을 보여 줍니다.|
|[유니버설 Windows 플랫폼으로 포팅](porting-to-the-universal-windows-platform-cpp.md)|Windows 10으로 코드를 이식하는 방법에 대한 정보를 포함합니다.|
|[UNIX 사용자를 위한 Visual C++ 소개](introduction-to-visual-cpp-for-unix-users.md)|Visual C++를 처음 사용하며 생산성을 높이려는 UNIX 사용자에게 정보를 제공합니다.|
|[UNIX에서 Win32로 포팅](porting-from-unix-to-win32.md)|UNIX 애플리케이션을 Windows로 마이그레이션하는 옵션을 설명합니다.|

## <a name="see-also"></a>참고 항목

[Visual Studio의 C++](../overview/visual-cpp-in-visual-studio.md)
