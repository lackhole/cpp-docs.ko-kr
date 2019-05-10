---
title: 도움말 파일(WinHelp)
ms.date: 11/04/2016
helpviewer_keywords:
- file types [C++], WinHelp files
ms.assetid: 4fdcbd66-66b0-4866-894a-fd7b4c2557e4
ms.openlocfilehash: 835300d2fe39688f3b9c41dad801f1a79984c803
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65446553"
---
# <a name="help-files-winhelp"></a>도움말 파일(WinHelp)

다음 파일은 **상황에 맞는 도움말** 확인란을 선택한 다음, MFC 애플리케이션 마법사의 [고급 기능](../../mfc/reference/advanced-features-mfc-application-wizard.md) 페이지에서 **WinHelp 형식**을 선택하여 애플리케이션에 WinHelp 형식의 도움말 지원을 추가하면 만들어집니다.

|파일 이름|디렉터리 위치|솔루션 탐색기 위치|설명|
|---------------|------------------------|--------------------------------|-----------------|
|*Projname*.hpj|*Projname*\hlp|소스 파일|도움말 컴파일러에서 프로그램이나 컨트롤의 도움말 파일을 만드는 데 사용하는 도움말 프로젝트 파일입니다.|
|*Projname*.rtf|*Projname*\hlp|도움말 파일|편집할 수 있는 템플릿 항목과 .hpj 파일을 사용자 지정하는 방법에 대한 정보가 들어 있습니다.|
|*Projname*.cnt|*Projname*\hlp|도움말 파일|Windows 도움말에서 **콘텐츠** 창의 구조를 제공합니다.|
|Makehelp.bat|*Projname*|소스 파일|프로젝트가 컴파일될 때 시스템이 도움말 프로젝트를 빌드하는 데 사용합니다.|
|Print.rtf|*Projname*\hlp|도움말 파일|프로젝트에 인쇄 지원이 포함된 경우 생성됩니다(기본값). 인쇄 명령과 대화 상자를 설명합니다.|
|*.bmp|*Projname*\hlp|리소스 파일|생성된 여러 도움말 파일 항목에 대한 이미지를 포함합니다.|

MFC ActiveX 컨트롤 마법사의 [애플리케이션 설정](../../mfc/reference/application-settings-mfc-activex-control-wizard.md) 탭에서 **도움말 파일 생성**을 선택하여 MFC ActiveX 컨트롤 프로젝트에 WinHelp 지원을 추가할 수 있습니다. MFC ActiveX 컨트롤에 도움말 지원을 추가하면 다음 파일이 프로젝트에 추가됩니다.

|파일 이름|디렉터리 위치|솔루션 탐색기 위치|설명|
|---------------|------------------------|--------------------------------|-----------------|
|*Projname*.hpj|*Projname*\hlp|소스 파일|도움말 컴파일러에서 프로그램이나 컨트롤의 도움말 파일을 만드는 데 사용하는 프로젝트 파일입니다.|
|*Projname*.rtf|*Projname*\hlp|프로젝트|편집할 수 있는 템플릿 항목과 .hpj 파일을 사용자 지정하는 방법에 대한 정보가 들어 있습니다.|
|Makehelp.bat|*Projname*|소스 파일|프로젝트가 컴파일될 때 시스템이 도움말 프로젝트를 빌드하는 데 사용합니다.|
|Bullet.bmp|*Projname*|리소스 파일|표준 도움말 파일 항목에서 글머리 기호 목록을 나타내는 데 사용됩니다.|

## <a name="see-also"></a>참고자료

[시각적 개체에 대해 만들어지는 형식 파일 C++ 프로젝트](file-types-created-for-visual-cpp-projects.md)
