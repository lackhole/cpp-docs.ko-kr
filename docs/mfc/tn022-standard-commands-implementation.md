---
title: 'TN022: 표준 명령 구현'
ms.date: 11/04/2016
f1_keywords:
- vc.commands
helpviewer_keywords:
- ID_PREV_PANE command [MFC]
- ID_APP_EXIT command [MFC]
- ID_NEXT_PANE command [MFC]
- ID_INDICATOR_REC command [MFC]
- ID_WINDOW_SPLIT command [MFC]
- ID_FILE_PRINT_PREVIEW command [MFC]
- ID_WINDOW_CASCADE command [MFC]
- ID_FILE_CLOSE command [MFC]
- ID_FILE_SAVE_COPY_AS command [MFC]
- ID_WINDOW_ARRANGE command [MFC]
- ID_EDIT_FIND command [MFC]
- ID_FILE_OPEN command [MFC]
- ID_FILE_PAGE_SETUP command [MFC]
- ID_OLE_VERB_FIRST command [MFC]
- ID_EDIT_UNDO command [MFC]
- ID_EDIT_CLEAR command [MFC]
- ID_INDICATOR_CAPS command [MFC]
- ID_HELP_INDEX command [MFC]
- commands [MFC], standard
- ID_FILE_PRINT_SETUP command [MFC]
- ID_DEFAULT_HELP command [MFC]
- ID_INDICATOR_SCRL command [MFC]
- ID_FILE_PRINT command [MFC]
- ID_INDICATOR_OVR command [MFC]
- ID_INDICATOR_KANA command [MFC]
- ID_EDIT_COPY command [MFC]
- ID_EDIT_REDO command [MFC]
- ID_EDIT_PASTE command [MFC]
- ID_OLE_INSERT_NEW command [MFC]
- ID_OLE_EDIT_LINKS command [MFC]
- ID_EDIT_PASTE_SPECIAL command [MFC]
- ID_INDICATOR_EXT command [MFC]
- ID_HELP_USING command [MFC]
- standard commands
- ID_VIEW_STATUS_BAR command [MFC]
- ID_FILE_SAVE_AS command [MFC]
- ID_EDIT_CLEAR_ALL command [MFC]
- ID_WINDOW_NEW command [MFC]
- ID_CONTEXT_HELP command [MFC]
- ID_EDIT_REPLACE command [MFC]
- ID_WINDOW_TILE_HORZ command [MFC]
- ID_APP_ABOUT command [MFC]
- TN022
- ID_VIEW_TOOLBAR command [MFC]
- ID_HELP command [MFC]
- ID_WINDOW_TILE_VERT command [MFC]
- ID_EDIT_CUT command [MFC]
- ID_FILE_UPDATE command [MFC]
- ID_EDIT_REPEAT command [MFC]
- ID_FILE_SAVE command [MFC]
- ID_EDIT_PASTE_LINK command [MFC]
- ID_EDIT_SELECT_ALL command [MFC]
- ID_FILE_NEW command [MFC]
- ID_INDICATOR_NUM command
ms.assetid: a7883b46-23f7-4870-ac3a-804aed9258b5
ms.openlocfilehash: 8d568760cc75a4c1f2ddb6dd88108cc830783194
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58775833"
---
# <a name="tn022-standard-commands-implementation"></a>TN022: 표준 명령 구현

> [!NOTE]
>  다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.

이 노트는 MFC 2.0에서 제공 하는 표준 명령 구현을 설명 합니다. 읽기 [기술 참고 21](../mfc/tn021-command-and-message-routing.md) 첫 번째 하므로 다양 한 표준 명령을 구현 하는 데 사용 하는 메커니즘에 설명 합니다.

이 설명은 MFC 아키텍처, Api 및 일반적인 프로그래밍 연습에 대 한 지식이 있다고 가정합니다. 문서화 된 뿐만 아니라 문서화 되지 않은 "구현"만 Api 설명 되어 있습니다. 부터의 기능 또는 MFC 프로그래밍 하는 방법에 대 한 학습을 시작 하는 아닙니다. 시각적 개체에 대 한 참조 C++ 문서화 된 Api의 세부 정보 및 자세한 내용은 합니다.

## <a name="the-problem"></a>문제

MFC 헤더 파일 AFXRES에에서 여러 표준 명령 Id를 정의합니다. 8. 이러한 명령에 대 한 프레임 워크 지원을 달라 집니다. 프레임 워크 클래스에 이러한 명령을 처리 위치와 방법을 이해를 보여 줄 뿐만 아니라 프레임 워크를 내부적으로 작동 하지만 표준 구현을 사용자 지정 구현에 대 한 몇 가지 기술을 설명 하는 방법에 유용한 정보를 제공 하는 방법 사용자 고유의 명령 처리기입니다.

## <a name="contents-of-this-technical-note"></a>이 기술 노트의 내용

각 명령 ID는 두 섹션에서 설명 합니다.

- 제목: 기호화 된 이름을 명령 ID (예를 들어 ID_FILE_SAVE)의 명령 (예: "현재 문서 저장")의 목적은 뒤에 콜론으로 구분 합니다.

- 명령 및 기본 구현은 용도 클래스를 설명 하는 하나 이상의 단락 구현

대부분의 기본 명령 구현 프레임 워크의 기본 클래스 메시지 구조의 prewired 됩니다. 파생된 클래스에서 명시적 연결 해야 하는 일부 명령 구현이 있습니다. 이러한 "노트" 아래에서 설명 합니다. 응용 프로그램 마법사에서 적절 한 옵션을 선택한 경우 이러한 기본 처리기를 생성된 된 기본 응용 프로그램에 연결 됩니다.

## <a name="naming-convention"></a>명명 규칙

