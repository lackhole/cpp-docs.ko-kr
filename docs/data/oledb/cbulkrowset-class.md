---
title: CBulkRowset 클래스
ms.date: 11/04/2016
f1_keywords:
- ATL::CBulkRowset
- ATL.CBulkRowset
- ATL::CBulkRowset<TAccessor>
- CBulkRowset
- ATL.CBulkRowset<TAccessor>
- CBulkRowset::AddRefRows
- AddRefRows
- CBulkRowset.AddRefRows
- ATL.CBulkRowset<TAccessor>.AddRefRows
- ATL::CBulkRowset::AddRefRows
- CBulkRowset<TAccessor>::AddRefRows
- ATL.CBulkRowset.AddRefRows
- ATL::CBulkRowset<TAccessor>::AddRefRows
- ATL.CBulkRowset<TAccessor>.CBulkRowset
- ATL::CBulkRowset::CBulkRowset
- CBulkRowset.CBulkRowset
- CBulkRowset::CBulkRowset
- ATL.CBulkRowset.CBulkRowset
- ATL::CBulkRowset<TAccessor>::CBulkRowset
- CBulkRowset<TAccessor>::CBulkRowset
- CBulkRowset
- ATL.CBulkRowset.MoveFirst
- CBulkRowset<TAccessor>.MoveFirst
- ATL.CBulkRowset<TAccessor>.MoveFirst
- ATL::CBulkRowset::MoveFirst
- ATL::CBulkRowset<TAccessor>::MoveFirst
- CBulkRowset::MoveFirst
- CBulkRowset<TAccessor>::MoveFirst
- CBulkRowset.MoveFirst
- CBulkRowset.MoveLast
- ATL.CBulkRowset.MoveLast
- ATL::CBulkRowset<TAccessor>::MoveLast
- CBulkRowset::MoveLast
- CBulkRowset<TAccessor>.MoveLast
- ATL::CBulkRowset::MoveLast
- ATL.CBulkRowset<TAccessor>.MoveLast
- CBulkRowset<TAccessor>::MoveLast
- MoveLast
- ATL.CBulkRowset<TAccessor>.MoveNext
- ATL::CBulkRowset::MoveNext
- CBulkRowset::MoveNext
- ATL.CBulkRowset.MoveNext
- CBulkRowset.MoveNext
- ATL::CBulkRowset<TAccessor>::MoveNext
- CBulkRowset<TAccessor>.MoveNext
- CBulkRowset<TAccessor>::MoveNext
- CBulkRowset::MovePrev
- MovePrev
- CBulkRowset<TAccessor>::MovePrev
- ATL::CBulkRowset<TAccessor>::MovePrev
- CBulkRowset<TAccessor>.MovePrev
- ATL::CBulkRowset::MovePrev
- CBulkRowset.MovePrev
- ATL.CBulkRowset.MovePrev
- ATL.CBulkRowset<TAccessor>.MovePrev
- CBulkRowset<TAccessor>::MoveToBookmark
- CBulkRowset.MoveToBookmark
- MoveToBookmark
- ATL.CBulkRowset.MoveToBookmark
- CBulkRowset::MoveToBookmark
- ATL::CBulkRowset<TAccessor>::MoveToBookmark
- ATL::CBulkRowset::MoveToBookmark
- CBulkRowset.MoveToRatio
- ATL::CBulkRowset::MoveToRatio
- MoveToRatio
- CBulkRowset::MoveToRatio
- ATL.CBulkRowset<TAccessor>.MoveToRatio
- ATL::CBulkRowset<TAccessor>::MoveToRatio
- ATL.CBulkRowset.MoveToRatio
- CBulkRowset<TAccessor>::MoveToRatio
- ReleaseRows
- ATL.CBulkRowset<TAccessor>.ReleaseRows
- ATL::CBulkRowset<TAccessor>::ReleaseRows
- ATL.CBulkRowset.ReleaseRows
- CBulkRowset<TAccessor>::ReleaseRows
- ATL::CBulkRowset::ReleaseRows
- CBulkRowset::ReleaseRows
- CBulkRowset.ReleaseRows
- ATL.CBulkRowset.SetRows
- CBulkRowset::SetRows
- CBulkRowset<TAccessor>.SetRows
- ATL.CBulkRowset<TAccessor>.SetRows
- CBulkRowset<TAccessor>::SetRows
- ATL::CBulkRowset<TAccessor>::SetRows
- ATL::CBulkRowset::SetRows
- CBulkRowset.SetRows
- SetRows
helpviewer_keywords:
- CBulkRowset class
- AddRefRows method
- CBulkRowset class, constructor
- MoveFirst method
- MoveLast method
- MoveNext method
- MovePrev method
- MoveToBookmark method
- MoveToRatio method
- ReleaseRows method
- SetRows method
ms.assetid: c6bde426-c543-4022-a98a-9519d9e2ae59
ms.openlocfilehash: ba6b41a708cd854e398cbaa80609472ebbe167e8
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59023232"
---
# <a name="cbulkrowset-class"></a>CBulkRowset 클래스

인출 하 고 단일 호출으로 여러 행 핸들을 검색 하 여 데이터를 대량으로 작업할 행을 조작 합니다.

## <a name="syntax"></a>구문

```cpp
template <class TAccessor>
class CBulkRowset : public CRowset<TAccessor>
```

### <a name="parameters"></a>매개 변수

*TAccessor*<br/>
접근자 클래스입니다.

## <a name="requirements"></a>요구 사항

