---
title: CAtlModule 클래스
ms.date: 11/04/2016
f1_keywords:
- CAtlModule
- ATLBASE/ATL::CAtlModule
- ATLBASE/ATL::CAtlModule::CAtlModule
- ATLBASE/ATL::CAtlModule::AddCommonRGSReplacements
- ATLBASE/ATL::CAtlModule::AddTermFunc
- ATLBASE/ATL::CAtlModule::GetGITPtr
- ATLBASE/ATL::CAtlModule::GetLockCount
- ATLBASE/ATL::CAtlModule::Lock
- ATLBASE/ATL::CAtlModule::Term
- ATLBASE/ATL::CAtlModule::Unlock
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceD
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceDHelper
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceS
- ATLBASE/ATL::CAtlModule::m_libid
- ATLBASE/ATL::CAtlModule::m_pGIT
helpviewer_keywords:
- CAtlModule class
ms.assetid: 63fe02f1-4c4b-4e7c-ae97-7ad7b4252415
ms.openlocfilehash: f01734d4ec9de323325dc793756f421388542ef2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62247009"
---
# <a name="catlmodule-class"></a>CAtlModule 클래스

이 클래스는 여러 ATL 모듈 클래스에서 사용 되는 메서드를 제공 합니다.

## <a name="syntax"></a>구문

