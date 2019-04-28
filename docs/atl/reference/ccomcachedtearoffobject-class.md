---
title: CComCachedTearOffObject 클래스
ms.date: 11/04/2016
f1_keywords:
- CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject::CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject::AddRef
- ATLCOM/ATL::CComCachedTearOffObject::FinalConstruct
- ATLCOM/ATL::CComCachedTearOffObject::FinalRelease
- ATLCOM/ATL::CComCachedTearOffObject::QueryInterface
- ATLCOM/ATL::CComCachedTearOffObject::Release
- ATLCOM/ATL::CComCachedTearOffObject::m_contained
helpviewer_keywords:
- cache, ATL cached tear-off objects
- CComCachedTearOffObject class
ms.assetid: ae19507d-a1de-4dbc-a988-da9f75a50c95
ms.openlocfilehash: fb7821da03e1ca69c850fa1a295851faf4af4c5b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62259679"
---
# <a name="ccomcachedtearoffobject-class"></a>CComCachedTearOffObject 클래스

이 클래스는 구현 [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) 분리 인터페이스입니다.

## <a name="syntax"></a>구문

```
template
<class contained>
class CComCachedTearOffObject : public
    IUnknown,
public CComObjectRootEx<contained
::_ThreadModel::ThreadModelNoCS>
```

#### <a name="parameters"></a>매개 변수

