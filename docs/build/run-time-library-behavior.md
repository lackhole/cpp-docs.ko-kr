---
title: Dll 및 시각적 개체 C++ 런타임 라이브러리 동작
ms.date: 11/04/2016
f1_keywords:
- _DllMainCRTStartup
- CRT_INIT
helpviewer_keywords:
- DLLs [C++], entry point function
- process detach [C++]
- process attach [C++]
- DLLs [C++], run-time library behavior
- DllMain function
- _CRT_INIT macro
- _DllMainCRTStartup method
- run-time [C++], DLL startup sequence
- DLLs [C++], startup sequence
ms.assetid: e06f24ab-6ca5-44ef-9857-aed0c6f049f2
ms.openlocfilehash: ea970f010e86d655963485339c48b8f7d36d6270
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62314795"
---
# <a name="dlls-and-visual-c-run-time-library-behavior"></a>Dll 및 시각적 개체 C++ 런타임 라이브러리 동작

시각적 개체를 사용 하 여 동적 연결 라이브러리 (DLL)를 빌드할 때 C++를 기본적으로 링커는 시각적 개체를 포함 C++ 런타임 라이브러리 (VCRuntime). 초기화 하 고 C를 종료 하는 데 필요한 코드를 포함 하는 VCRuntime /C++ 실행 합니다. VCRuntime 코드 제공 이라는 내부 DLL 진입점 함수를 DLL로 연결 하는 경우 `_DllMainCRTStartup` Windows OS 메시지 DLL에 연결 또는 스레드 또는 프로세스에서 분리를 처리 하는 합니다. `_DllMainCRTStartup` 함수 C 런타임 라이브러리 (CRT) 초기화 및 종료를 설정 하는 스택 버퍼 보안과 같은 필수 작업을 수행 하 고 정적 및 전역 개체에 대 한 생성자 및 소멸자를 호출 합니다. `_DllMainCRTStartup` 또한 호출 자체 초기화 및 종료 하는 데 WinRT, MFC 및 ATL 등의 기타 라이브러리에 대 한 함수를 연결 합니다. 이 초기화, CRT 및 다른 라이브러리와 정적 변수를 없이 초기화 되지 않은 상태로 유지할 수 됩니다. 동일한 VCRuntime 내부 초기화 및 종료 루틴에는 DLL을 정적으로 연결 된 CRT 또는 동적으로 연결 된 CRT DLL 사용 이라고 합니다.

## <a name="default-dll-entry-point-dllmaincrtstartup"></a>기본 DLL 항목 지점 _DllMainCRTStartup

Windows에서 Dll을 모두 일반적으로 호출 하는 선택적 진입점 함수를 포함할 수 있습니다 `DllMain`, 초기화 및 종료 시 모두 호출 합니다. 이렇게 하면 할당 하거나 필요에 따라 추가 리소스를 해제할 수 있습니다. 네 가지 상황에서 진입점 함수를 호출 하는 Windows: 프로세스 연결, 분리 프로세스, 스레드 연결 및 스레드 분리 합니다. 사용 하는 응용 프로그램을 로드 또는 응용 프로그램이 런타임 시 DLL을 요청 하는 경우 DLL을 프로세스 주소 공간에 로드 되 면 운영 체제는 별도 DLL 데이터 복사본을 만듭니다. 이 이라고 *프로세스 연결*합니다. *스레드 연결* 에서 DLL을 로드 하는 프로세스는 새 스레드를 만들 때 발생 합니다. *스레드를 분리* 스레드가 종료 될 때 발생 하 고 *프로세스 분리* DLL 더 이상 필요 하 고 응용 프로그램에 의해 해제 될 때입니다. 이러한 각 이벤트를 전달에 대 한 DLL 진입점으로 별도 호출 하는 운영 체제를 *이유* 각 이벤트 유형에 대 한 인수입니다. 예를 들어 OS 보냅니다 `DLL_PROCESS_ATTACH` 으로 *이유* 인수 프로세스 신호를 연결 합니다.