```
class ATL_NO_VTABLE CAtlModule : public _ATL_MODULE
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CAtlModule::CAtlModule](#catlmodule)|생성자입니다.|
|[CAtlModule::~CAtlModule](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements)|ATL 레지스트리 구성 요소 (등록자) 대체 구조에 매개 변수를 추가 하려면이 메서드를 재정의 합니다.|
|[CAtlModule::AddTermFunc](#addtermfunc)|종료 될 때 호출 되는 새 함수를 추가 합니다.|
|[CAtlModule::GetGITPtr](#getgitptr)|글로벌 인터페이스 포인터를 반환합니다.|
|[CAtlModule::GetLockCount](#getlockcount)|잠금 수를 반환합니다.|
|[CAtlModule::Lock](#lock)|잠금 수를 늘립니다.|
|[CAtlModule::Term](#term)|모든 데이터 멤버를 해제합니다.|
|[CAtlModule::Unlock](#unlock)|잠금 횟수를 줄입니다.|
|[CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced)|등록 또는 개체를 등록 취소는 지정 된 리소스가 포함 된 스크립트를 실행 합니다.|
|[CAtlModule::UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper)|이 메서드는 `UpdateRegistryFromResourceD` 레지스트리 업데이트를 수행 합니다.|
|[CAtlModule::UpdateRegistryFromResourceS](#updateregistryfromresources)|등록 또는 개체를 등록 취소는 지정 된 리소스가 포함 된 스크립트를 실행 합니다. 이 메서드는 정적으로 ATL 레지스트리 구성 요소를 연결합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CAtlModule::m_libid](#m_libid)|현재 모듈의 GUID를 포함 합니다.|
|[CAtlModule::m_pGIT](#m_pgit)|전역 인터페이스 테이블에 대 한 포인터입니다.|

## <a name="remarks"></a>설명

이 클래스에서 사용 됩니다 [CAtlDllModuleT 클래스](../../atl/reference/catldllmodulet-class.md)를 [CAtlExeModuleT 클래스](../../atl/reference/catlexemodulet-class.md), 및 [CAtlServiceModuleT 클래스](../../atl/reference/catlservicemodulet-class.md) DLL 응용 프로그램, EXE 응용 프로그램에 대 한 지원을 제공 하 고 Windows 서비스, 각각.

ATL에서 모듈에 대 한 자세한 내용은 참조 하세요. [ATL 모듈 클래스](../../atl/atl-module-classes.md)합니다.

이 클래스는 사용 되지 않는 대체 [CComModule 클래스](../../atl/reference/ccommodule-class.md) ATL.의 이전 버전에서 사용

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[_ATL_MODULE](atl-typedefs.md#_atl_module)

`CAtlModule`

## <a name="requirements"></a>요구 사항

**헤더:** atlbase.h

##  <a name="addcommonrgsreplacements"></a>  CAtlModule::AddCommonRGSReplacements

ATL 레지스트리 구성 요소 (등록자) 대체 구조에 매개 변수를 추가 하려면이 메서드를 재정의 합니다.

```
virtual HRESULT AddCommonRGSReplacements(IRegistrarBase* /* pRegistrar*/) throw() = 0;
```

### <a name="parameters"></a>매개 변수

*pRegistrar*<br/>
예약됨.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

대체 가능 매개 변수는 런타임 데이터를 지정 하는 등록자의 클라이언트를 허용 합니다. 이렇게 하려면 등록자에 스크립트에서 대체 가능 매개 변수를 사용 하 여 관련 된 값을 입력 하는 대체 맵을 유지 관리 합니다. 등록 기관은 런타임 시 이러한 항목을 만듭니다.

항목을 참조 하세요 [를 사용 하 여 대체 가능 매개 변수 (The 등록자 전처리기)](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) 대 한 자세한 내용은 합니다.

##  <a name="addtermfunc"></a>  CAtlModule::AddTermFunc

종료 될 때 호출 되는 새 함수를 추가 합니다.

```
HRESULT AddTermFunc(_ATL_TERMFUNC* pFunc, DWORD_PTR dw) throw();
```

### <a name="parameters"></a>매개 변수

*pFunc*<br/>
추가할 함수에 대 한 포인터입니다.

*dw*<br/>
사용자 정의 데이터를 함수에 전달 합니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

##  <a name="catlmodule"></a>  CAtlModule::CAtlModule

생성자입니다.

```
CAtlModule() throw();
```

### <a name="remarks"></a>설명

데이터 멤버를 초기화 하 고 모듈의 스레드 관련 중요 섹션을 시작 합니다.

##  <a name="dtor"></a>  CAtlModule::~CAtlModule

소멸자입니다.

```
~CAtlModule() throw();
```

### <a name="remarks"></a>설명

모든 데이터 멤버를 해제합니다.

##  <a name="getgitptr"></a>  CAtlModule::GetGITPtr

전역 인터페이스 테이블에 대 한 포인터를 검색합니다.

```
virtual HRESULT GetGITPtr(IGlobalInterfaceTable** ppGIT) throw();
```

### <a name="parameters"></a>매개 변수

*ppGIT*<br/>
전역 인터페이스 테이블에 대 한 포인터를 수신 하는 변수에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 코드를 반환합니다. E_POINTER 반환 됩니다 *ppGIT* NULL과 같습니다.

### <a name="remarks"></a>설명

전역 인터페이스 테이블 개체가 존재 하지 않는, 만들어진 해당 주소를 멤버 변수에 저장 되어 있으면 [CAtlModule::m_pGIT](#m_pgit)합니다.

디버그 빌드에서 어설션 오류가 발생 하는 경우 *ppGIT* NULL로 같은지 아니면 전역 인터페이스 테이블 포인터를 가져올 수 없습니다.

참조 [IGlobalInterfaceTable](/windows/desktop/api/objidl/nn-objidl-iglobalinterfacetable) 전역 인터페이스 테이블에 대 한 정보에 대 한 합니다.

##  <a name="getlockcount"></a>  CAtlModule::GetLockCount

잠금 수를 반환합니다.

```
virtual LONG GetLockCount() throw();
```

### <a name="return-value"></a>반환 값

잠금 수를 반환합니다. 이 값은 진단에 유용 하 고 디버깅 수 있습니다.

##  <a name="lock"></a>  CAtlModule::Lock

잠금 수를 늘립니다.

```
virtual LONG Lock() throw();
```

### <a name="return-value"></a>반환 값

잠금 수를 증가 하 고 업데이트 된 값을 반환 합니다. 이 값은 진단에 유용 하 고 디버깅 수 있습니다.

##  <a name="m_libid"></a>  CAtlModule::m_libid

현재 모듈의 GUID를 포함 합니다.

```
static GUID m_libid;
```

##  <a name="m_pgit"></a>  CAtlModule::m_pGIT

전역 인터페이스 테이블에 대 한 포인터입니다.

```
IGlobalInterfaceTable* m_pGIT;
```

##  <a name="term"></a>  CAtlModule::Term

모든 데이터 멤버를 해제합니다.

```
void Term() throw();
```

### <a name="remarks"></a>설명

모든 데이터 멤버를 해제합니다. 이 메서드는 소멸자에서 호출 됩니다.

##  <a name="unlock"></a>  CAtlModule::Unlock

잠금 횟수를 줄입니다.

```
virtual LONG Unlock() throw();
```

### <a name="return-value"></a>반환 값

잠금 횟수를 줄입니다 업데이트 된 값을 반환 합니다. 이 값은 진단에 유용 하 고 디버깅 수 있습니다.

##  <a name="updateregistryfromresourced"></a>  CAtlModule::UpdateRegistryFromResourceD

등록 또는 개체를 등록 취소는 지정 된 리소스가 포함 된 스크립트를 실행 합니다.

```
HRESULT WINAPI UpdateRegistryFromResourceD(
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

HRESULT WINAPI UpdateRegistryFromResourceD(
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```

### <a name="parameters"></a>매개 변수

*lpszRes*<br/>
리소스 이름입니다.

*nResID*<br/>
리소스 id입니다.

*bRegister*<br/>
TRUE 이면 개체를 등록 해야 합니다. FALSE이 고, 그렇지 합니다.

*pMapEntries*<br/>
스크립트의 대체 가능 매개 변수를 사용 하 여 연결 된 값을 저장 대체 지도에 대 한 포인터입니다. ATL 모듈 % 보기를 자동으로 사용합니다. 참조 추가 대체 가능 매개 변수를 사용 하려면 [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements)합니다. 그렇지 않으면 NULL 기본값을 사용 합니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

지정 하는 리소스가 포함 된 스크립트 실행 *lpszRes 또는 nResID*합니다. 하는 경우 *b 등록 하십시오* 가 TRUE 인 레지스트리에서 개체를 제거 하는 고, 그렇지 않으면이 메서드는 개체가 시스템 레지스트리에 등록 합니다.

ATL 레지스트리 구성 요소 (등록자)에 정적으로 링크를 참조 하세요 [CAtlModule::UpdateRegistryFromResourceS](#updateregistryfromresources)합니다.

이 메서드를 호출 [CAtlModule::UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper) 하 고 [IRegistrar::ResourceUnregister](iregistrar-class.md#resourceunregister)합니다.

##  <a name="updateregistryfromresourcedhelper"></a>  CAtlModule::UpdateRegistryFromResourceDHelper

이 메서드는 `UpdateRegistryFromResourceD` 레지스트리 업데이트를 수행 합니다.

```
inline HRESULT WINAPI UpdateRegistryFromResourceDHelper(
    LPCOLESTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```

### <a name="parameters"></a>매개 변수

*lpszRes*<br/>
리소스 이름입니다.

*bRegister*<br/>
개체를 등록할지 여부를 나타냅니다.

*pMapEntries*<br/>
스크립트의 대체 가능 매개 변수를 사용 하 여 연결 된 값을 저장 대체 지도에 대 한 포인터입니다. ATL 모듈 % 보기를 자동으로 사용합니다. 참조 추가 대체 가능 매개 변수를 사용 하려면 [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements)합니다. 그렇지 않으면 NULL 기본값을 사용 합니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

이 방법은 제공 구현의 [CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced)합니다.

##  <a name="updateregistryfromresources"></a>  CAtlModule::UpdateRegistryFromResourceS

등록 또는 개체를 등록 취소는 지정 된 리소스가 포함 된 스크립트를 실행 합니다. 이 메서드는 정적으로 ATL 레지스트리 구성 요소를 연결합니다.

```
HRESULT WINAPI UpdateRegistryFromResourceS(
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

HRESULT WINAPI UpdateRegistryFromResourceS(
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```

### <a name="parameters"></a>매개 변수

*nResID*<br/>
리소스 id입니다.

*lpszRes*<br/>
리소스 이름입니다.

*bRegister*<br/>
리소스 스크립트를 등록할지 여부를 나타냅니다.

*pMapEntries*<br/>
스크립트의 대체 가능 매개 변수를 사용 하 여 연결 된 값을 저장 대체 지도에 대 한 포인터입니다. ATL 모듈 % 보기를 자동으로 사용합니다. 참조 추가 대체 가능 매개 변수를 사용 하려면 [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements)합니다. 그렇지 않으면 NULL 기본값을 사용 합니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고, 또는 실패 시 오류 HRESULT 반환합니다.

### <a name="remarks"></a>설명

비슷합니다 [CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced) 제외한 `CAtlModule::UpdateRegistryFromResourceS` ATL 레지스트리 구성 요소 (등록자)에 정적 링크를 만듭니다.

## <a name="see-also"></a>참고자료

[_ATL_MODULE](atl-typedefs.md#_atl_module)<br/>
[클래스 개요](../../atl/atl-class-overview.md)<br/>
[모듈 클래스](../../atl/atl-module-classes.md)<br/>
[레지스트리 구성 요소 (등록자)](../../atl/atl-registry-component-registrar.md)
