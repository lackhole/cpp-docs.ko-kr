---
title: CComModule 클래스
ms.date: 11/04/2016
f1_keywords:
- CComModule
- ATLBASE/ATL::CComModule
- ATLBASE/ATL::CComModule::GetClassObject
- ATLBASE/ATL::CComModule::GetModuleInstance
- ATLBASE/ATL::CComModule::GetResourceInstance
- ATLBASE/ATL::CComModule::GetTypeLibInstance
- ATLBASE/ATL::CComModule::Init
- ATLBASE/ATL::CComModule::RegisterClassHelper
- ATLBASE/ATL::CComModule::RegisterClassObjects
- ATLBASE/ATL::CComModule::RegisterServer
- ATLBASE/ATL::CComModule::RegisterTypeLib
- ATLBASE/ATL::CComModule::RevokeClassObjects
- ATLBASE/ATL::CComModule::Term
- ATLBASE/ATL::CComModule::UnregisterClassHelper
- ATLBASE/ATL::CComModule::UnregisterServer
- ATLBASE/ATL::CComModule::UpdateRegistryClass
- ATLBASE/ATL::CComModule::UpdateRegistryFromResourceD
- ATLBASE/ATL::CComModule::UpdateRegistryFromResourceS
- ATLBASE/ATL::CComModule::m_csObjMap
- ATLBASE/ATL::CComModule::m_csTypeInfoHolder
- ATLBASE/ATL::CComModule::m_csWindowCreate
- ATLBASE/ATL::CComModule::m_hInst
- ATLBASE/ATL::CComModule::m_hInstResource
- ATLBASE/ATL::CComModule::m_hInstTypeLib
- ATLBASE/ATL::CComModule::m_pObjMap
helpviewer_keywords:
- CComModule class
- DLL modules [C++], ATL
ms.assetid: f5face2c-8fd8-40e6-9ec3-54ab74701769
ms.openlocfilehash: 6d95460902c44ff058a4c7b90c810ab44489d952
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62259276"
---
# <a name="ccommodule-class"></a>CComModule 클래스

ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
class CComModule : public _ATL_MODULE
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CComModule::GetClassObject](#getclassobject)|지정 된 CLSID의 개체를 만듭니다. Dll에 해당 합니다.|
|[CComModule::GetModuleInstance](#getmoduleinstance)|`m_hInst`를 반환합니다.|
|[CComModule::GetResourceInstance](#getresourceinstance)|`m_hInstResource`를 반환합니다.|
|[CComModule::GetTypeLibInstance](#gettypelibinstance)|`m_hInstTypeLib`를 반환합니다.|
|[CComModule::Init](#init)|데이터 멤버를 초기화합니다.|
|[CComModule::RegisterClassHelper](#registerclasshelper)|시스템 레지스트리에 개체의 표준 클래스 등록을 입력합니다.|
|[CComModule::RegisterClassObjects](#registerclassobjects)|클래스 개체를 등록합니다. 에 대 한 Exe에만 해당 합니다.|
|[CComModule::RegisterServer](#registerserver)|개체 맵의 각 개체에 대 한 시스템 레지스트리를 업데이트합니다.|
|[CComModule::RegisterTypeLib](#registertypelib)|형식 라이브러리를 등록합니다.|
|[CComModule::RevokeClassObjects](#revokeclassobjects)|클래스 개체를 취소합니다. 에 대 한 Exe에만 해당 합니다.|
|[CComModule::Term](#term)|데이터 멤버를 해제합니다.|
|[CComModule::UnregisterClassHelper](#unregisterclasshelper)|시스템 레지스트리에서 개체의 표준 클래스 등록을 제거합니다.|
|[CComModule::UnregisterServer](#unregisterserver)|개체 맵의 각 개체의 등록을 취소 합니다.|
|[CComModule::UpdateRegistryClass](#updateregistryclass)|등록 또는 등록 개체의 표준 클래스 등록을 취소 합니다.|
|[CComModule::UpdateRegistryFromResourceD](#updateregistryfromresourced)|등록 또는 개체를 등록 취소는 지정 된 리소스가 포함 된 스크립트를 실행 합니다.|
|[CComModule::UpdateRegistryFromResourceS](#updateregistryfromresources)|ATL 레지스트리 구성 요소에 정적으로 연결 합니다. 등록 또는 개체를 등록 취소는 지정 된 리소스가 포함 된 스크립트를 실행 합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CComModule::m_csObjMap](#m_csobjmap)|개체 맵 정보에 대 한 동기화 된 액세스를 보장합니다.|
|[CComModule::m_csTypeInfoHolder](#m_cstypeinfoholder)|형식 라이브러리 정보에 대 한 동기화 된 액세스를 보장합니다.|
|[CComModule::m_csWindowCreate](#m_cswindowcreate)|창 클래스 정보 창 만드는 동안 사용 되는 정적 데이터를 동기화 된 액세스를 보장 합니다.|
|[CComModule::m_hInst](#m_hinst)|모듈 인스턴스에 대 한 핸들을 포함합니다.|
|[CComModule::m_hInstResource](#m_hinstresource)|기본적으로 모듈 인스턴스에 대 한 핸들을 포함합니다.|
|[CComModule::m_hInstTypeLib](#m_hinsttypelib)|기본적으로 모듈 인스턴스에 대 한 핸들을 포함합니다.|
|[CComModule::m_pObjMap](#m_pobjmap)|개체 맵의 모듈 인스턴스에 의해 유지 관리를 가리킵니다.|

## <a name="remarks"></a>설명

> [!NOTE]
>  이 클래스는 사용 되지 않으며 이제 ATL 코드 생성 마법사를 사용 합니다 [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) 하 고 [CAtlModule](../../atl/reference/catlmodule-class.md) 클래스를 파생 합니다. 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 자세한 내용은 합니다. 다음에 나오는 정보는 ATL.의 이전 릴리스를 사용 하 여 만든 응용 프로그램을 사용 하 여 `CComModule` 여전히에 대 한 ATL의 일부 이전 버전과 기능입니다.

`CComModule` COM 서버 모듈의 경우 모듈의 구성 요소에 액세스 하는 클라이언트를 구현 합니다. `CComModule` DLL (in process) 및 EXE (local) 모듈을 모두 지원합니다.

`CComModule` 인스턴스 클래스 개체 정의의 집합을 유지 하기 위해 개체 맵을 사용 합니다. 이 개체 맵의 배열로 서 구현 됩니다 `_ATL_OBJMAP_ENTRY` 구조, 및에 대 한 정보를 포함 합니다.

- 입력 하 고 시스템 레지스트리에 개체 설명을 제거 합니다.

- 클래스 팩터리를 통해 개체를 인스턴스화.

- 구성 요소에서 루트 개체와 클라이언트 간의 통신을 설정 합니다.

- 클래스 개체의 수명 관리를 수행 합니다.

ATL COM 응용 프로그램 마법사를 실행 하면 마법사를 자동으로 생성 `_Module`의 전역 인스턴스 `CComModule` 클래스에서 파생 된 또는 합니다. ATL 프로젝트 마법사에 대 한 자세한 내용은 문서 참조 [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)합니다.

외에 `CComModule`, ATL 제공 [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md), Exe 및 Windows 서비스에 대 한 아파트 모델 모듈을 구현 하는 합니다. 모듈을 파생 `CComAutoThreadModule` 여러 아파트에서 개체를 만들려는 경우입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

`CComModule`

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

##  <a name="getclassobject"></a>  CComModule::GetClassObject

ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.

```
HRESULT GetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```

### <a name="parameters"></a>매개 변수

*rclsid*<br/>
[in] 만들 개체의 CLSID입니다.

*riid*<br/>
[in] 요청된 된 인터페이스의 IID입니다.

*ppv*<br/>
[out] 로 식별 되는 인터페이스 포인터에 대 한 포인터 *riid*합니다. 개체는이 인터페이스를 지원 하지 않는 경우 *ppv* NULL로 설정 됩니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

지정된 된 CLSID의 개체를 만들고이 개체에 대 한 인터페이스 포인터를 검색 합니다.

`GetClassObject` 만 Dll에 제공 됩니다.

##  <a name="getmoduleinstance"></a>  CComModule::GetModuleInstance

ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.

```
HINSTANCE GetModuleInstance() throw();
```

### <a name="return-value"></a>반환 값

HINSTANCE이이 모듈을 식별 합니다.

### <a name="remarks"></a>설명

반환 된 [m_hInst](#m_hinst) 데이터 멤버입니다.

##  <a name="getresourceinstance"></a>  CComModule::GetResourceInstance

ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.

```
HINSTANCE GetResourceInstance() throw();
```

### <a name="return-value"></a>반환 값

HINSTANCE 합니다.

### <a name="remarks"></a>설명

반환 된 [m_hInstResource](#m_hinstresource) 데이터 멤버입니다.

##  <a name="gettypelibinstance"></a>  CComModule::GetTypeLibInstance

ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.

```
HINSTANCE GetTypeLibInstance() const throw();
```

### <a name="return-value"></a>반환 값

HINSTANCE 합니다.

### <a name="remarks"></a>설명

반환 된 [m_hInstTypeLib](#m_hinsttypelib) 데이터 멤버입니다.

##  <a name="init"></a>  CComModule::Init

ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.

```
HRESULT Init(
    _ATL_OBJMAP_ENTRY* p,
    HINSTANCE h,
    const GUID* plibid = NULL) throw();
```

### <a name="parameters"></a>매개 변수

*p*<br/>
[in] 개체 맵 항목의 배열에 대 한 포인터입니다.

*h*<br/>
[in] 에 전달 된 HINSTANCE `DLLMain` 또는 `WinMain`합니다.

*plibid*<br/>
[in] 프로젝트에 연결 된 형식 라이브러리의 LIBID 포인터입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

모든 데이터 멤버를 초기화합니다.

##  <a name="m_csobjmap"></a>  CComModule::m_csObjMap

ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.

```
CRITICAL_SECTION m_csObjMap;
```

### <a name="remarks"></a>설명

개체 맵의에 대 한 동기화 된 액세스를 보장합니다.

##  <a name="m_cstypeinfoholder"></a>  CComModule::m_csTypeInfoHolder

ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.

```
CRITICAL_SECTION m_csTypeInfoHolder;
```

### <a name="remarks"></a>설명

형식 라이브러리에 대 한 동기화 된 액세스를 보장합니다.

##  <a name="m_cswindowcreate"></a>  CComModule::m_csWindowCreate

ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.

```
CRITICAL_SECTION m_csWindowCreate;
```

### <a name="remarks"></a>설명

창 클래스 정보를 창 만드는 동안 사용 되는 정적 데이터를 동기화 된 액세스를 보장 합니다.

##  <a name="m_hinst"></a>  CComModule::m_hInst

ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.

```
HINSTANCE m_hInst;
```

### <a name="remarks"></a>설명

모듈 인스턴스에 대 한 핸들을 포함합니다.

합니다 [Init](#init) 메서드 집합 `m_hInst` 에 전달 된 핸들 `DLLMain` 또는 `WinMain`합니다.

##  <a name="m_hinstresource"></a>  CComModule::m_hInstResource

ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.

```
HINSTANCE m_hInstResource;
```

### <a name="remarks"></a>설명

기본적으로 모듈 인스턴스에 대 한 핸들을 포함합니다.

합니다 [Init](#init) 메서드 집합 `m_hInstResource` 에 전달 된 핸들 `DLLMain` 또는 `WinMain`합니다. 명시적으로 설정할 수 있습니다 `m_hInstResource` 리소스에 대 한 핸들을 합니다.

합니다 [GetResourceInstance](#getresourceinstance) 에 저장 된 핸들을 반환 하는 메서드 `m_hInstResource`합니다.

##  <a name="m_hinsttypelib"></a>  CComModule::m_hInstTypeLib

ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.

```
HINSTANCE m_hInstTypeLib;
```

### <a name="remarks"></a>설명

기본적으로 모듈 인스턴스에 대 한 핸들을 포함합니다.

합니다 [Init](#init) 메서드 집합 `m_hInstTypeLib` 에 전달 된 핸들 `DLLMain` 또는 `WinMain`합니다. 명시적으로 설정할 수 있습니다 `m_hInstTypeLib` 형식 라이브러리에 대 한 핸들을 합니다.

합니다 [GetTypeLibInstance](#gettypelibinstance) 에 저장 된 핸들을 반환 하는 메서드 `m_hInstTypeLib`합니다.

##  <a name="m_pobjmap"></a>  CComModule::m_pObjMap

ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.

```
_ATL_OBJMAP_ENTRY* m_pObjMap;
```

### <a name="remarks"></a>설명

개체 맵의 모듈 인스턴스에 의해 유지 관리를 가리킵니다.

##  <a name="registerclasshelper"></a>  CComModule::RegisterClassHelper

ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.

```
ATL_DEPRECATED HRESULT RegisterClassHelper(
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID,
    UINT nDescID,
    DWORD dwFlags);
```

### <a name="parameters"></a>매개 변수

*clsid*<br/>
[in] 등록할 개체의 CLSID입니다.

*lpszProgID*<br/>
[in] 개체에 연결 된 ProgID입니다.

*lpszVerIndProgID*<br/>
[in] 개체에 연결 된 버전 독립 ProgID입니다.

*nDescID*<br/>
[in] 개체의 설명에 대 한 문자열 리소스의 식별자입니다.

*dwFlags*<br/>
[in] 스레딩 모델 레지스트리에 입력을 지정 합니다. 가능한 값은 THREADFLAGS_APARTMENT, THREADFLAGS_BOTH, 또는 AUTPRXFLAG입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

시스템 레지스트리에 개체의 표준 클래스 등록을 입력합니다.

합니다 [UpdateRegistryClass](#updateregistryclass) 메서드 호출 `RegisterClassHelper`합니다.

##  <a name="registerclassobjects"></a>  CComModule::RegisterClassObjects

ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.

```
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```

### <a name="parameters"></a>매개 변수

*dwClsContext*<br/>
[in] 클래스 개체를 실행할의 컨텍스트를 지정 합니다. 가능한 값은 CLSCTX_INPROC_SERVER, CLSCTX_INPROC_HANDLER, 또는 CLSCTX_LOCAL_SERVER입니다. 이러한 값에 대 한 참조 [CLSCTX](/windows/desktop/api/wtypesbase/ne-wtypesbase-tagclsctx) Windows SDK에 있습니다.

*dwFlags*<br/>
[in] 클래스 개체에 연결 형식을 결정합니다. 가능한 값은 REGCLS_SINGLEUSE, REGCLS_MULTIPLEUSE, 또는 REGCLS_MULTI_SEPARATE입니다. 이러한 값에 대 한 참조 [REGCLS](/windows/desktop/api/combaseapi/ne-combaseapi-tagregcls) Windows SDK에 있습니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

다른 응용 프로그램에 연결할 수 있도록 OLE를 사용 하 여 EXE 클래스 개체를 등록 합니다. 이 메서드는 Exe 수만 있습니다.

##  <a name="registerserver"></a>  CComModule::RegisterServer

ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.

```
HRESULT RegisterServer(
    BOOL bRegTypeLib = FALSE,
    const CLSID* pCLSID = NULL) throw();
```

### <a name="parameters"></a>매개 변수

*bRegTypeLib*<br/>
[in] 형식 라이브러리를 등록할 적이 있는지 여부를 나타냅니다. 기본값은 FALSE입니다.

*pCLSID*<br/>
[in] 등록할 개체의 CLSID 가리킵니다. NULL (기본값), 개체 맵의 모든 개체를 등록할 경우.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

에 따라 합니다 *하면* 매개 변수를 단일 클래스 개체 또는 개체 맵의 모든 개체에 대 한 시스템 레지스트리를 업데이트 합니다.

하는 경우 *bRegTypeLib* 가 TRUE 인 형식 라이브러리 정보도 업데이트 됩니다.

참조 [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) 개체 맵에 항목을 추가 하는 방법에 대 한 정보에 대 한 합니다.

`RegisterServer` 자동으로 호출 됩니다 `DLLRegisterServer` 또는 DLL에 대 한 `WinMain` 사용 하 여 실행 exe를 `/RegServer` 명령줄 옵션입니다.

##  <a name="registertypelib"></a>  CComModule::RegisterTypeLib

ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.

```
HRESULT RegisterTypeLib() throw();
HRESULT RegisterTypeLib(LPCTSTR lpszIndex) throw();
```

### <a name="parameters"></a>매개 변수

*lpszIndex*<br/>
[in] 형식에서 문자열 `"\\N"`여기서 `N` TYPELIB 리소스의 정수 인덱스입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

시스템 레지스트리를 형식 라이브러리에 대 한 정보를 추가합니다.

모듈 인스턴스 형식 라이브러리가 여러 개 있으면는 형식 라이브러리를 사용할지 지정 하려면이 메서드의 두 번째 버전을 사용 합니다.

##  <a name="revokeclassobjects"></a>  CComModule::RevokeClassObjects

ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.

```
HRESULT RevokeClassObjects() throw();
```

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

클래스 개체를 제거합니다. 이 메서드는 Exe 수만 있습니다.

##  <a name="term"></a>  CComModule::Term

ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.

```
void Term() throw();
```

### <a name="remarks"></a>설명

모든 데이터 멤버를 해제합니다.

##  <a name="unregisterclasshelper"></a>  CComModule::UnregisterClassHelper

ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.

```
ATL_DEPRECATED HRESULT UnregisterClassHelper(
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID);
```

### <a name="parameters"></a>매개 변수

*clsid*<br/>
[in] 등록을 취소할 개체의 CLSID입니다.

*lpszProgID*<br/>
[in] 개체에 연결 된 ProgID입니다.

*lpszVerIndProgID*<br/>
[in] 개체에 연결 된 버전 독립 ProgID입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

시스템 레지스트리에서 개체의 표준 클래스 등록을 제거합니다.

합니다 [UpdateRegistryClass](#updateregistryclass) 메서드 호출 `UnregisterClassHelper`합니다.

##  <a name="unregisterserver"></a>  CComModule::UnregisterServer

ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.

```
HRESULT UnregisterServer(const CLSID* pCLSID = NULL) throw ();
inline HRESULT UnregisterServer(BOOL bUnRegTypeLib, const CLSID* pCLSID = NULL) throw ();
```

### <a name="parameters"></a>매개 변수

*bUnRegTypeLib*<br/>
True 이면 형식 라이브러리는도 등록 합니다.

*pCLSID*<br/>
등록을 취소할 개체의 CLSID 가리킵니다. 경우 NULL (기본값), 개체 맵의 모든 개체를 등록 취소 됩니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

에 따라 합니다 *하면* 매개 변수를 단일 클래스 개체 또는 개체 맵의 모든 개체를 등록 취소 합니다.

`UnregisterServer` 자동으로 호출 됩니다 `DLLUnregisterServer` 또는 DLL에 대 한 `WinMain` 사용 하 여 실행 exe를 `/UnregServer` 명령줄 옵션입니다.

참조 [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) 개체 맵에 항목을 추가 하는 방법에 대 한 정보에 대 한 합니다.

##  <a name="updateregistryclass"></a>  CComModule::UpdateRegistryClass

ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.

```
ATL_DEPRECATED HRESULT UpdateRegistryClass(
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID,
    UINT nDescID,
    DWORD dwFlags,
    BOOL bRegister);

ATL_DEPRECATED HRESULT UpdateRegistryClass(
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID,
    LPCTSTR szDesc,
    DWORD dwFlags,
    BOOL bRegister);
```

### <a name="parameters"></a>매개 변수

*clsid*<br/>
등록 하거나 등록을 취소할 개체의 CLSID입니다.

*lpszProgID*<br/>
개체에 연결 된 ProgID입니다.

*lpszVerIndProgID*<br/>
개체에 연결 된 버전 독립 ProgID입니다.

*nDescID*<br/>
개체의 설명에 대 한 문자열 리소스의 식별자입니다.

*szDesc*<br/>
개체의 설명을 포함 하는 문자열입니다.

*dwFlags*<br/>
스레딩 모델 레지스트리에 입력을 지정 합니다. 가능한 값은 THREADFLAGS_APARTMENT, THREADFLAGS_BOTH, 또는 AUTPRXFLAG입니다.

*bRegister*<br/>
개체를 등록할지 여부를 나타냅니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

하는 경우 *b 등록 하십시오* 가 TRUE 이면이 메서드는 개체의 표준 클래스 등록 시스템 레지스트리에 입력 합니다.

하는 경우 *b 등록 하십시오* FALSE는 개체의 등록을 제거 합니다.

값에 따라 *b 등록 하십시오*를 `UpdateRegistryClass` 중 하나를 호출 [RegisterClassHelper](#registerclasshelper) 하거나 [UnregisterClassHelper](#unregisterclasshelper)합니다.

지정 하 여 합니다 [DECLARE_REGISTRY](registry-macros.md#declare_registry) 매크로 `UpdateRegistryClass` 개체 지도 처리 될 때 자동으로 호출 됩니다.

##  <a name="updateregistryfromresourced"></a>  CComModule::UpdateRegistryFromResourceD

ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.

```
virtual HRESULT UpdateRegistryFromResourceD(
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

virtual HRESULT UpdateRegistryFromResourceD(
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw ();
```

### <a name="parameters"></a>매개 변수

*lpszRes*<br/>
[in] 리소스 이름입니다.

*nResID*<br/>
[in] 리소스 id입니다.

*bRegister*<br/>
[in] 개체를 등록할지 여부를 나타냅니다.

*pMapEntries*<br/>
[in] 스크립트의 대체 가능 매개 변수를 사용 하 여 연결 된 값을 저장 대체 지도에 대 한 포인터입니다. ATL 사용 하 여 자동으로 `%MODULE%`입니다. 추가 대체 가능 매개 변수를 사용 하려면 세부 정보에 대 한 설명을 참조 하세요. 그렇지 않으면 NULL 기본값을 사용 합니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

지정 하는 리소스가 포함 된 스크립트 실행 *lpszRes* 하거나 *nResID*합니다.

하는 경우 *b 등록 하십시오* 가 TRUE 이면이 메서드는 개체가 시스템 레지스트리에 등록; 개체가 고, 그렇지 등록 취소 합니다.

지정 하 여는 [DECLARE_REGISTRY_RESOURCE](registry-macros.md#declare_registry_resource) 하거나 [DECLARE_REGISTRY_RESOURCEID](registry-macros.md#declare_registry_resourceid) 매크로 `UpdateRegistryFromResourceD` 개체 지도 처리 될 때 자동으로 호출 됩니다.

> [!NOTE]
>  런타임 시 대체 값을 대체, DECLARE_REGISTRY_RESOURCE 또는 DECLARE_REGISTRY_RESOURCEID 매크로 지정 하지 마십시오. 대신, 배열을 만든 `_ATL_REGMAP_ENTRIES` 런타임에 자리 표시자 값을 사용 하 여 쌍을 이루는 구조, 각 항목 변수 자리 표시자를 포함 하는 위치입니다. 다음 호출 `UpdateRegistryFromResourceD`에 대 한 배열을 전달 합니다 *pMapEntries* 매개 변수입니다. 모든 대체 값이 추가 `_ATL_REGMAP_ENTRIES` 기관의 대체 맵 구조입니다.

> [!NOTE]
>  ATL 레지스트리 구성 요소 (등록자)에 정적으로 링크를 참조 하세요 [UpdateRegistryFromResourceS](#updateregistryfromresources)합니다.

대체 가능 매개 변수 및 스크립팅 하는 방법에 대 한 자세한 내용은 문서 참조 [ATL 레지스트리 구성 요소 (등록자)](../../atl/atl-registry-component-registrar.md)합니다.

##  <a name="updateregistryfromresources"></a>  CComModule::UpdateRegistryFromResourceS

ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.

```
virtual HRESULT UpdateRegistryFromResourceS(
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

virtual HRESULT UpdateRegistryFromResourceS(
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```

### <a name="parameters"></a>매개 변수

*lpszRes*<br/>
[in] 리소스 이름입니다.

*nResID*<br/>
[in] 리소스 id입니다.

*bRegister*<br/>
[in] 리소스 스크립트를 등록할지 여부를 나타냅니다.

*pMapEntries*<br/>
[in] 스크립트의 대체 가능 매개 변수를 사용 하 여 연결 된 값을 저장 대체 지도에 대 한 포인터입니다. ATL 사용 하 여 자동으로 `%MODULE%`입니다. 추가 대체 가능 매개 변수를 사용 하려면 세부 정보에 대 한 설명을 참조 하세요. 그렇지 않으면 NULL 기본값을 사용 합니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

비슷합니다 [UpdateRegistryFromResourceD](#updateregistryfromresourced) 제외한 `UpdateRegistryFromResourceS` ATL 레지스트리 구성 요소 (등록자)에 정적 링크를 만듭니다.

`UpdateRegistryFromResourceS` 호출할 자동으로 지도 개체를 처리할 때 추가한 제공 `#define _ATL_STATIC_REGISTRY` 프로그램 stdafx.h로 합니다.

> [!NOTE]
>  런타임 시 대체 값을 대체를 지정 하지 않으면 합니다 [DECLARE_REGISTRY_RESOURCE](registry-macros.md#declare_registry_resource) 하거나 [DECLARE_REGISTRY_RESOURCEID](registry-macros.md#declare_registry_resourceid) 매크로입니다. 대신, 배열을 만든 `_ATL_REGMAP_ENTRIES` 런타임에 자리 표시자 값을 사용 하 여 쌍을 이루는 구조, 각 항목 변수 자리 표시자를 포함 하는 위치입니다. 다음 호출 `UpdateRegistryFromResourceS`에 대 한 배열을 전달 합니다 *pMapEntries* 매개 변수입니다. 모든 대체 값이 추가 `_ATL_REGMAP_ENTRIES` 기관의 대체 맵 구조입니다.

대체 가능 매개 변수 및 스크립팅 하는 방법에 대 한 자세한 내용은 문서 참조 [ATL 레지스트리 구성 요소 (등록자)](../../atl/atl-registry-component-registrar.md)합니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)
