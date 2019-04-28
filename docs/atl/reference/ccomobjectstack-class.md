---
title: CComObjectStack 클래스
ms.date: 11/04/2016
f1_keywords:
- CComObjectStack
- ATLCOM/ATL::CComObjectStack
- ATLCOM/ATL::CComObjectStack::CComObjectStack
- ATLCOM/ATL::CComObjectStack::AddRef
- ATLCOM/ATL::CComObjectStack::QueryInterface
- ATLCOM/ATL::CComObjectStack::Release
- ATLCOM/ATL::CComObjectStack::m_hResFinalConstruct
helpviewer_keywords:
- CComObjectStack class
ms.assetid: 3da72c40-c834-45f6-bb76-6ac204028d80
ms.openlocfilehash: 19fd226e617e4cdb1bba8a113b8984c36bf28d59
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62259588"
---
# <a name="ccomobjectstack-class"></a>CComObjectStack 클래스

이 클래스의 기본 구현을 제공와 임시 COM 개체를 만들고 `IUnknown`합니다.

## <a name="syntax"></a>구문

```
template <class  Base>
class CComObjectStack : public Base
```

#### <a name="parameters"></a>매개 변수

*Base*<br/>
파생 된 클래스 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 하거나 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)처럼 개체에서 지원 하려는 다른 모든 인터페이스 에서도 잘 합니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CComObjectStack::CComObjectStack](#ccomobjectstack)|생성자입니다.|
|[CComObjectStack::~CComObjectStack](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CComObjectStack::AddRef](#addref)|0을 반환합니다. 디버그 모드에서 호출 `_ASSERTE`합니다.|
|[CComObjectStack::QueryInterface](#queryinterface)|E_NOINTERFACE 반환 합니다. 디버그 모드에서 호출 `_ASSERTE`합니다.|
|[CComObjectStack::Release](#release)|0을 반환합니다. 디버그 모드에서 호출 `_ASSERTE`합니다. ~|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CComObjectStack::m_hResFinalConstruct](#m_hresfinalconstruct)|생성 중 반환 된 HRESULT를 포함 합니다 `CComObjectStack` 개체입니다.|

## <a name="remarks"></a>설명

`CComObjectStack` 임시 COM 개체를 만들고 개체의 기본 구현을 제공 하는 데는 `IUnknown`합니다. 일반적으로 개체 (즉, 스택에) 하나의 함수 내에서 지역 변수로 사용 됩니다. 함수가 완료 되는 개체가 제거 되므로 참조 카운팅 해도 효율성을 높이기 위해 수행 되지 않습니다.

다음 예제에서는 함수 내에서 사용 하는 COM 개체를 만드는 방법을 보여 줍니다.

[!code-cpp[NVC_ATL_COM#42](../../atl/codesnippet/cpp/ccomobjectstack-class_1.cpp)]

임시 개체 `Tempobj` 스택에 푸시됩니다 및 함수가 완료 되 면 자동으로 사라집니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`Base`

`CComObjectStack`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

##  <a name="addref"></a>  CComObjectStack::AddRef

0을 반환합니다.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>반환 값

0을 반환합니다.

### <a name="remarks"></a>설명

디버그 모드에서 호출 `_ASSERTE`합니다.

##  <a name="ccomobjectstack"></a>  CComObjectStack::CComObjectStack

생성자입니다.

```
CComObjectStack(void* = NULL);
```

### <a name="remarks"></a>설명

호출 `FinalConstruct` 설정한 [m_hResFinalConstruct](#m_hresfinalconstruct) 반환한 HRESULT를 `FinalConstruct`입니다. 기본 클래스에서 파생 되지 않은 하는 경우 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)를 직접 제공 해야 `FinalConstruct` 메서드. 이 소멸자는 `FinalRelease`을 호출합니다.

##  <a name="dtor"></a>  CComObjectStack::~CComObjectStack

소멸자입니다.

```
CComObjectStack();
```

### <a name="remarks"></a>설명

할당 된 모든 리소스 및 호출을 해제 [FinalRelease](ccomobjectrootex-class.md#finalrelease)합니다.

##  <a name="m_hresfinalconstruct"></a>  CComObjectStack::m_hResFinalConstruct

호출에서 반환 된 HRESULT를 포함 `FinalConstruct` 생성 하는 동안는 `CComObjectStack` 개체입니다.

```
HRESULT    m_hResFinalConstruct;
```

##  <a name="queryinterface"></a>  CComObjectStack::QueryInterface

E_NOINTERFACE 반환 합니다.

```
HRESULT    QueryInterface(REFIID, void**);
```

### <a name="return-value"></a>반환 값

E_NOINTERFACE 반환 합니다.

### <a name="remarks"></a>설명

디버그 모드에서 호출 `_ASSERTE`합니다.

##  <a name="release"></a>  CComObjectStack::Release

0을 반환합니다.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>반환 값

0을 반환합니다.

### <a name="remarks"></a>설명

디버그 모드에서 호출 `_ASSERTE`합니다.

## <a name="see-also"></a>참고자료

[CComAggObject 클래스](../../atl/reference/ccomaggobject-class.md)<br/>
[CComObject 클래스](../../atl/reference/ccomobject-class.md)<br/>
[CComObjectGlobal 클래스](../../atl/reference/ccomobjectglobal-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
