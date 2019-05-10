---
title: 명령줄 Visual Studio에서에서 MSVC 도구 집합을 사용 하 여
description: Microsoft C++ Visual Studio IDE 외부에서 명령줄 컴파일러 도구 체인 (MSVC).
ms.custom: conceptual
ms.date: 04/25/2019
helpviewer_keywords:
- command-line builds [C++]
- compiling source code [C++], command line
- builds [C++], command-line
- command line [C++], building from
- command line [C++], compilers
ms.assetid: 7ca9daed-a003-4162-842d-908f79058365
ms.openlocfilehash: 5f9ac1e4753fdba412af26bcc45022dee354cacf
ms.sourcegitcommit: 18d3b1e9cdb4fc3a76f7a650c31994bdbd2bde64
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2019
ms.locfileid: "64877143"
---
# <a name="use-the-msvc-toolset-from-the-command-line"></a>명령줄에서 MSVC 도구 집합을 사용 하 여

Visual Studio에 포함 된 도구를 사용 하 여 명령줄에서 C 및 C++ 응용 프로그램을 빌드할 수 있습니다. 컴파일러 도구 집합에서 독립 실행형 패키지로 다운로드할 수도 있습니다는 [Visual Studio 다운로드](https://visualstudio.microsoft.com/downloads/) 페이지입니다. 일부인 합니다 **for Visual Studio Build Tools** ; 패키지에 필요한 도구만을 다운로드 하도록 선택할 수 있습니다 C++ 개발 합니다.

## <a name="how-to-use-the-command-line-tools"></a>명령줄 도구를 사용 하는 방법

Visual Studio 설치 관리자에서 C++ 워크 로드 중 하나를 선택 하면 Visual Studio 설치 *플랫폼 도구 집합*합니다. 플랫폼 도구 집합에 일치 하는 라이브러리와 함께 C/C++ 컴파일러, 링커, 어셈블러를 다른 빌드 도구를 비롯 한 특정 Visual Studio 버전을 모든 C 및 C++ 도구가 있습니다. 명령줄에서 이러한 도구를 사용할 수 있습니다 하 고는 또한 Visual Studio IDE에서 내부적으로 사용 합니다. 별도 x86 호스트 및 x64 호스트 컴파일러 및 x86, x64, ARM에 대 한 코드를 작성 하는 도구 및 ARM64 대상 있습니다. 각 특정 호스트 및 대상 빌드 아키텍처에 대 한 도구 집합은 자체 디렉터리에 저장 됩니다.

컴파일러 도구 집합 설치 되는 컴퓨터 프로세서 및 설치 중에 선택한 옵션에 따라 달라 집니다. 최소한 32 비트 x86 네이티브 코드를 빌드 및 64 비트 x64 네이티브 코드를 작성 하는 도구를 교차 하는 32 비트 x86에 호스트 된 도구가 설치 됩니다. 64 비트 Windows에 있는 경우 64 비트 네이티브 코드를 빌드 및 32 비트 네이티브 코드를 작성 하는 도구를 교차 하는 64 비트 x64 호스트 도구로 설치 됩니다. 옵션 C++ 유니버설 Windows 플랫폼 도구를 설치 하려는 경우 32 비트 및 64 비트 네이티브 도구 ARM 코드를 작성 하는 설치 됩니다. 다른 워크 로드는 추가 도구를 설치할 수 있습니다.

## <a name="environment-variables-and-developer-command-prompts"></a>환경 변수 및 개발자 명령 프롬프트

도구는 올바르게 작동 하려면 몇 가지 특정 환경 변수를 설정할 필요 합니다. 이러한 경로 추가 하는 데 사용 됩니다 설정 파일, 라이브러리 파일 및 SDK 위치를 포함 합니다. 설치 관리자 쉽게 이러한 환경 변수를 설정, 사용자 지정 만듭니다 *명령 파일*, 또는 파일을 설치 하는 동안 일괄 처리 합니다. 특정 호스트 및 대상 빌드 아키텍처, Windows SDK 버전, 대상 플랫폼 및 플랫폼 도구 집합을 설정 하려면 명령 프롬프트 창에서 이러한 명령 파일 중 하나를 실행할 수 있습니다. 편의 위해 설치 관리자를 필요한 환경 변수가 모두 설정 되어 있고 사용할 수 있도록 이러한 명령 파일을 사용 하 여 개발자 명령 프롬프트 창을 시작 하는 시작 메뉴에 바로 가기를 만듭니다.

필요한 환경 변수는 특정 설치 하는 빌드 아키텍처를 선택 하 고 제품 업데이트 또는 업그레이드에서 변경 될 수 있습니다. 따라서 직접 Windows에서 환경 변수를 설정 하는 대신 설치 된 명령 프롬프트 바로 가기 또는 명령 파일 중 하나를 사용 하는 것이 좋습니다. 자세한 내용은 [명령줄 빌드에 맞는 경로 및 환경 변수 설정](setting-the-path-and-environment-variables-for-command-line-builds.md)합니다.

## <a name="developer_command_prompt_shortcuts"></a> 개발자 명령 프롬프트 바로 가기

명령 프롬프트 바로 가기는 시작 메뉴의 버전별 Visual Studio 폴더에 설치 됩니다. 기본 명령 프롬프트 바로 가기 키 목록과 지 빌드 아키텍처는 다음과 같습니다.

- **개발자 명령 프롬프트** -32 비트, x86 네이티브 도구를 사용 하 여 32 비트, x86 네이티브 코드를 작성 하도록 환경을 설정 합니다.
- **x86 native Tools 명령 프롬프트** -32 비트, x86 네이티브 도구를 사용 하 여 32 비트, x86 네이티브 코드를 작성 하도록 환경을 설정 합니다.
- **x64 native Tools 명령 프롬프트** -64 비트 x64 네이티브 도구를 사용 하 여 64 비트, x64 네이티브 코드를 작성 하도록 환경을 설정 합니다.
- **x86_x64 Cross Tools 명령 프롬프트** -32 비트, x86 네이티브 도구를 사용 하 여 64 비트, x64 네이티브 코드를 작성 하도록 환경을 설정 합니다.
- **x64_x86 Cross Tools 명령 프롬프트** -64 비트 x64 네이티브 도구를 사용 하 여 32 비트, x86 네이티브 코드를 작성 하도록 환경을 설정 합니다.

실제 시작 메뉴 폴더 및 바로 가기 이름 하나를 설정 하는 경우를 설치한 후 Visual Studio 버전 및 설치 애칭에 따라 달라 집니다. 예를 들어, Visual Studio 2017이 설치 되어 있는 경우에 대 한 한이 지정 된 설치 애칭입니다 *미리 보기*, 개발자 명령 프롬프트 바로 가기를 라고 **VS 2019 용 개발자 명령 프롬프트**의 폴더가 **Visual Studio 2019**합니다.

## <a name="developer_command_prompt"></a> 개발자 명령 프롬프트 창을 열려면

1. 바탕 화면에서 Windows를 엽니다 **시작** 메뉴 및 스크롤을 찾고 예를 들어, Visual Studio의 버전에 대 한 폴더를 열고 **Visual Studio 2019**합니다. 일부 이전 버전의 Visual Studio에서 바로 가기가 있는 라는 하위 폴더 **Visual Studio Tools**합니다.

1. 폴더를 선택 하 여 **개발자 명령 프롬프트** Visual Studio의 버전에 대 한 합니다. 이 바로 가기는 32 비트, x86 네이티브 코드를 작성 하는 기본 빌드 아키텍처의 32 비트, x86 네이티브 도구를 사용 하는 개발자 명령 프롬프트 창을 시작 합니다. 기본이 아닌 빌드 아키텍처를 원한다 면 네이티브 중 하나를 선택 또는 크로스 도구 명령 프롬프트를 호스트 및 대상 아키텍처를 지정 합니다.

개발자 명령 프롬프트 창을 여는 훨씬 빠른 방법은 입력 하는 것 *개발자 명령 프롬프트* 데스크톱 검색 상자를 선택한 다음 원하는 결과 선택 합니다.

## <a name="developer_command_file_locations"></a> 개발자 명령 파일 위치

기존 명령 프롬프트 창에서 빌드 아키텍처 환경을 설정 하려는 경우 필요한 환경을 설정 하려면 설치 관리자가 만든 명령 파일 (일괄 처리 파일) 중 하나를 사용할 수 있습니다. 만 좋습니다 새 명령 프롬프트 창에서이 작업을 수행 하 고 권장 하지는 않습니다 있습니다 이후 동일한 명령 창에서 환경을 전환 합니다. 이러한 파일의 위치를 설치한 후 Visual Studio 버전에 위치 및 설치 하는 동안 만든 명명 옵션에 따라 달라 집니다. Visual Studio 2019 64 비트 컴퓨터에 일반적인 설치 위치는 \Program 파일 (x86) \Microsoft Visual Studio\2019에\\*edition*여기서 *edition* 커뮤니티 수 Professional, Enterprise, BuildTools, 또는 다른 이름을 입력 합니다. Visual Studio 2017 위치는 유사 합니다. Visual Studio 2015 용 일반 설치 위치 \Program 파일 (x86) \Microsoft Visual Studio 14.0는 있습니다.

VsDevCmd.bat를 주 개발자 명령 프롬프트 명령 파일 설치 디렉터리의 Common7\Tools 하위 디렉터리에 있습니다. 매개 변수 없이 지정 된, 환경 설정 및 호스트 및 대상 아키텍처 32 비트 x86 네이티브 도구를 사용 하 여 32 비트 x86 빌드를 작성 하는 경우 코드입니다.

추가 명령 파일 프로세서 아키텍처 및 Visual Studio 워크 로드, 설치 옵션에 따라 특정 빌드 아키텍처를 설정할 수 있습니다. Visual Studio 2017 및 Visual Studio 2019 이러한 권장 사항은 Visual Studio 설치 디렉터리의 VC\Auxiliary\Build 하위 디렉터리입니다. Visual Studio 2015에서 이러한 권장 사항은 VC, VC\bin, 또는 VC\bin\\*아키텍처* 설치 디렉터리의 하위 디렉터리를 *아키텍처* 네이티브 중 하나인 또는 크로스 컴파일러 옵션입니다. 이러한 명령 파일 기본 매개 변수를 설정 및 지정 된 빌드 아키텍처 환경을 설정 하는 VsDevCmd.bat를 호출 합니다. 일반 설치의 경우 이러한 명령 파일을 포함할 수 있습니다.

|명령 파일|호스트 및 대상 아키텍처|
|---|---|
|**vcvars32.bat**| 32 비트 x86 네이티브 도구를 사용 하 여 32 비트 x86 빌드 코드입니다.|
|**vcvars64.bat**| 64 비트 x64 네이티브 도구를 사용 하 여 64 비트 x64 빌드 코드입니다.|
|**vcvarsx86_amd64.bat**| 32 비트 x86 네이티브 간 도구를 사용 하 여 64 비트 x64 빌드 코드입니다.|
|**vcvarsamd64_x86.bat**| 64 비트 x64 네이티브 간 도구를 사용 하 여 32 비트 x86 빌드 코드입니다.|
|**vcvarsx86_arm.bat**| 32 비트 x86 네이티브 간 도구를 사용 하 여 ARM 코드를 작성 합니다.|
|**vcvarsamd64_arm.bat**| 64 비트 x64 네이티브 간 도구를 사용 하 여 ARM 코드를 작성 합니다.|
|**vcvarsall.bat**| 매개 변수를 사용 하 여 지정 된 호스트 및 대상 아키텍처 뿐만 아니라 SDK 및 플랫폼 선택. 목록은 지원 되는 옵션을 사용 하 여 호출을 **/help** 매개 변수입니다.|

> [!CAUTION]
> Vcvarsall.bat 파일 및 기타 Visual Studio 명령 파일에는 컴퓨터에서 달라질 수 있습니다. 누락되거나 손상된 vcvarsall.bat 파일을 다른 컴퓨터의 파일로 바꾸지 마세요. 누락 된 파일을 바꾸려면 Visual Studio 설치 관리자를 다시 실행 합니다.
>
> 또한 vcvarsall.bat 파일은 버전별로 다릅니다. 현재 버전의 Visual Studio는 Visual Studio의 이전 버전이 있는 컴퓨터에 설치 하는 경우 실행 되지 않습니다 vcvarsall.bat 또는 다른 Visual Studio 명령 파일 같은 명령 프롬프트 창에서 다른 버전.

## <a name="use-the-developer-tools-in-an-existing-command-window"></a>기존 명령 창에서 개발자 도구를 사용 합니다.

기존 명령 창에서 특정 빌드 아키텍처를 지정 하는 가장 간단한 방법은 vcvarsall.bat 파일을 사용 하는 것입니다. Vcvarsall.bat를 사용 하 여 네이티브 32 비트 또는 64 비트 컴파일 또는 x86, x64 또는 ARM 프로세서 크로스 컴파일을 명령줄을 구성 하려면 환경 변수를 설정 하려면 Microsoft Store, 유니버설 Windows 플랫폼 또는 Windows 데스크톱 플랫폼; 대상 사용 하는 Windows SDK를 지정 하려면 및 플랫폼 도구 집합 버전을 지정 합니다. 인수가 제공 되지 않은, 경우 vcvarsall.bat x86에 대 한 현재 32 비트 네이티브 컴파일러를 사용 하는 것에 대 한 환경 변수를 구성 하는 Windows 데스크톱 대상입니다. 그러나 네이티브 또는 컴파일러 도구 간 구성에 사용할 수 있습니다. 가 설치 되지 않았거나 빌드 컴퓨터 아키텍처에서 사용할 수 없는 컴파일러 구성의 지정 하면 오류 메시지가 표시 됩니다.

### <a name="vcvarsall-syntax"></a>vcvarsall 구문

> **vcvarsall.bat** [*architecture*] [*platform_type*] [*winsdk_version*] [**-vcvars_ver=**_vcversion_]

*architecture*<br/>
이 선택적 인수를 사용 하는 호스트 및 대상 아키텍처를 지정 합니다. 하는 경우 *아키텍처* 지정 하지 않으면 기본 빌드 환경이 사용 됩니다. 이러한 인수는 지원 됩니다.

|*architecture*|컴파일러|호스트 컴퓨터 아키텍처|(대상) 출력 아키텍처 빌드|
|----------------------------|--------------|----------------------------------|-------------------------------|
|**x86**|x86 32비트 네이티브|x86, x64|x86|
|**x86\_amd64** 하거나 **x86\_x64**|x86 x64 cross|x86, x64|X64|
|**x86_arm**|x86용 ARM 크로스|x86, x64|ARM|
|**x86_arm64**|ARM64 간 x86|x86, x64|ARM64|
|**amd64** 또는 **x64**|x64 64 비트 네이티브|X64|X64|
|**amd64\_x86** 하거나 **x64\_x86**|x64 x86 cross|X64|x86|
|**amd64\_arm** 하거나 **x64\_arm**|X64 크로스 ARM|X64|ARM|
|**amd64\_arm64** 하거나 **x64\_arm64**|ARM64 x64 크로스|X64|ARM64|

*platform_type*<br/>
이 선택적 인수를 지정할 수 있습니다 **저장할** 하거나 **uwp** 플랫폼 형식으로 합니다. 기본적으로 데스크톱 또는 콘솔 앱을 빌드하는 환경 설정 됩니다.

*winsdk_version*<br/>
필요에 따라 사용할 Windows SDK의 버전을 지정 합니다. 기본적으로 설치 된 최신 Windows SDK 사용 됩니다. Windows SDK 버전을 지정 하려면 사용할 수는 전체 Windows 10 SDK 번호와 같은 **10.0.10240.0**를 지정 하거나 **8.1** Windows 8.1 SDK를 사용 하도록 합니다.

*vcversion*<br/>
필요에 따라 사용 하는 Visual Studio 컴파일러 도구 집합을 지정 합니다. 기본적으로 환경의 현재 Visual Studio 컴파일러 도구 집합을 사용 하도록 설정 됩니다. 사용 하 여 **-vcvars_ver 14.0 =** Visual Studio 2015 컴파일러 도구 집합을 지정 하 또는 **-vcvars_ver 15.0 =** 는 Visual Studio 2017 컴파일러 도구 집합을 지정 합니다.

<a name="vcvarsall"></a>
#### <a name="to-set-up-the-build-environment-in-an-existing-command-prompt-window"></a>기존 명령 프롬프트 창에서 빌드 환경을 설정 하려면

1. 명령 프롬프트에서 CD 명령을 사용 하 여 Visual Studio 설치 디렉터리로 변경 합니다. 그런 다음 다시 사용 하 여 CD 구성별 명령 파일을 포함 하는 하위 디렉터리로 변경 합니다. Visual Studio 2017 및 2019 VC\Auxiliary\Build 하위 디렉터리입니다. Visual Studio 2015 용 VC 하위 디렉터리를 사용 합니다.

1. 기본 개발자 환경에 대 한 명령을 입력 합니다. 예를 들어, 코드를 빌드하려면 ARM UWP 용 64 비트 플랫폼에서 최신 Windows SDK 및 Visual Studio 2019 컴파일러 도구 집합을 사용 하 여,이 명령줄을 사용 합니다.

   `vcvarsall.bat amd64_arm uwp`

## <a name="create-your-own-command-prompt-shortcut"></a>사용자 고유의 명령 프롬프트 바로 가기 만들기

기존 개발자 명령 프롬프트 바로 가기 중 하나에 대 한 속성 대화 상자를 열면 사용 하는 명령 대상을 볼 수 있습니다. 예를 들어 대상 합니다 **x64 VS 2019에 대 한 네이티브 도구 명령 프롬프트** 바로 가기는 비슷한:

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\VC\Auxiliary\Build\vcvars64.bat"`

아키텍처별 일괄 처리 파일 집합을 *아키텍처* vcvarsall.bat 매개 변수를 호출 합니다. Vcvarsall.bat를를 전달 하거나 vcvarsall.bat를 직접 호출 하기만 하면 이러한 일괄 처리 파일을 같은 추가 옵션을 전달할 수 있습니다. 자신의 명령 바로 가기에 대 한 매개 변수를 지정 하려면 큰따옴표에서 명령의 끝에 추가 합니다. 예를 들어, 코드를 빌드하려면 ARM UWP 용 64 비트 플랫폼에서 최신 Windows SDK 및 현재 버전 보다 이전 컴파일러 도구 집합을 사용 하 여 바로 가기의 설정 하려면 해야 버전 번호를 지정 합니다. 바로 가기에이 명령 대상 같이 사용 합니다.

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\VC\Auxiliary\Build\vcvarsall.bat amd64_arm uwp -vcvars_ver=15.0"`

Visual Studio 설치 디렉터리를 반영 하도록 경로 조정 해야 합니다. Vcvarsall.bat 파일에 특정 버전 번호에 대 한 추가 정보가 있습니다.

## <a name="command-line-tools"></a>명령줄 도구

명령줄에서 C/C++ 프로젝트를 빌드하려면 Visual Studio는 이러한 명령줄 도구를 제공 합니다.

[CL](reference/compiling-a-c-cpp-program.md)<br/>
컴파일러(cl.exe)를 사용하여 소스 코드 파일을 컴파일한 다음 앱, 라이브러리 및 DLL에 연결합니다.

[링크](reference/linking.md)<br/>
링커(link.exe)를 사용하여 컴파일된 개체 파일 및 라이브러리를 앱 및 DLL에 연결합니다.

[MSBuild](msbuild-visual-cpp.md)<br/>
MSBuild (msbuild.exe) 및 프로젝트 파일 (.vcxproj)를 사용 하 여 빌드를 구성 하 여 도구 집합을 직접 호출 합니다. 실행 중인 것과 같습니다 합니다 **빌드** 프로젝트 또는 **솔루션 빌드** Visual Studio IDE에 명령 합니다. 명령줄에서 MSBuild를 실행 합니다. 고급 시나리오 이며 일반적으로 권장 되지 않습니다.

[DEVENV](/visualstudio/ide/reference/devenv-command-line-switches)<br/>
명령줄 스위치와 함께 DEVENV (devenv.exe)를 사용 하 여-예를 들어 **/빌드** 또는 **정리/**-수행 하려면 특정 빌드 명령을 Visual Studio IDE를 표시 하지 않고 있습니다. 일반적이 기본 Visual Studio MSBuild의 복잡성을 처리 하도록 할 수 있으므로 직접 MSBuild를 사용 하 여 합니다.

[NMAKE](reference/nmake-reference.md)<br/>
Windows에서 NMAKE (nmake.exe)를 사용 하 여 빌드 C++ 기존 메이크파일을 기준으로 한 프로젝트입니다.

명령줄에서 빌드할 때 F1 명령을 사용할 수 없는 경우에 대 한 빠른 도움말 대신, 경고, 오류 및 메시지에 대 한 정보를 검색 엔진을 사용할 수 있습니다 하거나 오프 라인 도움말 파일을 사용할 수 있습니다. 검색을 사용 하도록 [docs.microsoft.com](https://docs.microsoft.com/cpp/), 페이지의 맨 위에 있는 검색 상자에 검색 문자열을 입력 합니다.

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
명령줄 빌드에 대 한 대상으로 하는 x86, x64, 설정 및 플랫폼을 32 비트 또는 64 비트 도구 집합을 사용 하 여 ARM 필수 환경 변수를 사용 하는 명령 프롬프트 창을 시작 하는 방법에 설명 합니다.

[NMAKE 참조](reference/nmake-reference.md)<br/>
Microsoft Program Maintenance Utility(NMAKE.EXE)에 대해 설명하는 문서의 링크를 제공합니다.

[명령줄에서 MSBuildC++](msbuild-visual-cpp.md)<br/>
명령줄에서 msbuild.exe를 사용 하는 방법을 설명 하는 문서에 대 한 링크를 제공 합니다.

## <a name="related-sections"></a>관련 단원

[/MD, /MT, /LD(런타임 라이브러리 사용)](reference/md-mt-ld-use-run-time-library.md)<br/>
컴파일러 옵션을 사용하여 디버그 또는 릴리스 런타임 라이브러리를 사용하는 방법에 대해 설명합니다.

[C/C++ 컴파일러 옵션](reference/compiler-options.md)<br/>
C 및 C++ 컴파일러 옵션과 CL.exe에 대해 설명하는 문서에 대한 링크를 제공합니다.

[MSVC 링커 옵션](reference/linker-options.md)<br/>
링커 옵션 및 LINK.exe에 대해 설명하는 문서에 대한 링크를 제공합니다.

[추가 MSVC 빌드 도구](reference/c-cpp-build-tools.md)<br/>
C/C++에 대 한 링크 빌드 Visual Studio에 포함 된 도구를 제공 합니다.

## <a name="see-also"></a>참고자료

[프로젝트 및 빌드 시스템](projects-and-build-systems-cpp.md)