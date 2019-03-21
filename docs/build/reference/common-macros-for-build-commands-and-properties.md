---
title: 빌드 명령 및 속성에 대한 일반 매크로
ms.date: 05/29/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.GenerateXMLDocumentationFiles
- VC.Project.VCCLCompilerTool.XMLDocumentationFileName
helpviewer_keywords:
- $(FrameworkSDKDir) macro
- ProjectName macro $(ProjectName)
- DevEnvDir macro $(DevEnvDir)
- $(DevEnvDir) macro
- TargetPath macro $(TargetPath)
- VSInstallDir macro $(VSInstallDir)
- $(InputFileName) macro
- $(SolutionFileName) macro
- macros [C++], build macros
- InputFileName macro $(InputFileName)
- $(VCInstallDir) macro
- $(IntDir) macro
- $(ConfigurationName) macro
- SolutionDir macro $(SolutionDir)
- $(TargetPath) macro
- $(Inherit) macro
- $(SolutionPath) macro
- WebDeployRoot macro $(WebDeployRoot)
- WebDeployPath macro $(WebDeployPath)
- StopEvaluating macro $(StopEvaluating)
- $(RootNamespace) macro
- $(WebDeployRoot) macro
- ProjectPath macro $(ProjectPath)
- $(ProjectPath) macro
- $(InputDir) macro
- SolutionName macro $(SolutionName)
- ProjectExt macro $(ProjectExt)
- $(TargetExt) macro
- $(ProjectFileName) macro
- TargetName macro $(TargetName)
- $(References) macro
- References macro $(References)
- TargetExt macro $(TargetExt)
- ProjectDir macro $(ProjectDir)
- $(TargetDir) macro
- SolutionExt macro $(SolutionExt)
- $(SolutionDir) macro
- ProjectFileName macro $(ProjectFileName)
- VCInstallDir macro $(VCInstallDir)
- $(InputExt) macro
- $(TargetFileName) macro
- $(SolutionExt) macro
- PlatformName macro $(PlatformName)
- IntDir macro $(IntDir)
- $(FrameworkVersion) macro
- $(ProjectDir) macro
- build macros [C++]
- InputPath macro $(InputPath)
- $(VSInstallDir) macro
- $(WebDeployPath) macro
- TargetFileName macro $(TargetFileName)
- NoInherit macro $(NoInherit)
- ConfigurationName macro $(ConfigurationName)
- $(ProjectExt) macro
- TargetDir macro $(TargetDir)
- InputName macro $(InputName)
- $(ProjectName) macro
- FrameworkSDKDir macro $(FrameworkSDKDir)
- $(ParentName) macro
- InputExt macro $(InputExt)
- $(SafeRootNamespace) macro
- InputDir macro $(InputDir)
- $(FxCopDir) macro
- $(RemoteMachine) macro
- Inherit macro $(Inherit)
- FrameworkVersion macro $(FrameworkVersion)
- $(StopEvaluating) macro
- $(OutDir) macro
- FrameworkDir macro $(FrameworkDir)
- SolutionFileName macro $(SolutionFileName)
- $(NoInherit) macro
- RemoteMachine macro $(RemoteMachine)
- properties [C++], build property macros
- $(TargetName) macro
- $(SolutionName) macro
- $(InputPath) macro
- ParentName macro $(ParentName)
- OutDir macro $(OutDir)
- SafeRootNamespace macro $(SafeRootNamespace)
- FxCopDir macro $(FxCopDir)
- $(InputName) macro
- RootNamespace macro $(RootNamespace)
- builds [C++], macros
- $(FrameworkDir) macro
- $(PlatformName) macro
- SolutionPath macro $(SolutionPath)
ms.assetid: 239bd708-2ea9-4687-b264-043f1febf98b
ms.openlocfilehash: 669114691bc89c1e8136e07a949be57cda3d71b9
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826647"
---
# <a name="common-macros-for-build-commands-and-properties"></a>빌드 명령 및 속성에 대한 일반 매크로

