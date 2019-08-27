---
title: CRowsetImpl 클래스
ms.date: 11/04/2016
f1_keywords:
- CRowsetImpl
- ATL.CRowsetImpl
- ATL::CRowsetImpl
- CRowsetImpl.NameFromDBID
- CRowsetImpl::NameFromDBID
- CRowsetImpl.SetCommandText
- CRowsetImpl::SetCommandText
- GetColumnInfo
- CRowsetImpl.GetColumnInfo
- CRowsetImpl::GetColumnInfo
- CRowsetImpl::GetCommandFromID
- GetCommandFromID
- CRowsetImpl.GetCommandFromID
- CRowsetImpl.ValidateCommandID
- CRowsetImpl::ValidateCommandID
- CRowsetImpl.m_rgRowData
- CRowsetImpl::m_rgRowData
- CRowsetImpl::m_strCommandText
- CRowsetImpl.m_strCommandText
- CRowsetImpl::m_strIndexText
- CRowsetImpl.m_strIndexText
helpviewer_keywords:
- CRowsetImpl class
- NameFromDBID method
- SetCommandText method
- GetColumnInfo method
- GetCommandFromID method
- ValidateCommandID method
- m_rgRowData
- m_strCommandText
- m_strIndexText
ms.assetid: e97614b3-b11d-4806-a0d3-b9401331473f
ms.openlocfilehash: 1fac3a74ca259fe3b680355fadc7f9bbd6e3cc13
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62368710"
---
# <a name="crowsetimpl-class"></a>CRowsetImpl 클래스

많은 구현 인터페이스의 여러 상속을 요구 하지 않고 표준 OLE DB 행 집합 구현을 제공 합니다.

## <a name="syntax"></a>구문

```cpp
template <
   class T,
   class Storage,
   class CreatorClass,
   class ArrayType = CAtlArray<Storage>,
   class RowClass = CSimpleRow,
   class RowsetInterface = IRowsetImpl <T, IRowset>
>
class CRowsetImpl : 
   public CComObjectRootEx<CreatorClass::_ThreadModel>,
   public CRowsetBaseImpl<T, Storage, ArrayType, RowsetInterface>,
   public IRowsetInfoImpl<T, CreatorClass::_PropClass>
```

### <a name="parameters"></a>매개 변수

*T*<br/>
사용자의 클래스에서 파생 되는 `CRowsetImpl`합니다.

*스토리지*<br/>
사용자 레코드 클래스입니다.

*CreatorClass*<br/>
행 집합; 속성을 포함 하는 클래스 일반적으로 명령입니다.

*ArrayType*<br/>
이 클래스는 행 집합의 데이터에 대 한 저장소 역할을 할입니다. 이 매개 변수의 기본값은 `CAtlArray`, 이지만 필요한 기능을 지 원하는 클래스일 수 있습니다.

## <a name="requirements"></a>요구 사항

