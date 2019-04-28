---
title: CComPolyObject 클래스
ms.date: 11/04/2016
f1_keywords:
- CComPolyObject
- ATLCOM/ATL::CComPolyObject
- ATLCOM/ATL::CComPolyObject::CComPolyObject
- ATLCOM/ATL::CComPolyObject::AddRef
- ATLCOM/ATL::CComPolyObject::CreateInstance
- ATLCOM/ATL::CComPolyObject::FinalConstruct
- ATLCOM/ATL::CComPolyObject::FinalRelease
- ATLCOM/ATL::CComPolyObject::QueryInterface
- ATLCOM/ATL::CComPolyObject::Release
- ATLCOM/ATL::CComPolyObject::m_contained
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComPolyObject class
ms.assetid: eaf67c18-e855-48ca-9b15-f1df3106121b
ms.openlocfilehash: a8dbbc06d35d2606cc76e89cc555ba7f8577daa9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62246259"
---
# <a name="ccompolyobject-class"></a>CComPolyObject 클래스

이 클래스는 구현 `IUnknown` 집계 또는 집계 개체에 대 한 합니다.

## <a name="syntax"></a>구문

```
template<class contained>
class CComPolyObject : public IUnknown,
      public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```

#### <a name="parameters"></a>매개 변수

