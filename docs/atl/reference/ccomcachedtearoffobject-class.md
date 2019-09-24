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
ms.openlocfilehash: d993a349d38342bda30a83dfdbe25577953799b3
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497544"
---
# <a name="ccomcachedtearoffobject-class"></a>CComCachedTearOffObject 클래스

이 클래스는 분리 인터페이스에 대해 [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) 을 구현 합니다.

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
에서 파생 된 분리 된 클래스 및 분리 `CComTearOffObjectBase` 개체에서 지원 하도록 할 인터페이스입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CComCachedTearOffObject::CComCachedTearOffObject](#ccomcachedtearoffobject)|생성자입니다.|
|[CComCachedTearOffObject::~CComCachedTearOffObject](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|Description|
|----------|-----------------|
|[CComCachedTearOffObject::AddRef](#addref)|`CComCachedTearOffObject` 개체의 참조 횟수를 증가 시킵니다.|
|[CComCachedTearOffObject::FinalConstruct](#finalconstruct)|(분리 `m_contained::FinalConstruct` 클래스의 메서드)를 호출 합니다.|
|[CComCachedTearOffObject::FinalRelease](#finalrelease)|(분리 `m_contained::FinalRelease` 클래스의 메서드)를 호출 합니다.|
|[CComCachedTearOffObject::QueryInterface](#queryinterface)|개체의에 `IUnknown` 대 한 포인터 또는 분리 클래스 (클래스 `contained`)의 요청 된 인터페이스에 대 한 포인터를 반환 합니다. `CComCachedTearOffObject`|
|[CComCachedTearOffObject::Release](#release)|`CComCachedTearOffObject` 개체의 참조 횟수를 감소 시키고 참조 횟수가 0 인 경우이를 소멸 시킵니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|Description|
|----------|-----------------|
|[CComCachedTearOffObject::m_contained](#m_contained)|떼어내기 클래스 (클래스 `contained`)에서 파생 된 개체입니다.`CComContainedObject`|

## <a name="remarks"></a>설명

`CComCachedTearOffObject`는 중단 인터페이스에 대해 [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) 을 구현 합니다. 이 클래스는 소유자 `CComTearOffObject` 개체의 `CComCachedTearOffObject` `IUnknown` `IUnknown` 자체를 포함 하는의와 다릅니다. 소유자 개체는 분리를 만들 개체입니다. `CComCachedTearOffObject`는 `IUnknown` 의 참조 횟수를 유지 관리 하 고 참조 횟수가 0 이면 자체를 삭제 합니다. 그러나 해당 분리 인터페이스를 쿼리하면 소유자 개체 `IUnknown` 의 참조 횟수가 증가 합니다 .이 경우

종료를 구현 하는 `CComCachedTearOffObject` 개체가이미인스턴스화되고분리인터페이스를다시쿼리하면동일한개체가다시사용됩니다.`CComCachedTearOffObject` 반면에에서 구현 하 `CComTearOffObject` 는 분리 인터페이스를 소유자 개체를 통해 다시 쿼리 하는 경우 다른 `CComTearOffObject` 가 인스턴스화됩니다.

Owner 클래스는에 대해 `FinalRelease` `Release` `IUnknown`캐시된 에서을 구현 하 고를 호출 하 여 참조 횟수 를감소시켜야합니다.`CComCachedTearOffObject` 이 `FinalRelease` 로 인해 `CComCachedTearOffObject`가 호출 되 고 제거를 삭제 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComCachedTearOffObject`

## <a name="requirements"></a>요구 사항

**헤더:**

##  <a name="addref"></a>  CComCachedTearOffObject::AddRef

`CComCachedTearOffObject` 개체의 참조 횟수를 1 씩 증가 시킵니다.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>반환 값

진단 및 테스트에 유용할 수 있는 값입니다.

##  <a name="ccomcachedtearoffobject"></a>  CComCachedTearOffObject::CComCachedTearOffObject

생성자입니다.

```
CComCachedTearOffObject(void* pv);
```

### <a name="parameters"></a>매개 변수

*pv*<br/>
진행 `IUnknown` 의에 대 한 포인터 입니다.`CComCachedTearOffObject`

### <a name="remarks"></a>설명

[M_contained](#m_contained) `CComContainedObject`멤버를 초기화합니다.

##  <a name="dtor"></a>  CComCachedTearOffObject::~CComCachedTearOffObject

소멸자입니다.

```
~CComCachedTearOffObject();
```

### <a name="remarks"></a>설명

할당 된 모든 리소스를 해제 하 고, 전체 [릴리스](#finalrelease)를 호출 합니다.

##  <a name="finalconstruct"></a>  CComCachedTearOffObject::FinalConstruct

만들기 `m_contained::FinalConstruct` `CComContainedObject` < 를 호출 합니다 .이 개체 는`contained`분리 클래스에서 구현 하는 인터페이스에 액세스 하는 데 사용 되는 > 개체입니다. `m_contained`

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

##  <a name="finalrelease"></a>  CComCachedTearOffObject::FinalRelease

> `m_contained::FinalRelease` 개체를 `m_contained`사용 하 `CComContainedObject`여 <  free를호출합니다`contained`.

```
void FinalRelease();
```

##  <a name="m_contained"></a>  CComCachedTearOffObject::m_contained

떼어내기 클래스에서 파생 된 [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) 개체입니다.

```
CcomContainedObject <contained> m_contained;
```

### <a name="parameters"></a>매개 변수

*contained*<br/>
진행 에서 파생 된 분리 된 클래스 및 분리 `CComTearOffObjectBase` 개체에서 지원 하도록 할 인터페이스입니다.

### <a name="remarks"></a>설명

상속 된 `m_contained` 메서드는 캐시 된 분리 개체 `FinalConstruct`의 `QueryInterface`, 및 `FinalRelease`을 통해 분리 된 클래스의 분리 인터페이스에 액세스 하는 데 사용 됩니다.

##  <a name="queryinterface"></a>  CComCachedTearOffObject::QueryInterface

요청된 인터페이스에 대한 포인터를 검색합니다.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>매개 변수

*iid*<br/>
진행 요청 되는 인터페이스의 GUID입니다.

*ppvObject*<br/>
제한이 *Iid*로 식별 되는 인터페이스 포인터에 대 한 포인터 이거나, 인터페이스를 찾을 수 없는 경우 NULL입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

요청 된 인터페이스가 인 `IUnknown`경우는 `CComCachedTearOffObject`자체 `IUnknown` 에 대 한 포인터를 반환 하 고 참조 횟수를 증가 시킵니다. 그렇지 않으면에서 `CComObjectRootEx`상속 된 [internalqueryinterface](ccomobjectrootex-class.md#internalqueryinterface) 메서드를 사용 하 여 분리 클래스에서 인터페이스를 쿼리 합니다.

##  <a name="release"></a>  CComCachedTearOffObject::Release

참조 횟수를 1 씩 감소 시키고 참조 횟수가 0 인 경우 `CComCachedTearOffObject` 개체를 삭제 합니다.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>반환 값

디버그가 아닌 빌드에서는 항상 0을 반환 합니다. 디버그 빌드에서는 진단 또는 테스트에 유용할 수 있는 값을 반환 합니다.

## <a name="see-also"></a>참고자료

[CComTearOffObject 클래스](../../atl/reference/ccomtearoffobject-class.md)<br/>
[CComObjectRootEx 클래스](../../atl/reference/ccomobjectrootex-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
