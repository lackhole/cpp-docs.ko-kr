---
title: ISpecifyPropertyPagesImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl::GetPages
helpviewer_keywords:
- property pages, CLSIDs associated with
- ISpecifyPropertyPages
- ISpecifyPropertyPagesImpl class
ms.assetid: 4e4b9795-b656-4d56-9b8c-85941e7731f9
ms.openlocfilehash: c201cf6d9d89ab1a6a8e888deee1be79e5770490
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495407"
---
# <a name="ispecifypropertypagesimpl-class"></a>ISpecifyPropertyPagesImpl 클래스

이 클래스는 `IUnknown` 를 구현 하 고 [ISpecifyPropertyPages](/windows/win32/api/ocidl/nn-ocidl-ispecifypropertypages) 인터페이스의 기본 구현을 제공 합니다.

> [!IMPORTANT]
>  이 클래스와 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template<class T>
class ATL_NO_VTABLE ISpecifyPropertyPagesImpl
   : public ISpecifyPropertyPages
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
에서 `ISpecifyPropertyPagesImpl`파생 된 클래스입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|Description|
|----------|-----------------|
|[ISpecifyPropertyPagesImpl::GetPages](#getpages)|계산 된 UUID 값 배열을 채웁니다. 각 UUID는 개체의 속성 시트에 표시 될 수 있는 속성 페이지 중 하나에 대 한 CLSID에 해당 합니다.|

## <a name="remarks"></a>설명

[ISpecifyPropertyPages](/windows/win32/api/ocidl/nn-ocidl-ispecifypropertypages) 인터페이스를 사용 하면 클라이언트가 개체에서 지 원하는 속성 페이지의 clsid 목록을 가져올 수 있습니다. 클래스 `ISpecifyPropertyPagesImpl` 는이 인터페이스의 기본 구현을 제공 하 고 `IUnknown` 디버그 빌드에서 정보를 덤프 장치로 전송 하 여를 구현 합니다.

> [!NOTE]
>  개체에서 속성 페이지 `ISpecifyPropertyPages` 를 지원 하지 않는 경우 인터페이스를 노출 하지 마십시오.

**관련 문서** Atl [자습서](../../atl/active-template-library-atl-tutorial.md), [atl 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`ISpecifyPropertyPages`

`ISpecifyPropertyPagesImpl`

## <a name="requirements"></a>요구 사항

**헤더:**

##  <a name="getpages"></a>  ISpecifyPropertyPagesImpl::GetPages

[CAUUID](/windows/win32/api/ocidl/ns-ocidl-cauuid) 구조체의 배열을 개체의 속성 시트에 표시할 수 있는 속성 페이지의 clsid로 채웁니다.

```
STDMETHOD(GetPages)(CAUUID* pPages);
```

### <a name="remarks"></a>설명

ATL은 개체의 속성 맵을 사용 하 여 각 CLSID를 검색 합니다.

Windows SDK [ISpecifyPropertyPages:: GetPages](/windows/win32/api/ocidl/nf-ocidl-ispecifypropertypages-getpages) 를 참조 하세요.

## <a name="see-also"></a>참고자료

[IPropertyPageImpl 클래스](../../atl/reference/ipropertypageimpl-class.md)<br/>
[IPerPropertyBrowsingImpl 클래스](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
