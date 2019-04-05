---
title: IRowsetImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IRowsetImpl
- IRowsetImpl::AddRefRows
- AddRefRows
- IRowsetImpl.AddRefRows
- ATL::IRowsetImpl::AddRefRows
- ATL.IRowsetImpl.AddRefRows
- IRowsetImpl.CreateRow
- ATL.IRowsetImpl.CreateRow
- ATL::IRowsetImpl::CreateRow
- CreateRow
- IRowsetImpl::CreateRow
- ATL.IRowsetImpl.GetData
- ATL::IRowsetImpl::GetData
- IRowsetImpl::GetData
- IRowsetImpl.GetData
- GetDBStatus
- IRowsetImpl.GetDBStatus
- IRowsetImpl::GetDBStatus
- GetNextRows
- ATL.IRowsetImpl.GetNextRows
- ATL::IRowsetImpl::GetNextRows
- IRowsetImpl::GetNextRows
- IRowsetImpl.GetNextRows
- IRowsetImpl.IRowsetImpl
- ATL::IRowsetImpl::IRowsetImpl
- ATL.IRowsetImpl.IRowsetImpl
- IRowsetImpl::IRowsetImpl
- IRowsetImpl
- ATL::IRowsetImpl::RefRows
- ATL.IRowsetImpl.RefRows
- IRowsetImpl.RefRows
- RefRows
- IRowsetImpl::RefRows
- ATL.IRowsetImpl.ReleaseRows
- ReleaseRows
- IRowsetImpl::ReleaseRows
- ATL::IRowsetImpl::ReleaseRows
- IRowsetImpl.ReleaseRows
- ATL.IRowsetImpl.RestartPosition
- IRowsetImpl::RestartPosition
- RestartPosition
- ATL::IRowsetImpl::RestartPosition
- IRowsetImpl.RestartPosition
- IRowsetImpl.SetDBStatus
- IRowsetImpl::SetDBStatus
- SetDBStatus
- ATL.IRowsetImpl.m_bCanFetchBack
- ATL::IRowsetImpl::m_bCanFetchBack
- IRowsetImpl.m_bCanFetchBack
- IRowsetImpl::m_bCanFetchBack
- m_bCanFetchBack
- IRowsetImpl::m_bCanScrollBack
- ATL::IRowsetImpl::m_bCanScrollBack
- IRowsetImpl.m_bCanScrollBack
- ATL.IRowsetImpl.m_bCanScrollBack
- m_bCanScrollBack
- ATL.IRowsetImpl.m_bReset
- IRowsetImpl.m_bReset
- m_bReset
- IRowsetImpl::m_bReset
- ATL::IRowsetImpl::m_bReset
- IRowsetImpl::m_iRowset
- IRowsetImpl.m_iRowset
- ATL::IRowsetImpl::m_iRowset
- ATL.IRowsetImpl.m_iRowset
- m_iRowset
- IRowsetImpl::m_rgRowHandles
- IRowsetImpl.m_rgRowHandles
- m_rgRowHandles
- ATL::IRowsetImpl::m_rgRowHandles
- ATL.IRowsetImpl.m_rgRowHandles
helpviewer_keywords:
- IRowsetImpl class
- AddRefRows method
- CreateRow method
- GetData method [OLE DB]
- GetDBStatus method
- GetNextRows method
- IRowsetImpl constructor
- RefRows method
- ReleaseRows method
- RestartPosition method
- SetDBStatus method
- m_bCanFetchBack
- m_bCanScrollBack
- m_bReset
- m_iRowset
- m_rgRowHandles
ms.assetid: 6a9189af-7556-45b1-adcb-9d62bb36704c
ms.openlocfilehash: 47b03a542933c6223e098bc9d8fa8d45bf5e047b
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59024454"
---
# <a name="irowsetimpl-class"></a>IRowsetImpl 클래스

`IRowset` 인터페이스의 구현을 제공합니다.

## <a name="syntax"></a>구문

```cpp
template <
   class T,
   class RowsetInterface,
   class RowClass = CSimpleRow,
   class MapClass = CAtlMap <
      RowClass::KeyType,
      RowClass*>>
class ATL_NO_VTABLE IRowsetImpl : public RowsetInterface
```