**헤더:** atldb.h

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[NameFromDBID](#namefromdbid)|문자열을 추출를 `DBID` 에 복사 합니다 *bstr* 전달 합니다.|
|[SetCommandText](#setcommandtext)|유효성을 검사 하 고 저장 합니다 `DBID`두 문자열의 ([m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) 하 고 [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)).|

### <a name="overridable-methods"></a>재정의 가능한 메서드

|||
|-|-|
|[GetColumnInfo](#getcolumninfo)|특정 클라이언트 요청에 대 한 열 정보를 검색합니다.|
|[GetCommandFromID](#getcommandfromid)|데이터 멤버에 문자열 값을 복사 하는 확인 중 하나 또는 두 매개 변수는 문자열 값을 포함 하 고 그렇다면 [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) 하 고 [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)합니다.|
|[ValidateCommandID](#validatecommandid)|참조 하는 경우 중 하나 또는 둘 다 검사 `DBID`s 문자열 값을 포함 하 고 그렇다면 해당 데이터 멤버에 복사 [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) 하 고 [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)합니다.|

### <a name="data-members"></a>데이터 멤버

|||
|-|-|
|[m_rgRowData](#rgrowdata)|기본적으로 `CAtlArray` 사용자 레코드 템플릿 인수에는 templatizes `CRowsetImpl`합니다. 다른 배열 형식 클래스를 변경 하 여 사용할 수는 `ArrayType` 템플릿 인수 `CRowsetImpl`합니다.|
|[m_strCommandText](#strcommandtext)|행 집합의 초기 명령을 포함합니다.|
|[m_strIndexText](#strindextext)|행 집합의 초기 인덱스를 포함합니다.|

## <a name="remarks"></a>설명

`CRowsetImpl` 정적으로 업캐스팅 형식의 재정의 제공합니다. 메서드는 지정된 된 행 집합의 유효성을 검사 명령 텍스트 방식으로 제어 합니다. 직접 만들 수 있습니다 `CRowsetImpl`-스타일 클래스를 만들어 구현 인터페이스 다중 상속 합니다. 구현은 제공 해야 하는 유일한 방법은 `Execute`합니다. Creator 메서드는에 대 한 다른 서명을 만드는 행 집합의 형식에 따라 예상 `Execute`합니다. 예를 들어, 사용 중인 경우는 `CRowsetImpl`-스키마 행 집합을 구현 하는 클래스를 파생 합니다 `Execute` 메서드는 다음 서명을 해야 합니다.:

`HRESULT Execute(LONG* pcRows, ULONG cRestrictions, const VARIANT* rgRestrictions)`

만들려는 경우는 `CRowsetImpl`-명령 또는 세션의 행 집합을 구현 하는 클래스를 파생 합니다 `Execute` 메서드는 다음 서명을 해야 합니다.:

`HRESULT Execute(LONG* pcRows, DBPARAMS* pParams)`

중 하나를 구현 하는 `CRowsetImpl`-파생 `Execute` 메서드를 내부 데이터 버퍼를 입력 해야 합니다 ([m_rgRowData](../../data/oledb/crowsetimpl-m-rgrowdata.md)).

## <a name="namefromdbid"></a> CRowsetImpl::NameFromDBID

문자열을 추출를 `DBID` 에 복사 합니다 *bstr* 전달 합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT CRowsetBaseImpl::NameFromDBID(DBID* pDBID,
   CComBSTR& bstr,
   bool bIndex);
```

#### <a name="parameters"></a>매개 변수

*pDBID*<br/>
[in] 에 대 한 포인터를 `DBID` 을 추출할 문자열입니다.

*bstr*<br/>
[in] A [CComBSTR](../../atl/reference/ccombstr-class.md) 의 복사본에 대 한 참조를 `DBID` 문자열입니다.

*bIndex*<br/>
[in] **true** 인덱스인 경우 `DBID`; **false** 테이블이 있는 경우 `DBID`합니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다. 여부에 따라를 `DBID` 테이블이 나 인덱스 (가리키는 *bIndex*), DB_E_NOINDEX 또는 DB_E_NOTABLE 메서드를 반환 하거나 됩니다.

### <a name="remarks"></a>설명

이 메서드는 합니다 `CRowsetImpl` 구현의 [ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md) 하 고 [GetCommandFromID](../../data/oledb/crowsetimpl-getcommandfromid.md)합니다.

## <a name="setcommandtext"></a> CRowsetImpl::SetCommandText

유효성을 검사 하 고 저장 합니다 `DBID`두 문자열의 ([m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) 하 고 [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)).

### <a name="syntax"></a>구문

```cpp
HRESULT CRowsetBaseImpl::SetCommandText(DBID* pTableID,
   DBID* pIndexID);
```

#### <a name="parameters"></a>매개 변수

*pTableID*<br/>
[in] 에 대 한 포인터를 `DBID` 나타내는 테이블 id입니다.

*pIndexID*<br/>
[in] 에 대 한 포인터를 `DBID` 나타내는 인덱스 id입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

### <a name="remarks"></a>설명

합니다 `SetCommentText` 메서드를 호출 `CreateRowset`, 정적 메서드를 처리할 `IOpenRowsetImpl`합니다.

이 메서드를 호출 하 여 해당 작업을 위임 [ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md) 하 고 [GetCommandFromID](../../data/oledb/crowsetimpl-getcommandfromid.md) 캐스팅 되지 않은 포인터를 통해.

## <a name="getcolumninfo"></a> CRowsetImpl::GetColumnInfo

특정 클라이언트 요청에 대 한 열 정보를 검색합니다.

### <a name="syntax"></a>구문

```cpp
static ATLCOLUMNINFO* CRowsetBaseImpl::GetColumnInfo(T* pv,
   ULONG* pcCols);
```

#### <a name="parameters"></a>매개 변수

*pv*<br/>
[in] 사용자에 대 한 포인터 `CRowsetImpl` 클래스를 파생 합니다.

*pcCols*<br/>
[in] 반환 된 열의 수 (출력) 포인터입니다.

### <a name="return-value"></a>반환 값

에 대 한 포인터를 정적 `ATLCOLUMNINFO` 구조입니다.

### <a name="remarks"></a>설명

이 메서드는 고급 재정의 합니다.

이 메서드는 특정 클라이언트 요청에 대 한 열 정보를 검색할 수 있는 여러 기본 구현 클래스에서 호출 됩니다. 이 메서드를 호출 하는는 일반적으로 `IColumnsInfoImpl`입니다. 이 메서드를 재정의 하는 경우에 메서드의 버전을 배치 해야 합니다 프로그램 `CRowsetImpl`-클래스를 파생 합니다. 템플릿 화 되지 않은 클래스에서 메서드를 배치할 수 있습니다, 되므로 변경 해야 합니다 *pv* 적절 한 `CRowsetImpl`-클래스를 파생 합니다.

다음 예제에서는 `GetColumnInfo` 사용 합니다. 이 예에서 `CMyRowset` 는 `CRowsetImpl`-클래스를 파생 합니다. 재정의 하기 위해 `GetColumnInfo` 이 클래스의 모든 인스턴스에 대 한 배치에 다음 메서드는 `CMyRowset` 클래스 정의:

[!code-cpp[NVC_OLEDB_Provider#1](../../data/oledb/codesnippet/cpp/crowsetimpl-getcolumninfo_1.h)]

## <a name="getcommandfromid"></a> CRowsetImpl::GetCommandFromID

데이터 멤버에 문자열 값을 복사 하는 확인 중 하나 또는 두 매개 변수는 문자열 값을 포함 하 고 그렇다면 [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) 하 고 [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT CRowsetBaseImpl::GetCommandFromID(DBID* pTableID,
   DBID* pIndexID);
```

#### <a name="parameters"></a>매개 변수

*pTableID*<br/>
[in] 에 대 한 포인터를 `DBID` 나타내는 테이블 id입니다.

*pIndexID*<br/>
[in] 에 대 한 포인터를 `DBID` id입니다. 인덱스를 나타내는

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

### <a name="remarks"></a>설명

이 메서드를 호출 하 여 정적 업캐스팅을 통해 `CRowsetImpl` 데이터 멤버를 채우는 [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) 하 고 [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)합니다. 기본적으로이 메서드 중 하나 또는 두 매개 변수 문자열 값을 포함 하는 경우를 확인 합니다. 문자열 값을 포함 하는 경우이 메서드는 데이터 멤버에 문자열 값을 복사 합니다. 이 서명 사용 하 여 메서드를 배치 하 여 프로그램 `CRowsetImpl`-파생 클래스 메서드의 기본 구현 대신 호출 됩니다.

## <a name="validatecommandid"></a> CRowsetImpl::ValidateCommandID

참조 하는 경우 중 하나 또는 둘 다 검사 `DBID`s 문자열 값을 포함 하 고 그렇다면 해당 데이터 멤버에 복사 [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) 하 고 [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT CRowsetBaseImpl::ValidateCommandID(DBID* pTableID,
   DBID* pIndexID);
```

#### <a name="parameters"></a>매개 변수

*pTableID*<br/>
[in] 에 대 한 포인터를 `DBID` 나타내는 테이블 id입니다.

*pIndexID*<br/>
[in] 에 대 한 포인터를 `DBID` 나타내는 인덱스 id입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

### <a name="remarks"></a>설명

이 메서드를 호출 하 여 정적 업캐스팅을 통해 `CRowsetImpl` 해당 데이터 멤버를 채우는 [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) 하 고 [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)합니다. 기본적으로이 메서드를 참조 하는 경우 중 하나 또는 둘 다 확인 `DBID`의문자열 값을 포함 하 고 그렇다면 해당 데이터 멤버에 복사 합니다. 이 서명 사용 하 여 메서드를 배치 하 여 프로그램 `CRowsetImpl`-파생 클래스 메서드의 기본 구현 대신 호출 됩니다.

## <a name="rgrowdata"></a> CRowsetImpl::m_rgRowData

기본적으로 `CAtlArray` 사용자 레코드 템플릿 인수에는 templatizes `CRowsetImpl`합니다.

### <a name="syntax"></a>구문

```cpp
ArrayType CRowsetBaseImpl::m_rgRowData;
```

### <a name="remarks"></a>설명

*ArrayType* 는 템플릿 매개 변수입니다 `CRowsetImpl`합니다.

## <a name="strcommandtext"></a> CRowsetImpl::m_strCommandText

행 집합의 초기 명령을 포함합니다.

### <a name="syntax"></a>구문

```cpp
CComBSTR CRowsetBaseImpl::m_strCommandText;
```

## <a name="strindextext"></a> CRowsetImpl::m_strIndexText

행 집합의 초기 인덱스를 포함합니다.

### <a name="syntax"></a>구문

```cpp
CComBSTR CRowsetBaseImpl::m_strIndexText;
```