표준 명령을 사용 가능한 경우 권장 되는 경우 간단한 명명 규칙을 따릅니다. 대부분의 표준 명령의 표준 위치에서 응용 프로그램의 메뉴 모음에 있습니다. 명령의 바로 가기 이름을 "ID_" 메뉴 항목 이름 뒤에 표준 팝업 메뉴 이름 뒤에 시작 됩니다. 기호화 된 이름은 밑줄 단어 분리를 사용 하 여 대문자로 변환 합니다. 표준 메뉴 항목 이름 없는 명령에 대 한 논리적 명령 이름 "ID_" (예를 들어 ID_NEXT_PANE)부터 정의 됩니다.

"ID_"를 접두사를 사용 하 여 메뉴 항목, 도구 모음 단추 또는 다른 명령 사용자 인터페이스 개체를 바인딩할 수 있도록 만들어진 명령을 나타냅니다. "ID_" 명령을 처리 하는 명령 처리기는 MFC 명령 아키텍처 ON_COMMAND 및 ON_UPDATE_COMMAND_UI 메커니즘을 사용 해야 합니다.

명령 아키텍처에 따라을 활성화 및 비활성화 하는 데 메뉴 특정 코드가 필요 하지 않고는 메뉴 항목에 대 한 표준 "IDM_" 접두사를 사용 하는 것이 좋습니다. 물론 MFC 명령 아키텍처 다음 (도구 모음을 사용 하 여 작동 됩니다) 이므로 더 강력한 명령 처리기를 통해 뿐 아니라 명령 처리기 코드를 재사용 가능 하면 되므로 특정 메뉴 명령의 수는 작은 되어야 합니다.

## <a name="id-ranges"></a>ID 범위

참조 하십시오 [Technical Note 20](../mfc/tn020-id-naming-and-numbering-conventions.md) MFC의 ID 범위 사용에 대 한 자세한 내용은 합니다.

MFC 표준 명령 0xE000에 0xEFFF 범위에 속합니다. 하세요 자제 이러한 Id의 특정 값 되므로 라이브러리의 이후 버전에서 변경 될 수 있습니다.

응용 프로그램 범위의 0x8000 ~ 0xDFFF 명령 정의 해야 합니다.

## <a name="standard-command-ids"></a>표준 명령 Id

각 명령 ID에 대 한 파일이 표시 되는 메시지에 있는 표준 메시지 줄 프롬프트 문자열이 있습니다. RC입니다. 해당 메뉴 프롬프트 문자열 ID를 사용 해야 명령 ID와 동일

- ID_FILE_NEW/비어 있는 새 문서를 만듭니다.

    > [!NOTE]
    >  이를 연결 해야 프로그램 `CWinApp`-이 기능을 사용 하는 클래스의 메시지 맵 파생 합니다.

   `CWinApp::OnFileNew` 응용 프로그램에서이 명령은 문서 템플릿의 수에 따라 다르게 구현합니다. 하나만 있으면 `CDocTemplate`, `CWinApp::OnFileNew` 형식 뿐만 아니라 적절 한 프레임 및 뷰 클래스의 새 문서를 만듭니다.

   둘 이상 있으면 `CDocTemplate`, `CWinApp::OnFileNew` 라는 메시지가 표시 됩니다 수 있도록 하 여 대화 상자 (AFX_IDD_NEWTYPEDLG)를 사용 하 여 사용자 문서 사용할 형식을 선택 합니다. 선택한 `CDocTemplate` 문서를 만드는 데 사용 됩니다.

   ID_FILE_NEW 하나의 일반적인 사용자 지정 다른 및 문서 종류의 그래픽 더 많은 선택 옵션이 제공 하는 것입니다. 이 경우에 구현할 수 있습니다 고유한 `CMyApp::OnFileNew` 대신 메시지 맵에 배치 `CWinApp::OnFileNew`합니다. 기본 클래스 구현을 호출 하지 않아도가 됩니다.

   ID_FILE_NEW의 또 다른 일반적인 사용자 지정 각 형식의 문서를 만들기 위한 별도 명령을 제공 하는 것입니다. 이 경우 새 명령을 Id, 예를 들어 ID_FILE_NEW_CHART ID_FILE_NEW_SHEET 정의 해야 합니다.

- ID_FILE_OPEN 기존 문서를 엽니다.

    > [!NOTE]
    >  이를 연결 해야 프로그램 `CWinApp`-이 기능을 사용 하는 클래스의 메시지 맵 파생 합니다.

   `CWinApp::OnFileOpen` 호출 하는 매우 간단한 구현을 `CWinApp::DoPromptFileName` 뒤에 `CWinApp::OpenDocumentFile` 열려는 파일의 파일 또는 경로 이름입니다. 합니다 `CWinApp` 구현 루틴 `DoPromptFileName` 표준 FileOpen 대화 상자를 시작 하 고 현재 문서 서식 파일에서 가져온 파일 확장명으로 채웁니다.

   ID_FILE_OPEN 하나의 일반적인 사용자 지정 FileOpen 대화 상자를 사용자 지정 하거나 추가 파일 필터를 추가 하는 것입니다. 이 사용자 지정할 수 있는 좋은 사용자 고유의 FileOpen 대화 및 호출을 사용 하 여 기본 구현을 바꿀를 `CWinApp::OpenDocumentFile` 문서 파일 또는 경로 이름입니다. 기본 클래스를 호출할 필요가 없습니다 있습니다.

- ID_FILE_CLOSE 현재 열려 있는 문서를 닫습니다.

   `CDocument::OnFileClose` 호출 `CDocument::SaveModified` 수정 된 경우 다음 문서를 저장 하려면 사용자에 게 프롬프트 `OnCloseDocument`합니다. 문서 삭제를 포함 하 여, 모든 닫는 논리 이루어집니다는 `OnCloseDocument` 루틴입니다.

    > [!NOTE]
    >  WM_CLOSE 메시지 또는 문서 프레임 창으로 전송 SC_CLOSE 시스템 명령을 다르게 ID_FILE_CLOSE 작동 합니다. 창을 닫는 경우에 있는 문서를 보여 주는 마지막 프레임 창을 문서를 닫습니다 됩니다. 문서를 닫는 ID_FILE_CLOSE만 문서를 닫지 않습니다 하지만 문서를 표시 하는 모든 프레임 창을 종료 됩니다.

