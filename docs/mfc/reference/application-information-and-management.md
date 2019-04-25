---
title: 응용 프로그램 정보 및 관리
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.macros
helpviewer_keywords:
- applications [MFC], managing
ms.assetid: b72f4154-24db-4e75-bca3-6873e2459c15
ms.openlocfilehash: 78b9ae467d3504f3922c540a3e4cd100322d8f4e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62151284"
---
# <a name="application-information-and-management"></a>응용 프로그램 정보 및 관리

단일 응용 프로그램을 작성할 때 만든 [CWinApp](../../mfc/reference/cwinapp-class.md)-파생 개체입니다. 때때로 하려는 경우 외부에서이 개체에 대 한 정보는 `CWinApp`-파생 개체입니다. 또는 다른 전역 "관리자" 개체에 대 한 액세스를 해야 할 수 있습니다.

Microsoft Foundation Class 라이브러리는 이러한 작업을 수행 하는 데 다음 전역 함수를 제공 합니다.

### <a name="application-information-and-management-functions"></a>응용 프로그램 정보 및 관리 기능

|||
|-|-|
|[AfxBeginThread](#afxbeginthread)|새 스레드를 만듭니다.|
|[AfxContextMenuManager](#afxcontextmenumanager)|전역에 대 한 포인터 [상황에 맞는 메뉴 관리자](ccontextmenumanager-class.md)합니다.|
|[AfxEndThread](#afxendthread)|현재 스레드를 종료합니다.|
|[AfxFindResourceHandle](#afxfindresourcehandle)|리소스 체인에 설명 하 고 특정 리소스에서 리소스 ID 및 리소스 종류를 찾습니다. |
|[AfxFreeLibrary](#afxfreelibrary)|동적 연결 라이브러리 (DLL)이 로드 된 모듈의 참조 횟수를 감소 시킵니다. 참조 횟수가 0에 도달 하면 모듈 매핑된 아닙니다.|
|[AfxGetApp](#afxgetapp)|응용 프로그램에 대 한 포인터의 단일 반환 `CWinApp` 개체입니다.|
|[AfxGetAppName](#afxgetappname)|응용 프로그램의 이름을 포함 하는 문자열을 반환 합니다.|
|[AfxGetInstanceHandle](#afxgetinstancehandle)|응용 프로그램의이 인스턴스를 나타내는 HINSTANCE를 반환 합니다.|
|[AfxGetMainWnd](#afxgetmainwnd)|현재 "main" 창 비 OLE 응용 프로그램 또는 서버 응용 프로그램의 내부 프레임 창에 대 한 포인터를 반환합니다.|
|[AfxGetPerUserRegistration](#afxgetperuserregistration)|이 함수를 사용 하 여 응용 프로그램에 대 한 레지스트리 액세스 리디렉션합니다 여부를 결정 하는 **HKEY_CURRENT_USER** ( **HKCU**) 노드.|
|[AfxGetResourceHandle](#afxgetresourcehandle)|응용 프로그램의 기본 리소스의 원본에 HINSTANCE를 반환합니다. 이 사용 하 여 응용 프로그램의 리소스에 직접 액세스할 수 있습니다.|
|[AfxGetThread](#afxgetthread)|현재 포인터를 검색 [CWinThread](../../mfc/reference/cwinthread-class.md) 개체입니다.|
|[AfxInitRichEdit](#afxinitrichedit)|버전 1.0 rich edit 컨트롤 응용 프로그램을 초기화 합니다.|
|[AfxInitRichEdit2](#afxinitrichedit2)|버전 2.0 이상 rich edit 컨트롤 응용 프로그램을 초기화 합니다.|
|[AfxIsExtendedFrameClass](#afxisextendedframeclass)|지정된 창이 확장된 프레임 개체인지 여부를 확인합니다.|
|[AfxIsMFCToolBar](#afxismfctoolbar)|지정된 된 창 도구 모음 개체 인지 여부를 결정 합니다.|
|[AfxKeyboardManager](#afxkeyboardmanager)|전역에 대 한 포인터 [키보드 manager](ckeyboardmanager-class.md)합니다.|
|[AfxLoadLibrary](#afxloadlibrary)|DLL 모듈을 매핑하고 DLL 함수의 주소를 가져오는 데 사용할 수 있는 핸들을 반환 합니다.|
|[AfxMenuTearOffManager](#afxmenutearoffmanager)|전역에 대 한 포인터 [인 tearoff 메뉴 관리자](cmenutearoffmanager-class.md)합니다.|
|[AfxMouseManager](#afxmousemanager)|전역에 대 한 포인터 [마우스 manager](cmousemanager-class.md)합니다.|
|[AfxRegisterClass](#afxregisterclass)|MFC를 사용 하는 DLL의 창 클래스를 등록 합니다.|
|[AfxRegisterWndClass](#afxregisterwndclass)|MFC에서 자동으로 등록 된를 보완 하기 위해 Windows 창 클래스를 등록 합니다.|
|[AfxSetPerUserRegistration](#afxsetperuserregistration)|응용 프로그램에 대 한 레지스트리 액세스 리디렉션합니다 있는지 여부를 설정 합니다 **HKEY_CURRENT_USER** ( **HKCU**) 노드.|
|[AfxSetResourceHandle](#afxsetresourcehandle)|응용 프로그램의 기본 리소스를 로드 하는 위치 HINSTANCE 핸들을 설정 합니다.|
|[AfxShellManager](#afxshellmanager)|전역에 대 한 포인터 [셸 관리자](cshellmanager-class.md)합니다. |
|[AfxSocketInit](#afxsocketinit)|호출을 `CWinApp::InitInstance` Windows 소켓을 초기화 하는 재정의 합니다.|
|[AfxUserToolsManager](#afxusertoolsmanager)|전역에 대 한 포인터 [사용자 도구 관리자](cusertoolsmanager-class.md)합니다.|
|[AfxWinInit](#afxwininit)|MFC에서 제공한 호출한 `WinMain` 의 일부로 함수를 [CWinApp](../../mfc/reference/cwinapp-class.md) GUI 기반 응용 프로그램을 MFC를 초기화 하려면 초기화 합니다. MFC를 사용 하는 콘솔 응용 프로그램에 대 한 직접 호출 해야 합니다.|

##  <a name="afxbeginthread"></a>  AfxBeginThread

새 스레드를 만드는 데이 함수를 호출 합니다.

```
CWinThread* AfxBeginThread(
    AFX_THREADPROC pfnThreadProc,
    LPVOID pParam,
    int nPriority = THREAD_PRIORITY_NORMAL,
    UINT nStackSize = 0,
    DWORD dwCreateFlags = 0,
    LPSECURITY_ATTRIBUTES lpSecurityAttrs = NULL);

CWinThread* AfxBeginThread(
    CRuntimeClass* pThreadClass,
    int nPriority = THREAD_PRIORITY_NORMAL,
    UINT nStackSize = 0,
    DWORD dwCreateFlags = 0,
    LPSECURITY_ATTRIBUTES lpSecurityAttrs = NULL);
```

### <a name="parameters"></a>매개 변수

*pfnThreadProc*<br/>
작업자 스레드의 제어 함수를 가리킵니다. NULL일 수 없습니다. 이 함수는 다음과 같이 선언 해야 합니다.

`UINT __cdecl MyControllingFunction( LPVOID pParam );`

*pThreadClass*<br/>
파생 된 개체의 RUNTIME_CLASS [CWinThread](../../mfc/reference/cwinthread-class.md)합니다.

*pParam*<br/>
함수 선언에 매개 변수에 표시 된 것 처럼 제어 함수에 전달할 매개 변수 *pfnThreadProc*합니다.

*nPriority*<br/>
스레드의 원하는 우선 순위입니다. 전체 목록 및 설명을 사용할 수 있는 우선 순위를 참조 하세요 [SetThreadPriority](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) Windows SDK에 있습니다.

*nStackSize*<br/>
새 스레드의 스택 (바이트)에서 크기를 지정합니다. 0 인 경우 스택 크기를 만드는 스레드와 스택의 동일한 크기가 기본값은입니다.

*dwCreateFlags*<br/>
스레드 생성을 제어 하는 추가 플래그를 지정 합니다. 이 플래그는 두 값 중 하나를 포함할 수 있습니다.

- CREATE_SUSPENDED 일시 중단 횟수 하나를 사용 하 여 스레드를 시작 합니다. 모든 멤버 데이터를 초기화 하려는 경우 CREATE_SUSPENDED를 사용 합니다 `CWinThread` 개체와 같은 [m_bAutoDelete](../../mfc/reference/cwinthread-class.md#m_bautodelete) 또는 스레드가 실행을 시작 하기 전에 파생된 클래스의 모든 멤버입니다. 사용 하 여 초기화 완료 되 면 [cwinthread:: Resumethread](../../mfc/reference/cwinthread-class.md#resumethread) 실행 스레드를 시작 합니다. 될 때까지 스레드가 실행 되지 것입니다 `CWinThread::ResumeThread` 라고 합니다.

- **0** 스레드를 만든 후 즉시 시작 합니다.

*lpSecurityAttrs*<br/>
가리키는 [SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560) 스레드에 대 한 보안 특성을 지정 하는 구조입니다. NULL 인 경우 만드는 스레드와 동일한 보안 특성이 사용 됩니다. 이 구조에 대 한 자세한 내용은 Windows SDK를 참조 하세요.

### <a name="return-value"></a>반환 값

새로 만든된 스레드 개체에 오류가 발생 하는 경우에 NULL 포인터입니다.

### <a name="remarks"></a>설명

첫 번째 폼은 `AfxBeginThread` 작업자 스레드를 만듭니다. 두 번째 형태는 사용자 인터페이스 스레드 또는 작업자 스레드로 사용 될 수 있는 스레드를 만듭니다.

`AfxBeginThread` 새로 만듭니다 `CWinThread` 개체, 호출 해당 [CreateThread](../../mfc/reference/cwinthread-class.md#createthread) 스레드의 실행을 시작 하는 함수 및 스레드에 대 한 포인터를 반환 합니다. 검사가 모든 개체가 제대로 할당 해제 생성 부분이 실패 했는지를 전체 프로시저에서 수행 됩니다. 호출 스레드를 종료 하려면 [AfxEndThread](#afxendthread) 에서 내 스레드 또는 작업자 스레드의 제어 함수에서 반환 합니다.

다중 스레딩 응용 프로그램에서 사용할 수 있어야 합니다. 그렇지 않으면이 함수가 실패 합니다. 다중 스레딩을 사용에 대 한 자세한 내용은 참조 [/MD, /MT, /LD (런타임 라이브러리 사용)](../../build/reference/md-mt-ld-use-run-time-library.md) 아래에서 *시각적 C++ 컴파일러 옵션*합니다.

에 대 한 자세한 `AfxBeginThread`, 문서를 참조 [다중 스레딩: 작업자 스레드를 만들지](../../parallel/multithreading-creating-worker-threads.md) 고 [다중 스레딩: 사용자 인터페이스 스레드 만들기](../../parallel/multithreading-creating-user-interface-threads.md)합니다.

### <a name="example"></a>예제

예를 참조 하세요 [csocket:: Attach](../../mfc/reference/csocket-class.md#attach)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

## <a name="afxcontextmenumanager"></a> AfxContextMenuManager

전역에 대 한 포인터 [상황에 맞는 메뉴 관리자](ccontextmenumanager-class.md)합니다.

### <a name="syntax"></a>구문

```
CContextMenuManager* afxContextMenuManager;
```

### <a name="requirements"></a>요구 사항

**헤더:** afxcontextmenumanager.h

##  <a name="afxendthread"></a>  AfxEndThread

현재 실행 중인 스레드를 종료 하려면이 함수를 호출 합니다.

```
void AFXAPI AfxEndThread(
    UINT nExitCode,
    BOOL bDelete  = TRUE);
```

### <a name="parameters"></a>매개 변수

*nExitCode*<br/>
스레드의 종료 코드를 지정합니다.

*bDelete*<br/>
스레드 개체가 메모리에서 삭제 합니다.

### <a name="remarks"></a>설명

종료 될 스레드 내에서 호출 되어야 합니다.

에 대 한 자세한 `AfxEndThread`, 문서를 참고 [다중 스레딩: 스레드 종료](../../parallel/multithreading-terminating-threads.md)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

  ## <a name="afxfindresourcehandle"></a>AfxFindResourceHandle
사용 하 여 `AfxFindResourceHandle` 리소스 체인을 탐색 하 여 특정 리소스에서 리소스 ID 및 리소스 유형을 찾습니다.

### <a name="syntax"></a>구문

```
HINSTANCE AFXAPI AfxFindResourceHandle( LPCTSTR lpszName,  LPCTSTR lpszType );
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
리소스 ID를 포함 하는 문자열에 대 한 포인터
*lpszType*<br/>
리소스 형식에 대 한 포인터입니다. 리소스 형식의 목록을 참조 하세요 [FindResource](/windows/desktop/api/winbase/nf-winbase-findresourcea) Windows SDK에 있습니다.

### <a name="return-value"></a>반환 값

리소스를 포함 하는 모듈에 대 한 핸들입니다.

### <a name="remarks"></a>설명

`AfxFindResourceHandle` 특정 리소스를 찾아 리소스가 포함 된 모듈에 대 한 핸들을 반환 합니다. MFC 확장명 DLL 로드 한 리소스가 있을 수 있습니다. `AfxFindResourceHandle` 어떤 리소스에 알려 줍니다.

모듈은이 순서 대로 검색 됩니다.

1. 주 모듈 (MFC 확장 DLL 경우).

1. 비시스템 모듈입니다.

1. 언어별 모듈입니다.

1. 주 모듈 (시스템 DLL 경우).

1. 시스템 모듈입니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

##  <a name="afxfreelibrary"></a>  AfxFreeLibrary

`AfxFreeLibrary` 및 `AfxLoadLibrary`는 각 코딩된 라이브러리 모듈에 대한 참조 횟수를 유지 관리합니다.

```
BOOL AFXAPI AfxFreeLibrary(HINSTANCE hInstLib);
```

### <a name="parameters"></a>매개 변수

*hInstLib*<br/>
로드된 라이브러리 모듈의 핸들입니다. [AfxLoadLibrary](#afxloadlibrary) 이 핸들을 반환 합니다.

### <a name="return-value"></a>반환 값

함수가 성공 하면 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

`AfxFreeLibrary`는 로드된 DLL(동적 연결 라이브러리) 모듈의 참조 횟수를 감소시킵니다. 참조 횟수가 0에 도달하면, 호출 프로세스의 주소 공간에서 모듈이 매핑 해제되고 핸들이 더 이상 유효하지 않습니다. 이 참조 카운트는 `AfxLoadLibrary`가 호출될 때마다 매번 증가합니다.

라이브러리 모듈을 매핑 해제하기 전에 시스템은 DLL이 이를 사용하는 프로세스에서 분리할 수 있게 해줍니다. 이렇게 하면 DLL이 현재 프로세스를 대신해서 할당된 리소스를 정리할 수 있는 기회가 부여됩니다. 진입점 함수가 반환된 다음 라이브러리 모듈은 현재 프로세스의 주소 공간에서 제거됩니다.

`AfxLoadLibrary`를 사용해서 DLL 모듈을 매핑합니다.

사용 해야 `AfxFreeLibrary` 하 고 `AfxLoadLibrary` (Win32 함수 대신 `FreeLibrary` 고 `LoadLibrary`) 응용 프로그램에서 여러 스레드를 사용 하는 경우. 사용 하 여 `AfxLoadLibrary` 고 `AfxFreeLibrary` 되도록 MFC 확장 DLL을 로드 하거나 언로드할 전역 MFC 상태가 손상 되지 않습니다 때 실행 되는 시작 및 종료 코드입니다.

### <a name="example"></a>예제

예를 참조 하세요 [AfxLoadLibrary](#afxloadlibrary)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdll_.h

##  <a name="afxgetapp"></a>  AfxGetApp

기본 메시지 디스패치 코드 맨 위 창 등 응용 프로그램 정보에 액세스 하려면이 함수에 의해 반환 된 포인터를 사용할 수 있습니다.

```
CWinApp* AFXAPI AfxGetApp();
```

### <a name="return-value"></a>반환 값

단일에 대 한 포인터 `CWinApp` 응용 프로그램에 대 한 개체입니다.

### <a name="remarks"></a>설명

이 메서드가 NULL을 반환 하는 경우는 응용 프로그램 주 창이 초기화 되지 않은 완전히 아직 나타낼 수 있습니다. 또한 문제를 나타낼 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#126](../../mfc/reference/codesnippet/cpp/application-information-and-management_1.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

##  <a name="afxgetappname"></a>  AfxGetAppName

이 함수에 의해 반환 된 문자열 수는 루트 또는 진단 메시지에 대 한 임시 문자열 이름에 대 한 합니다.

```
LPCTSTR AFXAPI AfxGetAppName();
```

### <a name="return-value"></a>반환 값

응용 프로그램의 이름을 포함 하는 null 종료 문자열입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#127](../../mfc/reference/codesnippet/cpp/application-information-and-management_2.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

##  <a name="afxgetinstancehandle"></a>  AfxGetInstanceHandle

이 함수를 사용 하면 현재 응용 프로그램의 인스턴스 핸들을 가져올 수 있습니다.

```
HINSTANCE  AFXAPI AfxGetInstanceHandle();
```

### <a name="return-value"></a>반환 값

응용 프로그램의 현재 인스턴스와 HINSTANCE 합니다. USRDLL 버전의 MFC 사용 하 여 연결 된 DLL 내에서 호출 하는 경우 DLL에 HINSTANCE 반환 됩니다.

### <a name="remarks"></a>설명

`AfxGetInstanceHandle` 실행 파일의 HINSTANCE은 항상 반환 (합니다. EXE) DLL USRDLL 버전의 MFC 사용 하 여 연결 내에서 호출 하지 않으면. 이 경우에 DLL에 대 한 HINSTANCE를 반환합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#128](../../mfc/reference/codesnippet/cpp/application-information-and-management_3.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

##  <a name="afxgetmainwnd"></a>  AfxGetMainWnd

OLE 서버 응용 프로그램을 사용 하는 경우 직접 참조 하는 대신 응용 프로그램의 활성 주 창에 대 한 포인터를 검색 하려면이 함수를 호출 합니다 [m_pMainWnd](../../mfc/reference/cwinthread-class.md#m_pmainwnd) 응용 프로그램 개체의 멤버입니다.

```
CWnd* AFXAPI AfxGetMainWnd();
```

### <a name="return-value"></a>반환 값

서버의 컨테이너 내에 내부 활성화된 개체가 있고 이 컨테이너가 활성 상태인 경우 이 함수는 내부 활성 문서가 포함된 프레임 창 개체에 대한 포인터를 반환합니다.

이 함수는 단순히 반환 하는 경우 컨테이너 내에 내부 활성화 된 개체가 없거나 응용 프로그램이 OLE 서버가 아닙니다., 합니다 *m_pMainWnd* 응용 프로그램 개체입니다.

응용 프로그램의 기본 스레드에서 `AfxGetMainWnd`가 호출되는 경우 위의 규칙에 따라 응용 프로그램의 주 창이 반환됩니다. 함수가 응용 프로그램의 보조 스레드에서 호출되면 함수는 호출한 스레드에 연결된 주 창을 반환합니다.

### <a name="remarks"></a>설명

응용 프로그램을 OLE 서버가 아닌 경우를 직접 참조 하는이 함수를 호출 합니다 *m_pMainWnd* 응용 프로그램 개체의 멤버입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#129](../../mfc/reference/codesnippet/cpp/application-information-and-management_4.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

##  <a name="afxgetperuserregistration"></a>  AfxGetPerUserRegistration

이 함수를 사용 하 여 응용 프로그램에 대 한 레지스트리 액세스 리디렉션합니다 여부를 결정 하는 **HKEY_CURRENT_USER** ( **HKCU**) 노드.

```
BOOL AFXAPI AfxGetPerUserRegistration();
```

### <a name="return-value"></a>반환 값

TRUE 이면 레지스트리 정보; HKCU 노드로 전달 되는 False로 기본 노드에 레지스트리 정보를 기록 하는 응용 프로그램을 나타냅니다. 기본 노드인 **HKEY_CLASSES_ROOT** ( **HKCR**).

### <a name="remarks"></a>설명

프레임 워크에서 액세스 리디렉션합니다 레지스트리 리디렉션을 사용 하도록 설정 하면 **HKCR** 하 **HKEY_CURRENT_USER\Software\Classes**합니다. MFC 및 ATL 프레임 리디렉션 영향을 받습니다.

응용 프로그램 레지스트리 액세스 리디렉션합니다 여부를 변경 하려면 [AfxSetPerUserRegistration](#afxsetperuserregistration)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxstat_.h

##  <a name="afxgetresourcehandle"></a>  AfxGetResourceHandle

응용 프로그램의 리소스에 직접 액세스 하려면이 함수에서 반환 된 HINSTANCE 처리 사용 예를 들어는 Windows에 대 한 호출에서 함수 `FindResource`합니다.

```
extern HINSTANCE  AfxGetResourceHandle();
```

### <a name="return-value"></a>반환 값

응용 프로그램의 기본 리소스를 로드 하는 위치는 HINSTANCE 핸들입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#130](../../mfc/reference/codesnippet/cpp/application-information-and-management_5.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

##  <a name="afxgetthread"></a>  AfxGetThread

에 대 한 포인터를 가져오려면이 함수를 호출 합니다 [CWinThread](../../mfc/reference/cwinthread-class.md) 현재 실행 중인 스레드를 나타내는 개체입니다.

```
CWinThread* AfxGetThread();
```

### <a name="return-value"></a>반환 값

현재 실행 중인 스레드와;에 대 한 포인터 그렇지 않으면 NULL입니다.

### <a name="remarks"></a>설명

원하는 스레드 내에서 호출 되어야 합니다.

> [!NOTE]
>  MFC 프로젝트 호출을 이식 하는 경우 `AfxGetThread` 시각적 개체에서 C++ 버전 4.2, 5.0 또는 6.0 `AfxGetThread` 호출 [AfxGetApp](#afxgetapp) 스레드가 없습니다 있으면 됩니다. 최신 버전의 컴파일러에서 `AfxGetThread` 없는 스레드를 찾을 수 없으면 NULL을 반환 합니다. 호출 해야 응용 프로그램 스레드에 원한다 면 `AfxGetApp`합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#132](../../mfc/reference/codesnippet/cpp/application-information-and-management_6.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

##  <a name="afxinitrichedit"></a>  AfxInitRichEdit

응용 프로그램에 rich edit 컨트롤 (버전 1.0)을 초기화 하려면이 함수를 호출 합니다.

```
BOOL AFXAPI AfxInitRichEdit();
```

### <a name="remarks"></a>설명

이 함수는 이전 버전과 호환성을 위해 제공 됩니다. 새 응용 프로그램을 사용할지 [AfxInitRichEdit2](#afxinitrichedit2)합니다.

`AfxInitRichEdit` RICHED32를 로드합니다. Rich edit 컨트롤의 버전 1.0을 초기화 하는 DLL입니다. 2.0 및 3.0 RICHED20 서식 있는 편집 컨트롤의 버전을 사용 하도록 DLL 로드 해야 합니다. 호출 하 여 이렇게 [AfxInitRichEdit2](#afxinitrichedit2)합니다.

업데이트 rich edit 기존 시각적 개체에서 컨트롤 C++ 버전 2.0 응용 프로그램을 열어 합니다. 텍스트로 RC 파일에는 "RICHEDIT"에서 "RichEdit20a" 각 서식 있는 편집 컨트롤의 클래스 이름을 변경 합니다. 그런 다음에 대 한 호출 `AfxInitRichEdit` 사용 하 여 `AfxInitRichEdit2`입니다.

이 함수는 또한 라이브러리 프로세스에 대 한 아직 초기화 되지 않은 경우 공용 컨트롤 라이브러리를 초기화 합니다. MFC 응용 프로그램에서 직접 rich edit 컨트롤을 사용 하는 경우 MFC 서식 있는 편집 컨트롤 런타임에 제대로 초기화가 수행 하기 위해이 함수를 호출 해야 합니다. Create 메서드를 호출 하는 경우 [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md)하십시오 [CRichEditView](../../mfc/reference/cricheditview-class.md), 또는 [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md), 일반적으로이 함수를 호출할 필요가 없습니다 있지만 일부의 경우 필요 합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

##  <a name="afxinitrichedit2"></a>  AfxInitRichEdit2

응용 프로그램에 rich edit 컨트롤 (버전 2.0 이상)을 초기화 하려면이 함수를 호출 합니다.

```
BOOL AFXAPI AfxInitRichEdit2();
```

### <a name="remarks"></a>설명

이 함수는 RICHED20 로드를 호출 합니다. DLL 및 초기화의 다양 한 버전 2.0에는 편집 컨트롤입니다. Create 메서드를 호출 하는 경우 [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md)하십시오 [CRichEditView](../../mfc/reference/cricheditview-class.md), 또는 [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md), 일반적으로이 함수를 호출할 필요가 없습니다 있지만 일부의 경우 필요 합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

  ## <a name="afxisextendedframeclass"></a>  AfxIsExtendedFrameClass
지정된 창이 확장된 프레임 개체인지 여부를 확인합니다.

### <a name="syntax"></a>구문

```
BOOL AFXAPI AfxIsExtendedFrameClass( CWnd* pWnd );
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
[in] 파생 된 개체에 대 한 포인터 `CWnd`합니다.

### <a name="return-value"></a>반환 값

제공 된 창이 확장 된 프레임 개체 이면 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 경우 TRUE를 반환 *pWnd* 다음 클래스 중 하나에서 파생 됩니다.

- `CFrameWndEx`

- `CMDIFrameWndEx`

- `COleIPFrameWndEx`

- `COleDocIPFrameWndEx`

- `CMDIChildWndEx`

이 메서드는 함수 또는 메서드 매개 변수가 확장된 프레임 창인지 확인해야 하는 경우에 유용합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxpriv.h

## <a name="afxismfctoolbar"></a> AfxIsMFCToolBar

지정된 된 창 도구 모음 개체 인지 여부를 결정 합니다.

### <a name="syntax"></a>구문

```
BOOL AFXAPI AfxIsMFCToolBar(CWnd* pWnd);
```

### <a name="parameters"></a>매개 변수

*pWnd*<br/>
[in] 파생 된 개체에 대 한 포인터 `CWnd`합니다.

### <a name="return-value"></a>반환 값

제공 된 창 도구 모음 개체; 이면 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 메서드는 반환 `TRUE` 하는 경우 *pWnd* 에서 파생 `CMFCToolBar`합니다. 이 메서드는 함수 또는 메서드 매개 변수 인지 확인 해야 할 경우에 유용를 `CMFCToolBar` 개체입니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxpriv.h

## <a name="afxkeyboardmanager"></a> AfxKeyboardManager

전역에 대 한 포인터 [키보드 manager](ckeyboardmanager-class.md)합니다.

### <a name="syntax"></a>구문

```
CKeyboardManager* afxKeyboardManager;
```

### <a name="requirements"></a>요구 사항

**헤더:** afxkeyboardmanager.h

##  <a name="afxloadlibrary"></a>  AfxLoadLibrary

`AfxLoadLibrary`를 사용해서 DLL 모듈을 매핑합니다.

```
HINSTANCE AFXAPI AfxLoadLibrary(LPCTSTR lpszModuleName);
```

### <a name="parameters"></a>매개 변수

*lpszModuleName*<br/>
모듈의 이름이 포함 된 null로 끝나는 문자열을 가리키는 (중 하나를 합니다. DLL 또는 합니다. EXE 파일)입니다. 지정 된 이름은 모듈의 이름입니다.

문자열의 경로 지정 하 고 지정된 된 디렉터리에 파일이 없는 경우 함수 실패 합니다.

파일 이름 확장명을 생략 하면 경로 지정 하지 않으면 경우 기본 확장명입니다. DLL이 추가 됩니다. 그러나 파일 이름 문자열이 모듈 이름에 확장명이 없고 있음을 나타내기 위해 후행 점 문자 (.)를 포함할 수 있습니다. 없는 경로 지정 하면 함수를 다음 순서로 파일을 검색 합니다.

- 응용 프로그램 로드는 디렉터리입니다.

- 현재 디렉터리입니다.

- **Windows 95/98:** Windows 시스템 디렉터리입니다. **Windows NT:** 32 비트 Windows 시스템 디렉터리입니다. 이 디렉터리의 이름은 SYSTEM32입니다.

- **Windows NT에만 해당:** 16 비트 Windows 시스템 디렉터리입니다. 이 디렉터리의 경로 가져옵니다 하는 Win32 함수가 있지만 검색 됩니다. 이 디렉터리의 이름은 시스템입니다.

- Windows 디렉터리입니다.

- PATH 환경 변수에 나열 된 디렉터리입니다.

### <a name="return-value"></a>반환 값

함수가 성공할 경우 반환 값은 모듈에 대 한 핸들입니다. 함수가 실패 한 경우 반환 값은 NULL입니다.

### <a name="remarks"></a>설명

사용할 수 있는 핸들을 반환 합니다 [GetProcAddress](/windows/desktop/api/libloaderapi/nf-libloaderapi-getprocaddress) DLL 함수의 주소를 가져옵니다. `AfxLoadLibrary` 다른 실행 파일 모듈을 매핑할도 사용할 수 있습니다.

각 프로세스에는 각 로드 된 라이브러리 모듈에 대 한 참조 횟수를 유지 관리합니다. 이 참조 개수가 증가 될 때마다 `AfxLoadLibrary` 라고 하며 각 시간 감소는 `AfxFreeLibrary` 라고 합니다. 참조 횟수가 0에 도달하면, 호출 프로세스의 주소 공간에서 모듈이 매핑 해제되고 핸들이 더 이상 유효하지 않습니다.

사용 해야 `AfxLoadLibrary` 하 고 `AfxFreeLibrary` (Win32 함수 대신 `LoadLibrary` 및 `FreeLibrary`) 여러 스레드를 사용 하는 응용 프로그램 및 동적으로 MFC 확장 DLL을 로드 합니다. 사용 하 여 `AfxLoadLibrary` 고 `AfxFreeLibrary` 하면 MFC 확장명 DLL이 로드 되거나 언로드될 때 실행 되는 시작 및 종료 코드는 전역 MFC 상태가 손상 되지 않습니다.

사용 하 여 `AfxLoadLibrary` 응용 프로그램에서 동적으로 MFC;의 DLL 버전에 연결 해야 헤더 파일에 대 한 `AfxLoadLibrary`, 전용인 Afxdll_.h, MFC DLL로 응용 프로그램에 연결 된 경우를 포함 합니다. 이것은 의도적인 MFC 확장명 Dll을 만들거나 사용 하 여 MFC의 DLL 버전에 연결 해야 하기 때문입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_DLLUser#1](../../mfc/reference/codesnippet/cpp/application-information-and-management_7.cpp)]
[!code-cpp[NVC_MFC_DLLUser#2](../../mfc/reference/codesnippet/cpp/application-information-and-management_8.cpp)]
[!code-cpp[NVC_MFC_DLLUser#3](../../mfc/reference/codesnippet/cpp/application-information-and-management_9.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxdll_.h

## <a name="afxmenutearoffmanager"></a> AfxMenuTearOffManager

전역에 대 한 포인터 [인 tearoff 메뉴 관리자](cmenutearoffmanager-class.md)합니다.

### <a name="syntax"></a>구문

```
CMenuTearOffManager* g_pTearOffMenuManager;
```

### <a name="requirements"></a>요구 사항

**헤더:** afxmenutearoffmanager.h

## <a name="afxmousemanager"></a>  AfxMouseManager

전역에 대 한 포인터 [마우스 manager](cmousemanager-class.md)합니다.

### <a name="syntax"></a>구문

```
CMouseManager* afxMouseManager;
```

### <a name="requirements"></a>요구 사항

**헤더:** afxmousemanager.h

##  <a name="afxregisterclass"></a>  AfxRegisterClass

이 함수를 사용 하 여 MFC를 사용 하는 DLL에서 창 클래스를 등록 합니다.

```
BOOL AFXAPI AfxRegisterClass(WNDCLASS* lpWndClass);
```

### <a name="parameters"></a>매개 변수

*lpWndClass*<br/>
에 대 한 포인터를 [WNDCLASS](/windows/desktop/api/winuser/ns-winuser-tagwndclassa) 창 클래스 등록에 대 한 정보를 포함 하는 구조체. 이 구조에 대 한 자세한 내용은 Windows SDK를 참조 하세요.

### <a name="return-value"></a>반환 값

클래스는 성공적으로 등록 되 면 TRUE입니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이 함수를 사용 하는 경우에 DLL을 언로드할 때 클래스를 자동으로 등록 취소 됩니다.

DLL이 아닌 빌드에는 `AfxRegisterClass` 식별자는 Windows 함수에 매핑되는 매크로로 정의 됩니다 `RegisterClass`응용 프로그램에 등록 하는 클래스를 자동으로 등록 되지 않은 때문입니다. 사용 하는 경우 `AfxRegisterClass` 대신 `RegisterClass`, 코드를 응용 프로그램 및 DLL의 변경 없이 사용할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_DLL#3](../../atl-mfc-shared/codesnippet/cpp/application-information-and-management_10.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

##  <a name="afxregisterwndclass"></a>  AfxRegisterWndClass

사용자 지정 창 클래스를 등록할 수 있습니다.

```
LPCTSTR AFXAPI AfxRegisterWndClass(
    UINT nClassStyle,
    HCURSOR hCursor = 0,
    HBRUSH hbrBackground = 0,
    HICON hIcon = 0);
```

### <a name="parameters"></a>매개 변수

*nClassStyle*<br/>
Windows 클래스 스타일 또는 조합 스타일에 비트 OR를 사용 하 여 만든 지정 ( **&#124;**) 창 클래스에 대 한 연산자입니다. 클래스 스타일의 목록은 참조 하세요. 합니다 [WNDCLASS](/windows/desktop/api/winuser/ns-winuser-tagwndclassa) Windows SDK에는 구조입니다. NULL 인 경우 기본값을 다음과 같이 설정 됩니다.

- CS_DBLCLKS를 보내고 메시지 창 프로시저를 두 번 클릭 마우스를 두 번 클릭할 때를 마우스로 스타일을 설정 합니다.

- Windows 표준 IDC_ARROW를 화살표 커서 스타일을 설정합니다.

- 창 배경을 지우지 됩니다 있도록 배경 브러시를 NULL로 설정 합니다.

- 표준, 손 흔드는 플래그 Windows 로고 아이콘 아이콘을 설정 합니다.

*hCursor*<br/>
창 클래스에서 만든 각 창에 설치 되도록 커서 리소스에 대 한 핸들을 지정 합니다. 기본값을 사용 하는 경우 **0**, 표준 IDC_ARROW 커서를 얻게 됩니다.

*hbrBackground*<br/>
창 클래스에서 만든 각 창에 설치 되어야 하는 브러시 리소스에 대 한 핸들을 지정 합니다. 기본값을 사용 하는 경우 **0**NULL 배경 브러시를 해야 하 고 창에는 기본적으로 지워지지 처리 하는 동안 배경이 [WM_ERASEBKGND](/windows/desktop/winmsg/wm-erasebkgnd)합니다.

*hIcon*<br/>
창 클래스에서 만든 각 창에 설치 되도록 아이콘 리소스에 대 한 핸들을 지정 합니다. 기본값을 사용 하는 경우 **0**, 표준, 손 흔드는 플래그 Windows 로고 아이콘을 얻게 됩니다.

### <a name="return-value"></a>반환 값

클래스 이름을 포함 하는 null 종료 문자열입니다. 이 클래스 이름을 전달할 수 있습니다 합니다 `Create` 멤버 함수 `CWnd` 또는 다른 **CWnd-** 창을 만들려면 클래스를 파생 합니다. Microsoft Foundation 클래스 라이브러리에서 이름을 생성 됩니다.

> [!NOTE]
>  반환 값은 정적 버퍼에 대 한 포인터입니다. 이 문자열을 저장 하려면 할당을 `CString` 변수입니다.

### <a name="remarks"></a>설명

Microsoft Foundation Class 라이브러리를 여러 표준 창 클래스를 자동으로 등록합니다. 사용자 지정 창 클래스 등록 하려는 경우이 함수를 호출 합니다.

클래스에 대 한 이름을 등록 `AfxRegisterWndClass` 매개 변수에서 전적으로 달라 집니다. 호출 하는 경우 `AfxRegisterWndClass` 여러 번 동일한 매개 변수를 사용 하 여 해당 등록만 첫 번째 호출에서 클래스입니다. 에 대 한 후속 호출 `AfxRegisterWndClass` 동일한 매개 변수를 사용 하 여 이미 등록 된 클래스를 반환 하기만 하면 됩니다.

호출 하는 경우 `AfxRegisterWndClass` 각 클래스에 대해 별도 창 클래스를 시작 하는 대신 동일한 매개 변수를 사용 하 여 여러 CWnd에서 파생 된 클래스에 대 한 각 클래스는 동일한 창 클래스를 공유 합니다. 이 있는 클래스 스타일을 사용 하는 경우이 문제가 발생할 수 있습니다. 여러이 있는 창 클래스 대신 끝나는 하나이 있는 창 클래스와 모든 C++ 클래스를 사용 하는 windows 동일한 DC를 공유 합니다. 이 문제를 방지 하려면 호출 [AfxRegisterClass](#afxregisterclass) 클래스를 등록 합니다.

기술 참고 참조 [TN001: 창 클래스 등록](../../mfc/tn001-window-class-registration.md) 창 클래스 등록에 대 한 자세한 내용은 및 `AfxRegisterWndClass` 함수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#134](../../mfc/reference/codesnippet/cpp/application-information-and-management_11.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

##  <a name="afxsetperuserregistration"></a>  AfxSetPerUserRegistration

응용 프로그램에 대 한 레지스트리 액세스 리디렉션합니다 있는지 여부를 설정 합니다 **HKEY_CURRENT_USER** ( **HKCU**) 노드.

```
void AFXAPI AfxSetPerUserRegistration(BOOL bEnable);
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
[in] TRUE 이면 레지스트리 정보; HKCU 노드로 전달 되는 False로 기본 노드에 레지스트리 정보를 기록 하는 응용 프로그램을 나타냅니다. 기본 노드인 **HKEY_CLASSES_ROOT** ( **HKCR**).

### <a name="remarks"></a>설명

일반적으로 사용 되는 레지스트리를 액세스 하는 응용 프로그램, Windows Vista 이전 합니다 **HKEY_CLASSES_ROOT** 노드. 그러나 Windows Vista 또는 이후 운영 체제를 사용 하 여 HKCR에 관리자 권한 모드로 응용 프로그램을 실행 해야 합니다.

이 메서드를 읽고 레지스트리에 HKCU에 대 한 레지스트리 액세스 HKCR에서 리디렉션하여 관리자 모드에서 실행 하지 않고 응용을 프로그램을 수 있습니다. 자세한 내용은 [Linker Property Pages](../../build/reference/linker-property-pages.md)을 참조하세요.

프레임 워크에 대 한 액세스를 HKCR에서 리디렉션합니다 레지스트리 리디렉션을 사용 하도록 설정 하면 **HKEY_CURRENT_USER\Software\Classes**합니다. MFC 및 ATL 프레임 리디렉션 영향을 받습니다.

HKCR 레지스트리에 액세스 하는 기본 구현입니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxstat_.h

##  <a name="afxsetresourcehandle"></a>  AfxSetResourceHandle

이 함수를 사용 하 여 응용 프로그램의 기본 리소스를 로드 하는 위치를 결정 하는 HINSTANCE 핸들을 설정 합니다.

```
void AFXAPI AfxSetResourceHandle(HINSTANCE hInstResource);
```

### <a name="parameters"></a>매개 변수

*hInstResource*<br/>
인스턴스 또는 모듈에 대 한 핸들을 합니다. 응용 프로그램의 리소스 로드 되는 EXE 또는 DLL 파일입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCWindowing#135](../../mfc/reference/codesnippet/cpp/application-information-and-management_12.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

## <a name="afxshellmanager"></a>  AfxShellManager

전역에 대 한 포인터 [셸 관리자](cshellmanager-class.md)합니다.

### <a name="syntax"></a>구문

```
CShellManager* afxShellManager;
```

### <a name="requirements"></a>요구 사항

**헤더:** afxshellmanager.h

##  <a name="afxsocketinit"></a>  AfxSocketInit

이 함수를 호출 하면 `CWinApp::InitInstance` Windows 소켓을 초기화 하는 재정의 합니다.

```
BOOL AfxSocketInit(WSADATA* lpwsaData = NULL);
```

### <a name="parameters"></a>매개 변수

*lpwsaData*<br/>
에 대 한 포인터를 [WSADATA](/windows/desktop/api/winsock2/ns-winsock2-wsadata) 구조입니다. 하는 경우 *lpwsaData* 을 NULL로 다음의 주소와 같지 않은 합니다 `WSADATA` 구조 호출에 의해 채워집니다 `WSAStartup`합니다. 이 함수 또한 되도록 `WSACleanup` 응용 프로그램을 종료 하기 전에 사용자에 대해 호출 됩니다.

### <a name="return-value"></a>반환 값

함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

정적으로 연결 된 MFC 응용 프로그램에서 보조 스레드에서 MFC 소켓을 사용 하는 경우 호출 해야 `AfxSocketInit` 소켓을 사용 하 여 소켓 라이브러리를 초기화 하는 각 스레드에서 합니다. 기본적으로 `AfxSocketInit` 기본 스레드에서만에서 호출 됩니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxsock.h

## <a name="afxusertoolsmanager"></a>  AfxUserToolsManager

전역에 대 한 포인터 [사용자 도구 관리자](cusertoolsmanager-class.md)합니다.

### <a name="syntax"></a>구문

```
CUserToolsManager* afxUserToolsManager;
```

### <a name="requirements"></a>요구 사항

**헤더:** afxusertoolsmanager.h

##  <a name="afxwininit"></a>  AfxWinInit

MFC에서 제공 하 여이 함수를 호출 `WinMain` 의 일부로 함수를 [CWinApp](../../mfc/reference/cwinapp-class.md) GUI 기반 응용 프로그램을 MFC를 초기화 하려면 초기화 합니다.

```
BOOL AFXAPI AfxWinInit(
    HINSTANCE hInstance,
    HINSTANCE hPrevInstance,
    LPTSTR lpCmdLine,
    int nCmdShow);
```

### <a name="parameters"></a>매개 변수

*hInstance*<br/>
현재 실행 중인 모듈의 핸들입니다.

*hPrevInstance*<br/>
응용 프로그램의 이전 인스턴스 핸들입니다. Win32 기반 응용 프로그램의 경우이 매개 변수는 항상 **NULL**합니다.

*lpCmdLine*<br/>
응용 프로그램에 대 한 명령줄을 지정 하는 null로 끝나는 문자열을 가리킵니다.

*nCmdShow*<br/>
GUI 응용 프로그램의 주 창이 표시 되는 방법을 지정 합니다.

### <a name="remarks"></a>설명

콘솔 응용 프로그램의 경우는 사용 하지 않는 MFC에서 제공한 `WinMain` 를 호출 해야 함수 `AfxWinInit` MFC 초기화를 직접.

호출 하는 경우 `AfxWinInit` 의 인스턴스를 선언 해야 사용자가 직접를 `CWinApp` 클래스입니다. 콘솔 응용 프로그램을를 고유한 클래스를 파생 하지 선택할 수 있습니다 `CWinApp` 의 인스턴스를 대신 사용 하 고 `CWinApp` 직접. 이 기술은 구현에서 응용 프로그램에 대 한 모든 기능을 유지 하려는 경우 적합 **주**합니다.

> [!NOTE]
>  어셈블리에 대 한 활성화 컨텍스트를 만들 때 MFC 사용자 모듈에서 제공 하는 매니페스트 리소스를 사용 합니다. 활성화 컨텍스트는 `AfxWinInit`에서 만듭니다. 자세한 내용은 [MFC 모듈 상태의 활성화 컨텍스트 지원](../../mfc/support-for-activation-contexts-in-the-mfc-module-state.md)합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_AfxWinInit#1](../../mfc/reference/codesnippet/cpp/application-information-and-management_13.cpp)]

### <a name="requirements"></a>요구 사항

  **헤더** afxwin.h

## <a name="see-also"></a>참고자료

[매크로 및 전역](mfc-macros-and-globals.md)<br/>
[CWinApp 클래스](cwinapp-class.md)<br/>
[CContextMenuManager 클래스](ccontextmenumanager-class.md)<br/>
[CWnd 클래스](cwnd-class.md)<br/>
[CFrameWndEx 클래스](cframewndex-class.md)<br/>
[CMFCToolBar 클래스](cmfctoolbar-class.md)<br/>
[CKeyboardManager 클래스](ckeyboardmanager-class.md)<br/>
[CMenuTearOffManager 클래스](cmenutearoffmanager-class.md)<br/>
[CMouseManager 클래스](cmousemanager-class.md)<br/>
[CShellManager 클래스](cshellmanager-class.md)<br/>
[CUserToolsManager 클래스](cusertoolsmanager-class.md)
