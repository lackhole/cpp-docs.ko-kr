---
title: IConnectionPointImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IConnectionPointImpl
- ATLCOM/ATL::IConnectionPointImpl
- ATLCOM/ATL::IConnectionPointImpl::Advise
- ATLCOM/ATL::IConnectionPointImpl::EnumConnections
- ATLCOM/ATL::IConnectionPointImpl::GetConnectionInterface
- ATLCOM/ATL::IConnectionPointImpl::GetConnectionPointContainer
- ATLCOM/ATL::IConnectionPointImpl::Unadvise
- ATLCOM/ATL::IConnectionPointImpl::m_vec
helpviewer_keywords:
- connection points [C++], implementing
- IConnectionPointImpl class
ms.assetid: 27992115-3b86-45dd-bc9e-54f32876c557
ms.openlocfilehash: 54231a4229db9a9afeecad878d695814565d776b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62275544"
---
# <a name="iconnectionpointimpl-class"></a>IConnectionPointImpl 클래스

이 클래스는 연결점을 구현합니다.

## <a name="syntax"></a>구문

```
template<class T, const IID* piid, class CDV = CComDynamicUnkArray>
class ATL_NO_VTABLE IConnectionPointImpl : public _ICPLocator<piid>
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
클래스에서 파생 된 `IConnectionPointImpl`합니다.

*piid*<br/>
연결 지점 개체를 나타내는 인터페이스의 IID에 대 한 포인터입니다.

*CDV*<br/>
연결을 관리 하는 클래스입니다. 기본값은 [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), 무제한 연결 수 있습니다. 사용할 수도 있습니다 [CComUnkArray](../../atl/reference/ccomunkarray-class.md), 고정 된 수의 연결을 지정 합니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[IConnectionPointImpl::Advise](#advise)|연결점 및 싱크 간에 연결을 설정 합니다.|
|[IConnectionPointImpl::EnumConnections](#enumconnections)|연결 지점에 대 한 연결을 통해 반복 하는 열거자를 만듭니다.|
|[IConnectionPointImpl::GetConnectionInterface](#getconnectioninterface)|연결 지점에서이 나타내는 인터페이스의 IID를 검색 합니다.|
|[IConnectionPointImpl::GetConnectionPointContainer](#getconnectionpointcontainer)|연결 가능 개체에 대 한 인터페이스 포인터를 검색합니다.|
|[IConnectionPointImpl::Unadvise](#unadvise)|연결을 통해 이전에 종료 `Advise`합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[IConnectionPointImpl::m_vec](#m_vec)|연결 지점에 대 한 연결을 관리합니다.|

## <a name="remarks"></a>설명

`IConnectionPointImpl` 클라이언트에 나가는 인터페이스를 노출 하는 개체를 허용 하는 연결점을 구현 합니다. 클라이언트는 싱크 라는 개체에이 인터페이스를 구현 합니다.

사용 하 여 ATL [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md) 연결 가능 개체를 구현 합니다. 연결 가능 개체 내에서 각 연결 지점으로 식별 되는 송신 인터페이스에 나타냅니다 *piid*합니다. 클래스 *CDV* 연결점 및 싱크 간의 연결을 관리 합니다. 각 연결에서 "쿠키". 고유 하 게 식별 됩니다.

ATL 연결 지점 사용에 대 한 자세한 내용은 문서를 참조 [연결점](../../atl/atl-connection-points.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`_ICPLocator`

`IConnectionPointImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

##  <a name="advise"></a>  IConnectionPointImpl::Advise

연결점 및 싱크 간에 연결을 설정 합니다.

```
STDMETHOD(Advise)(
    IUnknown* pUnkSink,
    DWORD* pdwCookie);
```

### <a name="remarks"></a>설명

사용 하 여 [unadvise로](#unadvise) 연결 호출을 종료 합니다.

참조 [IConnectionPoint::Advise](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpoint-advise) Windows SDK에에서 있습니다.

##  <a name="enumconnections"></a>  IConnectionPointImpl::EnumConnections

연결 지점에 대 한 연결을 통해 반복 하는 열거자를 만듭니다.

```
STDMETHOD(EnumConnections)(IEnumConnections** ppEnum);
```

### <a name="remarks"></a>설명

참조 [IConnectionPoint::EnumConnections](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpoint-enumconnections) Windows SDK에에서 있습니다.

##  <a name="getconnectioninterface"></a>  IConnectionPointImpl::GetConnectionInterface

연결 지점에서이 나타내는 인터페이스의 IID를 검색 합니다.

```
STDMETHOD(GetConnectionInterface)(IID* piid2);
```

### <a name="remarks"></a>설명

참조 [IConnectionPoint::GetConnectionInterface](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpoint-getconnectioninterface) Windows SDK에에서 있습니다.

##  <a name="getconnectionpointcontainer"></a>  IConnectionPointImpl::GetConnectionPointContainer

연결 가능 개체에 대 한 인터페이스 포인터를 검색합니다.

```
STDMETHOD(GetConnectionPointContainer)(IConnectionPointContainer** ppCPC);
```

### <a name="remarks"></a>설명

참조 [IConnectionPoint::GetConnectionPointContainer](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpoint-getconnectionpointcontainer) Windows SDK에에서 있습니다.

##  <a name="m_vec"></a>  IConnectionPointImpl::m_vec

연결 지점 개체와 싱크 간의 연결을 관리합니다.

```
CDV m_vec;
```

### <a name="remarks"></a>설명

기본적으로 `m_vec` 유형임 [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)합니다.

##  <a name="unadvise"></a>  IConnectionPointImpl::Unadvise

연결을 통해 이전에 종료 [Advise](#advise)합니다.

```
STDMETHOD(Unadvise)(DWORD dwCookie);
```

### <a name="remarks"></a>설명

참조 [iconnectionpoint:: Unadvise](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpoint-unadvise) Windows SDK에에서 있습니다.

## <a name="see-also"></a>참고자료

[IConnectionPoint](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpoint)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
