---
title: 명령줄에서 MSVC 도구 집합 사용 - Visual Studio
description: Visual Studio IDE 외부의 명령줄에서 Microsoft C++ 컴파일러 도구 체인(MSVC)을 사용합니다.
ms.custom: conceptual
ms.date: 05/16/2019
helpviewer_keywords:
- command-line builds [C++]
- compiling source code [C++], command line
- builds [C++], command-line
- command line [C++], building from
- command line [C++], compilers
ms.assetid: 7ca9daed-a003-4162-842d-908f79058365
ms.openlocfilehash: 97626455ace0d3ad47b9011594e82c144d7ea27d
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837124"
---
# <a name="use-the-msvc-toolset-from-the-command-line"></a>명령줄에서 MSVC 도구 집합 사용

Visual Studio에 포함된 도구를 사용하여 명령줄에서 C 및 C++ 애플리케이션을 빌드할 수 있습니다. 또한 [Visual Studio 다운로드](https://visualstudio.microsoft.com/downloads/) 페이지에서 컴파일러 도구 집합을 독립 실행형 패키지로 다운로드할 수도 있습니다. **Build Tools for Visual Studio** 패키지의 일부입니다. C++ 개발에 필요한 도구만 다운로드하도록 선택할 수 있습니다.

## <a name="how-to-use-the-command-line-tools"></a>명령줄 도구를 사용하는 방법

Visual Studio 설치 관리자에서 C++ 워크로드 중 하나를 선택하면 Visual Studio *플랫폼 도구 집합*이 설치됩니다. 플랫폼 도구 집합에는 C/C++ 컴파일러, 링커, 컴파일러 및 기타 빌드 도구뿐만 아니라 일치하는 라이브러리를 포함하여 특정 Visual Studio 버전용 모든 C 및 C++ 도구가 있습니다. 이러한 모든 도구는 명령줄에서 사용할 수 있으며, Visual Studio IDE에서도 내부적으로 사용됩니다. x86, x64, ARM 및 ARM64 대상에 대한 코드를 작성하는 별도의 x86 호스팅 및 x64 호스팅 컴파일러와 도구가 있습니다. 특정 호스트 및 대상 빌드 아키텍처에 대한 각 도구 집합은 자체의 디렉터리에 저장됩니다.

설치되는 컴파일러 도구 집합은 컴퓨터 프로세서와 설치 중에 선택한 옵션에 따라 달라집니다. 최소한 32비트 x86 네이티브 코드를 작성하는 32비트 x86 호스팅 도구 및 64비트 x64 네이티브 코드를 작성하는 크로스 도구가 설치됩니다. 64비트 Windows를 사용하는 경우 64비트 네이티브 코드를 작성하는 64비트 x64 호스팅 도구 및 32비트 네이티브 코드를 작성하는 크로스 도구도 설치됩니다. 선택적인 C++ 유니버설 Windows 플랫폼 도구를 설치하도록 선택한 경우 ARM 코드를 작성하는 32비트 및 64비트 네이티브 도구도 설치됩니다. 다른 워크로드에서는 추가 도구를 설치할 수 있습니다.

## <a name="environment-variables-and-developer-command-prompts"></a>환경 변수 및 개발자 명령 프롬프트

올바르게 작동하려면 도구에서 몇 가지 특정 환경 변수를 설정해야 합니다. 이러한 환경 변수는 경로에 추가하고 포함 파일, 라이브러리 파일 및 SDK 위치를 설정하는 데 사용됩니다. 이러한 환경 변수를 쉽게 설정할 수 있도록 설치 관리자에서 설치 중에 사용자 지정된 *명령 파일* 또는 배치 파일을 만듭니다. 명령 프롬프트 창에서 이러한 명령 파일 중 하나를 실행하여 특정 호스트 및 대상 빌드 아키텍처, Windows SDK 버전, 대상 플랫폼 및 플랫폼 도구 집합을 설정할 수 있습니다. 편의상 설치 관리자는 이러한 명령 파일을 사용하여 개발자 명령 프롬프트 창을 시작하는 바로 가기를 시작 메뉴에 만들므로 필요한 환경 변수가 모두 설정되어 사용할 준비가 됩니다.

필요한 환경 변수는 설치 및 선택한 빌드 아키텍처에 따라 다르며, 제품 업데이트 또는 업그레이드로 인해 변경될 수 있습니다. 따라서 Windows에서 환경 변수를 직접 설정하는 대신, 설치된 명령 프롬프트 바로 가기 또는 명령 파일 중 하나를 사용하는 것이 좋습니다. 자세한 내용은 [명령줄 빌드에 맞는 경로 및 환경 변수 설정](setting-the-path-and-environment-variables-for-command-line-builds.md)을 참조하세요.

## <a name="developer_command_prompt_shortcuts"></a> 개발자 명령 프롬프트 바로 가기

명령 프롬프트 바로 가기는 시작 메뉴의 버전별 Visual Studio 폴더에 설치됩니다. 지원되는 기본 명령 프롬프트 바로 가기 및 빌드 아키텍처의 목록은 다음과 같습니다.

- **개발자 명령 프롬프트** - 32비트 x86 네이티브 도구를 사용하여 32비트 x86 네이티브 코드를 작성하도록 환경을 설정합니다.
- **x86 Native Tools 명령 프롬프트** - 32비트 x86 네이티브 도구를 사용하여 32비트 x86 네이티브 코드를 작성하도록 환경을 설정합니다.
- **x64 Native Tools 명령 프롬프트** - 64비트 x64 네이티브 도구를 사용하여 64비트 x64 네이티브 코드를 작성하도록 환경을 설정합니다.
- **x86_x64 Cross Tools 명령 프롬프트** - 32비트 x86 네이티브 도구를 사용하여 64비트 x64 네이티브 코드를 작성하도록 환경을 설정합니다.
- **x64_x86 Cross Tools 명령 프롬프트** - 64비트 x64 네이티브 도구를 사용하여 32비트 x86 네이티브 코드를 작성하도록 환경을 설정합니다.

실제 시작 메뉴 폴더 및 바로 가기 이름은 설치한 Visual Studio 버전과 설정한 경우 설치 애칭에 따라 달라집니다. 예를 들어 Visual Studio 2019가 설치되어 있고 *미리 보기*라는 설치 애칭을 지정한 경우 개발자 명령 프롬프트 바로 가기의 이름은 **Visual Studio 2019** 폴더에서 **VS 2019용 개발자 명령 프롬프트**입니다.

## <a name="developer_command_prompt"></a> 개발자 명령 프롬프트 창 열기

1. 바탕 화면에서 Windows **시작** 메뉴를 연 다음, 스크롤하여 Visual Studio 버전에 맞는 폴더(예: **Visual Studio 2019**)를 찾아 엽니다. 일부 이전 버전의 Visual Studio에서는 바로 가기가 **Visual Studio Tools**라는 하위 폴더에 있습니다.

1. 폴더에서 Visual Studio 버전에 맞는 **개발자 명령 프롬프트**를 선택합니다. 이 바로 가기는 32비트 x86 네이티브 도구의 기본 빌드 아키텍처를 사용하여 32비트 x86 네이티브 코드를 작성하는 개발자 명령 프롬프트 창을 시작합니다. 기본이 아닌 빌드 아키텍처를 원하는 경우 네이티브 또는 크로스 도구 명령 프롬프트 중 하나를 선택하여 호스트 및 대상 아키텍처를 지정합니다.

개발자 명령 프롬프트 창을 여는 더 빠른 방법은 바탕 화면 검색 상자에서 *개발자 명령 프롬프트*를 입력한 다음, 원하는 결과를 선택하는 것입니다.

## <a name="developer_command_file_locations"></a> 개발자 명령 파일 위치

기존 명령 프롬프트 창에서 빌드 아키텍처 환경을 설정하려면 설치 관리자에서 만든 명령 파일(배치 파일) 중 하나를 사용하여 필요한 환경을 설정할 수 있습니다. 이 작업은 새 명령 프롬프트 창에서 수행하는 것이 좋으며, 나중에 동일한 명령 창에서 환경을 전환하지 않는 것이 좋습니다. 이러한 파일의 위치는 설치한 Visual Studio 버전과 설치 중에 선택한 위치 및 이름 지정에 따라 달라집니다. Visual Studio 2019의 경우 64비트 컴퓨터의 일반적인 설치 위치는 \Program Files (x86)\Microsoft Visual Studio\2019\*edition*에 있습니다. 여기서 *edition*은 Community, Professional, Enterprise, BuildTools 또는 제공한 다른 이름일 수 있습니다. Visual Studio 2017 위치도 비슷합니다. Visual Studio 2015의 경우 일반적인 설치 위치는 \Program Files (x86)\Microsoft Visual Studio 14.0입니다.

기본 개발자 명령 프롬프트 명령 파일인 VsDevCmd.bat은 설치 디렉터리의 Common7\Tools 하위 디렉터리에 있습니다. 매개 변수를 지정하지 않으면 32비트 x86 네이티브 도구를 사용하여 32비트 x86 코드를 작성하기 위한 환경, 호스트 및 대상 빌드 아키텍처가 설정됩니다.

추가 명령 파일은 프로세서 아키텍처, Visual Studio 워크로드 및 설치한 옵션에 따라 특정 빌드 아키텍처를 설정하는 데 사용할 수 있습니다. Visual Studio 2017 및 Visual Studio 2019의 경우 Visual Studio 설치 디렉터리의 VC\Auxiliary\Build 하위 디렉터리에 있습니다. Visual Studio 2015의 경우 설치 디렉터리의 VC, VC\bin 또는 VC\bin\\*architectures* 하위 디렉터리에 있습니다. 여기서 *architectures*는 네이티브 또는 크로스 컴파일러 옵션 중 하나입니다. 이러한 명령 파일은 기본 매개 변수를 설정하고 VsDevCmd.bat를 호출하여 지정된 빌드 아키텍처 환경을 설정합니다. 일반적인 설치에 포함될 수 있는 명령 파일은 다음과 같습니다.

|명령 파일|호스트 및 대상 아키텍처|
|---|---|
|**vcvars32.bat**| 32비트 x86 네이티브 도구를 사용하여 32비트 x86 코드를 작성합니다.|
|**vcvars64.bat**| 64비트 x64 네이티브 도구를 사용하여 64비트 x64 코드를 작성합니다.|
|**vcvarsx86_amd64.bat**| 32비트 x86 네이티브 크로스 도구를 사용하여 64비트 x64 코드를 작성합니다.|
|**vcvarsamd64_x86.bat**| 64비트 x64 네이티브 크로스 도구를 사용하여 32비트 x86 코드를 작성합니다.|
|**vcvarsx86_arm.bat**| 32비트 x86 네이티브 크로스 도구를 사용하여 ARM 코드를 작성합니다.|
|**vcvarsamd64_arm.bat**| 64비트 x64 네이티브 크로스 도구를 사용하여 ARM 코드를 작성합니다.|
|**vcvarsall.bat**| 매개 변수를 사용하여 호스트 및 대상 아키텍처뿐만 아니라 SDK 및 플랫폼 선택 항목도 지정할 수 있습니다. 지원되는 옵션 목록을 보려면 **/help** 매개 변수를 사용하여 호출합니다.|

> [!CAUTION]
> vcvarsall.bat 파일 및 다른 Visual Studio 명령 파일은 컴퓨터마다 다를 수 있습니다. 누락되거나 손상된 vcvarsall.bat 파일을 다른 컴퓨터의 파일로 바꾸지 마세요. Visual Studio 설치 관리자를 다시 실행하여 누락된 파일을 대체합니다.
>
> 또한 vcvarsall.bat 파일은 버전별로 다릅니다. 현재 버전의 Visual Studio가 이전 버전의 Visual Studio도 있는 컴퓨터에 설치되어 있는 경우 동일한 버전의 명령 프롬프트 창에서 다른 버전의 vcvarsall.bat 또는 다른 Visual Studio 명령 파일을 실행하지 마세요.

## <a name="use-the-developer-tools-in-an-existing-command-window"></a>기존 명령 창에서 개발자 도구 사용

기존 명령 창에서 특정 빌드 아키텍처를 지정하는 가장 간단한 방법은 vcvarsall.bat 파일을 사용하는 것입니다. vcvarsall.bat를 사용하여 네이티브 32비트/64비트 컴파일 또는 x86/x64/ARM 프로세서의 크로스 컴파일에 대한 명령줄을 구성하는 환경 변수를 설정하고, Microsoft Store, 유니버설 Windows 플랫폼 또는 Windows Desktop 플랫폼을 대상으로 지정하며, 사용할 Windows SDK를 지정하고, 플랫폼 도구 집합 버전을 지정할 수 있습니다. 인수가 제공되지 않으면 vcvarsall.bat에서 x86 Windows Desktop 대상에 현재 32비트 네이티브 컴파일러를 사용하도록 환경 변수를 구성합니다. 그러나 이 파일을 사용하여 네이티브 또는 크로스 컴파일러 도구 중 하나를 구성할 수 있습니다. 빌드 컴퓨터 아키텍처에서 설치되지 않았거나 사용할 수 없는 컴파일러 구성을 지정하면 오류 메시지가 표시됩니다.

### <a name="vcvarsall-syntax"></a>vcvarsall 구문

> **vcvarsall.bat** [*architecture*] [*platform_type*] [*winsdk_version*] [ **-vcvars_ver=**_vcversion_]

*architecture*<br/>
이 선택적 인수는 사용할 호스트 및 대상 아키텍처를 지정합니다. *architecture*를 지정하지 않으면 기본 빌드 환경이 사용됩니다. 지원되는 인수는 다음과 같습니다.

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
필요에 따라 사용할 Visual Studio 컴파일러 도구 집합을 지정합니다. 기본적으로 현재 Visual Studio 컴파일러 도구 집합을 사용하도록 환경이 설정됩니다. Visual Studio 2015 컴파일러 도구 집합을 지정하려면 **-vcvars_ver=14.0**을 사용하고, Visual Studio 2017 컴파일러 도구 집합을 지정하려면 **-vcvars_ver=15.0**을 사용합니다.

<a name="vcvarsall"></a>
#### <a name="to-set-up-the-build-environment-in-an-existing-command-prompt-window"></a>기존 명령 프롬프트 창에서 빌드 환경을 설정하려면

1. 명령 프롬프트에서 CD 명령을 사용하여 Visual Studio 설치 디렉터리로 변경합니다. 그런 다음, CD를 다시 사용하여 구성별 명령 파일이 있는 하위 디렉터리로 변경합니다. Visual Studio 2017 및 Visual Studio 2019의 경우 하위 디렉터리는 VC\Auxiliary\Build입니다. Visual Studio 2015의 경우 VC 하위 디렉터리를 사용합니다.

1. 기본 개발자 환경에 대한 명령을 입력합니다. 예를 들어 최신 Windows SDK 및 Visual Studio 2019 컴파일러 도구 집합을 사용하여 64비트 플랫폼에서 UWP용 ARM 코드를 작성하려면 다음 명령줄을 사용합니다.

   `vcvarsall.bat amd64_arm uwp`

## <a name="create-your-own-command-prompt-shortcut"></a>사용자 고유의 명령 프롬프트 바로 가기 만들기

기존 개발자 명령 프롬프트 바로 가기 중 하나에 대한 속성 대화 상자를 열면 사용하는 명령 대상을 볼 수 있습니다. 예를 들어 **VS 2019용 x64 Native Tools 명령 프롬프트** 바로 가기의 대상은 다음과 비슷합니다.

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\VC\Auxiliary\Build\vcvars64.bat"`

아키텍처별 배치 파일은 *architecture* 매개 변수를 설정하고 vcvarsall.bat를 호출합니다. vcvarsall.bat에 전달하는 것과 동일한 추가 옵션을 이러한 배치 파일에 전달하거나 vcvarsall.bat를 직접 호출할 수 있습니다. 사용자 고유의 명령 바로 가기에 대한 매개 변수를 지정하려면 명령의 끝에 큰따옴표로 추가합니다. 예를 들어 최신 Windows SDK 및 현재 버전보다 이전 버전의 컴파일러 도구 집합을 사용하여 64비트 플랫폼에서 UWP용 ARM 코드를 작성하기 위한 바로 가기를 설정하려면 버전 번호를 지정해야 합니다. 바로 가기에서 다음 명령 대상과 같은 항목을 사용합니다.

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\VC\Auxiliary\Build\vcvarsall.bat amd64_arm uwp -vcvars_ver=15.0"`

Visual Studio 설치 디렉터리를 반영하도록 경로를 조정해야 합니다. vcvarsall.bat 파일에는 특정 버전 번호에 대한 추가 정보가 있습니다.

## <a name="command-line-tools"></a>명령줄 도구

명령줄에서 C/C++ 프로젝트를 빌드하기 위해 Visual Studio에서 제공하는 명령줄 도구는 다음과 같습니다.

[CL](reference/compiling-a-c-cpp-program.md)<br/>
컴파일러(cl.exe)를 사용하여 소스 코드 파일을 컴파일한 다음 앱, 라이브러리 및 DLL에 연결합니다.

[링크](reference/linking.md)<br/>
링커(link.exe)를 사용하여 컴파일된 개체 파일 및 라이브러리를 앱 및 DLL에 연결합니다.

[MSBuild](msbuild-visual-cpp.md)<br/>
MSBuild(msbuild.exe) 및 프로젝트 파일(.vcxproj)을 사용하여 빌드를 구성하고 도구 집합을 간접적으로 호출합니다. 이는 Visual Studio IDE에서 프로젝트 **빌드** 또는 **솔루션 빌드** 명령을 실행하는 것과 같습니다. 명령줄에서 MSBuild를 실행하는 것은 고급 시나리오이며 일반적으로 사용하지 않는 것이 좋습니다.

[DEVENV](/visualstudio/ide/reference/devenv-command-line-switches)<br/>
Visual Studio IDE를 표시하지 않고 특정 빌드 명령을 수행하려면 명령줄 스위치(예: **/Build** 또는 **/Clean**)와 결합된 DEVENV(devenv.exe)를 사용합니다. 일반적으로 Visual Studio에서 MSBuild의 복잡성을 처리할 수 있으므로 MSBuild를 직접 사용하는 것보다 이 방법을 사용하는 것이 더 좋습니다.

[NMAKE](reference/nmake-reference.md)<br/>
기존 메이크파일을 기반으로 하여 C++ 프로젝트를 빌드하려면 Windows에서 NMAKE(nmake.exe)를 사용합니다.

명령줄에서 빌드하는 경우 도움말은 F1 명령을 사용하여 즉시 얻을 수 없습니다. 대신 검색 엔진을 사용하여 경고, 오류 및 메시지에 대한 정보를 얻거나 오프라인 도움말 파일을 사용할 수 있습니다. [docs.microsoft.com](https://docs.microsoft.com/cpp/)에서 검색을 사용하려면 페이지 위쪽의 검색 상자에서 검색 문자열을 입력합니다.

## <a name="in-this-section"></a>섹션 내용

설명서의 이 섹션에 있는 문서는 명령줄에서 앱을 빌드하는 방법을 보여주고, 64비트 도구 집합을 사용하고 x86, x64 및 ARM 플랫폼을 대상으로 하도록 명령줄 빌드 환경을 사용자 지정하는 방법에 대해 설명하고, 명령줄 빌드 도구인 MSBuild 및 NMAKE를 사용하는 방법을 보여줍니다.

[연습: 명령줄에서 네이티브 C++ 프로그램 컴파일](walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)<br/>
명령줄에서 간단한 C++ 프로그램을 만들고 컴파일하는 방법을 보여주는 예제를 제공합니다.

[연습: 명령줄에서 C 프로그램 컴파일](walkthrough-compile-a-c-program-on-the-command-line.md)<br/>
C 프로그래밍 언어로 작성한 프로그램을 컴파일하는 방법에 대해 설명합니다.

[연습: 명령줄에서 C++/CLI 프로그램 컴파일](walkthrough-compiling-a-cpp-cli-program-on-the-command-line.md)<br/>
.NET Framework를 사용하는 C++/CLI 프로그램을 만들어 컴파일하는 방법에 대해 설명합니다.

[연습: 명령줄에서 C++/CX 프로그램 컴파일](walkthrough-compiling-a-cpp-cx-program-on-the-command-line.md)<br/>
Windows 런타임을 사용하는 C++/CX 프로그램을 만들어 컴파일하는 방법에 대해 설명합니다.

[명령줄 빌드에 맞는 경로 및 환경 변수 설정](setting-the-path-and-environment-variables-for-command-line-builds.md)<br/>
32비트 또는 64비트 도구 집합을 사용하여 x86, x64 및 ARM 플랫폼을 대상으로 하는 명령줄 빌드에 필요한 환경 변수가 설정된 명령 프롬프트 창을 시작하는 방법에 대해 설명합니다.

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

## <a name="see-also"></a>참고 항목

[프로젝트 및 빌드 시스템](projects-and-build-systems-cpp.md)