**헤더:** atldbcli.h

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[AddRefRows](#addrefrows)|참조 횟수를 증가 시킵니다.|
|[CBulkRowset](#cbulkrowset)|생성자입니다.|
|[MoveFirst](#movefirst)|필요한 경우 새 대량 페치를 수행 하는 데이터의 첫 번째 행을 검색 합니다.|
|[MoveLast](#movelast)|마지막 행을 이동합니다.|
|[MoveNext](#movenext)|데이터의 다음 행을 검색합니다.|
|[MovePrev](#moveprev)|이전 행으로 이동 합니다.|
|[MoveToBookmark](#movetobookmark)|책갈피에서 책갈피로 표시 행 이나 지정된 된 오프셋에서 행을 인출 합니다.|
|[MoveToRatio](#movetoratio)|행 집합의 소수 자릿수 위치에서 시작 하는 행을 인출 합니다.|
|[ReleaseRows](#releaserows)|현재 행을 설정 (`m_nCurrentRow`) 모든 행과 릴리스 합니다.|
|[SetRows](#setrows)|한 번 호출 하 여 검색할 행 핸들의 수를 설정 합니다.|

## <a name="example"></a>예제

다음 예제에서는 사용 된 `CBulkRowset` 클래스입니다.

[!code-cpp[NVC_OLEDB_Consumer#1](../../data/oledb/codesnippet/cpp/cbulkrowset-class_1.cpp)]

## <a name="addrefrows"></a> CBulkRowset::AddRefRows

호출 [irowset:: Addrefrows](/previous-versions/windows/desktop/ms719619(v=vs.85)) bulk 행 집합에서 현재 검색 된 모든 행에 대 한 참조 수를 증가 합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT AddRefRows() throw();
```

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

## <a name="cbulkrowset"></a> CBulkRowset::CBulkRowset

새 `CBulkRowset` 개체 및 기본 행 수를 10으로 설정 합니다.

### <a name="syntax"></a>구문

```cpp
CBulkRowset();
```

## <a name="movefirst"></a> CBulkRowset::MoveFirst

첫 번째 데이터 행을 검색합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT MoveFirst() throw();
```

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

## <a name="movelast"></a> CBulkRowset::MoveLast

마지막 행을 이동합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT MoveLast() throw();
```

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

## <a name="movenext"></a> CBulkRowset::MoveNext

데이터의 다음 행을 검색합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT MoveNext() throw();
```

### <a name="return-value"></a>반환 값

표준 HRESULT입니다. 행 집합의 끝에 도달 하는 경우에 DB_S_ENDOFROWSET 반환 합니다.

## <a name="moveprev"></a> CBulkRowset::MovePrev

이전 행으로 이동 합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT MovePrev() throw();
```

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

## <a name="movetobookmark"></a> CBulkRowset::MoveToBookmark

책갈피 또는 지정 된 오프셋에 있는 행으로 표시 하는 행을 인출 (*lSkip*) 해당 책갈피에서.

### <a name="syntax"></a>구문

```cpp
HRESULT MoveToBookmark(const CBookmarkBase& bookmark,
   DBCOUNTITEM lSkip = 0) throw();
```

#### <a name="parameters"></a>매개 변수

*bookmark*<br/>
[in] 데이터를 인출 하려는 위치를 표시 하는 책갈피입니다.

*lSkip*<br/>
[in] 대상 행에 책갈피에서 행의 수입니다. 하는 경우 *lSkip* 가 0 이면 첫 번째 인출 된 행이 책갈피가 표시 된 행입니다. 하는 경우 *lSkip* 이 1 이면 첫 번째 인출 된 행이 행 책갈피가 표시 된 행 후 합니다. 하는 경우 *lSkip* 가-1 이면 첫 번째 인출 된 행이 책갈피가 표시 된 행 앞에 있는 행입니다.

### <a name="return-value"></a>반환 값

참조 [irowset:: Getdata](/previous-versions/windows/desktop/ms716988(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

## <a name="movetoratio"></a> CBulkRowset::MoveToRatio

행 집합의 소수 자릿수 위치에서 시작 하는 행을 인출 합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT MoveToRatio(DBCOUNTITEM nNumerator,
   DBCOUNTITEM nDenominator)throw();
```

#### <a name="parameters"></a>매개 변수

*nNumerator*<br/>
[in] 데이터를 인출 하는 소수 자릿수 위치를 결정 하는 데 분자입니다.

*nDenominator*<br/>
[in] 데이터를 인출 하는 소수 자릿수 위치를 결정 하는 데 분모입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

### <a name="remarks"></a>설명

`MoveToRatio` 다음 수식에 따라 약 행을 인출 합니다.

`(nNumerator *  RowsetSize ) / nDenominator`

여기서 `RowsetSize` 행 단위로 측정 되는 행 집합의 크기입니다. 이 수식의 정확도 특정 공급자에 따라 달라 집니다. 세부 정보를 참조 하세요 [irowsetscroll::](/previous-versions/windows/desktop/ms709602(v=vs.85)) 에 *OLE DB Programmer's Reference*합니다.

## <a name="releaserows"></a> CBulkRowset::ReleaseRows

호출 [irowset:: Releaserows](/previous-versions/windows/desktop/ms719771(v=vs.85)) bulk 행 집합에서 현재 검색 된 모든 행에 대 한 참조 횟수를 줄여야 합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT ReleaseRows() throw();
```

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

## <a name="setrows"></a> CBulkRowset::SetRows

각 호출에 의해 검색 되는 행 핸들의 수를 설정 합니다.

### <a name="syntax"></a>구문

```cpp
void SetRows(DBROWCOUNT nRows) throw();
```

#### <a name="parameters"></a>매개 변수

*nRows*<br/>
[in] 행 집합 (행 개수)의 새 크기입니다.

### <a name="remarks"></a>설명

이 함수를 호출 하면 행 집합을 열기 전에 이어야 합니다.

## <a name="see-also"></a>참고자료

[OLE DB 소비자 템플릿(C++)](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)