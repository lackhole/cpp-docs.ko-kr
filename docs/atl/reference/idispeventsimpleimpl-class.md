---
title: IDispEventSimpleImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IDispEventSimpleImpl
- ATLCOM/ATL::IDispEventSimpleImpl
- ATLCOM/ATL::IDispEventSimpleImpl::Advise
- ATLCOM/ATL::IDispEventSimpleImpl::DispEventAdvise
- ATLCOM/ATL::IDispEventSimpleImpl::DispEventUnadvise
- ATLCOM/ATL::IDispEventSimpleImpl::GetIDsOfNames
- ATLCOM/ATL::IDispEventSimpleImpl::GetTypeInfo
- ATLCOM/ATL::IDispEventSimpleImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispEventSimpleImpl::Invoke
- ATLCOM/ATL::IDispEventSimpleImpl::Unadvise
helpviewer_keywords:
- IDispEventSimpleImpl class
ms.assetid: 971d82b7-a921-47fa-a4d8-909bed377ab0
ms.openlocfilehash: 1578518b8918f59b1da54f474e82cf899f3c76f6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62275375"
---
# <a name="idispeventsimpleimpl-class"></a>IDispEventSimpleImpl 클래스

이 클래스의 구현을 제공 하는 `IDispatch` 형식 라이브러리에서 형식 정보를 가져오지 않고 메서드.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <UINT nID, class T, const IID* pdiid>
class ATL_NO_VTABLE IDispEventSimpleImpl : public _IDispEventLocator<nID, pdiid>
```

#### <a name="parameters"></a>매개 변수

*nID*<br/>
원본 개체에 대 한 고유 식별자입니다. 때 `IDispEventSimpleImpl` 기본 클래스인 복합 컨트롤의 경우이 매개 변수에 대해 원하는 포함 된 컨트롤의 리소스 ID를 사용 합니다. 다른 경우에는 임의의 양의 정수를 사용 합니다.

*T*<br/>
사용자의 클래스에서 파생 된 `IDispEventSimpleImpl`합니다.

*pdiid*<br/>
이 클래스에서 구현 되는 이벤트 인터페이스의 IID에 대 한 포인터입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[IDispEventSimpleImpl::Advise](#advise)|기본 이벤트 원본과 연결을 설정합니다.|
|[IDispEventSimpleImpl::DispEventAdvise](#dispeventadvise)|이벤트 소스와의 연결을 설정합니다.|
|[IDispEventSimpleImpl::DispEventUnadvise](#dispeventunadvise)|이벤트 소스와의 연결을 끊습니다.|
|[IDispEventSimpleImpl::GetIDsOfNames](#getidsofnames)|E_NOTIMPL 반환.|
|[IDispEventSimpleImpl::GetTypeInfo](#gettypeinfo)|E_NOTIMPL 반환.|
|[IDispEventSimpleImpl::GetTypeInfoCount](#gettypeinfocount)|E_NOTIMPL 반환.|
|[IDispEventSimpleImpl::Invoke](#invoke)|이벤트 처리기 호출 나열 이벤트 싱크 맵.|
|[IDispEventSimpleImpl::Unadvise](#unadvise)|기본 이벤트 소스와의 연결을 끊습니다.|

## <a name="remarks"></a>설명

`IDispEventSimpleImpl` 필요 없이 이벤트 인터페이스를 구현 하는 해당 인터페이스의 모든 메서드/이벤트에 대 한 구현 코드를 제공 하는 방법을 제공 합니다. `IDispEventSimpleImpl` 구현을 제공 하는 `IDispatch` 메서드. 처리에서 하려는 이벤트에 대 한 구현을 제공 해야 합니다.

`IDispEventSimpleImpl` 적절 한 처리기 함수에 이벤트를 라우팅하도록 클래스에서 이벤트 싱크 맵과 함께 작동합니다. 이 클래스를 사용 합니다.

- 추가 된 [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info) 처리 하려는 각 개체의 각 이벤트에 대 한 이벤트 싱크 맵 매크로입니다.

- 에 대 한 포인터를 전달 하 여 각 이벤트에 대 한 형식 정보를 제공 된 [_ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md) 각 항목에 대 한 매개 변수로 구조입니다. X86 플랫폼을 `_ATL_FUNC_INFO.cc` 값 __stdcall의 메서드를 호출 하는 콜백 함수를 사용 하 여 CC_CDECL 이어야 합니다.

- 호출 [DispEventAdvise](#dispeventadvise) 소스 개체와 기본 클래스 간의 연결을 설정 합니다.

- 호출 [DispEventUnadvise](#dispeventunadvise) 연결을 끊습니다.

파생 되어야 합니다 `IDispEventSimpleImpl` (에 대 한 고유한 값을 사용 하 여 *nID*) 이벤트를 처리 해야 하는 각 개체에 대 한 합니다. 그런 다음 다양 한 원본 개체에 대해 조언 하는 원본 개체에 대해 바이 하 여 기본 클래스를 재사용할 수 있습니다 하지만 한 번에 단일 개체로 처리 될 수 있는 원본 개체의 최대 수로 제한 됩니다 `IDispEventSimpleImpl` 기본 클래스입니다.

`IDispEventSimplImpl` 와 동일한 기능을 제공 [IDispEventImpl](../../atl/reference/idispeventimpl-class.md)을 제외 하 고 형식 라이브러리에서 인터페이스에 대 한 형식 정보를 가져오지 않습니다. 마법사 변수만 기반으로 하는 코드 생성 `IDispEventImpl`를 사용할 수 있지만 `IDispEventSimpleImpl` 직접 코드를 추가 하 여 합니다. 사용 하 여 `IDispEventSimpleImpl` 이벤트 인터페이스를 설명 하는 형식 라이브러리 또는 형식 라이브러리를 사용 하 여 연관 된 오버 헤드를 방지 하려면 없는 경우.

> [!NOTE]
> `IDispEventImpl` 및 `IDispEventSimpleImpl` 의 자체 구현을 제공할 `IUnknown::QueryInterface` 각를 사용 하도록 설정 하면 `IDispEventImpl` 또는 `IDispEventSimpleImpl` 여전히 기본 COM 개체에서 클래스 멤버에 대 한 직접 액세스를 허용 하는 동안 별도 COM id로 사용할 클래스를 기본.

ActiveX 이벤트 싱크만 지 원하는 형식의 반환 값 HRESULT 또는 이벤트 처리기 메서드에서; void CE ATL 구현 다른 모든 반환 값 지원 되지 않으며 해당 동작이 정의 되지 않습니다.

자세한 내용은 [IDispEventImpl 지원](../../atl/supporting-idispeventimpl.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`_IDispEvent`

`_IDispEventLocator`

`IDispEventSimpleImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

