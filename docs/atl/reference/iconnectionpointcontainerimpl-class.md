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
ms.openlocfilehash: 278ca6b1b9aac9539680d90b6fa0b18df22fc2f0
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496020"
---
# <a name="iconnectionpointcontainerimpl-class"></a>IConnectionPointContainerImpl 클래스

이 클래스는 [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) 개체의 컬렉션을 관리 하는 연결 지점 컨테이너를 구현 합니다.

## <a name="syntax"></a>구문

```
template<class T>
class ATL_NO_VTABLE IConnectionPointContainerImpl
   : public IConnectionPointContainer
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
에서 `IConnectionPointContainerImpl`파생 된 클래스입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|Description|
|----------|-----------------|
|[IConnectionPointContainerImpl::EnumConnectionPoints](#enumconnectionpoints)|연결 가능 개체에서 지원 되는 연결 요소를 반복 하는 열거자를 만듭니다.|
|[IConnectionPointContainerImpl::FindConnectionPoint](#findconnectionpoint)|지정 된 IID를 지 원하는 연결 지점에 대 한 인터페이스 포인터를 검색 합니다.|

## <a name="remarks"></a>설명

`IConnectionPointContainerImpl`[IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) 개체의 컬렉션을 관리 하는 연결 지점 컨테이너를 구현 합니다. `IConnectionPointContainerImpl`클라이언트에서 연결할 수 있는 두 가지 메서드를 제공 하 여 연결 가능 개체에 대 한 추가 정보를 검색 합니다.

- `EnumConnectionPoints`클라이언트가 개체에서 지 원하는 송신 인터페이스를 확인할 수 있도록 합니다.

- `FindConnectionPoint`클라이언트에서 개체가 특정 송신 인터페이스를 지원 하는지 여부를 확인할 수 있도록 합니다.

ATL에서 연결 지점의 사용에 대 한 자세한 내용은 [연결 요소](../../atl/atl-connection-points.md)문서를 참조 하세요.

## <a name="inheritance-hierarchy"></a>상속 계층

`IConnectionPointContainer`

`IConnectionPointContainerImpl`

## <a name="requirements"></a>요구 사항

**헤더:**

##  <a name="enumconnectionpoints"></a>  IConnectionPointContainerImpl::EnumConnectionPoints

연결 가능 개체에서 지원 되는 연결 요소를 반복 하는 열거자를 만듭니다.

```
STDMETHOD(EnumConnectionPoints)(IEnumConnectionPoints** ppEnum);
```

### <a name="remarks"></a>설명

Windows SDK의 [IConnectionPointContainer:: EnumConnectionPoints](/windows/win32/api/ocidl/nf-ocidl-iconnectionpointcontainer-enumconnectionpoints) 를 참조 하세요.

##  <a name="findconnectionpoint"></a>  IConnectionPointContainerImpl::FindConnectionPoint

지정 된 IID를 지 원하는 연결 지점에 대 한 인터페이스 포인터를 검색 합니다.

```
STDMETHOD(FindConnectionPoint)(REFIID riid, IConnectionPoint** ppCP);
```

### <a name="remarks"></a>설명

Windows SDK에서 [IConnectionPointContainer:: FindConnectionPoint](/windows/win32/api/ocidl/nf-ocidl-iconnectionpointcontainer-findconnectionpoint) 를 참조 하세요.

## <a name="see-also"></a>참고자료

[IConnectionPointContainer](/windows/win32/api/ocidl/nn-ocidl-iconnectionpointcontainer)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
