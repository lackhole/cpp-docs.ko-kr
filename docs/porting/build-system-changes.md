---
title: Visual Studio 2010의 시스템 변경 빌드
ms.date: 11/04/2016
f1_keywords:
- vc.msbuild.changes
helpviewer_keywords:
- Build system changes, project file (.vcxprog)
- Build system changes, custom build rules
- Build system changes, MSBuild
- MSBuild, build system changes
- Build system changes, .vsprops
- Build system changes, $(Inherit)
- Build system changes, $(NoInherit)
ms.assetid: e564d95f-a6cc-4d97-b57e-1a71daf66f4a
ms.openlocfilehash: c3e51aa7e5a4346137e94191b551b0d53452e460
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65449015"
---
# <a name="build-system-changes"></a>빌드 시스템 변경 사항

MSBuild 시스템은 Visual Studio C++ 프로젝트를 빌드하는 데 사용됩니다. 하지만 Visual Studio 2008 및 이전 버전에서는 VCBuild 시스템이 사용되었습니다. VCBuild에 의존하는 특정 파일 형식 및 개념은 현재 시스템에 존재하지 않거나 다르게 표현됩니다. 이 문서에서는 현재 빌드 시스템의 차이점을 설명합니다.

## <a name="vcproj-is-now-vcxproj"></a>.vcproj는 이제 .vcxproj입니다.

프로젝트 파일은 더 이상 .vcproj 파일 이름 확장명을 사용하지 않습니다. Visual Studio는 이전 버전의 Visual C++에서 만든 프로젝트 파일을 현재 시스템에서 사용하는 형식으로 자동 변환합니다. 프로젝트를 수동으로 업그레이드하는 방법에 대한 자세한 내용은 [/Upgrade(devenv.exe)](/visualstudio/ide/reference/upgrade-devenv-exe)를 참조하세요.

현재 릴리스에서 프로젝트 파일의 파일 이름 확장명은 .vcxproj입니다.

## <a name="vsprops-is-now-props"></a>.vsprops는 이제 .props입니다.

이전 릴리스에서 *프로젝트 속성 시트*는 .vsprops 파일 이름 확장명을 가진 XML 기반 파일입니다. 프로젝트 속성 시트를 사용하면 컴파일러나 링커 등의 빌드 도구에 대한 스위치를 지정하고 사용자 정의 매크로를 만들 수 있습니다.

현재 릴리스에서 프로젝트 속성 시트의 파일 이름 확장명은 .props입니다.

## <a name="custom-build-rules-and-rules-files"></a>사용자 지정 빌드 규칙 및 .rules 파일

이전 릴리스에서 *규칙 파일*은 .rules 파일 이름 확장명을 가진 XML 기반 파일입니다. 규칙 파일을 사용하면 사용자 지정 빌드 규칙을 정의하고 Visual Studio C++ 프로젝트의 빌드 프로세스에 통합할 수 있습니다. 하나 이상의 파일 이름 확장명과 연결할 수 있는 사용자 지정 빌드 규칙을 사용하면 하나 이상의 출력 파일을 만드는 도구에 입력 파일을 전달할 수 있습니다.

이 릴리스에서는 사용자 지정 빌드 규칙이 .rules 파일 대신 .xml, .props 및 .targets의 세 가지 파일 형식으로 표시됩니다. 이전 버전의 Visual C++를 사용하여 만든 .rules 파일이 현재 릴리스로 마이그레이션되면 해당하는 .xml, .props 및 .targets 파일이 생성되어 원래 .rules 파일과 함께 프로젝트에 저장됩니다.

> [!IMPORTANT]
>  현재 릴리스에서 IDE는 새로운 규칙 생성을 지원하지 않습니다. 따라서 이전 버전의 Visual C++를 사용해서 생성된 프로젝트의 규칙 파일을 사용하는 가장 쉬운 방법은 프로젝트를 현재 버전으로 마이그레이션하는 방법입니다.

## <a name="inheritance-macros"></a>상속 매크로

이전 릴리스에서 **$(Inherit)** 매크로는 프로젝트 빌드 시스템에서 구성된 명령줄에 상속된 속성이 나타나는 순서를 지정합니다. **$(NoInherit)** 매크로는 $(Inherit)이(가) 발생하더라도 무시하고 상속될 모든 속성을 상속되지 않게 합니다. 예를 들어, 기본적으로 $(Inherit) 매크로를 사용하면 [/I (추가 포함 디렉터리)](../build/reference/i-additional-include-directories.md) 컴파일러 옵션을 통해 지정한 파일을 명령줄에 추가할 수 있습니다.

현재 릴리스에서는 하나 이상의 리터럴 값과 속성 매크로를 연결한 속성 값을 지정하여 상속을 지원합니다. **$(Inherit)** 및 **$(NoInherit)** 매크로는 지원되지 않습니다.

다음 예제에서는 세미콜론으로 구분된 목록이 속성 페이지의 속성으로 할당됩니다. 이 목록은 매크로 표기법 **$(** <em>MyProperty</em> **)** 를 사용해서 액세스되는 `MyProperty` 속성 값 및 *\<value>* 리터럴의 연결로 구성됩니다.

```
Property=<value>;$(MyProperty)
```

## <a name="vcxprojuser-files"></a>.vcxproj.user 파일

사용자 파일(.vcxproj.user)은 디버깅 및 배포 설정과 같은 사용자별 속성을 저장합니다. vcxproj.user 파일은 특정 사용자를 위한 모든 프로젝트에 적용됩니다.

## <a name="vcxprojfilters-file"></a>.vcxproj.filters 파일

**솔루션 탐색기**를 사용하여 프로젝트에 파일을 추가하는 경우 필터 파일(.vcxproj.filters)은 **솔루션 탐색기** 트리 뷰에서 해당 파일 이름 확장명에 따라 파일이 추가되는 위치를 정의합니다.

## <a name="vc-directories-settings"></a>VC++ 디렉터리 설정

Visual C++ 디렉터리 설정은 [VC++ 디렉터리 속성 페이지](../ide/vcpp-directories-property-page.md)에 지정됩니다. Visual Studio의 이전 버전에서 디렉터리 설정은 사용자별로 적용되고, 제외된 디렉터리 목록은 sysincl.dat 파일에 지정됩니다.

명령줄에서 [devenv /resetsettings](/visualstudio/ide/reference/resetsettings-devenv-exe)를 실행하면 VC++ 디렉터리 설정을 변경할 수 없습니다. 또한 **도구** 메뉴를 열어 **가져오기 및 내보내기 설정**를 클릭한 다음, **모든 설정 다시 설정** 옵션을 선택하면 설정을 변경할 수 없습니다.

Visual C++의 이전 버전에서 만든 .vssettings 파일에서 VC++ 디렉터리 설정을 마이그레이션합니다. **도구** 메뉴를 열어 **가져오기 및 내보내기 설정**을 클릭하고 **선택한 환경 설정 가져오기**를 선택한 다음, 마법사의 지시를 따릅니다. 또는 Visual Studio를 처음 시작할 때 **기본 환경 설정 선택** 대화 상자에서 **이전 버전에서 적합한 설정을 마이그레이션하고 아래에서 선택한 기본 설정 외에도 적용**을 선택합니다.

## <a name="see-also"></a>참고 항목

[명령줄의 MSBuild - C++](../build/msbuild-visual-cpp.md)