- ID_FILE_SAVE 현재 문서를 저장합니다.

   도우미 루틴을 사용 하 여 구현 `CDocument::DoSave` 둘 다에 사용 되는 `OnFileSave` 고 `OnFileSaveAs`입니다. 전에 저장 되지 않은 문서를 저장 하는 경우 (즉, 되지 않은 경로 이름을 사용할 경우 FileNew의 경우) 또는 읽기 전용으로 문서에서 읽은 `OnFileSave` 논리는 ID_FILE_SAVE_AS 명령 및 새 파일 이름을 제공 하기 위해 사용자에 게 요청 하는 같은 역할 . 파일 열기 및 저장을 수행 하는 실제 프로세스가 가상 함수를 통해 이루어집니다 `OnSaveDocument`합니다.

   두 가지 일반적인 ID_FILE_SAVE를 사용자 지정할 수 있습니다. 저장 하지 않고 문서에 간단히 사용자 인터페이스에서 ID_FILE_SAVE 메뉴 항목 및 도구 모음 단추를 제거 합니다. 또한 문서에 변경 되지 된 해야 (즉, 호출 하지 `CDocument::SetModifiedFlag`) 프레임 워크 문서를 저장할 발생 하지 않습니다. 디스크 파일을 제외한 임의의 위치에 저장 하는 문서에 대 한 해당 작업에 대 한 새 명령을 정의 합니다.

   경우는 `COleServerDoc`, ID_FILE_SAVE (일반 문서)에 대 한 파일 저장 및 파일 (포함 된 문서)에 대 한 업데이트를 위해 모두 사용 됩니다.

   문서 데이터 개별 디스크 파일에 저장 되지만 기본값을 사용 하지 않을 경우 `CDocument` 직렬화 구현을 재정의 해야 합니다 `CDocument::OnSaveDocument` 대신 `OnFileSave`합니다.

- ID_FILE_SAVE_AS 다른 파일 이름으로 현재 문서를 저장합니다.

   합니다 `CDocument::OnFileSaveAs` 구현에서는 동일한 `CDocument::DoSave` 도우미 루틴으로 `OnFileSave`입니다. `OnFileSaveAs` 명령 문서를 저장 하기 전에 파일 이름이 없는 경우 ID_FILE_SAVE 처럼 처리 됩니다. `COleServerDoc::OnFileSaveAs` 일반 문서 데이터 파일을 저장 하거나 별도 파일로 다른 응용 프로그램에 포함 된 OLE 개체를 나타내는 server 문서를 저장 하는 논리를 구현 합니다.

   ID_FILE_SAVE의 논리를 사용자 지정 하면 ID_FILE_SAVE_AS 비슷한 방식으로 사용자 지정 하고자 또는 "다른 이름으로 저장" 작업 문서에 적용할 수 없습니다. 필요 하지 않은 경우 메뉴 모음에서 메뉴 항목을 제거할 수 있습니다.

- ID_FILE_SAVE_COPY_AS 새 이름으로 복사본 현재 문서를 저장합니다.

   합니다 `COleServerDoc::OnFileSaveCopyAs` 구현은 매우 비슷합니다 `CDocument::OnFileSaveAs`한다는 점을 제외 하는 문서 개체가 연결 되지 않은"" 기본 파일에 저장 한 후입니다. 즉, 메모리 내 문서 수정 된 경우""를 저장 하기 전에, 여전히 "수정입니다". 또한이 명령은 미치지 경로 이름이 나 제목을 문서에 저장 합니다.

- ID_FILE_UPDATE 포함된 된 문서를 저장할 컨테이너를에 알립니다.

   `COleServerDoc::OnUpdateDocument` 구현을 포함 하는 저장 해야 하는 컨테이너를 notifiies 하기만 하면 됩니다. 컨테이너는 포함된 된 개체를 저장 하려면 적절 한 OLE Api를 호출 합니다.

- ID_FILE_PAGE_SETUP 응용 프로그램별 페이지 설치/레이아웃 대화 상자를 호출합니다.

   현재는이 대화 상자에 대 한 표준이 및 프레임 워크는이 명령의 기본 구현이 없습니다.

   이 명령을 구현 하려는 경우이 명령 ID를 사용 하는 것이 좋습니다.

- ID_FILE_PRINT_SETUP 표준 인쇄 설정 대화 상자를 호출 합니다.

    > [!NOTE]
    >  이를 연결 해야 프로그램 `CWinApp`-이 기능을 사용 하는 클래스의 메시지 맵 파생 합니다.

   이 명령은 사용자가 프린터를 사용자 지정에 대 한 설정에 인쇄를 허용 하는 표준 인쇄 설정 대화 상자를 호출 합니다.이 문서 또는 최대 있는 모든 문서에이 응용 프로그램입니다. 전체 시스템에 대 한 기본 프린터 설정을 변경 하려면 제어판을 사용 해야 합니다.

   `CWinApp::OnFilePrintSetup` 매우 간단한 구현을 만드는는 `CPrintDialog` 개체와 호출은 `CWinApp::DoPrintDialog` 구현 함수입니다. 이 응용 프로그램 기본 프린터 설정을 설정합니다.

   이 명령은 사용자 지정 하기 위한 일반적인 필요성을 저장할 때 문서를 사용 하 여 저장할 문서별 프린터 설정에 대 한 것입니다. 이 작업을 수행 하려면 메시지 맵 처리기에 추가 해야 하 `CDocument` 만드는 클래스를 `CPrintDialog` 개체를 적절 한 프린터 특성을 사용 하 여 초기화 (일반적으로 *hDevMode* 및 *hDevNames*)를 호출 합니다 `CPrintDialog::DoModal`, 변경 된 프린터 설정을 저장 합니다. 강력한 구현의 경우 살펴봐야 구현의 `CWinApp::DoPrintDialog` 오류를 감지 하 고 `CWinApp::UpdatePrinterSelection` 합리적인 기본값을 사용 하 여 처리 및 시스템 수준 프린터 변경 내용 추적에 대 한 합니다.