*contained*<br/>
분리 막대가 클래스에서 파생 된 `CComTearOffObjectBase` 고 인터페이스를 지원 하기 위해 분리 개체입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CComCachedTearOffObject::CComCachedTearOffObject](#ccomcachedtearoffobject)|생성자입니다.|
|[CComCachedTearOffObject::~CComCachedTearOffObject](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CComCachedTearOffObject::AddRef](#addref)|에 대 한 참조 횟수를 증가 `CComCachedTearOffObject` 개체입니다.|
|[CComCachedTearOffObject::FinalConstruct](#finalconstruct)|호출 된 `m_contained::FinalConstruct` (분리 클래스의 메서드).|
|[CComCachedTearOffObject::FinalRelease](#finalrelease)|호출 된 `m_contained::FinalRelease` (분리 클래스의 메서드).|
|[CComCachedTearOffObject::QueryInterface](#queryinterface)|에 대 한 포인터를 반환 합니다 `IUnknown` 의 `CComCachedTearOffObject` 개체 또는 분리 클래스에 대해 요청된 된 인터페이스에 (클래스 `contained`).|
|[CComCachedTearOffObject::Release](#release)|에 대 한 참조 횟수를 감소는 `CComCachedTearOffObject` 개체 및 참조 횟수가 0 이면 삭제 합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CComCachedTearOffObject::m_contained](#m_contained)|A `CComContainedObject` 분리 클래스에서 파생 된 개체 (클래스 `contained`).|

## <a name="remarks"></a>설명

`CComCachedTearOffObject` 구현 [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) 분리 인터페이스입니다. 이 클래스에서 다른 `CComTearOffObject` 한다는 점에서 `CComCachedTearOffObject` 에 자체 `IUnknown`소유자 개체와에서는 별도로 `IUnknown` (소유자는의 분리는 생성 되는 개체를가 하는 데 사용). `CComCachedTearOffObject` 자체 유지 관리 참조 횟수에 해당 `IUnknown` 참조 횟수가 0이 되 면 자체를 삭제 합니다. 그러나 해당 분리 중 하나에 대 한 쿼리 하는 경우 인터페이스를 소유자 개체의 참조 횟수 `IUnknown` 증가 됩니다.

경우는 `CComCachedTearOffObject` 개체를 분리 구현 이미 인스턴스화된 분리 인터페이스를 쿼리 하는 마찬가지로 동일한 `CComCachedTearOffObject` 개체 다시 사용 됩니다. 반대로, 분리 인터페이스를 구현한 경우에 `CComTearOffObject` 다시 쿼리 하는 소유자 개체를 통해 다른 `CComTearOffObject` 인스턴스화됩니다.

소유자 클래스를 구현 해야 합니다 `FinalRelease` 호출 `Release` 에서 캐시 된 `IUnknown` 에 대 한는 `CComCachedTearOffObject`는 참조 횟수를 감소 됩니다. 그러면 `CComCachedTearOffObject`의 `FinalRelease` 호출할 및 삭제를 분리 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComCachedTearOffObject`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

##  <a name="addref"></a>  CComCachedTearOffObject::AddRef

참조 횟수를 증가 `CComCachedTearOffObject` 1만 개체입니다.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>반환 값

진단에 유용 하 고 테스트 될 수 있는 값입니다.

##  <a name="ccomcachedtearoffobject"></a>  CComCachedTearOffObject::CComCachedTearOffObject

생성자입니다.

```
CComCachedTearOffObject(void* pv);
```

### <a name="parameters"></a>매개 변수

*pv*<br/>
[in] 에 대 한 포인터를 `IUnknown` 의 `CComCachedTearOffObject`합니다.

### <a name="remarks"></a>설명

초기화 된 `CComContainedObject` 멤버 [m_contained](#m_contained)합니다.

##  <a name="dtor"></a>  CComCachedTearOffObject::~CComCachedTearOffObject

소멸자입니다.

```
~CComCachedTearOffObject();
```

### <a name="remarks"></a>설명

할당 된 모든 리소스 및 호출을 해제 [FinalRelease](#finalrelease)합니다.

##  <a name="finalconstruct"></a>  CComCachedTearOffObject::FinalConstruct

호출 `m_contained::FinalConstruct` 만들려는 `m_contained`서 `CComContainedObject` <  `contained`> 분리 클래스에서 구현 된 인터페이스에 액세스 하는 데 사용 되는 개체입니다.

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

##  <a name="finalrelease"></a>  CComCachedTearOffObject::FinalRelease

호출 `m_contained::FinalRelease` 무료 `m_contained`서 `CComContainedObject` <  `contained`> 개체입니다.

```
void FinalRelease();
```

##  <a name="m_contained"></a>  CComCachedTearOffObject::m_contained

A [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) 분리 클래스에서 파생 된 개체입니다.

```
CcomContainedObject <contained> m_contained;
```

### <a name="parameters"></a>매개 변수

*contained*<br/>
[in] 분리 막대가 클래스에서 파생 된 `CComTearOffObjectBase` 고 인터페이스를 지원 하기 위해 분리 개체입니다.

### <a name="remarks"></a>설명

메서드 `m_contained` 상속 개체를 통해 캐시 된 분리의 분리 클래스에서 분리 인터페이스에 액세스 하는 데 사용 됩니다 `QueryInterface`를 `FinalConstruct`, 및 `FinalRelease`합니다.

##  <a name="queryinterface"></a>  CComCachedTearOffObject::QueryInterface

요청된 인터페이스에 대한 포인터를 검색합니다.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>매개 변수

*iid*<br/>
[in] 요청 된 인터페이스의 GUID입니다.

*ppvObject*<br/>
[out] 로 식별 되는 인터페이스 포인터에 대 한 포인터 *iid*, 또는 인터페이스를 찾을 수 없으면 NULL입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

요청한 인터페이스가 `IUnknown`에 대 한 포인터를 반환 합니다는 `CComCachedTearOffObject`의 자체 `IUnknown` 참조 횟수를 증가 시킵니다. 그렇지 않은 경우 사용 하 여 분리 클래스에서 인터페이스에 대 한 쿼리를 [InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface) 에서 상속 된 메서드 `CComObjectRootEx`합니다.

##  <a name="release"></a>  CComCachedTearOffObject::Release

참조 횟수를 1 씩 감소 하 고, 참조 횟수가 0 이면 삭제를 `CComCachedTearOffObject` 개체입니다.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>반환 값

디버그가 아닌 빌드에서 항상 0을 반환 합니다. 디버그 빌드에서 진단에 유용 하거나 테스트 수 있는 값을 반환 합니다.

## <a name="see-also"></a>참고자료

[CComTearOffObject 클래스](../../atl/reference/ccomtearoffobject-class.md)<br/>
[CComObjectRootEx 클래스](../../atl/reference/ccomobjectrootex-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