설치 옵션에 따라 Visual Studio에서는 수백 개의 매크로를 사용할 수 있습니다. 이러한 속성은 기본적으로 .props 또는 .targets 파일 또는 프로젝트 설정에서 설정된 MSBuild 속성에 해당합니다. 프로젝트의 **속성 페이지** 대화 상자에서 문자열이 허용되는 모든 위치에서 이러한 매크로를 사용할 수 있습니다. 이러한 매크로는 대/소문자를 구분하지 않습니다.

## <a name="view-the-current-properties-and-macros"></a>현재 속성 및 매크로 보기

현재 사용 가능한 매크로를 표시하려면 **속성 페이지** 대화 상자의 속성 페이지에서 속성 행 끝에 있는 드롭다운 화살표를 선택합니다. **편집**을 사용할 수 있는 경우 해당 항목을 선택한 다음, 편집 대화 상자에서 **매크로** 단추를 선택합니다. Visual Studio에 표시되는 현재 속성 및 매크로 집합은 각각에 대한 현재 값과 함께 나열됩니다. 자세한 내용은 참조는 **Specifying User-Defined 값** 부분 [c + + 프로젝트 속성 페이지 참조](property-pages-visual-cpp.md)합니다.

## <a name="list-of-common-macros"></a>일반 매크로 목록

이 표에서는 사용 가능한 매크로의 일반적으로 사용되는 하위 집합에 대해 설명합니다. 이 목록은 완전하지 않습니다. MSBuild 속성 정의를 .props, .targets 및 .vcxproj 파일의 매크로로 생성하고 사용하는 방법에 대한 자세한 내용은 [MSBuild 속성](/visualstudio/msbuild/msbuild-properties)을 참조하세요.

