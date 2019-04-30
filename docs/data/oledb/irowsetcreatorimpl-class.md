---
title: IRowsetCreatorImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- ATL::IRowsetCreatorImpl
- ATL.IRowsetCreatorImpl
- ATL::IRowsetCreatorImpl<T>
- ATL.IRowsetCreatorImpl<T>
- IRowsetCreatorImpl
- IRowsetCreatorImpl.SetSite
- IRowsetCreatorImpl<T>::SetSite
- IRowsetCreatorImpl::SetSite
- SetSite
- ATL.IRowsetCreatorImpl.SetSite
- ATL::IRowsetCreatorImpl<T>::SetSite
- ATL::IRowsetCreatorImpl::SetSite
- ATL.IRowsetCreatorImpl<T>.SetSite
helpviewer_keywords:
- IRowsetCreatorImpl class
- SetSite method
ms.assetid: 92cc950f-7978-4754-8d9a-defa63867d82
ms.openlocfilehash: 3dc5cb06b3eb7f01667e4e1ec09dd60f9befae77
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390791"
---
# <a name="irowsetcreatorimpl-class"></a>IRowsetCreatorImpl 클래스

동일한 기능을 수행 `IObjectWithSite` 하지만 또한 OLE DB 속성을 사용 하면 `DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS`합니다.

## <a name="syntax"></a>구문

```cpp
template < class T >
class ATL_NO_VTABLE IRowsetCreatorImpl
   : public IObjectWithSiteImpl< T >
```

### <a name="parameters"></a>매개 변수

*T*<br/>
파생 된 클래스 `IRowsetCreator`합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atldb.h

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[SetSite](#setsite)|행 집합 개체를 포함 하는 사이트를 설정 합니다.|

## <a name="remarks"></a>설명

이 클래스에서 상속 [IObjectWithSite](/windows/desktop/api/ocidl/nn-ocidl-iobjectwithsite) 재정의 [IObjectWithSite::SetSite](/windows/desktop/api/ocidl/nf-ocidl-iobjectwithsite-setsite)합니다. 공급자 명령 또는 세션 개체를 행 집합을 만들 때 호출 `QueryInterface` 행 집합 개체에서 `IObjectWithSite` 호출 `SetSite` 행 집합 개체를 전달 `IUnkown` 사이트 인터페이스와 인터페이스입니다.

## <a name="setsite"></a> IRowsetCreatorImpl::SetSite

행 집합 개체를 포함 하는 사이트를 설정 합니다. 자세한 내용은 [IObjectWithSite::SetSite](/windows/desktop/api/ocidl/nf-ocidl-iobjectwithsite-setsite)합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD(SetSite )(IUnknown* pCreator);
```

#### <a name="parameters"></a>매개 변수

*pCreator*<br/>
[in] 에 대 한 포인터를 `IUnknown` 행 집합 개체를 관리 하는 사이트의 인터페이스 포인터입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

### <a name="remarks"></a>설명

또한 `IRowsetCreatorImpl::SetSite` OLE DB를 사용 하면 `DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS` 속성입니다.

## <a name="see-also"></a>참고자료

[OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)