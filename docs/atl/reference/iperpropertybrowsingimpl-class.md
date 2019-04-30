---
title: IPerPropertyBrowsingImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IPerPropertyBrowsingImpl
- ATLCTL/ATL::IPerPropertyBrowsingImpl
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetDisplayString
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetPredefinedStrings
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetPredefinedValue
- ATLCTL/ATL::IPerPropertyBrowsingImpl::MapPropertyToPage
helpviewer_keywords:
- IPerPropertyBrowsingImpl class
- property pages, accessing information
- IPerPropertyBrowsing, ATL implementation
ms.assetid: 0b1a9be3-d242-4767-be69-663a21e4b728
ms.openlocfilehash: 54c475e736425718e954b0e954ea2b327d938556
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62274921"
---
# <a name="iperpropertybrowsingimpl-class"></a>IPerPropertyBrowsingImpl 클래스

이 클래스는 구현 `IUnknown` 클라이언트 개체의 속성 페이지의 정보에 액세스할 수 있습니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```

template <class T>
class ATL_NO_VTABLE IPerPropertyBrowsingImpl :
    public IPerPropertyBrowsing
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
클래스에서 파생 된 `IPerPropertyBrowsingImpl`합니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[IPerPropertyBrowsingImpl::GetDisplayString](#getdisplaystring)|지정된 된 속성을 설명 하는 문자열을 검색 합니다.|
|[IPerPropertyBrowsingImpl::GetPredefinedStrings](#getpredefinedstrings)|지정된 된 속성을 받아들일 수 있는 값에 해당 하는 문자열의 배열을 검색 합니다.|
|[IPerPropertyBrowsingImpl::GetPredefinedValue](#getpredefinedvalue)|지정 된 DISPID로 식별 되는 속성의 값을 포함 하는 VARIANT를 검색 합니다. 검색할 문자열 이름을 연결 된 DISPID `GetPredefinedStrings`합니다. ATL 구현 E_NOTIMPL을 반환합니다.|
|[IPerPropertyBrowsingImpl::MapPropertyToPage](#mappropertytopage)|지정된 된 속성을 사용 하 여 연결 속성 페이지의 CLSID를 검색 합니다.|

## <a name="remarks"></a>설명

합니다 [IPerPropertyBrowsing](/windows/desktop/api/ocidl/nn-ocidl-iperpropertybrowsing) 인터페이스 클라이언트가 개체의 속성 페이지의 정보에 액세스 하는 데 사용 합니다. 클래스 `IPerPropertyBrowsingImpl` 이 인터페이스의 기본 구현을 제공 하 고 구현 `IUnknown` 장치에서 디버그 덤프에 정보를 전송 하 여 작성 합니다.

> [!NOTE]
>  클래스를 파생 되어야 합니다 Microsoft Access 컨테이너 응용 프로그램을 사용 하는 경우 `IPerPropertyBrowsingImpl`합니다. 그렇지 않으면 액세스 컨트롤을 로드 하지 않습니다.

**관련 문서** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md), [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IPerPropertyBrowsing`

`IPerPropertyBrowsingImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlctl.h

##  <a name="getdisplaystring"></a>  IPerPropertyBrowsingImpl::GetDisplayString

지정된 된 속성을 설명 하는 문자열을 검색 합니다.

```
STDMETHOD(GetDisplayString)(
    DISPID dispID,
    BSTR* pBstr);
```

### <a name="remarks"></a>설명

참조 [IPerPropertyBrowsing::GetDisplayString](/windows/desktop/api/ocidl/nf-ocidl-iperpropertybrowsing-getdisplaystring) Windows SDK에에서 있습니다.

##  <a name="getpredefinedstrings"></a>  IPerPropertyBrowsingImpl::GetPredefinedStrings

0 개 항목을 사용 하 여 각 배열을 채웁니다.

```
STDMETHOD(GetPredefinedStrings)(
    DISPID dispID,
    CALPOLESTR* pCaStringsOut,
    CADWORD* pCaCookiesOut);
```

### <a name="return-value"></a>반환 값

ATL의 구현의 [GetPredefinedValue](#getpredefinedvalue) E_NOTIMPL을 반환 합니다.

### <a name="remarks"></a>설명

참조 [IPerPropertyBrowsing::GetPredefinedStrings](/windows/desktop/api/ocidl/nf-ocidl-iperpropertybrowsing-getpredefinedstrings) Windows SDK에에서 있습니다.

##  <a name="getpredefinedvalue"></a>  IPerPropertyBrowsingImpl::GetPredefinedValue

지정 된 DISPID로 식별 되는 속성의 값을 포함 하는 VARIANT를 검색 합니다. 검색할 문자열 이름을 연결 된 DISPID `GetPredefinedStrings`합니다.

```
STDMETHOD(GetPredefinedValue)(
    DISPID dispID,
    DWORD dwCookie,
    VARIANT* pVarOut);
```

### <a name="return-value"></a>반환 값

E_NOTIMPL 반환.

### <a name="remarks"></a>설명

ATL의 구현의 [GetPredefinedStrings](#getpredefinedstrings) 없습니다 해당 문자열을 검색 합니다.

참조 [IPerPropertyBrowsing::GetPredefinedValue](/windows/desktop/api/ocidl/nf-ocidl-iperpropertybrowsing-getpredefinedvalue) Windows SDK에에서 있습니다.

##  <a name="mappropertytopage"></a>  IPerPropertyBrowsingImpl::MapPropertyToPage

지정 된 속성과 연결 된 속성 페이지의 CLSID를 검색 합니다.

```
STDMETHOD(MapPropertyToPage)(
    DISPID dispID,
    CLSID* pClsid);
```

### <a name="remarks"></a>설명

ATL 개체의 속성 맵에 사용 하 여이 정보를 가져옵니다.

참조 [IPerPropertyBrowsing::MapPropertyToPage](/windows/desktop/api/ocidl/nf-ocidl-iperpropertybrowsing-mappropertytopage) Windows SDK에에서 있습니다.

## <a name="see-also"></a>참고자료

[IPropertyPageImpl 클래스](../../atl/reference/ipropertypageimpl-class.md)<br/>
[ISpecifyPropertyPagesImpl 클래스](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
