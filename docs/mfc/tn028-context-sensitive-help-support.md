---
title: 'TN028: 상황에 맞는 도움말 지원'
ms.date: 11/04/2016
f1_keywords:
- vc.help
helpviewer_keywords:
- context-sensitive Help [MFC], MFC applications
- TN028
- resource identifiers, context-sensitive Help
ms.assetid: 884f1c55-fa27-4d4c-984f-30907d477484
ms.openlocfilehash: 5689e314c2ba94068619a066e5f458e06819b2b7
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58773478"
---
# <a name="tn028-context-sensitive-help-support"></a>TN028: 상황에 맞는 도움말 지원

이 이는 도움말 컨텍스트 Id 및 MFC에서 기타 도움말 문제를 할당 하기 위한 규칙을 설명 합니다. 상황에 맞는 도움말 지원에 사용할 수 있는 도움말 컴파일러가 필요 시각적 개체의 C++입니다.

> [!NOTE]
>  WinHelp를 사용 하 여 상황에 맞는 도움말을 구현 하는 것 외에도 MFC HTML 도움말 사용도 지원 합니다. 이 지원 및 HTML 도움말을 사용 하 여 프로그래밍에 대 한 자세한 내용은 참조 하세요. [HTML 도움말: 프로그램에 대 한 상황에 맞는 도움말](../mfc/html-help-context-sensitive-help-for-your-programs.md)합니다.

## <a name="types-of-help-supported"></a>형식의 도움말 지원

Windows 응용 프로그램에서 구현 하는 상황에 맞는 도움말에는 다음과 같은 두 종류가 있습니다. 첫 번째 라고 "F1 Help" 현재 활성 개체를 기준으로 적절 한 컨텍스트를 사용 하 여 WinHelp 시작 포함 합니다. 두 번째는 "Shift + F1" 모드입니다. 이 모드에서 마우스 커서가 변경 도움말 커서를 사용자 개체를 클릭 이동 합니다. 이 시점에서 사용자가 클릭할 수 있는 개체에 대 한 도움말을 제공 하려면 WinHelp 시작 됩니다.

Microsoft Foundation Classes 도움말의 다음이 형태 중 둘 다 구현 합니다. 또한 프레임 워크는 도움말 색인 및 사용 하 여 두 개의 간단한 도움말 명령을 지원합니다.

## <a name="help-files"></a>도움말 파일

Microsoft Foundation classes 단일 도움말 파일을 가정합니다. 해당 도움말 파일에는 응용 프로그램과 동일한 이름 및 경로 있어야 합니다. 예를 들어 실행 파일은 C:\MyApplication\MyHelp.exe 도움말 파일에 C:\MyApplication\MyHelp.hlp 이어야 합니다. 통해 경로 설정 합니다 *m_pszHelpFilePath* 멤버 변수의 [CWinApp 클래스](../mfc/reference/cwinapp-class.md)합니다.

## <a name="help-context-ranges"></a>도움말 컨텍스트 범위

MFC의 기본 구현 도움말 컨텍스트 Id의 할당에 대 한 몇 가지 규칙을 따르도록 프로그램에 필요 합니다. 이러한 규칙은 특정 컨트롤에 할당 된 Id 범위입니다. 다양 한 도움말 관련 멤버 함수의 다른 구현을 제공 하 여 이러한 규칙을 재정의할 수 있습니다.

```
0x00000000 - 0x0000FFFF : user defined
0x00010000 - 0x0001FFFF : commands (menus/command buttons)
0x00010000 + ID_
(note: 0x18000-> 0x1FFFF is the practical range since command IDs are>=0x8000)
0x00020000 - 0x0002FFFF : windows and dialogs
0x00020000 + IDR_
(note: 0x20000-> 0x27FFF is the practical range since IDRs are <= 0x7FFF)
0x00030000 - 0x0003FFFF : error messages (based on error string ID)
0x00030000 + IDP_
0x00040000 - 0x0004FFFF : special purpose (non-client areas)
0x00040000 + HitTest area
0x00050000 - 0x0005FFFF : controls (those that are not commands)
0x00040000 + IDW_
```

## <a name="simple-help-commands"></a>간단한 "Help" 명령

Microsoft Foundation 클래스에서 구현 되는 두 개의 간단한 도움말 명령입니다.