- 현재 문서의 ID_FILE_PRINT 표준 인쇄

    > [!NOTE]
    >  이를 연결 해야 프로그램 `CView`-이 기능을 사용 하는 클래스의 메시지 맵 파생 합니다.

   이 명령은 현재 문서 인쇄 또는 더 정확 하 게 표준 인쇄 대화 상자를 호출 하 고 인쇄 engine을 실행 하 여 인쇄 프로세스를 시작 합니다.

   `CView::OnFilePrint` 이 명령 및 기본 인쇄 루프를 구현합니다. 가상 호출 `CView::OnPreparePrinting` 인쇄 대화 상자를 사용 하 여 사용자의 프롬프트에 있습니다. 그런 다음 프린터를 출력 DC 준비, (AFX_IDD_PRINTDLG) 인쇄 진행률 대화 상자를 표시 하 고 보냅니다는 `StartDoc` 프린터를 이스케이프 합니다. `CView::OnFilePrint` 또한 기본 페이지 인쇄 루프를 포함합니다. 각 페이지에 대 한 가상 호출 `CView::OnPrepareDC` 뒤에 `StartPage` 이스케이프 및 가상 호출 `CView::OnPrint` 해당 페이지에 대 한 합니다. 완료 되 면, 가상 `CView::OnEndPrinting` 를 호출 하 고 인쇄 진행률 대화 상자를 닫습니다.

   MFC 인쇄 아키텍처는 인쇄 및 인쇄 미리 보기에 대 한 다양 한 방법으로 연결 하도록 설계 되었습니다. 일반적으로 보면 다양 한 `CView` 재정의 가능 함수를 모든 페이지의 인쇄 작업에 적합 합니다. ID_FILE_PRINT 구현을 바꿀 필요가 비페이지 지향된 출력에 대 한 프린터를 사용 하는 응용 프로그램의 경우에 찾을 해야 있습니다.

- 현재 문서에 대 한 인쇄 미리 보기 모드 ID_FILE_PRINT_PREVIEW 입력입니다.

    > [!NOTE]
    >  이를 연결 해야 프로그램 `CView`-이 기능을 사용 하는 클래스의 메시지 맵 파생 합니다.

   `CView::OnFilePrintPreview` 문서화 된 도우미 함수를 호출 하 여 인쇄 미리 보기 모드를 시작 `CView::DoPrintPreview`합니다. `CView::DoPrintPreview` 가 인쇄 미리 보기 루프에 대 한 기본 엔진 `OnFilePrint` 는 인쇄 루프에 대 한 기본 엔진입니다.

   인쇄 미리 보기 작업을 사용자 지정할 수 있습니다 다양 한 방법으로 다른 매개 변수를 전달 하 여 `DoPrintPreview`입니다. 참조 하십시오 [기술 참고 30](../mfc/tn030-customizing-printing-and-print-preview.md), 인쇄 미리 보기의 세부 정보 중 일부를 설명 하는 방법과 사용자 지정 합니다.

- ID_FILE_MRU_FILE1... FILE16 파일 MRU에 대 한 명령 Id 범위의 **목록**합니다.

   `CWinApp::OnUpdateRecentFileMenu` ON_UPDATE_COMMAND_UI 메커니즘을 사용 하는 고급 중 하나인 업데이트 명령 UI 처리기가 있습니다. 메뉴 리소스의만 ID_FILE_MRU_FILE1 ID를 사용 하 여 단일 메뉴 항목을 정의 해야 합니다. 해당 메뉴 항목에 처음에 비활성화 된 상태로 유지 됩니다.

   MRU 목록 많아지면, 추가 메뉴 항목이 목록에 추가 됩니다. 표준 `CWinApp` 네 개의 가장 최근에 사용한 파일의 표준도 기본적으로 구현 합니다. 호출 하 여 기본값을 변경할 수 있습니다 `CWinApp::LoadStdProfileSettings` 더 크거나 더 작은 값입니다. MRU 목록 응용 프로그램에 저장 됩니다. INI 파일입니다. 응용 프로그램의 목록 로드 되 `InitInstance` 함수를 호출 하면 `LoadStdProfileSettings`, 응용 프로그램이 종료 될 때 저장 됩니다. 또한 MRU 업데이트 명령 UI 처리기 파일 메뉴의 표시에 대 한 상대 경로를 절대 경로로 변환 됩니다.

   `CWinApp::OnOpenRecentFile` 실제 명령을 수행 하는 ON_COMMAND 처리기가입니다. MRU 목록 및 호출에서 단순히 파일 이름을 가져옵니다 `CWinApp::OpenDocumentFile`, 파일을 열고 MRU 목록 업데이트의 모든 작업을 수행 하는 합니다.

   사용자 지정이 명령 처리기의 권장 되지 않습니다.

- ID_EDIT_CLEAR 현재 선택을 취소합니다

   현재이 명령에 대 한 표준 구현 하지 않습니다. 각각에 대해이 구현 해야 `CView`-클래스를 파생 합니다.

   `CEditView` 이 명령을 사용 하는 구현을 제공 `CEdit::Clear`합니다. 현재 선택 영역이 없는 경우에 명령이 비활성화 됩니다.

   이 명령을 구현 하려는 경우이 명령 ID를 사용 하는 것이 좋습니다.

