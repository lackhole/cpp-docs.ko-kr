---
title: Visual C++ 프로젝트용으로 만들어지는 파일 형식
ms.date: 04/08/2019
helpviewer_keywords:
- header files [C++], Visual Studio projects
- ActiveX controls [C++], Help files
- def files
- project items [C++], files
- Visual Studio C++ projects, files and directories
- resource files, created by wizard
- files [C++], extensions
- Help files, for ActiveX controls
- Web projects [C++], adding items
- .def files
- licensing ActiveX controls
ms.assetid: 2b0ee2e0-ae81-4185-9bb9-11da3c99a283
ms.openlocfilehash: eee53acbb8b0b8432a7d5819fb773b616f0e8897
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62271168"
---
# <a name="file-types-created-for-visual-studio-c-projects"></a>Visual Studio에 대해 만들어진 형식 파일 C++ 프로젝트

파일의 많은 형식은 기존의 데스크톱 응용 프로그램에 대 한 Visual Studio 프로젝트와 연결 됩니다. 프로젝트 형식 및 마법사에서 선택한 옵션에 따라 프로젝트에 포함되는 실제 파일이 달라집니다.

- [프로젝트 및 솔루션 파일](project-and-solution-files.md)

- [CLR 프로젝트](files-created-for-clr-projects.md)

- [ATL 프로그램 또는 컨트롤 소스 및 헤더 파일](atl-program-or-control-source-and-header-files.md)

- [MFC 프로그램 또는 컨트롤 소스 및 헤더 파일](mfc-program-or-control-source-and-header-files.md)

- [미리 컴파일된 헤더 파일](../creating-precompiled-header-files.md)

- [리소스 파일](resource-files-cpp.md)

- [도움말 파일(WinHelp)](help-files-winhelp.md)

- [힌트 파일](hint-files.md)

Visual Studio 프로젝트를 만들면 새 솔루션을 만들 수 있습니다 또는 기존 솔루션에 프로젝트를 추가할 수 있습니다. 중요 애플리케이션은 일반적으로 솔루션의 여러 프로젝트로 개발됩니다.

프로젝트는 보통 EXE 또는 DLL을 생성합니다. 프로젝트; 서로 종속 될 수 있습니다. 빌드 프로세스 동안 Visual Studio 환경 내에서 및 프로젝트 간의 종속성을 확인합니다. 각 프로젝트에는 일반적으로 core 소스 코드에 있습니다. 프로젝트의 종류에 따라 다양 한 프로젝트를 포함 하는 다른 많은 파일 수 있습니다. 이러한 파일의 내용은 파일 확장명으로 표시됩니다. Visual Studio 개발 환경에서는 빌드하는 동안 파일 확장명을 사용하여 파일 내용을 처리할 방법을 결정합니다.

다음 표에서 Visual Studio 프로젝트에서는 공통 파일을 보여 줍니다. 및 파일 확장명을 사용 하 여이 식별 합니다.

