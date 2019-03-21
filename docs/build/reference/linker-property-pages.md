---
title: 링커 속성 페이지
ms.date: 11/21/2017
f1_keywords:
- VC.Project.VCLinkerTool.RegisterOutput
- VC.Project.VCLinkerTool.OVERWRITEImportLibrary
- VC.Project.VCLinkerTool.UseLibraryDependencyInputs
- VC.Project.VCLinkerTool.LinkLibraryDependencies
helpviewer_keywords:
- per-user redirection
- Linker property pages
ms.assetid: 7e7671e5-a35a-4e67-9bdb-661d75c4d11e
ms.openlocfilehash: 1412531ae0ca9c0f5270df6df7b79ddc9be425ad
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826857"
---
# <a name="linker-property-pages"></a>링커 속성 페이지

이 항목에서는 **일반** 링커 속성 페이지의 다음 속성에 대해 설명합니다. 이 페이지의 Linux 버전은 [링커 속성(Linux C++)](../../linux/prop-pages/linker-linux.md)을 참조하세요.

## <a name="general-page-properties"></a>일반 페이지 속성

### <a name="ignore-import-library"></a>가져오기 라이브러리 무시

이 속성은 이 빌드에서 생성된 .lib 출력을 종속 프로젝트에 연결하지 않도록 링커에 지시합니다. 이렇게 하면 프로젝트 시스템이 빌드될 때 .lib 파일을 생성하지 않는.dll 파일을 처리할 수 있습니다. 프로젝트가 DLL을 생성하는 다른 프로젝트에 종속되는 경우 프로젝트 시스템은 해당 하위 프로젝트에서 생성한 .lib 파일을 자동으로 연결합니다. COM DLL 또는 리소스 전용 DLL을 생성하는 프로젝트에서는 이 기능이 필요하지 않을 수 있습니다. 이러한 DLL에는 의미 있는 내보내기가 없습니다. DLL에 내보내기가 없는 경우 링커는 .lib 파일을 생성하지 않습니다. 디스크에 내보내기 .lib 파일이 없는 경우 프로젝트 시스템에서 링커에게 이 (누락된) DLL로 연결하도록 지시하면 연결이 실패합니다. 이 문제를 해결하려면 **가져오기 라이브러리 무시** 속성을 사용하세요. **예**로 설정하면 프로젝트 시스템이 해당 .lib 파일의 유무를 무시하고, 이 프로젝트에 종속된 모든 프로젝트가 존재하지 않는 .lib 파일과 연결되지 않도록 합니다.

프로그래밍 방식으로 이 속성에 액세스하려면 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreImportLibrary%2A>을 참조하세요.

### <a name="register-output"></a>출력 등록

.dll 프로젝트에서만 유효한 빌드 출력에서 `regsvr32.exe /s $(TargetPath)`를 실행합니다. .exe 프로젝트의 경우 이 속성은 무시됩니다. .exe 출력을 등록하려면 구성에 postbuild 이벤트를 설정하여, 등록된 .exe 파일에 항상 필요한 사용자 지정 등록을 수행합니다.

프로그래밍 방식으로 이 속성에 액세스하려면 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.RegisterOutput%2A>을 참조하세요.

### <a name="per-user-redirection"></a>사용자별 리디렉션

Visual Studio의 등록은 일반적으로 HKEY_CLASSES_ROOT(HKCR)에서 수행되었습니다. Windows Vista 이상의 운영 체제에서 HKCR에 액세스하려면 Visual Studio를 승격된 모드로 실행해야 합니다. 개발자가 승격된 모드로 실행하는 것이 항상 좋은 것은 아니지만 계속 등록 작업을 수행해야 합니다. 사용자별 리디렉션을 사용하면 이 모드에서 실행하지 않고도 등록할 수 있습니다.

사용자별 리디렉션은 HKCR에 대한 모든 쓰기가 HKEY\_CURRENT\_USER(HKCU)로 리디렉션되도록 합니다. 사용자별 리디렉션이 해제되어 있는 경우 프로그램이 HKCR에 쓰려고 할 때 [프로젝트 빌드 오류 PRJ0050](../../error-messages/tool-errors/project-build-error-prj0050.md)이 발생할 수 있습니다.

### <a name="link-library-dependencies"></a>라이브러리 종속성 링크

종속 프로젝트에서 생성한 .lib 파일을 연결할지 여부를 지정합니다. 일반적으로, .lib 파일에 연결하는 것이 좋지만 특정 DLL의 경우는 그렇지 않을 수 있습니다.

파일 이름과 상대 경로를 제공하여 .obj 파일을 지정할 수도 있습니다(예: "..\\..\MyLibProject\MyObjFile.obj"). 미리 컴파일된 헤더(예: pch.h)가 .obj 파일의 소스 코드에 포함되어 있는 경우 pch.obj 파일은 MyObjFile.obj와 같은 폴더에 위치하게 되고 pch.obj를 추가 종속성으로 추가해야 합니다.

### <a name="use-library-dependency-inputs"></a>라이브러리 종속성 입력 사용

대규모 프로젝트에서 종속 프로젝트가 .lib 파일을 생성하면 증분 연결은 사용할 수 없습니다. .lib 파일을 생성하는 많은 종속 프로젝트가 있는 경우 애플리케이션을 빌드하는 데 오랜 시간이 걸릴 수 있습니다. 이 속성을 **예**로 설정하면 프로젝트 시스템은 종속 프로젝트에서 생성한 .lib 파일에 .obj 파일을 연결하여 증분 연결을 사용할 수 있습니다.

액세스 하는 방법에 대 한 자세한 합니다 **일반** 링커 속성 페이지를 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

## <a name="see-also"></a>참고자료

[옵션 대화 상자, 프로젝트 및 솔루션, VC++ 프로젝트 설정](/visualstudio/ide/reference/vcpp-project-settings-projects-and-solutions-options-dialog-box)<br>
[C + + 프로젝트 속성 페이지 참조](property-pages-visual-cpp.md)