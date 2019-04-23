---
title: IRowsetLocateImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- IRowsetLocateImpl
- ATL.IRowsetLocateImpl.Compare
- IRowsetLocateImpl::Compare
- IRowsetLocateImpl.Compare
- ATL::IRowsetLocateImpl::Compare
- GetRowsAt
- IRowsetLocateImpl.GetRowsAt
- ATL::IRowsetLocateImpl::GetRowsAt
- IRowsetLocateImpl::GetRowsAt
- ATL.IRowsetLocateImpl.GetRowsAt
- IRowsetLocateImpl::GetRowsByBookmark
- IRowsetLocateImpl.GetRowsByBookmark
- GetRowsByBookmark
- IRowsetLocateImpl::Hash
- IRowsetLocateImpl.Hash
- m_rgBookmarks
- IRowsetLocateImpl::m_rgBookmarks
- ATL.IRowsetLocateImpl.m_rgBookmarks
- ATL::IRowsetLocateImpl::m_rgBookmarks
- IRowsetLocateImpl.m_rgBookmarks
helpviewer_keywords:
- providers, bookmarks
- IRowsetLocateImpl class
- bookmarks, OLE DB
- Compare method
- GetRowsAt method
- GetRowsByBookmark method
- Hash method
- m_rgbookmarks
ms.assetid: a8aa3149-7ce8-4976-a680-2da193fd3234
ms.openlocfilehash: e3513084697a60a33b9fa2ab02222a9b332cce79
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59039821"
---
# <a name="irowsetlocateimpl-class"></a>IRowsetLocateImpl 클래스

OLE DB 구현 [IRowsetLocate](/previous-versions/windows/desktop/ms721190(v=vs.85)) 인터페이스 행 집합에서 임의의 행을 인출 합니다.

## <a name="syntax"></a>구문

```cpp
template <
   class T,
   class RowsetInterface,
   class RowClass = CSimpleRow,
   class MapClass = CAtlMap < RowClass::KeyType, RowClass* >,
   class BookmarkKeyType = LONG,
   class BookmarkType = LONG,
   class BookmarkMapClass = CAtlMap < RowClass::KeyType, RowClass* >>
class ATL_NO_VTABLE IRowsetLocateImpl : public IRowsetImpl<
       T,
       RowsetInterface,
       RowClass,
       MapClass>
```

### <a name="parameters"></a>매개 변수

*T*<br/>
파생 된 클래스 `IRowsetLocateImpl`합니다.

*RowsetInterface*<br/>
파생 된 클래스 `IRowsetImpl`합니다.

*RowClass*<br/>
에 대 한 저장소 단위는 `HROW`합니다.

*MapClass*<br/>
공급자가 보유 하는 모든 행 핸들에 대 한 저장소 단위입니다.

*BookmarkKeyType*<br/>
긴 문자열 등 책갈피의 형식입니다. 일반 책갈피에는 최소한 2 바이트 길이의 있어야 합니다. (OLE DB에 대 한 싱글바이트 길이 이기 [표준 책갈피](/previous-versions/windows/desktop/ms712954(v=vs.85))`DBBMK_FIRST`를 `DBBMK_LAST`, 및 `DBBMK_INVALID`.)

*BookmarkType*<br/>
책갈피-데이터 관계를 유지 관리에 대 한 매핑 메커니즘입니다.

*BookmarkMapClass*<br/>
책갈피를 소유 하는 모든 행 핸들에 대 한 저장소 단위입니다.

## <a name="requirements"></a>요구 사항

**헤더**: atldb.h

## <a name="members"></a>멤버

### <a name="interface-methods"></a>인터페이스 메서드