- ID_EDIT_CLEAR_ALL 전체 문서를 지웁니다.

   현재이 명령에 대 한 표준 구현 하지 않습니다. 각각에 대해이 구현 해야 `CView`-클래스를 파생 합니다.

   이 명령을 구현 하려는 경우이 명령 ID를 사용 하는 것이 좋습니다. MFC 자습서 샘플을 참조 하세요 [SCRIBBLE](../overview/visual-cpp-samples.md) 구현 예제입니다.

- ID_EDIT_COPY는 클립보드에 현재 선택 영역을 복사합니다.

   현재이 명령에 대 한 표준 구현 하지 않습니다. 각각에 대해이 구현 해야 `CView`-클래스를 파생 합니다.

   `CEditView` 이 명령에서 현재 선택한 텍스트를 사용 하 여 CF_TEXT 클립보드에 복사 하는 구현을 제공 `CEdit::Copy`합니다. 현재 선택 영역이 없는 경우에 명령이 비활성화 됩니다.

   이 명령을 구현 하려는 경우이 명령 ID를 사용 하는 것이 좋습니다.

- ID_EDIT_CUT은 클립보드의 현재 선택 항목을 잘라냅니다.

   현재이 명령에 대 한 표준 구현 하지 않습니다. 각각에 대해이 구현 해야 `CView`-클래스를 파생 합니다.

   `CEditView` 이 명령 CF_TEXT 사용 하 여 클립보드에 현재 선택한 텍스트를 잘라내어의 구현을 제공 `CEdit::Cut`합니다. 현재 선택 영역이 없는 경우에 명령이 비활성화 됩니다.

   이 명령을 구현 하려는 경우이 명령 ID를 사용 하는 것이 좋습니다.

- 찾기 작업 ID_EDIT_FIND 시작 모덜리스 찾기 대화 상자를 엽니다.

   현재이 명령에 대 한 표준 구현 하지 않습니다. 각각에 대해이 구현 해야 `CView`-클래스를 파생 합니다.

   `CEditView` 이 명령을 구현 도우미 함수를 호출 하는 구현을 제공 `OnEditFindReplace` 사용 하 고 private 구현 변수에서 이전 찾기/바꾸기 설정을 저장 합니다. `CFindReplaceDialog` 클래스 사용자에 게 확인 하는 것에 대 한 모덜리스 대화 상자를 관리 하는 데 사용 됩니다.

   이 명령을 구현 하려는 경우이 명령 ID를 사용 하는 것이 좋습니다.

- ID_EDIT_PASTE 현재 클립보드 내용을 삽입합니다.

   현재이 명령에 대 한 표준 구현 하지 않습니다. 각각에 대해이 구현 해야 `CView`-클래스를 파생 합니다.

   `CEditView` 이 명령을 사용 하 여 선택한 텍스트 바꾸기 현재 클립보드 데이터를 복사 하는 구현을 제공 `CEdit::Paste`합니다. 명령이 비활성화 되어 있는 경우 없습니다 **CF_TEXT** 클립보드에 있습니다.

   `COleClientDoc` 이 명령에 대 한 업데이트 명령 UI 처리기를 제공 합니다. 클립보드 포함 가능한 OLE 항목/개체를 포함 하지 않으면 명령이 비활성화 됩니다. 실제 붙여넣기 작업을 수행 하는 실제 명령에 대 한 처리기를 작성할 책임이 있습니다. OLE 응용 프로그램 다른 형식에 붙여넣을 수도 경우 뷰 또는 문서에서 고유한 업데이트 명령 UI 처리기를 제공 해야 (즉, 어딘가에 전에 `COleClientDoc` 명령 대상 라우팅).

   이 명령을 구현 하려는 경우이 명령 ID를 사용 하는 것이 좋습니다.

   표준 OLE 구현을 대체를 사용 하 여 `COleClientItem::CanPaste`입니다.

- ID_EDIT_PASTE_LINK은 클립보드 내용을 현재에서 링크를 삽입합니다.

   현재이 명령에 대 한 표준 구현 하지 않습니다. 각각에 대해이 구현 해야 `CView`-클래스를 파생 합니다.

   `COleDocument` 이 명령에 대 한 업데이트 명령 UI 처리기를 제공 합니다. 클립보드에 링크할 수 있는 OLE 항목/개체 없으면 명령이 비활성화 됩니다. 실제 붙여넣기 작업을 수행 하는 실제 명령에 대 한 처리기를 작성할 책임이 있습니다. OLE 응용 프로그램 다른 형식에 붙여넣을 수도 경우 뷰 또는 문서에서 고유한 업데이트 명령 UI 처리기를 제공 해야 (즉, 어딘가에 전에 `COleDocument` 명령 대상 라우팅).

   이 명령을 구현 하려는 경우이 명령 ID를 사용 하는 것이 좋습니다.

   표준 OLE 구현을 대체를 사용 하 여 `COleClientItem::CanPasteLink`입니다.

- ID_EDIT_PASTE_SPECIAL 옵션을 사용 하 여 현재 클립보드 내용을 삽입합니다.

   현재이 명령에 대 한 표준 구현 하지 않습니다. 각각에 대해이 구현 해야 `CView`-클래스를 파생 합니다. MFC는이 대화 상자를 제공 하지 않습니다.

   이 명령을 구현 하려는 경우이 명령 ID를 사용 하는 것이 좋습니다.

- ID_EDIT_REPEAT 마지막 작업을 반복합니다.

   현재이 명령에 대 한 표준 구현 하지 않습니다. 각각에 대해이 구현 해야 `CView`-클래스를 파생 합니다.

   `CEditView` 이 명령은 마지막 찾기 작업을 반복 하는 구현을 제공 합니다. 마지막 찾기에 대 한 private 구현 변수가 사용 됩니다. 찾기를 시도할 수 없는 경우에 명령이 비활성화 됩니다.

   이 명령을 구현 하려는 경우이 명령 ID를 사용 하는 것이 좋습니다.