호출 하는 진입점 함수를 제공 하는 VCRuntime 라이브러리 `_DllMainCRTStartup` 기본 초기화 및 종료 작업을 처리할 수 있습니다. 프로세스에 연결 된 `_DllMainCRTStartup` 함수 버퍼 보안 검사 설정, CRT 및 다른 라이브러리를 초기화, 런타임 형식 정보를 초기화, 초기화 및 정적 및 로컬이 아닌 데이터에 대 한 생성자를 호출, 스레드 로컬 저장소를 초기화 합니다. 에서 각 연결에 대 한 내부 정적 카운터를 증가 시키고 다음 호출 하는 사용자 또는 라이브러리-제공 `DllMain`합니다. 프로세스 분리, 함수 역순에서이 단계를 거칩니다. 호출한 `DllMain`내부 카운터를 감소 시킵니다 소멸자를 호출, 호출 CRT 종료 함수와 등록 `atexit` 함수 및 다른 라이브러리의 종료를에 알립니다. 첨부 파일 카운터가 0이 되 면 하는 경우 함수 반환 `FALSE` 에 알리기 위해 Windows DLL을 로드할 수는 있습니다. `_DllMainCRTStartup` 함수도 호출 해야 하는 동안 스레드 연결 및 스레드 분리 합니다. 이러한 경우 VCRuntime 코드 추가 초기화 또는 자체적으로 종료 하지 않으며 호출 `DllMain` 함께 메시지를 전달 하도록 합니다. 경우 `DllMain` 반환 `FALSE` 프로세스에서 연결 오류 신호 `_DllMainCRTStartup` 호출 `DllMain` 다시 전달 `DLL_PROCESS_DETACH` 로 *이유* 인수 다음의 rest를 통해 이동 합니다 종료 프로세스입니다.

시각적 개체에 대 한 Dll을 빌드할 때 C++를 기본 진입점 `_DllMainCRTStartup` 제공한 VCRuntime에 자동으로 연결 합니다. 사용 하 여 DLL에 대 한 진입점 함수를 지정 해야 합니다 [/ENTRY (진입점 기호)](reference/entry-entry-point-symbol.md) 링커 옵션입니다.

> [!NOTE]
> /ENTRY를 사용 하 여 DLL에 대 한 다른 진입점 함수를 지정할 수 있지만: 링커 옵션을 권장 하지는 않습니다를 모든 진입점 함수는 있으므로 `_DllMainCRTStartup` 같은 순서로 수행 합니다. VCRuntime 해당 동작을 중복 할 수 있는 함수를 제공 합니다. 예를 들어, 호출할 수 있습니다 [__security_init_cookie](../c-runtime-library/reference/security-init-cookie.md) 즉시 프로세스를 지원 하기 위해 연결 된 [/GS (버퍼 보안 검사)](reference/gs-buffer-security-check.md) 버퍼 옵션을 선택 합니다. 호출할 수 있습니다는 `_CRT_INIT` 함수에 DLL 초기화 및 종료 함수의 나머지 부분을 수행 하는 항목 지점 함수와 동일한 매개 변수를 전달 합니다.

<a name="initializing-a-dll"></a>

## <a name="initialize-a-dll"></a>DLL 초기화

DLL에는 해당 DLL이 로드 될 때 실행 되어야 하는 초기화 코드가 있을 수 있습니다. 사용자 DLL 초기화 및 종료 함수를 수행 하는 순서 대로 `_DllMainCRTStartup` 라는 함수를 호출 `DllMain` 제공할 수 있는 합니다. 프로그램 `DllMain` DLL 진입점에 대 한 필수 시그니처가 있어야 합니다. 기본 진입점 함수 `_DllMainCRTStartup` 호출 `DllMain` 동일한 매개 변수를 사용 하 여 Windows에서 전달 합니다. 기본적으로 제공 하지 않는 경우는 `DllMain` 함수를 Visual C++ 에서 제공 하 고 연결에 있도록 `_DllMainCRTStartup` 항상 호출 하는 합니다. 이 DLL 초기화할 필요가 없는 경우 별도 DLL을 빌드할 때 수행할 작업을 의미 합니다.

에 사용 되는 시그니처 `DllMain`:

```cpp
#include <windows.h>

extern "C" BOOL WINAPI DllMain (
    HINSTANCE const instance,  // handle to DLL module
    DWORD     const reason,    // reason for calling function
    LPVOID    const reserved); // reserved
```

