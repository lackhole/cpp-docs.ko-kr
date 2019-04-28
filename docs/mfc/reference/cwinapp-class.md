---
title: CWinApp 클래스
ms.date: 11/04/2016
f1_keywords:
- CWinApp
- AFXWIN/CWinApp
- AFXWIN/CWinApp::CWinApp
- AFXWIN/CWinApp::AddDocTemplate
- AFXWIN/CWinApp::AddToRecentFileList
- AFXWIN/CWinApp::ApplicationRecoveryCallback
- AFXWIN/CWinApp::CloseAllDocuments
- AFXWIN/CWinApp::CreatePrinterDC
- AFXWIN/CWinApp::DelRegTree
- AFXWIN/CWinApp::DoMessageBox
- AFXWIN/CWinApp::DoWaitCursor
- AFXWIN/CWinApp::EnableD2DSupport
- AFXWIN/CWinApp::EnableHtmlHelp
- AFXWIN/CWinApp::EnableTaskbarInteraction
- AFXWIN/CWinApp::ExitInstance
- AFXWIN/CWinApp::GetApplicationRecoveryParameter
- AFXWIN/CWinApp::GetApplicationRecoveryPingInterval
- AFXWIN/CWinApp::GetApplicationRestartFlags
- AFXWIN/CWinApp::GetAppRegistryKey
- AFXWIN/CWinApp::GetDataRecoveryHandler
- AFXWIN/CWinApp::GetFirstDocTemplatePosition
- AFXWIN/CWinApp::GetHelpMode
- AFXWIN/CWinApp::GetNextDocTemplate
- AFXWIN/CWinApp::GetPrinterDeviceDefaults
- AFXWIN/CWinApp::GetProfileBinary
- AFXWIN/CWinApp::GetProfileInt
- AFXWIN/CWinApp::GetProfileString
- AFXWIN/CWinApp::GetSectionKey
- AFXWIN/CWinApp::HideApplication
- AFXWIN/CWinApp::HtmlHelp
- AFXWIN/CWinApp::InitInstance
- AFXWIN/CWinApp::IsTaskbarInteractionEnabled
- AFXWIN/CWinApp::LoadCursor
- AFXWIN/CWinApp::LoadIcon
- AFXWIN/CWinApp::LoadOEMCursor
- AFXWIN/CWinApp::LoadOEMIcon
- AFXWIN/CWinApp::LoadStandardCursor
- AFXWIN/CWinApp::LoadStandardIcon
- AFXWIN/CWinApp::OnDDECommand
- AFXWIN/CWinApp::OnIdle
- AFXWIN/CWinApp::OpenDocumentFile
- AFXWIN/CWinApp::ParseCommandLine
- AFXWIN/CWinApp::PreTranslateMessage
- AFXWIN/CWinApp::ProcessMessageFilter
- AFXWIN/CWinApp::ProcessShellCommand
- AFXWIN/CWinApp::ProcessWndProcException
- AFXWIN/CWinApp::Register
- AFXWIN/CWinApp::RegisterWithRestartManager
- AFXWIN/CWinApp::ReopenPreviousFilesAtRestart
- AFXWIN/CWinApp::RestartInstance
- AFXWIN/CWinApp::RestoreAutosavedFilesAtRestart
- AFXWIN/CWinApp::Run
- AFXWIN/CWinApp::RunAutomated
- AFXWIN/CWinApp::RunEmbedded
- AFXWIN/CWinApp::SaveAllModified
- AFXWIN/CWinApp::SelectPrinter
- AFXWIN/CWinApp::SetHelpMode
- AFXWIN/CWinApp::SupportsApplicationRecovery
- AFXWIN/CWinApp::SupportsAutosaveAtInterval
- AFXWIN/CWinApp::SupportsAutosaveAtRestart
- AFXWIN/CWinApp::SupportsRestartManager
- AFXWIN/CWinApp::Unregister
- AFXWIN/CWinApp::WinHelp
- AFXWIN/CWinApp::WriteProfileBinary
- AFXWIN/CWinApp::WriteProfileInt
- AFXWIN/CWinApp::WriteProfileString
- AFXWIN/CWinApp::EnableShellOpen
- AFXWIN/CWinApp::LoadStdProfileSettings
- AFXWIN/CWinApp::OnContextHelp
- AFXWIN/CWinApp::OnFileNew
- AFXWIN/CWinApp::OnFileOpen
- AFXWIN/CWinApp::OnFilePrintSetup
- AFXWIN/CWinApp::OnHelp
- AFXWIN/CWinApp::OnHelpFinder
- AFXWIN/CWinApp::OnHelpIndex
- AFXWIN/CWinApp::OnHelpUsing
- AFXWIN/CWinApp::RegisterShellFileTypes
- AFXWIN/CWinApp::SetAppID
- AFXWIN/CWinApp::SetRegistryKey
- AFXWIN/CWinApp::UnregisterShellFileTypes
- AFXWIN/CWinApp::m_bHelpMode
- AFXWIN/CWinApp::m_eHelpType
- AFXWIN/CWinApp::m_hInstance
- AFXWIN/CWinApp::m_lpCmdLine
- AFXWIN/CWinApp::m_nCmdShow
- AFXWIN/CWinApp::m_pActiveWnd
- AFXWIN/CWinApp::m_pszAppID
- AFXWIN/CWinApp::m_pszAppName
- AFXWIN/CWinApp::m_pszExeName
- AFXWIN/CWinApp::m_pszHelpFilePath
- AFXWIN/CWinApp::m_pszProfileName
- AFXWIN/CWinApp::m_pszRegistryKey
- AFXWIN/CWinApp::m_dwRestartManagerSupportFlags
- AFXWIN/CWinApp::m_nAutosaveInterval
- AFXWIN/CWinApp::m_pDataRecoveryHandler
helpviewer_keywords:
- CWinApp [MFC], CWinApp
- CWinApp [MFC], AddDocTemplate
- CWinApp [MFC], AddToRecentFileList
- CWinApp [MFC], ApplicationRecoveryCallback
- CWinApp [MFC], CloseAllDocuments
- CWinApp [MFC], CreatePrinterDC
- CWinApp [MFC], DelRegTree
- CWinApp [MFC], DoMessageBox
- CWinApp [MFC], DoWaitCursor
- CWinApp [MFC], EnableD2DSupport
- CWinApp [MFC], EnableHtmlHelp
- CWinApp [MFC], EnableTaskbarInteraction
- CWinApp [MFC], ExitInstance
- CWinApp [MFC], GetApplicationRecoveryParameter
- CWinApp [MFC], GetApplicationRecoveryPingInterval
- CWinApp [MFC], GetApplicationRestartFlags
- CWinApp [MFC], GetAppRegistryKey
- CWinApp [MFC], GetDataRecoveryHandler
- CWinApp [MFC], GetFirstDocTemplatePosition
- CWinApp [MFC], GetHelpMode
- CWinApp [MFC], GetNextDocTemplate
- CWinApp [MFC], GetPrinterDeviceDefaults
- CWinApp [MFC], GetProfileBinary
- CWinApp [MFC], GetProfileInt
- CWinApp [MFC], GetProfileString
- CWinApp [MFC], GetSectionKey
- CWinApp [MFC], HideApplication
- CWinApp [MFC], HtmlHelp
- CWinApp [MFC], InitInstance
- CWinApp [MFC], IsTaskbarInteractionEnabled
- CWinApp [MFC], LoadCursor
- CWinApp [MFC], LoadIcon
- CWinApp [MFC], LoadOEMCursor
- CWinApp [MFC], LoadOEMIcon
- CWinApp [MFC], LoadStandardCursor
- CWinApp [MFC], LoadStandardIcon
- CWinApp [MFC], OnDDECommand
- CWinApp [MFC], OnIdle
- CWinApp [MFC], OpenDocumentFile
- CWinApp [MFC], ParseCommandLine
- CWinApp [MFC], PreTranslateMessage
- CWinApp [MFC], ProcessMessageFilter
- CWinApp [MFC], ProcessShellCommand
- CWinApp [MFC], ProcessWndProcException
- CWinApp [MFC], Register
- CWinApp [MFC], RegisterWithRestartManager
- CWinApp [MFC], ReopenPreviousFilesAtRestart
- CWinApp [MFC], RestartInstance
- CWinApp [MFC], RestoreAutosavedFilesAtRestart
- CWinApp [MFC], Run
- CWinApp [MFC], RunAutomated
- CWinApp [MFC], RunEmbedded
- CWinApp [MFC], SaveAllModified
- CWinApp [MFC], SelectPrinter
- CWinApp [MFC], SetHelpMode
- CWinApp [MFC], SupportsApplicationRecovery
- CWinApp [MFC], SupportsAutosaveAtInterval
- CWinApp [MFC], SupportsAutosaveAtRestart
- CWinApp [MFC], SupportsRestartManager
- CWinApp [MFC], Unregister
- CWinApp [MFC], WinHelp
- CWinApp [MFC], WriteProfileBinary
- CWinApp [MFC], WriteProfileInt
- CWinApp [MFC], WriteProfileString
- CWinApp [MFC], EnableShellOpen
- CWinApp [MFC], LoadStdProfileSettings
- CWinApp [MFC], OnContextHelp
- CWinApp [MFC], OnFileNew
- CWinApp [MFC], OnFileOpen
- CWinApp [MFC], OnFilePrintSetup
- CWinApp [MFC], OnHelp
- CWinApp [MFC], OnHelpFinder
- CWinApp [MFC], OnHelpIndex
- CWinApp [MFC], OnHelpUsing
- CWinApp [MFC], RegisterShellFileTypes
- CWinApp [MFC], SetAppID
- CWinApp [MFC], SetRegistryKey
- CWinApp [MFC], UnregisterShellFileTypes
- CWinApp [MFC], m_bHelpMode
- CWinApp [MFC], m_eHelpType
- CWinApp [MFC], m_hInstance
- CWinApp [MFC], m_lpCmdLine
- CWinApp [MFC], m_nCmdShow
- CWinApp [MFC], m_pActiveWnd
- CWinApp [MFC], m_pszAppID
- CWinApp [MFC], m_pszAppName
- CWinApp [MFC], m_pszExeName
- CWinApp [MFC], m_pszHelpFilePath
- CWinApp [MFC], m_pszProfileName
- CWinApp [MFC], m_pszRegistryKey
- CWinApp [MFC], m_dwRestartManagerSupportFlags
- CWinApp [MFC], m_nAutosaveInterval
- CWinApp [MFC], m_pDataRecoveryHandler
ms.assetid: e426a3cd-0d15-40d6-bd55-beaa5feb2343
ms.openlocfilehash: 6366638ebfd5e78ad517a8913e4276d5cd820670
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62323361"
---
# <a name="cwinapp-class"></a>CWinApp 클래스

Windows 애플리케이션 개체를 파생하는 기본 클래스입니다.

## <a name="syntax"></a>구문

