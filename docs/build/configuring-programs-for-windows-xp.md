---
title: Windows XP용 프로그램 구성
ms.date: 05/16/2019
ms.assetid: 1e4487b3-d815-4123-878b-5718b22f0fd5
ms.openlocfilehash: 6c94c6a66d0f22b8707012856a65df4b19965acb
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837133"
---
# <a name="configuring-programs-for-windows-xp"></a>Windows XP용 프로그램 구성

Visual Studio는 여러 플랫폼 도구 집합을 지원하므로 기본 도구 집합에서 지원하지 않는 운영 체제 및 런타임 라이브러리를 대상으로 지정할 수 있습니다. 예를 들어 플랫폼 도구 집합을 전환하면 Visual Studio의 MSVC 컴파일러에서 지원하는 향상된 C++11, C++14 및 C++17 언어를 사용하여 Windows XP 및 Windows Server 2003을 대상으로 하는 앱을 만들 수 있습니다. 또한 이전 플랫폼 도구 집합을 사용하여 이진 호환 레거시 코드를 유지하면서도 Visual Studio IDE의 최신 기능을 활용할 수 있습니다.

Visual Studio 2019 이상부터는 v142 도구 집합을 사용한 Windows XP 코드 만들기를 지원하지 않습니다. Visual Studio 2017에서 제공되는 v141 도구 집합을 사용한 Windows XP 개발 지원은 Visual Studio 설치 관리자에서 선택적 구성 요소로 사용할 수 있습니다.

## <a name="install-the-windows-xp-platform-toolset"></a>Windows XP 플랫폼 도구 집합 설치

Visual Studio 2017에서 Windows XP 및 Windows Server 2003을 대상으로 하는 플랫폼 도구 집합과 구성 요소를 얻으려면 Visual Studio 설치 관리자를 실행합니다. Visual Studio를 처음 설치할 때 또는 기존 설치를 수정하기 위해 **수정**을 선택할 때 **C++를 사용한 데스크톱 개발** 워크로드를 선택해야 합니다. 이 워크로드에 대한 선택적 구성 요소 목록에서 **C++용 Windows XP 지원**을 선택한 다음, **설치** 또는 **수정**을 선택합니다.

## <a name="windows-xp-targeting-experience"></a>Windows XP 대상 환경

Visual Studio에 포함되어 있는 Windows XP 플랫폼 도구 집합은 Windows 7 SDK의 한 버전이지만 최신 C++ 컴파일러를 사용합니다. 또한 프로젝트 속성을 적합한 기본값(예: 하위 수준 대상 지정을 위한 호환 링커의 사양)으로 구성합니다. Windows XP 플랫폼 도구 집합을 사용하여 만든 Windows 데스크톱 앱만이 Windows XP 및 Windows Server 2003에서 실행되지만, 보다 최신 운영 체제에서도 이러한 앱을 실행할 수 있습니다.

#### <a name="to-target-windows-xp"></a>Windows XP를 대상으로 지정하려면

1. **솔루션 탐색기**에서 프로젝트의 바로 가기 메뉴를 열고 **속성**을 선택합니다.

1. 프로젝트 **속성 페이지** 대화 상자의 **구성 속성** > **일반**에서 **플랫폼 도구 집합** 속성을 원하는 Windows XP 도구 집합으로 설정합니다. 예를 들어 Visual Studio 2017에서 Microsoft C++ 컴파일러를 사용하여 Windows XP 및 Windows Server 2003에 대한 코드를 작성하려면 **Visual Studio 2017 - Windows XP(v141_xp)** 를 선택합니다.

### <a name="c-runtime-support"></a>C++ 런타임 지원

Windows XP 플랫폼 도구 집합과 함께 CRT(C 런타임 라이브러리), C++ 표준 라이브러리, ATL(액티브 템플릿 라이브러리), ConCRT(동시성 런타임 라이브러리), PPL(병렬 패턴 라이브러리), MFC(Microsoft Foundation Class) 라이브러리 및 C++ AMP(C++ Accelerated Massive Programming) 라이브러리에도 Windows XP 및 Windows Server 2003에 대한 런타임 지원이 포함되어 있습니다. 이러한 운영 체제에 지원되는 최소 버전은 x86의 경우 Windows XP SP3(서비스 팩 3), x64의 경우 Windows XP SP2(서비스 팩 2)이며 Windows Server 2003 SP2(서비스 팩 2)는 x86/x64 둘 다 지원됩니다.