- 바꾸기 작업 ID_EDIT_REPLACE 시작 모덜리스 바꾸기 대화 상자를 엽니다.

   현재이 명령에 대 한 표준 구현 하지 않습니다. 각각에 대해이 구현 해야 `CView`-클래스를 파생 합니다.

   `CEditView` 이 명령을 구현 도우미 함수를 호출 하는 구현을 제공 `OnEditFindReplace` 사용 하 고 private 구현 변수에서 이전 찾기/바꾸기 설정을 저장 합니다. `CFindReplaceDialog` 클래스 라는 메시지는 모덜리스 대화 상자를 관리 하는 데 사용 됩니다.

   이 명령을 구현 하려는 경우이 명령 ID를 사용 하는 것이 좋습니다.

- ID_EDIT_SELECT_ALL 전체 문서를 선택 합니다.

   현재이 명령에 대 한 표준 구현 하지 않습니다. 각각에 대해이 구현 해야 `CView`-클래스를 파생 합니다.

   `CEditView` 문서의 모든 텍스트를 선택 하는이 명령에서의 구현을 제공 합니다. 선택 하는 텍스트가 없는 경우에 명령이 비활성화 됩니다.

   이 명령을 구현 하려는 경우이 명령 ID를 사용 하는 것이 좋습니다.

- ID_EDIT_UNDO 마지막 작업 실행 취소합니다.

   현재이 명령에 대 한 표준 구현 하지 않습니다. 각각에 대해이 구현 해야 `CView`-클래스를 파생 합니다.

   `CEditView` 이 구현을 제공 명령을 사용 하 여 `CEdit::Undo`입니다. 명령이 비활성화 되어 있는 경우 `CEdit::CanUndo` FALSE를 반환 합니다.

   이 명령을 구현 하려는 경우이 명령 ID를 사용 하는 것이 좋습니다.

- ID_EDIT_REDO 마지막 작업 다시 실행합니다.

   현재이 명령에 대 한 표준 구현 하지 않습니다. 각각에 대해이 구현 해야 `CView`-클래스를 파생 합니다.

   이 명령을 구현 하려는 경우이 명령 ID를 사용 하는 것이 좋습니다.

- ID_WINDOW_NEW 활성 문서에서 다른 창을 시작 합니다.

   `CMDIFrameWnd::OnWindowNew` 현재 문서의 다른 뷰를 포함 하는 다른 프레임을 만들려면 현재 문서의 문서 서식 파일을 사용 하 여이 강력한 기능을 구현 합니다.

   대부분의 여러 문서 MDI (인터페이스) 창 메뉴 명령와 같은 활성 MDI 자식 창에 없는 경우 명령이 비활성화 됩니다.

   사용자 지정이 명령 처리기의 권장 되지 않습니다. 추가 뷰 또는 프레임 창을 만드는 명령을 제공 하려는 경우 아마도 됩니다 명령을 직접 고안 것이 좋습니다. 코드를 복제할 수 있습니다 `CMDIFrameWnd::OnWindowNew` 원하는 특정 프레임 및 뷰 클래스를 수정 합니다.

- MDI 창 맨 아래에 ID_WINDOW_ARRANGE 정렬 아이콘

   `CMDIFrameWnd` 이 표준 MDI 명령 구현 도우미 함수에 구현 `OnMDIWindowCmd`합니다. 이 도우미 명령 Id를 매핑하고 MDI Windows 메시지에 많은 양의 코드를 공유 하므로 수 있습니다.

   대부분의 MDI 창 메뉴 명령와 같은 활성 MDI 자식 창에 없는 경우 명령이 비활성화 됩니다.

   사용자 지정이 명령 처리기의 권장 되지 않습니다.

- ID_WINDOW_CASCADE 단계적 windows 겹치게 됩니다.

   `CMDIFrameWnd` 이 표준 MDI 명령 구현 도우미 함수에 구현 `OnMDIWindowCmd`합니다. 이 도우미 명령 Id를 매핑하고 MDI Windows 메시지에 많은 양의 코드를 공유 하므로 수 있습니다.

   대부분의 MDI 창 메뉴 명령와 같은 활성 MDI 자식 창에 없는 경우 명령이 비활성화 됩니다.

   사용자 지정이 명령 처리기의 권장 되지 않습니다.

- ID_WINDOW_TILE_HORZ 타일 windows 가로입니다.

   이 명령에서 구현 됩니다 `CMDIFrameWnd` ID_WINDOW_CASCADE을 제외 하면 처럼 다른 MDI Windows 메시지를 작업에 사용 됩니다.

   응용 프로그램에 대 한 기본 타일 방향을 선택 해야 합니다. ID_WINDOW_TILE_HORZ 또는 ID_WINDOW_TILE_VERT 창 "타일" 메뉴 항목에 대 한 ID를 변경 하 여이 수행할 수 있습니다.

- Windows ID_WINDOW_TILE_VERT 타일 세로 방향으로 합니다.

   이 명령에서 구현 됩니다 `CMDIFrameWnd` ID_WINDOW_CASCADE을 제외 하면 처럼 다른 MDI Windows 메시지를 작업에 사용 됩니다.

   응용 프로그램에 대 한 기본 타일 방향을 선택 해야 합니다. ID_WINDOW_TILE_HORZ 또는 ID_WINDOW_TILE_VERT 창 "타일" 메뉴 항목에 대 한 ID를 변경 하 여이 수행할 수 있습니다.

- 분할자를 ID_WINDOW_SPLIT 키보드 인터페이스입니다.

   `CView` 이 명령에 대 한 처리는 `CSplitterWnd` 구현 합니다. 이 명령은 구현 함수를 위임 하는 뷰 분할기 창의 일부 이면 `CSplitterWnd::DoKeyboardSplit`합니다. 이 분할자 키보드 사용자 분할 또는 분할 창 분할 해제 수 있는 모드에 배치할 수 있습니다.

   보기 분할자에 없는 경우에이 명령은 사용할 수 없습니다.

   사용자 지정이 명령 처리기의 권장 되지 않습니다.

