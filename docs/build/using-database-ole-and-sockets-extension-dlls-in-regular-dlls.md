---
title: 기본 MFC Dll에서 데이터베이스, OLE 및 소켓 MFC 확장명 Dll 사용
ms.date: 11/04/2016
helpviewer_keywords:
- DLLs [C++], initializing
- DLLs [C++], extension
- DLLs [C++], regular
ms.assetid: 9f1d14a7-9e2a-4760-b3b6-db014fcdb7ff
ms.openlocfilehash: d08822a04abe5a01883ad8aa1bd6d94269e810cc
ms.sourcegitcommit: faa42c8a051e746d99dcebe70fd4bbaf3b023ace
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2019
ms.locfileid: "57807977"
---
# <a name="using-database-ole-and-sockets-mfc-extension-dlls-in-regular-mfc-dlls"></a>기본 MFC Dll에서 데이터베이스, OLE 및 소켓 MFC 확장명 Dll 사용

MFC 확장명 DLL에 연결 하지는 경우에 MFC 확장 된 기본 MFC DLL에서 DLL을 사용 하는 경우는 **그렇지 않으면 CDynLinkLibrary** 체인 개체는 기본 MFC DLL의 관련된 문제 집합이 하나 이상에 실행할 수 있습니다. MFC 데이터베이스, OLE 및 소켓의 디버그 버전을 지원 하기 때문에 Dll이 MFC 확장명 Dll로 구현 됩니다, 그리고 사용 하지 않는 명시적으로 사용자 고유의 MFC 확장명 Dll의 경우에 이러한 MFC를 사용 하는 경우 유사한 문제 기능을 표시 될 수 있습니다. 일부 현상은 다음과 같습니다.

- 클래스 형식의 개체를 deserialize 하는 동안 정의 되어 있는 경우 MFC 확장 DLL 메시지에에서 "경고: CYourClass 보관 파일에서 로드할 수 없습니다. 클래스 정의 되지 않았습니다. " 직렬화에 실패 하면 추적 디버그 창 및 개체에 표시 됩니다.

- 잘못 된 클래스를 나타내는 예외가 throw 될 수 있습니다.

- MFC 확장명 DLL에에서 저장 된 리소스 때문에 로드 하지 못했습니다 `AfxFindResourceHandle` 반환 **NULL** 또는 잘못 된 리소스 핸들입니다.

- `DllGetClassObject`를 `DllCanUnloadNow`, 및 `UpdateRegistry`, `Revoke`, `RevokeAll`, 및 `RegisterAll` 멤버 함수의 `COleObjectFactory` MFC 확장명 DLL에에서 정의 된 클래스 팩터리를 찾지 못했습니다.

- `AfxDoForAllClasses` MFC 확장명 DLL의에서 모든 클래스에 대 한 작동 하지 않습니다.

- 표준 MFC 데이터베이스, 소켓 또는 OLE 리소스 로드 하지 못했습니다. 예를 들어 **AfxLoadString**(**AFX_IDP_SQL_CONNECT_FAIL**) 기본 MFC DLL은 MFC 데이터베이스 클래스를 사용 하 여 제대로 하는 경우에 빈 문자열을 반환 합니다.

이러한 문제에 솔루션을 만들고 MFC 확장명 DLL 만드는에서 초기화 함수를 내보내려면은 **그렇지 않으면 CDynLinkLibrary** 개체입니다. MFC 확장명 DLL을 사용 하는 각 기본 MFC DLL에서 정확히 한 번이 초기화 함수를 호출 합니다.

## <a name="mfc-ole-mfc-database-or-dao-or-mfc-sockets-support"></a>OLE MFC, MFC 데이터베이스 (또는 DAO) 또는 MFC 소켓 지원

