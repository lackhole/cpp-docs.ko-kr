---
title: CSimpleRow 클래스
ms.date: 11/04/2016
f1_keywords:
- CSimpleRow
- ATL::CSimpleRow
- ATL.CSimpleRow
- CSimpleRow::AddRefRow
- AddRefRow
- ATL.CSimpleRow.AddRefRow
- ATL::CSimpleRow::AddRefRow
- CSimpleRow.AddRefRow
- CSimpleRow.Compare
- CSimpleRow::Compare
- CSimpleRow
- ATL::CSimpleRow::CSimpleRow
- CSimpleRow.CSimpleRow
- ATL.CSimpleRow.CSimpleRow
- CSimpleRow::CSimpleRow
- ATL::CSimpleRow::ReleaseRow
- CSimpleRow::ReleaseRow
- ReleaseRow
- CSimpleRow.ReleaseRow
- ATL.CSimpleRow.ReleaseRow
- CSimpleRow.m_dwRef
- CSimpleRow::m_dwRef
- CSimpleRow::m_iRowset
- CSimpleRow.m_iRowset
helpviewer_keywords:
- CSimpleRow class
- AddRefRow method
- Compare method
- CSimpleRow class, constructor
- ReleaseRow method
- m_dwRef
- m_iRowset
ms.assetid: 06d9621d-60cc-4508-8b0c-528d1b1a809b
ms.openlocfilehash: 19b90f4454e784907366ef6cf7e3e7e1b9ada799
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59023843"
---
# <a name="csimplerow-class"></a>CSimpleRow 클래스

사용 되는 행 핸들에 대 한 기본 구현을 제공 합니다 [IRowsetImpl](../../data/oledb/irowsetimpl-class.md) 클래스입니다.

## <a name="syntax"></a>구문

```cpp
class CSimpleRow
```

## <a name="requirements"></a>요구 사항

**헤더:** atldb.h

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[AddRefRow](#addrefrow)|기존 행 핸들에 대 한 참조 횟수를 추가합니다.|
|[비교](#compare)|동일한 행 인스턴스를 참조 하는지에 두 개의 행을 비교 합니다.|
|[CSimpleRow](#csimplerow)|생성자입니다.|
|[ReleaseRow](#releaserow)|행을 해제합니다.|

### <a name="data-members"></a>데이터 멤버

|||
|-|-|
|[m_dwRef](#dwref)|기존 행 핸들에 대 한 참조 수입니다.|
|[m_iRowset](#irowset)|커서를 나타내는 행 집합에는 인덱스입니다.|

## <a name="remarks"></a>설명

행 핸들은 논리적으로 결과 행에 대 한 고유 태그입니다. `IRowsetImpl` 새로 만듭니다 `CSimpleRow` 에서 요청 된 모든 행에 대 한 [irowsetimpl:: Getnextrows](../../data/oledb/irowsetimpl-getnextrows.md)합니다. `CSimpleRow` 기본 템플릿 인수를 그대로의 행 핸들을 사용자 고유의 구현으로 대체할 수 있습니다 `IRowsetImpl`합니다. 이 클래스를 대체 한 유일한 요구 사항은 형식의 단일 매개 변수를 받아들이는 생성자를 제공 하는 대체 클래스는 **긴**합니다.

## <a name="addrefrow"></a> CSimpleRow::AddRefRow

스레드로부터 안전한 방식으로 기존 행 핸들에 대 한 참조 횟수를 추가합니다.

### <a name="syntax"></a>구문

```cpp
DWORD AddRefRow();
```

## <a name="compare"></a> CSimpleRow::Compare

동일한 행 인스턴스를 참조 하는지에 두 개의 행을 비교 합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT Compare(CSimpleRow* pRow);
```

#### <a name="parameters"></a>매개 변수

*pRow*<br/>
`CSimpleRow` 개체에 대한 포인터입니다.

### <a name="return-value"></a>반환 값

일반적으로 S_OK HRESULT 값을 두 행이 동일한 행 인스턴스를 나타내거나 S_FALSE를 두 개 행을 나타내는 다릅니다. 참조 [IRowsetIdentity::IsSameRow](/previous-versions/windows/desktop/ms719629(v=vs.85)) 에 *OLE DB Programmer's Reference* 다른 가능한 반환 값입니다.

## <a name="csimplerow"></a> CSimpleRow::CSimpleRow

생성자입니다.

### <a name="syntax"></a>구문

```cpp
CSimpleRow(DBCOUNTITEM iRowsetCur);
```

#### <a name="parameters"></a>매개 변수

*iRowsetCur*<br/>
[in] 현재 행 집합에 인덱스입니다.

### <a name="remarks"></a>설명

집합 [m_iRowset](../../data/oledb/csimplerow-m-irowset.md) 하 *iRowsetCur*합니다.

## <a name="releaserow"></a> CSimpleRow::ReleaseRow

스레드로부터 안전한 방식으로 행을 해제합니다.

### <a name="syntax"></a>구문

```cpp
DWORD ReleaseRow();
```

## <a name="dwref"></a> CSimpleRow::m_dwRef

기존 행 핸들에 대 한 참조 수입니다.

### <a name="syntax"></a>구문

```cpp
DWORD m_dwRef;
```

## <a name="irowset"></a> CSimpleRow::m_iRowset

커서를 나타내는 행 집합에 인덱스입니다.

### <a name="syntax"></a>구문

```cpp
KeyType m_iRowset;
```

## <a name="see-also"></a>참고자료

[OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[IRowsetImpl 클래스](../../data/oledb/irowsetimpl-class.md)