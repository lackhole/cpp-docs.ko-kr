---
title: MSBuild 내부 요소에 대 한 C++ Visual Studio의 프로젝트
ms.date: 12/08/2018
helpviewer_keywords:
- MSBuild overview
ms.assetid: dd258f6f-ab51-48d9-b274-f7ba911d05ca
ms.openlocfilehash: 6c8e891f6bf6ed6b3bb3d1c84dbc13b64ab7b868
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320893"
---
# <a name="msbuild-internals-for-c-projects"></a>MSBuild 내부 요소에 대 한 C++ 프로젝트

IDE에서 프로젝트 속성을 설정 하 고 다음 프로젝트를 저장 하는 경우 Visual Studio 프로젝트 설정 프로젝트 파일에 씁니다. 프로젝트 파일에는 프로젝트에 고유한 설정이 포함 되어 있습니다. 하지만 프로젝트를 빌드하는 데 필요한 모든 설정이 없습니다. 프로젝트 파일 포함 `Import` 추가 네트워크를 포함 하는 요소 *파일을 지원 합니다.* 지원 파일에는 나머지 속성, 대상 및 프로젝트를 빌드하는 데 필요한 설정을 포함 합니다.

대부분의 대상 및 지원 파일에 있는 속성은 빌드 시스템을 구현 하는 용도로 존재 합니다. 다음 섹션에서는 몇 가지 유용한 대상과 MSBuild 명령줄에서 지정할 수 있는 속성을 설명 합니다. 더 많은 대상과 속성을 검색 하려면 지원 파일 디렉터리에서 파일을 탐색 합니다.

## <a name="support-file-directories"></a>지원 파일 디렉터리

기본적으로 주 Visual Studio 지원 파일에 다음 디렉터리에 있습니다. Microsoft Visual Studio에서 디렉터리는 Visual Studio 2015 및 이전 버전에서 MSBuild에서 디렉터리를 사용 하는 동안 Visual Studio 2017 이상 버전에서 사용 됩니다.

|디렉터리|설명|
|---------------|-----------------|
|*drive*:\Program Files *(x86)* \Microsoft Visual Studio\\*year*\\*edition*\Common7\IDE\VC\VCTargets\ <br /><br />*drive*:\Program Files *(x86)* \MSBuild\Microsoft.Cpp (x86)\v4.0\\*version*\ |기본 대상 파일 (.targets)를 포함 하 고 대상에서 사용 되는 속성 파일 (.props). 기본적으로 $ (vctargetspath) 매크로이 디렉터리를 참조합니다.|
|*drive*:\Program Files *(x86)* \Microsoft Visual Studio\\*year*\\*edition*\Common7\IDE\VC\VCTargets\Platforms\\*platform*\ <br /><br />*drive*:\Program Files *(x86)* \MSBuild\Microsoft.Cpp\v4.0\\*version*\Platforms\\*platform*\ |부모 디렉터리의 대상과 속성을 재정의 하는 플랫폼별 대상 및 속성 파일을 포함 합니다. 이 디렉터리는이 디렉터리에 있는 대상에서 사용 되는 작업을 정의 하는 DLL도 포함 됩니다.<br /><br /> 합니다 *플랫폼* 자리 표시자는 ARM, Win32 또는 x64를 나타내는 하위 디렉터리입니다.|
|*drive*:\Program Files *(x86)* \Microsoft Visual Studio\\*year*\\*edition*\Common7\IDE\VC\VCTargets\Platforms\\*platform*\PlatformToolsets\\*toolset*\ <br /><br />*drive*:\Program Files *(x86)* \MSBuild\Microsoft.Cpp\v4.0\\*version*\Platforms\\*platform*\PlatformToolsets\\*toolset*\ <br /><br />*drive*:\Program Files *(x86)* \MSBuild\Microsoft.Cpp\v4.0\Platforms\\*platform*\PlatformToolsets\\*toolset*\ |빌드를 생성할 수 있도록 하는 디렉터리를 포함 C++ 지정을 사용 하 여 응용 프로그램 *도구 집합*합니다.<br /><br /> *연도* 하 고 *edition* Visual Studio 2017 및 이후 버전에서 사용 하는 자리 표시자입니다. 합니다 *버전* 자리 표시자는 Visual Studio 2013의 경우 V120 또는 Visual Studio 2015의 경우 V140, Visual Studio 2012 용 V110 합니다. 합니다 *플랫폼* 자리 표시자는 ARM, Win32 또는 x64를 나타내는 하위 디렉터리입니다. 합니다 *도구 집합* 자리 표시자 v120_xp를 v110_wp80를 Visual Studio 2013 도구를 사용 하 여 Windows XP에 대 한 빌드에 Visual Studio 2015 도구 집합을 사용 하 여 Windows 앱을 빌드하기 위한 예를 들어 v140 도구 집합 하위 디렉터리를 나타냅니다. Visual Studio 2012 도구 집합을 사용 하 여 Windows Phone 8.0 앱을 빌드하십시오.<br /><br />Visual Studio 2010 또는 Visual Studio 2008 응용 프로그램을 생성 하는 빌드를 사용 하도록 설정 하는 디렉터리를 포함 하는 경로 포함 되지 않습니다 합니다 *버전*, 및 *플랫폼* 자리 표시자 Win32, Itanium, x64를 나타내는 하위 디렉터리입니다. 합니다 *도구 집합* 자리 표시자 v90 또는 v100 도구 집합 하위 디렉터리를 나타냅니다.|

