---
title: '연습: 기존 Windows 데스크톱 응용 프로그램을 만듭니다 (c + +)'
ms.custom: get-started-article
ms.date: 09/18/2018
helpviewer_keywords:
- Windows applications [C++], Win32
- Windows Desktop applications [C++]
- Windows API [C++]
ms.openlocfilehash: cb6d09acc00f2e38ee41180c81c1877bc53027c2
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59037964"
---
# <a name="walkthrough-create-a-traditional-windows-desktop-application-c"></a>연습: 기존 Windows 데스크톱 응용 프로그램을 만듭니다 (c + +)

이 연습에서는 Visual Studio에서 기존 Windows 데스크톱 응용 프로그램을 만드는 방법을 보여 줍니다. 예제 응용 프로그램을 만든 Windows API를 사용 하 여 "Hello, Windows desktop!"를 표시 하려면 줍니다. 이 연습에서 개발하는 코드를 패턴으로 사용하여 다른 Windows 데스크톱 애플리케이션을 만들 수 있습니다.

Windows API (라고도: Win32 API, Windows Desktop API 및 Windows 클래식 API)는 Windows 응용 프로그램을 만들기 위한 C 언어 기반 프레임 워크입니다. 1980 년대부터 존재에서 되었습니다 하 고 수십 Windows 응용 프로그램을 만드는 데 사용 된 합니다. MFC, ATL 및.NET framework와 같은 Windows API를 기반으로 빌드되어 더욱 고급 및 프로그램을 쉽게 프레임 워크입니다. C +로 작성 된 UWP 및 스토어 앱에 대 한 가장 최신 코드 + WinRT 아래 Windows API를 사용 합니다. Windows API에 대 한 자세한 내용은 참조 하세요. [Windows API 인덱스](/windows/desktop/apiindex/windows-api-list)합니다. 여러 가지 방법으로 Windows 응용 프로그램을 만들어야 하지만 위에서 설명한 프로세스 첫 번째입니다.

