---
title: '연습: MFC Scribble 응용 프로그램 (파트 1) 업데이트'
ms.date: 09/20/2018
helpviewer_keywords:
- examples [MFC], update existing application
- ribbon UI, porting to
- Office Fluent UI, porting to
- samples [MFC], update existing application
- MFC Feature Pack, update existing application
- walkthroughs [MFC], update existing application
ms.assetid: aa6330d3-6cfc-4c79-8fcb-0282263025f7
ms.openlocfilehash: 213bc8087b58eac232cc8fcfccc88e13785a807e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62358296"
---
# <a name="walkthrough-updating-the-mfc-scribble-application-part-1"></a>연습: MFC Scribble 응용 프로그램 (파트 1) 업데이트

이 연습에서는 리본 메뉴 사용자 인터페이스를 사용하여 기존 MFC 응용 프로그램을 수정하는 방법을 보여 줍니다. Visual Studio는 Office 2007 리본과 Windows 7 Scenic 리본을 지원합니다. 리본 사용자 인터페이스에 대 한 자세한 내용은 참조 하세요. [리본](/windows/desktop/uxguide/cmd-ribbons)합니다.

이 연습에서는 마우스를 사용하여 줄 그리기를 만들 수 있는 클래식 Scribble 1.0 MFC 샘플을 수정합니다. 이 연습 부분에서는 리본 표시줄에 표시되도록 Scribble 샘플을 수정하는 방법을 보여 줍니다. [2 부](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md) 리본 표시줄에 단추를 추가 합니다.

## <a name="prerequisites"></a>전제 조건

