---
title: IDBCreateSessionImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IDBCreateSessionImpl
- ATL.IDBCreateSessionImpl
- ATL::IDBCreateSessionImpl
- IDBCreateSessionImpl::CreateSession
- IDBCreateSessionImpl.CreateSession
- CreateSession
helpviewer_keywords:
- IDBCreateSessionImpl class
- CreateSession method
ms.assetid: 48c02c5c-8362-45ac-af8e-bb119cf8c5c7
ms.openlocfilehash: ae59abc542a4599d289c099801fc34d56b2b13d4
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59028537"
---
# <a name="idbcreatesessionimpl-class"></a>IDBCreateSessionImpl 클래스

에 대 한 구현을 제공 합니다 [IDBCreateSession](/previous-versions/windows/desktop/ms724076(v=vs.85)) 인터페이스입니다.

## <a name="syntax"></a>구문

```cpp
template <class T, class SessionClass>
class ATL_NO_VTABLE IDBCreateSessionImpl
   : public IDBCreateSession
```

### <a name="parameters"></a>매개 변수

*T*<br/>
파생 된 클래스

*SessionClass*<br/>
세션 개체입니다.

## <a name="requirements"></a>요구 사항

**헤더:** atldb.h

## <a name="members"></a>멤버

### <a name="interface-methods"></a>인터페이스 메서드

|||
|-|-|
|[CreateSession](#createsession)|데이터 원본 개체에서 새 세션을 만들고 새로 만들어진된 세션에서 요청된 된 인터페이스를 반환 합니다.|

## <a name="remarks"></a>설명

데이터 원본 개체에는 필수 인터페이스입니다.

## <a name="createsession"></a> IDBCreateSessionImpl::CreateSession

데이터 원본 개체에서 새 세션을 만들고 새로 만들어진된 세션에서 요청된 된 인터페이스를 반환 합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD(CreateSession)(IUnknown * pUnkOuter,
   REFIID riid,
   IUnknown ** ppDBSession);
```

#### <a name="parameters"></a>매개 변수

참조 [idbcreatesession:: Createsession](/previous-versions/windows/desktop/ms714942(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

## <a name="see-also"></a>참고자료

[OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)