|매크로|설명|
|-----------|-----------------|
|**$(Configuration)**|현재 프로젝트 구성의 이름(예: "디버그")입니다.|
|**$(DevEnvDir)**|Visual Studio의 설치 디렉터리(드라이브 + 경로로 정의됨)이며, 뒤의 백슬래시 '\\'를 포함합니다.|
|**$(FrameworkDir)**|.NET Framework가 설치된 디렉터리입니다.|
|**$(FrameworkSDKDir)**|.NET Framework를 설치한 디렉터리입니다. .NET Framework는 Visual Studio의 일부로 설치하거나 별도로 설치할 수 있습니다.|
|**$(FrameworkVersion)**|Visual Studio에서 사용하는 .NET Framework의 버전입니다. **$(FrameworkDir)** 과 함께 사용할 경우 Visual Studio에서 사용하는 .NET Framework 버전의 전체 경로입니다.|
|**$(FxCopDir)**|fxcop.cmd 파일의 경로입니다. fxcop.cmd 파일은 일부 Visual C++ 버전에서 설치되지 않습니다.|
|**$(IntDir)**|중간 파일에 대해 지정된 디렉터리 경로입니다. 상대 경로인 경우 중간 파일은 프로젝트 디렉터리에 추가된 이 경로로 이동합니다. 이 경로의 끝에는 슬래시가 있어야 합니다. **Intermediate Directory** 속성에 대한 값으로 확인됩니다. **$(OutDir)** 을 사용하여 이 속성을 정의할 수 없습니다.|
|**$(OutDir)**|출력 파일 디렉터리에 대한 경로입니다. 상대 경로인 경우 출력 파일은 프로젝트 디렉터리에 추가된 이 경로로 이동합니다. 이 경로의 끝에는 슬래시가 있어야 합니다. **Output Directory** 속성에 대한 값으로 확인됩니다. **$(IntDir)** 을 사용하여 이 속성을 정의할 수 없습니다.|
|**$(Platform)**|현재 프로젝트 플랫폼의 이름(예: "Win32")입니다.|
|**$(ProjectDir)**|프로젝트의 디렉터리(드라이브 + 경로로 정의됨)이며, 뒤의 백슬래시 '\\'를 포함합니다.|
|**$(ProjectExt)**|프로젝트의 파일 확장명입니다. 파일 확장명 앞에 '.'을 포함합니다.|
|**$(ProjectFileName)**|프로젝트의 파일 이름(기본 이름 + 파일 확장명으로 정의됨)입니다.|
|**$(ProjectName)**|프로젝트의 기본 이름입니다.|
|**$(ProjectPath)**|프로젝트의 절대 경로 이름(드라이브 + 경로 + 기본 이름 + 파일 확장명으로 정의됨)입니다.|
|**$(RemoteMachine)**|디버그 속성 페이지에서 **Remote Machine** 속성의 값으로 설정합니다. 자세한 내용은 [C/C++ 디버그 구성에 대한 프로젝트 설정 변경](/visualstudio/debugger/project-settings-for-a-cpp-debug-configuration) 을 참조하세요.|
|**$(RootNameSpace)**|애플리케이션을 포함하는 네임스페이스(있는 경우)입니다.|
|**$(SolutionDir)**|솔루션의 디렉터리(드라이브 + 경로로 정의됨)이며, 뒤의 백슬래시 '\\'를 포함합니다. IDE에서 솔루션을 빌드할 때만 정의됩니다.|
|**$(SolutionExt)**|솔루션의 파일 확장명입니다. 파일 확장명 앞에 '.'을 포함합니다. IDE에서 솔루션을 빌드할 때만 정의됩니다.|
|**$(SolutionFileName)**|솔루션의 파일 이름(기본 이름 + 파일 확장명으로 정의됨)입니다. IDE에서 솔루션을 빌드할 때만 정의됩니다.|
|**$(SolutionName)**|솔루션의 기본 이름입니다. IDE에서 솔루션을 빌드할 때만 정의됩니다.|
|**$(SolutionPath)**|솔루션의 절대 경로 이름(드라이브 + 경로 + 기본 이름 + 파일 확장명으로 정의됨)입니다. IDE에서 솔루션을 빌드할 때만 정의됩니다.|
|**$(TargetDir)**|빌드에 대한 기본 출력 파일의 디렉터리(드라이브 + 경로로 정의됨)이며, 뒤에 백슬래시 '\\'가 포함됩니다.|
|**$(TargetExt)**|빌드에 대한 기본 출력 파일의 파일 확장명입니다. 파일 확장명 앞에 '.'을 포함합니다.|
|**$(TargetFileName)**|빌드에 대한 기본 출력 파일의 파일 이름(기본이름 + 파일 확장명으로 정의됨)입니다.|
|**$(TargetName)**|빌드에 대한 기본 출력 파일의 기본 이름입니다.|
|**$(TargetPath)**|빌드에 대한 기본 출력 파일의 절대 경로 이름(드라이브 + 경로 + 기본 이름 + 파일 확장명으로 정의됨)입니다.|
|**$(VCInstallDir)**|Visual Studio 설치의 C++ 컨텐츠가 들어 있는 디렉터리입니다. 이 속성에는 대상 Visual C++ 도구 집합의 버전이 포함되며, 이 버전은 호스트 Visual Studio와 다를 수 있습니다. 예를 들어 `$(PlatformToolset) = v140`으로 빌드하는 경우 **$(VCInstallDir)** 에는 Visual C++ 2015 설치 경로가 포함됩니다.|
|**$(VSInstallDir)**|Visual Studio을 설치한 디렉터리입니다. 이 속성에는 대상 Visual Studio의 도구 집합 버전이 포함되며, 이 버전은 호스트 Visual Studio와 다를 수 있습니다. 예를 들어 `$(PlatformToolset) = v110`으로 빌드하는 경우 **$(VSInstallDir)** 에는 Visual Studio 2012 설치 경로가 포함됩니다.|
|**$(WebDeployPath)**|웹 배포 루트에서 프로젝트 출력이 속하는 상대 경로입니다. <xref:Microsoft.VisualStudio.VCProjectEngine.VCWebDeploymentTool.RelativePath%2A>와 동일한 값을 반환합니다.|
|**$(WebDeployRoot)**|**\<localhost>** 의 위치에 대한 절대 경로입니다. 예를 들어 c:\inetpub\wwwroot입니다.|

## <a name="obsolete-macros"></a>사용되지 않는 매크로

