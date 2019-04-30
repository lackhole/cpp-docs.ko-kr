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
ms.openlocfilehash: fd35b1e9e69c97402dd1ec357fd25fa1dcd5dd49
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62259419"
---
# <a name="ccomtearoffobject-class"></a>CComTearOffObject 클래스

이 클래스는 분리 인터페이스를 구현합니다.

## <a name="syntax"></a>구문

```
template<class Base>
class CComTearOffObject : public Base
```

#### <a name="parameters"></a>매개 변수

*Base*<br/>
분리 막대가 클래스에서 파생 된 `CComTearOffObjectBase` 고 인터페이스를 지원 하기 위해 분리 개체입니다.

ATL 두 단계로 분리 인터페이스를 구현-는 `CComTearOffObjectBase` 메서드는 참조 횟수를 처리 하 고 `QueryInterface`, 하는 동안 `CComTearOffObject` 구현 [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown)합니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CComTearOffObject::CComTearOffObject](#ccomtearoffobject)|생성자입니다.|
|[CComTearOffObject::~CComTearOffObject](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CComTearOffObject::AddRef](#addref)|에 대 한 참조 횟수를 증가 `CComTearOffObject` 개체입니다.|
|[CComTearOffObject::QueryInterface](#queryinterface)|분리 막대가 클래스 또는 소유자 클래스에서 요청된 된 인터페이스에 대 한 포인터를 반환합니다.|
|[CComTearOffObject::Release](#release)|에 대 한 참조 횟수를 감소는 `CComTearOffObject` 개체 및이 제거 합니다.|

### <a name="ccomtearoffobjectbase-methods"></a>CComTearOffObjectBase 메서드

|||
|-|-|
|[CComTearOffObjectBase](#ccomtearoffobjectbase)|생성자입니다.|

### <a name="ccomtearoffobjectbase-data-members"></a>CComTearOffObjectBase 데이터 멤버

|||
|-|-|
|[m_pOwner](#m_powner)|에 대 한 포인터를 `CComObject` 소유자 클래스에서 파생 됩니다.|

## <a name="remarks"></a>설명

`CComTearOffObject` 해당 인터페이스에 대해 쿼리 하는 경우에 인스턴스화되는 별개의 개체로 분리 인터페이스를 구현 합니다. 참조 횟수가 0 인 경우는 분리 삭제 됩니다. 일반적으로 분리 하기 위한 인터페이스를 거의 사용 되지 않는, 주요 개체의 모든 인스턴스에서 vtable 대 한 포인터를 저장 한 분리를 사용 하 여 있으므로 인터페이스를 빌드할 수 있습니다.

분리를 구현 하는 클래스를 파생 해야 `CComTearOffObjectBase` 지원 하기 위해 분리 개체 원하는 어떤 인터페이스에서 합니다. `CComTearOffObjectBase` 소유자 클래스와 스레드 모델에서 템플릿 화 됩니다. 소유자 클래스에는 분리 막대가 구현 되는 개체의 클래스가입니다. 스레드 모델을 지정 하지 않으면 기본 스레드 모델 사용 됩니다.

분리 막대가 클래스에 대 한 COM 맵을 만들어야 합니다. ATL 인스턴스화하는 분리 하면 생성 됩니다 `CComTearOffObject<CYourTearOffClass>` 또는 `CComCachedTearOffObject<CYourTearOffClass>`합니다.

예를 들어, 호출기 샘플에에서는 `CBeeper2` 클래스는 분리 클래스 및 `CBeeper` 클래스는 소유자 클래스:

[!code-cpp[NVC_ATL_COM#43](../../atl/codesnippet/cpp/ccomtearoffobject-class_1.h)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`Base`

`CComTearOffObject`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

##  <a name="addref"></a>  CComTearOffObject::AddRef

참조 횟수를 증가 `CComTearOffObject` 개체 하나.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>반환 값

진단에 유용 하 고 테스트 될 수 있는 값입니다.

##  <a name="ccomtearoffobject"></a>  CComTearOffObject::CComTearOffObject

생성자입니다.

```
CComTearOffObject(void* pv);
```

### <a name="parameters"></a>매개 변수

*pv*<br/>
[in] 에 대 한 포인터로 변환할 포인터는 `CComObject<Owner>` 개체입니다.

### <a name="remarks"></a>설명

소유자의 참조 개수를 1 씩 증가 시킵니다.

##  <a name="dtor"></a>  CComTearOffObject::~CComTearOffObject

소멸자입니다.

```
~CComTearOffObject();
```

### <a name="remarks"></a>설명

할당 된 모든 리소스를 해제, FinalRelease를 롤백하고 모듈 호출 잠글 수 있습니다.

##  <a name="ccomtearoffobjectbase"></a>  CComTearOffObject::CComTearOffObjectBase

생성자입니다.

```
CComTearOffObjectBase();
```

### <a name="remarks"></a>설명

초기화 된 [m_pOwner](#m_powner) NULL 멤버입니다.

##  <a name="m_powner"></a>  CComTearOffObject::m_pOwner

에 대 한 포인터를 [CComObject](../../atl/reference/ccomobject-class.md) 에서 파생 된 개체 *소유자*합니다.

```
CComObject<Owner>* m_pOwner;
```

### <a name="parameters"></a>매개 변수

*소유자*<br/>
[in] 분리 막대가 구현 되는 클래스입니다.

### <a name="remarks"></a>설명

포인터를 생성 하는 동안 NULL로 초기화 됩니다.

##  <a name="queryinterface"></a>  CComTearOffObject::QueryInterface

요청된 인터페이스에 대한 포인터를 검색합니다.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>매개 변수

*iid*<br/>
[in] 요청 된 인터페이스의 IID입니다.

*ppvObject*<br/>
[out] 로 식별 되는 인터페이스 포인터에 대 한 포인터 *iid*, 또는 인터페이스를 찾을 수 없으면 NULL입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

먼저 분리 클래스에서 인터페이스에 대 한 쿼리. 인터페이스가 없는 경우, 소유자 개체의 인터페이스에 대 한 쿼리 합니다. 요청한 인터페이스가 있으면 `IUnknown`를 반환 합니다 `IUnknown` 소유자의 합니다.

##  <a name="release"></a>  CComTearOffObject::Release

참조 횟수를 1 씩 감소 하 고, 참조 횟수가 0 인 경우 삭제는 `CComTearOffObject`합니다.

```
STDMETHOD_ULONG Release();
```

### <a name="return-value"></a>반환 값

디버그가 아닌 빌드에서 항상 0을 반환합니다. 디버그 빌드에서 진단에 유용 하거나 테스트 수 있는 값을 반환 합니다.

## <a name="see-also"></a>참고자료

[CComCachedTearOffObject 클래스](../../atl/reference/ccomcachedtearoffobject-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
