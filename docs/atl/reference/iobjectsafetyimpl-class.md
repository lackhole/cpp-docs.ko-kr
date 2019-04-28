---
title: IObjectSafetyImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IObjectSafetyImpl
- ATLCTL/ATL::IObjectSafetyImpl
- ATLCTL/ATL::IObjectSafetyImpl::GetInterfaceSafetyOptions
- ATLCTL/ATL::IObjectSafetyImpl::SetInterfaceSafetyOptions
- ATLCTL/ATL::IObjectSafetyImpl::m_dwCurrentSafety
helpviewer_keywords:
- controls [ATL], safe
- safe for scripting and initialization (controls)
- IObjectSafety, ATL implementation
- IObjectSafetyImpl class
ms.assetid: 64e32082-d910-4a8a-a5bf-ebed9145359d
ms.openlocfilehash: e75c52b016fff5bf04fefc86d4289021efc4db8e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62277026"
---
# <a name="iobjectsafetyimpl-class"></a>IObjectSafetyImpl 클래스

이 클래스의 기본 구현을 제공 합니다 `IObjectSafety` 인터페이스 클라이언트를 검색 하 고 개체의 보안 수준을 설정할 수 있도록 합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <class T,DWORD dwSupportedSafety>
class IObjectSafetyImpl
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
클래스에서 파생 된 `IObjectSafetyImpl`합니다.

*dwSupportedSafety*<br/>
컨트롤에 대 한 지원 되는 보안 옵션을 지정합니다. 다음 값 중 하나입니다.

- INTERFACESAFE_FOR_UNTRUSTED_CALLER에서 식별 된 인터페이스를 [SetInterfaceSafetyOptions](#setinterfacesafetyoptions) 매개 변수 `riid` 안전한 이루어져야 합니다.

- INTERFACESAFE_FOR_UNTRUSTED_DATA에서 식별 된 인터페이스를 `SetInterfaceSafetyOptions` 매개 변수 `riid` 해야 안전 하 게 사용할 신뢰할 수 없는 데이터에 대 한 초기화 중입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[IObjectSafetyImpl::GetInterfaceSafetyOptions](#getinterfacesafetyoptions)|개체에 대 한 현재 설정 된 보안 옵션 뿐만 아니라 개체에서 지 원하는 보안 옵션을 검색 합니다.|
|[IObjectSafetyImpl::SetInterfaceSafetyOptions](#setinterfacesafetyoptions)|개체에 초기화 또는 스크립팅을 안전 하 게 합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[IObjectSafetyImpl::m_dwCurrentSafety](#m_dwcurrentsafety)|개체의 현재 보안 수준을 저장합니다.|

## <a name="remarks"></a>설명

클래스 `IObjectSafetyImpl` 의 기본 구현을 제공 `IObjectSafety`합니다. `IObjectSafety` 인터페이스를 사용 하면 클라이언트를 검색 하 여 개체의 보안 수준을 설정 합니다. 예를 들어, 웹 브라우저를 호출할 수 `IObjectSafety::SetInterfaceSafetyOptions` 초기화에 대 한 안전 하거나 안전 컨트롤을 확인 합니다.

사용 합니다 [IMPLEMENTED_CATEGORY](category-macros.md#implemented_category) CATID_SafeForScripting 및 CATID_SafeForInitializing 구성 요소 범주를 사용 하 여 매크로 구성 요소는 안전 하 게 지정 하는 대체 방법을 제공 합니다.

**관련 문서** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md), [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IObjectSafety`

`IObjectSafetyImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlctl.h

##  <a name="getinterfacesafetyoptions"></a>  IObjectSafetyImpl::GetInterfaceSafetyOptions

개체에 대 한 현재 설정 된 보안 옵션 뿐만 아니라 개체에서 지 원하는 보안 옵션을 검색 합니다.

```
HRESULT GetInterfaceSafetyOptions(
    REFIID riid,
    DWORD* pdwSupportedOptions,
    DWORD* pdwEnabledOptions);
```

### <a name="remarks"></a>설명

개체의 구현에서 지 원하는 모든 인터페이스에 대 한 적절 한 값을 반환 하는 구현 `IUnknown::QueryInterface`합니다.

> [!IMPORTANT]
>  지 원하는 개체 `IObjectSafety` 자체 보안 및 위임 하는 모든 개체에 대 한 일을 담당 합니다. 프로그래머가는 사용자의 컨텍스트에서 코드 실행으로 인해 발생 하는 계정에, 사이트 간 스크립팅 하 고 적합 한 영역 확인을 수행 합니다.

참조 [IObjectSafety::GetInterfaceSafetyOptions](https://msdn.microsoft.com/library/aa768223.aspx) Windows SDK에에서 있습니다.

##  <a name="m_dwcurrentsafety"></a>  IObjectSafetyImpl::m_dwCurrentSafety

개체의 현재 보안 수준을 저장합니다.

```
DWORD m_dwCurrentSafety;
```

##  <a name="setinterfacesafetyoptions"></a>  IObjectSafetyImpl::SetInterfaceSafetyOptions

개체를 초기화 하거나 설정 하 여 스크립트에 대 한 안전 하 게 합니다 [m_dwCurrentSafety](#m_dwcurrentsafety) 적절 한 값 멤버입니다.

```
HRESULT SetInterfaceSafetyOptions(
    REFIID riid,
    DWORD dwOptionsSetMask,
    DWORD dwEnabledOptions);
```

### <a name="remarks"></a>설명

개체의 구현에 의해 지원 되지 않습니다 모든 인터페이스에 대 한 구현 하면 E_NOINTERFACE가 반환 `IUnknown::QueryInterface`합니다.

> [!IMPORTANT]
>  지 원하는 개체 `IObjectSafety` 자체 보안 및 위임 하는 모든 개체에 대 한 일을 담당 합니다. 프로그래머가는 사용자의 컨텍스트에서 코드 실행으로 인해 발생 하는 계정에, 사이트 간 스크립팅 하 고 적합 한 영역 확인을 수행 합니다.

참조 [IObjectSafety::SetInterfaceSafetyOptions](https://msdn.microsoft.com/library/aa768225.aspx) Windows SDK에에서 있습니다.

## <a name="see-also"></a>참고자료

[IObjectSafety 인터페이스](https://msdn.microsoft.com/library/aa768224.aspx)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