Visual Studio 2008에서 Visual Studio 2010으로 가면서 C++ 빌드 시스템이 크게 변경되었습니다. 이전 프로젝트 형식에 사용된 많은 매크로가 새 매크로로 변경되었습니다. 이러한 매크로는 더 이상 사용되지 않거나 하나 이상의 동일한 속성 또는 [항목 메타데이터 매크로](/visualstudio/msbuild/itemmetadata-element-msbuild)(**%(**_name_**)**) 값으로 대체되었습니다. "마이그레이션됨"으로 표시된 매크로는 프로젝트 마이그레이션 도구로 업데이트할 수 있습니다. 매크로를 포함하는 프로젝트가 Visual Studio 2008 이하 버전에서 Visual Studio 2010으로 마이그레이션된 경우 Visual Studio는 매크로를 해당하는 현재 매크로로 변환합니다. 최신 버전의 Visual Studio는 프로젝트를 Visual Studio 2008 이하 버전에서 새 프로젝트 형식으로 변환할 수 없습니다. 이러한 프로젝트는 먼저 Visual Studio 2010으로 변환한 다음, 결과를 최신 버전의 Visual Studio로 변환하는 2단계 변환을 거쳐야 합니다. 자세한 내용은 [잠재적인 업그레이드 문제 개요](../../porting/overview-of-potential-upgrade-issues-visual-cpp.md)를 참조하세요.

|매크로|설명|
|-----------|-----------------|
|**$(InputDir)**|(마이그레이션됨.) 입력 파일의 디렉터리(드라이브 + 경로로 정의됨)이며, 뒤에 백슬래시 '\\'가 포함됩니다. 프로젝트가 입력인 경우 이 매크로는 **$(ProjectDir)** 에 해당합니다.|
|**$(InputExt)**|(마이그레이션됨.) 입력 파일의 파일 확장명입니다. 파일 확장명 앞에 '.'을 포함합니다. 프로젝트가 입력인 경우 이 매크로는 **$(ProjectExt)** 에 해당합니다. 원본 파일의 경우 이는 **%(Extension)** 입니다.|
|**$(InputFileName)**|(마이그레이션됨.) 입력 파일의 파일 이름(기본 이름 + 파일 확장명으로 정의됨)입니다. 프로젝트가 입력인 경우 이 매크로는 **$(ProjectFileName)** 에 해당합니다. 원본 파일의 경우 이는 **%(Identity)** 입니다.|
|**$(InputName)**|(마이그레이션됨.) 입력 파일의 기본 이름입니다. 프로젝트가 입력인 경우 이 매크로는 **$(ProjectName)** 에 해당합니다. 원본 파일의 경우 이는 **%(Filename)** 입니다.|
|**$(InputPath)**|(마이그레이션됨.) 입력 파일의 절대 경로 이름(드라이브 + 경로 + 기본 이름 + 파일 확장명으로 정의됨)입니다. 프로젝트가 입력인 경우 이 매크로는 **$(ProjectPath)** 에 해당합니다. 원본 파일의 경우 이는 **%(FullPath)** 입니다.|
|**$(ParentName)**|이 프로젝트 항목을 포함하는 항목의 이름입니다. 부모 폴더 이름 또는 프로젝트 이름이 됩니다.|
|**$(SafeInputName)**|파일 확장명을 뺀 유효한 클래스 이름으로 파일의 이름입니다. 이 속성에는 정확한 해당 사항이 없습니다.|
|**$(SafeParentName)**|유효한 이름 형식인 직계 부모의 이름입니다. 예를 들어 양식은 .resx 파일의 부모입니다. 이 속성에는 정확한 해당 사항이 없습니다.|
|**$(SafeRootNamespace)**|프로젝트 마법사에서 코드를 추가할 네임스페이스 이름입니다. 이 네임스페이스 이름에는 유효한 C++ 식별자에 사용할 수 있는 문자만 포함됩니다. 이 속성에는 정확한 해당 사항이 없습니다.|

## <a name="see-also"></a>참고자료

- [C + +-visual Studio 프로젝트](../creating-and-managing-visual-cpp-projects.md)
- [Visual C++ 이식 및 업그레이드 가이드](../../porting/visual-cpp-porting-and-upgrading-guide.md)
- [잠재적인 업그레이드 문제 개요](../../porting/overview-of-potential-upgrade-issues-visual-cpp.md)