- ID_APP_ABOUT 정보 대화 상자를 호출 합니다.

   응용 프로그램에 대 한 상자에 대 한 표준 구현 하지 않습니다. 기본 응용 프로그램 마법사가 만든 응용 프로그램을 만들고 응용 프로그램에 대 한 사용자 지정 대화 상자 클래스에 대 한 상자를 사용 합니다. 또한 응용 프로그램 마법사에서이 명령을 처리 하 고 대화 상자를 호출 하는 간단한 명령 처리기를 작성 합니다.

   이 명령은 거의 항상 구현 합니다.

- ID_APP_EXIT 응용 프로그램을 종료 합니다.

   `CWinApp::OnAppExit` 이 명령은 응용 프로그램의 주 창이 WM_CLOSE 메시지를 전송 하 여 처리 합니다. 표준 (묻는 더티 파일 등) 응용 프로그램의 종료를 처리 합니다 `CFrameWnd` 구현 합니다.

   사용자 지정이 명령 처리기의 권장 되지 않습니다. 재정의 `CWinApp::SaveAllModified` 또는 `CFrameWnd` 닫기 논리는 것이 좋습니다.

   이 명령을 구현 하려는 경우이 명령 ID를 사용 하는 것이 좋습니다.

- ID_HELP_INDEX 나열 도움말 항목입니다. HLP 파일입니다.

    > [!NOTE]
    >  이를 연결 해야 프로그램 `CWinApp`-이 기능을 사용 하는 클래스의 메시지 맵 파생 합니다.

   `CWinApp::OnHelpIndex` 이 명령은 일반적으로 호출 하 여 처리 `CWinApp::WinHelp`합니다.

   사용자 지정이 명령 처리기의 권장 되지 않습니다.

- 도움말을 사용 하는 방법에 도움말 ID_HELP_USING 표시 합니다.

    > [!NOTE]
    >  이를 연결 해야 프로그램 `CWinApp`-이 기능을 사용 하는 클래스의 메시지 맵 파생 합니다.

   `CWinApp::OnHelpUsing` 이 명령은 일반적으로 호출 하 여 처리 `CWinApp::WinHelp`합니다.

   사용자 지정이 명령 처리기의 권장 되지 않습니다.

- ID_CONTEXT_HELP 입력 SHIFT-F1 도움말 모드입니다.

    > [!NOTE]
    >  이를 연결 해야 프로그램 `CWinApp`-이 기능을 사용 하는 클래스의 메시지 맵 파생 합니다.

   `CWinApp::OnContextHelp` 도움말 모드 커서를 설정 하 고 모달 루프 입력 도움말을 보려면 창을 선택 하 여 사용자에 대 한 대기 하 여이 명령을 처리 합니다. 참조 하십시오 [Technical Note 28](../mfc/tn028-context-sensitive-help-support.md) MFC 도움말 구현에 대 한 자세한 내용은 합니다.

   사용자 지정이 명령 처리기의 권장 되지 않습니다.

- 현재 컨텍스트에 따라 ID_HELP 제공 도움말

    > [!NOTE]
    >  이를 연결 해야 프로그램 `CWinApp`-이 기능을 사용 하는 클래스의 메시지 맵 파생 합니다.

   `CWinApp::OnHelp` 이 명령은 현재 응용 프로그램 컨텍스트에 대 한 올바른 도움말 컨텍스트를 가져와서 처리 합니다. 간단한 F1 도움말 처리에 메시지 상자에서 등 수 있습니다. 참조 하십시오 [Technical Note 28](../mfc/tn028-context-sensitive-help-support.md) MFC에 대 한 자세한 내용은 도움말 구현에 대 한 합니다.

   사용자 지정이 명령 처리기의 권장 되지 않습니다.

- 컨텍스트에 대 한 기본 도움말을 ID_DEFAULT_HELP 표시

    > [!NOTE]
    >  이를 연결 해야 프로그램 `CWinApp`-이 기능을 사용 하는 클래스의 메시지 맵 파생 합니다.

   이 명령은 일반적으로 매핑될 `CWinApp::OnHelpIndex`합니다.

   기본 도움말 및 도움말 인덱스 간의 차이점을 원하는 경우 다른 명령 처리기를 제공할 수 있습니다.

- ID_NEXT_PANE 다음 창으로 이동

   `CView` 이 명령에 대 한 처리는 `CSplitterWnd` 구현 합니다. 이 명령은 구현 함수를 위임 하는 뷰 분할기 창의 일부 이면 `CSplitterWnd::OnNextPaneCmd`합니다. 현재 보기 분할자의 다음 창으로 이동 됩니다.

   보기 분할자에 있지 않거나 없는 다음 창으로 이동 하는 경우에이 명령은 사용할 수 없습니다.

   사용자 지정이 명령 처리기의 권장 되지 않습니다.

- ID_PREV_PANE 이전 창으로 이동

   `CView` 이 명령에 대 한 처리는 `CSplitterWnd` 구현 합니다. 이 명령은 구현 함수를 위임 하는 뷰 분할기 창의 일부 이면 `CSplitterWnd::OnNextPaneCmd`합니다. 현재 보기 분할자의 이전 창으로 이동 됩니다.

   보기 분할자에 있지 않거나 없는 이전 창으로 이동 하는 경우에이 명령은 사용할 수 없습니다.

   사용자 지정이 명령 처리기의 권장 되지 않습니다.

