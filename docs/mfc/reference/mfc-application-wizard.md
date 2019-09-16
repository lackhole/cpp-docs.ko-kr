---
title: MFC 애플리케이션 마법사
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.exe.overview
helpviewer_keywords:
- MFC Application Wizard
- executable files, creating
ms.assetid: 227ac090-921d-4b2f-be0a-66a5f4cab0d4
ms.openlocfilehash: e97c7a29dd56a69fad99e85c206ca2104fa71798
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65708183"
---
# <a name="mfc-application-wizard"></a>MFC 애플리케이션 마법사

MFC 응용 프로그램 마법사는 컴파일 시 Windows 실행 파일(.exe) 응용 프로그램의 기본 기능을 구현하는 코드를 생성합니다. 해당 방법으로 MFC를 시작하는 응용 프로그램은 C++(.cpp) 파일, 리소스(.rc) 파일, 헤더(.h) 파일 및 프로젝트(.vcxproj) 파일을 포함합니다. 이러한 시작 파일에서 생성되는 코드는 MFC를 기반으로 합니다.

> [!NOTE]
> 선택한 옵션에 따라 마법사는 프로젝트에 추가 파일을 만듭니다. 예를 들어 [고급 기능](../../mfc/reference/advanced-features-mfc-application-wizard.md) 페이지에서 **상황에 맞는 도움말**을 선택하면 마법사는 프로젝트의 도움말 파일을 컴파일하는 데 필요한 파일을 만듭니다. 마법사에서 생성하는 파일에 대한 자세한 내용은 [Visual Studio C++ 프로젝트용으로 생성되는 파일 형식](../../build/reference/file-types-created-for-visual-cpp-projects.md)과 프로젝트의 Readme.txt 파일을 참조합니다.

## <a name="overview"></a>개요

이 마법사 페이지에서는 개발 중인 MFC 응용 프로그램에 대한 현재 응용 프로그램 설정을 설명합니다. 기본적으로 마법사는 다음과 같이 프로젝트를 만듭니다.

- [MFC 애플리케이션 마법사, 애플리케이션 종류](../../mfc/reference/application-type-mfc-application-wizard.md)

   - 프로젝트는 탭으로 이루어진 다중 문서 인터페이스(MDI) 지원을 통해 만들어집니다. 자세한 내용은 [SDI 및 MDI](../../mfc/sdi-and-mdi.md)를 참조합니다.

   - 프로젝트는 [문서/뷰 아키텍처](../../mfc/document-view-architecture.md)를 사용합니다.

   - 프로젝트는 유니코드 라이브러리를 사용 합니다.

   - 프로젝트는 Visual Studio 프로젝트 스타일을 사용하여 만들어지며 비주얼 스타일 전환이 가능합니다.

   - 프로젝트는 공유 DLL에서 MFC를 사용합니다. 자세한 내용은 [Visual Studio에서 C/C++ DLL 만들기](../../build/dlls-in-visual-cpp.md)를 참조합니다.

- [복합 문서 지원, MFC 애플리케이션 마법사](../../mfc/reference/compound-document-support-mfc-application-wizard.md)

   - 프로젝트는 복합 문서를 지원하지 않습니다.

- [문서 템플릿 문자열, MFC 애플리케이션 마법사](../../mfc/reference/document-template-strings-mfc-application-wizard.md)

   - 프로젝트는 기본 문서 템플릿 문자열에 프로젝트 이름을 사용합니다.

- [데이터베이스 지원, MFC 응용 프로그램 마법사](../../mfc/reference/database-support-mfc-application-wizard.md)

   - 프로젝트는 데이터베이스를 지원하지 않습니다.

- [사용자 인터페이스 기능, MFC 애플리케이션 마법사](../../mfc/reference/user-interface-features-mfc-application-wizard.md)

   - 이 프로젝트는 시스템 메뉴, 상태 표시줄, 박스 최대화 및 최소화, **About** 박스, 표준 메뉴 표시줄 및 도킹 도구 모음, 자식 프레임과 같은 표준 Windows 사용자 인터페이스 기능을 구현합니다.

- [고급 기능, MFC 응용 프로그램 마법사](../../mfc/reference/advanced-features-mfc-application-wizard.md)

   - 프로젝트는 인쇄 및 인쇄 미리보기를 지원합니다.

   - 프로젝트는 ActiveX 컨트롤을 지원합니다. 자세한 내용은 [ActiveX 컨트롤 만들기 작업 순서](../../mfc/sequence-of-operations-for-creating-activex-controls.md)를 참조합니다.

   - 프로젝트에서 [Automation](../../mfc/automation.md), [MAPI](../../mfc/mapi-support-in-mfc.md), [Windows 소켓](../../mfc/windows-sockets-in-mfc.md) 또는 Active Accessibility에 대한 지원은 없습니다.

   - 프로젝트는 **탐색기** 도킹 창, **출력** 도킹 창 및 **속성** 도킹 창을 지원합니다.

- [생성된 클래스, MFC 애플리케이션 마법사](../../mfc/reference/generated-classes-mfc-application-wizard.md)

   - 프로젝트 뷰 클래스는 [CView 클래스](../../mfc/reference/cview-class.md)에서 파생됩니다.

   - 프로젝트 응용 프로그램 클래스는 [CWinAppEx 클래스](../../mfc/reference/cwinappex-class.md)에서 파생됩니다.

   - 프로젝트 문서 클래스는 [CDocument 클래스](../../mfc/reference/cdocument-class.md)에서 파생됩니다.

   - 프로젝트 주 프레임 클래스는 [CMDIFrameWndEx 클래스](../../mfc/reference/cmdiframewndex-class.md)에서 파생됩니다.

   - 프로젝트 자식 프레임 클래스는 [CMDIChildWndEx 클래스](../../mfc/reference/cmdichildwndex-class.md)에서 파생됩니다.

이러한 기본 설정을 변경하려면 마법사의 왼쪽 열에서 해당 탭 제목을 클릭하고 표시되는 페이지에서 변경합니다.

MFC 응용 프로그램 프로젝트를 만든 후 C++ [코드 마법사](../../ide/adding-functionality-with-code-wizards-cpp.md)를 사용하여 프로젝트에 개체나 컨트롤을 추가합니다.

## <a name="see-also"></a>참고자료

[MFC 애플리케이션 만들기](../../mfc/reference/creating-an-mfc-application.md)<br/>
[MFC 데스크톱 응용 프로그램](../../mfc/mfc-desktop-applications.md)<br/>
[클래스를 사용하여 Windows 애플리케이션 작성](../../mfc/using-the-classes-to-write-applications-for-windows.md)