- 구현 하는 ID_HELP_INDEX [CWinApp::OnHelpIndex](../mfc/reference/cwinapp-class.md#onhelpindex)

- 구현 하는 ID_HELP_USING [CWinApp::OnHelpUsing](../mfc/reference/cwinapp-class.md#onhelpusing)

첫 번째 명령은 응용 프로그램에 대 한 도움말 색인을 보여 줍니다. 두 번째 WinHelp 프로그램을 사용 하 여 사용자 도움말을 보여 줍니다.

## <a name="context-sensitive-help-f1-help"></a>상황에 맞는 도움말 (F1 도움말)

F1 키를 액셀러레이터 주 창의 액셀러레이터 키 테이블에 배치 하 여 ID의 ID_HELP 명령에 일반적으로 변환 됩니다. ID_HELP 명령 단추는 ID의 ID_HELP 주 창 또는 대화 상자를 사용 하 여도 생성 될 수 있습니다.

ID_HELP 명령 생성 되는 방법에 관계 없이 명령 처리기에 도달할 때까지 일반 명령으로 라우팅되는 것입니다. MFC 명령 라우팅 아키텍처에 대 한 자세한 내용은 참조 [기술 참고 21](../mfc/tn021-command-and-message-routing.md)합니다. ID_HELP 명령에서 처리 되는 응용 프로그램에 도움말을 사용 하도록 설정 하는 경우 [CWinApp::OnHelp](../mfc/reference/cwinapp-class.md#onhelp)합니다. 응용 프로그램 개체 도움말 메시지를 받고 그런 다음 명령을 적절 하 게 라우팅합니다. 이것이 필요한 특정 가장 컨텍스트를 결정 하는 데 적합 하지 않은 기본 명령 라우팅 때문입니다.

`CWinApp::OnHelp` 다음 순서 대로 WinHelp를 시작 하려고 시도 합니다.

1. 활성 확인 `AfxMessageBox` 호출를 도움말 id. 메시지 상자 현재 활성 상태인 경우 WinHelp 해당 messagebox에 적절 한 컨텍스트를 사용 하 여 시작 됩니다.

1. 활성 창에 WM_COMMANDHELP 메시지를 보냅니다. WinHelp를 시작 하 여 해당 창이 응답 하지 않으면, 동일한 메시지가 전송 됩니다 해당 창의 상위 항목에 메시지를 처리할 때까지 현재 최상위 창입니다.

1. ID_DEFAULT_HELP 명령을 주 창에 보냅니다. 이 기본 도움말을 호출합니다. 이 명령은 일반적으로 매핑될 `CWinApp::OnHelpIndex`합니다.

응용 프로그램에서 기본 ID 기본 값 (예: 0x10000 명령에 대 한 대화 상자와 같은 리소스에 대 한 0x20000)을 전역적으로 재정의 하려면 재정의 해야 [CWinApp::WinHelp](../mfc/reference/cwinapp-class.md#winhelp)합니다.

도움말 컨텍스트를 결정 됩니다 방법과이 기능을 재정의 하려면 WM_COMMANDHELP 메시지를 처리 해야 합니다. 보다 구체적인 도움말 라우팅을 제공 프레임 워크를 제공 하는 보다 때만 현재 MDI 자식 창으로 심층 하려고 할 수 있습니다. 특정 창이 나 대화 상자에서 해당 개체 또는 대화 상자 내에 있는 활성 컨트롤의 현재 내부 상태에 따라 아마도에 자세한 도움말을 제공할 수도 있습니다.

## <a name="wmcommandhelp"></a>WM_COMMANDHELP

```

afx_msg LRESULT CWnd::OnCommandHelp(WPARAM wParam, LPARAM lParam)
```

WM_COMMANDHELP에 도움말을 요청할 때 활성 창에서 받은 개인 Windows MFC 메시지입니다. 창에서이 메시지를 받으면 호출할 수 있습니다 `CWinApp::WinHelp` 창의 내부 상태와 일치 하는 컨텍스트를 사용 합니다.

*lParam*<br/>
현재 사용할 수 있는 도움말 컨텍스트를 포함 합니다. *lParam* 도움말 컨텍스트가 없는 결정 한 경우 0입니다. 구현의 `OnCommandHelp` 에서 컨텍스트 ID를 사용할 수 *lParam* 에 다른 컨텍스트를 확인 하거나 되도록 전달 하면 `CWinApp::WinHelp`합니다.

*wParam*<br/>
사용 되지 않으며 0이 됩니다.

경우는 `OnCommandHelp` 함수 호출 `CWinApp::WinHelp`를 반환 해야 **TRUE**합니다. 반환 **TRUE** 다른 클래스를 다른 창으로이 명령은 라우팅을 중지 합니다.

## <a name="help-mode-shiftf1-help"></a>도움말 모드 (Shift + F1 도움말)

상황에 맞는 도움말의 두 번째 형태입니다. 일반적으로이 모드는 메뉴 도구 모음 또는 SHIFT + F1 키를 눌러 입력 됩니다. 명령 (ID_CONTEXT_HELP)으로 구현 됩니다. 메시지 필터 후크 모달 대화 상자를 하는 동안이 명령은 변환 하는 데 사용 되지 않습니다 또는 메뉴의 활성화, 따라서이 명령은 에서만 사용 가능 사용자에 게 응용 프로그램은 기본 메시지 펌프를 실행할 때 (`CWinApp::Run`).

이 모드를 입력 한 후 응용 프로그램은 일반적으로 해당 영역 (예: 창 주변의 크기 조정 테두리)에 대 한 고유한 커서를 표시 하는 경우에 도움말 마우스 커서를 응용 프로그램의 모든 영역을 통해 표시 됩니다. 사용자가 명령을 선택 하려면 마우스 또는 키보드를 사용할 수 있습니다. 명령을 실행 하는 대신 해당 명령에 대 한 도움말이 표시 됩니다. 또한 도구 모음에서 단추와 같은 화면에서 표시 되는 개체를 클릭할 수 및 해당 개체에 대 한 도움말을 표시 됩니다. 도움말의이 모드에서 제공 하는 `CWinApp::OnContextHelp`합니다.

모든 키보드 입력이이 루프의 실행 중 메뉴에 액세스 하는 키를 제외 하 고 활성 상태가 아닙니다. 또한 명령 변환은 여전히 수행 통해 `PreTranslateMessage` 사용자 액셀러레이터 키를 누르고 해당 명령에 대 한 도움을 받을 수 있도록 합니다.

번역 또는 수행 작업에 배치할 경우 특정 합니다 `PreTranslateMessage` 걸리지 위치 SHIFT + F1 도움말 모드에 있는 동안 확인 해야 하는 함수를 *m_bHelpMode* 소속 `CWinApp` 것을 수행 하기 전에 작업입니다. 합니다 `CDialog` 구현의 `PreTranslateMessage` 호출 하기 전에이 확인 `IsDialogMessage`예를 들어 있습니다. 이 shift+f1 모드 중에 모덜리스 대화 상자에서 "대화 상자 탐색" 키를 비활성화 합니다. 또한 `CWinApp::OnIdle` 이 루프 동안 계속 호출 됩니다.

해당 명령에 대 한 도움말으로 처리 되는 사용자가 메뉴에서 명령을 선택 합니다 (WM_COMMANDHELP를 통해 아래 참조). 사용자가 응용 프로그램 창의 표시 영역을 클릭 하면 비클라이언트 클릭 또는 클라이언트 클릭에 대 한 결정이 됩니다. `OnContextHelp` 비클라이언트 매핑의 처리 클라이언트를 클릭할 때 자동으로 클릭합니다. 한 클라이언트 클릭이 클릭 된 창에는 WM_HELPHITTEST 다음 보냅니다. 해당 창에서 0이 아닌 값을 반환 하는 경우 해당 값에 대 한 도움말 컨텍스트로 사용 됩니다. 0을 반환 하는 경우 `OnContextHelp` 시도 부모 창 (및 해당 부모는 실패 및 등). 기본적으로 다음 (일반적으로)에 매핑되는 주 창 ID_DEFAULT_HELP 명령 보내기 도움말 컨텍스트를 확인할 수 없는 경우 `CWinApp::OnHelpIndex`합니다.

## <a name="wmhelphittest"></a>WM_HELPHITTEST

```

afx_msg LRESULT CWnd::OnHelpHitTest(
WPARAM, LPARAM lParam)
```

WM_HELPHITTEST에 SHIFT + F1 도움말 모드에 있는 동안 클릭 하면 활성 창에서 받은 MFC 개인 windows 메시지입니다. 창이이 메시지를 받으면 반환 된 **DWORD** WinHelp 사용에 대 한 도움말 ID입니다.

LOWORD(lParam) 창의 클라이언트 영역을 기준으로 마우스를 클릭는 x 축 장치 좌표를 포함 합니다.

HIWORD(lParam) y 축 좌표를 포함합니다.

*wParam*<br/>
사용 되지 않으며 0이 됩니다. 반환 값 0이 아닌 경우 해당 컨텍스트를 사용 하 여 WinHelp 라고 합니다. 반환 값이 0 이면 부모 창에 쿼리 됩니다.

대부분의 경우에서 이미 있을 수도 있습니다는 적중 테스트 코드를 활용할 수 있습니다. 참조 구현의 `CToolBar::OnHelpHitTest` WM_HELPHITTEST 메시지 처리의 예 (단추 및 도구 설명에 사용 되는 적중 테스트 코드를 활용 하는 코드 `CControlBar`).

## <a name="mfc-application-wizard-support-and-makehm"></a>MFC 응용 프로그램 마법사 지원 및 MAKEHM

MFC 응용 프로그램 마법사 도움말 파일 (.cnt 및.hpj 파일)을 빌드하는 데 필요한 파일을 만듭니다. Microsoft 도움말 컴파일러에서 허용 되는 미리 빌드된.rtf 파일 수가 포함 됩니다. 대부분의 항목은 완료 되지만 일부 특정 응용 프로그램에 대 한 수정 해야 할 수 있습니다.

"매핑 도움말" 파일의 자동 만들기가 MAKEHM 라는 유틸리티에서 지원 됩니다. MAKEHM 유틸리티 응용 프로그램의 리소스를 변환할 수 있습니다. H 파일 도움말 매핑 파일입니다. 예를 들어:

```
#define IDD_MY_DIALOG   2000
#define ID_MY_COMMAND   150
```

로 변환 됩니다.

```
HIDD_MY_DIALOG    0x207d0
HID_MY_COMMAND    0x10096
```

이 형식은 토픽 이름 (왼쪽에 있는 기호)를 사용 하 여 상황에 맞는 Id (오른쪽에 있는 번호)을 매핑하는 도움말 컴파일러의 기능과 호환 됩니다.

MAKEHM에 대 한 소스 코드는 MFC 프로그래밍 유틸리티 예제의 [MAKEHM](../overview/visual-cpp-samples.md)합니다.

## <a name="adding-help-support-after-running-the-mfc-application-wizard"></a>MFC 응용 프로그램 마법사를 실행 한 후 추가 도움말 지원

도움말 응용 프로그램을 추가 하는 가장 좋은 방법은 응용 프로그램을 만들기 전에 MFC 응용 프로그램 마법사의 고급 기능 페이지의 "상황에 맞는 도움말" 옵션을 선택 됩니다. 이런 방식으로 MFC 응용 프로그램 마법사를 자동으로 필요한 메시지 맵 항목을 추가 하 여 `CWinApp`-도움말을 지원 하려면 클래스를 파생 합니다.

## <a name="help-on-message-boxes"></a>메시지 상자에 대 한 도움말

메시지 상자 (경고)에 대 한 도움말을 통해 지원 됩니다 합니다 `AfxMessageBox` 함수에 대 한 래퍼를 `MessageBox` Windows API입니다.

두 가지 버전의 `AfxMessageBox`, 다른 하나는 문자열 ID와 문자열에 대 한 포인터 사용 (`LPCSTR`):

```
int AFXAPI AfxMessageBox(LPCSTR lpszText,
    UINT nType,
    UINT nIDHelp);

int AFXAPI AfxMessageBox(UINT nIDPrompt,
    UINT nType,
    UINT nIDHelp);
```

두 경우 모두 한지는 선택적 도움말 id입니다.

첫 번째 예에서 nIDHelp에 대 한 기본값은 0 이며이 메시지 상자에 대 한 도움말이 없습니다 나타냅니다. 상자 메시지와 같은 활성 상태인 동안 f1 키를 누를, 사용자 (경우에 응용 프로그램에는 도움말 지원) 도움말을 받지 못합니다. 필요 없는 경우 nIDHelp에 대 한 도움말 ID는 제공 합니다.

두 번째 경우에서 nIDHelp에 대 한 기본값은를 도움말 ID nIDPrompt와 같은지 여부를 나타내는-1입니다. 도움말 응용 프로그램은 도움말 사용 물론 경우에 작동 합니다). 메시지 상자가 있는 도움말 지원 되지 않습니다 하려는 경우 0 nIDHelp를 제공 해야 합니다. 메시지를 사용 하도록 설정 하는 도움이 될 nIDPrompt 보다는 서로 다른 도움말 ID를 원하는 하지만 단순히 nIDHelp nIDPrompt와 다른 양수 값을 제공 해야 합니다.

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
