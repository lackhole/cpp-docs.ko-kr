---
title: Microsoft C++ 명령줄에서 도구 집합
description: Visual Studio IDE 외부의 명령줄에서 Microsoft C++ 컴파일러 도구 체인(MSVC)을 사용합니다.
ms.custom: conceptual
ms.date: 06/06/2019
helpviewer_keywords:
- command-line builds [C++]
- compiling source code [C++], command line
- builds [C++], command-line
- command line [C++], building from
- command line [C++], compilers
ms.assetid: 7ca9daed-a003-4162-842d-908f79058365
ms.openlocfilehash: b5e9bf266d79ee86cae84535641a52c7c52be391
ms.sourcegitcommit: 8adabe177d557c74566c13145196c11cef5d10d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2019
ms.locfileid: "66821142"
---
# <a name="use-the-microsoft-c-toolset-from-the-command-line"></a>Microsoft C++ 명령줄에서 도구 집합

Visual Studio에 포함 된 도구를 사용 하 여 명령줄에서 C 및 C++ 응용 프로그램을 빌드할 수 있습니다. Microsoft C++ (MSVC) 컴파일러 도구 집합에서 독립 실행형 패키지로 다운로드할 수 있는 이기도 합니다 [Visual Studio 다운로드](https://visualstudio.microsoft.com/downloads/) 페이지. 일부를 **for Visual Studio Build Tools** 패키지 있습니다. 다운로드에 필요한 도구만 선택할 수 있습니다 C++ 개발 합니다.

## <a name="how-to-use-the-command-line-tools"></a>명령줄 도구를 사용하는 방법

Visual Studio 설치 관리자에서 C++ 워크 로드 중 하나를 선택 하면 Visual Studio 설치 *플랫폼 도구 집합*합니다. 플랫폼 도구 집합에 있는 모든 C 및 C++ 특정 Visual Studio 버전에 대 한 도구입니다. 도구에는 C /C++ 컴파일러, 링커, 어셈블러, 및 기타 빌드 도구 및 일치 하는 라이브러리입니다. 명령줄에서 이러한 도구를 사용할 수 있습니다. 또한는 내부적으로 Visual Studio IDE에서. 별도 x86 호스트 및 x64 호스트 컴파일러 및 도구를 빌드하는 대상을 x86, x64, ARM, ARM64 하 고 코드. 특정 호스트 및 대상 빌드 아키텍처에 대한 각 도구 집합은 자체의 디렉터리에 저장됩니다.

올바르게 작동하려면 도구에서 몇 가지 특정 환경 변수를 설정해야 합니다. 이러한 변수는 경로 설정 하는 도구 포함 파일, 라이브러리 파일 및 SDK 위치를 추가 하려면 사용 됩니다. 이러한 환경 변수를 쉽게 설정할 수 있도록 설치 관리자에서 설치 중에 사용자 지정된 *명령 파일* 또는 배치 파일을 만듭니다. 특정 호스트 및 대상 빌드 아키텍처, Windows SDK 버전 및 플랫폼 도구 집합을 설정 하려면 이러한 명령 파일 중 하나를 실행할 수 있습니다. 편의 위해 설치 관리자 시작 메뉴에 바로 가기를 만듭니다. 바로 가기는 호스트 및 대상의 특정 조합에 대 한 이러한 명령 파일을 사용 하 여 개발자 명령 프롬프트 창을 시작 합니다. 이러한 바로 가기 필요한 환경 변수가 모두 설정 되어 사용할 준비가 확인 합니다.

필요한 환경 변수를 설치 및 빌드 아키텍처를 선택 하는 것과 다릅니다. 또한 이러한 추가 제품 업데이트 또는 업그레이드에 변경 될 수 있습니다. 때문에 설치 된 명령 프롬프트 바로 가기 또는 명령 파일을 사용 하 여 환경 변수를 설정 하는 대신 하는 것이 좋습니다. 자세한 내용은 [명령줄 빌드에 대 한 경로 및 환경 변수 설정](setting-the-path-and-environment-variables-for-command-line-builds.md)합니다.

도구 집합, 명령 파일 및 설치 하는 바로 가기를 컴퓨터 프로세서 및 설치 중에 선택한 옵션에 따라 달라 집니다. X86에 호스트 된 도구 및 x86 및 x64 코드를 작성 하는 교차 도구를 항상 설치 됩니다. 64 비트 Windows가 고 x64 호스트 도구로 x86 및 x64 코드를 작성 하는 교차 도구도 설치 됩니다. 선택적 설정 하면 C++ 유니버설 Windows 플랫폼 도구 후 ARM 및 ARM64 코드를 작성 하는 x86 및 x64 도구도 설치 합니다. 다른 워크로드에서는 추가 도구를 설치할 수 있습니다.

## <a name="developer_command_prompt_shortcuts"></a> 개발자 명령 프롬프트 바로 가기

명령 프롬프트 바로 가기는 시작 메뉴의 버전별 Visual Studio 폴더에 설치됩니다. 지원되는 기본 명령 프롬프트 바로 가기 및 빌드 아키텍처의 목록은 다음과 같습니다.

- **개발자 명령 프롬프트** - 32비트 x86 네이티브 도구를 사용하여 32비트 x86 네이티브 코드를 작성하도록 환경을 설정합니다.
- **x86 Native Tools 명령 프롬프트** - 32비트 x86 네이티브 도구를 사용하여 32비트 x86 네이티브 코드를 작성하도록 환경을 설정합니다.
- **x64 Native Tools 명령 프롬프트** - 64비트 x64 네이티브 도구를 사용하여 64비트 x64 네이티브 코드를 작성하도록 환경을 설정합니다.
- **x86_x64 Cross Tools 명령 프롬프트** - 32비트 x86 네이티브 도구를 사용하여 64비트 x64 네이티브 코드를 작성하도록 환경을 설정합니다.
- **x64_x86 Cross Tools 명령 프롬프트** - 64비트 x64 네이티브 도구를 사용하여 32비트 x86 네이티브 코드를 작성하도록 환경을 설정합니다.

::: moniker range=">= vs-2019"

시작 메뉴의 폴더 및 바로 가기 이름을 Visual Studio의 설치 된 버전에 따라 달라 집니다. 설치에도 의존 하나를 설정 하면 **애칭**합니다. 예를 들어 Visual Studio 2019를 설치 하 고의 애칭을 지정한 *최신*합니다. 개발자 명령 프롬프트 바로 가기를 라고 **VS 2019 (최신) 용 개발자 명령 프롬프트**, 라는 폴더에 **Visual Studio 2019**합니다.

::: moniker-end
::: moniker range="= vs-2017"

시작 메뉴의 폴더 및 바로 가기 이름을 Visual Studio의 설치 된 버전에 따라 달라 집니다. 설치에도 의존 하나를 설정 하면 **애칭**합니다. 예를 들어 Visual Studio 2017을 설치 하 고의 애칭을 지정한 *최신*합니다. 개발자 명령 프롬프트 바로 가기를 라고 **(최신) VS 2017 용 개발자 명령 프롬프트**, 라는 폴더에 **Visual Studio 2017**합니다.

::: moniker-end
::: moniker range="< vs-2017"

시작 메뉴의 폴더 및 바로 가기 이름을 Visual Studio의 설치 된 버전에 따라 달라 집니다. 예를 들어, Visual Studio 2015를 설치 합니다. 개발자 명령 프롬프트 바로 가기를 라고 **VS 2015 용 개발자 명령 프롬프트**합니다.

::: moniker-end

## <a name="developer_command_prompt"></a> 개발자 명령 프롬프트 창 열기

1. 바탕 화면에서 Windows **시작** 메뉴를 연 다음, 스크롤하여 Visual Studio 버전에 맞는 폴더(예: **Visual Studio 2019**)를 찾아 엽니다.

1. 폴더에서 Visual Studio 버전에 맞는 **개발자 명령 프롬프트**를 선택합니다. 이 바로 가기는 32비트 x86 네이티브 도구의 기본 빌드 아키텍처를 사용하여 32비트 x86 네이티브 코드를 작성하는 개발자 명령 프롬프트 창을 시작합니다. 기본이 아닌 빌드 아키텍처를 원하는 경우 네이티브 또는 크로스 도구 명령 프롬프트 중 하나를 선택하여 호스트 및 대상 아키텍처를 지정합니다.

빨리 하려면 개발자 명령 프롬프트를 열고를 입력 *개발자 명령 프롬프트* 데스크톱 검색 상자에 있습니다. 원하는 결과 선택 합니다.

## <a name="developer_command_file_locations"></a> 개발자 명령 파일 위치

기존 명령 프롬프트 창에서 빌드 환경을 설정 하려는 경우 설치 관리자가 만든 명령 파일 중 하나를 사용할 수 있습니다. 새 명령 프롬프트 창에서 환경을 설정 하는 것이 좋습니다. 동일한 명령 창에서 이후 스위치 환경 권장 하지 않습니다.

::: moniker range=">= vs-2019"

명령 파일 위치에 설치한 Visual Studio의 버전에 설치 하는 동안 선택한 사항에 따라 달라 집니다. Visual Studio 2019에 대 한 64 비트 시스템에서 일반적인 설치 위치에는 \\프로그램 파일 (x86)\\Microsoft Visual Studio\\2019\\*edition*합니다. *Edition* Community, Professional, Enterprise, BuildTools, 또는 사용자가 제공한 다른 애칭 수 있습니다.

::: moniker-end
::: moniker range="= vs-2017"

명령 파일 위치에 설치한 Visual Studio의 버전에 설치 하는 동안 선택한 사항에 따라 달라 집니다. Visual Studio 2017 용 64 비트 시스템에서 일반적인 설치 위치에는 \\프로그램 파일 (x86)\\Microsoft Visual Studio\\2017\\*edition*합니다. *Edition* Community, Professional, Enterprise, BuildTools, 또는 사용자가 제공한 다른 애칭 수 있습니다.

::: moniker-end
::: moniker range="< vs-2017"

Visual Studio 버전 및 설치 디렉터리에서 명령 파일 위치에 따라 달라 집니다. Visual Studio 2015에 대 한 일반적인 설치 위치에는 \\프로그램 파일 (x86)\\Microsoft Visual Studio 14.0입니다.

::: moniker-end

VsDevCmd.bat를 주 개발자 명령 프롬프트 명령 파일의 Common7에 위치한\\도구 하위 디렉터리입니다. 32 비트 x86 빌드를 x86 네이티브 도구를 사용 하도록 환경을 설정 매개 변수 없이 지정 되 면 코드입니다.

::: moniker range=">= vs-2017"

자세한 명령 파일 특정 빌드 아키텍처를 설정할 수 있습니다. 명령 파일을 사용할 수 있는 옵션을 설치한 다음 Visual Studio 워크 로드에 따라 달라 집니다. Visual Studio 2017 및 Visual Studio 2019 것을 찾을 수에서 VC\\보조\\하위 디렉터리를 작성 합니다.

::: moniker-end
::: moniker range="< vs-2017"

자세한 명령 파일 특정 빌드 아키텍처를 설정할 수 있습니다. 명령 파일을 사용할 수 있는 옵션을 설치한 다음 Visual Studio 워크 로드에 따라 달라 집니다. VC, VC에에서 거주 하는 Visual Studio 2015에서\\bin 또는 VC\\bin\\*아키텍처* 하위 디렉터리 위치 *아키텍처* 네이티브 중 하나인 또는 크로스 컴파일러 옵션입니다.

::: moniker-end

이러한 명령 파일은 기본 매개 변수를 설정하고 VsDevCmd.bat를 호출하여 지정된 빌드 아키텍처 환경을 설정합니다. 일반적인 설치에 포함될 수 있는 명령 파일은 다음과 같습니다.

|명령 파일|호스트 및 대상 아키텍처|
|---|---|
|**vcvars32.bat**| 32비트 x86 네이티브 도구를 사용하여 32비트 x86 코드를 작성합니다.|
|**vcvars64.bat**| 64비트 x64 네이티브 도구를 사용하여 64비트 x64 코드를 작성합니다.|
|**vcvarsx86_amd64.bat**| 32비트 x86 네이티브 크로스 도구를 사용하여 64비트 x64 코드를 작성합니다.|
|**vcvarsamd64_x86.bat**| 64비트 x64 네이티브 크로스 도구를 사용하여 32비트 x86 코드를 작성합니다.|
|**vcvarsx86_arm.bat**| 32비트 x86 네이티브 크로스 도구를 사용하여 ARM 코드를 작성합니다.|
|**vcvarsamd64_arm.bat**| 64비트 x64 네이티브 크로스 도구를 사용하여 ARM 코드를 작성합니다.|
|**vcvarsall.bat**| 호스트 및 대상 아키텍처, Windows SDK 및 플랫폼을 선택할 수를 지정 하려면 매개 변수를 사용 합니다. 지원되는 옵션 목록을 보려면 **/help** 매개 변수를 사용하여 호출합니다.|

> [!CAUTION]
> vcvarsall.bat 파일 및 다른 Visual Studio 명령 파일은 컴퓨터마다 다를 수 있습니다. 누락되거나 손상된 vcvarsall.bat 파일을 다른 컴퓨터의 파일로 바꾸지 마세요. Visual Studio 설치 관리자를 다시 실행하여 누락된 파일을 대체합니다.
>
> 또한 vcvarsall.bat 파일은 버전별로 다릅니다. 현재 버전의 Visual Studio가 이전 버전의 Visual Studio도 있는 컴퓨터에 설치되어 있는 경우 동일한 버전의 명령 프롬프트 창에서 다른 버전의 vcvarsall.bat 또는 다른 Visual Studio 명령 파일을 실행하지 마세요.

## <a name="use-the-developer-tools-in-an-existing-command-window"></a>기존 명령 창에서 개발자 도구 사용

기존 명령 창에서 특정 빌드 아키텍처를 지정하는 가장 간단한 방법은 vcvarsall.bat 파일을 사용하는 것입니다. Vcvarsall.bat를 사용 하 여 네이티브 32 비트 또는 64 비트 컴파일 명령줄을 구성 하려면 환경 변수를 설정 합니다. X86, x64, ARM, 크로스 컴파일을 지정할 인수 수 또는 ARM64 프로세서. Microsoft Store, 유니버설 Windows 플랫폼 또는 Windows 데스크톱 플랫폼을 대상 지정할 수 있습니다. 도 사용 하는 Windows SDK를 지정 하 고 플랫폼 도구 집합 버전을 선택할 수 있습니다.

인수 없이 사용할 vcvarsall.bat 32 비트 Windows Desktop 대상에 대 한 현재 x86 네이티브 컴파일러를 사용 하려면 환경 변수를 구성 합니다. 네이티브 또는 크로스 컴파일러 도구를 사용 하도록 환경을 구성 하기 위한 인수를 추가할 수 있습니다. vcvarsall.bat 설치 되지 않은 구성을 지정 하는 경우 오류 메시지를 표시 하거나 컴퓨터에서 사용할 수 있습니다.

### <a name="vcvarsall-syntax"></a>vcvarsall 구문

> **vcvarsall.bat** [*architecture*] [*platform_type*] [*winsdk_version*] [ **-vcvars_ver=** _vcversion_]

*architecture*<br/>
이 선택적 인수는 사용할 호스트 및 대상 아키텍처를 지정합니다. 하는 경우 *아키텍처* 지정 하지 않으면 기본 빌드 환경이 사용 됩니다. 지원되는 인수는 다음과 같습니다.

|*architecture*|컴파일러|호스트 컴퓨터 아키텍처|빌드 출력(대상) 아키텍처|
|----------------------------|--------------|----------------------------------|-------------------------------|
|**x86**|x86 32비트 네이티브|x86, x64|x86|
|**x86\_amd64** 또는 **x86\_x64**|x64 크로스에서 x86|x86, x64|X64|
|**x86_arm**|x86용 ARM 크로스|x86, x64|ARM|
|**x86_arm64**|ARM64 크로스에서 x86|x86, x64|ARM64|
|**amd64** 또는 **x64**|x64 64비트 네이티브|X64|X64|
|**amd64\_x86** 또는 **x64\_x86**|x86 크로스에서 x64|X64|x86|
|**amd64\_arm** 또는 **x64\_arm**|ARM 크로스에서 x64|X64|ARM|
|**amd64\_arm64** 또는 **x64\_arm64**|ARM64 크로스에서 x64|X64|ARM64|

*platform_type*<br/>
이 선택적 인수를 사용하면 **store** 또는 **uwp**를 플랫폼 유형으로 지정할 수 있습니다. 기본적으로 환경은 데스크톱 또는 콘솔 앱을 빌드하도록 설정됩니다.

*winsdk_version*<br/>
필요에 따라 사용할 Windows SDK 버전을 지정합니다. 기본적으로 설치된 최신 Windows SDK가 사용됩니다. Windows SDK 버전을 지정하려면 **10.0.10240.0**과 같은 Windows 10 SDK 버전 번호 전체를 사용하거나, Windows 8.1 SDK를 사용하도록 **8.1**을 지정할 수 있습니다.

*vcversion*<br/>
필요에 따라 사용할 Visual Studio 컴파일러 도구 집합을 지정합니다. 기본적으로 현재 Visual Studio 컴파일러 도구 집합을 사용하도록 환경이 설정됩니다.

::: moniker range=">= vs-2019"

사용 하 여 **-vcvars_ver 14.2 =.yyyyy x** Visual Studio 2019 컴파일러 도구 집합의 특정 버전을 지정 합니다.

사용 하 여 **-vcvars_ver 14.16 =** 컴파일러 도구 집합을 Visual Studio 2017의 최신 버전을 지정할 수 있습니다.

::: moniker-end
::: moniker range="= vs-2017"

사용 하 여 **-vcvars_ver 14.16 =** 컴파일러 도구 집합을 Visual Studio 2017의 최신 버전을 지정할 수 있습니다.

사용 하 여 **-vcvars_ver 14.1 =.yyyyy x** Visual Studio 2017 컴파일러 도구 집합의 특정 버전을 지정 합니다.

::: moniker-end

사용 하 여 **-vcvars_ver 14.0 =** 는 Visual Studio 2015 컴파일러 도구 집합을 지정 합니다.

<a name="vcvarsall"></a>
#### <a name="to-set-up-the-build-environment-in-an-existing-command-prompt-window"></a>기존 명령 프롬프트 창에서 빌드 환경을 설정하려면

1. 명령 프롬프트에서 CD 명령을 사용하여 Visual Studio 설치 디렉터리로 변경합니다. 그런 다음, CD를 다시 사용하여 구성별 명령 파일이 있는 하위 디렉터리로 변경합니다. Visual Studio 2019로 Visual Studio 2017을 사용 하는 *VC\\보조\\빌드* 하위 디렉터리입니다. Visual Studio 2015를 사용 합니다 *VC* 하위 디렉터리입니다.

1. 기본 개발자 환경에 대한 명령을 입력합니다. 예를 들어, 64 비트 플랫폼에서 최신 Windows SDK 및 Visual Studio 컴파일러 도구 집합을 사용 하 여 UWP 용 ARM 코드를 작성 하려면이 명령줄을 사용 합니다.

   `vcvarsall.bat amd64_arm uwp`

## <a name="create-your-own-command-prompt-shortcut"></a>사용자 고유의 명령 프롬프트 바로 가기 만들기

::: moniker range=">= vs-2019"

개발자 명령 프롬프트 바로 가기 보려면 사용 하는 명령 대상에 대 한 속성 대화 상자를 엽니다. 예를 들어 **VS 2019용 x64 Native Tools 명령 프롬프트** 바로 가기의 대상은 다음과 비슷합니다.

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\VC\Auxiliary\Build\vcvars64.bat"`

::: moniker-end
::: moniker range="= vs-2017"

개발자 명령 프롬프트 바로 가기 보려면 사용 하는 명령 대상에 대 한 속성 대화 상자를 엽니다. 예를 들어 대상 합니다 **x64 VS 2017 용 네이티브 도구 명령 프롬프트** 바로 가기는 비슷한:

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Auxiliary\Build\vcvars64.bat"`

::: moniker-end
::: moniker range="< vs-2017"

개발자 명령 프롬프트 바로 가기 보려면 사용 하는 명령 대상에 대 한 속성 대화 상자를 엽니다. 예를 들어 대상 합니다 **VS2015 x64 Native Tools 명령 프롬프트** 바로 가기는 비슷한:

`%comspec% /k ""C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\vcvarsall.bat"" amd64`

::: moniker-end

아키텍처별 배치 파일은 *architecture* 매개 변수를 설정하고 vcvarsall.bat를 호출합니다. Vcvarsall.bat를를 전달 하거나 vcvarsall.bat를 직접 호출 하기만 하면 이러한 일괄 처리 파일에 동일한 옵션을 전달할 수 있습니다. 사용자 고유의 명령 바로 가기에 대한 매개 변수를 지정하려면 명령의 끝에 큰따옴표로 추가합니다. 예를 들어, 여기에 64 비트 플랫폼에서 최신 Windows SDK를 사용 하 여 UWP 용 ARM 코드를 작성 하는 바로 가기입니다. 이전 컴파일러 도구 집합을 사용 하려면 버전 번호를 지정 합니다. 바로 가기에서 다음 명령 대상과 같은 항목을 사용합니다.

::: moniker range=">= vs-2019"

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\VC\Auxiliary\Build\vcvarsall.bat amd64_arm uwp -vcvars_ver=14.16"`

::: moniker-end
::: moniker range="= vs-2017"

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Auxiliary\Build\vcvarsall.bat amd64_arm uwp -vcvars_ver=14.0"`

::: moniker-end
::: moniker range="< vs-2017"

`%comspec% /k ""C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\vcvarsall.bat"" amd64 -vcvars_ver=12.0`

::: moniker-end

Visual Studio 설치 디렉터리를 반영 하도록 경로 조정 합니다. vcvarsall.bat 파일에는 특정 버전 번호에 대한 추가 정보가 있습니다.

## <a name="command-line-tools"></a>명령줄 도구

빌드하는 C /C++ Visual Studio 명령 프롬프트에서 프로젝트에서는 이러한 명령줄 도구를 제공 합니다.

[CL](reference/compiling-a-c-cpp-program.md)<br/>
컴파일러(cl.exe)를 사용하여 소스 코드 파일을 컴파일한 다음 앱, 라이브러리 및 DLL에 연결합니다.

[링크](reference/linking.md)<br/>
링커(link.exe)를 사용하여 컴파일된 개체 파일 및 라이브러리를 앱 및 DLL에 연결합니다.

[MSBuild](msbuild-visual-cpp.md)<br/>
MSBuild(msbuild.exe) 및 프로젝트 파일(.vcxproj)을 사용하여 빌드를 구성하고 도구 집합을 간접적으로 호출합니다. 실행 한 것과 동일 합니다 **빌드** 프로젝트 또는 **솔루션 빌드** Visual Studio IDE에 명령 합니다. 명령줄에서 MSBuild를 실행 합니다. 고급 시나리오 이며 주로 것이 좋습니다.

[DEVENV](/visualstudio/ide/reference/devenv-command-line-switches)<br/>
명령줄 스위치와 함께 DEVENV (devenv.exe)를 사용 하 여 같은 결합 **/빌드** 또는 **정리/** 명령을 Visual Studio IDE를 표시 하지 않고 작성 특정 실행 합니다. 일반적으로 DEVENV 이므로 기본 MSBuild를 직접 사용 하 여 Visual Studio MSBuild의 복잡성을 처리 하도록 할 수 있습니다.

[NMAKE](reference/nmake-reference.md)<br/>
기존 메이크파일을 기반으로 하여 C++ 프로젝트를 빌드하려면 Windows에서 NMAKE(nmake.exe)를 사용합니다.

명령줄에서 빌드할 때 F1 명령 도움말을 즉시 사용할 수 없습니다. 대신 검색 엔진을 사용하여 경고, 오류 및 메시지에 대한 정보를 얻거나 오프라인 도움말 파일을 사용할 수 있습니다. 검색을 사용 하도록 [docs.microsoft.com](https://docs.microsoft.com/cpp/), 페이지의 맨 위에 있는 검색 상자를 사용 합니다.

## <a name="in-this-section"></a>섹션 내용

이러한 문서에서 명령 줄에서 앱을 빌드하는 방법을 보여 줍니다 및 명령줄 빌드 환경을 사용자 지정 하는 방법에 설명 합니다. 64 비트 도구 집합을 사용 하 여 x86, x64, ARM 대상으로 하는 방법을 보여 줍니다 일부 및 ARM64 플랫폼입니다. 또한 명령줄 빌드 도구인 MSBuild 및 NMAKE 사용에 대해서도 설명 합니다.

[연습: 명령줄에서 네이티브 C++ 프로그램 컴파일](walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)<br/>
만들고 컴파일하는 방법을 보여 주는 예제를 제공 된 C++ 명령줄에서 프로그램입니다.

[연습: 명령줄에서 C 프로그램 컴파일](walkthrough-compile-a-c-program-on-the-command-line.md)<br/>
C 프로그래밍 언어로 작성한 프로그램을 컴파일하는 방법에 대해 설명합니다.

[연습: 명령줄에서 C++/CLI 프로그램 컴파일](walkthrough-compiling-a-cpp-cli-program-on-the-command-line.md)<br/>
.NET Framework를 사용하는 C++/CLI 프로그램을 만들어 컴파일하는 방법에 대해 설명합니다.

[연습: 명령줄에서 C++/CX 프로그램 컴파일](walkthrough-compiling-a-cpp-cx-program-on-the-command-line.md)<br/>
Windows 런타임을 사용하는 C++/CX 프로그램을 만들어 컴파일하는 방법에 대해 설명합니다.

[명령줄 빌드에 맞는 경로 및 환경 변수 설정](setting-the-path-and-environment-variables-for-command-line-builds.md)<br/>
대상 x86, x64, ARM, 32 비트 또는 64 비트 도구 집합을 사용 하도록 환경 변수를 설정 하는 방법 및 ARM64 플랫폼입니다.

[NMAKE 참조](reference/nmake-reference.md)<br/>
Microsoft Program Maintenance Utility(NMAKE.EXE)에 대해 설명하는 문서의 링크를 제공합니다.

[명령줄에서 MSBuild 사용 - C++](msbuild-visual-cpp.md)<br/>
명령줄에서 msbuild.exe를 사용하는 방법을 설명하는 문서에 대한 링크를 제공합니다.

## <a name="related-sections"></a>관련 단원

[/MD, /MT, /LD(런타임 라이브러리 사용)](reference/md-mt-ld-use-run-time-library.md)<br/>
컴파일러 옵션을 사용하여 디버그 또는 릴리스 런타임 라이브러리를 사용하는 방법에 대해 설명합니다.

[C/C++ 컴파일러 옵션](reference/compiler-options.md)<br/>
C 및 C++ 컴파일러 옵션과 CL.exe에 대해 설명하는 문서에 대한 링크를 제공합니다.

[MSVC 링커 옵션](reference/linker-options.md)<br/>
링커 옵션 및 LINK.exe에 대해 설명하는 문서에 대한 링크를 제공합니다.

[추가 MSVC 빌드 도구](reference/c-cpp-build-tools.md)<br/>
Visual Studio에 포함된 C/C++ 빌드 도구에 대한 링크를 제공합니다.

## <a name="see-also"></a>참고자료

[프로젝트 및 빌드 시스템](projects-and-build-systems-cpp.md)
