---
title: IAccessorImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IAccessorImpl
- ATL.IAccessorImpl.IAccessorImpl
- ATL::IAccessorImpl::IAccessorImpl
- IAccessorImpl::IAccessorImpl
- IAccessorImpl.IAccessorImpl
- IAccessorImpl
- ATL::IAccessorImpl::AddRefAccessor
- AddRefAccessor
- IAccessorImpl::AddRefAccessor
- IAccessorImpl.AddRefAccessor
- ATL.IAccessorImpl.AddRefAccessor
- IAccessorImpl::CreateAccessor
- CreateAccessor
- ATL::IAccessorImpl::CreateAccessor
- IAccessorImpl.CreateAccessor
- ATL.IAccessorImpl.CreateAccessor
- IAccessorImpl.GetBindings
- ATL::IAccessorImpl::GetBindings
- IAccessorImpl::GetBindings
- GetBindings
- ATL.IAccessorImpl.GetBindings
- ReleaseAccessor
- IAccessorImpl::ReleaseAccessor
- ATL.IAccessorImpl.ReleaseAccessor
- ATL::IAccessorImpl::ReleaseAccessor
- IAccessorImpl.ReleaseAccessor
helpviewer_keywords:
- IAccessorImpl class
- IAccessorImpl class, constructor
- IAccessorImpl constructor
- AddRefAccessor method
- CreateAccessor method
- GetBindings method
- ReleaseAccessor method
ms.assetid: 768606da-8b71-417c-a62c-88069ce7730d
ms.openlocfilehash: a4f98cdfea9ea1e82ec0a3de09e292604a6c199f
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59032117"
---
# <a name="iaccessorimpl-class"></a>IAccessorImpl 클래스

구현을 제공 합니다 [IAccessor](/previous-versions/windows/desktop/ms719672(v=vs.85)) 인터페이스입니다.

## <a name="syntax"></a>구문

```cpp
template <class T,
   class BindType = ATLBINDINGS,
   class BindingVector = CAtlMap <HACCESSOR hAccessor, BindType* pBindingsStructure>>
class ATL_NO_VTABLE IAccessorImpl : public IAccessorImplBase<BindType>
```

### <a name="parameters"></a>매개 변수

*T*<br/>
행 집합이 나 명령 개체 클래스입니다.

*BindType*<br/>
바인딩 정보에 대 한 저장소 단위입니다. 기본값은는 `ATLBINDINGS` 구조 (atldb.h 참조).

*BindingVector*<br/>
열 정보에 대 한 저장소 단위입니다. 기본값은 [CAtlMap](../../atl/reference/catlmap-class.md) 여기서 주요 요소는는 HACCESSOR 값 이며 값 요소에 대 한 포인터를 `BindType` 구조입니다.

## <a name="requirements"></a>요구 사항

**헤더:** atldb.h

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[IAccessorImpl](#iaccessorimpl)|생성자입니다.|

### <a name="interface-methods"></a>인터페이스 메서드

|||
|-|-|
|[AddRefAccessor](#addrefaccessor)|기존 접근자에 대 한 참조 횟수를 추가합니다.|
|[CreateAccessor](#createaccessor)|바인딩 집합에서 접근자를 만듭니다.|
|[GetBindings](#getbindings)|접근자에서 바인딩을 반환합니다.|
|[ReleaseAccessor](#releaseaccessor)|접근자를 해제합니다.|

## <a name="remarks"></a>설명

이 행 집합 및 명령에 대해 필수입니다. OLE DB 공급자는 HACCESSOR 구현에 필요한 태그를 배열에는 [DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) 구조입니다. 제공한 HACCESSORs `IAccessorImpl` 의 주소는 `BindType` 구조입니다. 기본적으로 `BindType` 으로 정의 되는 `ATLBINDINGS` 에서 `IAccessorImpl`의 템플릿 정의 합니다. `BindType` 사용 하는 메커니즘을 제공 `IAccessorImpl` 의 요소 수를 추적 하는 `DBBINDING` 참조 개수 및 접근자 플래그 뿐만 아니라 배열입니다.

## <a name="iaccessorimpl"></a> IAccessorImpl::IAccessorImpl

생성자입니다.

### <a name="syntax"></a>구문

```cpp
IAccessorImpl();
```

## <a name="addrefaccessor"></a> IAccessorImpl::AddRefAccessor

기존 접근자에 대 한 참조 횟수를 추가합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD(AddRefAccessor)(HACCESSOR hAccessor,
   DBREFCOUNT* pcRefCount);
```

#### <a name="parameters"></a>매개 변수

참조 [IAccessor::AddRefAccessor](/previous-versions/windows/desktop/ms714978(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

## <a name="createaccessor"></a> IAccessorImpl::CreateAccessor

바인딩 집합에서 접근자를 만듭니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD(CreateAccessor)(DBACCESSORFLAGS dwAccessorFlags,
   DBCOUNTITEM cBindings,
   const DBBINDING rgBindings[],
   DBLENGTH cbRowSize,
   HACCESSOR* phAccessor,
   DBBINDSTATUS rgStatus[]);
```

#### <a name="parameters"></a>매개 변수

참조 [iaccessor:: Createaccessor](/previous-versions/windows/desktop/ms720969(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

## <a name="getbindings"></a> IAccessorImpl::GetBindings

접근자에서 소비자에서 기본 열 바인딩을 반환합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD(GetBindings)(HACCESSOR hAccessor,
   DBACCESSORFLAGS* pdwAccessorFlags,
   DBCOUNTITEM* pcBindings,
   DBBINDING** prgBindings);
```

#### <a name="parameters"></a>매개 변수

참조 [IAccessor::GetBindings](/previous-versions/windows/desktop/ms721253(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

## <a name="releaseaccessor"></a> IAccessorImpl::ReleaseAccessor

접근자를 해제합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD(ReleaseAccessor)(HACCESSOR hAccessor,
   DBREFCOUNT* pcRefCount);
```

#### <a name="parameters"></a>매개 변수

참조 [iaccessor:: Releaseaccessor](/previous-versions/windows/desktop/ms719717(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

## <a name="see-also"></a>참고자료

[OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)