### <a name="parameters"></a>매개 변수

*T*<br/>
클래스에서 파생 된 `IRowsetImpl`합니다.

*RowsetInterface*<br/>
파생 된 클래스 `IRowsetImpl`합니다.

*RowClass*<br/>
에 대 한 저장소 단위는 `HROW`합니다.

*MapClass*<br/>
공급자가 보유 하는 모든 행 핸들에 대 한 저장소 단위입니다.

## <a name="requirements"></a>요구 사항

**헤더:** atldb.h

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[AddRefRows](#addrefrows)|기존 행 핸들에 대 한 참조 횟수를 추가합니다.|
|[CreateRow](#createrow)|호출한 [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) 새 할당할 `HROW`합니다. 사용자가 직접 호출 되지 않습니다.|
|[GetData](#getdata)|행 집합의 행 복사본에서 데이터를 검색합니다.|
|[GetDBStatus](#getdbstatus)|지정된 된 필드에 대 한 상태를 반환합니다.|
|[GetNextRows](#getnextrows)|행을 순차적으로 인출의 이전 위치를 기억 합니다.|
|[IRowsetImpl](#irowsetimpl)|생성자입니다. 사용자가 직접 호출 되지 않습니다.|
|[RefRows](#refrows)|호출한 [AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) 하 고 [ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md)합니다. 사용자가 직접 호출 되지 않습니다.|
|[ReleaseRows](#releaserows)|행을 해제합니다.|
|[RestartPosition](#restartposition)|다음 인출 위치를 초기 위치로; 위치 변경 즉, 첫 번째 행 집합 때 해당 위치에 만들어집니다.|
|[SetDBStatus](#setdbstatus)|지정된 된 필드에 대 한 상태 플래그를 설정합니다.|

### <a name="data-members"></a>데이터 멤버

|||
|-|-|
|[m_bCanFetchBack](#bcanfetchback)|공급자를 이전 버전과 페치를 지원 하는지 여부를 나타냅니다.|
|[m_bCanScrollBack](#bcanscrollback)|공급자가 해당 커서 스크롤을 이전 버전과 있는지 여부를 나타냅니다.|
|[m_bReset](#breset)|공급자가 해당 커서 위치를 다시 설정 하는지 여부를 나타냅니다. 이 특별 한 의미가 뒤로 스크롤 때나에서 뒤로 인출 [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md)합니다.|
|[m_iRowset](#irowset)|커서를 나타내는 행 집합에는 인덱스입니다.|
|[m_rgRowHandles](#rgrowhandles)|목록 행 핸들입니다.|

## <a name="remarks"></a>설명

[IRowset](/previous-versions/windows/desktop/ms720986(v=vs.85)) 기본 행 집합 인터페이스입니다.

## <a name="addrefrows"></a> IRowsetImpl::AddRefRows

기존 행 핸들에 대 한 참조 횟수를 추가합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD(AddRefRows )(DBCOUNTITEM cRows,
   const HROW rghRows[],
   DBREFCOUNT rgRefCounts[],
   DBROWSTATUS rgRowStatus[]);
```

#### <a name="parameters"></a>매개 변수

참조 [irowset:: Addrefrows](/previous-versions/windows/desktop/ms719619(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

## <a name="createrow"></a> IRowsetImpl::CreateRow

호출 하는 도우미 메서드입니다 [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) 새 할당할 `HROW`합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT CreateRow(DBROWOFFSET lRowsOffset,
   DBCOUNTITEM& cRowsObtained,
   HROW* rgRows);
```

#### <a name="parameters"></a>매개 변수

*lRowsOffset*<br/>
만들고 있는 행의 커서 위치입니다.

*cRowsObtained*<br/>
참조가 생성 된 행의 수를 나타내는 사용자에 게 다시 전달 합니다.

*rgRows*<br/>
배열을 `HROW`s 새로 만든된 행 핸들을 사용 하 여 호출자에 게 반환 합니다.

### <a name="remarks"></a>설명

이 메서드를 호출 하는 행에 있으면 [AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) 반환 합니다. 그렇지 않으면 RowClass 템플릿 변수의 새 인스턴스를 할당 하 고 추가 [m_rgRowHandles](../../data/oledb/irowsetimpl-m-rgrowhandles.md)합니다.

## <a name="getdata"></a> IRowsetImpl::GetData

행 집합의 행 복사본에서 데이터를 검색합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD(GetData )(HROW hRow,
   HACCESSOR hAccessor,
   void* pDstData);
```

#### <a name="parameters"></a>매개 변수

참조 [irowset:: Getdata](/previous-versions/windows/desktop/ms716988(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

에 해당 하는 일부 매개 변수 *OLE DB Programmer's Reference* 매개 변수에서 설명 하는 다른 이름의 `IRowset::GetData`:

|OLE DB 템플릿 매개 변수|*OLE DB Programmer's Reference* 매개 변수|
|--------------------------------|------------------------------------------------|
|*pDstData*|*pData*|

### <a name="remarks"></a>설명

DLL의 OLE DB 데이터 변환을 사용 하 여 데이터 변환도 처리 합니다.

## <a name="getdbstatus"></a> IRowsetImpl::GetDBStatus

지정된 된 필드에 대 한 DBSTATUS 상태 플래그를 반환합니다.

### <a name="syntax"></a>구문

```cpp
virtual DBSTATUS GetDBStatus(RowClass* currentRow,
   ATLCOLUMNINFO* columnNames);
```

#### <a name="parameters"></a>매개 변수

*currentRow*<br/>
[in] 현재 행입니다.

*columnNames*<br/>
[in] 상태 요청 되는 열입니다.

### <a name="return-value"></a>반환 값

합니다 [DBSTATUS](/previous-versions/windows/desktop/ms722617(v=vs.85)) 열에 대 한 플래그입니다.

## <a name="getnextrows"></a> IRowsetImpl::GetNextRows

행을 순차적으로 인출의 이전 위치를 기억 합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD(GetNextRows )(HCHAPTER hReserved,
   DBROWOFFSET lRowsOffset,
   DBROWCOUNT cRows,
   DBCOUNTITEM* pcRowsObtained,
   HROW** prghRows);
```

#### <a name="parameters"></a>매개 변수

참조 [irowset:: Getnextrows](/previous-versions/windows/desktop/ms709827(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

## <a name="irowsetimpl"></a> IRowsetImpl::IRowsetImpl

생성자입니다.

### <a name="syntax"></a>구문

```cpp
IRowsetImpl();
```

### <a name="remarks"></a>설명

일반적으로이 메서드를 직접 호출할 필요가 없습니다.

## <a name="refrows"></a> IRowsetImpl::RefRows

호출한 [AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) 하 고 [ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md) 증가 하거나 기존 행 핸들에 참조 횟수를 해제 합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT RefRows(DBCOUNTITEM cRows,
   const HROWrghRows[],
   DBREFCOUNT rgRefCounts[],
   DBROWSTATUS rgRowStatus[],
   BOOL bAdd);
```

#### <a name="parameters"></a>매개 변수

참조 [irowset:: Addrefrows](/previous-versions/windows/desktop/ms719619(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

## <a name="releaserows"></a> IRowsetImpl::ReleaseRows

행을 해제합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD(ReleaseRows )(DBCOUNTITEM cRows,
   const HROW rghRows[],
   DBROWOPTIONS rgRowOptions[],
   DBREFCOUNT rgRefCounts[],
   DBROWSTATUS rgRowStatus[]);
```

#### <a name="parameters"></a>매개 변수

참조 [irowset:: Releaserows](/previous-versions/windows/desktop/ms719771(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

## <a name="restartposition"></a> IRowsetImpl::RestartPosition

다음 인출 위치를 초기 위치로; 위치 변경 즉, 첫 번째 행 집합 때 해당 위치에 만들어집니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD(RestartPosition )(HCHAPTER /* hReserved */);
```

#### <a name="parameters"></a>매개 변수

참조 [irowset:: Restartposition](/previous-versions/windows/desktop/ms712877(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

### <a name="remarks"></a>설명

행 집합 위치까지 정의 되지 않습니다. `GetNextRow` 라고 합니다. 이동할 수 있습니다 이전 버전과 rowet 호출 하 여 `RestartPosition` 및 다음 인출 또는 뒤로 스크롤.

## <a name="setdbstatus"></a> IRowsetImpl::SetDBStatus

지정된 된 필드에 대 한 DBSTATUS 상태 플래그를 설정합니다.

### <a name="syntax"></a>구문

```cpp
virtual HRESULT SetDBStatus(DBSTATUS* statusFlags,
   RowClass* currentRow,
   ATLCOLUMNINFO* columnInfo);
```

#### <a name="parameters"></a>매개 변수

*statusFlags*<br/>
합니다 [DBSTATUS](/previous-versions/windows/desktop/ms722617(v=vs.85)) 열에 대해 설정할 플래그입니다.

*currentRow*<br/>
현재 행입니다.

*columnInfo*<br/>
상태 설정 되는 열입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

공급자에는 DBSTATUS_S_ISNULL 및 DBSTATUS_S_DEFAULT에 대 한 특수 처리를 제공 하려면이 함수를 재정의 합니다.

## <a name="bcanfetchback"></a> IRowsetImpl::m_bCanFetchBack

공급자를 이전 버전과 페치를 지원 하는지 여부를 나타냅니다.

### <a name="syntax"></a>구문

```cpp
unsigned m_bCanFetchBack:1;
```

### <a name="remarks"></a>설명

에 연결 합니다 `DBPROP_CANFETCHBACKWARDS` 속성에는 `DBPROPSET_ROWSET` 그룹입니다. 공급자를 지원 해야 합니다 `DBPROP_CANFETCHBACKWARDS` 에 대 한 `m_bCanFetchBackwards` 되도록 **true**합니다.

## <a name="bcanscrollback"></a> IRowsetImpl::m_bCanScrollBack

공급자가 해당 커서 스크롤을 이전 버전과 있는지 여부를 나타냅니다.

### <a name="syntax"></a>구문

```cpp
unsigned  m_bCanScrollBack:1;
```

### <a name="remarks"></a>설명

에 연결 합니다 `DBPROP_CANSCROLLBACKWARDS` 속성에는 `DBPROPSET_ROWSET` 그룹입니다. 공급자를 지원 해야 합니다 `DBPROP_CANSCROLLBACKWARDS` 에 대 한 `m_bCanFetchBackwards` 되도록 **true**합니다.

## <a name="breset"></a> IRowsetImpl::m_bReset

커서 위치를 행 집합에 정의 된 경우를 결정 하는 데 사용 되는 비트 플래그입니다.

### <a name="syntax"></a>구문

```cpp
unsigned m_bReset:1;
```

### <a name="remarks"></a>설명

소비자를 호출 하는 경우 [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) 음수를 사용 하 여 `lOffset` 또는 *cRows* 하 고 `m_bReset` 가 true 이면 `GetNextRows` 행 집합의 끝으로 이동 합니다. 경우 `m_bReset` 이 false 인 경우 소비자는 OLE DB 사양에 오류 코드를 수신 합니다. 합니다 `m_bReset` 플래그로 설정 됩니다 **true** 소비자가 호출 하는 경우 및 행 집합을 처음으로 만들어질 [irowsetimpl:: Restartposition](../../data/oledb/irowsetimpl-restartposition.md)합니다. 로 설정 됩니다 **false** 호출 하는 경우 `GetNextRows`합니다.

## <a name="irowset"></a> IRowsetImpl::m_iRowset

커서를 나타내는 행 집합에는 인덱스입니다.

### <a name="syntax"></a>구문

```cpp
DBROWOFFSET m_iRowset;
```

## <a name="rgrowhandles"></a> IRowsetImpl::m_rgRowHandles

현재 공급자에 대 한 응답에서에 포함 된 행 핸들에 대 한 지도가 `GetNextRows`합니다.

### <a name="syntax"></a>구문

```cpp
MapClass m_rgRowHandles;
```

### <a name="remarks"></a>설명

행 핸들은 호출 하 여 제거 `ReleaseRows`합니다. 참조 된 [IRowsetImpl 개요](../../data/oledb/irowsetimpl-class.md) 정의 대 한 *MapClass*합니다.

## <a name="see-also"></a>참고자료

[OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[CSimpleRow 클래스](../../data/oledb/csimplerow-class.md)