- ID_OLE_INSERT_NEW 새 OLE 개체를 삽입합니다.

   현재이 명령에 대 한 표준 구현 하지 않습니다. 이 구현 해야 하 `CView`-현재 선택 영역에 새 OLE 항목/개체를 삽입할 클래스를 파생 합니다.

   모든 OLE 클라이언트 응용 프로그램에는이 명령을 구현 해야 합니다. 응용 프로그램 마법사, OLE 옵션으로는 스 켈 레 톤의 구현을 만듭니다 `OnInsertObject` 완료 해야 하는 뷰 클래스에 있습니다.

   MFC OLE 샘플을 참조 하세요 [OCLIENT](../overview/visual-cpp-samples.md) 이 명령의 전체 구현에 대 한 예제입니다.

- ID_OLE_EDIT_LINKS 편집 OLE 링크

   `COleDocument` 이 명령은 표준 OLE 링크 대화 상자의 MFC가 제공한 구현을 사용 하 여 처리 합니다. 이 대화의 구현을 통해 액세스 되는 `COleLinksDialog` 클래스입니다. 현재 문서에 대 한 연결 없으면 명령이 비활성화 됩니다.

   사용자 지정이 명령 처리기의 권장 되지 않습니다.

- ID_OLE_VERB_FIRST... OLE 동사에 대 한 마지막 ID 범위

   `COleDocument` 이 명령은 ID 범위를 사용 하 여 현재 선택 된 OLE 항목/개체를 지 원하는 동사에 대 한 합니다. 지정된 된 OLE 항목/개체 형식에는 0 개 이상의 사용자 지정 동사 지원할 수 있으므로 범위 여야 합니다. 응용 프로그램의 메뉴에서 ID_OLE_VERB_FIRST ID를 사용 하 여 메뉴 항목을 하나 있어야 합니다. 프로그램이 실행 될 때 메뉴 동사에 대 한 설명을 적절 한 메뉴 (또는 여러 동사를 사용 하 여 팝업 메뉴)를 사용 하 여 업데이트 됩니다. OLE 메뉴의 관리는에서 처리 `AfxOleSetEditMenu`,이 명령에 대 한 업데이트 명령 UI 처리기에서 수행 합니다.

   각이 범위에 있는 명령 ID를 처리 하기 위한 명시적인 명령 처리기가 없는 경우 `COleDocument::OnCmdMsg` 이 범위의 모든 명령 Id를 트래핑 하 고 0부터 시작 동사 숫자도 전환 해 해당 동사에 대 한 서버를 시작 하기 위해 재정의 됩니다 (사용 하 여 `COleClientItem::DoVerb`).

   사용자 지정 또는이 명령 ID 범위를 다른 사용은 권장 되지 않습니다.

- ID_VIEW_TOOLBAR 도구 모음을 설정 및 해제

   `CFrameWnd` 이 명령 및 도구 모음에서의 표시 상태를 설정/해제 명령 업데이트 UI 처리기를 처리 합니다. 도구 모음에는 자식 창 AFX_IDW_TOOLBAR의 ID를 사용 하 여 자식 창 프레임의 이어야 합니다. 명령 처리기는 실제로 도구 모음 창의 표시 유형을 전환합니다. `CFrameWnd::RecalcLayout` 새 상태로 도구 모음을 사용 하 여 프레임 창을 다시 그리도록 하는 데 사용 됩니다. 도구 모음을 표시 하는 경우 업데이트 명령 UI 처리기 메뉴 항목을 확인 합니다.

   사용자 지정이 명령 처리기의 권장 되지 않습니다. 추가 도구 모음을 추가 하려는 경우에 복제 명령 처리기 및이 명령에 대 한 업데이트 명령 UI 처리기를 수정 하는 것이 해야 합니다.

- ID_VIEW_STATUS_BAR 상태 표시줄 설정 및 해제

   이 명령에서 구현 됩니다 `CFrameWnd` ID (AFX_IDW_STATUS_BAR)는 다양 한 자식 창을 제외한 ID_VIEW_TOOLBAR, 마찬가지로 합니다.

## <a name="update-only-command-handlers"></a>업데이트 전용 명령 처리기

여러 표준 명령 Id 상태 표시줄에서 표시기로 사용 됩니다. 이러한 동일한 업데이트 명령 UI를 사용 하 처리 메커니즘 응용 프로그램이 유휴 시간 동안 현재 시각적 상태를 표시 합니다. 사용자가 선택할 수 없습니다 때문 (즉, 푸시할 수 없습니다는 상태 표시줄 창)에 올 수 없습니다는 ON_COMMAND 처리기에 대 한 명령 Id를 사용 하는 것입니다.

- ID_INDICATOR_CAPS : CAP 잠금 표시기입니다.

- ID_INDICATOR_NUM : NUM lock 표시기입니다.

- ID_INDICATOR_SCRL : SCRL 잠금 표시기입니다.

- ID_INDICATOR_KANA : 일본어가 나 구분 (일본어 시스템에만 해당) 표시기를 잠급니다.

이러한 세 가지 모두에서 구현 되는 `CFrameWnd::OnUpdateKeyIndicator`, 적절 한 가상 키에 매핑할 명령 ID를 사용 하는 구현 도우미입니다. 일반적인 구현은 사용 하거나 사용 하지 않도록 설정 (사용 하지 않도록 설정 하는 상태 창에 대 한 텍스트가 없는 =)는 `CCmdUI` 적절 한 가상 키 현재 잠겨 있는지 여부에 따라 개체입니다.

사용자 지정이 명령 처리기의 권장 되지 않습니다.

- ID_INDICATOR_EXT : 확장된 선택 표시기입니다.

- ID_INDICATOR_OVR : 겹쳐쓰기 표시기입니다.

- ID_INDICATOR_REC: 녹음/녹화 표시기입니다.

현재 이러한 지표의 표준 구현 하지 않습니다.

이러한 표시기를 구현 하려는 경우 이러한 표시기 Id 및 상태 표시줄에 표시기의 순서를 유지 관리를 사용 하는 것이 좋습니다 (즉,이 순서 대로: EXT, CAP, NUM, SCRL, 겹침, REC).

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
