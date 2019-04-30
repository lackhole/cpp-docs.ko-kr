---
title: IConnectionPointContainerImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IConnectionPointContainerImpl
- ATLCOM/ATL::IConnectionPointContainerImpl
- ATLCOM/ATL::IConnectionPointContainerImpl::EnumConnectionPoints
- ATLCOM/ATL::IConnectionPointContainerImpl::FindConnectionPoint
helpviewer_keywords:
- connectable objects
- connection points [C++], container
- IConnectionPointContainerImpl class
ms.assetid: 10db5a8d-8be9-4d9d-8a82-8ab9ffe3e9d6
ms.openlocfilehash: 06baa4dac3248d783648b8ce37e51250e0de2498
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62275518"
---
# <a name="iconnectionpointcontainerimpl-class"></a>IConnectionPointContainerImpl 클래스

이 클래스는 컬렉션을 관리 하는 연결 지점 컨테이너를 구현 [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) 개체입니다.

## <a name="syntax"></a>구문

```
template<class T>
class ATL_NO_VTABLE IConnectionPointContainerImpl
   : public IConnectionPointContainer
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
클래스에서 파생 된 `IConnectionPointContainerImpl`합니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[IConnectionPointContainerImpl::EnumConnectionPoints](#enumconnectionpoints)|연결 가능한 개체에서 지원 되는 연결점을 반복 하는 열거자를 만듭니다.|
|[IConnectionPointContainerImpl::FindConnectionPoint](#findconnectionpoint)|지정한 IID를 지 원하는 연결 지점에 대 한 인터페이스 포인터를 검색 합니다.|

## <a name="remarks"></a>설명

`IConnectionPointContainerImpl` 컬렉션을 관리 하는 연결 지점 컨테이너를 구현 [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) 개체입니다. `IConnectionPointContainerImpl` 클라이언트 연결 가능 개체에 대 한 자세한 정보를 검색 하기 위해 호출할 수 있는 두 가지 방법을 제공 합니다.

- `EnumConnectionPoints` 클라이언트를 개체에서 지 원하는 인터페이스는 나가는 결정할 수 있습니다.

- `FindConnectionPoint` 클라이언트를 개체는 특정 송신 인터페이스를 지원 하는지 여부를 결정할 수 있습니다.

ATL 연결 지점 사용에 대 한 자세한 문서를 참조 [연결점](../../atl/atl-connection-points.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IConnectionPointContainer`

`IConnectionPointContainerImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

##  <a name="enumconnectionpoints"></a>  IConnectionPointContainerImpl::EnumConnectionPoints

연결 가능한 개체에서 지원 되는 연결점을 반복 하는 열거자를 만듭니다.

```
STDMETHOD(EnumConnectionPoints)(IEnumConnectionPoints** ppEnum);
```

### <a name="remarks"></a>설명

참조 [IConnectionPointContainer::EnumConnectionPoints](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpointcontainer-enumconnectionpoints) Windows SDK에에서 있습니다.

##  <a name="findconnectionpoint"></a>  IConnectionPointContainerImpl::FindConnectionPoint

지정한 IID를 지 원하는 연결 지점에 대 한 인터페이스 포인터를 검색 합니다.

```
STDMETHOD(FindConnectionPoint)(REFIID riid, IConnectionPoint** ppCP);
```

### <a name="remarks"></a>설명

참조 [IConnectionPointContainer::FindConnectionPoint](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpointcontainer-findconnectionpoint) Windows SDK에에서 있습니다.

## <a name="see-also"></a>참고자료

[IConnectionPointContainer](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpointcontainer)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