합니다 [Scribble 1.0 MFC 샘플](http://download.microsoft.com/download/4/0/9/40946FEC-EE5C-48C2-8750-B0F8DA1C99A8/MFC/general/Scribble.zip.exe)합니다. Visual Studio 2017에 변환에 대 한 도움말을 참조 하세요. [포팅 가이드: MFC Scribble](../porting/porting-guide-mfc-scribble.md)합니다.

##  <a name="top"></a> 섹션

이 연습 부분에는 다음 단원이 있습니다.

- [기본 클래스 대체](#replaceclass)

- [프로젝트에 비트맵 추가](#addbitmap)

- [프로젝트에 리본 리소스 추가](#addribbon)

- [리본 표시줄의 인스턴스 만들기](#createinstance)

- [리본 범주 추가](#addcategory)

- [응용 프로그램의 모양 설정](#setlook)

##  <a name="replaceclass"></a> 기본 클래스 대체

메뉴를 지원하는 응용 프로그램을 리본을 지원하는 응용 프로그램으로 변환하려면 업데이트된 기본 클래스에서 응용 프로그램 프레임 창 및 도구 모음 클래스를 파생시켜야 합니다. (권장 원래 Scribble 샘플을 수정 하지 않는 합니다. 대신 Scribble 프로젝트를 정리, 다른 디렉터리에 복사 및 다음 복사본을 수정 합니다.)

### <a name="to-replace-the-base-classes-in-the-scribble-application"></a>Scribble 응용 프로그램에서 기본 클래스를 대체하려면

1. Scribble.cpp 확인 `CScribbleApp::InitInstance` 호출을 포함 [AfxOleInit](../mfc/reference/ole-initialization.md#afxoleinit)합니다.

1. stdafx.h 파일에 다음 코드를 추가합니다.

    ```cpp
    #include <afxcontrolbars.h>
    ```

1. Scribble.h에서에서 대 한 정의 수정 합니다 `CScribbleApp` 클래스에서 파생 됩니다 [CWinAppEx 클래스](../mfc/reference/cwinappex-class.md)합니다.

    ```cpp
    class CScribbleApp: public CWinAppEx
    ```

1. Windows 응용 프로그램이 사용자 기본 설정 데이터를 저장하기 위해 초기화(.ini) 파일을 사용한 경우 Scribble 1.0이 작성됩니다. 초기화 파일 대신 Scribble을 수정하여 레지스트리에 사용자 기본 설정을 저장합니다. 레지스트리 키와 기본 설정을 설정하려면 `CScribbleApp::InitInstance` 문 뒤의 `LoadStdProfileSettings()`에서 다음 코드를 입력합니다.

    ```cpp
    SetRegistryKey(_T("MFCNext\\Samples\\Scribble2"));
    SetRegistryBase(_T("Settings"));
    ```

1. MDI(다중 문서 인터페이스) 응용 프로그램에 대한 주 프레임은 더 이상 `CMDIFrameWnd` 클래스로부터 파생되지 않습니다. 파생 된 것 대신 합니다 [CMDIFrameWndEx](../mfc/reference/cmdiframewndex-class.md) 클래스입니다.

    mainfrm.h 및 mainfrm.cpp 파일에서 `CMDIFrameWnd`의 모든 참조를 `CMDIFrameWndEx`로 대체합니다.

1. childfrm.h 및 childfrm.cpp 파일에서 `CMDIChildWnd`를 `CMDIChildWndEx`로 대체합니다.

    Childfrm에서. h 파일을 바꿉니다 `CSplitterWnd` 사용 하 여 `CSplitterWndEx`입니다.

1. 새 MFC 클래스를 사용하여 도구 모음 및 상태 표시줄을 수정합니다.

    mainfrm.h 파일에서

    1. `CToolBar` 을 `CMFCToolBar`로 바꿉니다.

    1. `CStatusBar` 을 `CMFCStatusBar`로 바꿉니다.

1. mainfrm.cpp 파일에서

    1. `m_wndToolBar.SetBarStyle`를 `m_wndToolBar.SetPaneStyle`으로 대체합니다.

    1. `m_wndToolBar.GetBarStyle`를 `m_wndToolBar.GetPaneStyle`으로 대체합니다.

    1. `DockControlBar(&m_wndToolBar)`를 `DockPane(&m_wndToolBar)`으로 대체합니다.

1. ipframe.cpp 파일에서 코드의 다음 세 줄을 주석으로 처리합니다.

    ```cpp
    m_wndToolBar.EnableDocking(CBRS_ALIGN_ANY);
    pWndFrame->EnableDocking(CBRS_ALIGN_ANY);
    pWndFrame->DockPane(&m_wndToolBar);
    ```

1. 변경 사항을 저장한 다음 응용 프로그램을 빌드하고 실행합니다.

##  <a name="addbitmap"></a> 프로젝트에 비트맵 추가

이 연습의 다음 네 개의 단계에서는 비트맵 리소스가 필요합니다. 다양 한 방법으로 적절 한 비트맵을 얻을 수 있습니다.

- 사용 된 [리소스 편집기](../windows/resource-editors.md) 사용자 고유의 비트맵을 고안 하 고 합니다. 리소스 편집기를 사용 하 여 Visual Studio와 함께 포함 되며에서 다운로드할 수 있습니다는 이동식 네트워크 그래픽 (.png) 이미지에서 비트맵을 어셈블합니다 합니다 [Visual Studio 이미지 라이브러리](https://docs.microsoft.com/visualstudio/designers/the-visual-studio-image-library)합니다.

    그러나 합니다 **리본** 사용자 인터페이스는 특정 비트맵 지원 투명 이미지가 필요 합니다. 32 비트 픽셀을 여기서 24 비트 색의 빨강, 녹색 및 파랑 구성 요소를 지정 하 고 8 비트 정의 사용 하 여 투명 한 비트맵을 *알파 채널* 색의 투명도 지정 하는 합니다. 현재 리소스 편집기에서는 볼 수는 있지만 32비트 픽셀로 비트맵을 수정할 수 없습니다. 따라서, 리소스 편집기 대신에 외부 이미지 편집기를 사용하여 투명한 비트맵을 조작합니다.

- 프로젝트의 다른 응용 프로그램에서 적절한 리소스 파일을 복사한 다음 해당 파일에서 비트맵을 가져옵니다.

이 연습에서 만든 예제에서 리소스 파일을 복사 [연습: MFC를 사용 하 여 리본 응용 프로그램을 만드는](../mfc/walkthrough-creating-a-ribbon-application-by-using-mfc.md)합니다.

### <a name="to-add-bitmaps-to-the-project"></a>프로젝트에 비트맵을 추가하려면

1. 파일 탐색기를 사용 하 여 리소스 디렉터리에서 다음.bmp 파일 복사 (`res`) 리소스 디렉터리에 리본 예제의 (`res`) Scribble 프로젝트:

   1. Scribble 프로젝트에 main.bmp를 복사합니다.

   1. Scribble 프로젝트에 filesmall.bmp 및 filelarge.bmp를 복사합니다.

   1. Filelarge.bmp 및 filesmall.bmp 파일의 새 복사본 수 있지만 리본 예제에서 복사본을 저장 합니다. 해당 복사본의 이름을 homesmall.bmp 및 homelarge.bmp로 바꾼 다음 Scribble 프로젝트로 복사본을 이동합니다.

   1. Toolbar.bmp 파일의 복사본 수 있지만 리본 예제에서 복사본을 저장 합니다. 복사본의 이름을 panelicons.bmp로 바꾼 다음 Scribble 프로젝트로 복사본을 이동합니다.

1. MFC 응용 프로그램에 대한 비트맵을 가져옵니다. **리소스 뷰**를 두 번 클릭 합니다 **scribble.rc** 노드를 두 번 클릭를 **비트맵** 노드를 차례로 클릭 한 다음 **리소스 추가**. 나타나는 대화 상자에서 클릭 **가져오기**합니다. 로 이동 합니다 `res` 디렉터리에서 찾고 main.bmp 파일을 선택한 다음 클릭 **오픈**.

   main.bmp 비트맵에는 26x26 이미지가 포함됩니다. 비트맵의 ID를 변경 `IDB_RIBBON_MAIN`합니다.

1. 에 연결 된 파일 메뉴에 대 한 비트맵을 가져옵니다 합니다 **응용 프로그램** 단추입니다.

   1. 11 개의 16 x 16 (16 x 176) 포함 된 filesmall.bmp 파일을 가져올 이미지입니다. 비트맵의 ID를 변경 `IDB_RIBBON_FILESMALL`합니다.

   > [!NOTE]
   > 처음 8 개의 16x16 이미지 (16 x 128)만 해야 하므로 128 176에서이 비트맵의 오른쪽에 있는 너비를 필요에 따라 자를 수 있습니다.

   1. Filelarge.bmp를 9 개 32 x 32 (32 x 288)를 포함 하는 이미지입니다. 비트맵의 ID를 변경 `IDB_RIBBON_FILELARGE`합니다.

1. 리본 범주와 패널에 대한 비트맵을 가져옵니다. 리본 표시줄의 각 탭은 범주이며 텍스트 레이블 및 선택적 이미지로 구성되어 있습니다.

   1. 11 개의 작은 단추 비트맵에 대 한 16x16 이미지가 포함 된 homesmall.bmp 비트맵을 가져옵니다. 비트맵의 ID를 변경 `IDB_RIBBON_HOMESMALL`합니다.

   1. 큰 단추 비트맵에 대 한 이미지를 32 x 32를 9 개 포함 된 homelarge.bmp 비트맵을 가져옵니다. 비트맵의 ID를 변경 `IDB_RIBBON_HOMELARGE`합니다.

1. 크기가 조정된 리본 패널의 비트맵을 가져옵니다. 전체 창을 표시하기에 리본이 너무 작다면 크기 조정 작업 후에 이러한 비트맵 또는 패널 아이콘이 사용됩니다.

   1. 8개의 16x16 이미지가 포함된 panelicons.bmp 비트맵을 가져옵니다. 에 **속성** 기간 합니다 **비트맵 편집기**, 64 (16 x 64) 비트맵의 너비를 조정 합니다. 비트맵의 ID를 변경 `IDB_PANEL_ICONS`합니다.

   > [!NOTE]
   > 처음 네 개의 16 x 16 이미지 (16 x 64)만 해야 하므로 64 128에서이 비트맵의 오른쪽에 있는 너비를 필요에 따라 자를 수 있습니다.

##  <a name="addribbon"></a> 프로젝트에 리본 리소스 추가

리본 메뉴를 사용 하는 응용 프로그램 메뉴를 사용 하는 응용 프로그램으로 변환 하면 제거 하거나 기존 메뉴를 사용 하지 않도록 설정할 필요가 없습니다. 리본 리소스를 만들면, 리본 단추를 추가 및 기존 메뉴 항목을 사용 하 여 새 단추를 연결 합니다. 메뉴는 더 이상 표시, 메시지의 리본 메뉴 모음에서 메뉴를 통해 라우팅됩니다 및 메뉴 바로 가기는 계속 작동 합니다.

리본을 구성 합니다 **응용 프로그램** 리본 메뉴의 왼쪽 상단에 있는 큰 단추는 단추와 하나 이상의 범주 탭 합니다. 각 범주 탭에는 리본 단추 및 컨트롤에 대한 컨테이너 역할을 하는 패널이 하나 이상 포함되어 있습니다. 다음 절차에서는 리본 리소스를 만들고 사용자 지정 하는 방법을 보여 줍니다.는 **응용 프로그램** 단추입니다.

### <a name="to-add-a-ribbon-resource-to-the-project"></a>프로젝트에 리본 리소스를 추가하려면

1. Scribble 프로젝트에서 선택한 **솔루션 탐색기**를 **프로젝트** 메뉴에서 클릭 **리소스 추가**합니다.

1. 에 **리소스 추가** 대화 상자에서 **리본** 클릭 하 고 **새**합니다.

   Visual Studio에서는 리본 리소스를 만들어 디자인 뷰에서 엽니다. 리본 리소스 ID가 `IDR_RIBBON1`에 표시 됩니다 **리소스 뷰**합니다. 리본에는 범주 하나와 패널 하나가 포함되어 있습니다.

1. 사용자 지정할 수 있습니다 합니다 **응용 프로그램** 해당 속성을 수정 하 여는 단추입니다. 이 코드에 사용되는 메시지 ID는 Scribble 1.0에 대한 메뉴에 이미 정의되어 있습니다.

1. 디자인 뷰를 클릭 합니다 **응용 프로그램** 해당 속성을 표시 하는 단추입니다. 속성 값을 다음과 같이 변경 합니다. **이미지** 하 `IDB_RIBBON_MAIN`, **프롬프트** 에 `File`, **키** 에 `f`, **큰 이미지** 에 `IDB_RIBBON_FILELARGE`, 및 **Small Images** 하려면 `IDB_RIBBON_FILESMALL`합니다.

1. 클릭할 때 나타나는 메뉴를 만들려면 다음과 같이 수정 합니다 **응용 프로그램** 단추입니다. 줄임표 (**...** ) 옆에 **주 항목** 열려는 합니다 **항목 편집기**합니다.

   1. 사용 하 여는 **항목** 형식 **단추** 선택 **추가** 단추를 추가 합니다. 변경 **캡션** 하 `&New`, **ID** 에 `ID_FILE_NEW`, **이미지** 에 `0`, **큰 이미지** 에`0`.

   1. 클릭 **추가** 단추를 추가 합니다. 변경 **캡션** 하 `&Save`, **ID** 에 `ID_FILE_SAVE`, **이미지** 에 `2`, 및 **큰 이미지** 를`2`.

   1. 클릭 **추가** 단추를 추가 합니다. 변경 **캡션** 하 `Save &As`, **ID** 에 `ID_FILE_SAVE_AS`, **이미지** 에 `3`, 및 **큰 이미지** 를`3`.

   1. 클릭 **추가** 단추를 추가 합니다. 변경 **캡션** 하 `&Print`, **ID** 에 `ID_FILE_PRINT`, **이미지** 에 `4`, 및 **큰 이미지** 를`4`.

   1. 변경 된 **항목** 형식을 **구분 기호** 클릭 하 고 **추가**합니다.

   1. 변경 된 **항목** 형식을 **단추**합니다. 클릭 **추가** 다섯 번째 단추를 추가 합니다. 변경 **캡션** 하 `&Close`, **ID** 에 `ID_FILE_CLOSE`, **이미지** 에 `5`, 및 **큰 이미지** 를`5`.

1. 아래에 하위 메뉴가 만들려면 다음과 같이 수정 합니다 **인쇄** 이전 단계에서 만든 단추.

   1. 클릭는 **인쇄** 단추를 변경 합니다 **항목** 형식을 **레이블**, 클릭 하 고 **삽입**. 변경 **캡션** 에 `Preview and print the document`입니다.

   1. 클릭는 **인쇄** 단추를 변경 합니다 **항목** 형식을 **단추**, 클릭 **삽입**. 변경 **캡션** 하 `&Print`, **ID** 에 `ID_FILE_PRINT`, **이미지** 에 `4`, 및 **큰 이미지** 를`4`.

   1. 클릭 합니다 **인쇄** 단추를 클릭 한 다음 **삽입** 단추를 추가 합니다. 변경 **캡션** 하 `&Quick Print`, **ID** 에 `ID_FILE_PRINT_DIRECT`, **이미지** 에 `7`, 및 **큰 이미지** 를`7`.

   1. 클릭 합니다 **인쇄** 단추를 클릭 **삽입** 다른 단추를 추가 합니다. 변경 **캡션** 하 `Print Pre&view`, **ID** 에 `ID_FILE_PRINT_PREVIEW`, **이미지** 에 `6`, 및 **큰 이미지** 를`6`.

   1. 이제 수정한 합니다 **주 항목**합니다. 클릭 **닫습니다** 종료 합니다 **항목 편집기**합니다.

1. 다음과 같이 수정 맨 아래에 나타나는 종료 단추가 만듭니다는 **응용 프로그램** 단추 메뉴입니다.

   1. 에 **속성** 창에서 줄임표 (**...** ) 옆에 **단추** 열려는 합니다 **항목 편집기**합니다.

   1. 사용 하 여는 **항목** 형식 **단추** 선택 **추가** 단추를 추가 합니다. 변경 **캡션** 하 `E&xit`, **ID** 에 `ID_APP_EXIT`, **이미지** 에 `8`입니다.

   1. 수정한 합니다 **단추가**합니다. 클릭 **닫습니다** 종료 합니다 **항목 편집기**합니다.

##  <a name="createinstance"></a> 리본 표시줄의 인스턴스 만들기

다음 단계에서는 응용 프로그램 시작 시 리본 표시줄의 인스턴스를 만드는 방법을 보여 줍니다. 응용 프로그램에 리본 표시줄을 추가하려면 mainfrm.h 파일에 리본 표시줄을 선언합니다. 그런 다음 mainfrm.cpp 파일에서 리본 리소스를 로드하는 코드를 작성합니다.

### <a name="to-create-an-instance-of-the-ribbon-bar"></a>리본 표시줄의 인스턴스를 만들려면

1. mainfrm.h 파일에서 주 프레임에 대한 클래스 정의인 `CMainFrame`의 보호된 섹션에 데이터 멤버를 추가합니다. 이 멤버는 리본 표시줄입니다.

    ```cpp
    // Ribbon bar for the application
    CMFCRibbonBar m_wndRibbonBar;
    ```

2. mainfrm.cpp 파일에서 `return` 함수 끝의 마지막 `CMainFrame::OnCreate` 문 앞에 다음 코드를 추가합니다. 리본 표시줄의 인스턴스를 만듭니다.

    ```cpp
    // Create the ribbon bar
    if (!m_wndRibbonBar.Create(this))
    {
        return -1;   //Failed to create ribbon bar
    }
    m_wndRibbonBar.LoadFromResource(IDR_RIBBON1);
    ```

##  <a name="addcategory"></a> 리본 리소스를 사용자 지정

사용자가 만든 했으므로 합니다 **응용 프로그램** 단추를 리본에 요소를 추가할 수 있습니다.

> [!NOTE]
> 이 연습에서는 모든 패널에 대해 동일한 패널 아이콘을 사용합니다. 그러나 다른 아이콘을 표시하기 위해 다른 이미지 목록 인덱스를 사용할 수 있습니다.

### <a name="to-add-a-home-category-and-edit-panel"></a>홈 범주 및 편집 패널을 추가하려면

1. Scribble 프로그램에서는 하나의 범주만 필요로 합니다. 디자인 뷰에서는 **도구 상자**를 두 번 클릭 **범주** 하나를 추가 하 고 해당 속성을 표시 합니다. 속성 값을 다음과 같이 변경 합니다. **캡션** 하 `&Home`, **큰 이미지** 에 `IDB_RIBBON_HOMELARGE`, **작은 이미지** 에 `IDB_RIBBON_HOMESMALL`입니다.

1. 각 리본 범주는 명명된 패널로 구성되어 있습니다. 각 패널 컨트롤 집합이 완료 관련된 작업을 포함합니다. 이 범주에는 한 패널이 있습니다. 클릭 **패널**를 변경한 후 **캡션** 에 `Edit`입니다.

1. 에 **편집** 패널에서 문서의 내용을 지운 담당 단추를 추가 합니다. 이 단추에 대 한 메시지 ID에 이미 정의 된 `IDR_SCRIBBTYPE` 메뉴 리소스입니다. 지정 `Clear All` 단추 텍스트 및 단추를 데코레이팅하는 비트맵의 인덱스입니다. 엽니다는 **도구 상자**, 끌어서 놓습니다를 **단추** 에 **편집** 패널. 단추를 클릭 한 다음 변경 **캡션** 하 `Clear All`, **ID** 에 `ID_EDIT_CLEAR_ALL`, **이미지 인덱스** 에 `0`, **큰 이미지 인덱스**  에 `0`입니다.

1. 변경 사항을 저장한 다음 응용 프로그램을 빌드하고 실행합니다. Scribble 응용 프로그램은 표시되어야 하며 메뉴 모음 대신 창의 위쪽에 리본 표시줄이 있어야 합니다. 리본 표시줄에는 하나의 범주 있어야 **홈**, 및 **홈** 패널 하나 있어야 **편집**합니다. 추가한 리본 단추는 기존 이벤트 처리기를 연결 해야 합니다. 및 **엽니다**를 **닫기**를 **저장**를 **인쇄**, 및 **모두 지우기** 단추는 예상 대로 작동 해야 합니다.

##  <a name="setlook"></a> 응용 프로그램의 모양 설정

A *비주얼 관리자* 는 응용 프로그램에 대 한 모든 그리기를 제어 하는 전역 개체입니다. 원래 Scribble 응용 프로그램은 Office 2000 UI(사용자 인터페이스) 스타일을 사용하므로 해당 응용 프로그램이 더 이상 사용되지 않는 것처럼 보일 수 있습니다. Office 2007 응용 프로그램과 비슷하도록 Office 2007 비주얼 관리자를 사용하여 응용 프로그램을 다시 설정할 수 있습니다.

### <a name="to-set-the-look-of-the-application"></a>응용 프로그램의 모양을 설정하려면

1. 에 `CMainFrame::OnCreate` 함수를 앞에 다음 코드를 입력는 `return 0;` 기본 비주얼 관리자 및 스타일을 변경 하려면.

    ```cpp
    // Set the default manager to Office 2007
    CMFCVisualManager::SetDefaultManager(RUNTIME_CLASS(CMFCVisualManagerOffice2007));
    CMFCVisualManagerOffice2007::SetStyle(CMFCVisualManagerOffice2007::Office2007_LunaBlue);
    ```

1. 변경 사항을 저장한 다음 응용 프로그램을 빌드하고 실행합니다. 응용 프로그램 UI는 Office 2007 UI와 비슷해야 합니다.

## <a name="next-steps"></a>다음 단계

사용 하도록 클래식 Scribble 1.0 MFC 샘플을 수정 했을 **리본 디자이너**합니다. 이제 [2 부](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md)합니다.

## <a name="see-also"></a>참고자료

[연습](../mfc/walkthroughs-mfc.md)<br/>
[연습: MFC 자유 곡선 애플리케이션 업데이트(2부)](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md)
