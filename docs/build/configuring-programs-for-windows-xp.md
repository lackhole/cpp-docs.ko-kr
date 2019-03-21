---
title: Windows XP 용 프로그램 구성
ms.date: 02/02/2018
ms.assetid: 1e4487b3-d815-4123-878b-5718b22f0fd5
ms.openlocfilehash: 989a4e2c7e91c05498902bf1c5cb9d838ee47c3b
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57814295"
---
# <a name="configuring-programs-for-windows-xp"></a>Windows XP 용 프로그램 구성

Visual Studio에서는 여러 플랫폼 도구 집합을 지원 하므로 운영 체제 및 런타임 라이브러리 기본 도구 집합에서 지원 되지 않는 대상 수 있습니다. 예를 들어, 플랫폼 도구 집합을 전환 하 여 사용할 수 있습니다 c++11, c++14 및 Visual Studio의 MSVC 컴파일러에서 지원 되는 C + + 17 개의 언어 향상 된 Windows XP 및 Windows Server 2003을 대상으로 하는 앱을 만듭니다. 또한 이전 플랫폼 도구 집합을 사용 하 여 이진 호환 레거시 코드를 유지 하 고 여전히 Visual Studio IDE의 최신 기능을 활용 하기 위해 수 있습니다.

## <a name="install-the-windows-xp-platform-toolset"></a>Windows XP 플랫폼 도구 집합 설치

Visual Studio 2017에서 플랫폼 도구 집합 및 대상 Windows XP 및 Windows Server 2003 구성 요소를 가져오려면 Visual Studio 설치 관리자를 실행 합니다. Visual Studio를 처음 설치할 때 또는 선택 하면 **수정** 기존 설치를 수정 하려면 합니다 **C++를 사용한 데스크톱 개발** 워크 로드가 선택 합니다. 이 워크 로드에 대 한 선택적 구성 요소 목록에서 선택 **C++ 용 Windows XP 지원**를 선택한 후 **설치** 하거나 **수정**합니다.

## <a name="windows-xp-targeting-experience"></a>Windows XP 대상 환경

Visual Studio에 포함 된 Windows XP 플랫폼 도구 집합을 사용 하면 Windows 7 SDK의 버전이 있지만 현재 C++ 컴파일러를 사용 합니다. 또한 프로젝트 속성을 적절 한 기본 값, 예를 들어, 하위 수준 대상 지정을 위한 호환 링커의 사양으로 구성합니다. 또한 Windows 데스크톱 앱만 실행 Windows XP 및 Windows Server 2003, Windows XP 플랫폼 도구 집합을 사용 하 여 만든 하지만 해당 앱이 최신 Windows 운영 체제에서 실행할 수 있습니다.

#### <a name="to-target-windows-xp"></a>Windows XP를 대상으로 지정하려면

1. **솔루션 탐색기**에서 프로젝트의 바로 가기 메뉴를 열고 **속성**을 선택합니다.

1. 에 **속성 페이지** 대화 상자의 프로젝트에 대 한 **구성 속성** > **일반**설정의 **플랫폼 도구 집합** 속성을 원하는 Windows XP 도구 집합입니다. 예를 들어 선택할 **Visual Studio 2017-Windows XP (v141_xp)** Microsoft Visual C++ 2017 컴파일러를 사용 하 여 Windows XP 및 Windows Server 2003에 대 한 코드를 만듭니다.

### <a name="c-runtime-support"></a>C++ 런타임 지원

Windows XP 플랫폼 도구 집합, C 런타임 라이브러리 (CRT), C++ 표준 라이브러리, ATL 액티브 템플릿 라이브러리 (), 동시성 런타임 (ConCRT) 라이브러리, 라이브러리 PPL (병렬 패턴), Microsoft Foundation 클래스 라이브러리 (MFC) 및 C++ AMP (C++와 함께 대규모 프로그래밍 accelerated) 라이브러리에 Windows XP 및 Windows Server 2003에 대 한 런타임 지원이 포함 되어 있습니다. 이러한 운영 체제에 대 한 지원 되는 최소 버전은 Windows XP 서비스 팩 3(sp3) x86, Windows XP 서비스 팩 2(sp2), x64 및 x86 및 x64)에 대 한 Windows Server 2003 서비스 팩 2 (SP2).

이러한 라이브러리는 대상에 따라 Visual Studio가 설치 된 플랫폼 도구 집합에서 지원 됩니다.

