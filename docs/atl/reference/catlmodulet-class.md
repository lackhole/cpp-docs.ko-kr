---
title: CAtlModuleT 클래스
ms.date: 11/04/2016
f1_keywords:
- CAtlModuleT
- ATLBASE/ATL::CAtlModuleT
- ATLBASE/ATL::CAtlModuleT::CAtlModuleT
- ATLBASE/ATL::CAtlModuleT::InitLibId
- ATLBASE/ATL::CAtlModuleT::RegisterAppId
- ATLBASE/ATL::CAtlModuleT::RegisterServer
- ATLBASE/ATL::CAtlModuleT::UnregisterAppId
- ATLBASE/ATL::CAtlModuleT::UnregisterServer
- ATLBASE/ATL::CAtlModuleT::UpdateRegistryAppId
helpviewer_keywords:
- CAtlModuleT class
ms.assetid: 9b74d02f-9117-47b1-a05e-c5945f83dd2b
ms.openlocfilehash: 2cd207038a92b944bf95575f0e0c820b8f09d615
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62260151"
---
# <a name="catlmodulet-class"></a>CAtlModuleT 클래스

이 클래스는 ATL 모듈을 구현합니다.

## <a name="syntax"></a>구문

```
template <class T>
class ATL_NO_VTABLE CAtlModuleT : public CAtlModule
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
클래스에서 파생 된 `CAtlModuleT`합니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CAtlModuleT::CAtlModuleT](#catlmodulet)|생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CAtlModuleT::InitLibId](#initlibid)|현재 모듈의 GUID가 포함 된 데이터 멤버를 초기화 합니다.|
|[CAtlModuleT::RegisterAppId](#registerappid)|레지스트리에 exe 파일을 추가합니다.|
|[CAtlModuleT::RegisterServer](#registerserver)|레지스트리에 서비스를 추가합니다.|
|[CAtlModuleT::UnregisterAppId](#unregisterappid)|레지스트리에서 exe 파일을 제거합니다.|
|[CAtlModuleT::UnregisterServer](#unregisterserver)|레지스트리에서 서비스를 제거합니다.|
|[CAtlModuleT::UpdateRegistryAppId](#updateregistryappid)|레지스트리에서 EXE 정보를 업데이트합니다.|

## <a name="remarks"></a>설명

`CAtlModuleT`에서 파생 된 [CAtlModule](../../atl/reference/catlmodule-class.md), 실행 파일 (EXE) 또는 서비스 (EXE) ATL 모듈을 구현 합니다. 실행 모듈은 서비스 모듈은 Windows 시작 될 때 백그라운드에서 실행 되는 Windows 응용 프로그램을 로컬-out-of-process 서버를 합니다.

`CAtlModuleT` 초기화, 등록 및 모듈의 등록 취소에 대 한 지원을 제공 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

`CAtlModuleT`

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

##  <a name="catlmodulet"></a>  CAtlModuleT::CAtlModuleT

생성자입니다.

```
CAtlModuleT() throw();
```

### <a name="remarks"></a>설명

호출 [CAtlModuleT::InitLibId](#initlibid)합니다.

##  <a name="initlibid"></a>  CAtlModuleT::InitLibId

현재 모듈의 GUID가 포함 된 데이터 멤버를 초기화 합니다.

```
static void InitLibId() throw();
```

### <a name="remarks"></a>설명

생성자를 호출한 [CAtlModuleT::CAtlModuleT](#catlmodulet)합니다.

##  <a name="registerappid"></a>  CAtlModuleT::RegisterAppId

레지스트리에 exe 파일을 추가합니다.

```
HRESULT RegisterAppId() throw();
```

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="registerserver"></a>  CAtlModuleT::RegisterServer

레지스트리에 서비스를 추가합니다.

```
HRESULT RegisterServer(
    BOOL bRegTypeLib = FALSE,
    const CLSID* pCLSID = NULL) throw();
```

### <a name="parameters"></a>매개 변수

*bRegTypeLib*<br/>
TRUE 이면 형식 라이브러리 등록 됩니다. 기본값은 FALSE입니다.

*pCLSID*<br/>
등록할 개체의 CLSID 가리킵니다. NULL (기본값), 개체 맵의 모든 개체를 등록할 경우.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="unregisterappid"></a>  CAtlModuleT::UnregisterAppId

레지스트리에서 exe 파일을 제거합니다.

```
HRESULT UnregisterAppId() throw();
```

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="unregisterserver"></a>  CAtlModuleT::UnregisterServer

레지스트리에서 서비스를 제거합니다.

```
HRESULT UnregisterServer(
    BOOL bUnRegTypeLib,
    const CLSID* pCLSID = NULL) throw();
```

### <a name="parameters"></a>매개 변수

*bUnRegTypeLib*<br/>
형식 라이브러리 등록을 취소할 수도 이면 TRUE입니다.

*pCLSID*<br/>
등록을 취소할 개체의 CLSID 가리킵니다. 경우 NULL (기본값), 개체 맵의 모든 개체를 등록 취소 됩니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="updateregistryappid"></a>  CAtlModuleT::UpdateRegistryAppId

레지스트리에서 EXE 정보를 업데이트합니다.

```
static HRESULT WINAPI UpdateRegistryAppId(BOOL /* bRegister*/) throw();
```

### <a name="parameters"></a>매개 변수

*bRegister*<br/>
예약됨.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

## <a name="see-also"></a>참고자료

[CAtlModule 클래스](../../atl/reference/catlmodule-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[모듈 클래스](../../atl/atl-module-classes.md)
