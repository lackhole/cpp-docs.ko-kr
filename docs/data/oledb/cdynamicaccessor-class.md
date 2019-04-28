---
title: CDynamicAccessor 클래스
ms.date: 11/04/2016
f1_keywords:
- ATL.CDynamicAccessor
- ATL::CDynamicAccessor
- CDynamicAccessor
- ATL::CDynamicAccessor::AddBindEntry
- AddBindEntry
- CDynamicAccessor.AddBindEntry
- CDynamicAccessor::AddBindEntry
- ATL.CDynamicAccessor.AddBindEntry
- CDynamicAccessor::CDynamicAccessor
- ATL::CDynamicAccessor::CDynamicAccessor
- ATL.CDynamicAccessor.CDynamicAccessor
- CDynamicAccessor.CDynamicAccessor
- ATL::CDynamicAccessor::Close
- ATL.CDynamicAccessor.Close
- CDynamicAccessor.Close
- CDynamicAccessor::Close
- ATL.CDynamicAccessor.GetBlobHandling
- CDynamicAccessor::GetBlobHandling
- ATL::CDynamicAccessor::GetBlobHandling
- GetBlobHandling
- CDynamicAccessor.GetBlobHandling
- ATL::CDynamicAccessor::GetBlobSizeLimit
- CDynamicAccessor.GetBlobSizeLimit
- CDynamicAccessor::GetBlobSizeLimit
- GetBlobSizeLimit
- ATL.CDynamicAccessor.GetBlobSizeLimit
- CDynamicAccessor.GetBookmark
- GetBookmark
- CDynamicAccessor::GetBookmark
- ATL.CDynamicAccessor.GetBookmark
- ATL::CDynamicAccessor::GetBookmark
- ATL.CDynamicAccessor.GetColumnCount
- ATL::CDynamicAccessor::GetColumnCount
- CDynamicAccessor::GetColumnCount
- CDynamicAccessor.GetColumnCount
- GetColumnCount
- CDynamicAccessor.GetColumnFlags
- ATL::CDynamicAccessor::GetColumnFlags
- ATL.CDynamicAccessor.GetColumnFlags
- CDynamicAccessor::GetColumnFlags
- GetColumnFlags
- GetColumnInfo
- ATL.CDynamicAccessor.GetColumnInfo
- ATL::CDynamicAccessor::GetColumnInfo
- CDynamicAccessor.GetColumnInfo
- CDynamicAccessor::GetColumnInfo
- ATL::CDynamicAccessor::GetColumnName
- GetColumnName
- ATL.CDynamicAccessor.GetColumnName
- CDynamicAccessor::GetColumnName
- CDynamicAccessor.GetColumnName
- ATL.CDynamicAccessor.GetColumnType
- CDynamicAccessor::GetColumnType
- GetColumnType
- CDynamicAccessor.GetColumnType
- ATL::CDynamicAccessor::GetColumnType
- CDynamicAccessor.GetLength
- ATL.CDynamicAccessor.GetLength
- CDynamicAccessor::GetLength
- ATL::CDynamicAccessor::GetLength
- CDynamicAccessor.GetOrdinal
- ATL::CDynamicAccessor::GetOrdinal
- CDynamicAccessor::GetOrdinal
- ATL.CDynamicAccessor.GetOrdinal
- GetOrdinal
- ATL::CDynamicAccessor::GetStatus
- CDynamicAccessor.GetStatus
- ATL.CDynamicAccessor.GetStatus
- CDynamicAccessor::GetStatus
- GetValue
- CDynamicAccessor::GetValue<ctype>
- ATL.CDynamicAccessor.GetValue<ctype>
- CDynamicAccessor.GetValue
- CDynamicAccessor::GetValue
- ATL.CDynamicAccessor.GetValue
- ATL::CDynamicAccessor::GetValue
- ATL::CDynamicAccessor::GetValue<ctype>
- CDynamicAccessor::SetBlobHandling
- CDynamicAccessor.SetBlobHandling
- ATL::CDynamicAccessor::SetBlobHandling
- SetBlobHandling
- ATL.CDynamicAccessor.SetBlobHandling
- CDynamicAccessor::SetBlobSizeLimit
- SetBlobSizeLimit
- CDynamicAccessor.SetBlobSizeLimit
- ATL.CDynamicAccessor.SetBlobSizeLimit
- ATL::CDynamicAccessor::SetBlobSizeLimit
- ATL::CDynamicAccessor::SetLength
- CDynamicAccessor.SetLength
- CDynamicAccessor::SetLength
- ATL.CDynamicAccessor.SetLength
- CDynamicAccessor::SetStatus
- ATL::CDynamicAccessor::SetStatus
- CDynamicAccessor.SetStatus
- ATL.CDynamicAccessor.SetStatus
- ATL.CDynamicAccessor.SetValue
- ATL::CDynamicAccessor::SetValue
- ATL::CDynamicAccessor::SetValue<ctype>
- CDynamicAccessor.SetValue
- ATL.CDynamicAccessor.SetValue<ctype>
- CDynamicAccessor::SetValue
- CDynamicAccessor::SetValue<ctype>
helpviewer_keywords:
- CDynamicAccessor class
- AddBindEntry method
- CDynamicAccessor class, constructor
- Close method
- GetBlobHandling method
- GetBlobSizeLimit method
- GetBookmark method
- GetColumnCount method
- GetColumnFlags method
- GetColumnInfo method
- GetColumnName method
- GetColumnType method
- GetLength method
- GetOrdinal method
- GetStatus method
- GetValue method
- SetBlobHandling method
- SetBlobSizeLimit method
- SetLength method
- SetStatus method
- SetValue method
ms.assetid: 374b13b7-1f09-457d-9e6b-df260ff4d178
ms.openlocfilehash: 19b8d0c86044e04cc60fd7aab89ec828c46f5fb9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62209300"
---
# <a name="cdynamicaccessor-class"></a>CDynamicAccessor 클래스

