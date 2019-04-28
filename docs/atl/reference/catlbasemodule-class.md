---
title: CAtlBaseModule 클래스
ms.date: 11/04/2016
f1_keywords:
- CAtlBaseModule
- ATLCORE/ATL::CAtlBaseModule
- ATLCORE/ATL::CAtlBaseModule::CAtlBaseModule
- ATLCORE/ATL::CAtlBaseModule::AddResourceInstance
- ATLCORE/ATL::CAtlBaseModule::GetHInstanceAt
- ATLCORE/ATL::CAtlBaseModule::GetModuleInstance
- ATLCORE/ATL::CAtlBaseModule::GetResourceInstance
- ATLCORE/ATL::CAtlBaseModule::RemoveResourceInstance
- ATLCORE/ATL::CAtlBaseModule::SetResourceInstance
- ATLCORE/ATL::CAtlBaseModule::m_bInitFailed
helpviewer_keywords:
- CAtlBaseModule class
ms.assetid: 55ade80c-9b0c-4c51-933e-2158436c1096
ms.openlocfilehash: d382d1fe7d50a2fdeefc9b477625580792de7d6f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62247154"
---
# <a name="catlbasemodule-class"></a>CAtlBaseModule 클래스

이 클래스는 모든 ATL 프로젝트에서 인스턴스화됩니다.

## <a name="syntax"></a>구문

```
class CAtlBaseModule : public _ATL_BASE_MODULE
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CAtlBaseModule::CAtlBaseModule](#catlbasemodule)|생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CAtlBaseModule::AddResourceInstance](#addresourceinstance)|리소스 인스턴스를 저장된 핸들 목록에 추가합니다.|
|[CAtlBaseModule::GetHInstanceAt](#gethinstanceat)|지정 된 리소스 인스턴스에 대 한 핸들을 반환합니다.|
|[CAtlBaseModule::GetModuleInstance](#getmoduleinstance)|모듈 인스턴스를 반환을 `CAtlBaseModule` 개체입니다.|
|[CAtlBaseModule::GetResourceInstance](#getresourceinstance)|리소스 인스턴스를 반환을 `CAtlBaseModule` 개체입니다.|
|[CAtlBaseModule::RemoveResourceInstance](#removeresourceinstance)|저장 된 핸들의 목록에서 리소스 인스턴스를 제거합니다.|
|[CAtlBaseModule::SetResourceInstance](#setresourceinstance)|리소스 인스턴스의 집합을 `CAtlBaseModule` 개체입니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CAtlBaseModule::m_bInitFailed](#m_binitfailed)|모듈 초기화 실패 한 나타내는 변수입니다.|

## <a name="remarks"></a>설명

인스턴스의 `CAtlBaseModule` 명명된 _AtlBaseModule 모듈 인스턴스에 대 한 핸들, 기본 제공 모듈에 대 한 핸들의 배열 및 리소스 (기본적으로 동일)을 포함 하는 모듈에 대 한 핸들을 포함 하는 모든 ATL 프로젝트에 있습니다. 리소스입니다. `CAtlBaseModule` 수 여러 스레드에서 안전 하 게 액세스할 수 있습니다.

이 클래스는 사용 되지 않는 대체 [CComModule](../../atl/reference/ccommodule-class.md) ATL.의 이전 버전에서 사용 되는 클래스

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module)

`CAtlBaseModule`

## <a name="requirements"></a>요구 사항

**헤더:** atlcore.h

##  <a name="addresourceinstance"></a>  CAtlBaseModule::AddResourceInstance

리소스 인스턴스를 저장된 핸들 목록에 추가합니다.

```
bool AddResourceInstance(HINSTANCE hInst) throw();
```

### <a name="parameters"></a>매개 변수

*hInst*<br/>
추가할 리소스 인스턴스입니다.

### <a name="return-value"></a>반환 값

리소스가 성공적으로 되었으면 true를 반환 합니다 추가 false이 고, 그렇지입니다.

##  <a name="catlbasemodule"></a>  CAtlBaseModule::CAtlBaseModule

생성자입니다.

```
CAtlBaseModule() throw();
```

### <a name="remarks"></a>설명

`CAtlBaseModule`를 만듭니다.

##  <a name="gethinstanceat"></a>  CAtlBaseModule::GetHInstanceAt

지정 된 리소스 인스턴스에 대 한 핸들을 반환합니다.

```
HINSTANCE GetHInstanceAt(int i) throw();
```

### <a name="parameters"></a>매개 변수

*i*<br/>
리소스 인스턴스의 수입니다.

### <a name="return-value"></a>반환 값

해당 리소스 인스턴스가 없는 경우 리소스 인스턴스 또는 NULL에 핸들을 반환 합니다.

##  <a name="getmoduleinstance"></a>  CAtlBaseModule::GetModuleInstance

모듈 인스턴스를 반환을 `CAtlBaseModule` 개체입니다.

```
HINSTANCE GetModuleInstance() throw();
```

### <a name="return-value"></a>반환 값

모듈 인스턴스를 반환합니다.

##  <a name="getresourceinstance"></a>  CAtlBaseModule::GetResourceInstance

리소스 인스턴스를 반환합니다.

```
HINSTANCE GetResourceInstance() throw();
```

### <a name="return-value"></a>반환 값

리소스 인스턴스를 반환합니다.

##  <a name="m_binitfailed"></a>  CAtlBaseModule::m_bInitFailed

모듈 초기화 실패 한 나타내는 변수입니다.

```
static bool m_bInitFailed;
```

### <a name="remarks"></a>설명

모듈 초기화 true, false 초기화에 실패 한 경우.

##  <a name="removeresourceinstance"></a>  CAtlBaseModule::RemoveResourceInstance

저장 된 핸들의 목록에서 리소스 인스턴스를 제거합니다.

```
bool RemoveResourceInstance(HINSTANCE hInst) throw();
```

### <a name="parameters"></a>매개 변수

*hInst*<br/>
제거할 리소스 인스턴스입니다.

### <a name="return-value"></a>반환 값

그렇지 않으면 리소스를 제거 했습니다.이 고, false true를 반환 합니다.

##  <a name="setresourceinstance"></a>  CAtlBaseModule::SetResourceInstance

리소스 인스턴스의 집합을 `CAtlBaseModule` 개체입니다.

```
HINSTANCE SetResourceInstance(HINSTANCE hInst) throw();
```

### <a name="parameters"></a>매개 변수

*hInst*<br/>
새 리소스 인스턴스입니다.

### <a name="return-value"></a>반환 값

업데이트 된 리소스 인스턴스를 반환합니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)<br/>
[모듈 클래스](../../atl/atl-module-classes.md)