MFC OLE, MFC 데이터베이스 (또는 DAO)를 사용 하는 경우 각각에 기본 MFC DLL에서 MFC 소켓 지원 MFC 디버그 MFC 확장명 Dll MFCOxxD.dll, MFCDxxD.dll, 및 MFCNxxD.dll (여기서 xx는 버전 번호임) 자동으로 연결 됩니다. 각 사용 중인이 Dll에 대 한 미리 정의 된 초기화 함수를 호출 해야 합니다.

데이터베이스 지원에 대 한 호출을 추가 `AfxDbInitModule` 을 기본 MFC DLL의 `CWinApp::InitInstance` 함수입니다. 이 호출은 기본 클래스를 호출 하기 전에 나 서 MFCDxxD.dll에 액세스 하는 코드를 추가 해야 합니다. 이 함수는 매개 변수를 사용 하 고 void를 반환 합니다.

OLE 지원에 대 한 호출을 추가 `AfxOleInitModule` 을 기본 MFC DLL의 `CWinApp::InitInstance`합니다. 합니다 **COleControlModule InitInstance** 함수 호출 `AfxOleInitModule` 이미 사용 하 고 OLE 컨트롤을 작성 하는 경우 `COleControlModule`,이 호출을 추가 하면 안 `AfxOleInitModule`합니다.

소켓 지원에 대 한 호출을 추가 `AfxNetInitModule` 을 기본 MFC DLL의 `CWinApp::InitInstance`합니다.

MFC Dll의 릴리스 빌드 및 응용 프로그램 데이터베이스, 소켓에 대 한 별도 Dll을 사용 하지 않거나 OLE 지원 note 합니다. 그러나 릴리스 모드에서 이러한 초기화 함수를 호출 하려면 안전 합니다.

## <a name="cdynlinklibrary-objects"></a>그렇지 않으면 CDynLinkLibrary 개체가

이 항목의 앞부분에 언급 된 작업을 각각 중 MFC를 원하는 값 또는 개체를 검색 해야 합니다. 예를 들어 deserialization 도중 MFC가 적절 한 런타임 클래스를 사용 하 여 보관 파일에 있는 개체와 일치 하도록 모든 현재 사용할 수 있는 런타임 클래스를 통해 검색 해야 합니다.

이러한 검색의 일부로 MFC 사용 중인 모든 MFC 확장 Dll을 통해 여 검색의 체인 **그렇지 않으면 CDynLinkLibrary** 개체입니다. **그렇지 않으면 CDynLinkLibrary** 개체가 생성 하는 동안 체인에 자동으로 연결 하 고 초기화 하는 동안에 각 MFC 확장 DLL에 의해 생성 됩니다. 또한 모든 모듈 (응용 프로그램 또는 기본 MFC DLL)에 자체 체인 **그렇지 않으면 CDynLinkLibrary** 개체입니다.

MFC 확장 DLL에 유선 가져오려면를 **그렇지 않으면 CDynLinkLibrary** 체인을 생성 하도록 해야 합니다는 **그렇지 않으면 CDynLinkLibrary** MFC 확장명 DLL을 사용 하는 모든 모듈의 컨텍스트에서 개체입니다. 따라서 MFC 확장 DLL 기본 MFC Dll에서 사용할 것을 하는 경우 만든 내보낸된 초기화 함수를 제공 해야 합니다는 **그렇지 않으면 CDynLinkLibrary** 개체입니다. MFC 확장을 사용 하는 모든 기본 MFC DLL DLL 내보낸된 초기화 함수를 호출 해야 합니다.

MFC 확장 DLL만 것으로 기본 MFC DLL 되지 MFC 응용 프로그램 (.exe)에서 사용할 경우이 만드는 데 충분 합니다 **그렇지 않으면 CDynLinkLibrary** MFC 확장 DLL의 개체 `DllMain`합니다. MFC DLL 마법사 MFC 확장명 DLL 코드의 용도입니다. MFC 확장 DLL을 암시적으로 로드 하는 경우 `DllMain` 로드 하 고 응용 프로그램이 시작 되기 전에 실행 합니다. 모든 **그렇지 않으면 CDynLinkLibrary** 만들기 MFC DLL을 MFC 응용 프로그램에 대 한 예약 하는 기본 체인에 유선 됩니다.

