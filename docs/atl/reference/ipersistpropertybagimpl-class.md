---
title: IPersistPropertyBagImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IPersistPropertyBagImpl
- ATLCOM/ATL::IPersistPropertyBagImpl
- ATLCOM/ATL::IPersistPropertyBagImpl::GetClassID
- ATLCOM/ATL::IPersistPropertyBagImpl::InitNew
- ATLCOM/ATL::IPersistPropertyBagImpl::Load
- ATLCOM/ATL::IPersistPropertyBagImpl::Save
helpviewer_keywords:
- IPersistPropertyBagImpl class
ms.assetid: 712af24d-99f8-40f2-9811-53b3ff6e5b19
ms.openlocfilehash: 800c38c15e4ec8028fba9188d75e49be7ca51146
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62274895"
---
# <a name="ipersistpropertybagimpl-class"></a>IPersistPropertyBagImpl 클래스

이 클래스는 구현 `IUnknown` 클라이언트가 제공한 propertybag에 해당 속성을 저장 하는 개체를 허용 합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <class T>
class ATL_NO_VTABLE IPersistPropertyBagImpl : public IPersistPropertyBag
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
클래스에서 파생 된 `IPersistPropertyBagImpl`합니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[IPersistPropertyBagImpl::GetClassID](#getclassid)|개체의 CLSID를 검색합니다.|
|[IPersistPropertyBagImpl::InitNew](#initnew)|새로 만든된 개체를 초기화합니다. ATL 구현은 S_OK를 반환 합니다.|
|[IPersistPropertyBagImpl::Load](#load)|클라이언트가 제공한 propertybag에서 개체의 속성을 로드합니다.|
|[IPersistPropertyBagImpl::Save](#save)|개체의 속성을 클라이언트가 제공한 propertybag에 저장합니다.|

## <a name="remarks"></a>설명

합니다 [IPersistPropertyBag](https://msdn.microsoft.com/library/aa768205.aspx) 인터페이스를 사용 하면 클라이언트에서 제공한 속성 모음에 해당 속성을 저장 하는 개체입니다. 클래스 `IPersistPropertyBagImpl` 이 인터페이스의 기본 구현을 제공 하 고 구현 `IUnknown` 장치에서 디버그 덤프에 정보를 전송 하 여 작성 합니다.

`IPersistPropertyBag` 와 함께 작동 [IPropertyBag](https://msdn.microsoft.com/library/aa768196.aspx) 하 고 [IErrorLog](https://msdn.microsoft.com/library/aa768231.aspx)합니다. 후자의 두 인터페이스는 클라이언트에 의해 구현 되어야 합니다. 통해 `IPropertyBag`, 클라이언트는 저장 하 고 개체의 개별 속성을 로드 합니다. 통해 `IErrorLog`, 개체와 클라이언트 모두에서 발생 한 오류를 보고할 수 있습니다.

**관련 문서** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md), [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IPersistPropertyBag`

`IPersistPropertyBagImpl`

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

##  <a name="getclassid"></a>  IPersistPropertyBagImpl::GetClassID

개체의 CLSID를 검색합니다.

```
STDMETHOD(GetClassID)(CLSID* pClassID);
```

### <a name="remarks"></a>설명

참조 [IPersist::GetClassID](/windows/desktop/api/objidl/nf-objidl-ipersist-getclassid) Windows SDK에에서 있습니다.

##  <a name="initnew"></a>  IPersistPropertyBagImpl::InitNew

새로 만든된 개체를 초기화합니다.

```
STDMETHOD(InitNew)();
```

### <a name="return-value"></a>반환 값

S_OK 반환 합니다.

### <a name="remarks"></a>설명

참조 [IPersistPropertyBag::InitNew](https://msdn.microsoft.com/library/aa768204.aspx) Windows SDK에에서 있습니다.

##  <a name="load"></a>  IPersistPropertyBagImpl::Load

클라이언트가 제공한 propertybag에서 개체의 속성을 로드합니다.

```
STDMETHOD(Load)(LPPROPERTYBAG pPropBag, LPERRORLOG pErrorLog);
```

### <a name="remarks"></a>설명

ATL 개체의 속성 맵에 사용 하 여이 정보를 검색 합니다.

참조 [IPersistPropertyBag::Load](https://msdn.microsoft.com/library/aa768206.aspx) Windows SDK에에서 있습니다.

##  <a name="save"></a>  IPersistPropertyBagImpl::Save

개체의 속성을 클라이언트가 제공한 propertybag에 저장합니다.

```
STDMETHOD(Save)(
    LPPROPERTYBAG pPropBag,
    BOOL fClearDirty,
    BOOL fSaveAllProperties);
```

### <a name="remarks"></a>설명

ATL 개체의 속성 맵에 사용 하 여이 정보를 저장 합니다. 기본적으로이 메서드는 값에 관계 없이 모든 속성을 저장 *fSaveAllProperties*합니다.

참조 [IPersistPropertyBag::Save](https://msdn.microsoft.com/library/aa768207.aspx) Windows SDK에에서 있습니다.

## <a name="see-also"></a>참고자료

[BEGIN_PROP_MAP](property-map-macros.md#begin_prop_map)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
