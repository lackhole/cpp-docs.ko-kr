---
title: CAtlDllModuleT 클래스
ms.date: 11/04/2016
f1_keywords:
- CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT::CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT::DllCanUnloadNow
- ATLBASE/ATL::CAtlDllModuleT::DllGetClassObject
- ATLBASE/ATL::CAtlDllModuleT::DllMain
- ATLBASE/ATL::CAtlDllModuleT::DllRegisterServer
- ATLBASE/ATL::CAtlDllModuleT::DllUnregisterServer
- ATLBASE/ATL::CAtlDllModuleT::GetClassObject
helpviewer_keywords:
- CAtlDllModuleT class
ms.assetid: 351d5767-8257-4878-94be-45a85e31a72d
ms.openlocfilehash: be42915c6c2e941bc5fc1de78c5c7ac26ccca6e2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62247102"
---
# <a name="catldllmodulet-class"></a>CAtlDllModuleT 클래스

이 클래스는 DLL에 대 한 모듈을 나타냅니다.

## <a name="syntax"></a>구문

```
template <class T>
class ATL_NO_VTABLE CAtlDllModuleT : public CAtlModuleT<T>
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
클래스에서 파생 된 `CAtlDllModuleT`합니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CAtlDllModuleT::CAtlDllModuleT](#catldllmodulet)|생성자입니다.|
|[CAtlDllModuleT::~CAtlDllModuleT](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CAtlDllModuleT::DllCanUnloadNow](#dllcanunloadnow)|DLL을 로드할 수 있는지 테스트 합니다.|
|[CAtlDllModuleT::DllGetClassObject](#dllgetclassobject)|클래스 팩터리를 반환합니다.|
|[CAtlDllModuleT::DllMain](#dllmain)|선택적 진입점 동적 연결 라이브러리 (DLL)입니다.|
|[CAtlDllModuleT::DllRegisterServer](#dllregisterserver)|DLL의 개체에 대 한 시스템 레지스트리에 항목을 추가합니다.|
|[CAtlDllModuleT::DllUnregisterServer](#dllunregisterserver)|DLL의 개체에 대 한 시스템 레지스트리에 항목을 제거합니다.|
|[CAtlDllModuleT::GetClassObject](#getclassobject)|클래스 팩터리를 반환합니다. 호출 하 여 [DllGetClassObject](#dllgetclassobject)합니다.|

## <a name="remarks"></a>설명

`CAtlDllModuleT` 동적 연결 라이브러리 (DLL)에 대 한 모듈을 나타내며 모든 DLL 프로젝트에서 사용 되는 함수를 제공 합니다. 이 특수화 [CAtlModuleT](../../atl/reference/catlmodulet-class.md) 클래스 등록에 대 한 지원이 포함 되어 있습니다.

ATL에서 모듈에 대 한 자세한 내용은 참조 하세요. [ATL 모듈 클래스](../../atl/atl-module-classes.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

`CAtlDllModuleT`

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

##  <a name="catldllmodulet"></a>  CAtlDllModuleT::CAtlDllModuleT

생성자입니다.

```
CAtlDllModuleT() throw();
```

##  <a name="dtor"></a>  CAtlDllModuleT::~CAtlDllModuleT

소멸자입니다.

```
~CAtlDllModuleT() throw();
```

##  <a name="dllcanunloadnow"></a>  CAtlDllModuleT::DllCanUnloadNow

DLL을 로드할 수 있는지 테스트 합니다.

```
HRESULT DllCanUnloadNow() throw();
```

### <a name="return-value"></a>반환 값

불가능 한 경우 DLL을 로드할 수 있으면 S_OK 또는 S_FALSE를 반환 합니다.

##  <a name="dllgetclassobject"></a>  CAtlDllModuleT::DllGetClassObject

클래스 팩터리를 반환합니다.

```
HRESULT DllGetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```

### <a name="parameters"></a>매개 변수

*rclsid*<br/>
만들 개체의 CLSID입니다.

*riid*<br/>
요청된 된 인터페이스의 IID입니다.

*ppv*<br/>
로 식별 되는 인터페이스 포인터에 대 한 포인터 *riid*합니다. 개체는이 인터페이스를 지원 하지 않는 경우 *ppv* NULL로 설정 됩니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="dllmain"></a>  CAtlDllModuleT::DllMain

선택적 진입점 동적 연결 라이브러리 (DLL)입니다.

```
BOOL WINAPI DllMain(DWORD dwReason, LPVOID /* lpReserved*/) throw();
```

### <a name="parameters"></a>매개 변수

*dwReason*<br/>
DLL_PROCESS_ATTACH, 활발 및 DLL_THREAD_DETACH 알림 호출으로 사용 하지 않도록 설정 합니다.

*lpReserved*<br/>
예약됨.

### <a name="return-value"></a>반환 값

항상 TRUE를 반환 합니다.

### <a name="remarks"></a>설명

활발을 사용 하지 않도록 설정 하 고 DLL_THREAD_DETACH 알림 호출에는 여러 Dll이 있는 다중 스레드 응용 프로그램에 대 한 유용한 최적화 수, 자주 만들고 있는 스레드를 삭제 합니다. 해당 Dll의 이러한 스레드 수준 알림이 필요가 없습니다. 첨부/분리 합니다.

##  <a name="dllregisterserver"></a>  CAtlDllModuleT::DllRegisterServer

DLL의 개체에 대 한 시스템 레지스트리에 항목을 추가합니다.

```
HRESULT DllRegisterServer(BOOL bRegTypeLib = TRUE) throw();
```

### <a name="parameters"></a>매개 변수

*bRegTypeLib*<br/>
TRUE 이면 형식 라이브러리 등록 됩니다. 기본값은 TRUE입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="dllunregisterserver"></a>  CAtlDllModuleT::DllUnregisterServer

DLL의 개체에 대 한 시스템 레지스트리에 항목을 제거합니다.

```
HRESULT DllUnregisterServer(BOOL bUnRegTypeLib = TRUE) throw();
```

### <a name="parameters"></a>매개 변수

*bUnRegTypeLib*<br/>
형식 라이브러리를 레지스트리에서 제거할 이면 TRUE입니다. 기본값은 TRUE입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="getclassobject"></a>  CAtlDllModuleT::GetClassObject

지정된 된 CLSID의 개체를 만듭니다.

```
HRESULT GetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```

### <a name="parameters"></a>매개 변수

*rclsid*<br/>
만들 개체의 CLSID입니다.

*riid*<br/>
요청된 된 인터페이스의 IID입니다.

*ppv*<br/>
로 식별 되는 인터페이스 포인터에 대 한 포인터 *riid*합니다. 개체는이 인터페이스를 지원 하지 않는 경우 *ppv* NULL로 설정 됩니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

이 메서드는 [CAtlDllModuleT::DllGetClassObject](#dllgetclassobject) 되며 이전 버전과 호환성을 위해 포함 되었습니다.

## <a name="see-also"></a>참고자료

[CAtlModuleT 클래스](../../atl/reference/catlmodulet-class.md)<br/>
[CAtlExeModuleT 클래스](../../atl/reference/catlexemodulet-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[모듈 클래스](../../atl/atl-module-classes.md)
