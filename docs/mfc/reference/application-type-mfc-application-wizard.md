---
title: MFC 애플리케이션 마법사, 애플리케이션 종류
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.exe.apptype
helpviewer_keywords:
- static libraries, MFC
ms.assetid: c3f62b0e-3f13-42c5-9859-d3890d0c3e1d
ms.openlocfilehash: 2c7fc8c1d04105bbdf2fe05ff65283e1beeda810
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65446441"
---
# <a name="application-type-mfc-application-wizard"></a>MFC 애플리케이션 마법사, 애플리케이션 종류

이 페이지를 사용 합니다 [MFC 응용 프로그램 마법사](../../mfc/reference/mfc-application-wizard.md) 디자인 하 고 새 MFC 응용 프로그램에 기본 기능을 추가 합니다.

- **응용 프로그램 종류**

  응용 프로그램에서 만들려고 할 수 있는 문서 지원의 형식을 지정 합니다. 선택한 응용 프로그램 형식의 응용 프로그램에 사용할 수 있는 사용자 인터페이스 옵션을 결정 합니다. 참조 [MFC 응용 프로그램 마법사, 사용자 인터페이스 기능](../../mfc/reference/user-interface-features-mfc-application-wizard.md) 자세한 내용은 합니다.

   문서 유형에 대 한 자세한 내용은 다음을 참조 하세요.

  - [SDI 및 MDI](../../mfc/sdi-and-mdi.md)

  - [프레임 창](../../mfc/frame-windows.md)

  - [프레임 창 클래스](../../mfc/frame-window-classes.md)

  - [문서, 뷰 및 프레임워크](../../mfc/documents-views-and-the-framework.md)

  - [대화 상자](../../mfc/dialog-boxes.md)

  |옵션|설명|
  |------------|-----------------|
  |**단일 문서**|뷰 클래스를 기반으로 응용 프로그램에 대 한 단일 문서 인터페이스 (SDI) 아키텍처를 만듭니다 [CView 클래스](../../mfc/reference/cview-class.md)합니다. 뷰에 대 한 기본 클래스를 변경할 수는 [MFC 응용 프로그램 마법사, 생성 된 클래스](../../mfc/reference/generated-classes-mfc-application-wizard.md) 마법사의 페이지입니다. 예를 들어 사용 form 기반 응용 프로그램을 만들려면 [CFormView 클래스](../../mfc/reference/cformview-class.md) 뷰 클래스에 대 한 합니다.<br /><br /> 이 유형의 응용 프로그램에서는 문서 프레임 창 하나의 문서를 포함할 수 있습니다.|
  |**여러 문서**|뷰 클래스를 기반으로 응용 프로그램에 대 한 여러 문서 MDI (인터페이스) 아키텍처를 만들고 `CView`합니다. 뷰에 대 한 기본 클래스를 변경할 수는 **생성 된 클래스** 마법사의 페이지입니다. 폼 기반 응용 프로그램을 만들려면 사용 예를 들어 `CFormView` 뷰 클래스에 대 한 합니다.<br /><br /> 이 유형의 응용 프로그램에서 windows 문서 프레임 창은 여러 자식을 포함할 수 있습니다.|
  |**탭된 문서**|별도 탭에서 각 문서를 배치합니다.|
  |**대화 상자 기반**|대화 상자 클래스를 기반으로 하는 응용 프로그램에 대 한 대화 상자 기반 아키텍처를 만들고 `CDialog`합니다. (선택 상자는 HTML 대화 상자를 만들려면 **사용 하 여 HTML 대화**.)|
  |**HTML 대화 상자를 사용 합니다.**|대화 상자 응용 프로그램에만 합니다. 대화 상자 클래스에서 파생 [CDHtmlDialog 클래스](../../mfc/reference/cdhtmldialog-class.md) of [CDialog 클래스](../../mfc/reference/cdialog-class.md)합니다. 이 확인란 `CDHtmlDialog` 에 나열 된는 **기본 클래스** 상자에 [MFC 응용 프로그램 마법사, 생성 된 클래스](../../mfc/reference/generated-classes-mfc-application-wizard.md) 마법사의 페이지입니다.<br /><br /> `CDHtmlDialog`-HTML 기반 대화 상자를 표시 하는 파생 된 대화 상자, HTML 사용 하 여 데이터를 교환 컨트롤과 HTML 이벤트를 처리 합니다.|
  |**여러 최상위 문서**|뷰 클래스를 기반으로 응용 프로그램에 대 한 여러 최상위 아키텍처를 만들고 `CView`합니다.<br /><br /> 이 유형의 응용 프로그램을 클릭할 때 **새로 만들기** (또는 **새 프레임**)에 **파일** 메뉴 응용 프로그램이 부모는 암시적으로 바탕 화면 창을 만듭니다. 새 문서 프레임 작업 표시줄에 표시 되며 응용 프로그램 창의 클라이언트 영역에 제한 되지 않습니다.|