## <a name="support-files"></a>지원 파일

지원 파일 디렉터리에는 이러한 확장을 사용 하 여 파일 포함:

|확장명|설명|
|---------------|-----------------|
|.targets|포함 `Target` 대상에서 실행 되는 작업을 지정 하는 XML 요소입니다. 포함 될 수도 있습니다 `PropertyGroup`, `ItemGroup`를 `ItemDefinitionGroup`, 및 사용자 정의 `Item` 파일 및 명령줄 옵션을 작업 매개 변수에 할당 하는 데 사용 되는 요소입니다.<br /><br /> 자세한 내용은 [Target 요소 (MSBuild)](/visualstudio/msbuild/target-element-msbuild)합니다.|
|.props|포함 `Property Group` 및 사용자 정의 `Property` 빌드하는 동안 사용 되는 파일 및 매개 변수 설정을 지정 하는 XML 요소입니다.<br /><br /> 포함 될 수도 있습니다 `ItemDefinitionGroup` 및 사용자 정의 `Item` 추가 설정을 지정 하는 XML 요소입니다. 항목 정의 그룹에 정의 된 항목은 속성과 비슷하지만 명령줄에서 액세스할 수 없습니다. Visual Studio 프로젝트 파일 속성 대신 항목 설정을 나타내는 데 자주 사용 합니다.<br /><br /> 자세한 내용은 [ItemGroup 요소 (MSBuild)](/visualstudio/msbuild/itemgroup-element-msbuild), 
[ItemDefinitionGroup 요소 (MSBuild)](/visualstudio/msbuild/itemdefinitiongroup-element-msbuild), 및 [Item 요소 (MSBuild)](/visualstudio/msbuild/item-element-msbuild)합니다.|
|.xml|선언 하 고 속성 시트 및 속성 페이지, 텍스트 상자 및 목록 상자 컨트롤과 같은 IDE 사용자 인터페이스 요소를 초기화 하는 XML 요소를 포함 합니다.<br /><br /> .Xml 파일에는 직접 IDE, MSBuild가 아닌 지원. 그러나 IDE 속성의 값은 빌드 속성과 항목에 할당 됩니다.<br /><br /> 대부분의.xml 파일은 로캘별 하위 디렉터리입니다. 예를 들어 영어-미국 지역에 대 한 파일이 $(VCTargetsPath) \1033\\합니다.|

## <a name="user-targets-and-properties"></a>사용자 대상 및 속성

명령줄에서 MSBuild를 가장 효과적으로 사용 하는 속성 및 대상도 유용 하 고 관련 알아야 수 있습니다. 대부분의 속성과 대상은 Visual Studio 빌드 시스템을 구현 하는 데 도움이 및 결과적으로 사용자에 게 관련 되지 않습니다. 이 섹션에서는 몇 가지 유용한 사용자 기반 속성 및 대상을 설명 합니다.

### <a name="platformtoolset-property"></a>PlatformToolset 속성

`PlatformToolset` 속성 결정는 MSVC 도구 집합 빌드에 사용 됩니다. 현재 도구 집합은 기본적으로 사용 됩니다. 이 속성을 설정 하는 경우 속성의 값이 리터럴 문자열을 특정 플랫폼에 대 한 프로젝트를 빌드하는 데 필요한 속성 및 대상 파일을 포함 하는 디렉터리의 경로 사용 하 여 연결 됩니다. 해당 플랫폼 도구 집합 버전을 사용 하 여 빌드 플랫폼 도구 집합 설치 되어야 합니다.

예를 들어 설정 된 `PlatformToolset` 속성을 `v140` 응용 프로그램을 빌드하려면 Visual Studio 2015 도구 및 라이브러리를 사용 하려면:

`msbuild myProject.vcxproj /p:PlatformToolset=v140`

### <a name="preferredtoolarchitecture-property"></a>PreferredToolArchitecture 속성

`PreferredToolArchitecture` 속성 32 비트 또는 64 비트 컴파일러 및 도구를 빌드에 사용 되는지 여부를 결정 합니다. 출력 플랫폼 아키텍처 또는 구성에는이 속성이 적용 되지 않습니다. 기본적으로 MSBuild 사용 x86 버전의 컴파일러 및 도구가이 속성이 설정 되어 있지 않으면입니다.

예를 들어 설정 된 `PreferredToolArchitecture` 속성을 `x64` 64 비트 컴파일러 및 도구를 응용 프로그램을 빌드하는 데:

`msbuild myProject.vcxproj /p:PreferredToolArchitecture=x64`

### <a name="useenv-property"></a>UseEnv 속성

기본적으로 현재 프로젝트의 플랫폼별 설정은 PATH, INCLUDE, LIB, LIBPATH, 구성 및 플랫폼 환경 변수를 재정의 합니다. 설정 된 `UseEnv` 속성을 **true** 환경 변수 재정의 되지 않도록 보장 하기 위해.

`msbuild myProject.vcxproj /p:UseEnv=true`

### <a name="targets"></a>대상

Visual Studio 지원 파일에 있는 대상의 수백 가지 있습니다. 그러나 대부분은 사용자를 무시할 수 있는 시스템 기반 대상입니다. 대부분의 시스템 대상에 밑줄 (_), 접두사 또는 이름이 "Before", "After", "Pre" 또는 "Post" "PrepareFor", "Compute"로 시작 하는.

다음 표에서 몇 가지 유용한 사용자 기반 대상을 나열합니다.

|대상|설명|
|------------|-----------------|
|BscMake|실행 Microsoft Browse Information Maintenance Utility 도구인 bscmake.exe 합니다.|
|빌드|프로젝트를 빌드합니다.<br /><br /> 이 프로젝트에 대 한 기본 대상입니다.|
|ClCompile|실행 MSVC 컴파일러 도구 cl.exe 합니다.|
|정리|삭제 일시적이 고 중간 파일을 빌드합니다.|
|Lib|실행 Microsoft 32-Bit Library Manager 도구인 lib.exe 합니다.|
|링크|실행 MSVC 링커 도구인 link.exe 합니다.|
|ManifestResourceCompile|매니페스트에서 리소스 목록을 추출한 다음 Microsoft Windows Resource Compiler 도구인을 실행 rc.exe 합니다.|
|Midl|실행 인터페이스 정의 언어 (MIDL (Microsoft) 컴파일러 도구인 midl.exe 합니다.|
|다시 빌드|정리 하 고 프로젝트를 빌드합니다.|
|ResourceCompile|실행 Microsoft Windows Resource Compiler 도구인 rc.exe 합니다.|
|XdcMake|실행 XML 문서 도구인 xdcmake.exe 합니다.|
|Xsd|실행 XML 스키마 정의 도구인 xsd.exe 합니다. *다음 참고를 참조하세요.*|

> [!NOTE]
> Visual Studio 2017에서 C++ 프로젝트에 대 한 지원을 **xsd** 파일은 사용 되지 않습니다. 계속 사용할 수 있습니다 **Microsoft.VisualC.CppCodeProvider** 더하여 **CppCodeProvider.dll** 수동으로 GAC에 있습니다.

## <a name="see-also"></a>참고자료

[MSBuild 작업 참조](/visualstudio/msbuild/msbuild-task-reference)<br/>
[BscMake 작업](/visualstudio/msbuild/bscmake-task)<br/>
[CL 작업](/visualstudio/msbuild/cl-task)<br/>
[CPPClean 작업](/visualstudio/msbuild/cppclean-task)<br/>
[LIB 작업](/visualstudio/msbuild/lib-task)<br/>
[링크 작업](/visualstudio/msbuild/link-task)<br/>
[MIDL 작업](/visualstudio/msbuild/midl-task)<br/>
[MT 작업](/visualstudio/msbuild/mt-task)<br/>
[RC 작업](/visualstudio/msbuild/rc-task)<br/>
[SetEnv 작업](/visualstudio/msbuild/setenv-task)<br/>
[VCMessage 작업](/visualstudio/msbuild/vcmessage-task)<br/>
[XDCMake 작업](/visualstudio/msbuild/xdcmake-task)<br/>