##  <a name="advise"></a>  IDispEventSimpleImpl::Advise

이 메서드를 나타내는 이벤트 소스와 연결할 *pUnk*합니다.

```
HRESULT Advise(IUnknown* pUnk);
```

### <a name="parameters"></a>매개 변수

*pUnk*<br/>
[in] 에 대 한 포인터를 `IUnknown` 이벤트 소스 개체의 인터페이스입니다.

### <a name="return-value"></a>반환 값

S_OK 또는 모든 오류 HRESULT 값입니다.

### <a name="remarks"></a>설명

이벤트에서 발생 합니다. 연결이 설정 되 면 *pUnk* 이벤트 싱크 맵과 통해 클래스의 처리기에 라우팅됩니다.

> [!NOTE]
>  여러에서 클래스가 파생 되는 경우 `IDispEventSimpleImpl` 이 메서드를 호출 하려는 특정 기본 클래스를 사용 하 여 호출 범위를 지정 하 여 명확 하 게 해야 클래스입니다.

`Advise` 연결을 기준으로 개체의 기본 이벤트 소스의 IID를 가져옵니다 해당 기본 이벤트 원본과 [AtlGetObjectSourceInterface](composite-control-global-functions.md#atlgetobjectsourceinterface)합니다.

##  <a name="dispeventadvise"></a>  IDispEventSimpleImpl::DispEventAdvise

이 메서드를 나타내는 이벤트 소스와 연결할 *pUnk*합니다.

```
HRESULT DispEventAdvise(IUnknown* pUnk  const IID* piid);
```

### <a name="parameters"></a>매개 변수

*pUnk*<br/>
[in] 에 대 한 포인터를 `IUnknown` 이벤트 소스 개체의 인터페이스입니다.

*piid*<br/>
이벤트 소스 개체의 IID에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

S_OK 또는 모든 오류 HRESULT 값입니다.

### <a name="remarks"></a>설명

이벤트에서 발생 하는 이후에 *pUnk* 이벤트 싱크 맵과 통해 클래스의 처리기에 라우팅됩니다.

> [!NOTE]
>  여러에서 클래스가 파생 되는 경우 `IDispEventSimpleImpl` 이 메서드를 호출 하려는 특정 기본 클래스를 사용 하 여 호출 범위를 지정 하 여 명확 하 게 해야 클래스입니다.

`DispEventAdvise` 에 지정 된 이벤트 소스를 사용 하 여 연결을 설정 `pdiid`합니다.

##  <a name="dispeventunadvise"></a>  IDispEventSimpleImpl::DispEventUnadvise

나타내는 이벤트 소스를 사용 하 여 연결을 끊는 *pUnk*합니다.

```
HRESULT DispEventUnadvise(IUnknown* pUnk  const IID* piid);
```

### <a name="parameters"></a>매개 변수

*pUnk*<br/>
[in] 에 대 한 포인터를 `IUnknown` 이벤트 소스 개체의 인터페이스입니다.

*piid*<br/>
이벤트 소스 개체의 IID에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

S_OK 또는 모든 오류 HRESULT 값입니다.

### <a name="remarks"></a>설명

연결이 끊어지면 이벤트 싱크 맵과에 나열 된 처리기 함수에 이벤트 이상 라우팅됩니다.

> [!NOTE]
>  여러에서 클래스가 파생 되는 경우 `IDispEventSimpleImpl` 이 메서드를 호출 하려는 특정 기본 클래스를 사용 하 여 호출 범위를 지정 하 여 명확 하 게 해야 클래스입니다.

`DispEventAdvise` 에 지정 된 이벤트 소스를 사용 하 여 설정 된 연결을 중단 `pdiid`합니다.

##  <a name="getidsofnames"></a>  IDispEventSimpleImpl::GetIDsOfNames

이 구현의 `IDispatch::GetIDsOfNames` E_NOTIMPL을 반환 합니다.

```
STDMETHOD(GetIDsOfNames)(
    REFIID /* riid */,
    LPOLESTR* /* rgszNames */,
    UINT /* cNames */,
    LCID /* lcid */,
    DISPID* /* rgdispid */);
```

### <a name="remarks"></a>설명

참조 [IDispatch::GetIDsOfNames](/windows/desktop/api/oaidl/nf-oaidl-idispatch-getidsofnames) Windows SDK에에서 있습니다.

##  <a name="gettypeinfo"></a>  IDispEventSimpleImpl::GetTypeInfo

이 구현의 `IDispatch::GetTypeInfo` E_NOTIMPL을 반환 합니다.

```
STDMETHOD(GetTypeInfo)(
    UINT /* itinfo */,
    LCID /* lcid */,
    ITypeInfo** /* pptinfo */);
```

### <a name="remarks"></a>설명

참조 [IDispatch::GetTypeInfo](/windows/desktop/api/oaidl/nf-oaidl-idispatch-gettypeinfo) Windows SDK에에서 있습니다.

##  <a name="gettypeinfocount"></a>  IDispEventSimpleImpl::GetTypeInfoCount

이 구현의 `IDispatch::GetTypeInfoCount` E_NOTIMPL을 반환 합니다.

```
STDMETHOD(GetTypeInfoCount)(UINT* /* pctinfo */);
```

### <a name="remarks"></a>설명

참조 [IDispatch::GetTypeInfoCount](/windows/desktop/api/oaidl/nf-oaidl-idispatch-gettypeinfocount) Windows SDK에에서 있습니다.

##  <a name="invoke"></a>  IDispEventSimpleImpl::Invoke

이 구현의 `IDispatch::Invoke` 이벤트 처리기 나열 이벤트 싱크 맵 호출 합니다.

```
STDMETHOD(Invoke)(
    DISPID dispidMember,
    REFIID /* riid */,
    LCID lcid,
    WORD /* wFlags */,
    DISPPARMS* pdispparams,
    VARIANT* pvarResult,
    EXCEPINFO* /* pexcepinfo */,
    UINT* /* puArgErr */);
```

### <a name="remarks"></a>설명

참조 [idispatch:: Invoke](/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke)합니다.

##  <a name="unadvise"></a>  IDispEventSimpleImpl::Unadvise

나타내는 이벤트 소스를 사용 하 여 연결을 끊는 *pUnk*합니다.

```
HRESULT Unadvise(IUnknown* pUnk);
```

### <a name="parameters"></a>매개 변수

*pUnk*<br/>
[in] 에 대 한 포인터를 `IUnknown` 이벤트 소스 개체의 인터페이스입니다.

### <a name="return-value"></a>반환 값

S_OK 또는 모든 오류 HRESULT 값입니다.

### <a name="remarks"></a>설명

연결이 끊어지면 이벤트 싱크 맵과에 나열 된 처리기 함수에 이벤트 이상 라우팅됩니다.

> [!NOTE]
>  여러에서 클래스가 파생 되는 경우 `IDispEventSimpleImpl` 이 메서드를 호출 하려는 특정 기본 클래스를 사용 하 여 호출 범위를 지정 하 여 명확 하 게 해야 클래스입니다.

`Unadvise` 에 지정 된 기본 이벤트 소스를 사용 하 여 설정 된 연결을 중단 `pdiid`합니다.

`Unavise` 기준으로 개체의 기본 이벤트 소스의 IID를 가져옵니다 해당 기본 이벤트 소스를 사용 하 여 연결 나누기 [AtlGetObjectSourceInterface](composite-control-global-functions.md#atlgetobjectsourceinterface)합니다.

## <a name="see-also"></a>참고자료

[_ATL_FUNC_INFO 구조체](../../atl/reference/atl-func-info-structure.md)<br/>
[IDispatchImpl 클래스](../../atl/reference/idispatchimpl-class.md)<br/>
[IDispEventImpl 클래스](../../atl/reference/idispeventimpl-class.md)<br/>
[SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