이러한 라이브러리는 대상에 따라 Visual Studio에서 설치하는 플랫폼 도구 집합을 통해 지원됩니다.

|라이브러리|Windows 데스크톱 앱을 대상으로 하는 기본 플랫폼 도구 집합|스토어 앱을 대상으로 하는 기본 플랫폼 도구 집합|Windows XP, Windows Server 2003을 대상으로 하는 Windows XP 플랫폼 도구 집합|
|---|---|---|---|
|CRT|X|X|X|
|C++ 표준 라이브러리|X|X|X|
|ATL|X|X|X|
|ConCRT/PPL|X|X|X|
|MFC|X||X|
|C++ AMP|X|X||

> [!NOTE]
> C++/CLI로 작성되며 .NET Framework 4를 대상으로 하는 앱은 Windows XP 및 Windows Server 2003에서 실행됩니다.

### <a name="differences-between-the-toolsets"></a>도구 집합 간의 차이점

플랫폼 및 라이브러리 지원의 차이로 인해 Windows XP 플랫폼 도구 집합을 사용하는 앱의 개발 환경은 기본 Visual Studio 플랫폼 도구 집합을 사용하는 앱처럼 완전하지 않습니다.

- **C++ 언어 기능**

   v110\_XP 플랫폼 도구 집합을 사용하는 앱은 Visual Studio 2012에서 구현된 C++ 언어 기능만 지원합니다. v120\_XP 플랫폼 도구 집합을 사용하는 앱은 Visual Studio 2013에서 구현된 C++ 언어 기능만 지원합니다. v140\_XP 플랫폼 도구 집합을 사용하는 앱은 Visual Studio 2015에서 구현된 C++ 언어 기능만 지원합니다. Visual Studio는 이전 플랫폼 도구 집합을 사용하여 빌드할 때 해당 컴파일러를 사용합니다. 해당 컴파일러 버전에서 구현된 추가 C++ 언어 기능을 활용하려면 최신 Windows XP 플랫폼 도구 집합을 사용하세요.

- **원격 디버깅**

   Visual Studio용 원격 도구는 Windows XP 또는 Windows Server 2003의 원격 디버깅을 지원하지 않습니다. Windows XP 또는 Windows Server 2003에서 실행되는 앱을 디버그하려면 이전 버전 Visual Studio의 디버거를 사용하여 로컬 또는 원격으로 앱을 디버그하면 됩니다. 이러한 디버그 환경은 플랫폼 도구 집합의 런타임 대상이지만 원격 디버깅 대상은 아닌 Windows Vista에서 앱을 디버그하는 환경과 비슷합니다.

- **정적 분석**

   Windows 7 SDK의 SAL 주석과 런타임 라이브러리가 호환되지 않으므로 Windows XP 플랫폼 도구 집합은 정적 분석을 지원하지 않습니다. Windows XP 또는 Windows Server 2003을 지원하는 앱에서 정적 분석을 수행하려면 분석을 수행할 기본 플랫폼 도구 집합을 대상으로 하도록 솔루션을 일시적으로 전환했다가 다시 Windows XP 플랫폼 집합으로 전환하여 앱을 빌드할 수 있습니다.

- **DirectX 그래픽 디버깅**

   그래픽 디버거는 Direct3D 9 API를 지원하지 않으므로 Windows XP 또는 Windows Server 2003에서 Direct3D를 사용하는 앱을 디버그하는 데 사용할 수는 없습니다. 그러나 앱이 Direrct3D 10 또는 Direct3D 11 API를 사용하는 대체 렌더러를 구현하는 경우 그래픽 디버거를 사용하여 해당 API 사용 시 발생하는 문제를 진단할 수 있습니다.

- **HLSL 빌드**

   Windows XP 도구 집합은 기본적으로 HSLS 소스 코드 파일을 컴파일하지 않습니다. HLSL 파일을 컴파일하려면 2010년 6월 DirectX SDK를 다운로드하여 설치한 다음 해당 SDK를 포함하도록 프로젝트의 VC 디렉터리를 설정합니다. 자세한 내용은 [2010년 6월 DirectX SDK 다운로드 페이지](http://www.microsoft.com/download/details.aspx?displaylang=en&id=6812)의 "DirectX SDK가 Visual Studio 2010에 포함/라이브러리 경로를 등록하지 않음" 섹션을 참조하세요.
