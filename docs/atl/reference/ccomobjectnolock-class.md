---
title: CComObjectNoLock 클래스
ms.date: 11/04/2016
f1_keywords:
- CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock::CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock::AddRef
- ATLCOM/ATL::CComObjectNoLock::QueryInterface
- ATLCOM/ATL::CComObjectNoLock::Release
helpviewer_keywords:
- CComObjectNoLock class
ms.assetid: 288c6506-7da8-4127-8d58-7f4bd779539a
ms.openlocfilehash: 50dc4505c1da8df9efc0c9d0028461ef49c0840e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62246302"
---
# <a name="ccomobjectnolock-class"></a>CComObjectNoLock 클래스

이 클래스는 구현 `IUnknown` 집계 개체를 하지만 모듈 잠금 횟수를 생성자에는 증가 하지 않습니다.

## <a name="syntax"></a>구문

```
template<class Base>
class CComObjectNoLock : public Base
```

#### <a name="parameters"></a>매개 변수

*Base*<br/>
파생 된 클래스 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 하거나 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)처럼 개체에서 지원 하려는 다른 모든 인터페이스 에서도 잘 합니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CComObjectNoLock::CComObjectNoLock](#ccomobjectnolock)|생성자입니다.|
|[CComObjectNoLock::~CComObjectNoLock](#dtor)|소멸자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CComObjectNoLock::AddRef](#addref)|개체의 참조 횟수를 증가 시킵니다.|
|[CComObjectNoLock::QueryInterface](#queryinterface)|요청된 된 인터페이스에 대 한 포인터를 반환합니다.|
|[CComObjectNoLock::Release](#release)|개체의 참조 횟수를 감소 시킵니다.|

## <a name="remarks"></a>설명

`CComObjectNoLock` 비슷합니다 [CComObject](../../atl/reference/ccomobject-class.md) 구현 한다는 [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) 집계 개체입니다; 그러나 `CComObjectNoLock` 생성자에서 계산 모듈 잠금을 증가 하지 않습니다.

ATL 사용 `CComObjectNoLock` 클래스 팩터리를 내부적으로 합니다. 일반적으로이 클래스를 직접 넣지 됩니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`Base`

`CComObjectNoLock`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

##  <a name="addref"></a>  CComObjectNoLock::AddRef

개체의 참조 횟수를 증가 시킵니다.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>반환 값

진단에 유용 하거나 테스트 수 있는 값입니다.

##  <a name="ccomobjectnolock"></a>  CComObjectNoLock::CComObjectNoLock

생성자입니다. 와 달리 [CComObject](../../atl/reference/ccomobject-class.md), 모듈 잠금 수가 증가 하지 않습니다.

```
CComObjectNoLock(void* = NULL);
```

### <a name="parameters"></a>매개 변수

<em>void\*</em><br/>
[in] 이 명명 되지 않은 매개 변수 사용 되지 않습니다. 다른 대칭에 대 한 존재 `CComXXXObjectXXX` 생성자입니다.

##  <a name="dtor"></a>  CComObjectNoLock::~CComObjectNoLock

소멸자입니다.

```
~CComObjectNoLock();
```

### <a name="remarks"></a>설명

할당 된 모든 리소스 및 호출을 해제 [FinalRelease](ccomobjectrootex-class.md#finalrelease)합니다.

##  <a name="queryinterface"></a>  CComObjectNoLock::QueryInterface

요청된 인터페이스에 대한 포인터를 검색합니다.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>매개 변수

*iid*<br/>
[in] 요청 된 인터페이스의 식별자입니다.

*ppvObject*<br/>
[out] 로 식별 되는 인터페이스 포인터에 대 한 포인터 *iid*합니다. 개체는이 인터페이스를 지원 하지 않는 경우 *ppvObject* NULL로 설정 됩니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

##  <a name="release"></a>  CComObjectNoLock::Release

개체의 참조 횟수를 감소 시킵니다.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>반환 값

디버그 빌드에서 `Release` 진단용 유용 하거나 테스트 수 있는 값을 반환 합니다. 디버그가 아닌 빌드에서 `Release` 항상 0을 반환 합니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)
