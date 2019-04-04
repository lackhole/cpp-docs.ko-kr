---
title: Dll을 관리 하기 위한 함수와 매크로
ms.date: 03/27/2019
helpviewer_keywords:
- module macros in MFC
ms.assetid: 303f4161-cb5e-4099-81ad-acdb11aa60fb
ms.openlocfilehash: b27f8763b60dc7ce3ee074cad1365e7e1de3a7e6
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565427"
---
# <a name="macros-and-functions-for-managing-dlls"></a>Dll을 관리 하기 위한 함수와 매크로

|||
|-|-|
|[AFX_EXT_CLASS](#afx_ext_class)]|클래스를 내보냅니다.|
|[AFX_MANAGE_STATE](#afx_manage_state)|DLL에서 내보낸된 함수를 보호 합니다.|
|[AfxOleInitModule](#afxoleinitmodule)|MFC에 동적으로 연결 된 기본 MFC DLL에서 OLE 지원을 제공 합니다.|
|[AfxNetInitModule](#afxnetinitmodule)|MFC에 동적으로 연결 된 기본 MFC DLL에서 MFC 소켓 지원을 제공 합니다.|
|[AfxGetAmbientActCtx](#afxgetambientactctx)|모듈별 상태 플래그의 현재 상태를 가져옵니다.|
|[AfxGetStaticModuleState](#afxgetstaticmodulestate)|초기화 전에 및/또는 정리 후 이전 모듈 상태를 복원 하려면 모듈 상태를 설정 합니다.|
|[AfxInitExtensionModule](#afxinitextensionmodule)|DLL을 초기화합니다.|
|[AfxSetAmbientActCtx](#afxsetambientactctx)|MFC의 WinSxS 동작에 영향을 주는 모듈별 상태 플래그를 설정 합니다.|
|[AfxTermExtensionModule](#afxtermextensionmodule)|MFC를 DLL에서 각 프로세스 분리 하는 경우 MFC 확장명 DLL 정리할 수 있습니다.|

## <a name="afx_ext_class"></a>  AFX_EXT_CLASS

[MFC 확장명 Dll](../../build/extension-dlls.md) AFX_EXT_CLASS 매크로 사용 하 여 클래스를 내보내려면; 클래스를 가져오려면 매크로 사용 하는 MFC 확장명 DLL에 연결 된 실행 합니다.

### <a name="remarks"></a>설명

AFX_EXT_CLASS 매크로 사용 하 여 MFC 확장명 DLL을 빌드하는 데 사용 된 동일한 헤더 파일은 DLL에 대 한 링크는 실행 파일을 사용 하 여 사용할 수 있습니다.

DLL에 대 한 헤더 파일에서 클래스의 선언에 AFX_EXT_CLASS 키워드를 다음과 같이 추가:

```cpp
class AFX_EXT_CLASS CMyClass : public CDocument
{
// <body of class>
};
```

자세한 내용은 [내보내기 및 가져오기를 사용 하 여 AFX_EXT_CLASS](../../build/exporting-and-importing-using-afx-ext-class.md)합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxv_dll.h

## <a name="afx_manage_state"></a>  AFX_MANAGE_STATE

DLL에서 내보낸된 함수를 보호 하기 위해이 매크로 호출 합니다.

### <a name="syntax"></a>구문

```
AFX_MANAGE_STATE(AFX_MODULE_STATE* pModuleState )
```

### <a name="parameters"></a>매개 변수

*pModuleState*<br/>
에 대 한 포인터는 `AFX_MODULE_STATE` 구조입니다.

### <a name="remarks"></a>설명

이 매크로 호출 하면 *pModuleState* 은 바로의 나머지 부분에 대 한 유효한 모듈 상태 범위를 포함 합니다. 범위를 벗어나면, 유효한 모듈 상태로 자동으로 복원 됩니다.
`AFX_MODULE_STATE` 구조 모듈의 경우 푸시 되거나 팝 되는 모듈 상태의 일부 이므로 전역 데이터를 포함 합니다.

기본적으로 MFC 리소스 템플릿을 로드 하는 기본 응용 프로그램의 리소스 핸들을 사용 합니다. DLL의 대화 상자를 시작 하는 것과 같은 DLL에서 내보낸된 함수를 설정한 경우이 템플릿은 DLL 모듈에서 실제로 저장 됩니다. 사용할 올바른 핸들에 대 한 모듈 상태를 전환 해야 합니다. 함수의 시작 부분에 다음 코드를 추가 하 여이 수행할 수 있습니다.

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));
```

반환 된 상태와 현재 모듈 상태 서로 바뀝니다 [AfxGetStaticModuleState](#afxgetstaticmodulestate) 현재 범위의 끝까지 합니다.

MFC 모듈 상태에 대 한 자세한 내용은 "관리는 데이터의 MFC 모듈 상태"를 참조 하세요 [새 문서 만들기, Windows, 뷰와](../creating-new-documents-windows-and-views.md) 하 고 [기술 참고 58](../tn058-mfc-module-state-implementation.md)합니다.

> [!NOTE]
>  사용 하 여 MFC 활성화 컨텍스트는 어셈블리를 만들 때 [AfxWinInit](application-information-and-management.md#afxwininit) 컨텍스트를 만들기 위해 및 `AFX_MANAGE_STATE` 활성화 및 비활성화 합니다. 또한 `AFX_MANAGE_STATE` 사용자 DLL에서 선택 하는 적절 한 활성화 컨텍스트에서 실행 되도록 MFC 코드를 허용 하기 위해 정적 MFC 라이브러리와 MFC Dll의 경우 사용 됩니다. 자세한 내용은 [MFC 모듈 상태의 활성화 컨텍스트 지원](../support-for-activation-contexts-in-the-mfc-module-state.md)합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxstat_.h

## <a name="a-nameafxoleinitmodulea-afxoleinitmodule"></a><a name="afxoleinitmodule"><a/> AfxOleInitModule

MFC에 동적으로 연결 된 기본 MFC DLL에서 OLE 지원에 대 한 기본 MFC DLL에서이 함수를 호출 `CWinApp::InitInstance` MFC OLE DLL을 초기화 하는 함수입니다.

### <a name="syntax"></a>구문

```
void AFXAPI AfxOleInitModule( );
```

### <a name="remarks"></a>설명

MFC OLE DLL이 MFC 확장 DLL; MFC 확장 DLL에 유선 가져오려면 하려면에서를 `CDynLinkLibrary` 체인을 생성 하도록 해야 합니다는 `CDynLinkLibrary` 은 사용 하는 모든 모듈의 컨텍스트에서 개체입니다. `AfxOleInitModule` 만듭니다는 `CDynLinkLibrary` 에 유선 가져옵니다 있도록 기본 MFC DLL의 컨텍스트에서 개체를 `CDynLinkLibrary` 기본 MFC DLL의 체인 개체입니다.

OLE 컨트롤을 빌드하는 하 고 사용 하는 경우 `COleControlModule`를 호출 하지 않아야 `AfxOleInitModule` 때문에 `InitInstance` 멤버 함수에 대 한 `COleControlModule` 호출 `AfxOleInitModule`합니다.

### <a name="requirements"></a>요구 사항

**헤더**: \<afxdll_.h >

## <a name="afxnetinitmodule"></a>  AfxNetInitModule

MFC에 동적으로 연결 된 기본 MFC DLL에서 MFC 소켓 지원, 기본 MFC DLL의에이 함수에 대 한 호출 추가 `CWinApp::InitInstance` MFC 소켓 DLL을 초기화 하는 함수입니다.

### <a name="syntax"></a>구문

```
void AFXAPI AfxNetInitModule( );
```

### <a name="remarks"></a>설명

MFC 소켓 DLL이 MFC 확장 DLL; MFC 확장 DLL에 유선 가져오려면 하려면에서를 `CDynLinkLibrary` 체인을 생성 하도록 해야 합니다는 `CDynLinkLibrary` 은 사용 하는 모든 모듈의 컨텍스트에서 개체입니다. `AfxNetInitModule` 만듭니다는 `CDynLinkLibrary` 에 유선 가져옵니다 있도록 기본 MFC DLL의 컨텍스트에서 개체를 `CDynLinkLibrary` 기본 MFC DLL의 체인 개체입니다.

### <a name="requirements"></a>요구 사항

**헤더:** \<afxdll_.h >

## <a name="afxgetambientactctx"></a> AfxGetAmbientActCtx

MFC의 WinSxS 동작에 영향을 주는 모듈별 상태 플래그의 현재 상태를 가져오려면이 함수를 사용 합니다.

### <a name="syntax"></a>구문

```
BOOL AFXAPI AfxGetAmbientActCtx();
```

### <a name="return-value"></a>반환 값

모듈 상태 플래그 현재 값입니다.

### <a name="remarks"></a>설명

플래그를 설정 합니다 (기본값) 시간과 스레드 MFC 모듈을 입력 (참조 [AFX_MANAGE_STATE](#afx_manage_state)), 모듈의 컨텍스트에서 활성화 됩니다.

플래그를 설정 하지 않으면 모듈의 컨텍스트 항목에 대해 활성화 되지 않았습니다.

모듈의 컨텍스트는 일반적으로 모듈 리소스에 포함 된 매니페스트에서에서 결정 됩니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxcomctl32.h

## <a name="afxgetstaticmodulestate"></a> AfxGetStaticModuleState

초기화 하기 전에 모듈 상태를 설정 및/또는 정리 후 이전 모듈 상태를 복원 하려면이 함수를 호출 합니다.

### <a name="syntax"></a>구문

```
AFX_MODULE_STATE* AFXAPI AfxGetStaticModuleState( );
```

### <a name="return-value"></a>반환 값

에 대 한 포인터는 `AFX_MODULE_STATE` 구조입니다.

### <a name="remarks"></a>설명

`AFX_MODULE_STATE` 구조 모듈의 경우 푸시 되거나 팝 되는 모듈 상태의 일부 이므로 전역 데이터를 포함 합니다.

기본적으로 MFC 리소스 템플릿을 로드 하는 기본 응용 프로그램의 리소스 핸들을 사용 합니다. DLL의 대화 상자를 시작 하는 것과 같은 DLL에서 내보낸된 함수를 설정한 경우이 템플릿은 DLL 모듈에서 실제로 저장 됩니다. 사용할 올바른 핸들에 대 한 모듈 상태를 전환 해야 합니다. 함수의 시작 부분에 다음 코드를 추가 하 여이 수행할 수 있습니다.

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));
```

현재 모듈 상태에서 반환 된 상태와 교환이 `AfxGetStaticModuleState` 현재 범위의 끝까지 합니다.

MFC 모듈 상태에 대 한 자세한 내용은 "관리는 데이터의 MFC 모듈 상태"를 참조 하세요 [새 문서 만들기, Windows, 뷰와](../creating-new-documents-windows-and-views.md) 하 고 [기술 참고 58](../tn058-mfc-module-state-implementation.md)합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxstat_.h

## <a name="afxinitextensionmodule"></a>AfxInitExtensionModule

이 함수는 MFC 확장 DLL의 호출 `DllMain` DLL을 초기화 합니다.

### <a name="syntax"></a>구문

```
BOOL AFXAPI AfxInitExtensionModule( AFX_EXTENSION_MODULE& state,  HMODULE hModule );
```

### <a name="parameters"></a>매개 변수

*state*<br/>
에 대 한 참조를 [AFX_EXTENSION_MODULE 구조체](afx-extension-module-structure.md) 초기화 후 MFC 확장명 DLL 모듈의 상태를 포함 될 구조체입니다. 일반적인 정적 개체 생성 되기 전에 실행의 일부로 MFC 확장 DLL에 의해 초기화 된 런타임 클래스 개체의 복사본을 포함 하는 상태 `DllMain` 를 입력 합니다.

*hModule*<br/>
MFC 확장명 DLL 모듈의 핸들입니다.

### <a name="return-value"></a>반환 값

TRUE 이면 MFC 확장명 DLL 성공적으로 초기화 됩니다. 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

예를 들어:

```cpp
static AFX_EXTENSION_MODULE NVC_MFC_DLLDLL = { NULL, NULL };
extern "C" int APIENTRY
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)
{
    // Remove this if you use lpReserved
    UNREFERENCED_PARAMETER(lpReserved);

    if (dwReason == DLL_PROCESS_ATTACH)
    {
        TRACE0("NVC_MFC_DLL.DLL Initializing!\n");

        // MFC extension DLL one-time initialization
        if (!AfxInitExtensionModule(NVC_MFC_DLLDLL, hInstance))
            return 0;
...
```

`AfxInitExtensionModule` DLL의 HMODULE 복사본 및 DLL의 런타임 클래스를 캡처합니다 (`CRuntimeClass` 구조)와 해당 개체 팩터리 (`COleObjectFactory` 개체) 사용에 대 한 뒷부분에 나오는 경우를 `CDynLinkLibrary` 개체가 만들어집니다.
MFC 확장명 Dll에서 두 가지를 수행 해야 해당 `DllMain` 함수:

- 호출 [AfxInitExtensionModule](#afxinitextensionmodule) 반환 값을 확인 합니다.

- 만들기는 `CDynLinkLibrary` DLL를 내보내는 경우 개체 [CRuntimeClass 구조체](cruntimeclass-structure.md) 개체 또는 고유한 사용자 지정 리소스가 있습니다.

호출할 수 있습니다 `AfxTermExtensionModule` MFC 확장명 DLL에서에서 각 프로세스 분리 하는 경우에 MFC 확장명 DLL 정리 하려면 (프로세스가 종료 하거나 DLL의 결과로 언로드되는 때 발생 하는 `AfxFreeLibrary` 호출).

### <a name="requirements"></a>요구 사항

**헤더:** afxdll_.h

## <a name="afxsetambientactctx"></a>  AfxSetAmbientActCtx

MFC의 WinSxS 동작에 영향을 주는 모듈별 상태 플래그를 설정 하려면이 함수를 사용 합니다.

### <a name="syntax"></a>구문

```
void AFXAPI AfxSetAmbientActCtx(BOOL bSet);
```

### <a name="parameters"></a>매개 변수

*bSet*<br/>
모듈 상태 플래그의 새 값입니다.

### <a name="remarks"></a>설명

플래그를 설정 합니다 (기본값) 시간과 스레드 MFC 모듈을 입력 (참조 [AFX_MANAGE_STATE](#afx_manage_state)), 모듈의 컨텍스트에서 활성화 됩니다.
플래그를 설정 하지 않으면 모듈의 컨텍스트 항목에 대해 활성화 되지 않았습니다.
모듈의 컨텍스트는 일반적으로 모듈 리소스에 포함 된 매니페스트에서에서 결정 됩니다.

### <a name="example"></a>예제

```cpp
BOOL CMFCListViewApp::InitInstance()
{
   AfxSetAmbientActCtx(FALSE);
   // Remainder of function definition omitted.
}
```

### <a name="requirements"></a>요구 사항

**헤더:** afxcomctl32.h

## <a name="afxtermextensionmodule"></a>  AfxTermExtensionModule

MFC DLL에서 각 프로세스 분리 하는 경우 MFC 확장명 DLL 정리할 수 있도록이 함수를 호출 (프로세스가 종료 하거나 DLL의 결과로 언로드되는 때 발생 한 `AfxFreeLibrary` 호출).

### <a name="syntax"></a>구문

```
void AFXAPI AfxTermExtensionModule(  AFX_EXTENSION_MODULE& state,  BOOL bAll  = FALSE );
```

### <a name="parameters"></a>매개 변수

*state*<br/>
에 대 한 참조를 [AFX_EXTENSION_MODULE](afx-extension-module-structure.md) MFC 확장명 DLL 모듈의 상태를 포함 하는 구조입니다.

*bAll*<br/>
TRUE 이면 모든 MFC 확장명 DLL 모듈을 정리 합니다. 그렇지 않으면 현재 DLL 모듈을 정리 합니다.

### <a name="remarks"></a>설명

`AfxTermExtensionModule` 모듈에 연결 된 모든 로컬 저장소를 삭제 하 고 메시지 맵 캐시에서 모든 항목을 제거 됩니다. 예를 들어:

```cpp
static AFX_EXTENSION_MODULE NVC_MFC_DLLDLL = { NULL, NULL };
extern "C" int APIENTRY
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)
{
    // Remove this if you use lpReserved
    UNREFERENCED_PARAMETER(lpReserved);

    if (dwReason == DLL_PROCESS_ATTACH)
    {
        TRACE0("NVC_MFC_DLL.DLL Initializing!\n");

        // MFC extension DLL one-time initialization
        if (!AfxInitExtensionModule(NVC_MFC_DLLDLL, hInstance))
            return 0;

        new CMyDynLinkLibrary(NVC_MFC_DLLDLL);

    }
    else if (dwReason == DLL_PROCESS_DETACH)
    {
        TRACE0("NVC_MFC_DLL.DLL Terminating!\n");

        // Terminate the library before destructors are called
        AfxTermExtensionModule(NVC_MFC_DLLDLL);
    }
    return 1;   // ok
}
```

응용 프로그램 로드를 동적으로 MFC 확장명 Dll을 해제 하는 경우 호출 해야 `AfxTermExtensionModule`합니다. 대부분의 MFC 확장명 Dll을 동적으로 로드 되지 않은 이후 (일반적으로 연결 된 해당 가져오기 라이브러리를 통해), 호출 `AfxTermExtensionModule` 일반적으로 필요 하지 않습니다.

MFC 확장명 Dll 호출 해야 [AfxInitExtensionModule](#afxinitextensionmodule) 에서 해당 `DllMain`합니다. DLL를 내보내는 경우 [CRuntimeClass](cruntimeclass-structure.md) 개체 또는 고유한 사용자 지정 리소스가 만들어야 할 수도 `CDynLinkLibrary` 개체 `DllMain`합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxdll_.h

## <a name="see-also"></a>참고자료

[매크로 및 전역](mfc-macros-and-globals.md)<br/>
[AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)<br/>
[MFC 모듈의 상태 데이터 관리](../managing-the-state-data-of-mfc-modules.md)<br/>