- **문서/뷰 아키텍처 지원**

  사용 하 여 응용 프로그램에서 문서/뷰 아키텍처를 포함할지 여부를 지정 합니다 [CDocument 클래스](../../mfc/reference/cdocument-class.md) 하며 [CView 클래스](../../mfc/reference/cview-class.md) (기본값). 비 MFC 응용 프로그램을 이식 하는 경우 또는 컴파일된 실행 파일의 크기를 줄이고 싶은 경우이 확인란의 선택을 취소 합니다. 기본적으로 문서/뷰 아키텍처 없이 응용 프로그램에서 파생 됩니다 [CWinApp 클래스](../../mfc/reference/cwinapp-class.md), 디스크 파일에서 문서를 열에 대 한 MFC 지원을 포함 하지 않습니다.

- **리소스 언어**

  리소스의 언어를 설정합니다. Visual Studio가 설치 된 시스템에서 사용할 수 있는 언어를 표시 합니다. 시스템 언어 이외의 언어를 선택 하려는 경우 해당 언어에 대 한 적절 한 템플릿 폴더 이미 설치 되어 있어야 합니다.

  선택한 언어에 반영 됩니다는 **지역화 된 문자열** 옵션을 [MFC 응용 프로그램 마법사, 문서 템플릿 문자열](../../mfc/reference/document-template-strings-mfc-application-wizard.md) 마법사의 페이지입니다.

- **유니코드 라이브러리를 사용 합니다.**

  유니코드 또는 비유니코드 버전의 MFC 라이브러리가 사용 되는지 여부를 지정 합니다.

- **프로젝트 스타일**

  응용 프로그램에 표준 MFC, 파일 탐색기, Visual Studio 또는 Office 아키텍처 및 표시 여부를 나타냅니다. 자세한 내용은 [파일 탐색기 스타일 MFC 응용 프로그램을 만드는](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md)합니다.

  |옵션|설명|
  |------------|-----------------|
  |**MFC standard**|표준 MFC 응용 프로그램 아키텍처를 제공합니다.|
  |**파일 탐색기**|여기서는 왼쪽된 창 분할기 창을 사용 하 여 파일 탐색기와 같은 응용 프로그램을 구현 하는 [CTreeView 클래스](../../mfc/reference/ctreeview-class.md) 오른쪽 창은 및를 [CListView 클래스](../../mfc/reference/clistview-class.md)합니다.|
  |**Visual Studio**|4 개의 도킹 가능한 창을 포함 하는 Visual Studio와 유사한 응용 프로그램을 구현 (**파일 보기**를 **클래스 뷰**를 **속성**, 및 **출력**)에서 파생 되는 [CDockablePane Class](../../mfc/reference/cdockablepane-class.md) 에서 파생 되는 주 프레임 창이 [CMDIFrameWndEx 클래스](../../mfc/reference/cmdiframewndex-class.md) (기본값).|
  |**Office**|파생 되는 리본을 포함 하는 Office와 비슷한 응용 프로그램 구현 [CMFCRibbonBar 클래스](../../mfc/reference/cmfcribbonbar-class.md)에서 파생 되는 Outlook 표시줄 [CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md)에서 파생 되는 캡션 표시줄 [CMFCCaptionBar 클래스](../../mfc/reference/cmfccaptionbar-class.md), 및에서 파생 되는 주 프레임 [CMDIFrameWndEx 클래스](../../mfc/reference/cmdiframewndex-class.md)합니다.|

- **비주얼 스타일 및 색**

  응용 프로그램의 비주얼 스타일을 결정합니다. 다음 옵션을 사용할 수 있습니다.

  - **Windows 네이티브/기본값**

  - **Office 2003**

  - **Visual Studio 2005**

  - **Office 2007 (파랑 테마)**

  - **Office 2007 (검정 테마)**

  - **Office 2007 (은색 테마)**

  - **Office 2007 (바다색 테마)**

- **비주얼 스타일 전환 사용**

  여부 사용자가 변경할 수 런타임 시 응용 프로그램의 비주얼 스타일을 일반적으로 메뉴 또는 리본 메뉴에서 적절 한 비주얼 스타일을 선택 하 여 지정 합니다.

- **MFC 사용**

  MFC 라이브러리에 연결 하는 방법을 지정 합니다. 기본적으로 MFC 공유 DLL로 연결 됩니다.

  |옵션|설명|
  |------------|-----------------|
  |**공유 DLL에서 MFC 사용**|MFC 라이브러리를 공유 DLL로 응용 프로그램에 연결합니다. 응용 프로그램에서는 런타임에 MFC 라이브러리를 호출 합니다. 이 옵션에는 MFC 라이브러리를 사용 하는 여러 실행 파일의 구성 된 응용 프로그램의 디스크 및 메모리 요구 사항이 줄어듭니다. MFC 및 Win32 응용 프로그램 (기본값) DLL의 함수를 호출할 수 있습니다.|
  |**정적 라이브러리에서 MFC 사용**|빌드 시 정적 MFC 라이브러리에 응용 프로그램을 연결합니다.|

## <a name="see-also"></a>참고자료

[MFC 응용 프로그램 마법사](../../mfc/reference/mfc-application-wizard.md)<br/>
[시각적 개체에 대해 만들어지는 형식 파일 C++ 프로젝트](../../build/reference/file-types-created-for-visual-cpp-projects.md)