일부 라이브러리를 래핑하는 `DllMain` 를 함수입니다. 예를 들어, 기본 MFC DLL에서 구현 된 `CWinApp` 개체의 `InitInstance` 및 `ExitInstance` 초기화 및 DLL에 필요한 종료를 수행 하는 멤버 함수입니다. 자세한 내용은 참조는 [일반적인 MFC Dll 초기화](#initializing-regular-dlls) 섹션.

> [!WARNING]
> 수행할 수 있는 안전 하 게 한 DLL 진입점에서 중요 한 제한이 있습니다. 참조 [일반 모범 사례](/windows/desktop/Dlls/dynamic-link-library-best-practices) 호출 안전 하지 않은 특정 Windows Api에 대 한 `DllMain`합니다. 필요 하다는 가장 간단한 초기화 한 다음 DLL에 대 한 초기화 함수에서 수행 합니다. 함수 호출 하 여 초기화 한 후 응용 프로그램을 요구할 수 있습니다 `DllMain` 에 실행 하 고 하기 전에 다른 함수를 호출할 dll에서입니다.

<a name="initializing-non-mfc-dlls"></a>

### <a name="initialize-ordinary-non-mfc-dlls"></a>일반 (MFC 이외) Dll 초기화

VCRuntime 제공을 사용 하는 일반적인 (MFC 이외) Dll에서 직접 초기화를 수행 하도록 `_DllMainCRTStartup` 진입점 DLL 소스 코드 라는 함수를 포함 해야 합니다 `DllMain`합니다. 다음 코드의 정의 보여 주는 기본 형식을 제공 `DllMain` 다음과 같을 수 있습니다.

```cpp
#include <windows.h>

extern "C" BOOL WINAPI DllMain (
    HINSTANCE const instance,  // handle to DLL module
    DWORD     const reason,    // reason for calling function
    LPVOID    const reserved)  // reserved
{
    // Perform actions based on the reason for calling.
    switch (reason)
    {
    case DLL_PROCESS_ATTACH:
        // Initialize once for each new process.
        // Return FALSE to fail DLL load.
        break;

    case DLL_THREAD_ATTACH:
        // Do thread-specific initialization.
        break;

    case DLL_THREAD_DETACH:
        // Do thread-specific cleanup.
        break;

    case DLL_PROCESS_DETACH:
        // Perform any necessary cleanup.
        break;
    }
    return TRUE;  // Successful DLL_PROCESS_ATTACH.
}
```

> [!NOTE]
> 이전 Windows SDK 설명서는 DLL 진입점 함수가의 실제 이름 링커 /ENTRY 옵션을 사용 하 여 명령줄에 지정 해야 표시 됩니다. 시각적 개체를 사용 하 여 C++, 진입점 함수의 이름은 /ENTRY 옵션을 사용할 필요가 없습니다 `DllMain`합니다. 사실, /ENTRY 옵션 및 이름을 사용 하는 경우 프로그램 진입점 것 이외의 함수 `DllMain`, 진입점 함수 호출 동일한 초기화 하는 경우가 아니면 CRT 올바르게 초기화 되지 않습니다 `_DllMainCRTStartup` 수 있습니다.

<a name="initializing-regular-dlls"></a>

### <a name="initialize-regular-mfc-dlls"></a>기본 MFC Dll 초기화

기본 MFC Dll 있으므로 `CWinApp` 개체에 MFC 응용 프로그램과 동일한 위치에서 초기화 및 종료 작업을 수행 해야 이러한:에 `InitInstance` 및 `ExitInstance` dll의 멤버 함수 `CWinApp`-파생 클래스입니다. MFC 제공 하기 때문에 `DllMain` 함수에서 호출한 `_DllMainCRTStartup` 에 대 한 `DLL_PROCESS_ATTACH` 및 `DLL_PROCESS_DETACH`를 작성 하지 말아야 고유한 `DllMain` 함수입니다. MFC에서 제공한 `DllMain` 함수 호출 `InitInstance` DLL이 로드 시간과 호출 `ExitInstance` DLL 언로드되기 전에 합니다.

기본 MFC DLL를 추적할 수 여러 스레드를 호출 하 여 [TlsAlloc](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-tlsalloc) 하 고 [TlsGetValue](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-tlsgetvalue) 에서 해당 `InitInstance` 함수입니다. 이러한 함수는 스레드 관련 데이터를 추적 하는 DLL을 허용 합니다.

동적으로 MFC에 링크를 모든 MFC OLE, MFC 데이터베이스 (또는 DAO)를 사용 하는 경우 각각의 MFC 소켓 지원 MFC 확장명 Dll MFCO 디버그 하는 사용자가 기본 MFC DLL에서*버전*D.dll, MFCD*버전*D.dll을 및 MFCN*버전*D.dll (여기서 *버전* 은 버전 번호)에서 자동으로 연결 됩니다. 각 기본 MFC DLL에서 사용 중인이 Dll에 대 한 다음 미리 정의 된 초기화 함수 중 하나를 호출 해야 `CWinApp::InitInstance`합니다.

|MFC 지원 유형|초기화 함수 호출|
|-------------------------|-------------------------------------|
|MFC OLE (MFCO*버전*D.dll)|`AfxOleInitModule`|
|MFC 데이터베이스 (MFCD*버전*D.dll)|`AfxDbInitModule`|
|MFC 소켓 (MFCN*버전*D.dll)|`AfxNetInitModule`|

<a name="initializing-extension-dlls"></a>

### <a name="initialize-mfc-extension-dlls"></a>MFC 확장명 Dll 초기화

없으므로 MFC 확장명 Dll을 `CWinApp`-파생 (마찬가지로 기본 MFC Dll) 개체를 초기화 및 종료 코드를 추가 해야 합니다 `DllMain` MFC DLL 마법사에서 생성 하는 함수입니다.

마법사는 MFC 확장명 Dll에 대 한 다음 코드를 제공합니다. 코드에서 `PROJNAME` 자리 표시자 프로젝트의 이름입니다.

```cpp
#include "stdafx.h"
#include <afxdllx.h>

#ifdef _DEBUG
#define new DEBUG_NEW
#undef THIS_FILE
static char THIS_FILE[] = __FILE__;
#endif
static AFX_EXTENSION_MODULE PROJNAMEDLL = { NULL, NULL };

extern "C" int APIENTRY
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)
{
   if (dwReason == DLL_PROCESS_ATTACH)
   {
      TRACE0("PROJNAME.DLL Initializing!\n");

      // MFC extension DLL one-time initialization
      AfxInitExtensionModule(PROJNAMEDLL,
                                 hInstance);

      // Insert this DLL into the resource chain
      new CDynLinkLibrary(Dll3DLL);
   }
   else if (dwReason == DLL_PROCESS_DETACH)
   {
      TRACE0("PROJNAME.DLL Terminating!\n");
   }
   return 1;   // ok
}
```

새로 만들 `CDynLinkLibrary` 초기화 하는 동안 개체를 사용 하는 MFC 확장명 DLL이 내보내기 `CRuntimeClass` 개체 또는 클라이언트 응용 프로그램 리소스입니다.

초기화 함수를 만든 MFC 확장 DLL에서 하나 이상의 기본 MFC Dll을 사용 하려는 경우 내보내야를 `CDynLinkLibrary` 개체입니다. 각 MFC 확장명 DLL을 사용 하는 기본 MFC Dll에서 함수를 호출 합니다. 이 초기화 함수를 호출 하는 적절 한 위치를 `InitInstance` 기본 MFC DLL의 멤버 함수 `CWinApp`-MFC 확장 DLL의 내보낸 클래스나 함수 중 하나를 사용 하기 전에 개체를 파생 합니다.

`DllMain` 는 MFC DLL 마법사 생성에 대 한 호출 `AfxInitExtensionModule` 모듈의 런타임 클래스를 캡처합니다 (`CRuntimeClass` 구조)의 개체 팩터리 뿐만 아니라 (`COleObjectFactory` 개체) 사용 될 때를 `CDynLinkLibrary` 개체가 만들어집니다. 반환 값을 확인 해야 `AfxInitExtensionModule`에서 반환 값이 0 이면 `AfxInitExtensionModule`에서 0을 반환 하면 `DllMain` 함수.

MFC 확장 DLL에 실행 파일에 명시적으로 연결 되는 경우 (실행 호출을 의미 `AfxLoadLibrary` DLL에 연결할)에 대 한 호출을 추가 해야 `AfxTermExtensionModule` 에서 `DLL_PROCESS_DETACH`합니다. 이 함수에서는 각 프로세스 MFC 확장명 DLL에서에서 분리 하는 경우에 MFC 확장명 DLL 정리 하는 MFC (때나의 결과로 DLL이 언로드되어 프로세스가 종료 될 때 발생 한 `AfxFreeLibrary` 호출). 응용 프로그램에 대 한 호출 MFC 확장 DLL을 암시적으로 링크 되는 경우 `AfxTermExtensionModule` 필요 하지 않습니다.

링크 MFC 확장명 Dll 명시적으로 호출 해야 하는 응용 프로그램 `AfxTermExtensionModule` DLL을 해제 하는 경우. 또한 사용 해야 `AfxLoadLibrary` 하 고 `AfxFreeLibrary` (Win32 함수 대신 `LoadLibrary` 및 `FreeLibrary`) 여러 스레드를 사용 하면 응용 프로그램입니다. 사용 하 여 `AfxLoadLibrary` 고 `AfxFreeLibrary` 되도록 MFC 확장 DLL을 로드 하거나 언로드할 전역 MFC 상태가 손상 되지 않습니다 때 실행 되는 시작 및 종료 코드입니다.

MFCx0.dll는 시간을 기준으로 완전히 초기화 되기 때문에 `DllMain` 는 호출 메모리를 할당 하 MFC 함수 내에서 호출 `DllMain` (달리 16 비트 버전의 MFC).

확장명 Dll 처리할 수 있습니다 처리 하 여 다중 스레딩 합니다 `DLL_THREAD_ATTACH` 및 `DLL_THREAD_DETACH` 의 경우는 `DllMain` 함수입니다. 이러한 경우에 전달 됩니다 `DllMain` 스레드 연결 하 고 DLL에서 분리 하는 경우. 호출 [TlsAlloc](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-tlsalloc) 스레드 로컬 저장소 (TLS) DLL에 연결 된 모든 스레드에 대 한 인덱스를 유지 하기 위해 DLL을 사용 하면 DLL이 연결 하는 경우.

Afxdllx.h 헤더 파일에 대 한 정의 같은 MFC 확장명 Dll에서 사용 되는 구조에 대 한 특별 한 정의가 포함 되어 있습니다 `AFX_EXTENSION_MODULE` 고 `CDynLinkLibrary`입니다. MFC 확장 DLL에에서이 헤더 파일을 포함 해야 합니다.

> [!NOTE]
>  정의 아니고 중 하나를 해제 하는 중요 한 것은 `_AFX_NO_XXX` Stdafx.h에서 매크로입니다. 이러한 매크로 여부는 특정 대상 플랫폼 기능을 지원 하는지 여부를 확인 하는 용도로 존재 합니다. 이러한 매크로 확인 하려면 프로그램을 작성할 수 있습니다 (예를 들어 `#ifndef _AFX_NO_OLE_SUPPORT`), 있지만 프로그램 해야 하지 정의 하거나 이러한 매크로 정의 합니다.

다중 스레딩을 처리에 포함 된 샘플 초기화 함수 [를 사용 하 여 스레드 로컬 저장소에는 동적 링크 라이브러리](/windows/desktop/Dlls/using-thread-local-storage-in-a-dynamic-link-library) Windows SDK에 있습니다. 이 샘플 이라는 진입점 함수를 포함 하는 참고 `LibMain`,이 함수 이름을 지정 해야 하지만 `DllMain` MFC 및 C 런타임 라이브러리와 함께 작동 하도록 합니다.

## <a name="see-also"></a>참고자료

[Visual C++의 DLL](dlls-in-visual-cpp.md)<br/>
[DllMain 진입점](/windows/desktop/Dlls/dllmain)<br/>
[동적 연결 라이브러리에 대 한 유용한 정보](/windows/desktop/Dlls/dynamic-link-library-best-practices)
