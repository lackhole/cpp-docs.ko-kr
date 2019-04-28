---
title: CComObject 클래스
ms.date: 11/04/2016
f1_keywords:
- CComObject
- ATLCOM/ATL::CComObject
- ATLCOM/ATL::CComObject::CComObject
- ATLCOM/ATL::CComObject::AddRef
- ATLCOM/ATL::CComObject::CreateInstance
- ATLCOM/ATL::CComObject::QueryInterface
- ATLCOM/ATL::CComObject::Release
helpviewer_keywords:
- CComObject class
ms.assetid: e2b6433b-6349-4749-b4bc-acbd7a22c8b0
ms.openlocfilehash: 045292e4d06b1e86e991a755b267660b72a178da
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62246341"
---
# <a name="ccomobject-class"></a>CComObject 클래스

이 클래스는 구현 `IUnknown` 집계 개체에 대 한 합니다.

## <a name="syntax"></a>구문

```
template<class Base>
class CComObject : public Base
```

#### <a name="parameters"></a>매개 변수

*Base*<br/>
파생 된 클래스 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 하거나 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)처럼 개체에서 지원 하려는 다른 인터페이스 에서도 잘 합니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CComObject::CComObject](#ccomobject)|생성자입니다.|
|[CComObject::~CComObject](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CComObject::AddRef](#addref)|개체의 참조 횟수를 증가 시킵니다.|
|[CComObject::CreateInstance](#createinstance)|(정적) 새 `CComObject` 개체입니다.|
|[CComObject::QueryInterface](#queryinterface)|요청된 인터페이스에 대한 포인터를 검색합니다.|
|[CComObject::Release](#release)|개체의 참조 횟수를 감소 시킵니다.|

## <a name="remarks"></a>설명

`CComObject` 구현 [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) 집계 개체에 대 한 합니다. 그러나 호출 `QueryInterface`, `AddRef`, 및 `Release` 위임 됩니다 `CComObjectRootEx`합니다.

사용에 대 한 자세한 내용은 `CComObject`, 문서를 참조 하세요 [ATL COM 개체 기본 사항](../../atl/fundamentals-of-atl-com-objects.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`Base`

`CComObject`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

##  <a name="addref"></a>  CComObject::AddRef

개체의 참조 횟수를 증가 시킵니다.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>반환 값

이 함수는 개체에 새 증가 참조 횟수를 반환합니다. 이 값은 진단 또는 테스트에 유용할 수 있습니다.

##  <a name="ccomobject"></a>  CComObject::CComObject

생성자는 모듈 잠금 수를 늘립니다.

```
CComObject(void* = NULL);
```

### <a name="parameters"></a>매개 변수

<em>void\*</em><br/>
[in] 이 명명 되지 않은 매개 변수 사용 되지 않습니다. 다른 대칭에 대 한 존재 `CComXXXObjectXXX` 생성자입니다.

### <a name="remarks"></a>설명

소멸자 감소 것입니다.

경우는 `CComObject`-파생된 개체를 사용 하 여 성공적으로 생성 되는 **새** 연산자 초기 참조 개수는 0입니다. 참조 횟수를 적절 한 값 (1)을 설정 하려면에 대 한 호출을 확인 합니다 [AddRef](#addref) 함수입니다.

##  <a name="dtor"></a>  CComObject::~CComObject

소멸자입니다.

```
CComObject();
```

### <a name="remarks"></a>설명

할당 된 모든 리소스를 호출 해제 [FinalRelease](ccomobjectrootex-class.md#finalrelease), 및 모듈 잠금 횟수를 줄입니다.

##  <a name="createinstance"></a>  CComObject::CreateInstance

이 정적 함수를 사용 하면 새를 만들 수 있습니다 **CComObject <** `Base` **>** 오버 헤드 없이 개체 [CoCreateInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance)합니다.

```
static HRESULT WINAPI CreateInstance(CComObject<Base>** pp);
```

### <a name="parameters"></a>매개 변수

*pp*<br/>
[out] 에 대 한 포인터를 **CComObject <** `Base` **>** 포인터입니다. 하는 경우 `CreateInstance` 정상적이 지 않습니다 *pp* NULL로 설정 됩니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

반환 되는 개체 참조 개수가 0에 호출 되므로 `AddRef` 즉시 사용 하 여 `Release` 완료 되 면 개체 포인터에 대 한 참조를 해제 하려면.

개체에 대 한 액세스도 직접 필요한 수행 해도 여전히 오버 헤드 없이 새 개체를 만들려고 할 경우 `CoCreateInstance`를 사용 하 여 [CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) 대신 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#38](../../atl/codesnippet/cpp/ccomobject-class_1.h)]

[!code-cpp[NVC_ATL_COM#39](../../atl/codesnippet/cpp/ccomobject-class_2.cpp)]

##  <a name="queryinterface"></a>  CComObject::QueryInterface

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

##  <a name="release"></a>  CComObject::Release

개체의 참조 횟수를 감소 시킵니다.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>반환 값

이 함수는 개체에 새 감소 참조 횟수를 반환합니다. 디버그 빌드에서 반환 값에는 진단에 대 한 유용한 또는 테스트 수 있습니다. 디버그가 아닌 빌드에서 `Release` 항상 0을 반환 합니다.

## <a name="see-also"></a>참고자료

[CComAggObject 클래스](../../atl/reference/ccomaggobject-class.md)<br/>
[CComPolyObject 클래스](../../atl/reference/ccompolyobject-class.md)<br/>
[DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)<br/>
[DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
