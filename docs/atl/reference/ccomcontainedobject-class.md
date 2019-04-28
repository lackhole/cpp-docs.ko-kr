---
title: CComContainedObject 클래스
ms.date: 11/04/2016
f1_keywords:
- CComContainedObject
- ATLCOM/ATL::CComContainedObject
- ATLCOM/ATL::CComContainedObject::CComContainedObject
- ATLCOM/ATL::CComContainedObject::AddRef
- ATLCOM/ATL::CComContainedObject::GetControllingUnknown
- ATLCOM/ATL::CComContainedObject::QueryInterface
- ATLCOM/ATL::CComContainedObject::Release
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComContainedObject class
ms.assetid: e8616b41-c200-47b8-bf2c-fb9f713ebdad
ms.openlocfilehash: 15ea9be2a3576081901c9e744d89d33688fe838a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62259514"
---
# <a name="ccomcontainedobject-class"></a>CComContainedObject 클래스

이 클래스는 구현 [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) 소유자 개체에 위임 하 여 `IUnknown`입니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<class Base>
class CComContainedObject : public Base
```

#### <a name="parameters"></a>매개 변수

*Base*<br/>
파생 된 클래스 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 하거나 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)합니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CComContainedObject::CComContainedObject](#ccomcontainedobject)|생성자입니다. 멤버에 대 한 포인터로 소유자 개체의 초기화 `IUnknown`합니다.|
|[CComContainedObject::~CComContainedObject](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CComContainedObject::AddRef](#addref)|소유자 개체의 참조 횟수를 증가 시킵니다.|
|[CComContainedObject::GetControllingUnknown](#getcontrollingunknown)|소유자 개체의 검색 `IUnknown`합니다.|
|[CComContainedObject::QueryInterface](#queryinterface)|소유자 개체에서 요청한 인터페이스에 대 한 포인터를 검색 합니다.|
|[CComContainedObject::Release](#release)|소유자 개체의 참조 횟수를 감소 시킵니다.|

## <a name="remarks"></a>설명

ATL 사용 `CComContainedObject` 클래스의 [CComAggObject](../../atl/reference/ccomaggobject-class.md)를 [CComPolyObject](../../atl/reference/ccompolyobject-class.md), 및 [CComCachedTearOffObject](../../atl/reference/ccomcachedtearoffobject-class.md)합니다. `CComContainedObject` 구현 [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) 소유자 개체에 위임 하 여 `IUnknown`입니다. (소유자 개체 또는 집계의 외부 개체는 분리 인터페이스는 생성 되는 개체입니다.) `CComContainedObject` 호출 `CComObjectRootEx`의 `OuterQueryInterface`를 `OuterAddRef`, 및 `OuterRelease`를 통해 상속 된 모든, `Base`합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`Base`

`CComContainedObject`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

##  <a name="addref"></a>  CComContainedObject::AddRef

소유자 개체의 참조 횟수를 증가 시킵니다.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>반환 값

진단에 유용 하거나 테스트 수 있는 값입니다.

##  <a name="ccomcontainedobject"></a>  CComContainedObject::CComContainedObject

생성자입니다.

```
CComContainedObject(void* pv);
```

### <a name="parameters"></a>매개 변수

*pv*<br/>
[in] 소유자 개체의 `IUnknown`합니다.

### <a name="remarks"></a>설명

집합의 `m_pOuterUnknown` 멤버 포인터 (통해 상속 합니다 `Base` 클래스)를 *pv*.

##  <a name="dtor"></a>  CComContainedObject::~CComContainedObject

소멸자입니다.

```
~CComContainedObject();
```

### <a name="remarks"></a>설명

할당 된 모든 리소스를 해제합니다.

##  <a name="getcontrollingunknown"></a>  CComContainedObject::GetControllingUnknown

반환 된 `m_pOuterUnknown` 멤버 포인터 (통해 상속를 *자료* 클래스) 소유자 개체를 보유 하는 `IUnknown`.

```
IUnknown* GetControllingUnknown();
```

### <a name="return-value"></a>반환 값

소유자 개체의 `IUnknown`합니다.

### <a name="remarks"></a>설명

이 메서드는 가상 일 수 있음 경우 `Base` 선언에 [DECLARE_GET_CONTROLLING_UNKNOWN](aggregation-and-class-factory-macros.md#declare_get_controlling_unknown) 매크로입니다.

##  <a name="queryinterface"></a>  CComContainedObject::QueryInterface

소유자 개체에서 요청한 인터페이스에 대 한 포인터를 검색 합니다.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT STDMETHODCALLTYPE QueryInterface(Q** pp);
```

### <a name="parameters"></a>매개 변수

*iid*<br/>
[in] 요청 된 인터페이스의 식별자입니다.

*ppvObject*<br/>
[out] 로 식별 되는 인터페이스 포인터에 대 한 포인터 *iid*합니다. 개체는이 인터페이스를 지원 하지 않는 경우 *ppvObject* NULL로 설정 됩니다.

*pp*<br/>
[out] 형식별로 식별 된 인터페이스 포인터에 `Q`입니다. 개체는이 인터페이스를 지원 하지 않는 경우 *pp* NULL로 설정 됩니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

##  <a name="release"></a>  CComContainedObject::Release

소유자 개체의 참조 횟수를 감소 시킵니다.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>반환 값

디버그 빌드에서 `Release` 진단용 유용 하거나 테스트 수 있는 값을 반환 합니다. 디버그가 아닌 빌드에서 `Release` 항상 0을 반환 합니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)