*contained*<br/>
파생 된 클래스 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 하거나 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)처럼 개체에서 지원 하려는 다른 인터페이스 에서도 잘 합니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CComPolyObject::CComPolyObject](#ccompolyobject)|생성자입니다.|
|[CComPolyObject::~CComPolyObject](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CComPolyObject::AddRef](#addref)|개체의 참조 횟수를 증가 시킵니다.|
|[CComPolyObject::CreateInstance](#createinstance)|(정적) 새로 만들 수 있습니다 **CComPolyObject <** `contained` **>** 오버 헤드 없이 개체 [CoCreateInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance)합니다.|
|[CComPolyObject::FinalConstruct](#finalconstruct)|최종 초기화를 수행 `m_contained`합니다.|
|[CComPolyObject::FinalRelease](#finalrelease)|최종 소멸 수행 `m_contained`합니다.|
|[CComPolyObject::QueryInterface](#queryinterface)|요청된 인터페이스에 대한 포인터를 검색합니다.|
|[CComPolyObject::Release](#release)|개체의 참조 횟수를 감소 시킵니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CComPolyObject::m_contained](#m_contained)|대리자 `IUnknown` 개체가 집계 되는 경우 또는 알 수 없는 외부 호출을 `IUnknown` 개체 집계 되지 않은 경우 개체의 합니다.|

## <a name="remarks"></a>설명

`CComPolyObject` 구현 [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) 집계 또는 집계 개체에 대 한 합니다.

인스턴스가 `CComPolyObject` 만들어지면 외부의 값을 알 수 없는 확인란이 선택 되어 있습니다. 이 NULL 이면 `IUnknown` 집계 개체에 대 한 구현 됩니다. 알 수 없는 외부, NULL이 아닌 경우 `IUnknown` 집계 개체에 대해 구현 됩니다.

사용 하는 이점은 `CComPolyObject` 는 둘 다 필요 하지 않는 [CComAggObject](../../atl/reference/ccomaggobject-class.md) 및 [CComObject](../../atl/reference/ccomobject-class.md) 집계 및 집계 경우를 처리 하 여 모듈에서. 단일 `CComPolyObject` 두 경우를 처리 하는 개체입니다. 즉, 모듈에서 vtable의 복사본이 하나만 및 함수의 복사본 하나 존재 합니다. Vtable 큰 경우 현재 모듈 크기가 상당히 줄어들 수 있습니다이 합니다. Vtable이 작은 경우 사용 하는 반면 `CComPolyObject` 집계 또는 집계 개체에 대해 최적화 되어 있지 않으므로 약간 더 큰 모듈 크기를 발생할 수 있습니다는 `CComAggObject` 및 `CComObject`합니다.

DECLARE_POLY_AGGREGATABLE 매크로 개체의 클래스 정의에 지정 된 경우 `CComPolyObject` 개체를 만드는 데 사용할 됩니다. DECLARE_POLY_AGGREGATABLE는 ATL 프로젝트 마법사를 사용 하 여 모든 권한 또는 Internet Explorer 컨트롤을 만드는 경우 자동으로 선언 됩니다.

집계는 경우는 `CComPolyObject` 개체에는 자체 `IUnknown`외부 개체에서 별도 `IUnknown`, 자체 참조 횟수를 유지 관리 합니다. `CComPolyObject` 사용 하 여 [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) 알 수 없는 외부에 위임할 수 있습니다.

집계에 대 한 자세한 내용은 문서를 참조 하세요 [ATL COM 개체 기본 사항](../../atl/fundamentals-of-atl-com-objects.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComPolyObject`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

##  <a name="addref"></a>  CComPolyObject::AddRef

개체의 참조 횟수를 증가 시킵니다.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>반환 값

진단에 유용 하거나 테스트 수 있는 값입니다.

##  <a name="ccompolyobject"></a>  CComPolyObject::CComPolyObject

생성자입니다.

```
CComPolyObject(void* pv);
```

### <a name="parameters"></a>매개 변수

*pv*<br/>
[in] 외부 알 수 없는 경우 개체, 집계 또는 경우에 NULL에 대 한 포인터는 개체가 집계 되지 않은 경우 개체입니다.

### <a name="remarks"></a>설명

초기화 된 `CComContainedObject` 데이터 멤버 [m_contained](#m_contained), 모듈 잠금 횟수를 증가 시킵니다.

소멸자 모듈 잠금 횟수를 줄입니다.

##  <a name="dtor"></a>  CComPolyObject::~CComPolyObject

소멸자입니다.

```
~CComPolyObject();
```

### <a name="remarks"></a>설명

할당 된 모든 리소스를 호출 해제 [FinalRelease](#finalrelease), 및 모듈 잠금 횟수를 줄입니다.

##  <a name="createinstance"></a>  CComPolyObject::CreateInstance

새로 만들 수 있습니다 **CComPolyObject <** `contained` **>** 오버 헤드 없이 개체 [CoCreateInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance)합니다.

```
static HRESULT WINAPI CreateInstance(
    LPUNKNOWN pUnkOuter,
    CComPolyObject<contained>** pp);
```

### <a name="parameters"></a>매개 변수

*pp*<br/>
[out] 에 대 한 포인터를 **CComPolyObject <** `contained` **>** 포인터입니다. 하는 경우 `CreateInstance` 정상적이 지 않습니다 *pp* NULL로 설정 됩니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

반환 되는 개체 참조 개수가 0에 호출 되므로 `AddRef` 즉시 사용 하 여 `Release` 완료 되 면 개체 포인터에 대 한 참조를 해제 하려면.

개체에 대 한 액세스를 직접 필요 하지 않습니다 하지만 여전히 오버 헤드 없이 새 개체를 만들려고 할 경우 `CoCreateInstance`를 사용 하 여 [CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) 대신 합니다.

##  <a name="finalconstruct"></a>  CComPolyObject::FinalConstruct

개체 생성의 최종 단계 중에 호출을이 메서드가 수행 최종 초기화에는 [m_contained](#m_contained) 데이터 멤버입니다.

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

##  <a name="finalrelease"></a>  CComPolyObject::FinalRelease

이 메서드가 개체 소멸 중에 호출을 해제 합니다 [m_contained](#m_contained) 데이터 멤버입니다.

```
void FinalRelease();
```

##  <a name="m_contained"></a>  CComPolyObject::m_contained

A [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) 클래스에서 파생 된 개체입니다.

```
CComContainedObject<contained> m_contained;
```

### <a name="parameters"></a>매개 변수

*contained*<br/>
[in] 파생 된 클래스 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 하거나 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)처럼 개체에서 지원 하려는 다른 인터페이스 에서도 잘 합니다.

### <a name="remarks"></a>설명

`IUnknown` 통해 호출 `m_contained` 개체를 집계 하는 경우 또는 알 수 없는 외부에 위임 되는 `IUnknown` 개체 집계 되지 않은 경우이 개체의 합니다.

##  <a name="queryinterface"></a>  CComPolyObject::QueryInterface

요청된 인터페이스에 대한 포인터를 검색합니다.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT QueryInterface(Q** pp);
```

### <a name="parameters"></a>매개 변수

*Q*<br/>
COM 인터페이스입니다.

*iid*<br/>
[in] 요청 된 인터페이스의 식별자입니다.

*ppvObject*<br/>
[out] 로 식별 되는 인터페이스 포인터에 대 한 포인터 *iid*합니다. 개체는이 인터페이스를 지원 하지 않는 경우 *ppvObject* NULL로 설정 됩니다.

*pp*<br/>
[out] 로 식별 된 인터페이스에 대 한 포인터 `__uuidof(Q)`합니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

요청한 인터페이스가 있으면 집계 된 개체에 대 한 `IUnknown`, `QueryInterface` 집계 개체 자체에 대 한 포인터를 반환 `IUnknown` 참조 횟수를 증가 시킵니다. 이 메서드를 통해 인터페이스에 대 한 쿼리이 고, 그렇지 합니다 `CComContainedObject` 데이터 멤버 [m_contained](#m_contained)합니다.

##  <a name="release"></a>  CComPolyObject::Release

개체의 참조 횟수를 감소 시킵니다.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>반환 값

디버그 빌드에서 `Release` 진단용 유용 하거나 테스트 수 있는 값을 반환 합니다. 비디버그 빌드에서 `Release` 항상 0을 반환 합니다.

## <a name="see-also"></a>참고자료

[CComObjectRootEx 클래스](../../atl/reference/ccomobjectrootex-class.md)<br/>
[DECLARE_POLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_poly_aggregatable)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
