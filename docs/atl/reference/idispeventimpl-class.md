---
title: IDispEventImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IDispEventImpl
- ATLCOM/ATL::IDispEventImpl
- ATLCOM/ATL::IDispEventImpl::IDispEventImpl
- ATLCOM/ATL::IDispEventImpl::GetFuncInfoFromId
- ATLCOM/ATL::IDispEventImpl::GetIDsOfNames
- ATLCOM/ATL::IDispEventImpl::GetTypeInfo
- ATLCOM/ATL::IDispEventImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispEventImpl::GetUserDefinedType
helpviewer_keywords:
- IDispEventImpl class
ms.assetid: a64b5288-35cb-4638-aad6-2d15b1c7cf7b
ms.openlocfilehash: 8de620cd6e2433375284f6493b5117c40a356603
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62275323"
---
# <a name="idispeventimpl-class"></a>IDispEventImpl 클래스

이 클래스의 구현을 제공 하는 `IDispatch` 메서드.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <UINT nID, class T,
    const IID* pdiid = &IID_NULL,
    const GUID* plibid = &GUID_NULL,
    WORD wMajor = 0,
    WORD wMinor = 0,
    class tihclass = CcomTypeInfoHolder>
class ATL_NO_VTABLE IDispEventImpl : public IDispEventSimpleImpl<nID, T, pdiid>
```

#### <a name="parameters"></a>매개 변수

*nID*<br/>
원본 개체에 대 한 고유 식별자입니다. 때 `IDispEventImpl` 기본 클래스인 복합 컨트롤의 경우이 매개 변수에 대해 원하는 포함 된 컨트롤의 리소스 ID를 사용 합니다. 다른 경우에는 임의의 양의 정수를 사용 합니다.

*T*<br/>
사용자의 클래스에서 파생 된 `IDispEventImpl`합니다.

*pdiid*<br/>
이 클래스에서 구현 되는 이벤트 인터페이스의 IID에 대 한 포인터입니다. 이 인터페이스를 가리키는 형식 라이브러리에 정의 되어 있어야 *plibid*를 *wMajor*, 및 *wMinor*합니다.

*plibid*<br/>
디스패치 인터페이스를 정의 하는 형식 라이브러리에 대 한 포인터에서 가리키는 *pdiid*합니다. 하는 경우 **& GUID_NULL**, 이벤트 소싱 개체에서 형식 라이브러리를 로드 됩니다.

*wMajor*<br/>
형식 라이브러리의 주 버전입니다. 기본값은 0입니다.

*wMinor*<br/>
형식 라이브러리의 부 버전입니다. 기본값은 0입니다.

*tihclass*<br/>
클래스에 대 한 형식 정보를 관리 하는 데 *T*합니다. 기본값은 형식의 클래스 `CComTypeInfoHolder`있지만 아닌 다른 형식의 클래스를 제공 하 여이 템플릿 매개 변수를 재정의할 수 있습니다 `CComTypeInfoHolder`합니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|이름|설명|
|----------|-----------------|
|[IDispEventImpl::_tihclass](../../atl/reference/idispeventimpl-class.md)|형식 정보를 관리 하는 데 사용 되는 클래스입니다. 기본적으로 `CComTypeInfoHolder`입니다.|

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[IDispEventImpl::IDispEventImpl](#idispeventimpl)|생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[IDispEventImpl::GetFuncInfoFromId](#getfuncinfofromid)|지정된 된 디스패치 식별자에 대 한 함수 인덱스를 찾습니다.|
|[IDispEventImpl::GetIDsOfNames](#getidsofnames)|단일 멤버와 선택적 인수 이름 집합을 해당 집합이 Dispid 정수에 매핑됩니다.|
|[IDispEventImpl::GetTypeInfo](#gettypeinfo)|개체에 대 한 형식 정보를 검색 합니다.|
|[IDispEventImpl::GetTypeInfoCount](#gettypeinfocount)|형식 정보 인터페이스의 수를 검색 합니다.|
|[IDispEventImpl::GetUserDefinedType](#getuserdefinedtype)|사용자 정의 형식의 기본 형식을 검색합니다.|

## <a name="remarks"></a>설명

`IDispEventImpl` 필요 없이 이벤트 인터페이스를 구현 하는 해당 인터페이스의 모든 메서드/이벤트에 대 한 구현 코드를 제공 하는 방법을 제공 합니다. `IDispEventImpl` 구현을 제공 하는 `IDispatch` 메서드. 처리에서 하려는 이벤트에 대 한 구현을 제공 해야 합니다.

`IDispEventImpl` 적절 한 처리기 함수에 이벤트를 라우팅하도록 클래스에서 이벤트 싱크 맵과 함께 작동합니다. 이 클래스를 사용 합니다.

추가 된 [SINK_ENTRY](composite-control-macros.md#sink_entry) 또는 [SINK_ENTRY_EX](composite-control-macros.md#sink_entry_ex) 처리 하려는 각 개체의 각 이벤트에 대 한 이벤트 싱크 맵 매크로입니다. 사용 하는 경우 `IDispEventImpl` 복합 컨트롤의 기본 클래스를 호출할 수 있습니다 [AtlAdviseSinkMap](connection-point-global-functions.md#atladvisesinkmap) 설정 하 고 모든 항목이 맵에 싱크 이벤트에 대 한 이벤트 소스를 사용 하 여 연결을 해제 합니다. 다른 경우 또는 큰 컨트롤에 대 한 호출 [DispEventAdvise](idispeventsimpleimpl-class.md#dispeventadvise) 소스 개체와 기본 클래스 간의 연결을 설정 합니다. 호출 [DispEventUnadvise](idispeventsimpleimpl-class.md#dispeventunadvise) 연결을 끊습니다.

파생 되어야 합니다 `IDispEventImpl` (에 대 한 고유한 값을 사용 하 여 *nID*) 이벤트를 처리 해야 하는 각 개체에 대 한 합니다. 그런 다음 다양 한 원본 개체에 대해 조언 하는 원본 개체에 대해 바이 하 여 기본 클래스를 재사용할 수 있습니다 하지만 한 번에 단일 개체로 처리 될 수 있는 원본 개체의 최대 수로 제한 됩니다 `IDispEventImpl` 기본 클래스입니다.

`IDispEventImpl` 와 동일한 기능을 제공 [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)포인터로 제공이 필요 하지 않고 형식 라이브러리에서 인터페이스에 대 한 형식 정보를 가져와서 제외 하 고는 [_ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md) 구조체입니다. 사용 하 여 `IDispEventSimpleImpl` 경우 하거나 하지 않는 이벤트 인터페이스를 설명 하는 형식 라이브러리가 형식 라이브러리를 사용 하 여 연관 된 오버 헤드를 방지 하려면.

> [!NOTE]
> `IDispEventImpl` 및 `IDispEventSimpleImpl` 의 자체 구현을 제공할 `IUnknown::QueryInterface` 각를 사용 하도록 설정 하면 `IDispEventImpl` 및 `IDispEventSimpleImpl` 여전히 기본 COM 개체에서 클래스 멤버에 대 한 직접 액세스를 허용 하는 동안 별도 COM id로 사용할 클래스를 기본.

ActiveX 이벤트 싱크만 지 원하는 형식의 반환 값 HRESULT 또는 이벤트 처리기 메서드에서; void CE ATL 구현 다른 모든 반환 값 지원 되지 않으며 해당 동작이 정의 되지 않습니다.

자세한 내용은 [IDispEventImpl 지원](../../atl/supporting-idispeventimpl.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`_IDispEvent`

`_IDispEventLocator`

[IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)

`IDispEventImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

