---
title: CComTearOffObject 클래스
ms.date: 11/04/2016
f1_keywords:
- CComTearOffObject
- ATLCOM/ATL::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::AddRef
- ATLCOM/ATL::CComTearOffObject::QueryInterface
- ATLCOM/ATL::CComTearOffObject::Release
- ATLCOM/ATL::CComTearOffObjectBase
- ATLCOM/ATL::m_pOwner
helpviewer_keywords:
- tear-off interfaces, ATL
- tear-off interfaces
- CComTearOffObject class
ms.assetid: d974b598-c6b2-42b1-8360-9190d9d0fbf3
ms.openlocfilehash: 0d27a6fa3c0070cd32c78971a7544327c51d4393
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496912"
---
# <a name="ccomtearoffobject-class"></a>CComTearOffObject 클래스

이 클래스는 분리 인터페이스를 구현 합니다.

## <a name="syntax"></a>구문

```
template<class Base>
class CComTearOffObject : public Base
```

#### <a name="parameters"></a>매개 변수

*하단*<br/>
에서 파생 된 분리 된 클래스 및 분리 `CComTearOffObjectBase` 개체에서 지원 하도록 할 인터페이스입니다.

ATL은 두 단계에서 분리 인터페이스를 구현 합니다. 메서드 `CComTearOffObjectBase` 는 참조 횟수를 처리 하 `QueryInterface`고는 `CComTearOffObject` [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)을 구현 합니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CComTearOffObject::CComTearOffObject](#ccomtearoffobject)|생성자입니다.|
|[CComTearOffObject::~CComTearOffObject](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|Description|
|----------|-----------------|
|[CComTearOffObject::AddRef](#addref)|`CComTearOffObject` 개체의 참조 횟수를 증가 시킵니다.|
|[CComTearOffObject::QueryInterface](#queryinterface)|해제 클래스나 소유자 클래스에서 요청 된 인터페이스에 대 한 포인터를 반환 합니다.|
|[CComTearOffObject::Release](#release)|`CComTearOffObject` 개체의 참조 횟수를 감소 시켜 소멸 시킵니다.|

### <a name="ccomtearoffobjectbase-methods"></a>CComTearOffObjectBase 메서드

|||
|-|-|
|[CComTearOffObjectBase](#ccomtearoffobjectbase)|생성자입니다.|

### <a name="ccomtearoffobjectbase-data-members"></a>CComTearOffObjectBase 데이터 멤버

|||
|-|-|
|[m_pOwner](#m_powner)|Owner 클래스에서 `CComObject` 파생 되는에 대 한 포인터입니다.|

## <a name="remarks"></a>설명

`CComTearOffObject`에 대해 해당 인터페이스를 쿼리할 때만 인스턴스화된 개별 개체로 분리 인터페이스를 구현 합니다. 참조 횟수가 0이 되 면 분리가 삭제 됩니다. 일반적으로 분리를 사용 하면 기본 개체의 모든 인스턴스에 vtable 포인터가 저장 되므로 거의 사용 되지 않는 인터페이스의 분리 인터페이스를 빌드합니다.

분리 된 개체에서 지원 하려는 모든 인터페이스에서 분리를 `CComTearOffObjectBase` 구현 하는 클래스를 파생 해야 합니다. `CComTearOffObjectBase`는 owner 클래스와 스레드 모델의 템플릿 화입니다. Owner 클래스는 해제를 구현 하는 개체의 클래스입니다. 스레드 모델을 지정 하지 않으면 기본 스레드 모델이 사용 됩니다.

분리 클래스에 대해 COM 맵을 만들어야 합니다. ATL은 분리를 인스턴스화할 때 또는 `CComTearOffObject<CYourTearOffClass>` `CComCachedTearOffObject<CYourTearOffClass>`를 만듭니다.

예를 들어 BEEPER 샘플 `CBeeper2` 에서 클래스는 분리 클래스이 `CBeeper` 고 클래스는 owner 클래스입니다.

[!code-cpp[NVC_ATL_COM#43](../../atl/codesnippet/cpp/ccomtearoffobject-class_1.h)]

## <a name="inheritance-hierarchy"></a>상속 계층

`Base`

`CComTearOffObject`

## <a name="requirements"></a>요구 사항

**헤더:**

##  <a name="addref"></a>  CComTearOffObject::AddRef

`CComTearOffObject` 개체의 참조 횟수를 1 씩 증가 시킵니다.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>반환 값

진단 및 테스트에 유용할 수 있는 값입니다.

##  <a name="ccomtearoffobject"></a>  CComTearOffObject::CComTearOffObject

생성자입니다.

```
CComTearOffObject(void* pv);
```

### <a name="parameters"></a>매개 변수

*pv*<br/>
진행 `CComObject<Owner>` 개체에 대 한 포인터로 변환 되는 포인터입니다.

### <a name="remarks"></a>설명

소유자의 참조 횟수를 1 씩 증가 시킵니다.

##  <a name="dtor"></a>  CComTearOffObject::~CComTearOffObject

소멸자입니다.

```
~CComTearOffObject();
```

### <a name="remarks"></a>설명

할당 된 모든 리소스를 해제 하 고, 전체 릴리스를 호출 하 고, 모듈 잠금 횟수를 감소 시킵니다.

##  <a name="ccomtearoffobjectbase"></a>  CComTearOffObject::CComTearOffObjectBase

생성자입니다.

```
CComTearOffObjectBase();
```

### <a name="remarks"></a>설명

[M_pOwner](#m_powner) 멤버를 NULL로 초기화 합니다.

##  <a name="m_powner"></a>  CComTearOffObject::m_pOwner

*Owner*에서 파생 된 [CComObject](../../atl/reference/ccomobject-class.md) 개체에 대 한 포인터입니다.

```
CComObject<Owner>* m_pOwner;
```

### <a name="parameters"></a>매개 변수

*소유자*<br/>
진행 종료를 구현 하는 클래스입니다.

### <a name="remarks"></a>설명

생성 하는 동안 포인터가 NULL로 초기화 됩니다.

##  <a name="queryinterface"></a>  CComTearOffObject::QueryInterface

요청된 인터페이스에 대한 포인터를 검색합니다.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>매개 변수

*iid*<br/>
진행 요청 되는 인터페이스의 IID입니다.

*ppvObject*<br/>
제한이 *Iid*로 식별 되는 인터페이스 포인터에 대 한 포인터 이거나, 인터페이스를 찾을 수 없는 경우 NULL입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

분리 클래스의 인터페이스에 대 한 쿼리를 먼저 합니다. 인터페이스가 없으면 소유자 개체의 인터페이스를 쿼리 합니다. 요청 된 인터페이스가 `IUnknown`이면 소유자 `IUnknown` 의를 반환 합니다.

##  <a name="release"></a>  CComTearOffObject::Release

참조 횟수를 1 씩 감소 시키고 참조 횟수가 0 이면를 삭제 `CComTearOffObject`합니다.

```
STDMETHOD_ULONG Release();
```

### <a name="return-value"></a>반환 값

디버그가 아닌 빌드에서는 항상 0을 반환 합니다. 디버그 빌드에서는 진단 또는 테스트에 유용할 수 있는 값을 반환 합니다.

## <a name="see-also"></a>참고자료

[CComCachedTearOffObject 클래스](../../atl/reference/ccomcachedtearoffobject-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