```
class CWinApp : public CWinThread
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CWinApp::CWinApp](#cwinapp)|`CWinApp` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CWinApp::AddDocTemplate](#adddoctemplate)|문서 서식 파일 사용 가능한 문서 템플릿의 응용 프로그램의 목록에 추가합니다.|
|[CWinApp::AddToRecentFileList](#addtorecentfilelist)|가장 최근에 사용한 (MRU) 파일 목록에 파일을 추가합니다.|
|[CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)|응용 프로그램이 예기치 않게 종료 될 때 프레임 워크에서 호출 됩니다.|
|[CWinApp::CloseAllDocuments](#closealldocuments)|모든 열린 문서를 닫습니다.|
|[CWinApp::CreatePrinterDC](#createprinterdc)|프린터 장치 컨텍스트를 만듭니다.|
|[CWinApp::DelRegTree](#delregtree)|지정된 된 키와 모든 하위 키를 삭제합니다.|
|[CWinApp::DoMessageBox](#domessagebox)|구현 [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox) 응용 프로그램에 대 한 합니다.|
|[CWinApp::DoWaitCursor](#dowaitcursor)|대기 커서를 켜고 끕니다.|
|[CWinApp::EnableD2DSupport](#enabled2dsupport)|응용 프로그램 D2D 지원을 사용합니다. 주 창이 초기화되기 전에 이 메서드를 호출합니다.|
|[CWinApp::EnableHtmlHelp](#enablehtmlhelp)|WinHelp 보다는 응용 프로그램에 대 한 HTMLHelp를 구현합니다.|
|[CWinApp::EnableTaskbarInteraction](#enabletaskbarinteraction)|작업 표시줄 상호 작용할 수 있도록 합니다.|
|[CWinApp::ExitInstance](#exitinstance)|응용 프로그램이 종료 될 때 정리 하기 위해 재정의 합니다.|
|[CWinApp::GetApplicationRecoveryParameter](#getapplicationrecoveryparameter)|응용 프로그램 복구 방법에 대 한 입력된 매개 변수를 검색합니다.|
|[CWinApp::GetApplicationRecoveryPingInterval](#getapplicationrecoverypinginterval)|다시 시작 관리자를 반환 하는 복구 콜백 함수에 대 한 대기 하는 시간의 길이 반환 합니다.|
|[CWinApp::GetApplicationRestartFlags](#getapplicationrestartflags)|다시 시작 관리자에 대 한 플래그를 반환 합니다.|
|[CWinApp::GetAppRegistryKey](#getappregistrykey)|Returns key for HKEY_CURRENT_USER\\"Software"\RegistryKey\ProfileName.|
|[CWinApp::GetDataRecoveryHandler](#getdatarecoveryhandler)|응용 프로그램의이 인스턴스에 대 한 데이터 복구 처리기를 가져옵니다.|
|[CWinApp::GetFirstDocTemplatePosition](#getfirstdoctemplateposition)|첫 번째 문서 서식 파일의 위치를 검색 합니다.|
|[CWinApp::GetHelpMode](#gethelpmode)|응용 프로그램에서 사용 하는 도움말의 형식을 검색 합니다.|
|[CWinApp::GetNextDocTemplate](#getnextdoctemplate)|문서 서식 파일의 위치를 검색 합니다. 재귀적으로 사용할된 수 있습니다.|
|[CWinApp::GetPrinterDeviceDefaults](#getprinterdevicedefaults)|프린터 장치 기본값을 검색합니다.|
|[CWinApp::GetProfileBinary](#getprofilebinary)|응용 프로그램의 진입점에서 이진 데이터를 검색합니다. INI 파일입니다.|
|[CWinApp::GetProfileInt](#getprofileint)|응용 프로그램의 진입점에서 정수를 검색합니다. INI 파일입니다.|
|[CWinApp::GetProfileString](#getprofilestring)|응용 프로그램의 진입점에서 문자열을 검색합니다. INI 파일입니다.|
|[CWinApp::GetSectionKey](#getsectionkey)|Returns key for HKEY_CURRENT_USER\\"Software"\RegistryKey\AppName\lpszSection.|
|[CWinApp::HideApplication](#hideapplication)|모든 문서를 닫기 전에 응용 프로그램을 숨깁니다.|
|[CWinApp::HtmlHelp](#htmlhelp)|호출 된 `HTMLHelp` Windows 함수입니다.|
|[CWinApp::InitInstance](#initinstance)|창 개체 만들기와 같은 Windows 인스턴스 초기화를 수행 하도록 재정의 합니다.|
|[CWinApp::IsTaskbarInteractionEnabled](#istaskbarinteractionenabled)|Windows 7 작업 표시줄의 상호 작용 사용 되는지 여부를 알려 줍니다.|
|[CWinApp::LoadCursor](#loadcursor)|커서 리소스를 로드 합니다.|
|[CWinApp::LoadIcon](#loadicon)|아이콘 리소스를 로드합니다.|
|[CWinApp::LoadOEMCursor](#loadoemcursor)|로드 Windows OEM 커서 미리 정의 된는 합니다 **OCR_** 창의 상수를 지정 합니다. 8.|
|[CWinApp::LoadOEMIcon](#loadoemicon)|Windows OEM 미리 정의 된 아이콘을 로드 하는 합니다 **OIC_** 창의 상수를 지정 합니다. 8.|
|[CWinApp::LoadStandardCursor](#loadstandardcursor)|로드는 Windows 커서 미리 정의 된는 합니다 **IDC_** 창의 상수를 지정 합니다. 8.|
|[CWinApp::LoadStandardIcon](#loadstandardicon)|Windows 미리 정의 된 아이콘을 로드 하는 합니다 **IDI_** 창의 상수를 지정 합니다. 8.|
|[CWinApp::OnDDECommand](#onddecommand)|호출에 대 한 응답에 대 한 동적 데이터 프레임 워크에서 DDE (교환)는 명령을 실행 합니다.|
|[CWinApp::OnIdle](#onidle)|응용 프로그램별 유휴 시간 처리를 수행 하려면 재정의 합니다.|
|[CWinApp::OpenDocumentFile](#opendocumentfile)|파일에서 문서를 열려고 프레임 워크에서 호출 됩니다.|
|[CWinApp::ParseCommandLine](#parsecommandline)|개별 매개 변수 및 명령줄에서 플래그를 구문 분석합니다.|
|[CWinApp::PreTranslateMessage](#pretranslatemessage)|Windows 함수로 디스패치 되기 전에 메시지를 필터링 [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) 하 고 [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage)합니다.|
|[CWinApp::ProcessMessageFilter](#processmessagefilter)|응용 프로그램에 도달 하기 전에 특정 메시지를 차단 합니다.|
|[CWinApp::ProcessShellCommand](#processshellcommand)|명령줄 인수 및 플래그를 처리합니다.|
|[CWinApp::ProcessWndProcException](#processwndprocexception)|응용 프로그램의 메시지 및 명령 처리기에 의해 throw 되는 모든 처리 되지 않은 예외를 가로챕니다.|
|[CWinApp::Register](#register)|사용자 지정된 등록을 수행합니다.|
|[CWinApp::RegisterWithRestartManager](#registerwithrestartmanager)|다시 시작 관리자를 사용 하 여 응용 프로그램을 등록 합니다.|
|[CWinApp::ReopenPreviousFilesAtRestart](#reopenpreviousfilesatrestart)|다시 시작 관리자가 응용 프로그램이 예기치 않게 종료 될 때 열려 있던 파일이 있는지 여부를 결정 합니다.|
|[CWinApp::RestartInstance](#restartinstance)|다시 시작 관리자에서 시작 된 응용 프로그램이 다시 시작을 처리 합니다.|
|[CWinApp::RestoreAutosavedFilesAtRestart](#restoreautosavedfilesatrestart)|응용 프로그램을 다시 시작 될 때 다시 시작 관리자 자동 저장 된 파일을 복원할지 여부를 결정 합니다.|
|[CWinApp::Run](#run)|기본 메시지 루프를 실행합니다. 메시지 루프에 맞게 재정의 합니다.|
|[CWinApp::RunAutomated](#runautomated)|응용 프로그램의 명령줄에 대 한 테스트를 **/Automation** 옵션입니다. 사용되지 않습니다. 값을 사용 하는 대신 [CCommandLineInfo::m_bRunAutomated](../../mfc/reference/ccommandlineinfo-class.md#m_brunautomated) 호출한 후 [ParseCommandLine](#parsecommandline)합니다.|
|[CWinApp::RunEmbedded](#runembedded)|응용 프로그램의 명령줄에 대 한 테스트를 **포함/** 옵션입니다. 사용되지 않습니다. 값을 사용 하는 대신 [CCommandLineInfo::m_bRunEmbedded](../../mfc/reference/ccommandlineinfo-class.md#m_brunembedded) 호출한 후 [ParseCommandLine](#parsecommandline)합니다.|
|[CWinApp::SaveAllModified](#saveallmodified)|모든 수정 된 문서를 저장 하 라는 메시지입니다.|
|[CWinApp::SelectPrinter](#selectprinter)|인쇄 대화 상자를 통해 사용자가 이전에 표시 된 프린터를 선택 합니다.|
|[CWinApp::SetHelpMode](#sethelpmode)|설정 하 고 응용 프로그램에서 사용 하는 도움말의 형식을 초기화 합니다.|
|[CWinApp::SupportsApplicationRecovery](#supportsapplicationrecovery)|다시 시작 관리자 예기치 않게 종료 하는 응용 프로그램을 복구 하는지 여부를 결정 합니다.|
|[CWinApp::SupportsAutosaveAtInterval](#supportsautosaveatinterval)|일정 한 간격으로 다시 시작 관리자에서 열려 있는 문서 여부를 결정 합니다.|
|[CWinApp::SupportsAutosaveAtRestart](#supportsautosaveatrestart)|확인 여부를 다시 시작 관리자에서 응용 프로그램 다시 시작 되 면 모든 열린 문서.|
|[CWinApp::SupportsRestartManager](#supportsrestartmanager)|응용 프로그램 다시 시작 관리자를 지원 하는지 여부를 결정 합니다.|
|[CWinApp::Unregister](#unregister)|등록을 취소 하 여 등록에 알려진 모든 항목을 `CWinApp` 개체입니다.|
|[CWinApp::WinHelp](#winhelp)|호출 된 `WinHelp` Windows 함수입니다.|
|[CWinApp::WriteProfileBinary](#writeprofilebinary)|응용 프로그램의 진입점에 이진 데이터를 씁니다. INI 파일입니다.|
|[CWinApp::WriteProfileInt](#writeprofileint)|응용 프로그램의 항목에 정수를 씁니다. INI 파일입니다.|
|[CWinApp::WriteProfileString](#writeprofilestring)|응용 프로그램의 항목에는 문자열을 씁니다. INI 파일입니다.|

### <a name="protected-methods"></a>보호된 메서드

|이름|설명|
|----------|-----------------|
|[CWinApp::EnableShellOpen](#enableshellopen)|Windows 파일 관리자에서 데이터 파일을 열 수 있습니다.|
|[CWinApp::LoadStdProfileSettings](#loadstdprofilesettings)|로드 표준입니다. INI 파일 설정을 사용 하면 MRU 목록 기능을 파일입니다.|
|[CWinApp::OnContextHelp](#oncontexthelp)|응용 프로그램 내에서 SHIFT + F1 도움말을 처리합니다.|
|[CWinApp::OnFileNew](#onfilenew)|ID_FILE_NEW 명령을 구현합니다.|
|[CWinApp::OnFileOpen](#onfileopen)|ID_FILE_OPEN 명령을 구현합니다.|
|[CWinApp::OnFilePrintSetup](#onfileprintsetup)|ID_FILE_PRINT_SETUP 명령을 구현합니다.|
|[CWinApp::OnHelp](#onhelp)|현재 컨텍스트를 사용하여 응용 프로그램 내에서 F1 도움말을 처리합니다.|
|[CWinApp::OnHelpFinder](#onhelpfinder)|ID_HELP_FINDER 및 ID_DEFAULT_HELP 명령 처리합니다.|
|[CWinApp::OnHelpIndex](#onhelpindex)|ID_HELP_INDEX 명령을 처리 하 고 기본 도움말 항목을 제공 합니다.|
|[CWinApp::OnHelpUsing](#onhelpusing)|ID_HELP_USING 명령을 처리합니다.|
|[CWinApp::RegisterShellFileTypes](#registershellfiletypes)|응용 프로그램의 모든 문서 유형에 Windows 파일 관리자를 등록합니다.|
|[CWinApp::SetAppID](#setappid)|응용 프로그램에 대 한 응용 프로그램 사용자 모델 ID를 명시적으로 설정합니다. 사용자 인터페이스 (좋습니다는 응용 프로그램 생성자)에 게 표시 되기 전에이 메서드를 호출 해야 합니다.|
|[CWinApp::SetRegistryKey](#setregistrykey)|대신의 레지스트리에 저장 될 응용 프로그램 설정 하면 됩니다. INI 파일입니다.|
|[CWinApp::UnregisterShellFileTypes](#unregistershellfiletypes)|응용 프로그램의 모든 문서 유형에 Windows 파일 관리자를 등록 취소합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CWinApp::m_bHelpMode](#m_bhelpmode)|사용자 (일반적으로 SHIFT + f1 키를 사용 하 여 호출) 도움말 컨텍스트 모드 인지를 나타냅니다.|
|[CWinApp::m_eHelpType](#m_ehelptype)|응용 프로그램에서 사용 하는 도움말의 형식을 지정 합니다.|
|[CWinApp::m_hInstance](#m_hinstance)|응용 프로그램의 현재 인스턴스를 식별합니다.|
|[CWinApp::m_lpCmdLine](#m_lpcmdline)|응용 프로그램에 대 한 명령줄을 지정 하는 null로 끝나는 문자열을 가리킵니다.|
|[CWinApp::m_nCmdShow](#m_ncmdshow)|창이 처음 표시 될 방법을 지정 합니다.|
|[CWinApp::m_pActiveWnd](#m_pactivewnd)|OLE 서버에 내부 활성화 되 면 컨테이너 응용 프로그램의 주 창에 대 한 포인터입니다.|
|[CWinApp::m_pszAppID](#m_pszappid)|응용 프로그램 사용자 모델 id입니다.|
|[CWinApp::m_pszAppName](#m_pszappname)|애플리케이션의 이름을 지정합니다.|
|[CWinApp::m_pszExeName](#m_pszexename)|응용 프로그램의 모듈 이름입니다.|
|[CWinApp::m_pszHelpFilePath](#m_pszhelpfilepath)|응용 프로그램의 도움말 파일 경로입니다.|
|[CWinApp::m_pszProfileName](#m_pszprofilename)|응용 프로그램입니다. INI 파일 이름입니다.|
|[CWinApp::m_pszRegistryKey](#m_pszregistrykey)|응용 프로그램 프로필 설정을 저장 하기 위한 전체 레지스트리 키를 확인 하는 데 사용 합니다.|

### <a name="protected-data-members"></a>보호된 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CWinApp::m_dwRestartManagerSupportFlags](#m_dwrestartmanagersupportflags)|다시 시작 관리자가 동작 하는 방식을 결정 하는 플래그입니다.|
|[CWinApp::m_nAutosaveInterval](#m_nautosaveinterval)|자동으로 저장 간격 (밀리초) 시간의 길이입니다.|
|[CWinApp::m_pDataRecoveryHandler](#m_pdatarecoveryhandler)|응용 프로그램에 대 한 데이터 복구 처리기에 대 한 포인터입니다.|

## <a name="remarks"></a>설명

응용 프로그램 개체는 응용 프로그램 (및 각 인스턴스의)을 초기화 하 고 응용 프로그램을 실행 하는 것에 대 한 멤버 함수를 제공 합니다.

Microsoft Foundation 클래스를 사용 하는 각 응용 프로그램에서 파생 된 개체를 포함할 수 있습니다만 `CWinApp`합니다. 이 개체가 생성 될 때 다른 C++ 전역 개체 생성 되 고 Windows를 호출 하는 경우 사용할 수 있는 이미 합니다 `WinMain` Microsoft Foundation Class 라이브러리를 제공 하는 함수입니다. 파생 된 선언 `CWinApp` 전역 수준 개체입니다.

응용 프로그램 클래스를 파생 하는 경우 `CWinApp`를 재정의 합니다 [InitInstance](#initinstance) 멤버 함수 응용 프로그램의 주 창 개체를 만듭니다.

외에 `CWinApp` 멤버 함수는 Microsoft Foundation Class 라이브러리를 제공에 액세스 하려면 다음 전역 함수에 `CWinApp` 개체 및 기타 전역 정보:

- [AfxGetApp](application-information-and-management.md#afxgetapp) 포인터를 가져옵니다는 `CWinApp` 개체입니다.

- [AfxGetInstanceHandle](application-information-and-management.md#afxgetinstancehandle) 현재 응용 프로그램 인스턴스에 대 한 핸들을 가져옵니다.

- [AfxGetResourceHandle](application-information-and-management.md#afxgetresourcehandle) 응용 프로그램의 리소스에 대 한 핸들을 가져옵니다.

- [AfxGetAppName](application-information-and-management.md#afxgetappname) 응용 프로그램의 이름을 포함 하는 문자열 포인터를 가져옵니다. 또는에 대 한 포인터를 해야 하는 경우는 `CWinApp` 개체를 사용 하 여 `m_pszExeName` 응용 프로그램의 이름을 가져옵니다.

참조 [CWinApp: 응용 프로그램 클래스](../../mfc/cwinapp-the-application-class.md) 대 한 자세한 내용은 `CWinApp` 다음 개요를 비롯 하 여 클래스:

- `CWinApp`-응용 프로그램 마법사에서 작성 한 코드를 파생 합니다.

- `CWinApp`응용 프로그램의 실행 순서로 역할입니다.

- `CWinApp`기본 멤버 함수 구현 합니다.

- `CWinApp`키 재정의 가능 합니다.

`m_hPrevInstance` 데이터 멤버는 더 이상 존재 합니다. 응용 프로그램의 다른 인스턴스가 실행 중인지 여부를 확인 하려면 명명된 된 뮤텍스를 사용 합니다. 뮤텍스를 열 수 없으면 다음 가지 실행 중인 응용 프로그램의 다른 인스턴스가 없습니다.

## <a name="inheritance-hierarchy"></a>상속 계층

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWinThread](../../mfc/reference/cwinthread-class.md)

`CWinApp`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

##  <a name="adddoctemplate"></a>  CWinApp::AddDocTemplate

응용 프로그램 유지 관리 하는 사용 가능한 문서 템플릿 목록에 문서 템플릿을 추가 하려면이 멤버 함수를 호출 합니다.

```
void AddDocTemplate(CDocTemplate* pTemplate);
```

### <a name="parameters"></a>매개 변수

*pTemplate*<br/>
에 대 한 포인터를 `CDocTemplate` 추가 합니다.

### <a name="remarks"></a>설명

호출 하기 전에 모든 문서는 응용 프로그램에 템플릿을 추가 해야 [RegisterShellFileTypes](#registershellfiletypes)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#35](../../mfc/reference/codesnippet/cpp/cwinapp-class_1.cpp)]

##  <a name="addtorecentfilelist"></a>  CWinApp::AddToRecentFileList

이 멤버 함수를 호출 *lpszPathName* 최근에 사용한 파일 목록입니다.

```
virtual void AddToRecentFileList(LPCTSTR lpszPathName);
```

### <a name="parameters"></a>매개 변수

*lpszPathName*<br/>
파일의 경로입니다.

### <a name="remarks"></a>설명

호출 해야 합니다 [LoadStdProfileSettings](#loadstdprofilesettings) 멤버 함수를이 멤버 함수를 사용 하기 전에 현재 MRU 파일 목록을 로드 합니다.

프레임 워크 파일을 열거나 새 이름으로 파일을 저장 하려면 다른 이름으로 저장 명령을 실행 하는 경우이 멤버 함수를 호출 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#36](../../mfc/reference/codesnippet/cpp/cwinapp-class_2.cpp)]

##  <a name="applicationrecoverycallback"></a>  CWinApp::ApplicationRecoveryCallback

응용 프로그램이 예기치 않게 종료 될 때 프레임 워크에서 호출 됩니다.

```
virtual DWORD ApplicationRecoveryCallback(LPVOID lpvParam);
```

### <a name="parameters"></a>매개 변수

*lpvParam*<br/>
[in] 사용 하도록 예약 합니다.

### <a name="return-value"></a>반환 값

이 메서드는 성공 하는 경우에 0 오류가 발생 한 경우에 0이 아닙니다.

### <a name="remarks"></a>설명

응용 프로그램 다시 시작 관리자를 지 원하는 경우 프레임 워크는 응용 프로그램에서 예기치 않게 종료 될 때이 함수를 호출 합니다.

기본 구현을 `ApplicationRecoveryCallback` 사용 하 여는 `CDataRecoveryHandler` 레지스트리에 현재 열려 있는 문서의 목록을 저장 합니다. 이 메서드는 모든 파일 자동 저장 되지 않습니다.

동작을 사용자 지정 하려면이 함수에 파생 된 재정의 [CWinApp 클래스](../../mfc/reference/cwinapp-class.md) 하거나 사용자 고유의 응용 프로그램 복구 메서드를 매개 변수로 전달 [CWinApp::RegisterWithRestartManager](#registerwithrestartmanager)합니다.

##  <a name="closealldocuments"></a>  CWinApp::CloseAllDocuments

종료 하기 전에 열린 모든 문서를 닫으려면이 멤버 함수를 호출 합니다.

```
void CloseAllDocuments(BOOL bEndSession);
```

### <a name="parameters"></a>매개 변수

*bEndSession*<br/>
Windows 세션을 종료 되 고 있는지 여부를 지정 합니다. 이 TRUE 이면 세션을 종료 합니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

호출 [HideApplication](#hideapplication) 호출 하기 전에 `CloseAllDocuments`입니다.

##  <a name="createprinterdc"></a>  CWinApp::CreatePrinterDC

선택한 프린터의 프린터 디바이스 컨텍스트 (DC)를 만들려면이 멤버 함수를 호출 합니다.

```
BOOL CreatePrinterDC(CDC& dc);
```

### <a name="parameters"></a>매개 변수

*dc*<br/>
프린터 장치 컨텍스트에 대 한 참조입니다.

### <a name="return-value"></a>반환 값

0이 아닌 프린터 장치 컨텍스트를 만들었습니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

`CreatePrinterDC` 컨트롤 인쇄를 사용할 수 있도록 참조에 의해에 전달 하는 장치 컨텍스트를 초기화 합니다.

인쇄 했으면 함수 성공적 이면 장치 컨텍스트를 파기 해야 합니다. 소멸자의 수를 [CDC](../../mfc/reference/cdc-class.md) 개체에서 그렇게 또는 호출 하 여 명시적으로 수행할 수 있습니다 [CDC::DeleteDC](../../mfc/reference/cdc-class.md#deletedc)합니다.

##  <a name="cwinapp"></a>  CWinApp::CWinApp

생성을 `CWinApp` 개체 및 패스 *lpszAppName* 응용 프로그램 이름으로 저장 되도록 합니다.

```
CWinApp(LPCTSTR lpszAppName = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszAppName*<br/>
Windows를 사용 하는 응용 프로그램 이름을 포함 하는 null로 끝나는 문자열입니다. 이 인수는 제공 하지 않으면 아니거나 null 일 경우 경우 `CWinApp` AFX_IDS_APP_TITLE 리소스 문자열 또는 실행 파일의 파일 이름을 사용 합니다.

### <a name="remarks"></a>설명

전역 개체를 생성 해야 하면 `CWinApp`-클래스를 파생 합니다. 하나만 있습니다 `CWinApp` 응용 프로그램의 개체입니다. 생성자에 대 한 포인터를 저장 합니다 `CWinApp` 개체 있도록 `WinMain` 개체의 멤버를 초기화 하 고 응용 프로그램을 실행 하는 함수를 호출할 수 있습니다.

##  <a name="delregtree"></a>  CWinApp::DelRegTree

특정 레지스트리 키와 모든 하위 키를 삭제합니다.

```
LONG DelRegTree(
    HKEY hParentKey,
    const CString& strKeyName);

LONG DelRegTree(
    HKEY hParentKey,
    const CString& strKeyName,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>매개 변수

*hParentKey*<br/>
레지스트리 키에 대 한 핸들입니다.

*strKeyName*<br/>
삭제 하려는 레지스트리 키의 이름입니다.

*pTM*<br/>
CAtlTransactionManager 개체에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

함수가 성공할 경우 반환 값은 ERROR_SUCCESS입니다. 함수가 실패 한 경우 반환 값은 winerror에 정의 된 0이 아닌 오류 코드입니다.

### <a name="remarks"></a>설명

지정된 된 키와 해당 하위 키를 삭제 하려면이 함수를 호출 합니다.

##  <a name="domessagebox"></a>  CWinApp::DoMessageBox

전역 함수에 대 한 메시지 상자를 구현 하려면이 멤버 함수를 호출 하는 프레임 워크 [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)합니다.

```
virtual int DoMessageBox(
    LPCTSTR lpszPrompt,
    UINT nType,
    UINT nIDPrompt);
```

### <a name="parameters"></a>매개 변수

*lpszPrompt*<br/>
메시지 상자 텍스트의 주소입니다.

*nType*<br/>
메시지 상자가 [스타일](../../mfc/reference/styles-used-by-mfc.md#message-box-styles)합니다.

*nIDPrompt*<br/>
도움말 상황에 맞는 문자열로 인덱스입니다.

### <a name="return-value"></a>반환 값

동일한 값으로 반환 `AfxMessageBox`합니다.

### <a name="remarks"></a>설명

메시지 상자를 열려면이 멤버 함수를 호출 하지 마십시오 사용 하 여 `AfxMessageBox` 대신 합니다.

응용 프로그램 전체 처리를 사용자 지정 하려면이 멤버 함수를 재정의 `AfxMessageBox` 호출 합니다.

##  <a name="dowaitcursor"></a>  CWinApp::DoWaitCursor

이 멤버 함수를 구현 하기 위해 프레임 워크에서 호출 됩니다 [CWaitCursor](../../mfc/reference/cwaitcursor-class.md)를 [CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor)하십시오 [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor), 및 [ CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)합니다.

```
virtual void DoWaitCursor(int nCode);
```

### <a name="parameters"></a>매개 변수

*nCode*<br/>
이 매개 변수가 1 이면 대기 커서를 표시 합니다. 0 인 경우 대기 커서를 참조 횟수를 증가 하지 않고 복원 됩니다. -1 이면 대기 커서를 종료 합니다.

### <a name="remarks"></a>설명

기본 모래 시계 커서를 구현합니다. `DoWaitCursor` 참조 횟수를 유지 관리합니다. 양수, 모래 시계 커서 표시 됩니다.

일반적으로 호출 하지는 하지만 `DoWaitCursor` 대기 커서를 변경 하거나 대기 커서가 표시 되는 동안에 추가 처리를 수행 하려면이 멤버 함수를 직접 재정의할 수 있습니다.

대기 커서를 구현 하는 보다 쉽게, 더 효율적인 방법은 사용 하 여 `CWaitCursor`입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#37](../../mfc/reference/codesnippet/cpp/cwinapp-class_3.cpp)]

##  <a name="enabled2dsupport"></a>  CWinApp::EnableD2DSupport

Visual Studio 2010 SP1이 필요합니다.

응용 프로그램 D2D 지원을 사용합니다. 주 창이 초기화되기 전에 이 메서드를 호출합니다.

```
BOOL EnableD2DSupport(
    D2D1_FACTORY_TYPE d2dFactoryType = D2D1_FACTORY_TYPE_SINGLE_THREADED,
    DWRITE_FACTORY_TYPE writeFactoryType = DWRITE_FACTORY_TYPE_SHARED);
```

### <a name="parameters"></a>매개 변수

*d2dFactoryType*<br/>
D2d 및 리소스의 스레딩 모델을 만듭니다.

*writeFactoryType*<br/>
쓰기 팩터리 개체를 공유 또는 격리는 지 여부를 지정 하는 값

### <a name="return-value"></a>반환 값

D2D 지원이 되었으면 FALSE-을 사용 하도록 설정 그렇지 않은 경우 TRUE를 반환합니다

##  <a name="enablehtmlhelp"></a>  CWinApp::EnableHtmlHelp

생성자 내에서이 멤버 함수를 호출 하면 `CWinApp`-HTMLHelp 응용 프로그램의 도움말에 사용할 클래스를 파생 합니다.

```
void EnableHtmlHelp();
```

### <a name="remarks"></a>설명

##  <a name="enableshellopen"></a>  CWinApp::EnableShellOpen

일반적으로이 함수를 호출 하면 `InitInstance` 데이터 파일에서 파일을 Windows 파일 관리자 내에서 두 번 클릭 하 여 응용 프로그램의 사용자를 사용 하도록 설정 하려면 재정의 합니다.

```
void EnableShellOpen();
```

### <a name="remarks"></a>설명

호출 된 `RegisterShellFileTypes` 멤버 함수와 함께에서이 함수 또는 제공을 합니다. REG 파일은 응용 프로그램을 사용 하 여 문서 유형의 수동 등록에 대 한 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#38](../../mfc/reference/codesnippet/cpp/cwinapp-class_4.cpp)]

##  <a name="enabletaskbarinteraction"></a>  CWinApp::EnableTaskbarInteraction

작업 표시줄 상호 작용할 수 있도록 합니다.

```
BOOL EnableTaskbarInteraction(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
Windows 7 작업 표시줄을 사용 하 여 상호 작용 (TRUE)를 사용할지 또는 해제 (FALSE) 여부를 지정 합니다.

### <a name="return-value"></a>반환 값

작업 표시줄의 상호 작용을 사용 하도록 설정 하거나 해제할 수 있으면 TRUE를 반환 합니다.

### <a name="remarks"></a>설명

주 창 만들기 전에이 메서드를 호출 해야, 그렇지 않으면 어설션 하 고 FALSE를 반환 합니다.

##  <a name="exitinstance"></a>  CWinApp::ExitInstance

프레임 워크에서 호출을 `Run` 멤버 함수는 응용 프로그램의이 인스턴스를 종료 합니다.

```
virtual int ExitInstance();
```

### <a name="return-value"></a>반환 값

응용 프로그램의 종료 코드 0은 오류 없이 나타내고 0 보다 큰 값에 오류가 발생 합니다. 이 값의 반환 값으로 사용 됩니다 `WinMain`합니다.

### <a name="remarks"></a>설명

호출 하지 마십시오이 멤버 함수 어디에서 나 하지만 내는 `Run` 멤버 함수입니다.

이 함수의 기본 구현은 응용 프로그램의 프레임 워크 옵션을 씁니다. INI 파일입니다. 응용 프로그램이 종료 될 때 정리 하기 위해이 함수를 재정의 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#39](../../mfc/reference/codesnippet/cpp/cwinapp-class_5.cpp)]

##  <a name="getapplicationrecoveryparameter"></a>  CWinApp::GetApplicationRecoveryParameter

응용 프로그램 복구 방법에 대 한 입력된 매개 변수를 검색합니다.

```
virtual LPVOID GetApplicationRecoveryParameter();
```

### <a name="return-value"></a>반환 값

기본 입력된 매개 변수는 응용 프로그램 복구 방법에 대 한 합니다.

### <a name="remarks"></a>설명

이 함수의 기본 동작은 NULL을 반환합니다.

자세한 내용은 [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)합니다.

##  <a name="getapplicationrecoverypinginterval"></a>  CWinApp::GetApplicationRecoveryPingInterval

다시 시작 관리자를 반환 하는 복구 콜백 함수에 대 한 대기 하는 시간의 길이 반환 합니다.

```
virtual DWORD GetApplicationRecoveryPingInterval();
```

### <a name="return-value"></a>반환 값

시간 (밀리초)의 길이입니다.

### <a name="remarks"></a>설명

예기치 않게 다시 시작 관리자 종료를 사용 하 여 등록 된 응용 프로그램, 응용 프로그램 열려 있는 문서를 저장 하려고 하 고 복구 콜백 함수를 호출 합니다. 기본 복구 콜백 함수는 [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)합니다.

프레임 워크를 반환 하는 복구 콜백 함수에 대 한 대기 하는 시간의 길이 ping 간격입니다. Ping 간격을 재정의 하 여 사용자 지정할 수 있습니다 `CWinApp::GetApplicationRecoveryPingInterval` 또는 사용자 지정 값을 제공 하 여 `RegisterWithRestartManager`입니다.

##  <a name="getapplicationrestartflags"></a>  CWinApp::GetApplicationRestartFlags

다시 시작 관리자에 대 한 플래그를 반환 합니다.

```
virtual DWORD GetApplicationRestartFlags();
```

### <a name="return-value"></a>반환 값

다시 시작 관리자에 대 한 플래그입니다. 기본 구현에서는 0을 반환합니다.

### <a name="remarks"></a>설명

다시 시작 관리자에 대 한 플래그 기본 구현과 효과가 없습니다. 향후 용도로 제공 됩니다.

플래그를 사용 하 여 다시 시작 관리자를 사용 하 여 응용 프로그램을 등록할 때 설정한 [CWinApp::RegisterWithRestartManager](#registerwithrestartmanager)합니다.

다시 시작 관리자 플래그에 대 한 가능한 값은 다음과 같습니다.

- RESTART_NO_CRASH

- RESTART_NO_HANG

- RESTART_NO_PATCH

- RESTART_NO_REBOOT

##  <a name="getappregistrykey"></a>  CWinApp::GetAppRegistryKey

HKEY_CURRENT_USER에 대 한 키를 반환 합니다.\\"소프트웨어" \RegistryKey\ProfileName 합니다.

```
HKEY GetAppRegistryKey(CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>매개 변수

*pTM*<br/>
`CAtlTransactionManager` 개체에 대한 포인터입니다.

### <a name="return-value"></a>반환 값

함수가 성공 하면 응용 프로그램 키 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

##  <a name="getdatarecoveryhandler"></a>  CWinApp::GetDataRecoveryHandler

응용 프로그램의이 인스턴스에 대 한 데이터 복구 처리기를 가져옵니다.

```
virtual CDataRecoveryHandler *GetDataRecoveryHandler();
```

### <a name="return-value"></a>반환 값

응용 프로그램의이 인스턴스에 대 한 데이터 복구 처리기입니다.

### <a name="remarks"></a>설명

다시 시작 관리자를 사용 하는 각 응용 프로그램의 인스턴스 하나 있어야 합니다 [CDataRecoveryHandler 클래스](../../mfc/reference/cdatarecoveryhandler-class.md)합니다. 이 클래스는 열려 있는 문서 및 자동 저장 파일을 모니터링 하는 일을 담당 합니다. 동작을 `CDataRecoveryHandler` 다시 시작 관리자의 구성에 따라 달라 집니다. 자세한 내용은 [CDataRecoveryHandler 클래스](../../mfc/reference/cdatarecoveryhandler-class.md)합니다.

이 메서드는 Windows Vista 이전 운영 체제에서 NULL을 반환 합니다. Windows Vista 이전 운영 체제에서 다시 시작 관리자 지원 되지 않습니다.

응용 프로그램에 현재 없는 경우 데이터 복구 처리기를이 메서드 하나를 만들어에 대 한 포인터를 반환 합니다.

##  <a name="getfirstdoctemplateposition"></a>  CWinApp::GetFirstDocTemplatePosition

응용 프로그램에서 첫 번째 문서 서식 파일의 위치를 가져옵니다.

```
POSITION GetFirstDocTemplatePosition() const;
```

### <a name="return-value"></a>반환 값

반복 또는 개체 포인터 검색;에 사용할 수 있는 위치 값 목록이 비어 있는 경우 NULL입니다.

### <a name="remarks"></a>설명

에 대 한 호출에서 반환 되는 위치 값 사용 [GetNextDocTemplate](#getnextdoctemplate) 첫 번째 가져오려는 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) 개체입니다.

##  <a name="gethelpmode"></a>  CWinApp::GetHelpMode

응용 프로그램에서 사용 하는 도움말의 형식을 검색 합니다.

```
AFX_HELP_TYPE GetHelpMode();
```

### <a name="return-value"></a>반환 값

응용 프로그램에서 사용 하는 도움말 형식입니다. 참조 [CWinApp::m_eHelpType](#m_ehelptype) 자세한 내용은 합니다.

##  <a name="getnextdoctemplate"></a>  CWinApp::GetNextDocTemplate

로 식별 되는 문서 템플릿을 가져옵니다 *pos*에서 설정한 *pos* 위치 값입니다.

```
CDocTemplate* GetNextDocTemplate(POSITION& pos) const;
```

### <a name="parameters"></a>매개 변수

*pos*<br/>
에 대 한 이전 호출에서 반환 된 위치 값에 대 한 참조가 `GetNextDocTemplate` 나 [GetFirstDocTemplatePosition](#getfirstdoctemplateposition)합니다. 값이이 호출에서 다음 위치로 업데이트 됩니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) 개체입니다.

### <a name="remarks"></a>설명

사용할 수 있습니다 `GetNextDocTemplate` 정방향 반복 루프에 대 한 호출의 초기 위치를 설정한 경우에서 `GetFirstDocTemplatePosition`합니다.

사용자 위치 값이 유효한 지 확인 해야 합니다. 올바르지 않으면 Microsoft Foundation Class 라이브러리의 디버그 버전 어설션 합니다.

검색된 문서 서식 파일은 마지막 경우 사용 가능한 다음 새 값 *pos* NULL로 설정 됩니다.

##  <a name="getprinterdevicedefaults"></a>  CWinApp::GetPrinterDeviceDefaults

인쇄에 대 한 프린터 장치 컨텍스트를 준비 하려면이 멤버 함수를 호출 합니다.

```
BOOL GetPrinterDeviceDefaults(struct tagPDA* pPrintDlg);
```

### <a name="parameters"></a>매개 변수

*pPrintDlg*<br/>
에 대 한 포인터를 [PRINTDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpda) 구조입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

Windows에서 현재 프린터 기본값을 검색합니다. INI 필요에 따라 파일 또는 인쇄 설정에서 사용자가 설정 된 마지막 프린터 구성을 사용 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#40](../../mfc/reference/codesnippet/cpp/cwinapp-class_6.cpp)]

##  <a name="getprofilebinary"></a>  CWinApp::GetProfileBinary

응용 프로그램 레지스트리의 지정된 된 섹션 내에 있는 항목에서 이진 데이터를 검색 하려면이 멤버 함수 호출 또는 합니다. INI 파일입니다.

```
BOOL GetProfileBinary(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPBYTE* ppData,
    UINT* pBytes);
```

### <a name="parameters"></a>매개 변수

*lpszSection*<br/>
항목이 포함된 섹션을 지정하는 null로 끝나는 문자열을 가리킵니다.

*lpszEntry*<br/>
값을 검색할 항목이 포함된 null로 끝나는 문자열을 가리킵니다.

*ppData*<br/>
데이터의 주소를 수신 하는 포인터를 가리킵니다.

*pBytes*<br/>
크기 (바이트)의 데이터를 받을 UINT 가리킵니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 따라서 대/소문자 구분 하지에서 문자열을 *lpszSection* 및 *lpszEntry* 매개 변수에서는 다를 수 있습니다.

> [!NOTE]
> `GetProfileBinary` 버퍼를 할당 하 고 해당 주소에서 반환 \* *ppData*합니다. 호출자가 사용 하 여 버퍼를 해제 하는 일을 담당 **delete**합니다.

> [!IMPORTANT]
> 이 함수에서 반환된 데이터는 NULL로 끝나지 않아도 되며 호출자는 유효성 검사를 수행해야 합니다. 자세한 내용은 [버퍼 오버런 방지](/windows/desktop/SecBP/avoiding-buffer-overruns)를 참조하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#41](../../mfc/reference/codesnippet/cpp/cwinapp-class_7.cpp)]

추가 예제를 보려면 [CWinApp::WriteProfileBinary](#writeprofilebinary)합니다.

##  <a name="getprofileint"></a>  CWinApp::GetProfileInt

.INI 파일 또는 응용 프로그램 레지스트리의 지정된 섹션 내에 있는 항목으로 정수 값을 검색하려면 이 멤버 함수를 호출합니다.

```
UINT GetProfileInt(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    int nDefault);
```

### <a name="parameters"></a>매개 변수

*lpszSection*<br/>
항목이 포함된 섹션을 지정하는 null로 끝나는 문자열을 가리킵니다.

*lpszEntry*<br/>
값을 검색할 항목이 포함된 null로 끝나는 문자열을 가리킵니다.

*nDefault*<br/>
프레임워크에서 항목을 찾을 수 없는 경우 반환할 기본값을 지정합니다.

### <a name="return-value"></a>반환 값

함수가 성공하면 문자열의 정수 값은 지정된 항목 다음에 오게 됩니다. 반환 값은 값을 *n 기본* 함수 항목을 찾을 수 없는 경우 매개 변수입니다. 지정한 항목에 해당하는 값이 정수가 아닌 경우 반환 값은 0입니다.

이 멤버 함수는 .INI 파일에서 값에 대한 16 진수 표기법을 지원합니다. 부호 있는 정수를 검색할 때는 값을 캐스팅 해야는 **int**합니다.

### <a name="remarks"></a>설명

이 멤버 함수는 따라서 대/소문자 구분 하지에서 문자열을 *lpszSection* 및 *lpszEntry* 매개 변수에서는 다를 수 있습니다.

> [!IMPORTANT]
> 이 함수에서 반환된 데이터는 NULL로 끝나지 않아도 되며 호출자는 유효성 검사를 수행해야 합니다. 자세한 내용은 [버퍼 오버런 방지](/windows/desktop/SecBP/avoiding-buffer-overruns)를 참조하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#42](../../mfc/reference/codesnippet/cpp/cwinapp-class_8.cpp)]

추가 예제를 보려면 [cwinapp:: Writeprofileint](#writeprofileint)합니다.

##  <a name="getprofilestring"></a>  CWinApp::GetProfileString

응용 프로그램의 레지스트리에 지정된 된 섹션 내에 있는 항목을 사용 하 여 연결 문자열을 검색 하려면이 멤버 함수 호출 또는 합니다. INI 파일입니다.

```
CString GetProfileString(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPCTSTR lpszDefault = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszSection*<br/>
항목이 포함된 섹션을 지정하는 null로 끝나는 문자열을 가리킵니다.

*lpszEntry*<br/>
해당 문자열은 검색할 항목이 포함 된 null로 끝나는 문자열을 가리킵니다. 이 값에 NULL이 아니어야 합니다.

*lpszDefault*<br/>
초기화 파일의 항목을 찾을 수 없는 경우 제공된 된 항목의 기본 문자열 값을 가리킵니다.

### <a name="return-value"></a>반환 값

반환 값은 응용 프로그램의 문자열입니다. INI 파일 또는 *lpszDefault* 문자열을 찾을 수 없는 경우. 프레임 워크에서 지원 되는 최대 문자열 길이가 _max_path(256 합니다. 하는 경우 *lpszDefault* 가 null 인 경우 반환 값은 빈 문자열입니다.

### <a name="remarks"></a>설명

> [!IMPORTANT]
> 이 함수에서 반환된 데이터는 NULL로 끝나지 않아도 되며 호출자는 유효성 검사를 수행해야 합니다. 자세한 내용은 [버퍼 오버런 방지](/windows/desktop/SecBP/avoiding-buffer-overruns)를 참조하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]

다른 예를 들어에 대 한 예제를 참조 하세요 [CWinApp::GetProfileInt](#getprofileint)합니다.

##  <a name="getsectionkey"></a>  CWinApp::GetSectionKey

HKEY_CURRENT_USER에 대 한 키를 반환 합니다.\\"소프트웨어" \RegistryKey\AppName\lpszSection 합니다.

```
HKEY GetSectionKey(
    LPCTSTR lpszSection,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszSection*<br/>
가져올 키의 이름입니다.

*pTM*<br/>
`CAtlTransactionManager` 개체에 대한 포인터입니다.

### <a name="return-value"></a>반환 값

함수가 성공 하면; 섹션 키 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

##  <a name="hideapplication"></a>  CWinApp::HideApplication

열려 있는 문서를 닫기 전에 응용 프로그램을 숨기려면이 멤버 함수를 호출 합니다.

```
void HideApplication();
```

##  <a name="htmlhelp"></a>  CWinApp::HtmlHelp

HTMLHelp 응용 프로그램을 호출 하려면이 멤버 함수를 호출 합니다.

```
virtual void HtmlHelp(
    DWORD_PTR dwData,
    UINT nCmd = 0x000F);
```

### <a name="parameters"></a>매개 변수

*dwData*<br/>
추가 데이터를 지정합니다. 값에 따라 사용 되는 값을 *nCmd* 매개 변수입니다.

*nCmd*<br/>
요청한 도움말의 형식을 지정합니다. 가능한 값 목록과 미치는 영향에 대 한 합니다 *dwData* 매개 변수를 참조 합니다 *uCommand* 에 대 한 the HTMLHelp API 함수에서 Windows SDK에 설명 된 매개 변수.

### <a name="remarks"></a>설명

프레임 워크는 또한 HTMLHelp 응용 프로그램을 호출 하려면이 함수를 호출 합니다.

프레임 워크를 자동으로 닫힙니다 HTMLHelp 응용 프로그램을 응용 프로그램을 종료 하는 경우.

##  <a name="initinstance"></a>  CWinApp::InitInstance

Windows는 동시에 실행 하려면 동일한 프로그램의 여러 복사본을 허용 합니다.

```
virtual BOOL InitInstance();
```

### <a name="return-value"></a>반환 값

초기화에 성공 하면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

응용 프로그램 초기화 개념적으로 두 영역으로 나뉩니다: 첫 번째 수행 되는 일회성 응용 프로그램 초기화 시간 프로그램 실행 및 각 실행 되는 인스턴스 초기화 시간 처음으로 포함 하 여 프로그램 실행을 복사 합니다. 프레임 워크의 구현의 `WinMain` 이 함수를 호출 합니다.

재정의 `InitInstance` Windows에서 실행 중인 응용 프로그램의 각 새 인스턴스를 초기화 합니다. 재정의 하는 일반적으로 `InitInstance` 주 창 개체를 생성 하 고 설정 하 여 `CWinThread::m_pMainWnd` 창으로 가리키도록 데이터 멤버입니다. 이 멤버 함수를 재정의에 대 한 자세한 내용은 참조 하세요. [CWinApp: 응용 프로그램 클래스](../../mfc/cwinapp-the-application-class.md)합니다.

> [!NOTE]
> MFC 응용 프로그램은 단일 스레드 아파트 (STA)로 초기화 되어야 합니다. 호출 하는 경우 [CoInitializeEx](/windows/desktop/api/combaseapi/nf-combaseapi-coinitializeex) 에서 프로그램 `InitInstance` 재정의 COINIT_APARTMENTTHREADED (COINIT_MULTITHREADED 아님)를 지정 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCListView#9](../../atl/reference/codesnippet/cpp/cwinapp-class_10.cpp)]

##  <a name="istaskbarinteractionenabled"></a>  CWinApp::IsTaskbarInteractionEnabled

Windows 7 작업 표시줄의 상호 작용 사용 되는지 여부를 알려 줍니다.

```
virtual BOOL IsTaskbarInteractionEnabled();
```

### <a name="return-value"></a>반환 값

TRUE를 반환 합니다 `EnableTaskbarInteraction` 가 호출 된 운영 체제가 Windows 7 이상 및 합니다.

### <a name="remarks"></a>설명

작업 표시줄의 상호 작용 MDI 응용 프로그램 마우스 포인터를 응용 프로그램 작업 표시줄 단추 위로 가져갈 때 표시 되는 별도 탭된 미리 보기에 MDI 자식 폼의 콘텐츠를 표시 하는 것을 의미 합니다.

##  <a name="loadcursor"></a>  CWinApp::LoadCursor

으로 명명 된 커서 리소스를 로드 *lpszResourceName* 또는 지정 된 *nIDResource* 에서 현재 실행 파일입니다.

```
HCURSOR LoadCursor(LPCTSTR lpszResourceName) const;  HCURSOR LoadCursor(UINT nIDResource) const;
```

### <a name="parameters"></a>매개 변수

*lpszResourceName*<br/>
커서 리소스의 이름이 포함 된 null로 끝나는 문자열을 가리킵니다. 사용할 수는 `CString` 이 인수에 대 한 합니다.

*nIDResource*<br/>
커서 리소스의 ID입니다. 리소스의 목록을 참조 하세요 [LoadCursor](/windows/desktop/api/winuser/nf-winuser-loadcursora) Windows SDK에 있습니다.

### <a name="return-value"></a>반환 값

성공할 경우 커서에 대 한 핸들 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

`LoadCursor` 이 로드 되지 않은 이전; 하는 경우에 커서 메모리에 로드 그렇지 않으면 기존 리소스의 핸들을 검색합니다.

사용 된 [LoadStandardCursor](#loadstandardcursor) 또는 [LoadOEMCursor](#loadoemcursor) 미리 정의 된 Windows 커서를 액세스 하는 멤버 함수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#44](../../mfc/reference/codesnippet/cpp/cwinapp-class_11.cpp)]

##  <a name="loadicon"></a>  CWinApp::LoadIcon

으로 명명 된 아이콘 리소스를 로드 *lpszResourceName* 또는 지정 된 *nIDResource* 실행 파일에서 합니다.

```
HICON LoadIcon(LPCTSTR lpszResourceName) const;  HICON LoadIcon(UINT nIDResource) const;
```

### <a name="parameters"></a>매개 변수

*lpszResourceName*<br/>
아이콘 리소스의 이름을 포함 하는 null로 끝나는 문자열을 가리킵니다. 사용할 수도 있습니다는 `CString` 이 인수에 대 한 합니다.

*nIDResource*<br/>
아이콘 리소스의 ID.

### <a name="return-value"></a>반환 값

성공할 경우 아이콘에 대 한 핸들 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

`LoadIcon` 이 로드 되지 않은 이전; 하는 경우에 아이콘을 로드 그렇지 않으면 기존 리소스의 핸들을 검색합니다.

사용할 수는 [LoadStandardIcon](#loadstandardicon) 또는 [LoadOEMIcon](#loadoemicon) 멤버 함수를 미리 정의 된 Windows 아이콘에 액세스 합니다.

> [!NOTE]
> 이 멤버 함수는 Win32 API 함수를 호출 [LoadIcon](/windows/desktop/api/winuser/nf-winuser-loadicona)만 크기가 SM_CXICON 및 SM_CYICON 시스템 메트릭 값을 준수 하는 아이콘을 로드할 수는 있습니다.

##  <a name="loadoemcursor"></a>  CWinApp::LoadOEMCursor

로드는 Windows에 의해 지정 된 커서 리소스 미리 정의 된 *nIDCursor*합니다.

```
HCURSOR LoadOEMCursor(UINT nIDCursor) const;
```

### <a name="parameters"></a>매개 변수

*nIDCursor*<br/>
**OCR_** 미리 정의 된 Windows 커서를 지정 하는 상수 식별자를 매니페스트 합니다. 있어야 `#define OEMRESOURCE` 하기 전에 `#include \<afxwin.h>` 에 액세스할 수 합니다 **OCR_** WINDOWS의 상수입니다. 8.

### <a name="return-value"></a>반환 값

성공할 경우 커서에 대 한 핸들 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

사용 된 `LoadOEMCursor` 또는 [LoadStandardCursor](#loadstandardcursor) 미리 정의 된 Windows 커서를 액세스 하는 멤버 함수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#45](../../mfc/reference/codesnippet/cpp/cwinapp-class_12.h)]

[!code-cpp[NVC_MFCWindowing#46](../../mfc/reference/codesnippet/cpp/cwinapp-class_13.cpp)]

##  <a name="loadoemicon"></a>  CWinApp::LoadOEMIcon

로드는 Windows에 의해 지정 된 아이콘 리소스 미리 정의 된 *nIDIcon*합니다.

```
HICON LoadOEMIcon(UINT nIDIcon) const;
```

### <a name="parameters"></a>매개 변수

*nIDIcon*<br/>
**OIC_** 미리 정의 된 Windows 아이콘을 지정 하는 상수 식별자를 매니페스트 합니다. 있어야 `#define OEMRESOURCE` 하기 전에 `#include \<afxwin.h>` 에 액세스 하려면 합니다 **OIC_** WINDOWS의 상수입니다. 8.

### <a name="return-value"></a>반환 값

성공할 경우 아이콘에 대 한 핸들 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

사용 된 `LoadOEMIcon` 또는 [LoadStandardIcon](#loadstandardicon) 멤버 함수를 미리 정의 된 Windows 아이콘에 액세스 합니다.

##  <a name="loadstandardcursor"></a>  CWinApp::LoadStandardCursor

미리 정의 된 커서 리소스는 Windows를 로드 하는 *lpszCursorName* 지정 합니다.

```
HCURSOR LoadStandardCursor(LPCTSTR lpszCursorName) const;
```

### <a name="parameters"></a>매개 변수

*lpszCursorName*<br/>
**IDC_** 미리 정의 된 Windows 커서를 지정 하는 상수 식별자를 매니페스트 합니다. 이러한 식별자는 WINDOWS에 정의 됩니다. 8. 다음 목록은 가능한 미리 정의 된 값과 의미 *lpszCursorName*:

- IDC_ARROW 표준 화살표 커서

- IDC_IBEAM 표준 텍스트 삽입 커서

- Windows에는 시간이 오래 걸리는 작업을 수행 하는 경우에 사용 되는 IDC_WAIT 모래 시계 커서

- 선택 영역에 대 한 IDC_CROSS 십자 모양 커서

- 수직으로 가리키는 IDC_UPARROW 화살표

- 사용 되지 않는 IDC_SIZE 되거나 지원 되지 않는; IDC_SIZEALL 사용

- IDC_SIZEALL는 십자형 화살표입니다. 창의 크기를 조정 하는 데 커서입니다.

- 사용 되지 않는 IDC_ICON 되거나 지원 되지 않는 합니다. IDC_ARROW를 사용 합니다.

- 왼쪽 위 모서리와 오른쪽 아래에서 끝나는 사용 하 여 IDC_SIZENWSE 양방향 화살표

- 끝이 오른쪽 및 아래쪽 왼쪽 위에 있는 양방향 화살표 IDC_SIZENESW

- 가로 IDC_SIZEWE 양방향 화살표

- 세로 IDC_SIZENS 양방향 화살표

### <a name="return-value"></a>반환 값

성공할 경우 커서에 대 한 핸들 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

사용 된 `LoadStandardCursor` 또는 [LoadOEMCursor](#loadoemcursor) 미리 정의 된 Windows 커서를 액세스 하는 멤버 함수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#47](../../mfc/reference/codesnippet/cpp/cwinapp-class_14.cpp)]

##  <a name="loadstandardicon"></a>  CWinApp::LoadStandardIcon

미리 정의 된 아이콘 리소스를 Windows를 로드 하는 *lpszIconName* 지정 합니다.

```
HICON LoadStandardIcon(LPCTSTR lpszIconName) const;
```

### <a name="parameters"></a>매개 변수

*lpszIconName*<br/>
미리 정의 된 Windows 아이콘을 지정 하는 매니페스트 상수 식별자입니다. 이러한 식별자는 WINDOWS에 정의 됩니다. 8. 가능한 미리 정의 된 값 및 해당 설명의 목록을 참조 하세요. 합니다 *lpIconName* 에 매개 변수 [LoadIcon](/windows/desktop/api/winuser/nf-winuser-loadicona) Windows SDK의 합니다.

### <a name="return-value"></a>반환 값

성공할 경우 아이콘에 대 한 핸들 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

사용 된 `LoadStandardIcon` 또는 [LoadOEMIcon](#loadoemicon) 멤버 함수를 미리 정의 된 Windows 아이콘에 액세스 합니다.

##  <a name="loadstdprofilesettings"></a>  CWinApp::LoadStdProfileSettings

내에서이 멤버 함수를 호출 합니다 [InitInstance](#initinstance) 멤버 함수를 활성화 및 가장 최근에 사용한 (MRU) 파일의 목록을 로드 하 고 마지막으로 상태를 미리 봅니다.

```
void LoadStdProfileSettings(UINT nMaxMRU = _AFX_MRU_COUNT);
```

### <a name="parameters"></a>매개 변수

*nMaxMRU*<br/>
최근에 사용한 파일 추적의 수입니다.

### <a name="remarks"></a>설명

하는 경우 *nMaxMRU* 0 인 최근에 사용한 목록이 없습니다. 그대로 유지 됩니다.

##  <a name="m_bhelpmode"></a>  CWinApp::m_bHelpMode

응용 프로그램 (일반적으로 사용 하 여 호출 SHIFT + F1); 도움말 컨텍스트 모드에 있으면 TRUE입니다. 그렇지 않으면 FALSE입니다.

```
BOOL m_bHelpMode;
```

### <a name="remarks"></a>설명

도움말 컨텍스트 모드에서는 커서 물음표 되며 사용자 화면에 대 한 이동할 수 있습니다. 도움말 모드에 있을 때 특수 한 처리를 구현 하려는 경우이 플래그를 검사 합니다. `m_bHelpMode` BOOL 형식의 공용 변수가입니다.

##  <a name="m_dwrestartmanagersupportflags"></a>  CWinApp::m_dwRestartManagerSupportFlags

다시 시작 관리자가 동작 하는 방식을 결정 하는 플래그입니다.

```
DWORD m_dwRestartManagerSupportFlags;
```

### <a name="remarks"></a>설명

다시 시작 관리자를 사용 하도록 설정 하려면 설정 `m_dwRestartManagerSupportFlags` 원하는 동작입니다. 다음 표에서 사용할 수 있는 플래그를 표시 합니다.

|||
|-|-|
|플래그|설명|
|AFX_RESTART_MANAGER_SUPPORT_RESTART|응용 프로그램은 사용 하 여 등록 [CWinApp::RegisterWithRestartManager](#registerwithrestartmanager)합니다. 다시 시작 관리자는 예기치 않게 종료 되 면 응용 프로그램을 다시 시작 하는 일을 담당 합니다.|
|- AFX_RESTART_MANAGER_SUPPORT_RECOVERY|응용 프로그램은 다시 시작 관리자를 사용 하 여 등록 및 응용 프로그램을 다시 시작 될 때 다시 시작 관리자 복구 콜백 함수를 호출 합니다. 기본 복구 콜백 함수는 [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)합니다.|
|- AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART|자동 저장을 사용 하 고 다시 시작 관리자에서 응용 프로그램 다시 시작 될 때 모든 문서를 공개 합니다.|
|- AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL|자동 저장을 사용 하 고 다시 시작 관리자에서 일정 한 간격으로 모든 열린 문서. 간격 정의한 [CWinApp::m_nAutosaveInterval](#m_nautosaveinterval)합니다.|
|- AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES|다시 시작 관리자는 예기치 못한 종료에서 응용 프로그램을 다시 시작한 후 이전에 열려 있는 문서를 엽니다. 합니다 [CDataRecoveryHandler 클래스](../../mfc/reference/cdatarecoveryhandler-class.md) 열린 문서의 목록을 저장 및 복원에 처리 합니다.|
|- AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES|응용 프로그램을 다시 시작한 후 자동 저장 된 파일을 복원 하 라는 메시지를 표시 하는 다시 시작 관리자입니다. `CDataRecoveryHandler` 클래스는 사용자를 쿼리 합니다.|
|- AFX_RESTART_MANAGER_SUPPORT_NO_AUTOSAVE|AFX_RESTART_MANAGER_SUPPORT_RESTART, AFX_RESTART_MANAGER_SUPPORT_RECOVER, 및 AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES의 합집합입니다.|
|- AFX_RESTART_MANAGER_SUPPORT_ALL_ASPECTS|AFX_RESTART_MANAGER_SUPPORT_NO_AUTOSAVE, AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART, AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL, 및 AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES의 합집합입니다.|
|- AFX_RESTART_MANAGER_SUPPORT_RESTART_ASPECTS|AFX_RESTART_MANAGER_SUPPORT_RESTART, AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART, AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES, 및 AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES의 합집합입니다.|
|- AFX_RESTART_MANAGER_SUPPORT_RECOVERY_ASPECTS|Union ofAFX_RESTART_MANAGER_SUPPORT_RECOVERY, AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL, AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES, 및 AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES 합니다.|

##  <a name="m_ehelptype"></a>  CWinApp::m_eHelpType

이 데이터 멤버의 형식은 열거형된 형식 내에 정의 된 AFX_HELP_TYPE는 `CWinApp` 클래스입니다.

```
AFX_HELP_TYPE m_eHelpType;
```

### <a name="remarks"></a>설명

AFX_HELP_TYPE 열거형은 다음과 같이 정의 됩니다.

```
enum AFX_HELP_TYPE {
    afxWinHelp = 0,
    afxHTMLHelp = 1
    };
```

- HTML 도움말에는 응용 프로그램의 도움말을 설정 하려면 호출 [SetHelpMode](#sethelpmode) 지정 `afxHTMLHelp`합니다.

- WinHelp 응용 프로그램의 도움말을 설정 하려면 호출 `SetHelpMode` 지정 `afxWinHelp`합니다.

##  <a name="m_hinstance"></a>  CWinApp::m_hInstance

에 해당 하는 *hInstance* 매개 변수를 Windows 전달한 `WinMain`합니다.

```
HINSTANCE m_hInstance;
```

### <a name="remarks"></a>설명

`m_hInstance` 데이터 멤버는 Windows에서 실행 중인 응용 프로그램의 현재 인스턴스에 대 한 핸들입니다. 전역 함수에 의해 반환 됩니다 [AfxGetInstanceHandle](application-information-and-management.md#afxgetinstancehandle)합니다. `m_hInstance` HINSTANCE 형식의 공용 변수가입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#55](../../mfc/reference/codesnippet/cpp/cwinapp-class_15.cpp)]

##  <a name="m_lpcmdline"></a>  CWinApp::m_lpCmdLine

에 해당 하는 *lpCmdLine* 매개 변수를 Windows 전달한 `WinMain`합니다.

```
LPTSTR m_lpCmdLine;
```

### <a name="remarks"></a>설명

응용 프로그램에 대 한 명령줄을 지정 하는 null로 끝나는 문자열을 가리킵니다. 사용 하 여 `m_lpCmdLine` 사용자가 응용 프로그램 시작 했을 때 입력 한 명령줄 인수를 액세스할 수 있습니다. `m_lpCmdLine` LPTSTR 형식의 공용 변수가입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#52](../../mfc/reference/codesnippet/cpp/cwinapp-class_16.cpp)]

##  <a name="m_nautosaveinterval"></a>  CWinApp::m_nAutosaveInterval

자동으로 저장 간격 (밀리초) 시간의 길이입니다.

```
int m_nAutosaveInterval;
```

### <a name="remarks"></a>설명

지정한 간격으로 자동 저장 열린 문서를 다시 시작 관리자를 구성할 수 있습니다. 응용 프로그램 자동 저장 파일이 아닌 경우이 매개 변수는 영향을 주지 않습니다.

##  <a name="m_ncmdshow"></a>  CWinApp::m_nCmdShow

에 해당 하는 *nCmdShow* 매개 변수를 Windows 전달한 `WinMain`합니다.

```
int m_nCmdShow;
```

### <a name="remarks"></a>설명

전달 해야 `m_nCmdShow` 호출할 때 인수로 [CWnd::ShowWindow](../../mfc/reference/cwnd-class.md#showwindow) 응용 프로그램의 주 창에 대 한 합니다. `m_nCmdShow` 형식의 공용 변수 **int**합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#56](../../mfc/reference/codesnippet/cpp/cwinapp-class_17.cpp)]

##  <a name="m_pactivewnd"></a>  CWinApp::m_pActiveWnd

이 데이터 멤버를 사용 하 여 프로그램 OLE 서버 응용 프로그램에서 현재 위치 활성화가 OLE 컨테이너 응용 프로그램의 주 창에 대 한 포인터를 저장 합니다.

### <a name="remarks"></a>설명

이 데이터 멤버가 NULL 인 경우 응용 프로그램이 내부 활성화 아닙니다.

프레임 창 OLE 컨테이너 응용 프로그램에 의해 활성화 될 때이 멤버 변수를 설정 하는 프레임 워크입니다.

##  <a name="m_pdatarecoveryhandler"></a>  CWinApp::m_pDataRecoveryHandler

응용 프로그램에 대 한 데이터 복구 처리기에 대 한 포인터입니다.

```
CDataRecoveryHandler* m_pDataRecoveryHandler;
```

### <a name="remarks"></a>설명

응용 프로그램의 데이터 복구 처리기 모니터링 열려 있는 문서와 자동으로 저장 합니다. 프레임 워크 예기치 않게 종료 되 면 응용 프로그램이 다시 시작 하는 경우 자동 저장 된 파일을 복원 하는 데이터 복구 처리기를 사용 합니다. 자세한 내용은 [CDataRecoveryHandler 클래스](../../mfc/reference/cdatarecoveryhandler-class.md)합니다.

##  <a name="m_pszappname"></a>  CWinApp::m_pszAppName

애플리케이션의 이름을 지정합니다.

```
LPCTSTR m_pszAppName;
```

### <a name="remarks"></a>설명

응용 프로그램 이름에 전달 된 매개 변수에서 가져올 수 있습니다는 [CWinApp](#cwinapp) 생성자를 지정 하지 않으면 AFX_IDS_APP_TITLE ID를 사용 하 여 리소스 문자열입니다. 리소스에서 응용 프로그램 이름이 없으면 프로그램에서 제공 됩니다. EXE 파일 이름입니다.

전역 함수에서 반환한 [AfxGetAppName](application-information-and-management.md#afxgetappname)합니다. `m_pszAppName` 형식의 공용 변수 **const char**<strong>\*</strong>합니다.

> [!NOTE]
> 값을 할당 하는 경우 `m_pszAppName`, 힙에 동적으로 할당 해야 합니다. 합니다 `CWinApp` 소멸자 호출 **무료**이 포인터를 사용 하 여 (). 사용 하려면 여러는 `_tcsdup`()에서 런타임 라이브러리 함수를 할당 합니다. 또한 새 값을 할당 하기 전에 현재 포인터를 사용 하 여 연결 된 메모리를 확보 합니다. 예를 들어 다음과 같습니다.

[!code-cpp[NVC_MFCWindowing#57](../../mfc/reference/codesnippet/cpp/cwinapp-class_18.cpp)]

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#65](../../mfc/reference/codesnippet/cpp/cwinapp-class_19.cpp)]

##  <a name="m_pszexename"></a>  CWinApp::m_pszExeName

확장명 없이 응용 프로그램의 실행 파일의 이름을 포함합니다.

```
LPCTSTR m_pszExeName;
```

### <a name="remarks"></a>설명

와 달리 [m_pszAppName](#m_pszappname),이 이름은 공백을 포함할 수 없습니다. `m_pszExeName` 형식의 공용 변수 **const char**<strong>\*</strong>합니다.

> [!NOTE]
> 값을 할당 하는 경우 `m_pszExeName`, 힙에 동적으로 할당 해야 합니다. 합니다 `CWinApp` 소멸자 호출 **무료**이 포인터를 사용 하 여 (). 사용 하려면 여러는 `_tcsdup`()에서 런타임 라이브러리 함수를 할당 합니다. 또한 새 값을 할당 하기 전에 현재 포인터를 사용 하 여 연결 된 메모리를 확보 합니다. 예를 들어 다음과 같습니다.

[!code-cpp[NVC_MFCWindowing#58](../../mfc/reference/codesnippet/cpp/cwinapp-class_20.cpp)]

##  <a name="m_pszhelpfilepath"></a>  CWinApp::m_pszHelpFilePath

응용 프로그램의 도움말 파일의 경로를 포함합니다.

```
LPCTSTR m_pszHelpFilePath;
```

### <a name="remarks"></a>설명

기본적으로 프레임 워크는 다음과 같이 초기화 됩니다. `m_pszHelpFilePath` 사용 하 여 응용 프로그램의 이름으로 ". HLP "추가 합니다. 도움말 파일의 이름을 변경 하려면 설정 `m_pszHelpFilePath` 원하는 도움말 파일의 전체 이름을 포함 하는 문자열을 가리키도록 합니다. 응용 프로그램에서은이 작업을 수행 하는 편리한 장소 [InitInstance](#initinstance) 함수입니다. `m_pszHelpFilePath` 형식의 공용 변수 **const char**<strong>\*</strong>합니다.

> [!NOTE]
> 값을 할당 하는 경우 `m_pszHelpFilePath`, 힙에 동적으로 할당 해야 합니다. 합니다 `CWinApp` 소멸자 호출 **무료**이 포인터를 사용 하 여 (). 사용 하려면 여러는 `_tcsdup`()에서 런타임 라이브러리 함수를 할당 합니다. 또한 새 값을 할당 하기 전에 현재 포인터를 사용 하 여 연결 된 메모리를 확보 합니다. 예를 들어 다음과 같습니다.

[!code-cpp[NVC_MFCWindowing#59](../../mfc/reference/codesnippet/cpp/cwinapp-class_21.cpp)]

##  <a name="m_pszprofilename"></a>  CWinApp::m_pszProfileName

응용 프로그램의 이름을 포함합니다. INI 파일입니다.

```
LPCTSTR m_pszProfileName;
```

### <a name="remarks"></a>설명

`m_pszProfileName` 형식의 공용 변수 **const char**<strong>\*</strong>합니다.

> [!NOTE]
> 값을 할당 하는 경우 `m_pszProfileName`, 힙에 동적으로 할당 해야 합니다. 합니다 `CWinApp` 소멸자 호출 **무료**이 포인터를 사용 하 여 (). 사용 하려면 여러는 `_tcsdup`()에서 런타임 라이브러리 함수를 할당 합니다. 또한 새 값을 할당 하기 전에 현재 포인터를 사용 하 여 연결 된 메모리를 확보 합니다. 예를 들어 다음과 같습니다.

[!code-cpp[NVC_MFCWindowing#60](../../mfc/reference/codesnippet/cpp/cwinapp-class_22.cpp)]

##  <a name="m_pszregistrykey"></a>  CWinApp::m_pszRegistryKey

여기서 레지스트리 또는 INI 파일에서 응용 프로그램 프로필 설정 저장 되는 결정 하는 데 사용 합니다.

```
LPCTSTR m_pszRegistryKey;
```

### <a name="remarks"></a>설명

일반적으로이 데이터 멤버는 읽기 전용으로 처리 됩니다.

- 값은 레지스트리 키에 저장 됩니다. 응용 프로그램 프로필 설정에 대 한 이름은 다음 레지스트리 키에 추가 됩니다. HKEY_CURRENT_USER/Software/LocalAppWizard-Generated/.

값을 할당 하는 경우 `m_pszRegistryKey`, 힙에 동적으로 할당 해야 합니다. 합니다 `CWinApp` 소멸자 호출 **무료**이 포인터를 사용 하 여 (). 사용 하려면 여러는 `_tcsdup`()에서 런타임 라이브러리 함수를 할당 합니다. 또한 새 값을 할당 하기 전에 현재 포인터를 사용 하 여 연결 된 메모리를 확보 합니다. 예를 들어 다음과 같습니다.

[!code-cpp[NVC_MFCWindowing#61](../../mfc/reference/codesnippet/cpp/cwinapp-class_23.cpp)]

##  <a name="m_pszappid"></a>  CWinApp::m_pszAppID

응용 프로그램 사용자 모델 id입니다.

```
LPCTSTR m_pszAppID;
```

### <a name="remarks"></a>설명

##  <a name="oncontexthelp"></a>  CWinApp::OnContextHelp

응용 프로그램 내에서 SHIFT + F1 도움말을 처리합니다.

```
afx_msg void OnContextHelp();
```

### <a name="remarks"></a>설명

추가 해야 합니다는 `ON_COMMAND( ID_CONTEXT_HELP, OnContextHelp )` 문을 프로그램 `CWinApp` 메시지 맵 클래스 및 일반적으로 SHIFT + f1 키를이 멤버 함수를 사용 하도록 설정 하는 액셀러레이터 키 테이블 항목을 추가할 수도 있습니다.

`OnContextHelp` 도움말 모드로 응용 프로그램을 배치합니다. 그런 다음 커서로 변경 되는 화살표와 물음표를 및 사용자 마우스 포인터를 이동 하 고 대화 상자, 창, 메뉴 또는 명령 단추를 선택 합니다. 마우스 왼쪽된 단추를 눌러 수 있습니다. 이 멤버 함수는 커서 아래에 있는 개체의 도움말 컨텍스트를 검색 하 고 Windows가 해당 도움말 컨텍스트를 사용 하 여 WinHelp 함수를 호출 합니다.

##  <a name="onddecommand"></a>  CWinApp::OnDDECommand

주 프레임 창 DDE를 받을 때 프레임 워크에서 호출 메시지를 실행 합니다.

```
virtual BOOL OnDDECommand(LPTSTR lpszCommand);
```

### <a name="parameters"></a>매개 변수

*lpszCommand*<br/>
응용 프로그램이 수신한 DDE 명령 문자열을 가리킵니다.

### <a name="return-value"></a>반환 값

0이 아닌 명령 처리 됩니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

기본 구현 여부를 명령 인지 확인 문서 열기 요청을, 그렇다면 지정 된 문서를 엽니다. 일반적으로 Windows 파일 관리자 데이터 파일을 두 번 클릭할 때 이러한 DDE 명령 문자열을 보냅니다. 재정의 다른 DDE 처리 하려면이 함수를 인쇄 하는 명령 같은 명령을 실행 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#48](../../mfc/reference/codesnippet/cpp/cwinapp-class_24.cpp)]

##  <a name="onfilenew"></a>  CWinApp::OnFileNew

ID_FILE_NEW 명령을 구현합니다.

```
afx_msg void OnFileNew();
```

### <a name="remarks"></a>설명

추가 해야 합니다는 `ON_COMMAND( ID_FILE_NEW, OnFileNew )` 문을 여 `CWinApp` 이 멤버 함수를 사용 하도록 설정 하는 클래스 메시지 맵. 사용 하도록 설정 하는 경우이 함수는 새 파일 명령 실행을 처리 합니다.

참조 [Technical Note 22](../../mfc/tn022-standard-commands-implementation.md) 기본 동작과이 멤버 함수를 재정의 하는 방법에 대 한 자세한 내용은 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]

[!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]

##  <a name="onfileopen"></a>  CWinApp::OnFileOpen

ID_FILE_OPEN 명령을 구현합니다.

```
afx_msg void OnFileOpen();
```

### <a name="remarks"></a>설명

추가 해야 합니다는 `ON_COMMAND( ID_FILE_OPEN, OnFileOpen )` 문을 여 `CWinApp` 이 멤버 함수를 사용 하도록 설정 하는 클래스 메시지 맵. 사용 하도록 설정 하는 경우이 함수는 파일 열기 명령 실행을 처리 합니다.

기본 동작에 대 한 내용은이 멤버 함수를 재정의 하는 방법에 대 한 지침을 참조 하세요 [Technical Note 22](../../mfc/tn022-standard-commands-implementation.md)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]

[!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]

##  <a name="onfileprintsetup"></a>  CWinApp::OnFilePrintSetup

ID_FILE_PRINT_SETUP 명령을 구현합니다.

```
afx_msg void OnFilePrintSetup();
```

### <a name="remarks"></a>설명

추가 해야 합니다는 `ON_COMMAND( ID_FILE_PRINT_SETUP, OnFilePrintSetup )` 문을 여 `CWinApp` 이 멤버 함수를 사용 하도록 설정 하는 클래스 메시지 맵. 사용 하도록 설정 하는 경우이 함수는 파일 인쇄 명령 실행을 처리 합니다.

기본 동작에 대 한 내용은이 멤버 함수를 재정의 하는 방법에 대 한 지침을 참조 하세요 [Technical Note 22](../../mfc/tn022-standard-commands-implementation.md)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]

[!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]

##  <a name="onhelp"></a>  CWinApp::OnHelp

현재 컨텍스트를 사용하여 응용 프로그램 내에서 F1 도움말을 처리합니다.

```
afx_msg void OnHelp();
```

### <a name="remarks"></a>설명

일반적으로 F1 키에 대 한 바로 가기 키 항목이 추가 합니다. F1 키를 사용 하도록 설정 하는 것은 요구 사항이 아니라 규칙이 합니다.

추가 해야 합니다는 `ON_COMMAND( ID_HELP, OnHelp )` 문을 여 `CWinApp` 이 멤버 함수를 사용 하도록 설정 하는 클래스 메시지 맵. 사용 하도록 설정 하는 경우 사용자가 F1 키를 누를 때 프레임 워크에서 호출 합니다.

이 메시지 처리기 함수의 기본 구현은 현재 창, 대화 상자 또는 메뉴 항목에 해당 하며 다음 WINHELP를 호출 하는 도움말 컨텍스트를 결정 합니다. EXE 수 있습니다. 컨텍스트가 없습니다. 현재 사용 가능한 경우 함수는 기본 컨텍스트를 사용 합니다.

창, 대화 상자, 메뉴 항목 또는 현재 포커스가 있는 도구 모음 단추 이외의 값으로 도움말 컨텍스트를 설정 하려면이 멤버 함수를 재정의 합니다. 호출 `WinHelp` 원하는 도움말 컨텍스트 id입니다.

##  <a name="onhelpfinder"></a>  CWinApp::OnHelpFinder

ID_HELP_FINDER 및 ID_DEFAULT_HELP 명령 처리합니다.

```
afx_msg void OnHelpFinder();
```

### <a name="remarks"></a>설명

추가 해야 합니다는 `ON_COMMAND( ID_HELP_FINDER, OnHelpFinder )` 문을 여 `CWinApp` 이 멤버 함수를 사용 하도록 설정 하는 클래스 메시지 맵. 응용 프로그램의 사용자가 호출할 도움말 찾기 명령을 선택 하면 프레임 워크가이 메시지 처리기 함수를 호출을 사용 하는 경우 `WinHelp` 표준을 **HELP_FINDER** 항목입니다.

##  <a name="onhelpindex"></a>  CWinApp::OnHelpIndex

ID_HELP_INDEX 명령을 처리 하 고 기본 도움말 항목을 제공 합니다.

```
afx_msg void OnHelpIndex();
```

### <a name="remarks"></a>설명

추가 해야 합니다는 `ON_COMMAND( ID_HELP_INDEX, OnHelpIndex )` 문을 여 `CWinApp` 이 멤버 함수를 사용 하도록 설정 하는 클래스 메시지 맵. 응용 프로그램의 사용자가 호출할 도움말 색인 명령을 선택 하면 프레임 워크가이 메시지 처리기 함수를 호출을 사용 하는 경우 `WinHelp` 표준을 **HELP_INDEX** 항목입니다.

##  <a name="onhelpusing"></a>  CWinApp::OnHelpUsing

ID_HELP_USING 명령을 처리합니다.

```
afx_msg void OnHelpUsing();
```

### <a name="remarks"></a>설명

추가 해야 합니다는 `ON_COMMAND( ID_HELP_USING, OnHelpUsing )` 문을 여 `CWinApp` 이 멤버 함수를 사용 하도록 설정 하는 클래스 메시지 맵. 응용 프로그램의 호출을 사용 하 여 도움말 명령을 선택 하면 프레임 워크가이 메시지 처리기 함수를 호출 합니다 `WinHelp` 표준 응용 프로그램 **HELP_HELPONHELP** 항목입니다.

##  <a name="onidle"></a>  CWinApp::OnIdle

유휴 시간 처리를 수행 하려면이 멤버 함수를 재정의 합니다.

```
virtual BOOL OnIdle(LONG lCount);
```

### <a name="parameters"></a>매개 변수

*lCount*<br/>
카운터를 증가 될 때마다 `OnIdle` 응용 프로그램의 메시지 큐가 비어 있을 때 호출 됩니다. 이 횟수가 새 메시지가 처리 될 때마다 0으로 재설정 됩니다. 사용할 수는 *lCount* 매개 변수를 응용 프로그램 연결이 유휴 상태 메시지를 처리 하지 않고 상대적 기간을 확인 합니다.

### <a name="return-value"></a>반환 값

유휴 처리 시간이; 받으려면 0이 아닌 값 더 이상 유휴 시간이 필요 하는 경우 0입니다.

### <a name="remarks"></a>설명

`OnIdle` 응용 프로그램의 메시지 큐가 비어 있을 때 기본 메시지 루프에서 호출 됩니다. 고유한 백그라운드 유휴 처리기 작업을 호출 하려면 재정의 사용 합니다.

`OnIdle` 유휴 처리 시간이 필요한 임을 나타내려면 0을 반환 해야 합니다. 합니다 *lCount* 매개 변수 될 때마다 증가 `OnIdle` 메시지 큐가 비어 있으며 0으로 다시 설정 될 때마다 새 메시지를 처리할 때 호출 됩니다. 이 수에 따라 다른 유휴 루틴을 호출할 수 있습니다.

유휴 루프 처리를 요약는 다음과 같습니다.

1. Microsoft Foundation Class 라이브러리의 메시지 루프 메시지 큐를 검사 하 고 이상 보류 중인 메시지를 발견 하는 경우 호출 `OnIdle` 응용 프로그램 개체 및 0으로 제공 합니다 *lCount* 인수입니다.

2. `OnIdle` 일부 처리를 수행 하 고 것을 나타내기 위해 0 이외의 값을 위해 다시 호출 해야 반환 추가로 처리 합니다.

3. 메시지 루프 메시지 큐를 다시 확인합니다. 보류 중인 메시지가 없을 경우 호출한 `OnIdle` 다시 증가 합니다 *lCount* 인수입니다.

4. 결국 `OnIdle` 모든 유휴 작업 처리를 완료 하 고 0을 반환 합니다. 이렇게 하면 호출을 중지 하려면 메시지 루프 `OnIdle` 다음 메시지를 메시지 큐에서 받을 때까지 시점에서 유휴 주기를 다시 시작을 0으로 설정 하는 인수를 사용 하 여 합니다.

중에 시간이 오래 걸리는 작업을 수행 하지 않습니다 `OnIdle` 응용 프로그램까지 사용자 입력을 처리할 수 없습니다 때문에 `OnIdle` 반환 합니다.

> [!NOTE]
> 기본 구현을 `OnIdle` 업데이트 명령 메뉴 항목 및 도구 모음 단추와 같은 사용자 인터페이스 개체 및 내부 데이터 구조 정리를 수행 합니다. 따라서 재정의 하는 경우 `OnIdle`를 호출 해야 합니다 `CWinApp::OnIdle` 사용 하 여는 `lCount` 재정의 된 버전에서 합니다. 모든 기본 클래스 유휴 프로세스를 먼저 호출 (즉, 기본 클래스까지 `OnIdle` 0을 반환 합니다). 기본 클래스 처리 완료 되기 전에 작업을 수행 해야 할 경우 적절 한 선택 하는 기본 클래스 구현을 검토 *lCount* 작업을 수행 하는 중입니다.

원하지 않는 경우 `OnIdle` 재정의할 수 있습니다 메시지 큐에서 메시지를 검색할 때마다 호출 되도록 하는 [CWinThreadIsIdleMessage](../../mfc/reference/cwinthread-class.md#isidlemessage)합니다. 응용 프로그램에는 매우 간단한 타이머를 설정한 경우 또는 시스템 다음 WM_SYSTIMER 메시지를 보내는 경우 `OnIdle` 반복적으로 호출 되며 성능이 저하 됩니다.

### <a name="example"></a>예제

다음 두 예제에 사용 하는 방법을 보여 줍니다 `OnIdle`합니다. 사용 하 여 두 개의 유휴 작업을 처리 하는 첫 번째 예제는 *lCount* 인수 작업 우선 순위를 지정 합니다. 첫 번째 작업은 매우 중요 하 고 가능 하면 수행 해야 합니다. 두 번째 작업은 그 보다 중요 및 사용자 입력에 오랫동안 일시 중지 하는 경우에 수행 해야 합니다. 호출의 기본 클래스 버전을 `OnIdle`입니다. 두 번째 예제는 다른 우선 순위를 사용 하 여 유휴 작업 그룹을 관리합니다.

[!code-cpp[NVC_MFCWindowing#51](../../mfc/reference/codesnippet/cpp/cwinapp-class_27.cpp)]

##  <a name="opendocumentfile"></a>  CWinApp::OpenDocumentFile

명명 된 열에이 메서드를 호출 하는 프레임 워크 [CDocument](../../mfc/reference/cdocument-class.md) 응용 프로그램에 대 한 파일입니다.

```
virtual CDocument* OpenDocumentFile(
    LPCTSTR lpszFileName
    BOOL bAddToMRU = TRUE);
```

### <a name="parameters"></a>매개 변수

*lpszFileName*<br/>
[in] 열려는 파일의 이름입니다.

*bAddToMRU*<br/>
[in] TRUE 이면 문서를 사용 하면 가장 최근의 파일 중 하나인 FALSE 문서가 아닌 최신 파일 중 하나를 나타냅니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 `CDocument` 성공 하면 NULL입니다.

### <a name="remarks"></a>설명

해당 이름의 문서가 이미 열려 있으면 해당 문서를 포함 하는 첫 번째 프레임 창에 포커스를 받게 됩니다. 응용 프로그램에서 여러 문서 서식 파일을 지 원하는 경우 프레임 워크 파일 이름 확장명을 사용 하 여 문서를 로드 하려고 적절 한 문서 템플릿을 찾습니다. 성공 하면 프레임 창 및 문서에 대 한 보기를가 다음 문서 서식 파일에 만듭니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#52](../../mfc/reference/codesnippet/cpp/cwinapp-class_16.cpp)]

##  <a name="parsecommandline"></a>  CWinApp::ParseCommandLine

명령줄을 구문 분석 하 고 한 번에 하나씩 매개 변수를 보낼이 멤버 함수 호출 [CCommandLineInfo::ParseParam](../../mfc/reference/ccommandlineinfo-class.md#parseparam)합니다.

```
void ParseCommandLine(CCommandLineInfo& rCmdInfo);
```

### <a name="parameters"></a>매개 변수

*rCmdInfo*<br/>
에 대 한 참조를 [CCommandLineInfo](../../mfc/reference/ccommandlineinfo-class.md) 개체입니다.

### <a name="remarks"></a>설명

응용 프로그램 마법사를 사용 하 여 새 MFC 프로젝트를 시작 하면 응용 프로그램 마법사가의 로컬 인스턴스를 만듭니다 `CCommandLineInfo`, 다음 호출 `ProcessShellCommand` 및 `ParseCommandLine` 에 [InitInstance](#initinstance) 멤버 함수입니다. 명령 줄 아래에 설명 된 경로 다음과 같습니다.

1. 생성 한 후 `InitInstance`서 `CCommandLineInfo` 개체를 전달 `ParseCommandLine`합니다.

2. `ParseCommandLine` 그런 다음 호출 `CCommandLineInfo::ParseParam` 반복적으로 각 매개 변수에 대해 한 번입니다.

3. `ParseParam` 채웁니다 합니다 `CCommandLineInfo` 에 전달 되는 개체 [ProcessShellCommand](#processshellcommand)합니다.

4. `ProcessShellCommand` 명령줄 인수 및 플래그를 처리합니다.

호출할 수 있는 참고 `ParseCommandLine` 필요에 따라 직접.

명령줄 플래그에 대 한 참조 [CCommandLineInfo::m_nShellCommand](../../mfc/reference/ccommandlineinfo-class.md#m_nshellcommand)합니다.

##  <a name="pretranslatemessage"></a>  CWinApp::PreTranslateMessage

창 메시지를 필터링 하려면이 함수를 재정의 하 여 Windows 함수로 디스패치 되기 전에 [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) 하 고 [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) 액셀러레이터 키를 수행 하는 기본 구현 호출 해야 하므로 변환 된 `CWinApp::PreTranslateMessage` 재정의 된 버전에서 멤버 함수입니다.

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>매개 변수

*pMsg*<br/>
에 대 한 포인터를 [MSG](/windows/desktop/api/winuser/ns-winuser-tagmsg) 처리할 메시지를 포함 하는 구조입니다.

### <a name="return-value"></a>반환 값

메시지에서 완전히 처리 된 경우 0이 아닌 `PreTranslateMessage` 하며 추가로 처리할 수 없습니다. 일반적인 방법으로 메시지를 처리 해야 하면 0입니다.

##  <a name="processmessagefilter"></a>  CWinApp::ProcessMessageFilter

프레임 워크의 후크 함수는 필터링 하 고 특정 Windows 메시지에 응답 하려면이 멤버 함수를 호출 합니다.

```
virtual BOOL ProcessMessageFilter(
    int code,
    LPMSG lpMsg);
```

### <a name="parameters"></a>매개 변수

*코드*<br/>
후크 코드를 지정합니다. 이 멤버 함수는 코드를 사용 하 여 처리 하는 방법을 결정 *lpMsg 합니다.*

*lpMsg*<br/>
Windows에 대 한 포인터 [MSG](/windows/desktop/api/winuser/ns-winuser-tagmsg) 구조입니다.

### <a name="return-value"></a>반환 값

0이 아닌 메시지를 처리 합니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

응용 프로그램의 일반 메시지를 보내기 전에 이벤트를 처리 하는 후크 함수를 처리 합니다.

이 고급 기능을 재정의 하는 경우 사용할 프레임 워크의 유지 관리 하는 기본 클래스 버전을 호출 해야 처리를 연결 합니다.

##  <a name="processshellcommand"></a>  CWinApp::ProcessShellCommand

이 멤버 함수 호출 됩니다 [InitInstance](#initinstance) 에서 전달 된 매개 변수를 수락 합니다 `CCommandLineInfo` 식별 되는 개체 *rCmdInfo*, 표시 된 후 작업을 수행 합니다.

```
BOOL ProcessShellCommand(CCommandLineInfo& rCmdInfo);
```

### <a name="parameters"></a>매개 변수

*rCmdInfo*<br/>
에 대 한 참조를 [CCommandLineInfo](../../mfc/reference/ccommandlineinfo-class.md) 개체입니다.

### <a name="return-value"></a>반환 값

셸 명령을 성공적으로 처리 하는 경우에 0이 아닙니다. 0에서 FALSE를 반환 하는 경우 [InitInstance](#initinstance)합니다.

### <a name="remarks"></a>설명

응용 프로그램 마법사를 사용 하 여 새 MFC 프로젝트를 시작 하면 응용 프로그램 마법사가의 로컬 인스턴스를 만듭니다 `CCommandLineInfo`, 호출 `ProcessShellCommand` 하 고 [ParseCommandLine](#parsecommandline) 에서 `InitInstance` 멤버 함수입니다. 명령 줄 아래에 설명 된 경로 다음과 같습니다.

1. 생성 한 후 `InitInstance`서 `CCommandLineInfo` 개체를 전달 `ParseCommandLine`합니다.

2. `ParseCommandLine` 그런 다음 호출 [CCommandLineInfo::ParseParam](../../mfc/reference/ccommandlineinfo-class.md#parseparam) 반복적으로 각 매개 변수에 대해 한 번입니다.

3. `ParseParam` 채웁니다 합니다 `CCommandLineInfo` 개체에 전달 되는 `ProcessShellCommand`합니다.

4. `ProcessShellCommand` 명령줄 인수 및 플래그를 처리합니다.

데이터 멤버를 `CCommandLineInfo` 로 식별 된 개체 [CCommandLineInfo::m_nShellCommand](../../mfc/reference/ccommandlineinfo-class.md#m_nshellcommand), 내에 정의 된 열거 형식에 `CCommandLineInfo` 클래스.

```
enum {
    FileNew,
    FileOpen,
    FilePrint,
    FilePrintTo,
    FileDDE
    };
```

이러한 각 값의 간략 한 설명을 참조 하세요. `CCommandLineInfo::m_nShellCommand`합니다.

##  <a name="processwndprocexception"></a>  CWinApp::ProcessWndProcException

처리기는 응용 프로그램의 메시지 또는 명령 처리기 중 하나에서 throw 된 예외를 catch 하지 않습니다 될 때마다이 멤버 함수를 호출 하는 프레임 워크입니다.

```
virtual LRESULT ProcessWndProcException(
    CException* e,
    const MSG* pMsg);
```

### <a name="parameters"></a>매개 변수

*e*<br/>
예외로 포인터입니다.

*pMsg*<br/>
A [MSG](/windows/desktop/api/winuser/ns-winuser-tagmsg) 예외를 throw 하기 위해 프레임 워크를 발생 시킨 windows 메시지에 대 한 정보를 포함 하는 구조입니다.

### <a name="return-value"></a>반환 값

Windows에 반환 되어야 하는 값입니다. 일반적으로이 0l windows 메시지의 경우 1 L (TRUE) 명령 메시지입니다.

### <a name="remarks"></a>설명

이 멤버 함수를 직접 호출 하지 마세요.

이 멤버 함수의 기본 구현은 메시지 상자를 만듭니다. 메시지 상자는 "명령이 실패 했습니다." 메시지가 표시 메뉴, 도구 모음 또는 액셀러레이터 키 명령 실패를 사용 하 여 확인할 수 없는 예외가 발생 하는 경우 그렇지 않으면 "내부 응용 프로그램 오류" 메시지가 표시 됩니다.

전역 예외 처리를 제공 하려면이 멤버 함수를 재정의 합니다. 메시지 상자를 표시 하려는 경우에 기본 기능을 호출 합니다.

##  <a name="register"></a>  CWinApp::Register

처리 되지 않은 모든 등록 작업을 수행 `RegisterShellFileTypes`합니다.

```
virtual BOOL Register();
```

### <a name="return-value"></a>반환 값

성공하면 0이 아닌 값이고, 실패하면 0입니다.

### <a name="remarks"></a>설명

기본 구현은 단순히 TRUE를 반환합니다. 모든 사용자 지정된 등록 단계를 제공 하려면이 함수를 재정의 합니다.

##  <a name="registershellfiletypes"></a>  CWinApp::RegisterShellFileTypes

모든 응용 프로그램의 문서 유형에 Windows 파일 관리자에 등록 하려면이 멤버 함수를 호출 합니다.

```
void RegisterShellFileTypes(BOOL bCompat = FALSE);
```

### <a name="parameters"></a>매개 변수

*bCompat*<br/>
[in] TRUE는 인쇄 및 인쇄에 파일을 인쇄 하려면 셸에서 직접 파일을 끌거나 프린터 개체를 사용자가 셸 명령에 대 한 등록 항목을 추가 합니다. 또한 DefaultIcon 키 추가. 기본적으로이 매개 변수는 FALSE는 이전 버전과 호환성에 대 한 합니다.

### <a name="remarks"></a>설명

이 파일 관리자 내에서 두 번 클릭 하 여 응용 프로그램에서 만든 데이터 파일을 열 수 있습니다. 호출 `RegisterShellFileTypes` 호출한 후 [AddDocTemplate](#adddoctemplate) 각 응용 프로그램에서 문서 서식 파일에 대 한 합니다. 호출 된 [EnableShellOpen](#enableshellopen) 멤버 함수를 호출할 때 `RegisterShellFileTypes`합니다.

`RegisterShellFileTypes` 목록 반복 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) 개체는 응용 프로그램 유지 관리 하 고, 각 문서 서식 파일에 대 한 Windows 파일 연결에 대 한 유지 관리 하는 등록 데이터베이스에 항목을 추가 합니다. 파일 관리자 이러한 항목을 사용 하 여 사용자가 해당 데이터 파일을 엽니다. 전달할 필요가이 합니다. 응용 프로그램을 사용 하 여 레지스트리 파일입니다.

> [!NOTE]
> `RegisterShellFileTypes` 사용자는 관리자 권한으로 프로그램을 실행 하는 경우에 작동 합니다. 프로그램에 대 한 관리자 권한이 없는 경우 레지스트리 키를 변경할 수 없습니다 것입니다.

등록 데이터베이스는 이미 다른 파일 형식을 사용 하 여 지정 된 파일 확장명을 연결 하면 새 의도가 없으며 만들어집니다. 참조 된 `CDocTemplate` 이 정보를 등록 하는 데 필요한 문자열의 형식에 대 한 클래스입니다.

##  <a name="registerwithrestartmanager"></a>  CWinApp::RegisterWithRestartManager

다시 시작 관리자를 사용 하 여 응용 프로그램을 등록 합니다.

```
virtual HRESULT RegisterWithRestartManager(
    BOOL bRegisterRecoveryCallback,
    const CString& strRestartIdentifier);

virtual HRESULT RegisterWithRestartManager(
    LPCWSTR pwzCommandLineArgs,
    DWORD dwRestartFlags,
    APPLICATION_RECOVERY_CALLBACK pRecoveryCallback,
    LPVOID lpvParam,
    DWORD dwPingInterval,
    DWORD dwCallbackFlags);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|설명|
|*bRegisterRecoveryCallback*|[in] TRUE 이면 응용 프로그램의이 인스턴스는 복구 콜백 함수입니다. FALSE 되지 않은 것을 나타냅니다. 프레임 워크는 응용 프로그램이 예기치 않게 종료 될 때 복구 콜백 함수를 호출 합니다. 자세한 내용은 [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)합니다.|
|*strRestartIdentifier*|[in] 다시 시작 관리자의이 인스턴스를 식별 하는 고유 문자열입니다. 다시 시작 관리자 식별자는 응용 프로그램의 각 인스턴스에 대해 고유 합니다.|
|*pwzCommandLineArgs*|[in] 명령줄에서 추가 인수를 포함 하는 문자열입니다.|
|*dwRestartFlags*|[in] 다시 시작 관리자에 대 한 선택적 플래그입니다. 자세한 내용은 설명 섹션을 참조하세요.|
|*pRecoveryCallback*|[in] 복구 콜백 함수입니다. 이 함수는 입력으로 LPVOID 매개 변수를 사용 하 고 DWORD를 반환 해야 합니다. 기본 복구 콜백 함수는 `CWinApp::ApplicationRecoveryCallback`합니다.|
|*lpvParam*|[in] 복구 콜백 함수에 대 한 입력된 매개 변수입니다. 자세한 내용은 [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)합니다.|
|*dwPingInterval*|[in] 다시 시작 관리자를 반환 하는 복구 콜백 함수에 대 한 대기 하는 시간의 길이입니다. 이 매개 변수는 밀리초에서입니다.|
|*dwCallbackFlags*|[in] 플래그 복구 콜백 함수에 전달 합니다. 나중에 사용하기 위해 예약되어 있습니다.|

### <a name="return-value"></a>반환 값

메서드가 성공 하면 s_ok이 고 그렇지 않으면 오류 코드입니다.

### <a name="remarks"></a>설명

간단한 버전의 응용 프로그램에서는 자동 저장 파일 기본 MFC 구현 하는 경우 사용할지 `RegisterWithRestartManager`합니다. 복잡 한 버전을 사용 하 여 `RegisterWithRestartManager` 응용 프로그램의 자동 동작을 사용자 지정 하려는 경우.

빈 문자열을 사용 하 여이 메서드를 호출 하는 경우 *strRestartIdentifier*, `RegisterWithRestartManager` 관리자 다시 시작이이 인스턴스에 대 한 고유 식별자 문자열을 만듭니다.

응용 프로그램이 예기치 않게 종료 되 면 다시 시작 관리자 명령줄에서 응용 프로그램을 다시 시작 하 고 고유 식별자는 선택적 인수를 다시 시작을 제공 합니다. 이 시나리오에서는 프레임 워크는 다음과 같이 호출 됩니다. `RegisterWithRestartManager` 두 배입니다. 첫 번째 호출에서 가져온 [CWinApp::InitInstance](#initinstance) 문자열 식별자에 대 한 빈 문자열을 사용 하 여 합니다. 메서드를 차례로 [CWinApp::ProcessShellCommand](#processshellcommand) 호출 `RegisterWithRestartManager` 다시 시작 고유 식별자를 사용 합니다.

다시 시작 관리자를 사용 하 여 응용 프로그램을 등록 한 후 다시 시작 관리자는 응용 프로그램을 모니터링 합니다. 응용 프로그램이 예기치 않게 종료 되 면 다시 시작 관리자 종료 프로세스 중 복구 콜백 함수를 호출 합니다. 다시 시작 관리자 대기 합니다 *dwPingInterval* 복구 콜백 함수에서 응답할 수 있도록 합니다. 이 시간 안에 응답 하지 않으면 복구 콜백 함수를 하는 경우 응용 프로그램 복구 콜백 함수를 실행 하지 않고 종료 됩니다.

기본적으로 dwRestartFlags는 지원 되지 않습니다 하지만 나중에 사용할에 제공 됩니다. 가능한 값에 대 한 *dwRestartFlags* 는 다음과 같습니다.

- RESTART_NO_CRASH

- RESTART_NO_HANG

- RESTART_NO_PATCH

- RESTART_NO_REBOOT

##  <a name="reopenpreviousfilesatrestart"></a>  CWinApp::ReopenPreviousFilesAtRestart

다시 시작 관리자가 응용 프로그램이 예기치 않게 종료 될 때 열려 있던 파일이 있는지 여부를 결정 합니다.

```
virtual BOOL ReopenPreviousFilesAtRestart() const;
```

### <a name="return-value"></a>반환 값

TRUE 이면 다시 시작 관리자가 이전에 열려 있는 파일입니다. FALSE 이면 다시 시작 관리자 하지 않습니다.

##  <a name="restartinstance"></a>  CWinApp::RestartInstance

다시 시작 관리자에서 시작 된 응용 프로그램이 다시 시작을 처리 합니다.

```
virtual BOOL CWinApp::RestartInstance();
```

### <a name="return-value"></a>반환 값

데이터 복구 처리기 열리면 이전에 열린 문서; TRUE 데이터 복구 처리기에 오류가 발생 하는 경우 또는 이전에 열린 문서가 없는 경우 FALSE입니다.

### <a name="remarks"></a>설명

다시 시작 관리자에서 응용 프로그램을 다시 시작할 때 프레임 워크는이 메서드를 호출 합니다. 이 메서드는 데이터 복구 처리기를 검색 하 고 자동 저장 된 파일을 복원 합니다. 이 메서드를 호출 [CDataRecoveryHandler::RestoreAutosavedDocuments](../../mfc/reference/cdatarecoveryhandler-class.md#restoreautosaveddocuments) 자동 저장 된 파일을 복원 하는 사용자가 있는지 여부를 확인 하려면.

이 메서드가 FALSE를 반환 하는 경우는 [CDataRecoveryHandler](../../mfc/reference/cdatarecoveryhandler-class.md) 열려 있는 문서 되었는지 확인 합니다. 열린 문서에 없는 경우 응용 프로그램이 일반적으로 시작 합니다.

##  <a name="restoreautosavedfilesatrestart"></a>  CWinApp::RestoreAutosavedFilesAtRestart

응용 프로그램을 다시 시작 될 때 다시 시작 관리자 자동 저장 된 파일을 복원할지 여부를 결정 합니다.

```
virtual BOOL RestoreAutosavedFilesAtRestart() const;
```

### <a name="return-value"></a>반환 값

TRUE 이면 자동 저장 된 파일을 복원 하는 다시 시작 관리자 FALSE 이면 다시 시작 관리자 하지 않습니다.

##  <a name="run"></a>  CWinApp::Run

기본 메시지 루프를 제공합니다.

```
virtual int Run();
```

### <a name="return-value"></a>반환 값

**int** 반환한 값 `WinMain`합니다.

### <a name="remarks"></a>설명

`Run` 획득 하 고 응용 프로그램 WM_QUIT 메시지를 받을 때까지 Windows 메시지를 디스패치합니다. 응용 프로그램의 메시지 큐에 현재 없는 메시지를 포함 하는 경우 `Run` 호출 [OnIdle](#onidle) 유휴 시간 처리를 수행 합니다. 들어오는 메시지를 [PreTranslateMessage](#pretranslatemessage) 특수 한 처리 한 다음 Windows 함수에 멤버 함수 `TranslateMessage` 표준 키보드 변환;에 대 한 마지막으로 `DispatchMessage` Windows 함수를 호출 합니다.

`Run` 대부분 재정의 하지만 특수 동작을 제공 하도록 재정의할 수 있습니다.

##  <a name="runautomated"></a>  CWinApp::RunAutomated

확인 하려면이 함수를 호출 하는지 여부를 " **/Automation**"또는" **-Automation**" 옵션이 있는 서버 응용 프로그램이 클라이언트 응용 프로그램에서 시작 하는지 여부를 나타냅니다.

```
BOOL RunAutomated();
```

### <a name="return-value"></a>반환 값

옵션을 발견 하는 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

있는 경우 옵션은 명령줄에서 제거 됩니다. OLE Automation에 대 한 자세한 내용은 문서 참조 [자동화 서버](../../mfc/automation-servers.md)합니다.

##  <a name="runembedded"></a>  CWinApp::RunEmbedded

확인 하려면이 함수를 호출 하는지 여부를 " **포함/**"또는" **-포함**" 옵션이 있는 서버 응용 프로그램이 클라이언트 응용 프로그램에서 시작 하는지 여부를 나타냅니다.

```
BOOL RunEmbedded();
```

### <a name="return-value"></a>반환 값

옵션을 발견 하는 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

있는 경우 옵션은 명령줄에서 제거 됩니다. 포함에 대 한 자세한 내용은 문서를 참조 하세요. [서버: 서버 구현](../../mfc/servers-implementing-a-server.md)합니다.

##  <a name="saveallmodified"></a>  CWinApp::SaveAllModified

응용 프로그램의 주 프레임 창을 닫을 때 모든 문서를 저장 하기 위해 프레임 워크 또는 WM_QUERYENDSESSION 메시지를 통해 호출 됩니다.

```
virtual BOOL SaveAllModified();
```

### <a name="return-value"></a>반환 값

안전한 응용 프로그램을 종료 하면 0이 아니고 응용 프로그램을 종료 하는 안전 하지 않은 경우 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수의 기본 구현을 호출 합니다 [CDocument::SaveModified](../../mfc/reference/cdocument-class.md#savemodified) 멤버 함수는 응용 프로그램 내의 모든 수정 된 문서입니다.

##  <a name="selectprinter"></a>  CWinApp::SelectPrinter

특정 프린터를 선택 하려면이 멤버 함수를 호출 하 고 인쇄 대화 상자에서 이전에 선택한 프린터를 릴리스 합니다.

```
void SelectPrinter(
    HANDLE hDevNames,
    HANDLE hDevMode,
    BOOL bFreeOld = TRUE);
```

### <a name="parameters"></a>매개 변수

*hDevNames*<br/>
에 대 한 핸들을 [DEVNAMES](/windows/desktop/api/commdlg/ns-commdlg-tagdevnames) 드라이버, 장치 및 특정 프린터의 출력 포트 이름을 식별 하는 구조입니다.

*hDevMode*<br/>
에 대 한 핸들을 [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) 장치 초기화 및 프린터의 환경에 대 한 정보를 지정 하는 구조입니다.

*bFreeOld*<br/>
이전에 선택한 프린터를 해제합니다.

### <a name="remarks"></a>설명

둘 다 *hDevMode* 하 고 *hDevNames* null이 `SelectPrinter` 현재 기본 프린터를 사용 합니다.

##  <a name="sethelpmode"></a>  CWinApp::SetHelpMode

응용 프로그램의 도움말 유형을 설정합니다.

```
void SetHelpMode(AFX_HELP_TYPE eHelpType);
```

### <a name="parameters"></a>매개 변수

*eHelpType*<br/>
사용 하는 도움말의 형식을 지정 합니다. 참조 [CWinApp::m_eHelpType](#m_ehelptype) 자세한 내용은 합니다.

### <a name="remarks"></a>설명

응용 프로그램의 도움말 유형을 설정합니다.

HTMLHelp 응용 프로그램의 도움말 형식으로를 호출할 수 있습니다 [EnableHTMLHelp](#enablehtmlhelp)합니다. 호출 했으면 `EnableHTMLHelp`, 응용 프로그램의 도움말 응용 프로그램으로 HTMLHelp를 사용 해야 합니다. WinHelp를 사용 하 여 변경 하려는 경우 호출할 수 있습니다 `SetHelpMode` 설정 *eHelpType* 하려면 `afxWinHelp`합니다.

##  <a name="setregistrykey"></a>  CWinApp::SetRegistryKey

INI 파일 대신 레지스트리에 저장 될 응용 프로그램 설정 하면 됩니다.

```
void SetRegistryKey(LPCTSTR lpszRegistryKey);
void SetRegistryKey(UINT nIDRegistryKey);
```

### <a name="parameters"></a>매개 변수

*lpszRegistryKey*<br/>
키의 이름을 포함 하는 문자열에 대 한 포인터입니다.

*nIDRegistryKey*<br/>
레지스트리 키의 이름을 포함 하는 문자열 리소스의 ID입니다.

### <a name="remarks"></a>설명

이 함수를 설정 합니다 *m_pszRegistryKey*에서 사용 되는 합니다 `GetProfileInt`를 `GetProfileString`를 `WriteProfileInt`, 및 `WriteProfileString` 의 멤버 함수 `CWinApp`합니다. 이 함수를 호출 하면 가장 최근에 사용한 (MRU) 파일의 목록도 레지스트리에 저장 됩니다. 레지스트리 키를 일반적으로 회사의 이름입니다. 다음과 같은 형식의 키에 저장 됩니다. HKEY_CURRENT_USER\Software\\< 회사 이름\>\\< 응용 프로그램 이름\>\\< 섹션 이름\>\\< 값 이름\>합니다.

##  <a name="supportsapplicationrecovery"></a>  CWinApp::SupportsApplicationRecovery

다시 시작 관리자 예기치 않게 종료 하는 응용 프로그램을 복구 하는지 여부를 결정 합니다.

```
virtual BOOL SupportsApplicationRecovery() const;
```

### <a name="return-value"></a>반환 값

TRUE 이면 응용 프로그램을 복구 하는 다시 시작 관리자 FALSE 이면 다시 시작 관리자 하지 않습니다.

##  <a name="supportsautosaveatinterval"></a>  CWinApp::SupportsAutosaveAtInterval

일정 한 간격으로 다시 시작 관리자에서 열려 있는 문서 여부를 결정 합니다.

```
virtual BOOL SupportsAutosaveAtInterval() const;
```

### <a name="return-value"></a>반환 값

TRUE 이면 다시 시작 관리자에서 열려 있는 문서입니다. FALSE 이면 다시 시작 관리자 하지 않습니다.

##  <a name="supportsautosaveatrestart"></a>  CWinApp::SupportsAutosaveAtRestart

확인 여부를 다시 시작 관리자에서 응용 프로그램 다시 시작 되 면 모든 열린 문서.

```
virtual BOOL SupportsAutosaveAtRestart() const;
```

### <a name="return-value"></a>반환 값

TRUE 이면 다시 시작 관리자에서 응용 프로그램을 다시 시작 되; 문서 열기 FALSE 이면 다시 시작 관리자 하지 않습니다.

##  <a name="supportsrestartmanager"></a>  CWinApp::SupportsRestartManager

응용 프로그램 다시 시작 관리자를 지원 하는지 여부를 결정 합니다.

```
virtual BOOL SupportsRestartManager() const;
```

### <a name="return-value"></a>반환 값

TRUE 이면 응용 프로그램을 다시 시작 관리자 지원 FALSE 이면 응용 프로그램을 하지 않습니다.

##  <a name="unregister"></a>  CWinApp::Unregister

응용 프로그램 개체에 의해 등록 된 모든 파일을 등록 취소 합니다.

```
virtual BOOL Unregister();
```

### <a name="return-value"></a>반환 값

성공하면 0이 아닌 값이고, 실패하면 0입니다.

### <a name="remarks"></a>설명

합니다 `Unregister` 응용 프로그램 개체에서 수행 하 여 등록을 취소 하는 함수 및 [등록](#register) 함수입니다. 일반적으로 두 함수는 MFC에서 암시적으로 라고 하며 코드에 표시 되지 않습니다.

사용자 지정 등록 해제 단계를 수행 하려면이 함수를 재정의 합니다.

##  <a name="unregistershellfiletypes"></a>  CWinApp::UnregisterShellFileTypes

응용 프로그램의 문서 유형에 Windows 파일 관리자의 모든 등록을 취소 하려면이 멤버 함수를 호출 합니다.

```
void UnregisterShellFileTypes();
```

##  <a name="winhelp"></a>  CWinApp::WinHelp

WinHelp 응용 프로그램을 호출 하려면이 멤버 함수를 호출 합니다.

```
virtual void WinHelp(
    DWORD_PTR dwData,
    UINT nCmd = HELP_CONTEXT);
```

### <a name="parameters"></a>매개 변수

*dwData*<br/>
추가 데이터를 지정합니다. 값에 따라 사용 되는 값을 *nCmd* 매개 변수입니다.

*nCmd*<br/>
요청한 도움말의 형식을 지정합니다. 가능한 값 목록과 미치는 영향에 대 한 합니다 *dwData* 매개 변수를 참조 합니다 [WinHelp](/windows/desktop/api/winuser/nf-winuser-winhelpa) Windows 함수입니다.

### <a name="remarks"></a>설명

프레임 워크는 또한 WinHelp 응용 프로그램을 호출 하려면이 함수를 호출 합니다.

프레임 워크를 자동으로 닫힙니다 WinHelp 응용 프로그램을 응용 프로그램을 종료 하는 경우.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#53](../../mfc/reference/codesnippet/cpp/cwinapp-class_28.cpp)]

##  <a name="writeprofilebinary"></a>  CWinApp::WriteProfileBinary

응용 프로그램 레지스트리의 지정된 된 섹션에 이진 데이터를 쓸이 멤버 함수 호출 또는 합니다. INI 파일입니다.

```
BOOL WriteProfileBinary(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPBYTE pData,
    UINT nBytes);
```

### <a name="parameters"></a>매개 변수

*lpszSection*<br/>
항목이 포함된 섹션을 지정하는 null로 끝나는 문자열을 가리킵니다. 섹션 존재 하지 않는 경우 만들어집니다. 섹션의 이름은 대/소문자 독립; 모든 조합을 대문자 및 소문자 문자열 수 있습니다.

*lpszEntry*<br/>
값이 쓰여질 항목이 포함 된 null로 끝나는 문자열을 가리킵니다. 지정된 된 섹션에 항목이 없으면 자동으로 만들어집니다.

*pData*<br/>
쓸 데이터를 가리킵니다.

*nBytes*<br/>
쓸 바이트 수를 포함 합니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

이 예제에서는 `CWinApp* pApp = AfxGetApp();` CWinApp 클래스가 더는 방법을 보여 주는 가져옵니다 하 `WriteProfileBinary` 및 `GetProfileBinary` MFC 응용 프로그램에서 모든 함수에서 사용할 수 있습니다.

[!code-cpp[NVC_MFCWindowing#54](../../mfc/reference/codesnippet/cpp/cwinapp-class_29.cpp)]

다른 예를 들어에 대 한 예제를 참조 하세요 [CWinApp::GetProfileBinary](#getprofilebinary)합니다.

##  <a name="writeprofileint"></a>  CWinApp::WriteProfileInt

응용 프로그램 레지스트리의 지정된 된 섹션에 지정된 된 값을 쓸이 멤버 함수 호출 또는 합니다. INI 파일입니다.

```
BOOL WriteProfileInt(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    int nValue);
```

### <a name="parameters"></a>매개 변수

*lpszSection*<br/>
항목이 포함된 섹션을 지정하는 null로 끝나는 문자열을 가리킵니다. 섹션 존재 하지 않는 경우 만들어집니다. 섹션의 이름은 대/소문자 독립; 모든 조합을 대문자 및 소문자 문자열 수 있습니다.

*lpszEntry*<br/>
값이 쓰여질 항목이 포함 된 null로 끝나는 문자열을 가리킵니다. 지정된 된 섹션에 항목이 없으면 자동으로 만들어집니다.

*nValue*<br/>
쓸 값을 포함 합니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

이 예제에서는 `CWinApp* pApp = AfxGetApp();` CWinApp 클래스가 더는 방법을 보여 주는에서 하 `WriteProfileString`, `WriteProfileInt`, `GetProfileString`, 및 `GetProfileInt` MFC 응용 프로그램에서 모든 함수에서 사용할 수 있습니다.

[!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]

다른 예를 들어에 대 한 예제를 참조 하세요 [CWinApp::GetProfileInt](#getprofileint)합니다.

##  <a name="writeprofilestring"></a>  CWinApp::WriteProfileString

응용 프로그램 레지스트리의 지정된 된 섹션에 지정된 된 문자열을 작성 하려면이 멤버 함수 호출 또는 합니다. INI 파일입니다.

```
BOOL WriteProfileString(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPCTSTR lpszValue);
```

### <a name="parameters"></a>매개 변수

*lpszSection*<br/>
항목이 포함된 섹션을 지정하는 null로 끝나는 문자열을 가리킵니다. 섹션 존재 하지 않는 경우 만들어집니다. 섹션의 이름은 대/소문자 독립; 모든 조합을 대문자 및 소문자 문자열 수 있습니다.

*lpszEntry*<br/>
값이 쓰여질 항목이 포함 된 null로 끝나는 문자열을 가리킵니다. 지정된 된 섹션에 항목이 없으면 자동으로 만들어집니다. 섹션에서 지정 된이 매개 변수가 NULL 이면 *lpszSection* 삭제 됩니다.

*lpszValue*<br/>
쓸 문자열을 가리킵니다. 이 매개 변수가 NULL 인 항목을 지정 합니다 *lpszEntry* 매개 변수 삭제 합니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]

다른 예를 들어에 대 한 예제를 참조 하세요 [CWinApp::GetProfileInt](#getprofileint)합니다.

##  <a name="setappid"></a>  CWinApp::SetAppID

응용 프로그램에 대 한 응용 프로그램 사용자 모델 ID를 명시적으로 설정합니다. 사용자 인터페이스 (좋습니다는 응용 프로그램 생성자) 사용자에 게 표시 되기 전에이 메서드를 호출 해야 합니다.

```
void SetAppID(LPCTSTR lpcszAppID);
```

### <a name="parameters"></a>매개 변수

*lpcszAppID*<br/>
응용 프로그램 사용자 모델 ID를 지정합니다.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고자료

[CWinThread 클래스](../../mfc/reference/cwinthread-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[방법: 다시 시작 관리자 지원 추가](../../mfc/how-to-add-restart-manager-support.md)