|||
|-|-|
|[Compare](#compare)|두 개의 책갈피를 비교합니다.|
|[GetRowsAt](#getrowsat)|책갈피에서의 오프셋으로 지정 된 행부터 행을 인출 합니다.|
|[GetRowsByBookmark](#getrowsbybookmark)|지정한 책갈피를 일치 하는 행을 인출 합니다.|
|[해시](#hash)|지정 된 책갈피에 대 한 값을 해시 하는 반환 합니다.|

### <a name="data-members"></a>데이터 멤버

|||
|-|-|
|[m_rgBookmarks](#rgbookmarks)|책갈피의 배열입니다.|

## <a name="remarks"></a>설명

`IRowsetLocateImpl` OLE DB 템플릿 구현 된 [IRowsetLocate](/previous-versions/windows/desktop/ms721190(v=vs.85)) 인터페이스입니다. `IRowsetLocate` 행 집합에서 임의의 행을 인출 하는 데 사용 됩니다. 이 인터페이스를 구현 하지 않는 행 집합은을 `sequential` 행 집합입니다. 때 `IRowsetLocate` 가 행 집합 열 0이 행에 대 한 책갈피가;이 칼럼을 읽은 같은 행의 위치를 변경 하는 책갈피 값을 가져옵니다.

`IRowsetLocateImpl` 공급자에 책갈피 지원을 구현 하는 데 사용 됩니다. 책갈피는 자리 표시자 (인덱스 행 집합에서) 소비자는 행에 신속 하 게 반환할 수 있도록 하는 고속 데이터에 액세스할 수 있습니다. 공급자 책갈피 수 있는 고유 하 게 결정 한 행을 식별 합니다. 사용 하 여 `IRowsetLocateImpl` 메서드, 책갈피를 비교할 수 있습니다, fetch 행에서 오프셋을 책갈피 행 인출 및 책갈피에 대 한 해시 값을 반환 합니다.

행 집합의 OLE DB 책갈피를 지원 하려면이 클래스에서 상속 하는 행 집합을 확인 합니다.

책갈피 지원 구현에 대 한 정보를 참조 하세요. [책갈피에 대 한 공급자 지원](../../data/oledb/provider-support-for-bookmarks.md) 에 *Visual C++ Programmer's Guide* 및 [책갈피](/previous-versions/windows/desktop/ms709728(v=vs.85)) 합니다 에서 *OLE DB Programmer's Reference* 플랫폼 SDK에에서 있습니다.

## <a name="compare"></a> IRowsetLocateImpl::Compare

두 개의 책갈피를 비교합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD (Compare )(HCHAPTER /* hReserved */,
   DBBKMARK cbBookmark1,
   const BYTE* pBookmark1,
   DBBKMARK cbBookmark2,
   const BYTE* pBookmark2,
   DBCOMPARE* pComparison);
```

#### <a name="parameters"></a>매개 변수

참조 [IRowsetLocate::Compare](/previous-versions/windows/desktop/ms709539(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

### <a name="remarks"></a>설명

중 책갈피 표준 수 OLE DB 정의 [표준 책갈피](/previous-versions/windows/desktop/ms712954(v=vs.85)) (`DBBMK_FIRST`를 `DBBMK_LAST`, 또는 `DBBMK_INVALID`). 반환 된 값 `pComparison` 두 책갈피 간의 관계를 나타냅니다.

- DBCOMPARE_LT (`cbBookmark1` 하기 전에 `cbBookmark2`.)

- DBCOMPARE_EQ (`cbBookmark1` 값과 같음 `cbBookmark2`.)

- DBCOMPARE_GT (`cbBookmark1` 후 `cbBookmark2`.)

- DBCOMPARE_NE (책갈피는 같음 및 정렬 되지 않습니다.)

- DBCOMPARE_NOTCOMPARABLE (책갈피를 비교할 수 없습니다.)

## <a name="getrowsat"></a> IRowsetLocateImpl::GetRowsAt

책갈피에서의 오프셋으로 지정 된 행부터 행을 인출 합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD (GetRowsAt )(HWATCHREGION /* hReserved1 */,
   HCHAPTER hReserved2,
   DBBKMARK cbBookmark,
   const BYTE* pBookmark,
   DBROWOFFSET lRowsOffset,
   DBROWCOUNT cRows,
   DBCOUNTITEM* pcRowsObtained,
   HROW** prghRows);
```

#### <a name="parameters"></a>매개 변수

참조 [irowsetlocate:: Getrowsat](/previous-versions/windows/desktop/ms723031(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

### <a name="remarks"></a>설명

대신 인출할 커서 위치에서 사용 하 여 [IRowset::GetRowsAt](/previous-versions/windows/desktop/ms723031(v=vs.85))합니다.

`IRowsetLocateImpl::GetRowsAt` 커서 위치를 변경 하지 않습니다.

## <a name="getrowsbybookmark"></a> IRowsetLocateImpl::GetRowsByBookmark

지정한 책갈피를 일치 하는 하나 이상의 행을 인출 합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD (GetRowsByBookmark )(HCHAPTER /* hReserved */,
   DBCOUNTITEM cRows,
   const DBBKMARK rgcbBookmarks[],
   const BYTE* rgpBookmarks,
   HROW rghRows[],
   DBROWSTATUS* rgRowStatus[]);
```

#### <a name="parameters"></a>매개 변수

*hReserved*<br/>
[in] 에 해당 *hChapter* 매개 변수를 [irowsetlocate:: Getrowsbybookmark](/previous-versions/windows/desktop/ms725420(v=vs.85))합니다.

다른 매개 변수를 참조 하세요 [irowsetlocate:: Getrowsbybookmark](/previous-versions/windows/desktop/ms725420(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

### <a name="remarks"></a>설명

책갈피는 정의한 값 또는 OLE DB 수 [표준 책갈피](/previous-versions/windows/desktop/ms712954(v=vs.85)) (`DBBMK_FIRST` 또는 `DBBMK_LAST`). 커서 위치를 변경 하지 않습니다.

## <a name="hash"></a> IRowsetLocateImpl::Hash

지정 된 책갈피에 대 한 값을 해시 하는 반환 합니다.

### <a name="syntax"></a>구문

```cpp
STDMETHOD (Hash )(HCHAPTER /* hReserved */,
   DBBKMARK cbBookmarks,
   const DBBKMARK* rgcbBookmarks[],
   const BYTE* rgpBookmarks[],
   DBHASHVALUE rgHashValues[],
   DBROWSTATUS rgBookmarkStatus[]);
```

#### <a name="parameters"></a>매개 변수

*hReserved*<br/>
[in] 에 해당 *hChapter* 매개 변수를 [IRowsetLocate::Hash](/previous-versions/windows/desktop/ms709697(v=vs.85))합니다.

다른 매개 변수를 참조 하세요 [IRowsetLocate::Hash](/previous-versions/windows/desktop/ms709697(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

## <a name="rgbookmarks"></a> IRowsetLocateImpl::m_rgBookmarks

책갈피의 배열입니다.

### <a name="syntax"></a>구문

```cpp
CAtlArray<DBROWCOUNT> m_rgBookmarks;
```

## <a name="see-also"></a>참고자료

[OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[IRowsetLocate:IRowset](/previous-versions/windows/desktop/ms721190(v=vs.85))
[공급자의 책갈피 지원](../../data/oledb/provider-support-for-bookmarks.md)<br/>
[책갈피](/previous-versions/windows/desktop/ms709728(v=vs.85))