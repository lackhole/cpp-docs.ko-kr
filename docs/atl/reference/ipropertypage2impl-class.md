---
title: IPropertyPage2Impl 클래스
ms.date: 11/04/2016
f1_keywords:
- IPropertyPage2Impl
- ATLCTL/ATL::IPropertyPage2Impl
- ATLCTL/ATL::IPropertyPage2Impl::EditProperty
helpviewer_keywords:
- property pages
- IPropertyPage2 ATL implementation
- IPropertyPage2Impl class
ms.assetid: e89fbe90-203a-47f0-a5de-23616697e1ce
ms.openlocfilehash: bf76182242f7b76e3a2c18f85b72674e88afa737
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62274778"
---
# <a name="ipropertypage2impl-class"></a>IPropertyPage2Impl 클래스

이 클래스는 구현 `IUnknown` 의 기본 구현을 상속 [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<class T>
class IPropertyPage2Impl : public IPropertyPageImpl<T>
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
클래스에서 파생 된 `IPropertyPage2Impl`합니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[IPropertyPage2Impl::EditProperty](#editproperty)|속성 페이지를 활성화할 때 속성 컨트롤에서 포커스를 수신 하도록 지정 합니다. ATL 구현 E_NOTIMPL을 반환합니다.|

## <a name="remarks"></a>설명

합니다 [IPropertyPage2](/windows/desktop/api/ocidl/nn-ocidl-ipropertypage2) 인터페이스를 확장 [IPropertyPage](/windows/desktop/api/ocidl/nn-ocidl-ipropertypage) 추가 하 여는 `EditProperty` 메서드. 이 메서드는 클라이언트가 속성 페이지 개체의 특정 속성을 선택 하는 데 사용 합니다.

클래스 `IPropertyPage2Impl` 에 대 한 E_NOTIMPL을 반환 하기만 `IPropertyPage2::EditProperty`합니다. 하지만 기본 구현을 상속 [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md) 구현 및 `IUnknown` 장치에서 디버그 덤프에 정보를 전송 하 여 작성 합니다.

클래스에서 파생 된 일반적으로 속성 페이지를 만들면 `IPropertyPageImpl`합니다. 추가 지원을 제공 하기 위해 `IPropertyPage2`클래스 정의 수정 하 고 재정의 `EditProperty` 메서드.

**관련 문서** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md), [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IPropertyPage`

[IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)

`IPropertyPage2Impl`

## <a name="requirements"></a>요구 사항

**헤더:** atlctl.h

##  <a name="editproperty"></a>  IPropertyPage2Impl::EditProperty

속성 페이지를 활성화할 때 속성 컨트롤에서 포커스를 수신 하도록 지정 합니다.

```
HRESULT EditProperty(DISPID dispID);
```

### <a name="return-value"></a>반환 값

E_NOTIMPL 반환.

### <a name="remarks"></a>설명

참조 [IPropertyPage2::EditProperty](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage2-editproperty) Windows SDK에에서 있습니다.

## <a name="see-also"></a>참고자료

[IPerPropertyBrowsingImpl 클래스](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[ISpecifyPropertyPagesImpl 클래스](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