|라이브러리|Windows 데스크톱 앱을 대상으로 하는 기본 플랫폼 도구 집합|기본 플랫폼 도구 집합 타기 팅 스토어 앱|Windows XP, Windows Server 2003을 대상으로 하는 Windows XP 플랫폼 도구 집합|
|---|---|---|---|
|CRT|X|X|X|
|C++ 표준 라이브러리|X|X|X|
|ATL|X|X|X|
|ConCRT/PPL|X|X|X|
|MFC|X||X|
|C++ AMP|X|X||

> [!NOTE]
> 작성 응용 프로그램은 C++ /cli CLI 및.NET Framework 4를 대상 Windows XP 및 Windows Server 2003에서 실행 합니다.

### <a name="differences-between-the-toolsets"></a>도구 집합 간의 차이점

플랫폼 및 라이브러리 지원의 차이로 인해 Windows XP 플랫폼 도구 집합을 사용 하는 앱에 대 한 개발 환경을 기본 Visual Studio 플랫폼 도구 집합을 사용 하는 앱 처럼 완전 하지 않습니다.

- **C++ 언어 기능**

   C++ 언어 기능만 Visual Studio 2012에서 구현 되는 v110를 사용 하는 앱에서 지\_xp 플랫폼 도구 집합입니다. C++ 언어 기능만 Visual Studio 2013에서 구현 되는 v120을 사용 하는 앱에서 지\_xp 플랫폼 도구 집합입니다. C++ 언어 기능만 Visual Studio 2015에서 구현 된 v140을 사용 하는 앱에서 지\_xp 플랫폼 도구 집합입니다. Visual Studio는 이전 플랫폼 도구 집합을 사용 하 여 빌드할 때 해당 컴파일러를 사용 합니다. 해당 버전의 컴파일러에서 구현 되는 추가 C++ 언어 기능을 활용 하려면 최신 Windows XP 플랫폼 도구 집합을 사용 합니다.

- **원격 디버깅**

   Visual Studio 용 원격 도구는 Windows XP 또는 Windows Server 2003에서 원격 디버깅을 지원 하지 않습니다. Windows XP 또는 Windows Server 2003에서 실행 되는 경우 앱을 디버그, 로컬 또는 원격으로 디버그 하는 이전 버전의 Visual Studio에서 디버거를 사용할 수 있습니다. 이러한 디버그 환경은 플랫폼 도구 집합의 런타임 대상이지만 원격 디버깅 대상은 아닌 Windows Vista에서 앱을 디버그하는 환경과 비슷합니다.

- **정적 분석**

   Windows 7 SDK 및 런타임 라이브러리의 SAL 주석과 호환 되지 않으므로 Windows XP 플랫폼 도구 집합 정적 분석을 지원 하지 않습니다. 분석을 수행 하려면 기본 플랫폼 도구 집합을 대상으로 솔루션을 일시적으로 전환 하 고 빌드하려면 Windows XP 플랫폼 도구 집합으로 다시 전환할 수 있습니다 Windows XP 또는 Windows Server 2003을 지 원하는 앱에서 정적 분석을 수행 하려는 경우 앱입니다.

- **DirectX 그래픽 디버깅**

   그래픽 디버거는 Direct3D 9 API를 지원 하지 않으므로, Windows XP 또는 Windows Server 2003에서 Direct3D를 사용 하는 앱을 디버깅 하려면 사용할 수 없습니다. 그러나 앱이 Direrct3D 10 또는 Direct3D 11 API를 사용하는 대체 렌더러를 구현하는 경우 그래픽 디버거를 사용하여 해당 API 사용 시 발생하는 문제를 진단할 수 있습니다.

- **HLSL 빌드**

   Windows XP 도구 집합은 기본적으로 HSLS 소스 코드 파일을 컴파일하지 않습니다. HLSL 파일을 컴파일하려면 2010년 6월 DirectX SDK를 다운로드하여 설치한 다음 해당 SDK를 포함하도록 프로젝트의 VC 디렉터리를 설정합니다. 자세한 내용은 참조 하세요.를 "DirectX SDK를 등록 하지 않습니다 Visual Studio 2010을 사용 하 여 포함/라이브러리 경로" 섹션을 [2010 년 6 월 DirectX SDK 다운로드 페이지](http://www.microsoft.com/download/details.aspx?displaylang=en&id=6812)합니다.