##  <a name="getfuncinfofromid"></a>  IDispEventImpl::GetFuncInfoFromId

지정된 된 디스패치 식별자에 대 한 함수 인덱스를 찾습니다.

```
HRESULT GetFuncInfoFromId(
    const IID& iid,
    DISPID dispidMember,
    LCID lcid,
    _ATL_FUNC_INFO& info);
```

### <a name="parameters"></a>매개 변수

*iid*<br/>
[in] 함수의 ID에 대 한 참조입니다.

*dispidMember*<br/>
[in] 디스패치 ID 함수입니다.

*lcid*<br/>
[in] 로캘 컨텍스트의 함수 id입니다.

*info*<br/>
[in] 함수를 호출 하는 방법을 나타내는 구조입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

##  <a name="getidsofnames"></a>  IDispEventImpl::GetIDsOfNames

단일 멤버와 선택적 인수 이름 집합 정수 Dispid 후속 호출에서 사용할 수 있는 해당 집합에 매핑합니다 [idispatch:: Invoke](/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke)합니다.

```
STDMETHOD(GetIDsOfNames)(
    REFIID riid,
    LPOLESTR* rgszNames,
    UINT cNames,
    LCID lcid,
    DISPID* rgdispid);
```

### <a name="remarks"></a>설명

