---
title: IColumnsInfoImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- ATL.IColumnsInfoImpl<T>
- ATL::IColumnsInfoImpl
- IColumnsInfoImpl
- ATL.IColumnsInfoImpl
- ATL::IColumnsInfoImpl<T>
- GetColumnInfo
- ATL::IColumnsInfoImpl::GetColumnInfo
- ATL.IColumnsInfoImpl.GetColumnInfo
- ATL::IColumnsInfoImpl<T>::GetColumnInfo
- IColumnsInfoImpl::GetColumnInfo
- IColumnsInfoImpl<T>::GetColumnInfo
- IColumnsInfoImpl.GetColumnInfo
- IColumnsInfoImpl<T>::MapColumnIDs
- MapColumnIDs
- ATL::IColumnsInfoImpl::MapColumnIDs
- IColumnsInfoImpl.MapColumnIDs
- ATL::IColumnsInfoImpl<T>::MapColumnIDs
- IColumnsInfoImpl::MapColumnIDs
- ATL.IColumnsInfoImpl<T>.MapColumnIDs
- ATL.IColumnsInfoImpl.MapColumnIDs
helpviewer_keywords:
- IColumnsInfoImpl class
- GetColumnInfo method
- MapColumnIDs method
ms.assetid: ba74c1c5-2eda-4452-8b57-84919fa0d066
ms.openlocfilehash: d9fbe95f87cfdf51ae9c52c7890e6f6c4075c89a
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59039795"
---
# <a name="icolumnsinfoimpl-class"></a>IColumnsInfoImpl 클래스

구현을 제공 합니다 [IColumnsInfo](/previous-versions/windows/desktop/ms724541(v=vs.85)) 인터페이스입니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
class ATL_NO_VTABLE IColumnsInfoImpl :
   public IColumnsInfo, 
   public CDBIDOps
```

### <a name="parameters"></a>매개 변수

*T*<br/>
클래스에서 파생 된 `IColumnsInfoImpl`합니다.

## <a name="requirements"></a>요구 사항

**헤더:** atldb.h

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[GetColumnInfo](#getcolumninfo)|대부분의 소비자에 필요한 열 메타 데이터를 반환 합니다.|
|[MapColumnIDs](#mapcolumnids)|지정된 된 열 Id로 식별 되는 행 집합의 열 서 수의 배열을 반환 합니다.|

## <a name="remarks"></a>설명

행 집합 및 명령에는 필수 인터페이스입니다. 공급자의 동작을 수정 하려면 `IColumnsInfo` 공급자 열 지도 수정 해야 하는 구현 합니다.

## <a name="getcolumninfo"></a> IColumnsInfoImpl::GetColumnInfo

대부분의 소비자에 필요한 열 메타 데이터를 반환 합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD (GetColumnInfo)(DBORDINAL* pcColumns,
   DBCOLUMNINFO** prgInfo,
   OLECHAR** ppStringsBuffer);
```

#### <a name="parameters"></a>매개 변수

참조 [icolumnsinfo:: Getcolumninfo](/previous-versions/windows/desktop/ms722704\(v=vs.85\)) 에 *OLE DB Programmer's Reference*합니다.

## <a name="mapcolumnids"></a> IColumnsInfoImpl::MapColumnIDs

지정된 된 열 Id로 식별 되는 행 집합의 열 서 수의 배열을 반환 합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD (MapColumnIDs)(DBORDINAL cColumnIDs,
   const DBID rgColumnIDs[],
   DBORDINAL rgColumns[]);
```

#### <a name="parameters"></a>매개 변수

참조 [IColumnsInfo::MapColumnIDs](/previous-versions/windows/desktop/ms714200(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

## <a name="see-also"></a>참고자료

[OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)