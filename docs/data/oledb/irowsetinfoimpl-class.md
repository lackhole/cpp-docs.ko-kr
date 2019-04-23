---
title: IRowsetInfoImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- ATL.IRowsetInfoImpl
- IRowsetInfoImpl
- ATL::IRowsetInfoImpl
- ATL.IRowsetInfoImpl.GetProperties
- IRowsetInfoImpl.GetProperties
- ATL::IRowsetInfoImpl::GetProperties
- IRowsetInfoImpl::GetProperties
- GetProperties
- ATL::IRowsetInfoImpl::GetReferencedRowset
- GetReferencedRowset
- ATL.IRowsetInfoImpl.GetReferencedRowset
- IRowsetInfoImpl.GetReferencedRowset
- IRowsetInfoImpl::GetReferencedRowset
- IRowsetInfoImpl::GetSpecification
- ATL.IRowsetInfoImpl.GetSpecification
- IRowsetInfoImpl.GetSpecification
- GetSpecification
- ATL::IRowsetInfoImpl::GetSpecification
helpviewer_keywords:
- IRowsetInfoImpl class
- GetProperties method
- GetReferencedRowset method
- GetSpecification method
ms.assetid: 9c654155-7727-464e-bd31-143e68391a47
ms.openlocfilehash: b42ecf6c03dd1023d1ba150d579f77c4bae8998a
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59029173"
---
# <a name="irowsetinfoimpl-class"></a>IRowsetInfoImpl 클래스

에 대 한 구현을 제공 합니다 [IRowsetInfo](/previous-versions/windows/desktop/ms724541(v=vs.85)) 인터페이스입니다.

## <a name="syntax"></a>구문

```cpp
template <class T, class PropClass = T>
class ATL_NO_VTABLE IRowsetInfoImpl :
   public IRowsetInfo, 
   public CUtlProps<PropClass>
```

### <a name="parameters"></a>매개 변수

*T*<br/>
클래스에서 파생 된 `IRowsetInfoImpl`합니다.

*PropClass*<br/>
기본적으로 사용자 정의 가능한 속성 클래스 *T*합니다.

## <a name="requirements"></a>요구 사항

**헤더:** altdb.h

## <a name="members"></a>멤버

### <a name="interface-methods"></a>인터페이스 메서드

|||
|-|-|
|[GetProperties](#getproperties)|행 집합에서 지 원하는 모든 속성의 현재 설정을 반환 합니다.|
|[GetReferencedRowset](#getreferencedrowset)|책갈피 적용 되는 행 집합에 대 한 인터페이스 포인터를 반환 합니다.|
|[GetSpecification](#getspecification)|이 행 집합을 만든 개체 (명령 또는 세션)에 대 한 인터페이스 포인터를 반환 합니다.|

## <a name="remarks"></a>설명

행 집합에는 필수 인터페이스입니다. 이 클래스를 사용 하 여 행 집합 속성을 구현 합니다 [속성 집합 맵](../../data/oledb/begin-propset-map.md) 명령 클래스에 정의 합니다. 행 집합 클래스를 사용 하 여 명령 클래스의 속성 수를 설정 하는 나타나지만, 명령 또는 세션 개체로 만들 때 런타임 속성의 자체 복사본을 사용 하 여 행 집합 제공 됩니다.

## <a name="getproperties"></a> IRowsetInfoImpl::GetProperties

속성에 대 한 현재 설정을 반환 합니다 `DBPROPSET_ROWSET` 그룹입니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD (GetProperties )(const ULONG cPropertyIDSets,
   const DBPROPIDSET rgPropertyIDSets[],
   ULONG* pcPropertySets,
   DBPROPSET** prgPropertySets);
```

#### <a name="parameters"></a>매개 변수

참조 [irowsetinfo:: Getproperties](/previous-versions/windows/desktop/ms719611(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

## <a name="getreferencedrowset"></a> IRowsetInfoImpl::GetReferencedRowset

책갈피 적용 되는 행 집합에 대 한 인터페이스 포인터를 반환 합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD (GetReferencedRowset )(DBORDINAL iOrdinal,
   REFIID riid,
   IUnknown** ppReferencedRowset);
```

#### <a name="parameters"></a>매개 변수

참조 [IRowsetInfo::GetReferencedRowset](/previous-versions/windows/desktop/ms721145(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다. 합니다 *iOrdinal* 매개 변수는 책갈피 열 이어야 합니다.

## <a name="getspecification"></a> IRowsetInfoImpl::GetSpecification

이 행 집합을 만든 개체 (명령 또는 세션)에 대 한 인터페이스 포인터를 반환 합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD (GetSpecification )(REFIID riid,
   IUnknown** ppSpecification);
```

#### <a name="parameters"></a>매개 변수

참조 [IRowsetInfo::GetSpecification](/previous-versions/windows/desktop/ms716746(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

### <a name="remarks"></a>설명

이 메서드를 사용 하 여 [IGetDataSourceImpl](../../data/oledb/igetdatasourceimpl-class.md) 데이터 원본 개체에서 속성을 검색할 수 있습니다.

## <a name="see-also"></a>참고자료

[OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)