것이 여러 개 바람직하지 **그렇지 않으면 CDynLinkLibrary** MFC 확장명 DLL를 동적으로 메모리에서 언로드할 수 없는 경우에 특히 하나 모든 체인에서 한 MFC 확장명 DLL에서에서 개체입니다. 모든 모듈에서 초기화 함수가 두 번 이상는 호출 하지 마세요.

## <a name="sample-code"></a>샘플 코드

이 샘플 코드에서는 기본 MFC DLL이 MFC 확장명 DLL에 암시적으로 링크 하 고는 가정 합니다. 기본 MFC DLL을 빌드할 때 MFC 확장 DLL 가져오기 라이브러리 (.lib)에 연결 하면 됩니다.

다음 줄을 MFC 확장명 DLL의 소스 이어야 합니다.

```
// YourExtDLL.cpp:

// standard MFC extension DLL routines
#include "afxdllx.h"

static AFX_EXTENSION_MODULE NEAR extensionDLL = { NULL, NULL };

extern "C" int APIENTRY
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)
{
    if (dwReason == DLL_PROCESS_ATTACH)
    {
        // MFC extension DLL one-time initialization
        if (!AfxInitExtensionModule(extensionDLL, hInstance))
           return 0;
    }
    return 1;   // ok
}

// Exported DLL initialization is run in context of
// application or regular MFC DLL
extern "C" void WINAPI InitYourExtDLL()
{
    // create a new CDynLinkLibrary for this app
    new CDynLinkLibrary(extensionDLL);

    // add other initialization here
}
```

내보내기 해야 합니다 **InitYourExtDLL** 함수입니다. 수행할 수 있습니다 사용 하 여 **__declspec (dllexport)** 또는 같이 DLL의.def 파일:

```
// YourExtDLL.Def:
LIBRARY      YOUREXTDLL
CODE         PRELOAD MOVEABLE DISCARDABLE
DATA         PRELOAD SINGLE
EXPORTS
    InitYourExtDLL
```

호출을 추가 합니다 `InitInstance` 의 멤버는 `CWinApp`-파생 MFC 확장 DLL을 사용 하는 각 기본 MFC DLL 개체:

```
// YourRegularDLL.cpp:

class CYourRegularDLL : public CWinApp
{
public:
    virtual BOOL InitInstance(); // Initialization
    virtual int ExitInstance();  // Termination

    // nothing special for the constructor
    CYourRegularDLL(LPCTSTR pszAppName) : CWinApp(pszAppName) { }
};

BOOL CYourRegularDLL::InitInstance()
{
    // any DLL initialization goes here
    TRACE0("YOUR regular MFC DLL initializing\n");

    // wire any MFC extension DLLs into CDynLinkLibrary chain
    InitYourExtDLL();

    return TRUE;
}
```

### <a name="what-do-you-want-to-do"></a>원하는 작업을 선택하세요.

- [MFC 확장 DLL 초기화](run-time-library-behavior.md#initializing-extension-dlls)

- [기본 MFC Dll 초기화](run-time-library-behavior.md#initializing-regular-dlls)

### <a name="what-do-you-want-to-know-more-about"></a>추가 정보

- [MFC 확장명 DLL](extension-dlls.md)

- [정적으로 MFC에 링크된 기본 MFC DLL](regular-dlls-statically-linked-to-mfc.md)

- [동적으로 MFC에 링크된 기본 MFC DLL](regular-dlls-dynamically-linked-to-mfc.md)

- [DLL의 일부로 MFC 사용](../mfc/tn011-using-mfc-as-part-of-a-dll.md)

- [MFC의 DLL 버전](../mfc/tn033-dll-version-of-mfc.md)

## <a name="see-also"></a>참고자료

[MFC 확장명 DLL](extension-dlls.md)
