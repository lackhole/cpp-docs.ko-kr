---
title: CComAggObject 클래스
ms.date: 11/04/2016
f1_keywords:
- CComAggObject
- ATLCOM/ATL::CComAggObject
- ATLCOM/ATL::CComAggObject::CComAggObject
- ATLCOM/ATL::CComAggObject::AddRef
- ATLCOM/ATL::CComAggObject::CreateInstance
- ATLCOM/ATL::CComAggObject::FinalConstruct
- ATLCOM/ATL::CComAggObject::FinalRelease
- ATLCOM/ATL::CComAggObject::QueryInterface
- ATLCOM/ATL::CComAggObject::Release
- ATLCOM/ATL::CComAggObject::m_contained
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComAggObject class
ms.assetid: 7aa90d69-d399-477b-880d-e2cdf0ef7881
ms.openlocfilehash: 52cdddb1d922ca21e24122422ca14d9c12d13a83
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62259926"
---
# <a name="ccomaggobject-class"></a>CComAggObject 클래스

이 클래스에서 구현 된 [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) 집계 개체에 대 한 인터페이스입니다. 정의 따라 집계 개체는 외부 개체에 포함 됩니다. 합니다 `CComAggObject` 클래스는 비슷합니다는 [CComObject 클래스](../../atl/reference/ccomobject-class.md)외부 클라이언트에 직접 액세스할 수 있는 인터페이스를 노출 하는 점을 제외 하 고 합니다.

## <a name="syntax"></a>구문

```
template<class contained>
class CComAggObject : public IUnknown,
   public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```

#### <a name="parameters"></a>매개 변수

*contained*<br/>
파생 된 클래스 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 하거나 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)처럼 개체에서 지원 하려는 다른 인터페이스 에서도 잘 합니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CComAggObject::CComAggObject](#ccomaggobject)|생성자입니다.|
|[CComAggObject::~CComAggObject](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CComAggObject::AddRef](#addref)|집계 된 개체의 참조 횟수를 증가 시킵니다.|
|[CComAggObject::CreateInstance](#createinstance)|이 정적 함수를 사용 하면 새를 만들 수 있습니다 **CComAggObject <** `contained` **>** 오버 헤드 없이 개체 [CoCreateInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance)합니다.|
|[CComAggObject::FinalConstruct](#finalconstruct)|최종 초기화를 수행 `m_contained`합니다.|
|[CComAggObject::FinalRelease](#finalrelease)|최종 소멸 수행 `m_contained`합니다.|
|[CComAggObject::QueryInterface](#queryinterface)|요청된 인터페이스에 대한 포인터를 검색합니다.|
|[CComAggObject::Release](#release)|집계 된 개체의 참조 횟수를 감소 시킵니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CComAggObject::m_contained](#m_contained)|대리자 `IUnknown` 알 수 없는 외부 호출 합니다.|

## <a name="remarks"></a>설명

`CComAggObject` 구현 [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) 집계 개체에 대 한 합니다. `CComAggObject` 에 자체 `IUnknown` 인터페이스를 외부 개체의 분리 `IUnknown` 인터페이스 및 자체 참조 횟수를 유지 관리 합니다.

집계에 대 한 자세한 내용은 문서를 참조 하세요 [ATL COM 개체 기본 사항](../../atl/fundamentals-of-atl-com-objects.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComAggObject`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

##  <a name="addref"></a>  CComAggObject::AddRef

집계 된 개체의 참조 횟수를 증가 시킵니다.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>반환 값

진단에 유용 하거나 테스트 수 있는 값입니다.

##  <a name="ccomaggobject"></a>  CComAggObject::CComAggObject

생성자입니다.

```
CComAggObject(void* pv);
```

### <a name="parameters"></a>매개 변수

*pv*<br/>
[in] 외부 알 수 없는 합니다.

### <a name="remarks"></a>설명

초기화 된 `CComContainedObject` 멤버 [m_contained](#m_contained), 모듈 잠금 횟수를 증가 시킵니다.

소멸자 모듈 잠금 횟수를 줄입니다.

##  <a name="dtor"></a>  CComAggObject::~CComAggObject

소멸자입니다.

```
~CComAggObject();
```

### <a name="remarks"></a>설명

할당 된 모든 리소스를 호출 해제 [FinalRelease](#finalrelease), 및 모듈 잠금 횟수를 줄입니다.

##  <a name="createinstance"></a>  CComAggObject::CreateInstance

이 정적 함수를 사용 하면 새를 만들 수 있습니다 **CComAggObject <** `contained` **>** 오버 헤드 없이 개체 [CoCreateInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance)합니다.

```
static HRESULT WINAPI CreateInstance(
    LPUNKNOWN pUnkOuter,
    CComAggObject<contained>** pp);
```

### <a name="parameters"></a>매개 변수

*pp*<br/>
[out] 에 대 한 포인터를 **CComAggObject\<**<em>포함</em> **>** 포인터입니다. 하는 경우 `CreateInstance` 정상적이 지 않습니다 *pp* NULL로 설정 됩니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

반환 되는 개체 참조 개수가 0에 호출 되므로 `AddRef` 즉시 사용 하 여 `Release` 완료 되 면 개체 포인터에 대 한 참조를 해제 하려면.

개체에 대 한 액세스도 직접 필요한 수행 해도 여전히 오버 헤드 없이 새 개체를 만들려고 할 경우 `CoCreateInstance`를 사용 하 여 [CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) 대신 합니다.

##  <a name="finalconstruct"></a>  CComAggObject::FinalConstruct

개체 생성의 최종 단계 중에 호출을이 메서드가 수행 최종 초기화에는 [m_contained](#m_contained) 멤버입니다.

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

##  <a name="finalrelease"></a>  CComAggObject::FinalRelease

이 메서드가 개체 소멸 중에 호출을 해제 합니다 [m_contained](#m_contained) 멤버입니다.

```
void FinalRelease();
```

##  <a name="m_contained"></a>  CComAggObject::m_contained

A [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) 클래스에서 파생 된 개체입니다.

```
CComContainedObject<contained> m_contained;
```

### <a name="parameters"></a>매개 변수

*contained*<br/>
[in] 파생 된 클래스 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 하거나 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)처럼 개체에서 지원 하려는 다른 인터페이스 에서도 잘 합니다.

### <a name="remarks"></a>설명

모든 `IUnknown` 호출을 통해 `m_contained` 알 수 없는 외부 위임 됩니다.

##  <a name="queryinterface"></a>  CComAggObject::QueryInterface

요청된 인터페이스에 대한 포인터를 검색합니다.

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

### <a name="remarks"></a>설명

요청한 인터페이스가 `IUnknown`, `QueryInterface` 집계 개체 자체에 대 한 포인터를 반환 `IUnknown` 참조 횟수를 증가 시킵니다. 이 메서드를 통해 인터페이스에 대 한 쿼리이 고, 그렇지 합니다 `CComContainedObject` 멤버 [m_contained](#m_contained)합니다.

##  <a name="release"></a>  CComAggObject::Release

집계 된 개체의 참조 횟수를 감소 시킵니다.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>반환 값

디버그 빌드에서 `Release` 진단용 유용 하거나 테스트 수 있는 값을 반환 합니다. 디버그가 아닌 빌드에서 `Release` 항상 0을 반환 합니다.

## <a name="see-also"></a>참고자료

[CComObject 클래스](../../atl/reference/ccomobject-class.md)<br/>
[CComPolyObject 클래스](../../atl/reference/ccompolyobject-class.md)<br/>
[DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)<br/>
[DECLARE_ONLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_only_aggregatable)<br/>
[DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