참조 [IDispatch::GetIDsOfNames](/windows/desktop/api/oaidl/nf-oaidl-idispatch-getidsofnames) Windows SDK에에서 있습니다.

##  <a name="gettypeinfo"></a>  IDispEventImpl::GetTypeInfo

인터페이스의 형식 정보를 가져오는 데 사용할 수 있는 개체의 형식 정보를 검색합니다.

```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```

### <a name="remarks"></a>설명

##  <a name="gettypeinfocount"></a>  IDispEventImpl::GetTypeInfoCount

개체에서 제공하는 형식 정보 인터페이스의 수를 검색합니다(0 또는 1).

```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```

### <a name="remarks"></a>설명

참조 [IDispatch::GetTypeInfoCount](/windows/desktop/api/oaidl/nf-oaidl-idispatch-gettypeinfocount) Windows SDK에에서 있습니다.

##  <a name="getuserdefinedtype"></a>  IDispEventImpl::GetUserDefinedType

사용자 정의 형식의 기본 형식을 검색합니다.

```
VARTYPE GetUserDefinedType(
    ITypeInfo* pTI,
    HREFTYPE hrt);
```

### <a name="parameters"></a>매개 변수

*pTI*<br/>
[in] 에 대 한 포인터를 [ITypeInfo](/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) 사용자 정의 형식을 포함 하는 인터페이스입니다.

*hrt*<br/>
[in] 검색 될 형식 설명에 대 한 핸들입니다.

### <a name="return-value"></a>반환 값

Variant의 형식입니다.

### <a name="remarks"></a>설명

참조 [ITypeInfo::GetRefTypeInfo](/windows/desktop/api/oaidl/nf-oaidl-itypeinfo-getreftypeinfo)합니다.

##  <a name="idispeventimpl"></a>  IDispEventImpl::IDispEventImpl

생성자입니다. 클래스 템플릿 매개 변수의 값을 저장 *plibid*, *pdiid*하십시오 *wMajor*, 및 *wMinor*.

```
IDispEventImpl();
```

##  <a name="tihclass"></a>  IDispEventImpl::tihclass

이 형식 정의 클래스 템플릿 매개 변수 인스턴스의 *tihclass*합니다.

```
typedef tihclass _tihclass;
```

### <a name="remarks"></a>설명

기본적으로 클래스는 `CComTypeInfoHolder`합니다. `CComTypeInfoHolder` 클래스에 대 한 형식 정보를 관리합니다.

## <a name="see-also"></a>참고자료

[_ATL_FUNC_INFO 구조체](../../atl/reference/atl-func-info-structure.md)<br/>
[IDispatchImpl 클래스](../../atl/reference/idispatchimpl-class.md)<br/>
[IDispEventSimpleImpl 클래스](../../atl/reference/idispeventsimpleimpl-class.md)<br/>
[SINK_ENTRY](composite-control-macros.md#sink_entry)<br/>
[SINK_ENTRY_EX](composite-control-macros.md#sink_entry_ex)<br/>
[SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