데이터베이스 스키마(데이터베이스의 내부 구조)에 대해 모를 때 데이터 소스에 액세스할 수 있습니다.

## <a name="syntax"></a>구문

```cpp
class CDynamicAccessor : public CAccessorBase
```

## <a name="requirements"></a>요구 사항

**헤더**: atldbcli.h

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[AddBindEntry](#addbindentry)|기본 접근자를 재정의할 때 바인딩 항목을 출력 열에 추가 합니다.|
|[CDynamicAccessor](#cdynamicaccessor)|인스턴스화하고 초기화는 `CDynamicAccessor` 개체입니다.|
|[닫기](#close)|모든 열을 바인딩 해제, 할당된 된 메모리를 해제 하 고 해제 합니다 [IAccessor](/previous-versions/windows/desktop/ms719672(v=vs.85)) 클래스에 대 한 인터페이스 포인터입니다.|
|[GetBlobHandling](#getblobhandling)|BLOB 처리 현재 행에 대 한 값을 검색 합니다.|
|[GetBlobSizeLimit](#getblobsizelimit)|최대 BLOB 크기 (바이트) 검색합니다.|
|[GetBookmark](#getbookmark)|현재 행에 대 한 책갈피를 검색 합니다.|
|[GetColumnCount](#getcolumncount)|행 집합의 열 개수를 검색합니다.|
|[GetColumnFlags](#getcolumnflags)|열 특징을 검색합니다.|
|[GetColumnInfo](#getcolumninfo)|열 메타 데이터를 검색합니다.|
|[GetColumnName](#getcolumnname)|지정 된 열 이름을 검색합니다.|
|[GetColumnType](#getcolumntype)|지정 된 열의 데이터 형식을 검색합니다.|
|[GetLength](#getlength)|최대 허용 길이 (바이트)에서 열을 검색합니다.|
|[GetOrdinal](#getordinal)|열 이름이 지정 된 열 인덱스를 검색 합니다.|
|[GetStatus](#getstatus)|지정 된 열 상태를 검색합니다.|
|[GetValue](#getvalue)|버퍼에서 데이터를 검색합니다.|
|[SetBlobHandling](#setblobhandling)|BLOB 처리 현재 행에 대 한 값을 설정 합니다.|
|[SetBlobSizeLimit](#setblobsizelimit)|최대 BLOB 크기를 바이트 단위로 설정 합니다.|
|[SetLength](#setlength)|열의 길이 바이트 단위로 설정 합니다.|
|[SetStatus](#setstatus)|지정 된 열 상태를 설정합니다.|
|[SetValue](#setvalue)|버퍼에 데이터를 저장합니다.|

## <a name="remarks"></a>설명

사용 하 여 `CDynamicAccessor` 열 이름, 열 수, 데이터 형식 등과 같은 열 정보를 가져오는 방법입니다. 그런 다음 런타임에 접근자를 동적으로 만들려면이 열 정보를 사용 합니다.

열 정보를 만들고이 클래스에서 관리 하는 버퍼에 저장 됩니다. 사용 하 여 버퍼에서 데이터를 가져올 [GetValue](../../data/oledb/cdynamicaccessor-getvalue.md)합니다.

토론 및 동적 접근자 클래스를 사용 하 여 예제를 참조 하세요 [동적 접근자를 사용 하 여](../../data/oledb/using-dynamic-accessors.md)입니다.

## <a name="addbindentry"></a> CDynamicAccessor::AddBindEntry

출력 열에 바인딩 항목을 추가합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT AddBindEntry(const DBCOLUMNINFO& info) throw();
```

#### <a name="parameters"></a>매개 변수

*info*<br/>
[in] `DBCOLUMNINFO` 열 정보가 포함 된 구조입니다. "DBCOLUMNINFO 구조"를 참조 하세요 [icolumnsinfo:: Getcolumninfo](/previous-versions/windows/desktop/ms722704\(v=vs.85\)) 에 *OLE DB Programmer's Reference*합니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

사용 하 여 만든 기본 접근자를 재정의 하는 경우이 메서드를 사용 하 여 `CDynamicAccessor` (참조 [가져올 데이터 구성 방법?](../../data/oledb/fetching-data.md)).

## <a name="cdynamicaccessor"></a> CDynamicAccessor::CDynamicAccessor

인스턴스화하고 초기화는 `CDynamicAccessor` 개체입니다.

### <a name="syntax"></a>구문

```cpp
CDynamicAccessor(DBBLOBHANDLINGENUM eBlobHandling = DBBLOBHANDLING_DEFAULT,
   DBLENGTH nBlobSize = 8000);
```

#### <a name="parameters"></a>매개 변수

*eBlobHandling*<br/>
Binary large object (BLOB) 데이터 처리 방법을 지정 합니다. 기본값은 DBBLOBHANDLING_DEFAULT 합니다. 참조 [SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md) DBBLOBHANDLINGENUM 값에 대 한 합니다.

*nBlobSize*<br/>
최대 BLOB 크기 (바이트) 이 값에 대해 열 데이터를 BLOB로 처리 됩니다. 기본값은 8000입니다. 참조 [SetBlobSizeLimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md) 세부 정보에 대 한 합니다.

### <a name="remarks"></a>설명

초기화 하는 생성자를 사용 하는 경우는 `CDynamicAccessor` 개체 Blob 바인딩합니다 방법을 지정할 수 있습니다. Blob은 그래픽, 사운드 또는 컴파일된 코드와 같은 이진 데이터를 포함할 수 있습니다. 기본 동작은 Blob으로 8,000 바이트 보다 큰 열을 처리 하도록 바인딩하려고 시도 하는 `ISequentialStream` 개체입니다. 그러나 BLOB 크기를 다른 값을 지정할 수 있습니다.

지정할 수도 있습니다 어떻게 `CDynamicAccessor` BLOB 데이터를 정규화 하는 열 데이터를 처리: 기본 방식으로 BLOB 데이터를 처리할 수; 건너뛸 수 있습니다 (바인딩할 수 없으면) 또는 BLOB 데이터를 공급자에서 할당 된 메모리에 BLOB 데이터를 바인딩할 수 있습니다.

## <a name="close"></a> CDynamicAccessor::Close

모든 열을 바인딩 해제, 할당된 된 메모리를 해제 하 고 해제 합니다 [IAccessor](/previous-versions/windows/desktop/ms719672(v=vs.85)) 클래스에 대 한 인터페이스 포인터입니다.

### <a name="syntax"></a>구문

```cpp
void Close() throw();
```

## <a name="getblobhandling"></a> CDynamicAccessor::GetBlobHandling

BLOB 처리 현재 행에 대 한 값을 검색 합니다.

### <a name="syntax"></a>구문

```cpp
const DBBLOBHANDLINGENUM GetBlobHandling() const;
```

### <a name="remarks"></a>설명

반환 값을 처리 하는 BLOB *eBlobHandling* 으로 설정 된 [SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md)합니다.

## <a name="getblobsizelimit"></a> CDynamicAccessor::GetBlobSizeLimit

최대 BLOB 크기 (바이트) 검색합니다.

### <a name="syntax"></a>구문

```cpp
const DBLENGTH GetBlobSizeLimit() const;
```

### <a name="remarks"></a>설명

반환 값을 처리 하는 BLOB *nBlobSize* 으로 설정 된 [SetBlobSizeLimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md)합니다.

## <a name="getbookmark"></a> CDynamicAccessor::GetBookmark

현재 행에 대 한 책갈피를 검색 합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT GetBookmark(CBookmark< >* pBookmark) const throw();
```

#### <a name="parameters"></a>매개 변수

*pBookmark*<br/>
[out] 에 대 한 포인터를 [CBookmark](../../data/oledb/cbookmark-class.md) 개체입니다.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

설정 해야 `DBPROP_IRowsetLocate` 을 VARIANT_TRUE로 책갈피를 검색 합니다.

## <a name="getcolumncount"></a> CDynamicAccessor::GetColumnCount

열 개수를 검색합니다.

### <a name="syntax"></a>구문

```cpp
DBORDINAL GetColumnCount() const throw();
```

### <a name="return-value"></a>반환 값

열 개수를 검색 합니다.

## <a name="getcolumnflags"></a> CDynamicAccessor::GetColumnFlags

열 특징을 검색합니다.

### <a name="syntax"></a>구문

```cpp
bool GetColumnFlags(DBORDINAL nColumn,
   DBCOLUMNFLAGS* pFlags) const throw();
```

#### <a name="parameters"></a>매개 변수

*nColumn*<br/>
[in] 열 번호입니다. 열 번호는 1부터 시작 합니다. 값이 0 있으면 책갈피 열을 참조 합니다.

*pFlags*<br/>
[out] 열 특징을 설명 하는 비트 마스크에 대 한 포인터입니다. "DBCOLUMNFLAGS 열거 형식"을 참조 하세요 [icolumnsinfo:: Getcolumninfo](/previous-versions/windows/desktop/ms722704\(v=vs.85\)) 에 *OLE DB Programmer's Reference*합니다.

### <a name="return-value"></a>반환 값

반환 **true** 열 특성을 성공적으로 검색 됩니다. 그렇지 않으면 **false**를 반환합니다.

### <a name="remarks"></a>설명

열 번호를 하나에서 오프셋 됩니다. 0 번 열은 특별 한 경우. 사용 가능한 경우 책갈피입니다.

## <a name="getcolumninfo"></a> CDynamicAccessor::GetColumnInfo

대부분의 소비자에 필요한 열 메타 데이터를 반환 합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT GetColumnInfo(IRowset* pRowset,
   DBORDINAL* pColumns,
   DBCOLUMNINFO** ppColumnInfo,
   OLECHAR** ppStringsBuffer) throw();
```

#### <a name="parameters"></a>매개 변수

*pRowset*<br/>
[in] 에 대 한 포인터를 [IRowset](/previous-versions/windows/desktop/ms720986(v=vs.85)) 인터페이스입니다.

*pColumns*<br/>
[out] 행 집합의 열 개수를 반환할 메모리에 대 한 포인터 있는 경우이 숫자는 책갈피 열을 포함 합니다.

*ppColumnInfo*<br/>
[out] 배열을 반환할 메모리에 대 한 포인터 `DBCOLUMNINFO` 구조입니다. "DBCOLUMNINFO 구조"를 참조 하세요 [icolumnsinfo:: Getcolumninfo](/previous-versions/windows/desktop/ms722704\(v=vs.85\)) 에 *OLE DB Programmer's Reference*합니다.

*ppStringsBuffer*<br/>
[out] 모든 문자열 값에 대 한 저장소에 대 한 포인터를 반환할 메모리에 대 한 포인터 (이름 내에서 사용할 *columnid* 용인지 *pwszName*) 단일 할당 블록 내에서.

### <a name="return-value"></a>반환 값

HRESULT 값 중 하나입니다.

### <a name="remarks"></a>설명

참조 [icolumnsinfo:: Getcolumninfo](/previous-versions/windows/desktop/ms722704\(v=vs.85\)) 에 *OLE DB Programmer's Reference* 데이터 형식에 대 한 내용은 `DBORDINAL`를 `DBCOLUMNINFO`, 및 `OLECHAR`합니다.

## <a name="getcolumnname"></a> CDynamicAccessor::GetColumnName

지정 된 열 이름을 검색합니다.

### <a name="syntax"></a>구문

```cpp
LPOLESTR GetColumnName(DBORDINAL nColumn) const throw();
```

#### <a name="parameters"></a>매개 변수

*nColumn*<br/>
[in] 열 번호입니다. 열 번호는 1부터 시작 합니다. 값이 0 있으면 책갈피 열을 참조 합니다.

### <a name="return-value"></a>반환 값

지정된 열의 이름입니다.

## <a name="getcolumntype"></a> CDynamicAccessor::GetColumnType

지정 된 열의 데이터 형식을 검색합니다.

### <a name="syntax"></a>구문

```cpp
bool GetColumnType(DBORDINAL nColumn,
   DBTYPE* pType) const throw();
```

#### <a name="parameters"></a>매개 변수

*nColumn*<br/>
[in] 열 번호입니다. 열 번호는 1부터 시작 합니다. 값이 0 있으면 책갈피 열을 참조 합니다.

*pType*<br/>
[out] 지정 된 열의 데이터 형식에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

반환 **true** 성공 하거나 **false** 실패 합니다.

## <a name="getlength"></a> CDynamicAccessor::GetLength

지정 된 열의 길이 검색 합니다.

### <a name="syntax"></a>구문

```cpp
bool GetLength(DBORDINAL nColumn,
   DBLENGTH* pLength) const throw();

bool GetLength(const CHAR* pColumnName,
   DBLENGTH* pLength) const throw();

bool GetLength(const WCHAR* pColumnName,
   DBLENGTH* pLength) const throw();
```

#### <a name="parameters"></a>매개 변수

*nColumn*<br/>
[in] 열 번호입니다. 열 번호는 1부터 시작 합니다. 값이 0 있으면 책갈피 열을 참조 합니다.

*pColumnName*<br/>
[in] 열 이름을 포함 하는 문자열에 대 한 포인터입니다.

*pLength*<br/>
[out] 바이트의 열 길이 포함 하는 정수에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

반환 **true** 지정된 된 열이 없으면입니다. 반환이 고, 그렇지 **false**합니다.

### <a name="remarks"></a>설명

첫 번째 재정의 열 번호를 사용 하 고 두 번째 및 세 번째 재정의 수행 열 이름을 ANSI 또는 유니코드 형식으로 각각.

## <a name="getordinal"></a> CDynamicAccessor::GetOrdinal

열 이름이 지정 된 열 번호를 검색 합니다.

### <a name="syntax"></a>구문

```cpp
bool GetOrdinal(const CHAR* pColumnName,
   DBORDINAL* pOrdinal) const throw();

bool GetOrdinal(const WCHAR* pColumnName,
   DBORDINAL* pOrdinal) const throw();
```

#### <a name="parameters"></a>매개 변수

*pColumnName*<br/>
[in] 열 이름을 포함 하는 문자열에 대 한 포인터입니다.

*pOrdinal*<br/>
[out] 열 번호에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

반환 **true** 지정 된 이름의 열이 없으면입니다. 반환이 고, 그렇지 **false**합니다.

## <a name="getstatus"></a> CDynamicAccessor::GetStatus

지정 된 열 상태를 검색합니다.

### <a name="syntax"></a>구문

```cpp
bool GetStatus(DBORDINAL nColumn,
   DBSTATUS* pStatus) const throw();

bool GetStatus(const CHAR* pColumnName,
   DBSTATUS* pStatus) const throw();

bool GetStatus(const WCHAR* pColumnName,
   DBSTATUS* pStatus) const throw();
```

#### <a name="parameters"></a>매개 변수

*nColumn*<br/>
[in] 열 번호입니다. 열 번호는 1부터 시작 합니다. 값이 0 있으면 책갈피 열을 참조 합니다.

*pColumnName*<br/>
[in] 열 이름을 포함 하는 문자열에 대 한 포인터입니다.

*pStatus*<br/>
[out] 열 상태가 들어 있는 변수에 대 한 포인터입니다. 참조 [DBSTATUS](/previous-versions/windows/desktop/ms722617(v=vs.85)) 에 *OLE DB Programmer's Reference* 자세한 내용은 합니다.

### <a name="return-value"></a>반환 값

반환 **true** 지정된 된 열이 없으면입니다. 반환이 고, 그렇지 **false**합니다.

## <a name="getvalue"></a> CDynamicAccessor::GetValue

지정된 된 열에 대 한 데이터를 검색합니다.

### <a name="syntax"></a>구문

```cpp
void* GetValue(DBORDINAL nColumn) const throw();

void* GetValue(const CHAR* pColumnName) const throw();

void* GetValue(const WCHAR* pColumnName) const throw();

template < class ctype >
bool GetValue(DBORDINAL nColumn, ctype* pData) const throw();

template < class ctype >
bool GetValue(const CHAR* pColumnName, ctype* pData) const throw();

template < class ctype >
bool GetValue(const WCHAR* pColumnName, ctype* pData) const throw();
```

#### <a name="parameters"></a>매개 변수

*ctype*<br/>
[in] 문자열 형식 제외한 모든 데이터 형식을 처리 하는 템플릿 매개 변수 (`CHAR*`, `WCHAR*`), 특별 한 처리가 필요 합니다. `GetValue` 지정한 것 여기에 따라 적절 한 데이터 형식을 사용 합니다.

*nColumn*<br/>
[in] 열 번호입니다. 열 번호는 1부터 시작 합니다. 값이 0 있으면 책갈피 열을 참조 합니다.

*pColumnName*<br/>
[in] 열 이름입니다.

*pData*<br/>
[out] 지정 된 열의 내용에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

문자열 데이터를 전달 하려는 경우 템플릿이 아닌 버전을 사용 하 여 `GetValue`입니다. 이 메서드의 템플릿이 아닌 버전은 반환 `void*`, 지정 된 열 데이터를 포함 하는 버퍼의 부분을 가리킵니다. 열이 없는 경우 NULL을 반환 합니다.

다른 모든 데이터 형식에 대 한 템플릿 버전을 사용 하기 더욱 간편해졌으며은 `GetValue`합니다. 템플릿 버전을 반환 **true** 성공 하거나 **false** 실패 합니다.

### <a name="remarks"></a>설명

문자열 및 다른 데이터 형식이 포함 된 열에 대 한 템플릿 버전을 포함 하는 열을 반환 하는 템플릿이 아닌 버전을 사용 합니다.

디버그 모드에서 하면 얻을 수 있습니다 어설션을 크기인 *pData* 가리키는 열의 크기와 같지 않습니다.

## <a name="setblobhandling"></a> CDynamicAccessor::SetBlobHandling

BLOB 처리 현재 행에 대 한 값을 설정 합니다.

### <a name="syntax"></a>구문

```cpp
bool SetBlobHandling(DBBLOBHANDLINGENUM eBlobHandling);
```

#### <a name="parameters"></a>매개 변수

*eBlobHandling*<br/>
BLOB 데이터를 처리할 방법을 지정 합니다. 다음 값을 걸릴 수 있습니다.

- DBBLOBHANDLING_DEFAULT: 보다 큰 열 데이터를 처리 *nBlobSize* (에서 설정 된 `SetBlobSizeLimit`) 데이터를 BLOB과 통해 검색을 `ISequentialStream` 또는 `IStream` 개체입니다. 이 옵션 보다 큰 데이터를 포함 하는 모든 열을 바인딩할 시도가 *nBlobSize* 또는 BLOB 데이터로 DBTYPE_IUNKNOWN으로 나열 합니다.

- DBBLOBHANDLING_NOSTREAMS: 보다 큰 열 데이터 처리 *nBlobSize* (에서 설정 된 `SetBlobSizeLimit`) 데이터를 BLOB과 공급자 할당, 소비자가 소유한 메모리에 대 한 참조를 통해 쿼리를 검색 합니다. 이 옵션은 둘 이상의 BLOB 열이 있는 테이블에 대 한 유용한 및 공급자가 지 원하는 하나만 `ISequentialStream` 접근자 마다 개체입니다.

- DBBLOBHANDLING_SKIP: Skip (연결 하지 않음) Blob을 포함 한 것으로 한정 되는 열 (접근자 바인딩하거나 열 값을 검색 하지는 않지만 열 상태 및 길이 계속 검색 합니다).

### <a name="remarks"></a>설명

`SetBlobHandling`를 호출하기 전에 `Open`를 호출해야 합니다.

Constructor 메서드 [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) DBBLOBHANDLING_DEFAULT 값을 처리 하는 BLOB을 설정 합니다.

## <a name="setblobsizelimit"></a> CDynamicAccessor::SetBlobSizeLimit

최대 BLOB 크기를 바이트 단위로 설정 합니다.

### <a name="syntax"></a>구문

```cpp
void SetBlobSizeLimit(DBLENGTH nBlobSize);
```

#### <a name="parameters"></a>매개 변수

*nBlobSize*<br/>
BLOB 크기 제한을 지정합니다.

### <a name="remarks"></a>설명

최대 BLOB 크기 (바이트) 설정 이 값 보다 큰 열 데이터를 BLOB로 처리 됩니다. 일부 공급자 (예: 2GB) 열에 대 한 매우 큰 크기를 제공합니다. 이 크기는 열에 대 한 메모리를 할당 하는 동안에 대신 Blob으로 이러한 열을 바인딩할 하려고 일반적으로 합니다. 이런에서 모든 메모리를 할당할 수 없지만 여전히 잘림 걱정 없이 모든 데이터를 읽을 수 있습니다. 그러나는 강제로 하려는 경우도 있습니다. `CDynamicAccessor` 네이티브 데이터 형식으로의 큰 열을 바인딩합니다. 이렇게 하려면 호출 `SetBlobSizeLimit` 호출 하기 전에 `Open`입니다.

Constructor 메서드 [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) 8,000 바이트의 기본 값으로 최대 BLOB 크기를 설정 합니다.

## <a name="setlength"></a> CDynamicAccessor::SetLength

지정 된 열의 길이 설정 합니다.

### <a name="syntax"></a>구문

```cpp
bool SetLength(DBORDINAL nColumn,
   DBLENGTH nLength)throw();

bool SetLength(const CHAR* pColumnName,
   DBLENGTH nLength) throw();

bool SetLength(const WCHAR* pColumnName,
   DBLENGTH nLength) throw();
```

#### <a name="parameters"></a>매개 변수

*nColumn*<br/>
[in] 열 번호입니다. 열 번호는 1부터 시작 합니다. 값이 0 있으면 책갈피 열을 참조 합니다.

*nLength*<br/>
[in] 길이 (바이트)에서 열입니다.

*pColumnName*<br/>
[in] 열 이름을 포함 하는 문자열에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

반환 **true** 지정 된 열 길이 성공적으로 설정 된 경우. 반환이 고, 그렇지 **false**합니다.

## <a name="setstatus"></a> CDynamicAccessor::SetStatus

지정 된 열 상태를 설정합니다.

### <a name="syntax"></a>구문

```cpp
bool SetStatus(DBORDINAL nColumn,
   DBSTATUS status)throw();

bool SetStatus(const CHAR* pColumnName,
   DBSTATUS status) throw();

bool SetStatus(const WCHAR* pColumnName,
   DBSTATUS status) throw();
```

#### <a name="parameters"></a>매개 변수

*nColumn*<br/>
[in] 열 번호입니다. 열 번호는 1부터 시작 합니다. 값이 0 있으면 책갈피 열을 참조 합니다.

*status*<br/>
[in] 열 상태입니다. 참조 [DBSTATUS](/previous-versions/windows/desktop/ms722617(v=vs.85)) 에 *OLE DB Programmer's Reference* 자세한 내용은 합니다.

*pColumnName*<br/>
[in] 열 이름을 포함 하는 문자열에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

반환 **true** 지정 된 열 상태는 성공적으로 설정 된 경우. 반환이 고, 그렇지 **false**합니다.

## <a name="setvalue"></a> CDynamicAccessor::SetValue

지정 된 열에 데이터를 저장합니다.

### <a name="syntax"></a>구문

```cpp
template <class ctype>
bool SetValue(
   DBORDINAL nColumn,
   constctype& data) throw( );

template <class ctype> 
bool SetValue(
   const CHAR * pColumnName,
   const ctype& data) throw( );

template <class ctype>
bool SetValue(
   const WCHAR *pColumnName,
   const ctype& data) throw( );
```

#### <a name="parameters"></a>매개 변수

*ctype*<br/>
[in] 문자열 형식 제외한 모든 데이터 형식을 처리 하는 템플릿 매개 변수 (`CHAR*`, `WCHAR*`), 특별 한 처리가 필요 합니다. `GetValue` 지정한 것 여기에 따라 적절 한 데이터 형식을 사용 합니다.

*pColumnName*<br/>
[in] 열 이름을 포함 하는 문자열에 대 한 포인터입니다.

*data*<br/>
[in] 데이터를 포함 하는 메모리에 대 한 포인터입니다.

*nColumn*<br/>
[in] 열 번호입니다. 열 번호는 1부터 시작 합니다. 값이 0 있으면 책갈피 열을 참조 합니다.

### <a name="return-value"></a>반환 값

문자열 데이터를 설정 하려는 경우 템플릿이 아닌 버전을 사용 하 여 `GetValue`입니다. 이 메서드의 템플릿이 아닌 버전은 반환 `void*`, 지정 된 열 데이터를 포함 하는 버퍼의 부분을 가리킵니다. 열이 없는 경우 NULL을 반환 합니다.

다른 모든 데이터 형식에 대 한 템플릿 버전을 사용 하기 더욱 간편해졌으며은 `GetValue`합니다. 템플릿 버전을 반환 **true** 성공 하거나 **false** 실패 합니다.

## <a name="see-also"></a>참고자료

[OLE DB 소비자 템플릿(C++)](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessor 클래스](../../data/oledb/caccessor-class.md)<br/>
[CDynamicParameterAccessor 클래스](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
[CManualAccessor 클래스](../../data/oledb/cmanualaccessor-class.md)