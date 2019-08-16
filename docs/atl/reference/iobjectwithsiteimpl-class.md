---
title: IObjectWithSiteImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IObjectWithSiteImpl
- ATLCOM/ATL::IObjectWithSiteImpl
- ATLCOM/ATL::IObjectWithSiteImpl::GetSite
- ATLCOM/ATL::IObjectWithSiteImpl::SetChildSite
- ATLCOM/ATL::IObjectWithSiteImpl::SetSite
- ATLCOM/ATL::IObjectWithSiteImpl::m_spUnkSite
helpviewer_keywords:
- IObjectWithSiteImpl class
ms.assetid: 4e1f774f-bc3d-45ee-9a1c-c3533a511588
ms.openlocfilehash: e857f739e3ff7235c473e99abbef6aab0d3f4205
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495843"
---
# <a name="iobjectwithsiteimpl-class"></a>IObjectWithSiteImpl 클래스

이 클래스는 개체가 사이트와 통신할 수 있도록 하는 메서드를 제공 합니다.

## <a name="syntax"></a>구문

```
template <class T>
    class ATL_NO_VTABLE IObjectWithSiteImpl :
    public IObjectWithSite
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
에서 `IObjectWithSiteImpl`파생 된 클래스입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|Description|
|----------|-----------------|
|[IObjectWithSiteImpl::GetSite](#getsite)|사이트에서 인터페이스 포인터를 쿼리 합니다.|
|[IObjectWithSiteImpl::SetChildSite](#setchildsite)|사이트의 `IUnknown` 포인터를 사용 하 여 개체를 제공 합니다.|
|[IObjectWithSiteImpl::SetSite](#setsite)|사이트의 `IUnknown` 포인터를 사용 하 여 개체를 제공 합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|Description|
|----------|-----------------|
|[IObjectWithSiteImpl::m_spUnkSite](#m_spunksite)|사이트의 `IUnknown` 포인터를 관리 합니다.|

## <a name="remarks"></a>설명

[IObjectWithSite](/windows/win32/api/ocidl/nn-ocidl-iobjectwithsite) 인터페이스를 사용 하면 개체가 사이트와 통신할 수 있습니다. 클래스 `IObjectWithSiteImpl` 는이 인터페이스의 기본 구현을 제공 하 고 `IUnknown` 디버그 빌드에서 정보를 덤프 장치로 전송 하 여를 구현 합니다.

`IObjectWithSiteImpl`두 메서드를 지정 합니다. 클라이언트는 먼저를 `SetSite`호출 하 여 사이트의 `IUnknown` 포인터를 전달 합니다. 이 포인터는 개체 내에 저장 되며 나중에를 `GetSite`호출 하 여 검색할 수 있습니다.

일반적으로 컨트롤이 아닌 개체를 만들 `IObjectWithSiteImpl` 때에서 클래스를 파생 시킵니다. 컨트롤의 경우 사이트 포인터를 제공 하는 [IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md)에서 클래스를 파생 시킵니다. `IObjectWithSiteImpl` 및`IOleObjectImpl`에서 클래스를 파생 하지 마십시오.

## <a name="inheritance-hierarchy"></a>상속 계층

`IObjectWithSite`

`IObjectWithSiteImpl`

## <a name="requirements"></a>요구 사항

**헤더:**

##  <a name="getsite"></a>  IObjectWithSiteImpl::GetSite

로 `riid`식별 되는 인터페이스에 대 한 포인터를 사이트에 쿼리 합니다.

```
STDMETHOD(GetSite)(
    REFIID riid,
    void** ppvSite);
```

### <a name="remarks"></a>설명

사이트에서이 인터페이스를 지 원하는 경우 포인터는를 통해 `ppvSite`반환 됩니다. 그렇지 않으면 `ppvSite` 가 NULL로 설정 됩니다.

Windows SDK [IObjectWithSite:: GetSite](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-getsite) 를 참조 하세요.

##  <a name="m_spunksite"></a>  IObjectWithSiteImpl::m_spUnkSite

사이트의 `IUnknown` 포인터를 관리 합니다.

```
CComPtr<IUnknown> m_spUnkSite;
```

### <a name="remarks"></a>설명

`m_spUnkSite`[SetSite](#setsite)에 대 한 호출을 통해 처음에이 포인터를 받습니다.

##  <a name="setchildsite"></a>  IObjectWithSiteImpl::SetChildSite

사이트의 `IUnknown` 포인터를 사용 하 여 개체를 제공 합니다.

```
HRESULT SetChildSite(IUnknown* pUnkSite);
```

### <a name="parameters"></a>매개 변수

*pUnkSite*<br/>
진행 이 개체를 `IUnknown` 관리 하는 사이트의 인터페이스 포인터에 대 한 포인터입니다. NULL 인 경우 개체는 기존 사이트 `IUnknown::Release` 에서를 호출 해야 합니다 .이 시점에서 개체가 해당 사이트를 더 이상 인식 하지 못합니다.

### <a name="return-value"></a>반환 값

S_OK를 반환 합니다.

##  <a name="setsite"></a>  IObjectWithSiteImpl::SetSite

사이트의 `IUnknown` 포인터를 사용 하 여 개체를 제공 합니다.

```
STDMETHOD(SetSite)(IUnknown* pUnkSite);
```

### <a name="remarks"></a>설명

Windows SDK에서 [IObjectWithSite:: SetSite](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-setsite) 를 참조 하세요.

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)