> [!IMPORTANT]
> 간단히 하기 위해 일부 코드 문은 텍스트에서 생략 됩니다. 합니다 [코드를 작성](#build-the-code) 이 문서의 끝에 있는 섹션에는 전체 코드를 보여 줍니다.

## <a name="prerequisites"></a>전제 조건

- Microsoft Windows 7 이상을 실행 하는 컴퓨터입니다. 최상의 개발 환경을 위해 Windows 10이 좋습니다.

- Visual Studio 2017의 복사본입니다. 다운로드 하 여 Visual Studio를 설치 하는 방법에 대 한 정보를 참조 하세요 [Visual Studio 설치](/visualstudio/install/install-visual-studio)합니다. 설치 관리자를 실행 해야 합니다 **c + +를 사용한 데스크톱 개발** 작업 확인란이 선택 되어 있습니다. Visual Studio를 설치할 때이 워크 로드를 설치 하지 않은 경우 걱정 하지 마세요. 설치 관리자를 다시 실행 하 고 지금 설치 수 있습니다.

   ![C + +를 사용한 데스크톱 개발](../build/media/desktop-development-with-cpp.png "c + +를 사용한 데스크톱 개발")

- Visual Studio IDE를 사용 하 여의 기본 사항 이해 합니다. 이전 Windows 데스크톱 앱을 사용한 경우 아마도 유지할 수 있습니다. 참조에 대 한 소개 [Visual Studio IDE 기능 둘러보기](/visualstudio/ide/visual-studio-ide)합니다.

- 과정을 따르려면 c + + 언어의 기본 사항을 충분히 이해 합니다. 걱정 하지 마십시오, 너무 복잡 아무일도 하지 않는 것입니다.

## <a name="create-a-windows-desktop-project"></a>Windows 데스크톱 프로젝트 만들기

첫 번째 Windows 데스크톱 프로젝트를 만들고 작동 하는 Windows 데스크톱 응용 프로그램에 대 한 코드를 입력 하려면 다음이 단계를 따릅니다. Visual Studio 2017 15.3 버전 보다 오래 된 Visual Studio의 버전을 사용 하는 경우 건너 뛰 세요 [Visual Studio 2017 RTM에서 Windows 데스크톱 프로젝트를 만들려면](#create-in-vs2017-rtm)합니다.

### <a name="to-create-a-windows-desktop-project-in-visual-studio-2017-update-153-and-later"></a>Visual Studio 2017 업데이트 15.3 이상 Windows 데스크톱 프로젝트를 만들려면

1. **파일** 메뉴에서 **새로 만들기**, **프로젝트**를 차례로 선택합니다.

1. 에 **새 프로젝트** 대화 상자의 왼쪽된 창에서 확장 **설치 됨** > **Visual c + +** 를 선택 하 고 **Windows Desktop**. 가운데 창에서 선택 **Windows 데스크톱 마법사**합니다.

   에 **이름을** 상자 예를 들어 프로젝트의 이름을 입력 합니다 *DesktopApp*합니다. **확인**을 선택합니다.

   ![DesktopApp 프로젝트 이름을](../build/media/desktop-app-new-project-name-153.png "DesktopApp 프로젝트 이름을")

1. 에 **Windows 데스크톱 프로젝트** 대화 상자 아래에 있는 **응용 프로그램 유형**를 선택 **Windows 응용 프로그램 (.exe)**. **추가 옵션**에서 **빈 프로젝트**를 선택합니다. 선택할 **확인** 프로젝트를 만듭니다.

   ![Windows 데스크톱 프로젝트 마법사에서 DesktopApp 만들](../build/media/desktop-app-new-project-wizard-153.png "DesktopApp Windows 데스크톱 프로젝트 마법사에서 만들기")

1. **솔루션 탐색기**, 마우스 오른쪽 단추로 클릭 합니다 **DesktopApp** 프로젝트 **추가**를 선택한 후 **새 항목**.

   ![DesktopApp 프로젝트에 새 항목 추가](../build/media/desktop-app-project-add-new-item-153.gif "DesktopApp 프로젝트에 새 항목 추가")

1. **새 항목 추가** 대화 상자에서 **C++ 파일(.cpp)** 을 선택합니다. 에 **이름을** 상자 예를 들어 파일의 이름을 입력 합니다 *HelloWindowsDesktop.cpp*합니다. **추가**를 선택합니다.

   ![.Cpp 파일 DesktopApp 프로젝트에 추가](../build/media/desktop-app-add-cpp-file-153.png "DesktopApp 프로젝트.cpp 파일 추가")

프로젝트가 만들어집니다 및 원본 파일을 편집기에서 열립니다. 계속 하려면 건너 뛰 세요 [코드를 만들](#create-the-code)합니다.

### <a id="create-in-vs2017-rtm"></a> Visual Studio 2017 RTM에서 Windows 데스크톱 프로젝트를 만들려면

1. **파일** 메뉴에서 **새로 만들기**, **프로젝트**를 차례로 선택합니다.

1. 에 **새 프로젝트** 대화 상자의 왼쪽된 창에서 확장 **설치 됨** > **템플릿** > **Visual c + +** 를 선택한 후 **Win32**합니다. 가운데 창에서 **Win32 프로젝트**를 선택합니다.

   에 **이름을** 상자 예를 들어 프로젝트의 이름을 입력 합니다 *DesktopApp*합니다. **확인**을 선택합니다.

   ![DesktopApp 프로젝트 이름을](../build/media/desktop-app-new-project-name-150.png "DesktopApp 프로젝트 이름을")

1. 에 **개요** 페이지의 **Win32 응용 프로그램 마법사**, 선택 **다음**합니다.

   ![Win32 응용 프로그램 마법사 개요에서 DesktopApp 만들](../build/media/desktop-app-win32-wizard-overview-150.png "DesktopApp Win32 응용 프로그램 마법사 개요에서 만들기")

1. 에 **응용 프로그램 설정** 페이지의 **응용 프로그램 종류**를 선택 **Windows 응용 프로그램**합니다. **추가 옵션**에서 **빈 프로젝트**를 선택합니다. 선택할 **완료** 프로젝트를 만듭니다.

   ![Win32 응용 프로그램 마법사 설정에서 DesktopApp 만듭니다](../build/media/desktop-app-win32-wizard-settings-150.png "DesktopApp Win32 응용 프로그램 마법사 설정에서 만들기")

1. **솔루션 탐색기**DesktopApp 프로젝트를 마우스 오른쪽 단추로 선택 **추가**를 선택한 후 **새 항목**합니다.

   ![DesktopApp 프로젝트에 새 항목 추가](../build/media/desktop-app-project-add-new-item-150.gif "DesktopApp 프로젝트에 새 항목 추가")

1. **새 항목 추가** 대화 상자에서 **C++ 파일(.cpp)** 을 선택합니다. 에 **이름을** 상자 예를 들어 파일의 이름을 입력 합니다 *HelloWindowsDesktop.cpp*합니다. **추가**를 선택합니다.

   ![.Cpp 파일 DesktopApp 프로젝트에 추가](../build/media/desktop-app-add-cpp-file-150.png "DesktopApp 프로젝트.cpp 파일 추가")

프로젝트가 만들어집니다 및 원본 파일을 편집기에서 열립니다.

## <a name="create-the-code"></a>코드 작성

다음으로 Visual Studio에서 Windows 데스크톱 응용 프로그램에 대 한 코드를 만드는 방법에 알아봅니다.

### <a name="to-start-a-windows-desktop-application"></a>Windows 데스크톱 애플리케이션을 시작하려면

1. 모든 C와 마찬가지로 응용 프로그램 및 c + + 응용 프로그램이 있어야 합니다는 `main` 데스크톱 응용 프로그램에 있어야 하는 모든 Windows 시작 지점으로 함수를 `WinMain` 함수입니다. `WinMain` 에 다음 구문이 있습니다.

   ```cpp
   int CALLBACK WinMain(
      _In_ HINSTANCE hInstance,
      _In_ HINSTANCE hPrevInstance,
      _In_ LPSTR     lpCmdLine,
      _In_ int       nCmdShow
   );
   ```

   매개 변수 및 반환 값이 함수에 대 한 정보를 참조 하세요 [WinMain 진입점](/windows/desktop/api/winbase/nf-winbase-winmain)합니다.

   > [!NOTE]
   > 추가 된 모든 단어를 같은 이란 `CALLBACK`, 또는 `HINSTANCE`, 또는 `_In_`? 기존의 Windows API는 typedef를 사용 하 고 전처리기 매크로 추상화를 광범위 하 게 형식 및 플랫폼별의 세부 정보 중 일부 코딩, 규칙을 호출 하는 등 **__declspec** 선언과 컴파일러 pragmas 합니다. Visual Studio에서 IntelliSense를 사용할 수 있습니다 [요약 정보](/visualstudio/ide/using-intellisense#quick-info) 이러한 typedefs 및 매크로 정의 항목을 참조 하는 기능입니다. 관심 단어 위로 마우스를 가져가서 또는 선택 하 고 키를 눌러 **Ctrl**+**K**를 **Ctrl**+**합니까** 에 대 한는 정의 포함 하는 작은 팝업 창입니다. 자세한 내용은 [IntelliSense 사용](/visualstudio/ide/using-intellisense)을 참조하세요. 매개 변수 및 반환 형식을 사용할 경우가 많습니다 *SAL 주석을* 수 있도록 프로그래밍 오류 catch 합니다. 자세한 내용은 [C/c + + 코드 오류를 줄이기 위한 SAL 주석 사용](/visualstudio/code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects)합니다.

1. Windows 데스크톱 프로그램 필요 &lt;windows.h >. &lt;tchar.h > 정의 `TCHAR` 궁극적으로 확인 되는 매크로를 **wchar_t** 유니코드 기호가 프로젝트에 정의 된 경우 그렇지 않은 경우 확인 **char**합니다.  TCHAR 필요 하 고를 사용할 수 없는 항상를 빌드하는 경우 사용 하도록 설정 하는 유니코드를 사용 하 여 **wchar_t** 직접.

   ```cpp
   #include <windows.h>
   #include <tchar.h>
   ```

1. `WinMain` 함수 이외에 모든 Windows 데스크톱 응용 프로그램에는 창 프로시저 함수도 있어야 합니다. 이 함수 이름은 일반적으로 `WndProc` 하지만 원하는 이름을 지정할 수 있습니다. `WndProc` 에 다음 구문이 있습니다.

   ```cpp
   LRESULT CALLBACK WndProc(
      _In_ HWND   hwnd,
      _In_ UINT   uMsg,
      _In_ WPARAM wParam,
      _In_ LPARAM lParam
   );
   ```

   이 함수를 처리 하는 코드 작성 *메시지* Windows에서 응용 프로그램에서 받는 경우 *이벤트* 발생 합니다. 사용자는 응용 프로그램에서 확인 단추를 선택 하면 Windows 메시지를 보냅니다 하 고 내 코드를 작성할 수 있습니다 예를 들어 프로그램 `WndProc` 적합 한 모든 작업을 수행 하는 함수입니다. 라고 *처리* 이벤트입니다. 응용 프로그램에 대 한 관련 된 이벤트를 처리 합니다.

   자세한 내용은 [창 프로시저](/windows/desktop/winmsg/window-procedures)를 참조하세요.

### <a name="to-add-functionality-to-the-winmain-function"></a>WinMain 함수에 기능을 추가하려면

1. 에 `WinMain` 함수를 형식의 구조체를 채우는 [WNDCLASSEX](/windows/desktop/api/winuser/ns-winuser-tagwndclassexa)합니다. 예를 들어, 응용 프로그램 아이콘, 제목 표시줄에 중요 한 점은 창 프로시저에 대 한 함수 포인터를 표시할 이름 창의 배경색을 창에 대 한 정보를 포함 하는 구조입니다. 다음 예제에서는 일반적인 `WNDCLASSEX` 구조를 보여 줍니다.

   ```cpp
   WNDCLASSEX wcex;

   wcex.cbSize         = sizeof(WNDCLASSEX);
   wcex.style          = CS_HREDRAW | CS_VREDRAW;
   wcex.lpfnWndProc    = WndProc;
   wcex.cbClsExtra     = 0;
   wcex.cbWndExtra     = 0;
   wcex.hInstance      = hInstance;
   wcex.hIcon          = LoadIcon(hInstance, IDI_APPLICATION);
   wcex.hCursor        = LoadCursor(NULL, IDC_ARROW);
   wcex.hbrBackground  = (HBRUSH)(COLOR_WINDOW+1);
   wcex.lpszMenuName   = NULL;
   wcex.lpszClassName  = szWindowClass;
   wcex.hIconSm        = LoadIcon(wcex.hInstance, IDI_APPLICATION);
   ```

   위의 구조의 필드에 대 한 정보를 참조 하세요 [WNDCLASSEX](/windows/desktop/api/winuser/ns-winuser-tagwndclassexa)합니다.

1. 등록 된 `WNDCLASSEX` 한다는 창 및 메시지를 보내는 방법에 대 한 알 수 있도록 Windows를 사용 하 여 합니다. [RegisterClassEx](/windows/desktop/api/winuser/nf-winuser-registerclassexa) 함수를 사용하고 창 클래스 구조를 인수로 전달합니다. `_T` 매크로 사용 하기 때문에 사용 되는 `TCHAR` 형식.

   ```cpp
   if (!RegisterClassEx(&wcex))
   {
      MessageBox(NULL,
         _T("Call to RegisterClassEx failed!"),
         _T("Windows Desktop Guided Tour"),
         NULL);

      return 1;
   }
   ```

1. 이제 창을 만들 수 있습니다. [CreateWindow](/windows/desktop/api/winuser/nf-winuser-createwindowa) 함수를 사용합니다.

   ```cpp
   static TCHAR szWindowClass[] = _T("DesktopApp");
   static TCHAR szTitle[] = _T("Windows Desktop Guided Tour Application");

   // The parameters to CreateWindow explained:
   // szWindowClass: the name of the application
   // szTitle: the text that appears in the title bar
   // WS_OVERLAPPEDWINDOW: the type of window to create
   // CW_USEDEFAULT, CW_USEDEFAULT: initial position (x, y)
   // 500, 100: initial size (width, length)
   // NULL: the parent of this window
   // NULL: this application does not have a menu bar
   // hInstance: the first parameter from WinMain
   // NULL: not used in this application
   HWND hWnd = CreateWindow(
      szWindowClass,
      szTitle,
      WS_OVERLAPPEDWINDOW,
      CW_USEDEFAULT, CW_USEDEFAULT,
      500, 100,
      NULL,
      NULL,
      hInstance,
      NULL
   );
   if (!hWnd)
   {
      MessageBox(NULL,
         _T("Call to CreateWindow failed!"),
         _T("Windows Desktop Guided Tour"),
         NULL);

      return 1;
   }
   ```

   이 함수는 반환을 `HWND`, 창에 대 한 핸들 인 합니다. 핸들은 다소 열려 있는 창을 추적 하기 위해 Windows를 사용 하는 포인터입니다. 자세한 내용은 [Windows 데이터 형식](/windows/desktop/WinProg/windows-data-types)을 참조하세요.

1. 이 시점에서 창, 만들어졌지만 표시 되도록 Windows 알 필요가 있습니다. 다음과 같습니다.이 코드의 용도

   ```cpp
   // The parameters to ShowWindow explained:
   // hWnd: the value returned from CreateWindow
   // nCmdShow: the fourth parameter from WinMain
   ShowWindow(hWnd,
      nCmdShow);
   UpdateWindow(hWnd);
   ```

   아직 구현 하지 않았다면 때문에 표시 된 창 만큼의 콘텐츠가 없는 `WndProc` 함수입니다. 즉, 응용 프로그램 이제는 Windows를 전송 하는 메시지를 아직 처리 되지 않습니다.

1. 메시지를 처리 하려면 먼저 Windows에서 보내는 메시지를 수신 메시지 루프를 추가 합니다. 응용 프로그램 메시지를 받으면이 루프가 디스패치합니다 프로그램 `WndProc` 처리할 함수. 메시지 루프는 다음 코드와 유사합니다.

   ```cpp
   MSG msg;
   while (GetMessage(&msg, NULL, 0, 0))
   {
      TranslateMessage(&msg);
      DispatchMessage(&msg);
   }

   return (int) msg.wParam;
   ```

   메시지 루프의 구조 및 함수에 대한 자세한 내용은 [MSG](/windows/desktop/api/winuser/ns-winuser-msg), [GetMessage](/windows/desktop/api/winuser/nf-winuser-getmessage), [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage)및 [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage)를 참조하세요.

   이때 `WinMain` 함수는 다음 코드와 유사합니다.

   ```cpp
   int WINAPI WinMain(HINSTANCE hInstance,
                      HINSTANCE hPrevInstance,
                      LPSTR lpCmdLine,
                      int nCmdShow)
   {
      WNDCLASSEX wcex;

      wcex.cbSize = sizeof(WNDCLASSEX);
      wcex.style          = CS_HREDRAW | CS_VREDRAW;
      wcex.lpfnWndProc    = WndProc;
      wcex.cbClsExtra     = 0;
      wcex.cbWndExtra     = 0;
      wcex.hInstance      = hInstance;
      wcex.hIcon          = LoadIcon(hInstance, IDI_APPLICATION);
      wcex.hCursor        = LoadCursor(NULL, IDC_ARROW);
      wcex.hbrBackground  = (HBRUSH)(COLOR_WINDOW+1);
      wcex.lpszMenuName   = NULL;
      wcex.lpszClassName  = szWindowClass;
      wcex.hIconSm        = LoadIcon(wcex.hInstance, IDI_APPLICATION);

      if (!RegisterClassEx(&wcex))
      {
         MessageBox(NULL,
            _T("Call to RegisterClassEx failed!"),
            _T("Windows Desktop Guided Tour"),
            NULL);

         return 1;
      }

      // Store instance handle in our global variable
      hInst = hInstance;

      // The parameters to CreateWindow explained:
      // szWindowClass: the name of the application
      // szTitle: the text that appears in the title bar
      // WS_OVERLAPPEDWINDOW: the type of window to create
      // CW_USEDEFAULT, CW_USEDEFAULT: initial position (x, y)
      // 500, 100: initial size (width, length)
      // NULL: the parent of this window
      // NULL: this application dows not have a menu bar
      // hInstance: the first parameter from WinMain
      // NULL: not used in this application
      HWND hWnd = CreateWindow(
         szWindowClass,
         szTitle,
         WS_OVERLAPPEDWINDOW,
         CW_USEDEFAULT, CW_USEDEFAULT,
         500, 100,
         NULL,
         NULL,
         hInstance,
         NULL
      );

      if (!hWnd)
      {
         MessageBox(NULL,
            _T("Call to CreateWindow failed!"),
            _T("Windows Desktop Guided Tour"),
            NULL);

         return 1;
      }

      // The parameters to ShowWindow explained:
      // hWnd: the value returned from CreateWindow
      // nCmdShow: the fourth parameter from WinMain
      ShowWindow(hWnd,
         nCmdShow);
      UpdateWindow(hWnd);

      // Main message loop:
      MSG msg;
      while (GetMessage(&msg, NULL, 0, 0))
      {
         TranslateMessage(&msg);
         DispatchMessage(&msg);
      }

      return (int) msg.wParam;
   }
   ```

### <a name="to-add-functionality-to-the-wndproc-function"></a>WndProc 함수에 기능을 추가하려면

1. `WndProc` 함수에서 응용 프로그램이 받는 메시지를 처리하게 하려면 switch 문을 구현합니다.

   하나의 중요 한 메시지를 처리 하는 합니다 [WM_PAINT](/windows/desktop/gdi/wm-paint) 메시지입니다. 응용 프로그램이 수신 된 `WM_PAINT` 표시 된 창에 메시지를 업데이트 해야 합니다. 응용 프로그램에 이러한 이벤트가 발생할 때 알 수 없습니다 및 사용자 창을 이동 하 여 사용자의 창 앞에 다음 이동 위치로 다시 이벤트가 발생할 수 있습니다. Windows만 알고 사용 하 여 알려 하므로 `WM_PAINT`합니다. 창이 처음 표시 되 면 모두 업데이트 되어야 합니다.

   `WM_PAINT` 메시지를 처리하려면 먼저 [BeginPaint](/windows/desktop/api/winuser/nf-winuser-beginpaint)를 호출하고, 모든 논리를 처리하여 창에 텍스트, 단추 및 기타 컨트롤을 배치하고, [EndPaint](/windows/desktop/api/winuser/nf-winuser-endpaint)를 호출합니다. 응용 프로그램에 대 한 시작 호출과 종료 호출 간의 논리 "Hello, Windows desktop!" 문자열을 표시 하는 것입니다. 다음 코드에서 [TextOut](/windows/desktop/api/wingdi/nf-wingdi-textouta) 함수는 문자열을 표시하는 데 사용됩니다.

   ```cpp
   PAINTSTRUCT ps;
   HDC hdc;
   TCHAR greeting[] = _T("Hello, Windows desktop!");

   switch (message)
   {
   case WM_PAINT:
      hdc = BeginPaint(hWnd, &ps);

      // Here your application is laid out.
      // For this introduction, we just print out "Hello, Windows desktop!"
      // in the top left corner.
      TextOut(hdc,
         5, 5,
         greeting, _tcslen(greeting));
      // End application-specific layout section.

      EndPaint(hWnd, &ps);
      break;
   }
   ```

   `HDC` 코드의 그래픽 하위 시스템을 사용 하 여 통신 하도록 응용 프로그램을 사용 하도록 설정 하려면 Windows를 사용 하는 데이터 구조는 장치 컨텍스트에 대 한 핸들입니다. 합니다 `BeginPaint` 및 `EndPaint` 함수 적합 처럼 응용 프로그램 및 필요한 것 보다 더 이상에 대 한 장치 컨텍스트를 사용 하지 않습니다. 함수 도움말 make 그래픽 하위 시스템은 다른 응용 프로그램에서 사용할 수 있습니다.

1. 응용 프로그램이 일반적으로 많은 기타 메시지를 처리 예를 들어 [WM_CREATE](/windows/desktop/winmsg/wm-create) 창을 처음 만들어질 때와 [WM_DESTROY](/windows/desktop/winmsg/wm-destroy) 창이 닫힐 때. 다음 코드에서는 기본적인 전체 `WndProc` 함수를 보여 줍니다.

   ```cpp
   LRESULT CALLBACK WndProc(HWND hWnd, UINT message, WPARAM wParam, LPARAM lParam)
   {
      PAINTSTRUCT ps;
      HDC hdc;
      TCHAR greeting[] = _T("Hello, Windows desktop!");

      switch (message)
      {
      case WM_PAINT:
         hdc = BeginPaint(hWnd, &ps);

         // Here your application is laid out.
         // For this introduction, we just print out "Hello, Windows desktop!"
         // in the top left corner.
         TextOut(hdc,
            5, 5,
            greeting, _tcslen(greeting));
         // End application specific layout section.

         EndPaint(hWnd, &ps);
         break;
      case WM_DESTROY:
         PostQuitMessage(0);
         break;
      default:
         return DefWindowProc(hWnd, message, wParam, lParam);
         break;
      }

      return 0;
   }
   ```

## <a name="build-the-code"></a>코드 작성

앞서 말한 대로 작업 응용 프로그램에 대 한 전체 코드는 다음과 같습니다.

### <a name="to-build-this-example"></a>이 예제를 빌드하려면

1. 에 입력 하면 코드 삭제 *HelloWindowsDesktop.cpp* 편집기에서. 이 예제 코드를 복사한 후 붙여 넣습니다 *HelloWindowsDesktop.cpp*:

   ```cpp
   // HelloWindowsDesktop.cpp
   // compile with: /D_UNICODE /DUNICODE /DWIN32 /D_WINDOWS /c

   #include <windows.h>
   #include <stdlib.h>
   #include <string.h>
   #include <tchar.h>

   // Global variables

   // The main window class name.
   static TCHAR szWindowClass[] = _T("DesktopApp");

   // The string that appears in the application's title bar.
   static TCHAR szTitle[] = _T("Windows Desktop Guided Tour Application");

   HINSTANCE hInst;

   // Forward declarations of functions included in this code module:
   LRESULT CALLBACK WndProc(HWND, UINT, WPARAM, LPARAM);

   int CALLBACK WinMain(
      _In_ HINSTANCE hInstance,
      _In_ HINSTANCE hPrevInstance,
      _In_ LPSTR     lpCmdLine,
      _In_ int       nCmdShow
   )
   {
      WNDCLASSEX wcex;

      wcex.cbSize = sizeof(WNDCLASSEX);
      wcex.style          = CS_HREDRAW | CS_VREDRAW;
      wcex.lpfnWndProc    = WndProc;
      wcex.cbClsExtra     = 0;
      wcex.cbWndExtra     = 0;
      wcex.hInstance      = hInstance;
      wcex.hIcon          = LoadIcon(hInstance, IDI_APPLICATION);
      wcex.hCursor        = LoadCursor(NULL, IDC_ARROW);
      wcex.hbrBackground  = (HBRUSH)(COLOR_WINDOW+1);
      wcex.lpszMenuName   = NULL;
      wcex.lpszClassName  = szWindowClass;
      wcex.hIconSm        = LoadIcon(wcex.hInstance, IDI_APPLICATION);

      if (!RegisterClassEx(&wcex))
      {
         MessageBox(NULL,
            _T("Call to RegisterClassEx failed!"),
            _T("Windows Desktop Guided Tour"),
            NULL);

         return 1;
      }

      // Store instance handle in our global variable
      hInst = hInstance;

      // The parameters to CreateWindow explained:
      // szWindowClass: the name of the application
      // szTitle: the text that appears in the title bar
      // WS_OVERLAPPEDWINDOW: the type of window to create
      // CW_USEDEFAULT, CW_USEDEFAULT: initial position (x, y)
      // 500, 100: initial size (width, length)
      // NULL: the parent of this window
      // NULL: this application does not have a menu bar
      // hInstance: the first parameter from WinMain
      // NULL: not used in this application
      HWND hWnd = CreateWindow(
         szWindowClass,
         szTitle,
         WS_OVERLAPPEDWINDOW,
         CW_USEDEFAULT, CW_USEDEFAULT,
         500, 100,
         NULL,
         NULL,
         hInstance,
         NULL
      );

      if (!hWnd)
      {
         MessageBox(NULL,
            _T("Call to CreateWindow failed!"),
            _T("Windows Desktop Guided Tour"),
            NULL);

         return 1;
      }

      // The parameters to ShowWindow explained:
      // hWnd: the value returned from CreateWindow
      // nCmdShow: the fourth parameter from WinMain
      ShowWindow(hWnd,
         nCmdShow);
      UpdateWindow(hWnd);

      // Main message loop:
      MSG msg;
      while (GetMessage(&msg, NULL, 0, 0))
      {
         TranslateMessage(&msg);
         DispatchMessage(&msg);
      }

      return (int) msg.wParam;
   }

   //  FUNCTION: WndProc(HWND, UINT, WPARAM, LPARAM)
   //
   //  PURPOSE:  Processes messages for the main window.
   //
   //  WM_PAINT    - Paint the main window
   //  WM_DESTROY  - post a quit message and return
   LRESULT CALLBACK WndProc(HWND hWnd, UINT message, WPARAM wParam, LPARAM lParam)
   {
      PAINTSTRUCT ps;
      HDC hdc;
      TCHAR greeting[] = _T("Hello, Windows desktop!");

      switch (message)
      {
      case WM_PAINT:
         hdc = BeginPaint(hWnd, &ps);

         // Here your application is laid out.
         // For this introduction, we just print out "Hello, Windows desktop!"
         // in the top left corner.
         TextOut(hdc,
            5, 5,
            greeting, _tcslen(greeting));
         // End application-specific layout section.

         EndPaint(hWnd, &ps);
         break;
      case WM_DESTROY:
         PostQuitMessage(0);
         break;
      default:
         return DefWindowProc(hWnd, message, wParam, lParam);
         break;
      }

      return 0;
   }
   ```

1. **빌드** 메뉴에서 **솔루션 빌드**를 선택합니다. 컴파일 결과에 표시 해야 합니다 **출력** Visual Studio의 창.

   ![DesktopApp 프로젝트를 빌드할](../build/media/desktop-app-project-build-150.gif "DesktopApp 프로젝트 빌드")

1. 응용 프로그램을 실행 하려면 키를 누릅니다 **F5**합니다. "Hello, Windows desktop!" 텍스트가 있는 창 디스플레이의 왼쪽 위에 표시됩니다.

   ![DesktopApp 프로젝트 실행](../build/media/desktop-app-project-run-157.png "DesktopApp 프로젝트 실행")

지금까지 이 연습을 완료 하 고 기존 Windows 데스크톱 응용 프로그램을 구축 했습니다.

## <a name="see-also"></a>참고자료

[Windows 데스크톱 응용 프로그램](../windows/windows-desktop-applications-cpp.md)