|파일 확장명|형식|목차|
|--------------------|----------|--------------|
|.asmx|소스|배포 파일|
|.asp|Source|Active Server Page 파일|
|.asp|프로젝트|애플리케이션 템플릿 프로젝트 파일|
|.bmp, .dib, .gif, .jpg, .jpe, .png|리소스|일반 이미지 파일|
|.bsc|컴파일|브라우저 코드 파일|
|.cpp, .c|Source|애플리케이션의 기본 소스 코드 파일|
|.cur|리소스|커서 비트맵 그래픽 파일|
|.dbp|프로젝트|데이터베이스 프로젝트 파일|
|.disco|Source|동적 검색 문서 파일. XML Web services 검색을 처리합니다.|
|.exe, .dll|프로젝트|실행 파일 또는 동적 연결 라이브러리 파일|
|.h|Source|헤더(포함) 파일|
|.htm, .html, .xsp, .asp, .htc, .hta, .xml|리소스|공용 웹 파일|
|.HxC|프로젝트|도움말 프로젝트 파일|
|.ico|리소스|아이콘 비트맵 그래픽 파일|
|.idb|컴파일|소스 파일과 클래스 정의 간의 종속성 정보를 포함 하는 상태 파일. 증분 컴파일 중 컴파일러에서 사용할 수 있습니다. .idb 이름을 지정하려면 [/Fd](fd-program-database-file-name.md) 컴파일러 옵션을 사용합니다.|
|.idl|컴파일|IDL(Interface Definition Language) 파일. 자세한 내용은 Windows SDK의 [인터페이스 정의(IDL) 파일](/windows/desktop/Rpc/the-interface-definition-language-idl-file)을 참조하세요.|
|.ilk|연결|증분 링크 파일. 자세한 내용은 [증분/](incremental-link-incrementally.md)합니다.|
|.map|연결|링커 정보가 포함된 텍스트 파일. 맵 파일 이름을 지정하려면 [/Fm](fm-name-mapfile.md) 컴파일러 옵션을 사용합니다. 자세한 내용은 [/map](map-generate-mapfile.md)합니다.|
|.mfcribbon-ms|리소스|리본 메뉴에는 MFC 단추, 컨트롤 및 특성을 정의 하는 XML 코드를 포함 하는 리소스 파일입니다. 자세한 내용은 [Ribbon Designer](../../mfc/ribbon-designer-mfc.md)을 참조하십시오.|
|.obj, .o||컴파일되었지만 연결되지 않은 개체 파일|
|.pch|디버그|미리 컴파일된 헤더 파일|
|.rc, .rc2|리소스|리소스를 생성하는[리소스 스크립트 파일](../../windows/working-with-resource-files.md) |
|.sbr|컴파일|소스 브라우저 중간 파일. [BSCMAKE](bscmake-options.md)의 입력 파일입니다.|
|.sln|솔루션|[솔루션](/visualstudio/ide/solutions-and-projects-in-visual-studio) 파일|
|.suo|솔루션|솔루션 옵션 파일|
|.txt|리소스|텍스트 파일(일반적으로 "추가 정보" 파일)|
|.vap|프로젝트|Visual Studio Analyzer 프로젝트 파일|
|.vbg|솔루션|호환 가능한 프로젝트 그룹 파일|
|.vbp, .vip, .vbproj|프로젝트|Visual Basic 프로젝트 파일|
|.vcxitems|프로젝트|여러 C++ 프로젝트 간에 코드 파일을 공유하는 공유 항목 프로젝트입니다. 자세한 내용은 [프로젝트 및 솔루션 파일](project-and-solution-files.md)합니다.|
|.vcxproj|프로젝트|Visual Studio 프로젝트 파일입니다. 자세한 내용은 [프로젝트 및 솔루션 파일](project-and-solution-files.md)합니다.|
|.vcxproj.filters|프로젝트|솔루션 탐색기를 사용 하 여 파일을 프로젝트에 추가할 때 사용 합니다. 필터 파일의 파일 이름 확장명에 따라 파일을 추가 하려면 솔루션 탐색기 트리 뷰에서 위치를 정의 합니다.|
|.vdproj|프로젝트|Visual Studio 배포 프로젝트 파일|
|.vmx|프로젝트|매크로 프로젝트 파일|
|.vup|프로젝트|유틸리티 프로젝트 파일.|

Visual Studio와 관련된 다른 파일에 대한 자세한 내용은 [Visual Studio.NET의 파일 형식 및 파일 확장명](/visualstudio/ide/reference/project-and-solution-file-types)을 참조하세요.

프로젝트 파일은 솔루션 탐색기에서 폴더로 구성됩니다. Visual Studio 소스 파일과 헤더 파일에 리소스 파일에 대 한 폴더 만들지만 이러한 폴더를 다시 구성 하거나 새로 만들 수 있습니다. 폴더를 사용하여 프로젝트 계층 내에서 파일의 논리적 클러스터를 명시적으로 구성할 수 있습니다. 예를 들어 모든 사용자 인터페이스 소스 파일을 포함 하는 폴더를 만들 수 있습니다. 또는 사양, 문서 또는 테스트 도구 모음에 대 한 폴더입니다. 모든 파일 폴더 이름은 고유해야 합니다.

프로젝트에 항목을 추가 하면 해당 프로젝트에 대 한 모든 구성에는 항목을 추가 합니다. 항목 인지 여부를 해당 빌드 가능한 추가 됩니다. 예를 들어 MyProject라는 프로젝트가 있는 경우 항목을 추가하면 디버그 및 릴리스 프로젝트 구성 둘 다에 항목이 추가됩니다.

## <a name="see-also"></a>참고자료

[만들기 및 Visual Studio 관리 C++ 프로젝트](../creating-and-managing-visual-cpp-projects.md)<br>
[Visual Studio C++ 프로젝트 형식](visual-cpp-project-types.md)<br>