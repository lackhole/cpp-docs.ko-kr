---
title: CDaoRecordset 클래스
ms.date: 08/27/2018
f1_keywords:
- CDaoRecordset
- AFXDAO/CDaoRecordset
- AFXDAO/CDaoRecordset::CDaoRecordset
- AFXDAO/CDaoRecordset::AddNew
- AFXDAO/CDaoRecordset::CanAppend
- AFXDAO/CDaoRecordset::CanBookmark
- AFXDAO/CDaoRecordset::CancelUpdate
- AFXDAO/CDaoRecordset::CanRestart
- AFXDAO/CDaoRecordset::CanScroll
- AFXDAO/CDaoRecordset::CanTransact
- AFXDAO/CDaoRecordset::CanUpdate
- AFXDAO/CDaoRecordset::Close
- AFXDAO/CDaoRecordset::Delete
- AFXDAO/CDaoRecordset::DoFieldExchange
- AFXDAO/CDaoRecordset::Edit
- AFXDAO/CDaoRecordset::FillCache
- AFXDAO/CDaoRecordset::Find
- AFXDAO/CDaoRecordset::FindFirst
- AFXDAO/CDaoRecordset::FindLast
- AFXDAO/CDaoRecordset::FindNext
- AFXDAO/CDaoRecordset::FindPrev
- AFXDAO/CDaoRecordset::GetAbsolutePosition
- AFXDAO/CDaoRecordset::GetBookmark
- AFXDAO/CDaoRecordset::GetCacheSize
- AFXDAO/CDaoRecordset::GetCacheStart
- AFXDAO/CDaoRecordset::GetCurrentIndex
- AFXDAO/CDaoRecordset::GetDateCreated
- AFXDAO/CDaoRecordset::GetDateLastUpdated
- AFXDAO/CDaoRecordset::GetDefaultDBName
- AFXDAO/CDaoRecordset::GetDefaultSQL
- AFXDAO/CDaoRecordset::GetEditMode
- AFXDAO/CDaoRecordset::GetFieldCount
- AFXDAO/CDaoRecordset::GetFieldInfo
- AFXDAO/CDaoRecordset::GetFieldValue
- AFXDAO/CDaoRecordset::GetIndexCount
- AFXDAO/CDaoRecordset::GetIndexInfo
- AFXDAO/CDaoRecordset::GetLastModifiedBookmark
- AFXDAO/CDaoRecordset::GetLockingMode
- AFXDAO/CDaoRecordset::GetName
- AFXDAO/CDaoRecordset::GetParamValue
- AFXDAO/CDaoRecordset::GetPercentPosition
- AFXDAO/CDaoRecordset::GetRecordCount
- AFXDAO/CDaoRecordset::GetSQL
- AFXDAO/CDaoRecordset::GetType
- AFXDAO/CDaoRecordset::GetValidationRule
- AFXDAO/CDaoRecordset::GetValidationText
- AFXDAO/CDaoRecordset::IsBOF
- AFXDAO/CDaoRecordset::IsDeleted
- AFXDAO/CDaoRecordset::IsEOF
- AFXDAO/CDaoRecordset::IsFieldDirty
- AFXDAO/CDaoRecordset::IsFieldNull
- AFXDAO/CDaoRecordset::IsFieldNullable
- AFXDAO/CDaoRecordset::IsOpen
- AFXDAO/CDaoRecordset::Move
- AFXDAO/CDaoRecordset::MoveFirst
- AFXDAO/CDaoRecordset::MoveLast
- AFXDAO/CDaoRecordset::MoveNext
- AFXDAO/CDaoRecordset::MovePrev
- AFXDAO/CDaoRecordset::Open
- AFXDAO/CDaoRecordset::Requery
- AFXDAO/CDaoRecordset::Seek
- AFXDAO/CDaoRecordset::SetAbsolutePosition
- AFXDAO/CDaoRecordset::SetBookmark
- AFXDAO/CDaoRecordset::SetCacheSize
- AFXDAO/CDaoRecordset::SetCacheStart
- AFXDAO/CDaoRecordset::SetCurrentIndex
- AFXDAO/CDaoRecordset::SetFieldDirty
- AFXDAO/CDaoRecordset::SetFieldNull
- AFXDAO/CDaoRecordset::SetFieldValue
- AFXDAO/CDaoRecordset::SetFieldValueNull
- AFXDAO/CDaoRecordset::SetLockingMode
- AFXDAO/CDaoRecordset::SetParamValue
- AFXDAO/CDaoRecordset::SetParamValueNull
- AFXDAO/CDaoRecordset::SetPercentPosition
- AFXDAO/CDaoRecordset::Update
- AFXDAO/CDaoRecordset::m_bCheckCacheForDirtyFields
- AFXDAO/CDaoRecordset::m_nFields
- AFXDAO/CDaoRecordset::m_nParams
- AFXDAO/CDaoRecordset::m_pDAORecordset
- AFXDAO/CDaoRecordset::m_pDatabase
- AFXDAO/CDaoRecordset::m_strFilter
- AFXDAO/CDaoRecordset::m_strSort
helpviewer_keywords:
- CDaoRecordset [MFC], CDaoRecordset
- CDaoRecordset [MFC], AddNew
- CDaoRecordset [MFC], CanAppend
- CDaoRecordset [MFC], CanBookmark
- CDaoRecordset [MFC], CancelUpdate
- CDaoRecordset [MFC], CanRestart
- CDaoRecordset [MFC], CanScroll
- CDaoRecordset [MFC], CanTransact
- CDaoRecordset [MFC], CanUpdate
- CDaoRecordset [MFC], Close
- CDaoRecordset [MFC], Delete
- CDaoRecordset [MFC], DoFieldExchange
- CDaoRecordset [MFC], Edit
- CDaoRecordset [MFC], FillCache
- CDaoRecordset [MFC], Find
- CDaoRecordset [MFC], FindFirst
- CDaoRecordset [MFC], FindLast
- CDaoRecordset [MFC], FindNext
- CDaoRecordset [MFC], FindPrev
- CDaoRecordset [MFC], GetAbsolutePosition
- CDaoRecordset [MFC], GetBookmark
- CDaoRecordset [MFC], GetCacheSize
- CDaoRecordset [MFC], GetCacheStart
- CDaoRecordset [MFC], GetCurrentIndex
- CDaoRecordset [MFC], GetDateCreated
- CDaoRecordset [MFC], GetDateLastUpdated
- CDaoRecordset [MFC], GetDefaultDBName
- CDaoRecordset [MFC], GetDefaultSQL
- CDaoRecordset [MFC], GetEditMode
- CDaoRecordset [MFC], GetFieldCount
- CDaoRecordset [MFC], GetFieldInfo
- CDaoRecordset [MFC], GetFieldValue
- CDaoRecordset [MFC], GetIndexCount
- CDaoRecordset [MFC], GetIndexInfo
- CDaoRecordset [MFC], GetLastModifiedBookmark
- CDaoRecordset [MFC], GetLockingMode
- CDaoRecordset [MFC], GetName
- CDaoRecordset [MFC], GetParamValue
- CDaoRecordset [MFC], GetPercentPosition
- CDaoRecordset [MFC], GetRecordCount
- CDaoRecordset [MFC], GetSQL
- CDaoRecordset [MFC], GetType
- CDaoRecordset [MFC], GetValidationRule
- CDaoRecordset [MFC], GetValidationText
- CDaoRecordset [MFC], IsBOF
- CDaoRecordset [MFC], IsDeleted
- CDaoRecordset [MFC], IsEOF
- CDaoRecordset [MFC], IsFieldDirty
- CDaoRecordset [MFC], IsFieldNull
- CDaoRecordset [MFC], IsFieldNullable
- CDaoRecordset [MFC], IsOpen
- CDaoRecordset [MFC], Move
- CDaoRecordset [MFC], MoveFirst
- CDaoRecordset [MFC], MoveLast
- CDaoRecordset [MFC], MoveNext
- CDaoRecordset [MFC], MovePrev
- CDaoRecordset [MFC], Open
- CDaoRecordset [MFC], Requery
- CDaoRecordset [MFC], Seek
- CDaoRecordset [MFC], SetAbsolutePosition
- CDaoRecordset [MFC], SetBookmark
- CDaoRecordset [MFC], SetCacheSize
- CDaoRecordset [MFC], SetCacheStart
- CDaoRecordset [MFC], SetCurrentIndex
- CDaoRecordset [MFC], SetFieldDirty
- CDaoRecordset [MFC], SetFieldNull
- CDaoRecordset [MFC], SetFieldValue
- CDaoRecordset [MFC], SetFieldValueNull
- CDaoRecordset [MFC], SetLockingMode
- CDaoRecordset [MFC], SetParamValue
- CDaoRecordset [MFC], SetParamValueNull
- CDaoRecordset [MFC], SetPercentPosition
- CDaoRecordset [MFC], Update
- CDaoRecordset [MFC], m_bCheckCacheForDirtyFields
- CDaoRecordset [MFC], m_nFields
- CDaoRecordset [MFC], m_nParams
- CDaoRecordset [MFC], m_pDAORecordset
- CDaoRecordset [MFC], m_pDatabase
- CDaoRecordset [MFC], m_strFilter
- CDaoRecordset [MFC], m_strSort
ms.assetid: 2322067f-1027-4662-a5d7-aa2fc7488630
ms.openlocfilehash: 96118645aa656e97fcb93a0fd223045208ab03a3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62206361"
---
# <a name="cdaorecordset-class"></a>CDaoRecordset 클래스

데이터 소스에서 선택한 레코드 집합을 나타냅니다.

## <a name="syntax"></a>구문

```
class CDaoRecordset : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CDaoRecordset::CDaoRecordset](#cdaorecordset)|`CDaoRecordset` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CDaoRecordset::AddNew](#addnew)|새 레코드를 추가 하는 것에 대 한 준비 합니다. 호출 [업데이트](#update) 추가 완료 합니다.|
|[CDaoRecordset::CanAppend](#canappend)|새 레코드를 통해 레코드 집합에 추가할 수 있으면 0이 아닌 값을 반환 합니다 [AddNew](#addnew) 멤버 함수입니다.|
|[CDaoRecordset::CanBookmark](#canbookmark)|레코드 집합에서 책갈피를 지 원하는 경우 0이 아닌 값을 반환 합니다.|
|[CDaoRecordset::CancelUpdate](#cancelupdate)|취소로 인해 모든 보류 중인 업데이트는 [편집할](#edit) 또는 [AddNew](#addnew) 작업 합니다.|
|[CDaoRecordset::CanRestart](#canrestart)|0이 아닌 경우 반환 [Requery](#requery) 레코드 집합의 쿼리를 다시 실행 하기 위해 호출할 수 있습니다.|
|[CDaoRecordset::CanScroll](#canscroll)|레코드를 스크롤할 수 있으면 0이 아닌 값을 반환 합니다.|
|[CDaoRecordset::CanTransact](#cantransact)|데이터 소스에서 트랜잭션을 지원 하면 0이 아닌 값을 반환 합니다.|
|[CDaoRecordset::CanUpdate](#canupdate)|레코드를 업데이트할 수 있으면 0이 아닌 값을 반환 합니다 (있습니다 수 추가, 업데이트 또는 레코드 삭제).|
|[CDaoRecordset::Close](#close)|레코드 집합을 닫습니다.|
|[CDaoRecordset::Delete](#delete)|레코드 집합에서 현재 레코드를 삭제합니다. 삭제 한 후 다른 레코드에 명시적으로 스크롤하여 해야 있습니다.|
|[CDaoRecordset::DoFieldExchange](#dofieldexchange)|레코드 집합의 필드 데이터 멤버와 데이터 원본에 있는 해당 레코드 간에 (양방향)으로 데이터를 교환 하기 위해 호출 됩니다. 구현 DAO 레코드 필드 교환 (DFX).|
|[CDaoRecordset::Edit](#edit)|현재 레코드에 변경 내용을 준비합니다. 호출 `Update` 편집을 완료 합니다.|
|[CDaoRecordset::FillCache](#fillcache)|모든 채우기 또는 ODBC 데이터 원본에서 데이터를 포함 하는 레코드 집합 개체에 대 한 로컬 캐시의 일부입니다.|
|[CDaoRecordset::Find](#find)|먼저 다음을 찾고 현재 레코드로 설정 확인 하 고 지정 된 조건을 충족 하는 다이너셋 형식 레코드 집합에서 특정 문자열의 이전 또는 마지막 위치입니다.|
|[CDaoRecordset::FindFirst](#findfirst)|다이너셋 형식 또는 현재 레코드로 설정 확인 하 고 지정 된 조건을 충족 하는 스냅숏 형식 레코드 집합에서 첫 번째 레코드를 찾습니다.|
|[CDaoRecordset::FindLast](#findlast)|다이너셋 형식 또는 현재 레코드로 설정 확인 하 고 지정 된 조건을 충족 하는 스냅숏 형식 레코드 집합에서 마지막 레코드를 찾습니다.|
|[CDaoRecordset::FindNext](#findnext)|다이너셋 형식 또는 현재 레코드로 설정 확인 하 고 지정 된 조건을 충족 하는 스냅숏 형식 레코드 집합에서 다음 레코드를 찾습니다.|
|[CDaoRecordset::FindPrev](#findprev)|다이너셋 형식 또는 현재 레코드로 설정 확인 하 고 지정 된 조건을 충족 하는 스냅숏 형식 레코드 집합에서 이전 레코드를 찾습니다.|
|[CDaoRecordset::GetAbsolutePosition](#getabsoluteposition)|레코드 집합 개체의 현재 레코드의 레코드 수를 반환합니다.|
|[CDaoRecordset::GetBookmark](#getbookmark)|레코드에서 책갈피를 나타내는 값을 반환 합니다.|
|[CDaoRecordset::GetCacheSize](#getcachesize)|데이터를 ODBC 데이터 원본에서 로컬 캐시를 포함 하는 다이너셋 형식 레코드 집합에서 레코드의 수를 지정 하는 값을 반환 합니다.|
|[CDaoRecordset::GetCacheStart](#getcachestart)|캐시할 레코드 집합의 첫 번째 레코드의 책갈피를 지정 하는 값을 반환 합니다.|
|[CDaoRecordset::GetCurrentIndex](#getcurrentindex)|반환 된 `CString` 인덱싱된 테이블 형식에 사용 되는 이름을 포함 하는 인덱스의 가장 최근에 `CDaoRecordset`합니다.|
|[CDaoRecordset::GetDateCreated](#getdatecreated)|반환 날짜 및 시간을 기본 테이블 내부를 `CDaoRecordset` 개체가 만들어진|
|[CDaoRecordset::GetDateLastUpdated](#getdatelastupdated)|내부 기본 테이블의 디자인에 대 한 최신 변경의 시간과 날짜를 반환 합니다.는 `CDaoRecordset` 개체입니다.|
|[CDaoRecordset::GetDefaultDBName](#getdefaultdbname)|기본 데이터 원본의 이름을 반환합니다.|
|[CDaoRecordset::GetDefaultSQL](#getdefaultsql)|기본 SQL 문자열 실행을 가져오기 위해 호출 됩니다.|
|[CDaoRecordset::GetEditMode](#geteditmode)|현재 레코드의 편집 상태를 나타내는 값을 반환 합니다.|
|[CDaoRecordset::GetFieldCount](#getfieldcount)|레코드 집합의 필드 수를 나타내는 값을 반환 합니다.|
|[CDaoRecordset::GetFieldInfo](#getfieldinfo)|레코드 집합의 특정 종류의 필드에 대 한 정보를 반환합니다.|
|[CDaoRecordset::GetFieldValue](#getfieldvalue)|레코드 집합에서 필드의 값을 반환합니다.|
|[CDaoRecordset::GetIndexCount](#getindexcount)|레코드 집합을 기본 테이블의 인덱스 수를 검색 합니다.|
|[CDaoRecordset::GetIndexInfo](#getindexinfo)|다양 한 종류의 인덱스에 대 한 정보를 반환합니다.|
|[CDaoRecordset::GetLastModifiedBookmark](#getlastmodifiedbookmark)|가장 최근에 추가 되거나 레코드 업데이트를 확인 하는 데 사용 합니다.|
|[CDaoRecordset::GetLockingMode](#getlockingmode)|편집 하는 동안 적용 되는 잠금 유형을 나타내는 값을 반환 합니다.|
|[CDaoRecordset::GetName](#getname)|반환 된 `CString` 레코드 집합의 이름이 들어 있는입니다.|
|[CDaoRecordset::GetParamValue](#getparamvalue)|기본 DAOParameter 개체에 저장 된 지정된 된 매개 변수의 현재 값을 검색 합니다.|
|[CDaoRecordset::GetPercentPosition](#getpercentposition)|현재 레코드의 총 레코드 수의 백분율로 표시 위치를 반환합니다.|
|[CDaoRecordset::GetRecordCount](#getrecordcount)|레코드 집합 개체에 액세스 하는 레코드의 수를 반환 합니다.|
|[CDaoRecordset::GetSQL](#getsql)|레코드 집합에 대 한 레코드를 선택 하는 데 사용 되는 SQL 문자열을 가져옵니다.|
|[CDaoRecordset::GetType](#gettype)|레코드 집합의 형식을 확인 하기 위해 호출 됩니다: 테이블 형식, 다이너셋-형식 또는 스냅숏 유형입니다.|
|[CDaoRecordset::GetValidationRule](#getvalidationrule)|반환을 `CString` 필드에 입력할 때 데이터의 유효성을 검사 하는 값을 포함 합니다.|
|[CDaoRecordset::GetValidationText](#getvalidationtext)|유효성 검사 규칙을 만족 하지 않을 때 표시 되는 텍스트를 검색 합니다.|
|[CDaoRecordset::IsBOF](#isbof)|첫 번째 레코드 앞 레코드 집합에 배치 하는 경우 0이 아닌 값을 반환 합니다. 현재 레코드가 없습니다.|
|[CDaoRecordset::IsDeleted](#isdeleted)|레코드 집합은 삭제 된 레코드에 배치 되 면 0이 아닌 값을 반환 합니다.|
|[CDaoRecordset::IsEOF](#iseof)|레코드 집합 마지막 레코드 다음 배치 된 경우 0이 아닌 값을 반환 합니다. 현재 레코드가 없습니다.|
|[CDaoRecordset::IsFieldDirty](#isfielddirty)|지정된 된 필드에서 현재 레코드가 변경 된 경우 0이 아닌 값을 반환 합니다.|
|[CDaoRecordset::IsFieldNull](#isfieldnull)|현재 레코드에 지정된 된 필드 (값이 없는 것) Null 이면 0이 아닌 값을 반환 합니다.|
|[CDaoRecordset::IsFieldNullable](#isfieldnullable)|현재 레코드에 지정된 된 필드 (값 필요) 하는 Null로 설정할 수 있는 경우 0이 아닌 값을 반환 합니다.|
|[CDaoRecordset::IsOpen](#isopen)|0이 아닌 경우 반환 [열려](#open) 가 이전에 호출 되었습니다.|
|[CDaoRecordset::Move](#move)|어느 방향으로든에서 현재 레코드에서 지정된 된 수의 레코드를 레코드 집합을 배치합니다.|
|[CDaoRecordset::MoveFirst](#movefirst)|레코드 집합의 첫 번째 레코드에서 현재 레코드를 배치합니다.|
|[CDaoRecordset::MoveLast](#movelast)|레코드 집합의 마지막 레코드를 현재 레코드를 배치합니다.|
|[CDaoRecordset::MoveNext](#movenext)|레코드 집합에서 다음 레코드를 현재 레코드를 배치합니다.|
|[CDaoRecordset::MovePrev](#moveprev)|레코드 집합에서 이전 레코드를 현재 레코드를 배치합니다.|
|[CDaoRecordset::Open](#open)|테이블, 다이너셋, 또는 스냅숏에서 새 레코드 집합을 만듭니다.|
|[CDaoRecordset::Requery](#requery)|레코드 집합의 쿼리를 선택한 레코드를 새로 고치려면 다시 실행 합니다.|
|[CDaoRecordset::Seek](#seek)|현재 인덱스를 사용 하면 현재 레코드를 기록 하는 지정 된 조건을 충족 하는 인덱싱된 테이블 형식 레코드 집합 개체에서 레코드를 찾습니다.|
|[CDaoRecordset::SetAbsolutePosition](#setabsoluteposition)|레코드 집합 개체의 현재 레코드의 레코드 번호를 설정합니다.|
|[CDaoRecordset::SetBookmark](#setbookmark)|지정한 책갈피를 포함 하는 레코드를 레코드 집합을 배치 합니다.|
|[CDaoRecordset::SetCacheSize](#setcachesize)|데이터를 ODBC 데이터 원본에서 로컬 캐시를 포함 하는 다이너셋 형식 레코드 집합에서 레코드의 수를 지정 하는 값을 설정 합니다.|
|[CDaoRecordset::SetCacheStart](#setcachestart)|캐시할 레코드 집합의 첫 번째 레코드의 책갈피를 지정 하는 값을 설정 합니다.|
|[CDaoRecordset::SetCurrentIndex](#setcurrentindex)|테이블 형식 레코드 집합에 인덱스를 설정 하기 위해 호출 됩니다.|
|[CDaoRecordset::SetFieldDirty](#setfielddirty)|변경 된 것으로 현재 레코드에 지정된 된 필드를 표시 합니다.|
|[CDaoRecordset::SetFieldNull](#setfieldnull)|(값이 없는 것) Null로 현재 레코드에 지정된 된 필드의 값을 설정 합니다.|
|[CDaoRecordset::SetFieldValue](#setfieldvalue)|레코드 집합에서 필드의 값을 설정 합니다.|
|[CDaoRecordset::SetFieldValueNull](#setfieldvaluenull)|Null로 레코드 집합에서 필드의 값을 설정 합니다. (값이 없는 필요 없음).|
|[CDaoRecordset::SetLockingMode](#setlockingmode)|편집 하는 동안 적용 넣을 잠금 유형을 나타내는 값을 설정 합니다.|
|[CDaoRecordset::SetParamValue](#setparamvalue)|기본 DAOParameter 개체에 저장 된 지정된 된 매개 변수의 현재 값을 설정|
|[CDaoRecordset::SetParamValueNull](#setparamvaluenull)|지정된 된 매개 변수의 현재 값 (값이 없는 것) Null로 설정 합니다.|
|[CDaoRecordset::SetPercentPosition](#setpercentposition)|레코드 집합에서 레코드의 총 수 백분율에 해당 하는 위치에 현재 레코드의 위치를 설정 합니다.|
|[CDaoRecordset::Update](#update)|완료 되는 `AddNew` 또는 `Edit` 데이터 원본에서 새로 만들거나 편집한 데이터를 저장 하 여 작업 합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CDaoRecordset::m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields)|변경 된 것으로 필드는 자동으로 표시 여부를 나타내는 플래그를 포함 합니다.|
|[CDaoRecordset::m_nFields](#m_nfields)|레코드 집합 클래스의 필드 데이터 멤버의 수 및 데이터 원본에서 레코드 집합에서 선택한 열 수가 포함 됩니다.|
|[CDaoRecordset::m_nParams](#m_nparams)|레코드 집합 클래스에서 매개 변수 데이터 멤버 수가 포함-레코드 집합의 쿼리와 함께 전달 되는 매개 변수 개수|
|[CDaoRecordset::m_pDAORecordset](#m_pdaorecordset)|레코드 집합 개체를 기본 DAO 인터페이스에 대 한 포인터입니다.|
|[CDaoRecordset::m_pDatabase](#m_pdatabase)|이 결과 집합에 대 한 원본 데이터베이스입니다. 에 대 한 포인터를 포함 한 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체입니다.|
|[CDaoRecordset::m_strFilter](#m_strfilter)|SQL을 생성 하는 데 사용 하는 문자열을 포함 **여기서** 문입니다.|
|[CDaoRecordset::m_strSort](#m_strsort)|SQL을 생성 하는 데 사용 하는 문자열을 포함 **ORDER BY** 문입니다.|

## <a name="remarks"></a>설명

"레코드 집합" 이라고 `CDaoRecordset` 개체는 다음과 같은 세 가지 형태로 사용할 수 있습니다.

- 테이블 형식 레코드 집합 검사, 추가, 변경 또는 단일 데이터베이스 테이블에서 레코드를 삭제 하는 데 사용할 수 있는 기본 테이블을 나타냅니다.

- 다이너셋 형식 레코드 집합은 업데이트할 수 있는 레코드를 가질 수 있는 쿼리의 결과입니다. 이러한 레코드 집합은 검사, 추가, 변경 또는 기본 데이터베이스 테이블 또는 테이블에서 레코드를 삭제 하는 데 사용할 수 있는 레코드 집합이 있습니다. 다이너셋 형식 레코드 집합을 데이터베이스에서 하나 이상의 테이블의 필드를 포함할 수 있습니다.

- 스냅숏 형식 레코드 집합은 데이터를 찾거나 보고서를 생성 하는 데 사용할 수 있는 레코드 집합의 정적 복사본입니다. 이러한 레코드 집합을 데이터베이스에서 하나 이상의 테이블의 필드를 포함할 수 있지만 업데이트할 수 없습니다.

각 형식의 레코드 집합에는 레코드 집합을 열 때 고정 된 레코드 집합을 나타냅니다. 테이블 형식 레코드 집합 또는 다이너셋 형식 레코드 집합에서 레코드를 스크롤할 때 다른 사용자 또는 응용 프로그램의 다른 레코드 집합에서 레코드 집합을 연 후에 레코드에 변경한 내용을 반영 합니다. (스냅숏 형식 레코드 집합을 업데이트할 수 없습니다.) 사용할 수 있습니다 `CDaoRecordset` 직접는 응용 프로그램 관련 레코드 집합 클래스에서 파생 또는 `CDaoRecordset`합니다. 그런 다음 다음을 수행할 수 있습니다.

- 레코드를 스크롤하십시오.

- 인덱스를 설정 하 고 신속 하 게 사용 하 여 레코드를 검색할 [Seek](#seek) (테이블 형식 레코드 집합에만 해당).

- 문자열 비교를 기반으로 하는 레코드를 찾는: "<","\<=", "=" "> =", 또는 ">" (다이너셋 형식 및 스냅숏 형식 레코드 집합).

- 레코드를 업데이트 하 고 (스냅숏 형식 레코드 집합) 제외 잠금 모드를 지정 합니다.

- 데이터 원본에 사용할 수 있는 파일에서 선택 하는 레코드를 제한 하는 레코드 집합을 필터링 합니다.

- 레코드 집합을 정렬 합니다.

- 런타임 전에 알 수 없는 정보를 사용 하 여 해당 선택 항목이 사용자 지정 하는 레코드 집합 매개 변수화 합니다.

클래스 `CDaoRecordset` 클래스와 비슷한 인터페이스를 제공 `CRecordset`합니다. 주요 차이점은 해당 클래스 `CDaoRecordset` OLE에 따라 데이터 액세스 개체 (DAO)를 통해 데이터에 액세스 합니다. 클래스 `CRecordset` DBMS에 대 한 DBMS 개방형 데이터베이스 연결 (ODBC) 및 ODBC 드라이버를 통해 액세스 합니다.

> [!NOTE]
> DAO 데이터베이스 클래스로 개방형 데이터베이스 연결 (ODBC)에 따라 MFC 데이터베이스 클래스와에서 다릅니다. 모든 DAO 데이터베이스 클래스 이름 "CDao" 접두사가 있습니다. DAO 클래스;를 사용 하 여 ODBC 데이터 원본 액세스 수 Microsoft Jet 데이터베이스 엔진에 특정 되므로 DAO 클래스 일반적으로 뛰어난 기능을 제공 합니다.

사용할 수 있습니다 `CDaoRecordset` 직접에서 클래스를 파생 하거나 `CDaoRecordset`합니다. 두 경우 모두에서 레코드 집합 클래스를 사용 하려면 데이터베이스를 열고 생성자에 대 한 포인터를 전달 하는 레코드 집합 개체를 생성 하면 `CDaoDatabase` 개체입니다. 생성할 수도 있습니다는 `CDaoRecordset` 개체를 임시 역할을 만들려면 MFC `CDaoDatabase` 개체입니다. 레코드 집합의 다음 호출 [열고](#open) 멤버 함수를 테이블 형식 레코드 집합, 다이너셋 형식 레코드 집합 또는 스냅숏 형식 레코드 집합 개체 인지 여부를 지정 합니다. 호출 `Open` 데이터베이스에서 데이터를 선택 하 고 첫 번째 레코드를 검색 합니다.

개체의 멤버 함수 및 데이터 멤버를 사용 하 여 레코드를 스크롤할를 에서도 작동 합니다. 사용할 수 있는 작업 개체 인지 여부는 테이블 형식의 레코드 집합, 다이너셋 형식 레코드 집합을 스냅숏 형식 레코드 집합 및 업데이트 가능 또는 읽기 전용 인지에 따라 달라 집니다-데이터베이스 또는 개방형 데이터베이스 연결 (ODBC)의 기능에 따라 달라 집니다. 데이터 원본입니다. 변경 되거나 이후 추가 된 있습니다 레코드를 새로 고치려면 합니다 `Open` 호출, 개체의 호출 [Requery](#requery) 멤버 함수입니다. 개체의 호출 `Close` 멤버 함수 및이 사용 하 여 마친 후 개체를 제거 합니다.

`CDaoRecordset` DAO 레코드 필드 교환 (DFX)를 사용 하 여 형식이 안전한 통해 읽기 및 레코드 필드의 업데이트를 지원 하기 위해 C++ 의 멤버에 `CDaoRecordset` 또는 `CDaoRecordset`-클래스를 파생 합니다. 사용 하 여 DFX 메커니즘을 사용 하지 않고 데이터베이스에 열 동적 바인딩 구현할 수도 있습니다 [GetFieldValue](#getfieldvalue) 하 고 [SetFieldValue](#setfieldvalue)합니다.

관련된 내용은 DAO 도움말에서 "레코드 집합 개체" 항목을 참조 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CDaoRecordset`

## <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

##  <a name="addnew"></a>  CDaoRecordset::AddNew

테이블 형식 또는 다이너셋 형식 레코드 집합에 새 레코드를 추가 하려면이 멤버 함수를 호출 합니다.

```
virtual void AddNew();
```

### <a name="remarks"></a>설명

레코드의 필드는 처음에 Null입니다. (데이터베이스 용어에서 "값 필요"는 의미를 Null 및 NULL에과 같지 않습니다 C++입니다.) 호출 작업을 완료 해야 합니다 [업데이트](#update) 멤버 함수입니다. `Update` 데이터 원본에 변경 내용을 저장 합니다.

> [!CAUTION]
>  레코드를 편집 하 고 호출 하지 않고 다른 레코드를 스크롤한 `Update`, 변경 내용을 경고 없이 손실 됩니다.

호출 하 여 다이너셋 형식 레코드 집합에 레코드를 추가 하는 경우 [AddNew](#addnew), 레코드는 레코드 집합에 표시 되며 수에 새 기본 테이블에 포함 되어 `CDaoRecordset` 개체입니다.

새 레코드의 위치 레코드 집합의 형식에 따라 달라 집니다.

- 다이너셋 형식의 레코드 집합을 새 레코드를 삽입 하는 위치 보장 되지 않습니다. 이 동작은 성능 및 동시성의 이유로 Microsoft Jet 3.0을 사용 하 여 변경 합니다. 현재 레코드를 새로 추가 된 레코드를 확인 하는 것이 목표인 경우 마지막으로 수정 된 레코드의 책갈피를 가져오고 해당 책갈피로 이동 합니다.

[!code-cpp[NVC_MFCDatabase#1](../../mfc/codesnippet/cpp/cdaorecordset-class_1.cpp)]

- 인덱스로 지정 된 테이블 형식 레코드 집합의 정렬 순서에서 적절 한 위치에서 레코드가 반환 됩니다. 지정 된 인덱스가 없는 경우 레코드 집합의 끝에 새 레코드가 반환 됩니다.

사용 하기 전에 현재 레코드가 `AddNew` 현재 상태로 유지 됩니다. 현재 새 레코드를 확인 하 고 레코드 집합 지원 책갈피를 호출 하는 경우 [SetBookmark](#setbookmark) 기본 DAO 레코드 집합 개체의 LastModified 속성 설정에 의해 식별 된 책갈피로 합니다. 이렇게 추가 된 레코드의 카운터 (자동 증분) 필드에 대 한 값을 결정 하는 데 유용 합니다. 자세한 내용은 [GetLastModifiedBookmark](#getlastmodifiedbookmark)합니다.

데이터베이스에서 트랜잭션을 지원할 경우에 `AddNew` 트랜잭션의 일부로 호출 합니다. 트랜잭션에 대 한 자세한 내용은 클래스를 참조 하세요 [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)합니다. 호출 해야 하는 참고 [CDaoWorkspace::BeginTrans](../../mfc/reference/cdaoworkspace-class.md#begintrans) 호출 하기 전에 `AddNew`입니다.

호출 하는 것이 올바르지 `AddNew` 레코드 집합에 대 한 해당 [오픈](#open) 멤버 함수가 호출 되지 않았습니다. A `CDaoException` 호출 하는 경우 throw 되 `AddNew` 레코드 집합을 추가할 수 없습니다. 호출 하 여 레코드 집합을 업데이트할 수 있는지 여부를 확인할 수 있습니다 [CanAppend](#canappend)합니다.

Framework 표시 DAO 레코드 필드 교환 (DFX) 메커니즘을 통해 데이터 소스에서 레코드를 기록 수는 되도록 필드 데이터 멤버를 변경 합니다. 필드의 값을 일반적으로 변경 필드 설정 더티 자동으로 호출할 필요가 거의 [SetFieldDirty](#setfielddirty) 수 있지만 사용자가 직접 할 때도 열은 명시적으로 업데이트 되거나 삽입 될와 상관 없이 확인 값의 필드 데이터 멤버입니다. DFX 메커니즘 사용을 손쉽게 **의사 NULL**합니다. 자세한 내용은 [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation)합니다.

이중 버퍼링 메커니즘을 사용 하지 않는 경우 필드의 값을 변경한 다음 설정 하지 않습니다 자동으로 필드 변경 된 상태로 보입니다. 이 경우 커밋되지 않은 데이터 필드를 명시적으로 설정 하는 데 필요한 됩니다. 에 포함 된 플래그 [m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) 이 자동 필드 검사를 제어 합니다.

> [!NOTE]
> 이중 버퍼링 된 경우 레코드 (즉, 자동 필드 검사 사용), 호출 `CancelUpdate` 멤버 변수를 실행 하기 전과 값으로 복원 `AddNew` 또는 `Edit` 호출 되었습니다.

관련된 정보에 대 한 "AddNew 메서드", "CancelUpdate 메서드", "LastModified 속성" 및 "EditMode 속성" DAO 도움말의 항목을 참조 합니다.

##  <a name="canappend"></a>  CDaoRecordset::CanAppend

이전에 열린된 레코드를 호출 하 여 새 레코드를 추가할 수를 허용 하는지 여부를 결정 하는이 멤버 함수를 호출 합니다 [AddNew](#addnew) 멤버 함수입니다.

```
BOOL CanAppend() const;
```

### <a name="return-value"></a>반환 값

0이 아닌 레코드 집합; 새 레코드를 추가할 수 있습니다. 그렇지 않으면 0입니다. `CanAppend` 읽기 전용으로 레코드 집합을 연 경우에 0을 반환 합니다.

### <a name="remarks"></a>설명

관련된 내용은 DAO 도움말의 "메서드 추가" 항목을 참조 합니다.

##  <a name="canbookmark"></a>  CDaoRecordset::CanBookmark

책갈피를 사용 하 여 레코드를 개별적으로 표시 하 여 이전에 열린된 레코드 집합 허용 하는지 여부를 결정 하는이 멤버 함수를 호출 합니다.

```
BOOL CanBookmark();
```

### <a name="return-value"></a>반환 값

레코드 집합에서 책갈피, 그렇지 않으면 0을 지 원하는 경우에 0이 아닙니다.

### <a name="remarks"></a>설명

레코드 집합을 기준으로 Microsoft Jet 데이터베이스 엔진 테이블을 사용 하는 경우 스크롤 레코드 집합을 정방향으로 플래그가 지정 된 스냅숏 형식 레코드 집합에서 제외 하 고 책갈피에 사용할 수 있습니다. 다른 데이터베이스 제품 (외부 ODBC 데이터 원본) 책갈피를 지원 하지 않습니다.

관련된 정보 DAO 도움말의 "책갈피를 설정할 속성" 항목을 참조 하세요.

##  <a name="cancelupdate"></a>  CDaoRecordset::CancelUpdate

합니다 `CancelUpdate` 로 인해 모든 보류 중인 업데이트를 취소 하는 멤버 함수는 [편집](#edit) 또는 [AddNew](#addnew) 작업 합니다.

```
virtual void CancelUpdate();
```

### <a name="remarks"></a>설명

예를 들어, 응용 프로그램을 호출 하는 경우는 `Edit` 또는 `AddNew` 멤버 함수에 호출 되지 [업데이트](#update)를 `CancelUpdate` 이후의 모든 변경 내용을 취소 `Edit` 또는 `AddNew` 호출 되었습니다.

> [!NOTE]
>  이중 버퍼링 된 경우 레코드 (즉, 자동 필드 검사 사용), 호출 `CancelUpdate` 멤버 변수를 실행 하기 전과 값으로 복원 `AddNew` 또는 `Edit` 호출 되었습니다.

없는 경우 없습니다 `Edit` 나 `AddNew` 작업을 보류 `CancelUpdate` MFC 예외를 throw 하면 합니다. 호출 된 [GetEditMode](#geteditmode) 멤버 함수를 취소할 수 있는 보류 중인 작업이 있는지 확인 합니다.

관련된 내용은 DAO 도움말의 "CancelUpdate 메서드" 항목을 참조 합니다.

##  <a name="canrestart"></a>  CDaoRecordset::CanRestart

레코드 집합 (해당 레코드를 새로 고침)를 해당 쿼리를 호출 하 여 다시 시작을 허용 하는지 여부를 결정 하는이 멤버 함수를 호출 합니다 `Requery` 멤버 함수입니다.

```
BOOL CanRestart();
```

### <a name="return-value"></a>반환 값

0이 아닌 경우 `Requery` 레코드 집합의 쿼리를 다시 그렇지 않으면 0을 실행 하기 위해 호출할 수 있습니다.

### <a name="remarks"></a>설명

테이블 형식 레코드 집합을 지원 하지 않는 `Requery`합니다.

경우 `Requery` 는 지원 되지 않는 호출 [닫기](#close) 한 다음 [열기](#open) 데이터를 새로 고치려면. 호출할 수 있습니다 `Requery` 레코드 집합 개체를 업데이트 하려면의 기본 매개 변수 쿼리 매개 변수 값을 변경한 후입니다.

관련된 정보 DAO 도움말에서 "다시 시작 가능 속성" 항목을 참조 하세요.

##  <a name="canscroll"></a>  CDaoRecordset::CanScroll

레코드 스크롤을 허용 하는지 여부를 결정 하는이 멤버 함수를 호출 합니다.

```
BOOL CanScroll() const;
```

### <a name="return-value"></a>반환 값

그렇지 않으면 0 레코드를 스크롤할 수 있습니다 하는 경우에 0이 아닙니다.

### <a name="remarks"></a>설명

호출 하는 경우 [엽니다](#open) 사용 하 여 `dbForwardOnly`, 레코드 집합 정방향 스크롤만 있습니다.

관련된 내용은 DAO 도움말에서 "DAO를 사용 하 여 하 여 현재 레코드 포인터 위치 지정" 항목을 참조 합니다.

##  <a name="cantransact"></a>  CDaoRecordset::CanTransact

레코드 집합 트랜잭션을 허용 하는지 여부를 결정 하는이 멤버 함수를 호출 합니다.

```
BOOL CanTransact();
```

### <a name="return-value"></a>반환 값

데이터 원본에서 트랜잭션, 그렇지 않으면 0을 지 원하는 경우에 0이 아닙니다.

### <a name="remarks"></a>설명

관련된 정보 DAO 도움말의 "트랜잭션 속성" 항목을 참조 하세요.

##  <a name="canupdate"></a>  CDaoRecordset::CanUpdate

레코드 집합을 업데이트할 수 있는지 여부를 결정 하는이 멤버 함수를 호출 합니다.

```
BOOL CanUpdate() const;
```

### <a name="return-value"></a>반환 값

0이 아닌 레코드 집합을 업데이트할 수 있습니다 (추가, 업데이트 및 삭제 레코드), 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

레코드 집합 수 읽기 전용 데이터 원본 읽기 전용인 지 아니면 지정한 `dbReadOnly` 에 대 한 *nOptions* 호출 하는 경우 [오픈](#open) 레코드 집합에 대 한 합니다.

관련된 정보에 대 한 "AddNew 메서드", "편집", "Delete 메서드", "Update 메서드" 메서드와 DAO 도움말의 "업데이트할 수 있는 속성" 항목을 참조 합니다.

##  <a name="cdaorecordset"></a>  CDaoRecordset::CDaoRecordset

`CDaoRecordset` 개체를 생성합니다.

```
CDaoRecordset(CDaoDatabase* pDatabase = NULL);
```

### <a name="parameters"></a>매개 변수

*pDatabase*<br/>
에 대 한 포인터를 포함 한 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체 또는 NULL 값입니다. NULL이 아닌 경우 및 `CDaoDatabase` 개체의 `Open` 멤버 함수는 데이터 원본에 연결할 호출 되지 않은, 레코드 집합을 하는 동안 자체를 열려고 시도할 [엽니다](#open) 호출 합니다. NULL을 전달 하는 경우는 `CDaoDatabase` 개체가 생성 되 고 연결에서 레코드 집합 클래스를 파생 하는 경우 지정한 데이터 원본 정보를 사용 하 여 `CDaoRecordset`입니다.

### <a name="remarks"></a>설명

사용할 수 있습니다 `CDaoRecordset` 직접에서 응용 프로그램 관련 클래스를 파생 하거나 `CDaoRecordset`합니다. 레코드 집합 클래스를 파생 시킬 클래스 마법사를 사용할 수 있습니다.

> [!NOTE]
>  파생 하는 경우는 `CDaoRecordset` 클래스에서 파생 된 클래스는 자체 생성자를 제공 해야 합니다. 파생된 클래스의 생성자에서 생성자를 호출 `CDaoRecordset::CDaoRecordset`을 따라 적절 한 매개 변수를 전달 합니다.

할 레코드 집합 생성자에 NULL을 전달할를 `CDaoDatabase` 개체 생성 및를 자동으로 연결 합니다. 이 생성 하 고 연결에 필요 하지 않은 한 유용한 바로 가기는 `CDaoDatabase` 레코드 집합을 생성 하기 전에 개체입니다. 경우는 `CDaoDatabase` 개체가 열려 있지 않으면를 [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) 기본 작업 영역을 사용 하는 개체도 생성 됩니다. 자세한 내용은 [CDaoDatabase::CDaoDatabase](../../mfc/reference/cdaodatabase-class.md#cdaodatabase)합니다.

##  <a name="close"></a>  CDaoRecordset::Close

닫기는 `CDaoRecordset` 개체 관련된 데이터베이스에서 열려 있는 레코드 집합이 컬렉션에서 제거 합니다.

```
virtual void Close();
```

### <a name="remarks"></a>설명

때문에 `Close` 제거 하지 않습니다 합니다 `CDaoRecordset` 개체를 호출 하 여 개체를 다시 사용할 수 있습니다 `Open` 동일한 데이터 원본 또는 다른 데이터 원본입니다.

모든 보류 중인 [AddNew](#addnew) 하거나 [편집](#edit) 문이 취소 되 고 보류 중인 모든 트랜잭션이 롤백됩니다. 보류 중인 추가 또는 편집에 유지 하려는 경우 호출할 [업데이트](#update) 를 호출 하기 전에 `Close` 각 레코드 집합에 대 한 합니다.

호출할 수 있습니다 `Open` 호출 후에 다시 `Close`입니다. 이 기능을 사용 하면 레코드 집합 개체를 다시 사용할 수 있습니다. 더 나은 방법은 호출 [Requery](#requery)가능한 경우.

관련된 내용은 DAO 도움말의 "Close 메서드가" 항목을 참조 합니다.

##  <a name="delete"></a>  CDaoRecordset::Delete

열려 있는 다이너셋 형식 또는 테이블 형식 레코드 집합 개체의 현재 레코드를 삭제 하려면이 멤버 함수를 호출 합니다.

```
virtual void Delete();
```

### <a name="remarks"></a>설명

성공적으로 삭제 한 후 레코드 집합의 필드 데이터 멤버는 Null 값으로 설정 되 고 레코드 집합 탐색 멤버 함수 중 하나를 명시적으로 호출 해야 합니다 ( [이동](#move)하십시오 [Seek](#seek), [ SetBookmark](#setbookmark)등) 삭제 된 레코드를 이동 하기 위해. 레코드 집합에서 레코드를 삭제 하면 현재 레코드에에서 있어야 레코드를 호출 하기 전에 `Delete`고, 그렇지 않으면 MFC 예외를 throw 합니다.

`Delete` 현재 레코드를 제거 하 고 액세스할 수 없게 합니다. 편집 하거나 삭제 된 레코드를 사용할 수 없습니다, 있지만 현재 유지 됩니다. 그러나 다른 레코드를 이동 하면 만들 수 없습니다는 삭제 된 레코드 현재 다시 합니다.

> [!CAUTION]
>  해당 레코드를 업데이트할 수 있어야 하며 있어야 유효한 레코드 레코드 집합의 현재 호출할 때 `Delete`합니다. 예를 들어 레코드를 삭제 해도 스크롤되지 새 레코드를 호출 하기 전에 `Delete` 다시 `Delete` throw를 [CDaoException](../../mfc/reference/cdaoexception-class.md)합니다.

트랜잭션을 사용 하 고 호출 하는 경우에 레코드를 삭제 취소 수는 [CDaoWorkspace::Rollback](../../mfc/reference/cdaoworkspace-class.md#rollback) 멤버 함수입니다. 기본 테이블은 기본 테이블 계단식으로 관계를 삭제할 경우 현재 레코드를 삭제 하는 중 하나 이상의 레코드에 있는 외래 테이블에서 삭제할 수도 있습니다. 자세한 내용은 DAO 도움말의 정의 "하위 삭제"를 참조 하세요.

와 달리 `AddNew` 하 고 `Edit`에 대 한 호출 `Delete` 를 호출 하 여 따르지 않으면 `Update`합니다.

관련된 정보에 대 한 "AddNew 메서드", "편집", "Delete 메서드", "Update 메서드" 메서드와 DAO 도움말의 "업데이트할 수 있는 속성" 항목을 참조 합니다.

##  <a name="dofieldexchange"></a>  CDaoRecordset::DoFieldExchange

프레임 워크가 자동으로 레코드 집합 개체의 필드 데이터 멤버와 데이터 소스에서 현재 레코드의 해당 열 간에 데이터를 교환 하려면이 멤버 함수를 호출 합니다.

```
virtual void DoFieldExchange(CDaoFieldExchange* pFX);
```

### <a name="parameters"></a>매개 변수

*pFX*<br/>
에 대 한 포인터를 포함 한 `CDaoFieldExchange` 개체입니다. 프레임 워크는 이미 설정한이 개체 필드 exchange 작업에 대 한 컨텍스트를 지정 합니다.

### <a name="remarks"></a>설명

레코드 집합의 선택에 대 한 SQL 문 문자열의 매개 변수 자리 표시자에 있는 경우 새 매개 변수 데이터 멤버에 바인딩합니다. 두 방향 모두에서 작동 하는 DAO 레코드 필드 교환 (DFX) 라고 하는 필드 데이터 교환을: 레코드 집합 개체를 데이터 소스에서 레코드 및 레코드 집합 개체의 필드 데이터 멤버 데이터 소스에서 레코드의 필드에에서 있습니다. 열에 동적으로 바인딩하는 경우는 필요가 없으며 구현 `DoFieldExchange`합니다.

일반적으로 구현 하기 위해 취해야 할 유일한 작업은 `DoFieldExchange` 클래스는 파생 된 레코드 집합에 대 한 클래스 마법사를 사용 하 여 클래스를 만들고 필드 데이터 멤버의 이름과 데이터 형식을 지정 합니다. 또한 매개 변수 데이터 멤버를 지정 쓸 classwizard 함께 사용 하려면 코드를 추가할 수 있습니다. 모든 필드를 동적으로 바인딩할 수 없으면이 함수가 비활성화 됩니다 매개 변수 데이터 멤버를 지정 하지 않으면.

마법사에 대 한 재정의 기록 클래스 마법사를 사용 하 여 파생된 레코드 집합 클래스를 선언할 때 `DoFieldExchange` , 다음 예제에서는 유사 합니다.

[!code-cpp[NVC_MFCDatabase#2](../../mfc/codesnippet/cpp/cdaorecordset-class_2.cpp)]

##  <a name="edit"></a>  CDaoRecordset::Edit

현재 레코드에 대 한 변경을 허용 하려면이 멤버 함수를 호출 합니다.

```
virtual void Edit();
```

### <a name="remarks"></a>설명

호출 하 여 `Edit` 멤버 함수의 경우 현재 레코드의 필드에 대 한 변경 내용을 복사 버퍼에 복사 됩니다. 원하는 변경 내용을 레코드에 변경한 후 호출 `Update` 변경 내용을 저장 합니다. `Edit` 레코드 집합의 데이터 멤버의 값을 저장합니다. 호출 하는 경우 `Edit`을 변경한 다음 호출 `Edit` 으로 첫 번째 레코드의 값이 복원 됩니다 다시 `Edit` 호출 합니다.

> [!CAUTION]
>  레코드를 편집한 다음 첫 번째 호출 하지 않고 다른 레코드로 이동 하는 작업을 수행 하는 경우 `Update`, 변경 내용을 경고 없이 손실 됩니다. 또한 레코드 집합 또는 부모 데이터베이스를 닫는 경우 경고 없이 편집된 하 여 레코드 삭제 됩니다.

경우에 따라 Null (데이터 포함) 하 여 열을 업데이트 하는 것이 좋습니다. 이렇게 하려면 호출 `SetFieldNull` Null 필드를 표시 하는 true로 설정 하면 매개 변수를 사용 하 여이 인해 업데이트할 열입니다. 해당 값이 변경 되지 않은 경우에 데이터 원본에 쓸 수를 호출 하는 필드를 원하는 경우 `SetFieldDirty` true 매개 변수를 사용 합니다. 이 필드를 Null 값이 있으면도 작동 합니다.

Framework 표시 DAO 레코드 필드 교환 (DFX) 메커니즘을 통해 데이터 소스에서 레코드를 기록 수는 되도록 필드 데이터 멤버를 변경 합니다. 필드의 값을 일반적으로 변경 필드 설정 더티 자동으로 호출할 필요가 거의 [SetFieldDirty](#setfielddirty) 수 있지만 사용자가 직접 할 때도 열은 명시적으로 업데이트 되거나 삽입 될와 상관 없이 확인 값의 필드 데이터 멤버입니다. DFX 메커니즘 사용을 손쉽게 **의사 NULL**합니다. 자세한 내용은 [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation)합니다.

이중 버퍼링 메커니즘을 사용 하지 않는 경우 필드의 값을 변경한 다음 설정 하지 않습니다 자동으로 필드 변경 된 상태로 보입니다. 이 경우 커밋되지 않은 데이터 필드를 명시적으로 설정 하는 데 필요한 됩니다. 에 포함 된 플래그 [m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) 이 자동 필드 검사를 제어 합니다.

레코드 집합 개체를 잠그면 pessimistically 다중 사용자 환경에서, 레코드 잠긴 상태로 유지 됩니다 시간부터 `Edit` 업데이트가 완료 될 때까지 사용 됩니다. 레코드 집합 낙관적으로 잠겨 있으면 레코드 잠기고 데이터베이스의 업데이트 직전 미리 편집한 레코드와 비교 합니다. 레코드는 호출한 후에 변경 된 경우 `Edit`, `Update` 작업이 실패 하 고 MFC 예외를 throw 합니다. 사용 하 여 잠금 모드를 변경할 수 있습니다 `SetLockingMode`합니다.

> [!NOTE]
>  낙관적 잠금 ODBC 등 설치 가능한 ISAM 외부 데이터베이스 형식으로 항상 사용 됩니다.

현재 레코드를 호출한 후 남아 `Edit`합니다. 호출 `Edit`, 현재 레코드 여야 합니다. 현재 레코드가 없을 또는 레코드 집합 열기 테이블 형식 또는 다이너셋 형식 레코드 집합 개체를 참조 하지 않는 경우 예외가 발생 합니다. 호출 `Edit` 하면는 `CDaoException` 다음과 같은 경우 throw 됩니다.

- 현재 레코드가 없습니다.

- 데이터베이스 또는 레코드 집합에는 읽기 전용입니다.

- 레코드에 없는 필드를 업데이트할 수 있습니다.

- 데이터베이스 또는 레코드 집합이 배타적으로 사용에 대 한 다른 사용자가 열립니다.

- 다른 사용자에는 레코드가 포함 된 페이지에서 잠 궜 습니다.

가능 데이터 소스에서 트랜잭션을 지원 합니다 `Edit` 트랜잭션의 일부로 호출 합니다. 호출 해야 하는 참고 `CDaoWorkspace::BeginTrans` 호출 하기 전에 `Edit` 열리면 레코드 집합 및 합니다. 호출 하는 참고 `CDaoWorkspace::CommitTrans` 호출에 대 한 대체 하지 않습니다 `Update` 완료 하는 `Edit` 작업 합니다. 트랜잭션에 대 한 자세한 내용은 클래스를 참조 하세요. `CDaoWorkspace`합니다.

관련된 정보에 대 한 "AddNew 메서드", "편집", "Delete 메서드", "Update 메서드" 메서드와 DAO 도움말의 "업데이트할 수 있는 속성" 항목을 참조 합니다.

##  <a name="fillcache"></a>  CDaoRecordset::FillCache

지정 된 수의 레코드 집합에서 레코드를 캐시 하려면이 멤버 함수를 호출 합니다.

```
void FillCache(
    long* pSize = NULL,
    COleVariant* pBookmark = NULL);
```

### <a name="parameters"></a>매개 변수

*pSize*<br/>
캐시를 작성 하는 행 수를 지정 합니다. 이 매개 변수를 생략 하면 값이 기본 DAO 개체의 CacheSize 속성 설정에 따라 결정 됩니다.

*pBookmark*<br/>
A [COleVariant](../../mfc/reference/colevariant-class.md) 책갈피를 지정 합니다. 이 책갈피를 가리키는 레코드에서 시작 캐시가 채워집니다. 이 매개 변수를 생략 하면 기본 DAO 개체의 CacheStart 속성으로 표시 된 레코드에서 시작 캐시가 채워집니다.

### <a name="remarks"></a>설명

캐싱은 검색 하거나 원격 서버에서 데이터를 인출 하는 응용 프로그램의 성능을 개선 합니다. 캐시는 데이터는 다시 요청할 가능성이 응용 프로그램이 실행 되는 동안 가정에 서버에서 가장 최근에 인출 된 데이터를 보유 하는 로컬 메모리에 공간이 있습니다. 데이터가 요청 되 면 Microsoft Jet 데이터베이스 엔진의 캐시 데이터를 먼저 확인 대신 더 많은 시간이 소모 하는 서버에서 가져오는 것입니다. 데이터 비 ODBC 데이터 원본에서 캐싱을 사용 하 여 효과가 없습니다 데이터 캐시에 저장 되지 않습니다.

인출 될 레코드 채울 캐시를 대기 하는 대신 명시적으로 채우면 됩니다 캐시 언제 든 지 호출 하 여는 `FillCache` 멤버 함수입니다. 이 때문에 캐시를 채우는 데는 더 빠른 방법이 `FillCache` 한 번에 하나씩 대신 한 번에 여러 레코드를 인출 합니다. 예를 들어, 레코드의 전체 화면 표시 되 면, 응용 프로그램 호출 있을 수 있습니다 `FillCache` 레코드의 다음 전체 화면을 가져올 수 있습니다.

레코드 집합 개체를 사용 하 여 액세스 하는 모든 ODBC 데이터베이스에는 로컬 캐시를 가질 수 있습니다. 캐시를 만들려면 원격 데이터 원본에서 레코드 집합 개체를 열고 다음 호출을 `SetCacheSize` 고 `SetCacheStart` 레코드 집합의 멤버 함수입니다. 경우 *lSize* 하 고 *lBookmark* 부분적으로 나 완전히 지정 된 범위 밖에 있는 범위를 만들고 `SetCacheSize` 및 `SetCacheStart`,이 범위를 벗어나는 레코드 집합의 부분을 무시 되 고 아닙니다 캐시에 로드 합니다. 경우 `FillCache` 요청 원격 데이터 원본에 보다 더 많은 레코드 유지, 나머지는 레코드는 인출 되 고 예외가 throw 되지 않습니다.

캐시에서 인출 된 레코드에는 다른 사용자가 원본 데이터에 동시에 변경 내용을 반영 하지 않습니다.

`FillCache` 아직 캐시 레코드만 인출 합니다. 캐시 된 모든 데이터의 업데이트를 적용 하려면 호출을 `SetCacheSize` 사용 하 여 멤버 함수는 *lSize* 매개 변수를 0으로 호출 `SetCacheSize` 사용 하 여 다시를 *lSize* 매개 변수는 캐시의 크기를 원래 요청 하 고 다음 호출 `FillCache`합니다.

관련된 내용은 DAO 도움말의 "FillCache 메서드" 항목을 참조 합니다.

##  <a name="find"></a>  CDaoRecordset::Find

비교 연산자를 사용 하 여 다이너셋 또는 스냅숏 형식 레코드 집합에서 특정 문자열을 찾아이 멤버 함수를 호출 합니다.

```
virtual BOOL Find(
    long lFindType,
    LPCTSTR lpszFilter);
```

### <a name="parameters"></a>매개 변수

*lFindType*<br/>
원하는 찾기 작업의 형식을 나타내는 값입니다. 가능한 값은 다음과 같습니다.

- AFX_DAO_NEXT 일치 하는 문자열의 다음 위치를 찾습니다.

- AFX_DAO_PREV 일치 하는 문자열의 이전 위치를 찾습니다.

- AFX_DAO_FIRST 일치 하는 문자열의 첫 번째 위치를 찾습니다.

- AFX_DAO_LAST 일치 하는 문자열의 마지막 위치를 찾습니다.

*lpszFilter*<br/>
문자열 식 (같은 **위치** 단어 없이 SQL 문의 절 **여기서**) 레코드를 찾는 데 사용 합니다. 예를 들어:

[!code-cpp[NVC_MFCDatabase#3](../../mfc/codesnippet/cpp/cdaorecordset-class_3.cpp)]

### <a name="return-value"></a>반환 값

그렇지 않은 0 일치 하는 레코드가 발견 하는 경우에 0이 아닙니다.

### <a name="remarks"></a>설명

먼저 다음을 찾을 수 있습니다 문자열의 이전 또는 마지막 인스턴스. `Find` 가상 함수를 재정의 하 고 고유한 구현을 추가할 수 있도록. `FindFirst`, `FindLast`, `FindNext`, 및 `FindPrev` 멤버 함수 호출을 `Find` 멤버 함수를 사용할 수 있도록 `Find` 모든 찾기 작업의 동작을 제어 합니다.

테이블 형식 레코드 집합에서 레코드를 찾으려고 호출을 [Seek](#seek) 멤버 함수입니다.

> [!TIP]
>  레코드에 있는 보다 효과적인 집합이 작을수록 `Find` 됩니다. 일반적으로 및 ODBC 데이터를 사용 하 여 특히 원하는 레코드만 검색 하는 새 쿼리를 작성 하는 것이 좋습니다.

관련된 정보에 대 한 항목을 DAO 도움말의 "FindFirst, FindLast FindNext, FindPrevious 메서드" 참조 합니다.

##  <a name="findfirst"></a>  CDaoRecordset::FindFirst

지정 된 조건과 일치 하는 첫 번째 레코드를 확인 하려면이 멤버 함수를 호출 합니다.

```
BOOL FindFirst(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>매개 변수

*lpszFilter*<br/>
문자열 식 (같은 **위치** 단어 없이 SQL 문의 절 **여기서**) 레코드를 찾는 데 사용 합니다.

### <a name="return-value"></a>반환 값

그렇지 않은 0 일치 하는 레코드가 발견 하는 경우에 0이 아닙니다.

### <a name="remarks"></a>설명

`FindFirst` 멤버 함수는 레코드 집합의 시작 부분에서 검색 및 레코드 집합의 끝에 검색을 시작 합니다.

레코드 (뿐 아니라 특정 조건에 맞는)를 검색에 이동 작업 중 하나를 사용 하 여 레코드 간을 이동할 모두 포함 하려면. 테이블 형식 레코드 집합에서 레코드를 찾으려고 호출을 `Seek` 멤버 함수입니다.

현재 레코드 포인터 아직 결정 되지 조건과 일치 하는 레코드를 찾으면 및 `FindFirst` 0을 반환 합니다. 레코드 집합, 조건을 충족 하는 둘 이상의 레코드를 포함 하는 경우 `FindFirst` 첫 번째 발생을 찾습니다 `FindNext` 다음 항목과 등을 찾습니다.

> [!CAUTION]
>  현재 레코드를 편집 하는 경우 사용할 호출 하 여 변경 내용을 저장 해야 합니다 `Update` 다른 레코드로 이동 하기 전에 멤버 함수입니다. 다른 레코드를 업데이트 하지 않고 이동 하는 경우 변경 내용을 경고 없이 손실 됩니다.

`Find` 멤버 함수는 다음 표에 지정 된 방향 및 위치에서 검색 합니다.

|찾기 작업|시작|검색 방향|
|---------------------|-----------|----------------------|
|`FindFirst`|레코드 집합 시작|레코드 집합의 끝|
|`FindLast`|레코드 집합의 끝|레코드 집합 시작|
|`FindNext`|현재 레코드|레코드 집합의 끝|
|`FindPrevious`|현재 레코드|레코드 집합 시작|

> [!NOTE]
>  호출 하는 경우 `FindLast`, Microsoft Jet 데이터베이스 엔진 이미 수행 하지 않은 경우 검색을 시작 하기 전에 레코드 집합 완전히 채웁니다. 첫 번째 검색은 후속 검색 보다 더 오래 걸릴 수 있습니다.

그러나 찾기 작업 중 하나를 사용 하 여 같지 않습니다 호출 하는 것 `MoveFirst` 또는 `MoveNext`,는 간단히 첫 번째 또는 다음 레코드를 현재 조건을 지정 하지 않고 있습니다. 이동 작업을 사용 하 여 찾기 작업을 수행할 수 있습니다.

찾기 작업을 사용 하는 경우 다음을 염두에 두십시오.

- 경우 `Find` 반환 0이 아닌 경우 현재 레코드가 정의 되어 있지 않습니다. 이 경우에 현재 레코드 포인터 유효한 레코드에 다시 배치 해야 합니다.

- 앞 으로만 이동 가능한 스크롤 스냅숏 형식 레코드 집합을 사용 하 여 찾기 작업을 사용할 수 없습니다.

- 미국 날짜 형식 (월-일-연도)를 사용 해야 Microsoft Jet 데이터베이스 엔진; (미국) 버전을 사용 하지 않는 경우에 날짜를 포함 하는 필드를 검색할 때 그렇지 않으면 일치 하는 레코드 없을 수 있습니다.

- ODBC 데이터베이스 및 큰 다이너셋에서 작업할 때 특히 큰 레코드 집합으로 작업할 경우 찾기 작업을 사용 하는 느린를 발견할 수 있습니다. SQL 쿼리를 사용 하 여 성능을 향상 시킬 수 있습니다 사용 하 여 사용자 지정 **ORDERBY** 또는 **여기서** 절, 쿼리 매개 변수 또는 `CDaoQuerydef` 인덱싱된 특정 레코드를 검색 하는 개체입니다.

관련된 정보에 대 한 항목을 DAO 도움말의 "FindFirst, FindLast FindNext, FindPrevious 메서드" 참조 합니다.

##  <a name="findlast"></a>  CDaoRecordset::FindLast

지정 된 조건과 일치 하는 마지막 레코드를 확인 하려면이 멤버 함수를 호출 합니다.

```
BOOL FindLast(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>매개 변수

*lpszFilter*<br/>
문자열 식 (같은 **위치** 단어 없이 SQL 문의 절 **여기서**) 레코드를 찾는 데 사용 합니다.

### <a name="return-value"></a>반환 값

그렇지 않은 0 일치 하는 레코드가 발견 하는 경우에 0이 아닙니다.

### <a name="remarks"></a>설명

`FindLast` 멤버 함수는 레코드 집합의 끝에 검색 및 레코드 집합의 시작 부분 쪽으로 뒤로 검색을 시작 합니다.

레코드 (뿐 아니라 특정 조건에 맞는)를 검색에 이동 작업 중 하나를 사용 하 여 레코드 간을 이동할 모두 포함 하려면. 테이블 형식 레코드 집합에서 레코드를 찾으려고 호출을 `Seek` 멤버 함수입니다.

현재 레코드 포인터 아직 결정 되지 조건과 일치 하는 레코드를 찾으면 및 `FindLast` 0을 반환 합니다. 레코드 집합, 조건을 충족 하는 둘 이상의 레코드를 포함 하는 경우 `FindFirst` 첫 번째 발생을 찾습니다 `FindNext` 첫 번째 발생 후에 다음 항목을 찾습니다.

> [!CAUTION]
>  현재 레코드를 편집 하는 경우 반드시 호출 하 여 변경 내용을 저장 합니다 `Update` 다른 레코드로 이동 하기 전에 멤버 함수입니다. 다른 레코드를 업데이트 하지 않고 이동 하는 경우 변경 내용을 경고 없이 손실 됩니다.

그러나 찾기 작업 중 하나를 사용 하 여 같지 않습니다 호출 하는 것 `MoveFirst` 또는 `MoveNext`,는 간단히 첫 번째 또는 다음 레코드를 현재 조건을 지정 하지 않고 있습니다. 이동 작업을 사용 하 여 찾기 작업을 수행할 수 있습니다.

찾기 작업을 사용 하는 경우 다음을 염두에 두십시오.

- 경우 `Find` 반환 0이 아닌 경우 현재 레코드가 정의 되어 있지 않습니다. 이 경우에 현재 레코드 포인터 유효한 레코드에 다시 배치 해야 합니다.

- 앞 으로만 이동 가능한 스크롤 스냅숏 형식 레코드 집합을 사용 하 여 찾기 작업을 사용할 수 없습니다.

- 미국 날짜 형식 (월-일-연도)를 사용 해야 Microsoft Jet 데이터베이스 엔진; (미국) 버전을 사용 하지 않는 경우에 날짜를 포함 하는 필드를 검색할 때 그렇지 않으면 일치 하는 레코드 없을 수 있습니다.

- ODBC 데이터베이스 및 큰 다이너셋에서 작업할 때 특히 큰 레코드 집합으로 작업할 경우 찾기 작업을 사용 하는 느린를 발견할 수 있습니다. SQL 쿼리를 사용 하 여 성능을 향상 시킬 수 있습니다 사용 하 여 사용자 지정 **ORDERBY** 또는 **여기서** 절, 쿼리 매개 변수 또는 `CDaoQuerydef` 인덱싱된 특정 레코드를 검색 하는 개체입니다.

관련된 정보에 대 한 항목을 DAO 도움말의 "FindFirst, FindLast FindNext, FindPrevious 메서드" 참조 합니다.

##  <a name="findnext"></a>  CDaoRecordset::FindNext

지정 된 조건과 일치 하는 다음 레코드를 확인 하려면이 멤버 함수를 호출 합니다.

```
BOOL FindNext(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>매개 변수

*lpszFilter*<br/>
문자열 식 (같은 **위치** 단어 없이 SQL 문의 절 **여기서**) 레코드를 찾는 데 사용 합니다.

### <a name="return-value"></a>반환 값

그렇지 않은 0 일치 하는 레코드가 발견 하는 경우에 0이 아닙니다.

### <a name="remarks"></a>설명

`FindNext` 멤버 함수는 현재 레코드에서 해당 검색을 시작 하 고 레코드 집합의 끝에 검색 합니다.

레코드 (뿐 아니라 특정 조건에 맞는)를 검색에 이동 작업 중 하나를 사용 하 여 레코드 간을 이동할 모두 포함 하려면. 테이블 형식 레코드 집합에서 레코드를 찾으려고 호출을 `Seek` 멤버 함수입니다.

현재 레코드 포인터 아직 결정 되지 조건과 일치 하는 레코드를 찾으면 및 `FindNext` 0을 반환 합니다. 레코드 집합, 조건을 충족 하는 둘 이상의 레코드를 포함 하는 경우 `FindFirst` 첫 번째 발생을 찾습니다 `FindNext` 다음 항목과 등을 찾습니다.

> [!CAUTION]
>  현재 레코드를 편집 하는 경우 반드시 호출 하 여 변경 내용을 저장 합니다 `Update` 다른 레코드로 이동 하기 전에 멤버 함수입니다. 다른 레코드를 업데이트 하지 않고 이동 하는 경우 변경 내용을 경고 없이 손실 됩니다.

그러나 찾기 작업 중 하나를 사용 하 여 같지 않습니다 호출 하는 것 `MoveFirst` 또는 `MoveNext`,는 간단히 첫 번째 또는 다음 레코드를 현재 조건을 지정 하지 않고 있습니다. 이동 작업을 사용 하 여 찾기 작업을 수행할 수 있습니다.

찾기 작업을 사용 하는 경우 다음을 염두에 두십시오.

- 경우 `Find` 반환 0이 아닌 경우 현재 레코드가 정의 되어 있지 않습니다. 이 경우에 현재 레코드 포인터 유효한 레코드에 다시 배치 해야 합니다.

- 앞 으로만 이동 가능한 스크롤 스냅숏 형식 레코드 집합을 사용 하 여 찾기 작업을 사용할 수 없습니다.

- 미국 날짜 형식 (월-일-연도)를 사용 해야 Microsoft Jet 데이터베이스 엔진; (미국) 버전을 사용 하지 않는 경우에 날짜를 포함 하는 필드를 검색할 때 그렇지 않으면 일치 하는 레코드 없을 수 있습니다.

- ODBC 데이터베이스 및 큰 다이너셋에서 작업할 때 특히 큰 레코드 집합으로 작업할 경우 찾기 작업을 사용 하는 느린를 발견할 수 있습니다. SQL 쿼리를 사용 하 여 성능을 향상 시킬 수 있습니다 사용 하 여 사용자 지정 **ORDERBY** 또는 **여기서** 절, 쿼리 매개 변수 또는 `CDaoQuerydef` 인덱싱된 특정 레코드를 검색 하는 개체입니다.

관련된 정보에 대 한 항목을 DAO 도움말의 "FindFirst, FindLast FindNext, FindPrevious 메서드" 참조 합니다.

##  <a name="findprev"></a>  CDaoRecordset::FindPrev

지정 된 조건과 일치 하는 이전 레코드를 확인 하려면이 멤버 함수를 호출 합니다.

```
BOOL FindPrev(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>매개 변수

*lpszFilter*<br/>
문자열 식 (같은 **위치** 단어 없이 SQL 문의 절 **여기서**) 레코드를 찾는 데 사용 합니다.

### <a name="return-value"></a>반환 값

그렇지 않은 0 일치 하는 레코드가 발견 하는 경우에 0이 아닙니다.

### <a name="remarks"></a>설명

`FindPrev` 멤버 함수는 현재 레코드에서 해당 검색을 시작 하 고 레코드 집합의 시작 부분 쪽으로 뒤로 검색 합니다.

레코드 (뿐 아니라 특정 조건에 맞는)를 검색에 이동 작업 중 하나를 사용 하 여 레코드 간을 이동할 모두 포함 하려면. 테이블 형식 레코드 집합에서 레코드를 찾으려고 호출을 `Seek` 멤버 함수입니다.

현재 레코드 포인터 아직 결정 되지 조건과 일치 하는 레코드를 찾으면 및 `FindPrev` 0을 반환 합니다. 레코드 집합, 조건을 충족 하는 둘 이상의 레코드를 포함 하는 경우 `FindFirst` 첫 번째 발생을 찾습니다 `FindNext` 다음 항목과 등을 찾습니다.

> [!CAUTION]
>  현재 레코드를 편집 하는 경우 반드시 호출 하 여 변경 내용을 저장 합니다 `Update` 다른 레코드로 이동 하기 전에 멤버 함수입니다. 다른 레코드를 업데이트 하지 않고 이동 하는 경우 변경 내용을 경고 없이 손실 됩니다.

그러나 찾기 작업 중 하나를 사용 하 여 같지 않습니다 호출 하는 것 `MoveFirst` 또는 `MoveNext`,는 간단히 첫 번째 또는 다음 레코드를 현재 조건을 지정 하지 않고 있습니다. 이동 작업을 사용 하 여 찾기 작업을 수행할 수 있습니다.

찾기 작업을 사용 하는 경우 다음을 염두에 두십시오.

- 경우 `Find` 반환 0이 아닌 경우 현재 레코드가 정의 되어 있지 않습니다. 이 경우에 현재 레코드 포인터 유효한 레코드에 다시 배치 해야 합니다.

- 앞 으로만 이동 가능한 스크롤 스냅숏 형식 레코드 집합을 사용 하 여 찾기 작업을 사용할 수 없습니다.

- 미국 날짜 형식 (월-일-연도)를 사용 해야 Microsoft Jet 데이터베이스 엔진; (미국) 버전을 사용 하지 않는 경우에 날짜를 포함 하는 필드를 검색할 때 그렇지 않으면 일치 하는 레코드 없을 수 있습니다.

- ODBC 데이터베이스 및 큰 다이너셋에서 작업할 때 특히 큰 레코드 집합으로 작업할 경우 찾기 작업을 사용 하는 느린를 발견할 수 있습니다. SQL 쿼리를 사용 하 여 성능을 향상 시킬 수 있습니다 사용 하 여 사용자 지정 **ORDERBY** 또는 **여기서** 절, 쿼리 매개 변수 또는 `CDaoQuerydef` 인덱싱된 특정 레코드를 검색 하는 개체입니다.

관련된 정보에 대 한 항목을 DAO 도움말의 "FindFirst, FindLast FindNext, FindPrevious 메서드" 참조 합니다.

##  <a name="getabsoluteposition"></a>  CDaoRecordset::GetAbsolutePosition

레코드 집합 개체의 현재 레코드의 레코드 수를 반환합니다.

```
long GetAbsolutePosition();
```

### <a name="return-value"></a>반환 값

정수 0에서 레코드 집합의 레코드 수입니다. 레코드 집합의 현재 레코드의 서 수 위치에 해당합니다.

### <a name="remarks"></a>설명

기본 DAO 개체의 AbsolutePosition 속성 값이 0부터 시작 합니다. 0으로 설정 된 레코드 집합의 첫 번째 레코드를 가리킵니다. 호출 하 여 레코드 집합의 레코드의 개수를 확인할 수 있습니다 [GetRecordCount](#getrecordcount)합니다. 호출 `GetRecordCount` 수를 결정 하는 모든 레코드에 액세스 해야 하므로 약간의 시간이 걸릴 수 있습니다.

레코드에서 레코드가 없는 경우로, 현재 레코드가 없을 경우 1이 반환 됩니다. 현재 레코드를 삭제 하면 AbsolutePosition 속성 값을를 정의 하지 않으면 및 MFC 참조 하는 경우 예외를 throw 합니다. 다이너셋 형식 레코드 집합에 대해 새 레코드 시퀀스의 끝에 추가 됩니다.

> [!NOTE]
>  이 속성을 서로게이트 레코드 수로 사용할 수 없습니다. 책갈피는 여전히 유지 하 고 지정된 된 위치를 반환 하는 권장된 방법을 이며 모든 유형의 레코드 집합 개체에서 현재 레코드의 위치에 대 한 유일한 방법입니다. 특히 지정된 된 레코드의 위치 앞에 레코드가 삭제 되 면 변경 합니다. 지정된 된 레코드 되어 동일한 절대 위치 사용 하 여 SQL 문을 사용 하 여 생성 되지 않는 한 레코드 집합 내의 개별 레코드의 순서가 보장 되지 않으므로 레코드 집합을 다시 만들면 다시 확신할 수 없습니다 이기도 한  **ORDERBY** 절.

> [!NOTE]
>  이 멤버 함수는 다이너셋 형식 및 스냅숏 형식 레코드 집합에 대해서만 유효 합니다.

관련된 정보 DAO 도움말의 "AbsolutePosition 속성" 항목을 참조 하세요.

##  <a name="getbookmark"></a>  CDaoRecordset::GetBookmark

특정 레코드에 책갈피 값을 가져오려면이 함수를 호출 합니다.

```
COleVariant GetBookmark();
```

### <a name="return-value"></a>반환 값

현재 레코드에서 책갈피를 나타내는 값을 반환 합니다.

### <a name="remarks"></a>설명

레코드 집합 개체를 만들거나 열 때 각 레코드에 이미 고유 책갈피가 지 원하는 경우. 호출 `CanBookmark` 레코드 집합 책갈피를 지원 하는지 확인 합니다.

책갈피의 값을 할당 하 여 현재 레코드에 대 한 책갈피를 저장할 수는 `COleVariant` 개체입니다. 언제 든 지 다른 레코드로 이동 하 고 나면, 해당 레코드를 신속 하 게 반환 하려면 호출 `SetBookmark` 의 값에 해당 하는 매개 변수를 사용 하 여 `COleVariant` 개체입니다.

> [!NOTE]
>  호출 [Requery](#requery) DAO 책갈피를 변경 합니다.

관련된 내용은 DAO 도움말의 "Bookmark 속성" 항목을 참조 합니다.

##  <a name="getcachesize"></a>  CDaoRecordset::GetCacheSize

캐시 된 레코드 번호를 가져오려면이 함수를 호출 합니다.

```
long GetCacheSize();
```

### <a name="return-value"></a>반환 값

데이터를 ODBC 데이터 원본에서 로컬 캐시를 포함 하는 다이너셋 형식 레코드 집합에서 레코드의 수를 지정 하는 값입니다.

### <a name="remarks"></a>설명

데이터 캐싱 다이너셋 형식 레코드 집합 개체를 통해 원격 서버에서 데이터를 검색 하는 응용 프로그램의 성능을 향상 시킵니다. 캐시에서 데이터를 다시 요청 되는 응용 프로그램이 실행 되는 동안 서버에서 가장 최근에 검색 된 데이터를 보유 하는 로컬 메모리에 공간이 있습니다. 데이터가 요청 되 면 Microsoft Jet 데이터베이스 엔진의 캐시는 요청 된 데이터를 먼저 확인 더 많은 시간을 사용 하는 서버에서 검색 하는 대신 합니다. ODBC 데이터 원본에서 제공 되지 않는 데이터 캐시에 저장 되지 않습니다.

모든 ODBC 데이터 원본에 연결 된 테이블을 같은 로컬 캐시를 가질 수 있습니다.

관련된 내용은 DAO 도움말의 "CacheSize CacheStart 속성" 항목을 참조 합니다.

##  <a name="getcachestart"></a>  CDaoRecordset::GetCacheStart

캐시할 레코드 집합의 첫 번째 레코드의 책갈피 값을 가져오려면이 함수를 호출 합니다.

```
COleVariant GetCacheStart();
```

### <a name="return-value"></a>반환 값

`COleVariant` 캐시할 레코드 집합의 첫 번째 레코드의 책갈피를 지정 하는 합니다.

### <a name="remarks"></a>설명

Microsoft Jet 데이터베이스 엔진 캐시에서 캐시 범위 내에서 레코드를 요청 하 고 서버에서 캐시 범위 외부의 레코드를 요청 합니다.

> [!NOTE]
>  캐시에서 검색 된 레코드에는 다른 사용자가 원본 데이터에 동시에 변경 내용을 반영 하지 않습니다.

관련된 내용은 DAO 도움말의 "CacheSize CacheStart 속성" 항목을 참조 합니다.

##  <a name="getcurrentindex"></a>  CDaoRecordset::GetCurrentIndex

인덱싱된 테이블 형식에서 사용 중인 현재 인덱스를 확인 하려면이 멤버 함수 호출 `CDaoRecordset` 개체입니다.

```
CString GetCurrentIndex();
```

### <a name="return-value"></a>반환 값

`CString` 사용 하 여 테이블 형식으로 레코드 집합의 현재 인덱스의 이름을 포함 합니다. 설정 된 인덱스가 없는 경우 빈 문자열을 반환 합니다.

### <a name="remarks"></a>설명

이 인덱스는 테이블 형식 레코드 집합에서 레코드를 정렬 하기 위한 기본 이며 사용 되는 [Seek](#seek) 멤버 함수 레코드를 찾을 수 있습니다.

A `CDaoRecordset` 개체 둘 이상의 인덱스가 있을 수 있지만 한 번에 하나의 인덱스를 사용할 수 있습니다 (하지만 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) 개체에 정의 된 인덱스를 여러 개 있을 수 있습니다).

관련된 정보 항목 "인덱스 개체" 및 "현재 인덱스" DAO 도움말의 정의 참조 하세요.

##  <a name="getdatecreated"></a>  CDaoRecordset::GetDateCreated

기본 테이블을 만든 시간과 날짜를 검색 하려면이 멤버 함수를 호출 합니다.

```
COleDateTime GetDateCreated();
```

### <a name="return-value"></a>반환 값

A [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 기본 테이블을 만든 시간과 날짜를 포함 하는 개체입니다.

### <a name="remarks"></a>설명

날짜 및 시간 설정에는 기본 테이블을 만든 컴퓨터에서 파생 됩니다.

관련된 내용은 DAO 도움말의 "DateCreated LastUpdated 속성" 항목을 참조 합니다.

##  <a name="getdatelastupdated"></a>  CDaoRecordset::GetDateLastUpdated

스키마 마지막으로 업데이트 된 시간과 날짜를 검색 하려면이 멤버 함수를 호출 합니다.

```
COleDateTime GetDateLastUpdated();
```

### <a name="return-value"></a>반환 값

A [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 기본 테이블 구조 (스키마) 마지막으로 업데이트 된 시간과 날짜를 포함 하는 개체입니다.

### <a name="remarks"></a>설명

날짜 및 시간 설정 (스키마) 기본 테이블 구조를 마지막으로 업데이트 된 컴퓨터에서 파생 됩니다.

관련된 내용은 DAO 도움말의 "DateCreated LastUpdated 속성" 항목을 참조 합니다.

##  <a name="getdefaultdbname"></a>  CDaoRecordset::GetDefaultDBName

이 레코드 집합에 대 한 데이터베이스의 이름을 확인 하려면이 멤버 함수를 호출 합니다.

```
virtual CString GetDefaultDBName();
```

### <a name="return-value"></a>반환 값

`CString` 이 레코드 집합 파생 되는 데이터베이스의 이름과 경로 포함 하는 합니다.

### <a name="remarks"></a>설명

레코드 집합에 대 한 포인터 없이 만들어질 경우는 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md),이 경로 사용 하는 레코드 집합에서 기본 데이터베이스 열을 합니다. 기본적으로이 함수는 빈 문자열을 반환합니다. 클래스 마법사에서 새 레코드 집합을 파생 하는 경우 `CDaoRecordset`,이 함수를 만듭니다.

다음 예제에서는 이중 백슬래시 (\\\\) 문자열에서 요구 된 대로 올바르게 해석 될 문자열입니다.

[!code-cpp[NVC_MFCDatabase#4](../../mfc/codesnippet/cpp/cdaorecordset-class_4.cpp)]

##  <a name="getdefaultsql"></a>  CDaoRecordset::GetDefaultSQL

프레임 워크는 레코드 집합의 기반이 되는 기본 SQL 문을 하려면이 멤버 함수를 호출 합니다.

```
virtual CString GetDefaultSQL();
```

### <a name="return-value"></a>반환 값

`CString` 기본 SQL 문을 포함 하는 합니다.

### <a name="remarks"></a>설명

테이블 이름 또는 SQL 때문일 **선택** 문입니다.

직접 정의할 있습니다 기본 SQL 문을 클래스 마법사를 사용 하 여 레코드 집합 클래스를 선언 하 여 및 classwizard 함께 사용 하면에 대 한이 작업을 수행 합니다.

Null SQL 문자열을 전달 하는 경우 [열려](#open), 레코드 집합에 대 한 테이블 이름 또는 SQL을 확인 하려면이 함수 호출 됩니다.

##  <a name="geteditmode"></a>  CDaoRecordset::GetEditMode

다음 값 중 하나인 편집의 상태를 확인 하려면이 멤버 함수를 호출 합니다.

```
short GetEditMode();
```

### <a name="return-value"></a>반환 값

현재 레코드의 편집 상태를 나타내는 값을 반환 합니다.

### <a name="remarks"></a>설명

|값|설명|
|-----------|-----------------|
|`dbEditNone`|편집 작업이 진행 중입니다.|
|`dbEditInProgress`|`Edit` 가 호출 되었습니다.|
|`dbEditAdd`|`AddNew` 가 호출 되었습니다.|

관련된 정보 DAO 도움말의 "EditMode 속성" 항목을 참조 하세요.

##  <a name="getfieldcount"></a>  CDaoRecordset::GetFieldCount

필드 (열) 레코드 집합에 정의 된 횟수를 검색 하려면이 멤버 함수를 호출 합니다.

```
short GetFieldCount();
```

### <a name="return-value"></a>반환 값

레코드 집합의 필드 수입니다.

### <a name="remarks"></a>설명

관련된 내용은 DAO 도움말에서 "Count 속성" 항목을 참조 합니다.

##  <a name="getfieldinfo"></a>  CDaoRecordset::GetFieldInfo

레코드 집합의 필드에 대 한 정보를 가져오려면이 함수를 호출 합니다.

```
void GetFieldInfo(
    int nIndex,
    CDaoFieldInfo& fieldinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

void GetFieldInfo(
    LPCTSTR lpszName,
    CDaoFieldInfo& fieldinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
인덱스에서 조회에 대 한 레코드 집합의 필드 컬렉션의 미리 정의 된 필드의 0부터 시작 하는 인덱스입니다.

*fieldinfo*<br/>
에 대 한 참조를 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) 구조입니다.

*dwInfoOptions*<br/>
검색할 레코드 집합에 대 한 정보를 지정 하는 옵션입니다. 사용 가능한 옵션은 어떤 문제를 일으킬 있습니다를 반환 하는 함수 함께 나열 됩니다. 최상의 성능을 위해 필요한 정보 수준의 검색 합니다.

- `AFX_DAO_PRIMARY_INFO` (기본값) 이름, 유형, 크기, 특성

- `AFX_DAO_SECONDARY_INFO` 기본 정보, plus: 서 수 위치에 필요한 순서, 외부 이름, 원본 필드, 원본 테이블 데이터 정렬, 길이가 0 허용

- `AFX_DAO_ALL_INFO` 기본 및 보조 정보 및: 기본 값, 유효성 검사 규칙 유효성 검사 텍스트

*lpszName*<br/>
@FSHO2@필드의 이름입니다.

### <a name="remarks"></a>설명

한 버전의 함수를 사용 하면 인덱스에서 필드를 조회할 수 있습니다. 다른 버전을 통해 필드 이름으로 조회할 수 있습니다.

반환 되는 정보에 대 한 참조를 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) 구조입니다. 이 구조에 대 한 설명에서 위에 나열 된 정보 항목에 해당 하는 멤버가 *dwInfoOptions*합니다. 한 수준 정보를 요청으로 모든 이전 수준에 대 한 정보를 얻을 수 있습니다.

관련된 정보 DAO 도움말의 "특성 속성" 항목을 참조 하세요.

##  <a name="getfieldvalue"></a>  CDaoRecordset::GetFieldValue

레코드 집합에서 데이터를 검색 하려면이 멤버 함수를 호출 합니다.

```
virtual void GetFieldValue(
    LPCTSTR lpszName,
    COleVariant& varValue);

virtual void GetFieldValue(
    int nIndex,
    COleVariant& varValue);

virtual COleVariant GetFieldValue(LPCTSTR lpszName);
virtual COleVariant GetFieldValue(int nIndex);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
필드의 이름을 포함 하는 문자열에 대 한 포인터입니다.

*varValue*<br/>
에 대 한 참조를 `COleVariant` 필드의 값을 저장 하는 개체입니다.

*nIndex*<br/>
인덱스에서 조회에 대 한 레코드 집합의 필드 컬렉션의 필드는 0부터 시작 하는 인덱스입니다.

### <a name="return-value"></a>반환 값

두 버전의 `GetFieldValue` 반환 하는 값을 반환 된 [COleVariant](../../mfc/reference/colevariant-class.md) 필드의 값이 포함 된 개체입니다.

### <a name="remarks"></a>설명

필드 이름 또는 서 수 위치로 조회할 수 있습니다.

> [!NOTE]
>  것이 더 효율적이 멤버 함수는 버전 중 하나를 호출 하는 `COleVariant` 매개 변수를 반환 하는 버전을 호출 하는 대신 개체 참조가 `COleVariant` 개체. 이 함수의 두 번째 버전은 이전 버전과 호환성을 위해 유지 됩니다.

사용 하 여 `GetFieldValue` 하 고 [SetFieldValue](#setfieldvalue) 실행된 시간 보다는 정적으로 사용 하 여 바인딩 열 필드를 동적으로 바인딩할 합니다 [DoFieldExchange](#dofieldexchange) 메커니즘입니다.

`GetFieldValue` 및 `DoFieldExchange` 성능 향상을 위해 메커니즘을 결합할 수 있습니다. 예를 들어, 사용 하 여 `GetFieldValue` 주문형만 해야 하는 값을 검색할 인터페이스의 "추가 정보" 단추에 대 한 호출이 할당 하 합니다.

관련된 정보에 대 한 "필드 개체" 속성과 "값" DAO 도움말의 항목을 참조 합니다.

##  <a name="getindexcount"></a>  CDaoRecordset::GetIndexCount

테이블 형식 레코드 집합에서 사용할 수 있는 인덱스의 수를 확인 하려면이 멤버 함수를 호출 합니다.

```
short GetIndexCount();
```

### <a name="return-value"></a>반환 값

테이블 형식 레코드 집합의 인덱스 수입니다.

### <a name="remarks"></a>설명

`GetIndexCount` 레코드 집합의 모든 인덱스를 통해 반복 하는 데 유용 합니다. 이 위해 사용 하 여 `GetIndexCount` 와 함께에서 [GetIndexInfo](#getindexinfo)합니다. 다이너셋 형식 또는 스냅숏 형식 레코드 집합에서이 멤버 함수를 호출 하는 경우 MFC 예외를 throw 합니다.

관련된 정보 DAO 도움말의 "특성 속성" 항목을 참조 하세요.

##  <a name="getindexinfo"></a>  CDaoRecordset::GetIndexInfo

다양 한 종류의 레코드 집합을 기본 기본 테이블에 정의 된 인덱스에 대 한 정보를 가져오려면이 함수를 호출 합니다.

```
void GetIndexInfo(
    int nIndex,
    CDaoIndexInfo& indexinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

void GetIndexInfo(
    LPCTSTR lpszName,
    CDaoIndexInfo& indexinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
숫자 위치에 따라 조회에 대 한 테이블의 인덱스 컬렉션의 0부터 시작 하는 인덱스입니다.

*indexinfo*<br/>
에 대 한 참조를 [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) 구조입니다.

*dwInfoOptions*<br/>
검색할 인덱스에 대 한 정보를 지정 하는 옵션입니다. 사용 가능한 옵션은 어떤 문제를 일으킬 있습니다를 반환 하는 함수 함께 나열 됩니다. 최상의 성능을 위해 필요한 정보 수준의 검색 합니다.

- `AFX_DAO_PRIMARY_INFO` (기본값) 이름, 필드 정보 필드

- `AFX_DAO_SECONDARY_INFO` 기본 정보, plus: 기본, 고유, 클러스터형 IgnoreNulls, 필요한 경우 외부

- `AFX_DAO_ALL_INFO` 기본 및 보조 정보 및: Distinct Count

*lpszName*<br/>
이름별 조회에 대 한 인덱스 개체의 이름에 대 한 포인터입니다.

### <a name="remarks"></a>설명

한 버전의 함수를 사용 하면 컬렉션의 위치를 기준으로 인덱스를 찾을 수 있습니다. 다른 버전을 통해 이름으로 인덱스를 조회할 수 있습니다.

반환 되는 정보에 대 한 참조를 [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) 구조입니다. 이 구조에 대 한 설명에서 위에 나열 된 정보 항목에 해당 하는 멤버가 *dwInfoOptions*합니다. 한 수준 정보를 요청으로 모든 이전 수준에 대 한 정보를 얻을 수 있습니다.

관련된 정보 DAO 도움말의 "특성 속성" 항목을 참조 하세요.

##  <a name="getlastmodifiedbookmark"></a>  CDaoRecordset::GetLastModifiedBookmark

가장 최근에 추가 되거나 업데이트 된 레코드의 책갈피를 검색 하려면이 멤버 함수를 호출 합니다.

```
COleVariant GetLastModifiedBookmark();
```

### <a name="return-value"></a>반환 값

`COleVariant` 추가 되거나 변경 된 레코드 포함 가장 최근에 나타내는 책갈피입니다.

### <a name="remarks"></a>설명

레코드 집합 개체를 만들거나 열 때 각 레코드에 이미 고유 책갈피가 지 원하는 경우. 호출 [GetBookmark](#getbookmark) 를 레코드 집합에서 책갈피를 지원 하는지 확인 합니다. 레코드 집합에 책갈피를 지원 하지 않는 경우는 `CDaoException` throw 됩니다.

레코드를 추가 하는 경우 레코드 집합의 끝에 표시 되 고 현재 레코드가 아닙니다. 현재 새 레코드를 확인, 호출 `GetLastModifiedBookmark` 호출 `SetBookmark` 새로 추가 된 레코드를 반환 합니다.

관련된 내용은 DAO 도움말의 "LastModified Property" 항목을 참조 합니다.

##  <a name="getlockingmode"></a>  CDaoRecordset::GetLockingMode

레코드 집합에 대 한 잠금 유형을 결정 하려면이 멤버 함수를 호출 합니다.

```
BOOL GetLockingMode();
```

### <a name="return-value"></a>반환 값

잠금 유형을 비관적, 0이 아닌 레코드 낙관적 잠금에 대 한 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

호출 하는 즉시 잠긴 경우 비관적 잠금이 적용 됩니다, 편집 하는 레코드를 포함 하는 데이터 페이지의 [편집](#edit) 멤버 함수입니다. 호출할 때 페이지 잠금이 아닙니다 합니다 [업데이트](#update) 또는 [닫기](#close) 멤버 함수 또는 이동 또는 찾기 작업 중 하나입니다.

레코드를 포함 하는 데이터 페이지를 사용 하 여 레코드를 업데이트 하는 동안에 잠겨 경우 낙관적 잠금 적용 되는 `Update` 멤버 함수입니다.

ODBC 데이터 원본으로 작업할 경우에 잠금 모드는 낙관적 항상입니다.

관련된 정보에 대 한 "LockEdits 속성" 및 "잠금 동작에서 다중 사용자 응용 프로그램" DAO 도움말의 항목을 참조 합니다.

##  <a name="getname"></a>  CDaoRecordset::GetName

레코드 집합의 이름을 검색 하려면이 멤버 함수를 호출 합니다.

```
CString GetName();
```

### <a name="return-value"></a>반환 값

`CString` 레코드 집합의 이름을 포함 합니다.

### <a name="remarks"></a>설명

레코드 집합의 이름을 문자로 시작 해야 하며 40 자까지 포함할 수 있습니다. 숫자를 포함할 수 있습니다 및 밑줄 문자 이지만 문장 부호 또는 공백을 포함할 수 없습니다.

관련된 내용은 DAO 도움말의 "Name 속성" 항목을 참조 합니다.

##  <a name="getparamvalue"></a>  CDaoRecordset::GetParamValue

기본 DAOParameter 개체에 저장 된 지정된 된 매개 변수의 현재 값을 검색 하려면이 멤버 함수를 호출 합니다.

```
virtual COleVariant GetParamValue(int nIndex);
virtual COleVariant GetParamValue(LPCTSTR lpszName);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
내부 DAOParameter 개체에 있는 숫자 위치 매개 변수입니다.

*lpszName*<br/>
매개 변수 값을 변경할의 이름입니다.

### <a name="return-value"></a>반환 값

클래스의 개체 [COleVariant](../../mfc/reference/colevariant-class.md) 매개 변수의 값이 들어 있는입니다.

### <a name="remarks"></a>설명

매개 변수 이름 또는 컬렉션에 있는 숫자 위치를 기준으로 액세스할 수 있습니다.

관련된 내용은 DAO 도움말에서 "매개 변수 개체" 항목을 참조 합니다.

##  <a name="getpercentposition"></a>  CDaoRecordset::GetPercentPosition

호출 하는 경우 다이너셋 형식 또는 스냅숏 형식 레코드 집합을 사용 하 여 작업 하는 경우 `GetPercentPosition` 레코드를 완전 하 게 채운 하기 전에 이동의 양을 호출 하 여 표시 된 대로 액세스 하는 레코드의 수를 기준으로 [GetRecordCount](#getrecordcount).

```
float GetPercentPosition();
```

### <a name="return-value"></a>반환 값

레코드 집합에서 레코드의 비율을 기준으로 레코드 집합 개체의 현재 레코드의 대략적인 위치를 나타내는 0과 100 사이의 숫자입니다.

### <a name="remarks"></a>설명

이동할 수 있습니다 마지막 레코드를 호출 하 여 [MoveLast](#movelast) 에 완료 되지만 모든 레코드 집합의 채우기 걸릴 수 있습니다 상당한 양의 시간입니다.

호출할 수 있습니다 `GetPercentPosition` 레코드 집합 개체의 모든 세 가지 종류 인덱스가 없는 테이블을 포함 합니다. 그러나 호출할 수 없습니다 `GetPercentPosition` 정방향 스크롤 스냅숏 또는 외부 데이터베이스에 대해 통과 쿼리에서 연 레코드 집합입니다. 현재 레코드가 없는 경우 그 현재 레코드를 삭제 한 `CDaoException` throw 됩니다.

관련된 내용은 DAO 도움말의 "PercentPosition Property" 항목을 참조 합니다.

##  <a name="getrecordcount"></a>  CDaoRecordset::GetRecordCount

레코드 집합에서 레코드 개수에 액세스를 확인 하려면이 멤버 함수를 호출 합니다.

```
long GetRecordCount();
```

### <a name="return-value"></a>반환 값

레코드 집합 개체에 액세스 하는 레코드의 수를 반환 합니다.

### <a name="remarks"></a>설명

`GetRecordCount` 모든 레코드에 액세스 될 때까지 얼마나 많은 레코드 다이너셋 형식 또는 스냅숏 형식 레코드 집합에 포함 된을 나타내지 않습니다. 이 멤버 함수 호출에는 완료 하는 시간이 많이 걸릴 수 있습니다.

마지막 레코드에 액세스 한 후 반환 값은 레코드 집합에서 삭제 되지 않은 레코드의 총 수를 나타냅니다. 액세스할 마지막 레코드를 강제로 호출 합니다 `MoveLast` 또는 `FindLast` 레코드 집합에 대 한 멤버 함수입니다. 또한 여 쿼리에서 반환 될 레코드의 대략적인 수를 확인 하려면 SQL 개수를 사용할 수 있습니다.

다이너셋 형식 레코드 집합의 반환 값에 대 한 레코드를 삭제 하는 응용 프로그램으로 `GetRecordCount` 감소 합니다. 그러나 다른 사용자가 삭제 된 레코드에서 반영 되지 않습니다 `GetRecordCount` 까지 현재 레코드 삭제 된 레코드에 배치 됩니다. Record count에 영향을 주는 트랜잭션을 실행 하 고 트랜잭션을 롤백할 경우 `GetRecordCount` 나머지 레코드의 실제 수를 반영 되지 것입니다.

변수의 `GetRecordCount` 스냅숏 형식 레코드 집합에서 영향을 받지 기본 테이블이 변경 합니다.

변수의 `GetRecordCount` 테이블 형식에서 레코드 집합 테이블의 레코드의 대략적인 수를 반영 하 고는 영향을 받는 즉시 테이블 레코드 추가 및 삭제 합니다.

레코드가 없는 레코드 집합 값이 0 반환합니다. 연결 된 테이블 또는 ODBC 데이터베이스를 사용 하 여 작업할 때 `GetRecordCount` 항상-1이 반환 됩니다. 호출을 `Requery` 멤버 함수는 레코드 집합에서 값을 다시 설정 `GetRecordCount` 것 처럼 쿼리 다시 실행 합니다.

관련된 정보 DAO 도움말의 "RecordCount 속성" 항목을 참조 하세요.

##  <a name="getsql"></a>  CDaoRecordset::GetSQL

이 멤버 함수는 열린 경우 레코드 집합의 레코드를 선택 하는 데 사용 된 SQL 문이를 호출 합니다.

```
CString GetSQL() const;
```

### <a name="return-value"></a>반환 값

`CString` SQL 문이 들어 있는입니다.

### <a name="remarks"></a>설명

일반적으로 SQL 됩니다 **선택** 문입니다.

반환한 문자열 `GetSQL` 일반적으로 다른 모든 문자열에서 레코드 집합에 전달 했습니다 합니다 *lpszSQL* 매개 변수를를 [열기](#open) 멤버 함수입니다. 레코드 집합을 전달 하는 내용에 따라 전체 SQL 문을 생성 하기 때문에 이것이 `Open`클래스 마법사를 사용 하 여 지정 된 고 수 있는에 지정 하는 [m_strFilter](#m_strfilter) 및 [m_strSort](#m_strsort) 데이터 멤버입니다.

> [!NOTE]
>  이 멤버 함수를 호출한 후에 호출 `Open`합니다.

관련된 내용은 DAO 도움말의 "SQL Property" 항목을 참조 합니다.

##  <a name="gettype"></a>  CDaoRecordset::GetType

레코드 집합 개체의 형식을 결정 하는 레코드 집합을 연 후이 함수를 호출 합니다.

```
short GetType();
```

### <a name="return-value"></a>반환 값

레코드 집합의 형식을 나타내는 다음 값 중 하나입니다.

- `dbOpenTable` 테이블 형식 레코드 집합

- `dbOpenDynaset` 다이너셋 형식 레코드 집합

- `dbOpenSnapshot` 스냅숏 형식 레코드 집합

### <a name="remarks"></a>설명

관련된 내용은 DAO 도움말의 "형식 속성" 항목을 참조 합니다.

##  <a name="getvalidationrule"></a>  CDaoRecordset::GetValidationRule

데이터 유효성을 검사 하는 데 사용 하는 규칙을 확인 하려면이 멤버 함수를 호출 합니다.

```
CString GetValidationRule();
```

### <a name="return-value"></a>반환 값

`CString` 변경 되거나 테이블에 추가 되는 레코드의 데이터의 유효성을 검사 하는 값을 포함 하는 개체입니다.

### <a name="remarks"></a>설명

이 규칙은 텍스트를 기반으로 하 고 기본 테이블에 변경 될 때마다 적용 됩니다. 데이터가 유효 하지 않은 경우 MFC 예외를 throw 합니다. 반환 된 오류 메시지를 지정 하는 경우 기본 필드 개체의 유효성 검사 텍스트 속성의 텍스트 또는 내부 필드 개체의 유효성 검사 규칙 속성에 지정 된 식의 텍스트입니다. 호출할 수 있습니다 [GetValidationText](#getvalidationtext) 오류 메시지의 텍스트를 가져오는 데 있습니다.

예를 들어, 해당 월의 일을 해야 하는 레코드의 필드 규칙이 있을 수 유효성 검사와 같은 "일 BETWEEN 1에서 31입니다."

관련된 내용은 DAO 도움말의 "ValidationRule Property" 항목을 참조 합니다.

##  <a name="getvalidationtext"></a>  CDaoRecordset::GetValidationText

기본 필드 개체의 유효성 검사 텍스트 속성의 텍스트를 검색 하려면이 멤버 함수를 호출 합니다.

```
CString GetValidationText();
```

### <a name="return-value"></a>반환 값

`CString` 필드의 값은 기본 필드 개체의 유효성 검사 규칙을 충족 하지 않으면 표시 되는 메시지의 텍스트를 포함 하는 개체입니다.

### <a name="remarks"></a>설명

관련된 정보 DAO 도움말의 "유효성 검사 텍스트 속성" 항목을 참조 하세요.

##  <a name="isbof"></a>  CDaoRecordset::IsBOF

레코드 집합의 첫 번째 레코드 앞를 벗어났는지 여부를 자세한 레코드를 레코드에서 스크롤하면 전에이 멤버 함수를 호출 합니다.

```
BOOL IsBOF() const;
```

### <a name="return-value"></a>반환 값

레코드 집합에 레코드가 없는 경우 또는 첫 번째 레코드; 앞 뒤로 스크롤 하는 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

호출할 수도 있습니다 `IsBOF` 와 함께 `IsEOF` 레코드 집합 레코드를 포함 하거나 비어 있는지 확인 하려면. 호출 직후 `Open`레코드 집합 레코드가 없는 경우 `IsBOF` 0이 아닌 값을 반환 합니다. 첫 번째 레코드는 현재 레코드에 하나 이상의 레코드가 있는 레코드 집합을 열 때 및 `IsBOF` 0을 반환 합니다.

첫 번째 레코드에는 현재 레코드가 고 호출 하는 경우 `MovePrev`, `IsBOF` 이후에 0이 아닌 반환 됩니다. 하는 경우 `IsBOF` 0이 아닌 값을 반환 하 고 호출 `MovePrev`, 예외가 throw 됩니다. 경우 `IsBOF` 반환 되는 0이 아닌 경우 현재 레코드가 정의 되어 있지 및 현재 레코드에 필요한 모든 작업은 예외가 발생 합니다.

특정 메서드에 미치는 `IsBOF` 고 `IsEOF` 설정:

- 호출 `Open*` 내부적으로 사용 하면 첫 번째 레코드는 레코드 집합의 현재 레코드를 호출 하 여 `MoveFirst`입니다. 따라서 호출 `Open` 레코드 원인의 빈 집합을 온 `IsBOF` 및 `IsEOF` 0이 아닌 값을 반환 합니다. (실패 한 동작에 대 한 다음 표를 참조 하세요 `MoveFirst` 또는 `MoveLast` 호출 합니다.)

- 레코드를 제대로 찾는 이동 작업의 모든 발생 둘 다 `IsBOF` 고 `IsEOF` 0을 반환 합니다.

- `AddNew` 호출 뒤에 `Update` 성공적으로 새 레코드를 삽입 하는 호출 하면 `IsBOF` 0 이지만 경우에만 반환할 `IsEOF` 0이 아닌 이미 합니다. 상태의 `IsEOF` 는 항상 그대로 유지 합니다. Microsoft Jet 데이터베이스 엔진에 의해 정의 된 대로 빈 레코드 집합의 현재 레코드 포인터 이므로 파일의 끝에 현재 레코드 뒤에 새 레코드 삽입 됩니다.

- 모든 `Delete` 호출 하 여 레코드 집합에서 남아 있는 마지막 레코드를 제거 하는 경우에 변경 되지 것입니다 변수의 `IsBOF` 또는 `IsEOF`합니다.

이 테이블의 다른 조합을 사용 하 여 허용 하는 이동 작업을 보여 줍니다 `IsBOF` /  `IsEOF`합니다.

||MoveFirst, MoveLast|MovePrev,<br /><br /> Move < 0|0 이동|MoveNext<br /><br /> > 0 이동|
|------|-------------------------|-----------------------------|------------|-----------------------------|
|`IsBOF`=nonzero,<br /><br /> `IsEOF`=0|Allowed|예외|예외|Allowed|
|`IsBOF`=0,<br /><br /> `IsEOF`=nonzero|Allowed|Allowed|예외|예외|
|둘 다 0이 아닌 값|예외|예외|예외|예외|
|둘 다 0|Allowed|Allowed|Allowed|Allowed|

이동 작업 허용을 작업 레코드를 제대로 찾는 것은 아닙니다. 단순히 지정된 이동 작업을 수행 하려고 허용 되 고 예외가 생성 되지 것입니다 나타냅니다. 값을 `IsBOF` 및 `IsEOF` 멤버 함수는 이동을 시도 결과로 변경 될 수 있습니다.

레코드의 값에 배치 하지 마십시오는 이동 작업의 효과 `IsBOF` 및 `IsEOF` 설정은 다음 표에 표시 됩니다.

||IsBOF|IsEOF|
|------|-----------|-----------|
|`MoveFirst`, `MoveLast`|0이 아닌 값|0이 아닌 값|
|`Move` 0|변경 안 함|변경 안 함|
|`MovePrev`, `Move` < 0|0이 아닌 값|변경 안 함|
|`MoveNext`, `Move` > 0|변경 안 함|0이 아닌 값|

관련된 내용은 항목을 참조 하십시오. "BOF, EOF 속성" DAO 도움말입니다.

##  <a name="isdeleted"></a>  CDaoRecordset::IsDeleted

현재 레코드 삭제 되었는지 여부를 결정 하는이 멤버 함수를 호출 합니다.

```
BOOL IsDeleted() const;
```

### <a name="return-value"></a>반환 값

레코드 집합은 삭제 된 레코드에 배치 되 면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

레코드 스크롤 하는 경우 및 `IsDeleted` 스크롤해야 다른 레코드가 다른 레코드 집합 작업을 수행 하기 전에 다음 (0이 아닌) 경우 TRUE를 반환 합니다.

> [!NOTE]
>  스냅숏 또는 테이블 형식 레코드 집합의 레코드에 대 한 삭제 된 상태를 확인할 필요가 없습니다. 호출 하지 않아도 됩니다 스냅숏에서 레코드를 삭제할 수 없으므로, `IsDeleted`합니다. 테이블 형식 레코드 집합에 대해 삭제 된 레코드는 레코드 집합에서 실제로 제거 됩니다. 레코드가 다른 레코드 집합 또는 사용자, 다른 사용자가 삭제 된 후 다시 해당 레코드를 스크롤할 수 없습니다. 따라서 호출 하지 않아도 됩니다 `IsDeleted`합니다.

다이너셋에서 레코드를 삭제 하면 레코드 집합에서 제거 되 고 해당 레코드를 다시 스크롤할 수 없습니다. 그러나 레코드 다이너셋 삭제 됩니다 또는 다른 사용자가 동일한 테이블을 기반으로 하는 다른 레코드 집합에서 `IsDeleted` 는 나중에 해당 레코드를 스크롤할 때 TRUE를 반환 합니다.

관련된 정보에 대 한 "Delete 메서드", "LastModified 속성" 및 "EditMode 속성" DAO 도움말의 항목을 참조 합니다.

##  <a name="iseof"></a>  CDaoRecordset::IsEOF

레코드에서 레코드 집합의 마지막 레코드 범위를 벗어났는지 여부를 자세한 레코드를 스크롤할 때이 멤버 함수를 호출 합니다.

```
BOOL IsEOF() const;
```

### <a name="return-value"></a>반환 값

레코드 집합에는 레코드가 없으며 스크롤 마지막 레코드; 했는지 아니면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

호출할 수도 있습니다 `IsEOF` 레코드 집합 레코드를 포함 하거나 비어 있는지 확인 하려면. 호출 직후 `Open`레코드 집합 레코드가 없는 경우 `IsEOF` 0이 아닌 값을 반환 합니다. 첫 번째 레코드는 현재 레코드에 하나 이상의 레코드가 있는 레코드 집합을 열 때 및 `IsEOF` 0을 반환 합니다.

마지막 레코드 인지 현재 레코드를 호출할 때 `MoveNext`, `IsEOF` 이후에 0이 아닌 반환 됩니다. 하는 경우 `IsEOF` 0이 아닌 값을 반환 하 고 호출 `MoveNext`, 예외가 throw 됩니다. 경우 `IsEOF` 반환 되는 0이 아닌 경우 현재 레코드가 정의 되어 있지 및 현재 레코드에 필요한 모든 작업은 예외가 발생 합니다.

특정 메서드에 미치는 `IsBOF` 고 `IsEOF` 설정:

- 호출 `Open` 내부적으로 사용 하면 첫 번째 레코드는 레코드 집합의 현재 레코드를 호출 하 여 `MoveFirst`입니다. 따라서 호출 `Open` 레코드 원인의 빈 집합을 온 `IsBOF` 및 `IsEOF` 0이 아닌 값을 반환 합니다. (실패 한 동작에 대 한 아래 표 참조 `MoveFirst` 호출 합니다.)

- 레코드를 제대로 찾는 이동 작업의 모든 발생 둘 다 `IsBOF` 고 `IsEOF` 0을 반환 합니다.

- `AddNew` 호출 뒤에 `Update` 성공적으로 새 레코드를 삽입 하는 호출 하면 `IsBOF` 0 이지만 경우에만 반환할 `IsEOF` 0이 아닌 이미 합니다. 상태의 `IsEOF` 는 항상 그대로 유지 합니다. Microsoft Jet 데이터베이스 엔진에 의해 정의 된 대로 빈 레코드 집합의 현재 레코드 포인터 이므로 파일의 끝에 현재 레코드 뒤에 새 레코드 삽입 됩니다.

- 모든 `Delete` 호출 하 여 레코드 집합에서 남아 있는 마지막 레코드를 제거 하는 경우에 변경 되지 것입니다 변수의 `IsBOF` 또는 `IsEOF`합니다.

이 테이블의 다른 조합을 사용 하 여 허용 하는 이동 작업을 보여 줍니다 `IsBOF` /  `IsEOF`합니다.

||MoveFirst, MoveLast|MovePrev,<br /><br /> Move < 0|0 이동|MoveNext<br /><br /> > 0 이동|
|------|-------------------------|-----------------------------|------------|-----------------------------|
|`IsBOF`=nonzero,<br /><br /> `IsEOF`=0|Allowed|예외|예외|Allowed|
|`IsBOF`=0,<br /><br /> `IsEOF`=nonzero|Allowed|Allowed|예외|예외|
|둘 다 0이 아닌 값|예외|예외|예외|예외|
|둘 다 0|Allowed|Allowed|Allowed|Allowed|

이동 작업 허용을 작업 레코드를 제대로 찾는 것은 아닙니다. 단순히 지정된 이동 작업을 수행 하려고 허용 되 고 예외가 생성 되지 것입니다 나타냅니다. 값을 `IsBOF` 및 `IsEOF` 멤버 함수는 이동을 시도 결과로 변경 될 수 있습니다.

레코드의 값에 배치 하지 마십시오는 이동 작업의 효과 `IsBOF` 및 `IsEOF` 설정은 다음 표에 표시 됩니다.

||IsBOF|IsEOF|
|------|-----------|-----------|
|`MoveFirst`, `MoveLast`|0이 아닌 값|0이 아닌 값|
|`Move` 0|변경 안 함|변경 안 함|
|`MovePrev`, `Move` < 0|0이 아닌 값|변경 안 함|
|`MoveNext`, `Move` > 0|변경 안 함|0이 아닌 값|

관련된 내용은 항목을 참조 하십시오. "BOF, EOF 속성" DAO 도움말입니다.

##  <a name="isfielddirty"></a>  CDaoRecordset::IsFieldDirty

다이너셋의 지정 된 필드 데이터 멤버 "더티"로 플래그가 지정 되었는지 여부를 확인 하려면 (변경)이 멤버 함수를 호출 합니다.

```
BOOL IsFieldDirty(void* pv);
```

### <a name="parameters"></a>매개 변수

*pv*<br/>
필드 데이터 멤버를 확인 하거나 NULL로 커밋되지 않은 데이터 필드를 확인 하려는 상태에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

지정 된 필드 데이터 멤버; 커밋되지 않은 것으로 플래그가 지정 되어 있으면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

모든 더티 필드 데이터 멤버의 데이터를 전송할 레코드를 데이터 원본에 현재 레코드를 호출 하 여 업데이트 되 면 합니다 `Update` 멤버 함수 `CDaoRecordset` (호출 `Edit` 또는 `AddNew`). 이러한 지식을 바탕으로 작업을 수행할 추가, 같은 스레드에 필드 데이터 멤버는 데이터 소스에 기록 되지 것입니다 있도록 열을 표시 합니다.

`IsFieldDirty` 통해 구현 됩니다 `DoFieldExchange`합니다.

##  <a name="isfieldnull"></a>  CDaoRecordset::IsFieldNull

지정 된 필드 데이터 멤버는 레코드 집합의 Null로 플래그가 지정 되었는지 여부를 결정 하는이 멤버 함수를 호출 합니다.

```
BOOL IsFieldNull(void* pv);
```

### <a name="parameters"></a>매개 변수

*pv*<br/>
필드 데이터 멤버를 확인 하거나 Null 필드 중 하나 인지 확인 하려면 NULL 상태에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

지정 된 필드 데이터 멤버를 Null로 플래그가 지정 되어 있으면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

(데이터베이스 용어에서 "값 필요"는 의미를 Null 및 NULL에과 같지 않습니다 C++입니다.) 필드 데이터 멤버를 Null로 플래그가 지정 되 면 값은 현재 레코드의 열으로 해석 됩니다.

> [!NOTE]
>  사용 하 여 특정 상황에서 `IsFieldNull` 비효율적일 수 있습니다, 다음 코드 예제와 같이:

[!code-cpp[NVC_MFCDatabase#5](../../mfc/codesnippet/cpp/cdaorecordset-class_5.cpp)]

> [!NOTE]
>  파생 하지 않고 동적 레코드 바인딩의 경우 사용 중인 경우 `CDaoRecordset`, 예제에 표시 된 대로 VT_NULL을 사용 해야 합니다.

##  <a name="isfieldnullable"></a>  CDaoRecordset::IsFieldNullable

지정 된 필드 데이터 멤버 "null"이 허용 되는지 확인 하려면 (설정할 수 있습니다에 Null 값이 멤버 함수 호출 C++ NULL은 Null 이며 데이터베이스 용어에서 의미와 동일 하지 않습니다 "값 필요").

```
BOOL IsFieldNullable(void* pv);
```

### <a name="parameters"></a>매개 변수

*pv*<br/>
필드 데이터 멤버를 확인 하거나 Null 필드 중 하나 인지 확인 하려면 NULL 상태에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

지정 된 필드 데이터 멤버에 Null 만들 수 있으면 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

Null이 될 수 없는 필드 값이 있어야 합니다. 데이터 원본 추가 또는 업데이트를 취소 하는 필드를 추가 하거나 레코드를 업데이트 하는 경우에 Null로 설정 하려고 하면 및 `Update` 예외가 throw 됩니다. 호출 하면 예외가 발생 `Update`문의할 때가 아니라, `SetFieldNull`합니다.

##  <a name="isopen"></a>  CDaoRecordset::IsOpen

레코드 집합 열려 있는지 확인 하려면이 멤버 함수를 호출 합니다.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>반환 값

0이 아닌 경우 레코드 집합 개체의 `Open` 또는 `Requery` 멤버 함수가 이전에 호출 된 및 레코드 집합 닫히지 않은; 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

##  <a name="m_bcheckcachefordirtyfields"></a>  CDaoRecordset::m_bCheckCacheForDirtyFields

여부를 캐시 된 필드는 자동으로 표시 더티 (변경)를 나타내는 플래그를 포함 및 Null입니다.

### <a name="remarks"></a>설명

플래그의 기본값은 TRUE입니다. 이 데이터 멤버의 설정이 전체 이중 버퍼링 메커니즘을 제어합니다. 플래그를 TRUE로 설정 하면 DFX 메커니즘을 사용 하 여 필드 별로 캐싱을 해제할 수 있습니다. 플래그를 FALSE로 설정 하면 호출 해야 합니다 `SetFieldDirty` 고 `SetFieldNull` 직접.

이 데이터 멤버를 호출 하기 전에 설정 `Open`합니다. 이 메커니즘은 주로 사용 하기 쉬운 됩니다. 성능 변경 내용을 적용할 때 이중 버퍼링 필드 때문에 느려질 수 있습니다.

##  <a name="m_nfields"></a>  CDaoRecordset::m_nFields

레코드 집합 클래스의 필드 데이터 멤버의 수 및 데이터 원본에서 레코드 집합에서 선택한 열 수가 포함 됩니다.

### <a name="remarks"></a>설명

레코드 집합 클래스의 생성자를 초기화 해야 `m_nFields` 정적으로 바인딩된 필드의 정확한 수를 사용 하 여 합니다. 클래스 마법사 클래스를 선언할 때 레코드 집합을 사용 하는 경우이 초기화를 작성 합니다. 작성할 수도 있습니다 것 수동으로.

프레임 워크는이 번호를 사용 하 여 필드 데이터 멤버와 데이터 소스에서 현재 레코드의 해당 열 간의 상호 작용을 관리 합니다.

> [!NOTE]
>  이 숫자에 등록 하는 출력 열 수가 같아야 `DoFieldExchange` 를 호출한 후 `SetFieldType` 매개 변수를 사용 하 여 `CDaoFieldExchange::outputColumn`입니다.

동적으로의 방식으로 열을 바인딩할 수 있습니다 `CDaoRecordset::GetFieldValue` 고 `CDaoRecordset::SetFieldValue`입니다. 이렇게 하면 필요가 없습니다의 횟수를 증가 시킬 `m_nFields` 의 호출 DFX 함수의 수를 반영 하도록 프로그램 `DoFieldExchange` 멤버 함수입니다.

##  <a name="m_nparams"></a>  CDaoRecordset::m_nParams

레코드 집합 클래스에서 매개 변수 데이터 멤버 수가 포함-레코드 집합의 쿼리와 함께 전달 되는 매개 변수 개수입니다.

### <a name="remarks"></a>설명

레코드 집합 클래스는 매개 변수 데이터 멤버에 경우에 클래스의 생성자는 초기화 해야 합니다 *m_nParams* 올바른 번호를 사용 하 여 합니다. 변수의 *m_nParams* 기본값은 0입니다. 매개 변수 데이터 멤버를 추가 하는 경우-수동으로 수행 해야 하는-매개 변수의 수를 반영 하도록 클래스 생성자에서 초기화를 수동으로 추가 해야 합니다 (수가 이상이 이어야 합니다 "의 자리 표시자에 *m_strFilter*  나 *m_strSort* 문자열)입니다.

프레임 워크는 레코드 집합의 쿼리를 매개 변수화 하는 경우이 번호를 사용 합니다.

> [!NOTE]
>  이 숫자에 등록 하는 "params"의 수와 일치 해야 `DoFieldExchange` 를 호출한 후 `SetFieldType` 매개 변수를 사용 하 여 `CFieldExchange::param`입니다.

관련된 내용은 DAO 도움말에서 "매개 변수 개체" 항목을 참조 합니다.

##  <a name="m_pdaorecordset"></a>  CDaoRecordset::m_pDAORecordset

DAO 레코드 집합 개체 기본 OLE 인터페이스에 대 한 포인터를 `CDaoRecordset` 개체입니다.

### <a name="remarks"></a>설명

DAO 인터페이스를 직접 액세스 해야 하는 경우에이 포인터를 사용 합니다.

관련된 내용은 DAO 도움말에서 "레코드 집합 개체" 항목을 참조 합니다.

##  <a name="m_pdatabase"></a>  CDaoRecordset::m_pDatabase

에 대 한 포인터를 포함 합니다 `CDaoDatabase` 는 레코드 집합을 데이터 원본에 연결 하는 개체입니다.

### <a name="remarks"></a>설명

이 변수는 두 가지 방법으로 설정 됩니다. 포인터에 전달 되는 일반적으로 `CDaoDatabase` 레코드 집합 개체를 생성 하는 경우 개체입니다. 대신 NULL을 전달 하는 경우 `CDaoRecordset` 만듭니다는 `CDaoDatabase` 개체를 엽니다. 두 경우 모두 `CDaoRecordset` 이 변수에 대 한 포인터를 저장 합니다.

일반적으로 직접 필요가에 저장 된 포인터를 사용 하 여 `m_pDatabase`입니다. 사용자 고유의 확장을 작성 하는 경우 `CDaoRecordset`에 포인터를 사용 해야 하는 반면 합니다. 예를 들어 해야 포인터 throw 되는 경우 사용자 고유의 `CDaoException`(s).

관련된 내용은 DAO 도움말의 "데이터베이스 개체" 항목을 참조 합니다.

##  <a name="m_strfilter"></a>  CDaoRecordset::m_strFilter

생성 하는 데 사용 되는 문자열을 포함 합니다 **여기서** SQL 문의 절.

### <a name="remarks"></a>설명

예약 된 단어는 포함 되지 않습니다 **여기서** 레코드 집합을 필터링 합니다. 이 데이터 멤버를 사용 하 여 테이블 형식 레코드 집합에 적용 됩니다. 사용 `m_strFilter` 를 사용 하 여 레코드 집합을 열 때 아무 효과가 `CDaoQueryDef` 포인터입니다.

미국 날짜 형식 (월-일-연도)를 사용 하 여 Microsoft Jet 데이터베이스 엔진; (미국) 버전을 사용 하지 않는 경우에 날짜를 포함 하는 필드를 필터링 하는 경우 이 고, 그렇지 예상한 대로 데이터를 필터링 하지 않을 수 있습니다.

관련된 정보 DAO 도움말의 "필터 속성" 항목을 참조 하세요.

##  <a name="m_strsort"></a>  CDaoRecordset::m_strSort

포함 된 문자열을 포함 합니다 **ORDERBY** 예약어 없이 SQL 문의 절 **ORDERBY**합니다.

### <a name="remarks"></a>설명

다이너셋 및 스냅숏 형식 레코드 집합 개체에서 정렬할 수 있습니다.

테이블 형식 레코드 집합 개체를 정렬할 수 없습니다. 테이블 형식 레코드 집합의 정렬 순서를 확인 하려면 호출 [SetCurrentIndex](#setcurrentindex)합니다.

사용 *m_strSort* 사용 하 여 레코드 집합을 열 때 아무 효과가 `CDaoQueryDef` 포인터입니다.

관련된 내용은 DAO 도움말에서 "Sort 속성" 항목을 참조 합니다.

##  <a name="move"></a>  CDaoRecordset::Move

레코드 집합을 배치 하려면이 멤버 함수 호출 *lRows* 현재 레코드의 레코드입니다.

```
virtual void Move(long lRows);
```

### <a name="parameters"></a>매개 변수

*lRows*<br/>
앞으로 또는 뒤로 이동 하는 레코드의 수입니다. 양수 값을 레코드 집합의 끝에 다가가 앞으로 이동합니다. 음수 값 시작 부분을 향해 뒤로 이동합니다.

### <a name="remarks"></a>설명

앞으로 또는 뒤로 이동할 수 있습니다. `Move( 1 )` 동일 `MoveNext`, 및 `Move( -1 )` 동일 `MovePrev`합니다.

> [!CAUTION]
>  호출 된 `Move` 함수 레코드 집합에 레코드가 없는 경우 예외를 throw 합니다. 일반적으로 둘 다 호출 `IsBOF` 고 `IsEOF` 레코드 집합에 레코드가 있는지 확인 하는 이동 작업 전에 합니다. 호출한 후 `Open` 나 `Requery`를 호출 `IsBOF` 또는 `IsEOF`합니다.

> [!NOTE]
>  시작 또는 레코드 집합의 끝을 지난 스크롤 하는 경우 ( `IsBOF` 또는 `IsEOF` 0이 아닌 반환), 호출 `Move` throw를 `CDaoException`입니다.

> [!NOTE]
>  중 하나를 호출 하는 경우는 `Move` 함수 중에 현재 레코드는 업데이트 되거나 추가, 업데이트 경고 없이 손실 됩니다.

호출 하는 경우 `Move` 정방향 스크롤 스냅숏에 *lRows* 책갈피는 허용 되지 않으므로 진행할 수 있습니다만 및 매개 변수는 양의 정수 여야 합니다.

첫 번째, 마지막에 있도록 다음 또는 이전 레코드는 레코드 집합에서 현재 레코드를 호출 합니다 `MoveFirst`, `MoveLast`를 `MoveNext`, 또는 `MovePrev` 멤버 함수입니다.

관련된 정보에 대 한 "Move 메서드" 항목을 참조 하 고 "MoveFirst, MoveLast, MoveNext, MovePrevious 메서드" DAO 도움말입니다.

##  <a name="movefirst"></a>  CDaoRecordset::MoveFirst

(해당 되는 경우) 레코드 집합의 첫 번째 레코드를 확인 하려면이 멤버 함수를 호출 하면 현재 레코드입니다.

```
void MoveFirst();
```

### <a name="remarks"></a>설명

호출할 필요가 없습니다 `MoveFirst` 레코드 집합을 연 후에 즉시 합니다. 이때 첫 번째 레코드 (해당 되는 경우) 자동으로 현재 레코드가 됩니다.

> [!CAUTION]
>  호출 된 `Move` 함수 레코드 집합에 레코드가 없는 경우 예외를 throw 합니다. 일반적으로 둘 다 호출 `IsBOF` 고 `IsEOF` 레코드 집합에 레코드가 있는지 확인 하는 이동 작업 전에 합니다. 호출한 후 `Open` 나 `Requery`를 호출 `IsBOF` 또는 `IsEOF`합니다.

> [!NOTE]
>  중 하나를 호출 하는 경우는 `Move` 함수 중에 현재 레코드는 업데이트 되거나 추가, 업데이트 경고 없이 손실 됩니다.

사용 된 `Move` 조건을 적용 하지 않고 레코드에서를 이동 하는 함수입니다. 다이너셋 형식 또는 특정 조건을 만족 하는 스냅숏 형식 레코드 집합 개체에서 레코드를 찾을 수는 찾기 작업을 사용 합니다. 테이블 형식 레코드 집합 개체에서 레코드를 찾으려고 호출 `Seek`합니다.

레코드는 테이블 형식 레코드 집합을 참조 하는 경우 이동 테이블의 현재 인덱스를 따릅니다. 기본 DAO 개체의 인덱스 속성을 사용 하 여 현재 인덱스를 설정할 수 있습니다. 현재 인덱스를 설정 하지 않으면 반환 된 레코드의 순서가 정의 되지 않습니다.

호출 하는 경우 `MoveLast` SQL 쿼리 또는 쿼리 정의에 따라 레코드 집합 개체에서 쿼리가 완료 될 때까지 강제 되 고 레코드 집합 개체를 완벽 하 게으로 채워집니다.

호출할 수 없습니다는 `MoveFirst` 또는 `MovePrev` 정방향 스크롤 스냅숏 사용 하 여 멤버 함수입니다.

현재 위치 기록 레코드 집합 개체에서 특정 개의 레코드를 앞으로 또는 뒤로 이동할 호출 `Move`합니다.

관련된 정보에 대 한 "Move 메서드" 항목을 참조 하 고 "MoveFirst, MoveLast, MoveNext, MovePrevious 메서드" DAO 도움말입니다.

##  <a name="movelast"></a>  CDaoRecordset::MoveLast

현재 레코드를 레코드 집합의 마지막 레코드 (해당 되는 경우)를 확인 하려면이 멤버 함수를 호출 합니다.

```
void MoveLast();
```

### <a name="remarks"></a>설명

> [!CAUTION]
>  호출 된 `Move` 함수 레코드 집합에 레코드가 없는 경우 예외를 throw 합니다. 일반적으로 둘 다 호출 `IsBOF` 고 `IsEOF` 레코드 집합에 레코드가 있는지 확인 하는 이동 작업 전에 합니다. 호출한 후 `Open` 나 `Requery`를 호출 `IsBOF` 또는 `IsEOF`합니다.

> [!NOTE]
>  중 하나를 호출 하는 경우는 `Move` 함수 중에 현재 레코드는 업데이트 되거나 추가, 업데이트 경고 없이 손실 됩니다.

사용 된 `Move` 조건을 적용 하지 않고 레코드에서를 이동 하는 함수입니다. 다이너셋 형식 또는 특정 조건을 만족 하는 스냅숏 형식 레코드 집합 개체에서 레코드를 찾을 수는 찾기 작업을 사용 합니다. 테이블 형식 레코드 집합 개체에서 레코드를 찾으려고 호출 `Seek`합니다.

레코드는 테이블 형식 레코드 집합을 참조 하는 경우 이동 테이블의 현재 인덱스를 따릅니다. 기본 DAO 개체의 인덱스 속성을 사용 하 여 현재 인덱스를 설정할 수 있습니다. 현재 인덱스를 설정 하지 않으면 반환 된 레코드의 순서가 정의 되지 않습니다.

호출 하는 경우 `MoveLast` SQL 쿼리 또는 쿼리 정의에 따라 레코드 집합 개체에서 쿼리가 완료 될 때까지 강제 되 고 레코드 집합 개체를 완벽 하 게으로 채워집니다.

현재 위치 기록 레코드 집합 개체에서 특정 개의 레코드를 앞으로 또는 뒤로 이동할 호출 `Move`합니다.

관련된 정보에 대 한 "Move 메서드" 항목을 참조 하 고 "MoveFirst, MoveLast, MoveNext, MovePrevious 메서드" DAO 도움말입니다.

##  <a name="movenext"></a>  CDaoRecordset::MoveNext

현재 레코드를 레코드 집합의 다음 레코드를 확인 하려면이 멤버 함수를 호출 합니다.

```
void MoveNext();
```

### <a name="remarks"></a>설명

호출 하는 것이 좋습니다. `IsBOF` 이전 레코드로 이동 하기 전에 합니다. 에 대 한 호출 `MovePrev` 시킵니다를 `CDaoException` 경우 `IsBOF` 0이 아닌 경우 첫 번째 레코드 앞 이미 스크롤 또는 레코드가 레코드 집합에서 선택 된 있는지를 나타내는 반환 합니다.

> [!CAUTION]
>  호출 된 `Move` 함수 레코드 집합에 레코드가 없는 경우 예외를 throw 합니다. 일반적으로 둘 다 호출 `IsBOF` 고 `IsEOF` 레코드 집합에 레코드가 있는지 확인 하는 이동 작업 전에 합니다. 호출한 후 `Open` 나 `Requery`를 호출 `IsBOF` 또는 `IsEOF`합니다.

> [!NOTE]
>  중 하나를 호출 하는 경우는 `Move` 함수 중에 현재 레코드는 업데이트 되거나 추가, 업데이트 경고 없이 손실 됩니다.

사용 된 `Move` 조건을 적용 하지 않고 레코드에서를 이동 하는 함수입니다. 다이너셋 형식 또는 특정 조건을 만족 하는 스냅숏 형식 레코드 집합 개체에서 레코드를 찾을 수는 찾기 작업을 사용 합니다. 테이블 형식 레코드 집합 개체에서 레코드를 찾으려고 호출 `Seek`합니다.

레코드는 테이블 형식 레코드 집합을 참조 하는 경우 이동 테이블의 현재 인덱스를 따릅니다. 기본 DAO 개체의 인덱스 속성을 사용 하 여 현재 인덱스를 설정할 수 있습니다. 현재 인덱스를 설정 하지 않으면 반환 된 레코드의 순서가 정의 되지 않습니다.

현재 위치 기록 레코드 집합 개체에서 특정 개의 레코드를 앞으로 또는 뒤로 이동할 호출 `Move`합니다.

관련된 정보에 대 한 "Move 메서드" 항목을 참조 하 고 "MoveFirst, MoveLast, MoveNext, MovePrevious 메서드" DAO 도움말입니다.

##  <a name="moveprev"></a>  CDaoRecordset::MovePrev

현재 레코드를 레코드 집합에서 이전 레코드를 확인 하려면이 멤버 함수를 호출 합니다.

```
void MovePrev();
```

### <a name="remarks"></a>설명

호출 하는 것이 좋습니다. `IsBOF` 이전 레코드로 이동 하기 전에 합니다. 에 대 한 호출 `MovePrev` 시킵니다를 `CDaoException` 경우 `IsBOF` 0이 아닌 경우 첫 번째 레코드 앞 이미 스크롤 또는 레코드가 레코드 집합에서 선택 된 있는지를 나타내는 반환 합니다.

> [!CAUTION]
>  호출 된 `Move` 함수 레코드 집합에 레코드가 없는 경우 예외를 throw 합니다. 일반적으로 둘 다 호출 `IsBOF` 고 `IsEOF` 레코드 집합에 레코드가 있는지 확인 하는 이동 작업 전에 합니다. 호출한 후 `Open` 나 `Requery`를 호출 `IsBOF` 또는 `IsEOF`합니다.

> [!NOTE]
>  중 하나를 호출 하는 경우는 `Move` 함수 중에 현재 레코드는 업데이트 되거나 추가, 업데이트 경고 없이 손실 됩니다.

사용 된 `Move` 조건을 적용 하지 않고 레코드에서를 이동 하는 함수입니다. 다이너셋 형식 또는 특정 조건을 만족 하는 스냅숏 형식 레코드 집합 개체에서 레코드를 찾을 수는 찾기 작업을 사용 합니다. 테이블 형식 레코드 집합 개체에서 레코드를 찾으려고 호출 `Seek`합니다.

레코드는 테이블 형식 레코드 집합을 참조 하는 경우 이동 테이블의 현재 인덱스를 따릅니다. 기본 DAO 개체의 인덱스 속성을 사용 하 여 현재 인덱스를 설정할 수 있습니다. 현재 인덱스를 설정 하지 않으면 반환 된 레코드의 순서가 정의 되지 않습니다.

호출할 수 없습니다는 `MoveFirst` 또는 `MovePrev` 정방향 스크롤 스냅숏 사용 하 여 멤버 함수입니다.

현재 위치 기록 레코드 집합 개체에서 특정 개의 레코드를 앞으로 또는 뒤로 이동할 호출 `Move`합니다.

관련된 정보에 대 한 "Move 메서드" 항목을 참조 하 고 "MoveFirst, MoveLast, MoveNext, MovePrevious 메서드" DAO 도움말입니다.

##  <a name="open"></a>  CDaoRecordset::Open

레코드 집합에 대 한 레코드를 검색 하려면이 멤버 함수를 호출 해야 합니다.

```
virtual void Open(
    int nOpenType = AFX_DAO_USE_DEFAULT_TYPE,
    LPCTSTR lpszSQL = NULL,
    int nOptions = 0);

virtual void Open(
    CDaoTableDef* pTableDef,
    int nOpenType = dbOpenTable,
    int nOptions = 0);

virtual void Open(
    CDaoQueryDef* pQueryDef,
    int nOpenType = dbOpenDynaset,
    int nOptions = 0);
```

### <a name="parameters"></a>매개 변수

*nOpenType*<br/>
다음 값 중 하나입니다.

- `dbOpenDynaset` 양방향 스크롤 다이너셋 형식 레코드 집합입니다. 이 값이 기본값입니다.

- `dbOpenTable` 양방향 스크롤을 가진 테이블 형식 레코드 집합입니다.

- `dbOpenSnapshot` 양방향 스크롤 스냅숏 형식 레코드 집합입니다.

*lpszSQL*<br/>
다음 중 하나를 포함 하는 문자열 포인터.

- NULL 포인터입니다.

- 하나 이상의 테이블 정의 및/또는 쿼리 정의 (쉼표로 구분)의 이름입니다.

- SQL **선택** 문 (SQL를 사용 하 여 필요에 따라 **여기서** 하거나 **ORDERBY** 절).

- 통과 쿼리입니다.

*nOptions*<br/>
하나 이상의 아래 나열 된 옵션입니다. 기본값은 0입니다. 다음과 같은 값을 사용할 수 있습니다.

- `dbAppendOnly` 새 레코드 (다이너셋 형식 레코드 집합에만 해당)만 추가할 수 있습니다. 이 옵션은 문자 그대로 레코드 추가할 수만 있습니다. MFC ODBC 데이터베이스 클래스에는 레코드를 검색 하 고 추가 허용 하는 추가 전용 옵션이 있습니다.

- `dbForwardOnly` 레코드 집합은 정방향 스크롤 스냅숏입니다.

- `dbSeeChanges` 다른 사용자가 편집 하는 데이터를 변경 하는 경우 예외를 생성 합니다.

- `dbDenyWrite` 다른 사용자가 수정 하거나 레코드를 추가할 수 없습니다.

- `dbDenyRead` 다른 사용자 (테이블 형식 레코드 집합에만 해당) 레코드를 볼 수 없습니다.

- `dbReadOnly` 레코드; 볼 수 있습니다. 다른 사용자가 수정할 수 있습니다.

- `dbInconsistent` 일관성 없는 업데이트 (다이너셋 형식 레코드 집합에만 해당) 허용 됩니다.

- `dbConsistent` 일관 된 업데이트만 (다이너셋 형식 레코드 집합에만 해당)를 허용 됩니다.

> [!NOTE]
>  상수 `dbConsistent` 고 `dbInconsistent` 함께 사용할 수 없습니다. 하나를 사용할 수 있습니다 또는 다른 하나만 지정 된 인스턴스의 `Open`합니다.

*pTableDef*<br/>
에 대 한 포인터를 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) 개체입니다. 이 버전은 테이블 형식 레코드 집합에 대해서만 유효 합니다. 이 옵션을 사용 하는 경우는 `CDaoDatabase` 포인터를 생성 하는 데는 `CDaoRecordset` 사용 되지 않습니다; 테이블 정의 상주 하는 데이터베이스를 사용 하는 대신 합니다.

*pQueryDef*<br/>
에 대 한 포인터를 [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) 개체입니다. 이 버전 다이너셋 형식 및 스냅숏 형식 레코드 집합에 대해서만 유효 합니다. 이 옵션을 사용 하는 경우는 `CDaoDatabase` 포인터를 생성 하는 데는 `CDaoRecordset` 사용 되지 않습니다; 쿼리 정의가 상주 하는 데이터베이스를 사용 하는 대신 합니다.

### <a name="remarks"></a>설명

호출 하기 전에 `Open`, 레코드 집합 개체를 생성 해야 합니다. 다음과 같은 여러 가지 방법으로 이 작업을 수행할 수 있습니다.

- 레코드 집합 개체를 생성할 때 전달에 대 한 포인터를 `CDaoDatabase` 이미 열려 있는 개체입니다.

- 레코드 집합 개체를 생성할 때 전달에 대 한 포인터를 `CDaoDatabase` 열려 있지 않은 개체입니다. 레코드 집합이 열립니다는 `CDaoDatabase` 개체 이지만 닫지 것입니다 레코드 집합 개체를 닫을 때.

- 레코드 집합 개체를 생성 하는 경우 NULL 포인터를 전달 합니다. 레코드 집합 개체 호출 `GetDefaultDBName` Microsoft Access의 이름을 가져옵니다. MDB 파일을 열 수 있습니다. 레코드 집합을 연 다음을 `CDaoDatabase` 개체와 recordset 열려으로 열리지 유지 합니다. 호출 하는 경우 `Close` 레코드에는 `CDaoDatabase` 개체도 닫힙니다.

    > [!NOTE]
    >  레코드 집합이 열리면는 `CDaoDatabase` 개체, 비독점적 액세스를 사용 하 여 데이터 원본 열립니다.

버전용 `Open` 를 사용 하는 *lpszSQL* 매개 변수를 레코드 집합을 연 후 여러 방법 중 하나에서 레코드를 검색할 수 있습니다. DFX 함수에 첫 번째 옵션은 프로그램 `DoFieldExchange`합니다. 두 번째 옵션을 호출 하 여 동적 바인딩을 사용 하는 것은 `GetFieldValue` 멤버 함수입니다. 이러한 옵션은 개별적으로 또는 함께 구현할 수 있습니다. 전달할 SQL 문에서 직접 호출 해야 함께 사용할 경우 `Open`합니다.

두 번째 버전을 사용 하는 경우 `Open` 에 전달 하는 `CDaoTableDef` 개체를 결과 열을 통해 바인딩할 수 있게 됩니다 `DoFieldExchange` 및 DFX 메커니즘 및/또는 통해 동적으로 바인딩 `GetFieldValue`합니다.

> [!NOTE]
>  에서만 호출할 수 있습니다 `Open` 를 사용 하는 `CDaoTableDef` 테이블 형식 레코드 집합에 대 한 개체입니다.

세 번째 버전을 사용 하는 경우 `Open` 에 전달 하는 `CDaoQueryDef` 개체를 쿼리 실행 되 고, 결과 열을 통해 바인딩할 수 있게 됩니다 `DoFieldExchange` 및 DFX 메커니즘 및/또는 통해 동적으로 바인딩 `GetFieldValue`합니다.

> [!NOTE]
>  에서만 호출할 수 있습니다 `Open` 를 사용 하는 `CDaoQueryDef` 다이너셋 형식과 스냅숏 형식 레코드 집합에 대 한 개체입니다.

첫 번째 버전의 `Open` 를 사용 하는 `lpszSQL` 매개 변수를 레코드는 다음 표에 표시 된 선택된 기준에 따라 합니다.

|`lpszSQL` 매개 변수의 값|선택한 레코드에 따라 결정 됩니다.|예제|
|--------------------------------------|----------------------------------------|-------------|
|NULL|반환한 문자열 `GetDefaultSQL`합니다.||
|하나 이상의 테이블 정의 및/또는 쿼리 정의 이름을 포함 하는 쉼표로 구분 된 목록입니다.|모든 열에 표시 된 `DoFieldExchange`합니다.|`"Customer"`|
|**선택** 열 목록 **FROM** 테이블 목록|지정 된 tabledef(s) 및/또는 querydef(s)에서 지정 된 열입니다.|`"SELECT CustId, CustName`<br /><br /> `FROM Customer"`|

NULL을 전달 하는 일반적인 절차는 `Open`; 경우 `Open` 호출 `GetDefaultSQL`를 만들 때 클래스 마법사에서 생성 하는 재정의 가능한 멤버 함수를를 `CDaoRecordset`-파생 클래스입니다. 이 값은 클래스 마법사에서 지정한 tabledef(s) 및/또는 쿼리 정의 이름을 제공 합니다. 기타 정보를 지정할 수 있습니다 합니다 *lpszSQL* 매개 변수입니다.

전달 무엇이 든 `Open` 쿼리에 대 한 최종 SQL 문자열을 생성 (문자열 SQL 있을 수 있습니다 **여기서** 및 **ORDERBY** 절에 추가 합니다 *lpszSQL* 문자열 전달 된 사용자) 하 고 다음 쿼리를 실행 합니다. 호출 하 여 생성 된 문자열을 검사할 수 있습니다 `GetSQL` 호출한 후 `Open`합니다.

레코드 집합 클래스의 필드 데이터 멤버는 선택한 데이터의 열에 바인딩됩니다. 레코드가 반환 되는 경우 첫 번째 레코드는 현재 레코드가 됩니다.

필터 또는 정렬 같은 레코드에 대 한 옵션을 설정 하려는 경우 설정 `m_strSort` 나 `m_strFilter` 레코드 집합 개체를 생성 하지만 호출 하기 전에 `Open`입니다. 레코드 집합이 이미 열린 후 레코드 집합의 레코드를 새로 고쳐야 할 경우, 호출 `Requery`합니다.

호출 하는 경우 `Open` 다이너셋 형식 또는 스냅숏 형식 레코드 집합에 데이터 소스를 참조 하는 SQL 문 또는 연결 된 테이블을 나타내는 테이블 정의 사용할 수 없습니다 또는 `dbOpenTable` ; 형식 인수에 대 한 경우 MFC 예외를 throw 합니다. 테이블 정의 연결 된 테이블을 나타내는지 여부를 확인 하려면 만든를 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) 개체와 호출 해당 [GetConnect](../../mfc/reference/cdaotabledef-class.md#getconnect) 멤버 함수입니다.

사용 하 여는 `dbSeeChanges` 편집 하거나 동일한 레코드를 삭제 하는 경우 다른 사용자 또는 컴퓨터에 다른 응용 프로그램에서 변경 내용을 트랩 하려는 경우를 플래그 합니다. 예를 들어, 두 명의 사용자가 동일한 레코드를 호출 하는 첫 번째 사용자 편집을 시작 하는 경우는 `Update` 멤버 함수가 성공적으로 실행 합니다. 때 `Update` 두 번째 사용자에 의해 호출 되는 `CDaoException` throw 됩니다. 마찬가지로, 두 번째 사용자를 호출 하려고 `Delete` 하며 레코드를 삭제 하려면 이미 변경 된 첫 번째 사용자가를 `CDaoException` 발생 합니다.

일반적으로 사용자가이 `CDaoException` 업데이트 하는 동안 코드 해야 필드의 내용을 새로 고침 및 새로 수정 된 값을 검색 합니다. 삭제 하 고 예외가 발생 하는 경우 코드 데이터 최근에 변경 되었음을 나타내는 메시지를 사용자에 게 새 레코드 데이터를 표시할 수 있습니다. 이 시점에서 코드는 레코드를 삭제 하는 사용자가 여전히는 확인을 요청할 수 있습니다.

> [!TIP]
>  앞 으로만 이동 가능한 스크롤 옵션을 사용 하 여 (`dbForwardOnly`) 응용 프로그램에 단일 레코드 집합 통과 하면 성능을 향상 시키기 위해 ODBC 데이터 원본에서 열립니다.

관련된 내용은 DAO 도움말의 "OpenRecordset 메서드" 항목을 참조 합니다.

##  <a name="requery"></a>  CDaoRecordset::Requery

레코드 집합 (새로 고침)를 다시 작성 하려면이 멤버 함수를 호출 합니다.

```
virtual void Requery();
```

### <a name="remarks"></a>설명

레코드가 반환 되는 경우 첫 번째 레코드는 현재 레코드가 됩니다.

레코드 집합을 추가 및 삭제는 사용자나 다른 사용자에 게 데이터 원본에 반영 되려면, 다시 작성 해야 레코드를 호출 하 여 `Requery`입니다. 레코드 집합이 다이너셋 이면 자동으로 또는 다른 사용자에 게 해당 기존 레코드 (추가 되지 않음) 하는 업데이트를 반영 합니다. 레코드 집합을 스냅숏을 호출 해야 `Requery` 편집 하 여 다른 사용자 뿐만 아니라 추가 및 삭제를 반영 하도록 합니다.

다이너셋 또는 스냅숏으로 호출 `Requery` 매개 변수 값을 사용 하 여 레코드 집합을 다시 작성 하려면 언제 든 지 합니다. 설정 하 여 새 필터 또는 정렬 설정 [m_strFilter](#m_strfilter) 하 고 [m_strSort](#m_strsort) 호출 하기 전에 `Requery`입니다. 새 값을 호출 하기 전에 매개 변수 데이터 멤버에 할당 하 여 새 매개 변수를 설정 `Requery`합니다.

레코드 집합 다시 시도가 실패 하면 레코드 집합 닫혀 있습니다. 호출 하기 전에 `Requery`를 호출 하 여 레코드 집합을 다시 쿼리되어 수 있는지 여부를 확인할 수 있습니다 합니다 [CanRestart](#canrestart) 멤버 함수입니다. `CanRestart` 반드시 `Requery` 성공적으로 수행 됩니다.

> [!CAUTION]
>  호출 `Requery` 호출한 후에 `Open`합니다.

> [!NOTE]
>  호출 [Requery](#requery) DAO 책갈피를 변경 합니다.

호출할 수 없습니다 `Requery` 다이너셋 형식 또는 호출 하는 경우 스냅숏 형식 레코드 집합에 `CanRestart` 0을 반환 합니다. 사용 하 여 테이블 형식 레코드 집합에도 합니다.

모두 `IsBOF` 하 고 `IsEOF` 호출한 후 0이 아닌 반환 `Requery`, 쿼리에서 반환 하지 않았습니다. 모든 레코드 및 레코드 집합은 데이터가 포함 되지 않습니다.

관련된 내용은 DAO 도움말의 "Requery 메서드" 항목을 참조 합니다.

##  <a name="seek"></a>  CDaoRecordset::Seek

현재 지정된 된 조건을 인덱스 하 고 해당 레코드를 현재 레코드로 충족 하는 인덱싱된 테이블 형식 레코드 집합 개체에서의 레코드를 찾아이 멤버 함수를 호출 합니다.

```
BOOL Seek(
    LPCTSTR lpszComparison,
    COleVariant* pKey1,
    COleVariant* pKey2 = NULL,
    COleVariant* pKey3 = NULL);

BOOL Seek(
    LPCTSTR lpszComparison,
    COleVariant* pKeyArray,
    WORD nKeys);
```

### <a name="parameters"></a>매개 변수

*lpszComparison*<br/>
다음 문자열 식 중 하나: "<","\<=", "=" "> =", 또는 ">"입니다.

*pKey1*<br/>
에 대 한 포인터를 [COleVariant](../../mfc/reference/colevariant-class.md) 인덱스의 첫 번째 필드에 해당 하는 값입니다. 필수 요소.

*pKey2*<br/>
에 대 한 포인터를 `COleVariant` 있으면 해당 값은 인덱스의 두 번째 필드에 해당 합니다. 기본값은 NULL입니다.

*pKey3*<br/>
에 대 한 포인터를 `COleVariant` 값인 경우 인덱스의 세 번째 필드에 해당 합니다. 기본값은 NULL입니다.

*pKeyArray*<br/>
Variant의 배열에 대 한 포인터입니다. 배열 크기는 인덱스의 필드 수에 해당합니다.

*nKeys*<br/>
인덱스의 필드 수가 배열의 크기에 해당 하는 정수입니다.

> [!NOTE]
>  키에는 와일드 카드를 지정 하지 마십시오. 와일드 카드 하면 `Seek` 없는 일치 하는 레코드를 반환 합니다.

### <a name="return-value"></a>반환 값

그렇지 않은 0 일치 하는 레코드가 발견 하는 경우에 0이 아닙니다.

### <a name="remarks"></a>설명

두 번째 (배열) 버전을 사용 하 여 `Seek` 이상인 4 개의 필드의 인덱스를 처리할 수 있습니다.

`Seek` 테이블 형식의 레코드를 검색 하는 고성능 인덱스를 설정 합니다. 호출 하 여 현재 인덱스를 설정 해야 합니다 `SetCurrentIndex` 호출 하기 전에 `Seek`입니다. 인덱스는 고유 키 필드 또는 필드를 식별 하는 경우 `Seek` 기준을 만족 하는 첫 번째 레코드를 찾습니다. 인덱스를 설정 하지 않으면 예외가 throw 됩니다.

유니코드 레코드 집합을 만들지 않는 경우, `COleVariant` 개체가 명시적으로 선언 해야 ANSI 합니다. 이 사용 하 여 가능 합니다 [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** *lpszSrc* **를** *vtSrc* **)**  형식으로 사용 하 여 생성자 *vtSrc* 로 설정 `VT_BSTRT` (ANSI) 또는 사용 하 여 합니다 `COleVariant` 함수 [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** *lpszSrc* **하십시오** *vtSrc* **)** 사용 하 여 *vtSrc* 로 `VT_BSTRT`합니다.

호출 하는 경우 `Seek`, 하나 이상의 키 값과 비교 연산자를 전달 하면 ("<","\<=", "=" "> =", 또는 ">"). `Seek` 지정 된 키 필드를 검색 하 고 지정 된 조건을 충족 하는 첫 번째 레코드를 찾아 *lpszComparison* 하 고 *pKey1*합니다. 일단 찾았으면 `Seek` 0이 아닌 값을 반환 하며 해당 레코드를 현재 만듭니다. 하는 경우 `Seek` 일치 하는 항목을 찾지 못하면 `Seek` , 0을 반환 하 고 현재 레코드 정의 되지 않습니다. DAO를 직접 사용 하는 경우 NoMatch 속성이 명시적으로 확인 해야 합니다.

하는 경우 `lpszComparison` 는 "=" "> =", 또는 ">", `Seek` 인덱스부터 시작 합니다. 하는 경우 *lpszComparison* 는 "<" 또는 "< =", `Seek` 인덱스의 끝에서 시작 및 끝에 있는 중복 된 인덱스 항목이 없는 뒤로 검색 합니다. 이 경우 `Seek` 끝 인덱스에 중복 인덱스 항목 중에서 임의의 항목부터 시작 합니다.

있습니다 사용 하는 경우 현재 레코드 수 하지 않아도 `Seek`합니다.

다이너셋 형식 또는 특정 조건을 충족 하는 스냅숏 형식 레코드 집합에서 레코드를 찾으려고 찾기 작업을 사용 합니다. 뿐만 아니라 특정 조건을 만족 하는 모든 레코드를 포함 하려면 레코드를 이동 하려면 이동 작업을 사용 합니다.

호출할 수 없습니다 `Seek` 의 연결 된 테이블에 연결 된 테이블 다이너셋 형식 또는 스냅숏 형식 레코드 집합으로 열려 있어야 하기 때문에 입력 합니다. 그러나 호출 하는 경우 `CDaoDatabase::Open` ISAM 데이터베이스를 설치할 수 있는 열려면 직접 호출할 수 있습니다 `Seek` 해당 데이터베이스의 테이블에 성능이 될 수 있지만 느리게 합니다.

관련된 내용은 DAO 도움말의 "메서드 검색" 항목을 참조 합니다.

##  <a name="setabsoluteposition"></a>  CDaoRecordset::SetAbsolutePosition

레코드 집합 개체의 현재 레코드의 상대 레코드 수를 설정합니다.

```
void SetAbsolutePosition(long lPosition);
```

### <a name="parameters"></a>매개 변수

*lPosition*<br/>
레코드 집합의 현재 레코드의 서 수 위치에 해당합니다.

### <a name="remarks"></a>설명

호출 `SetAbsolutePosition` 다이너셋 형식 또는 스냅숏 형식 레코드 집합의 서 수 위치에 따라 특정 레코드를 현재 레코드 포인터를 배치할 수 있습니다. 또한 호출 하 여 현재 레코드 수를 확인할 수 있습니다 [GetAbsolutePosition](#getabsoluteposition)합니다.

> [!NOTE]
>  이 멤버 함수는 다이너셋 형식 및 스냅숏 형식 레코드 집합에 대해서만 유효 합니다.

기본 DAO 개체의 AbsolutePosition 속성 값이 0부터 시작 합니다. 0으로 설정 된 레코드 집합의 첫 번째 레코드를 가리킵니다. 채워진된 레코드 원인 예외를 throw 하는 MFC의 수보다 큰 값을 설정 합니다. 호출 하 여 레코드 집합의 레코드의 수를 확인할 수는 `GetRecordCount` 멤버 함수입니다.

현재 레코드를 삭제 하면 AbsolutePosition 속성 값을를 정의 하지 않으면 및 MFC 참조 하는 경우 예외를 throw 합니다. 새 레코드 시퀀스의 끝에 추가 됩니다.

> [!NOTE]
>  이 속성을 서로게이트 레코드 수로 사용할 수 없습니다. 책갈피는 여전히 유지 하 고 지정된 된 위치를 반환 하는 권장된 방법을 이며 책갈피를 지 원하는 레코드 집합 개체의 모든 형식에서 현재 레코드의 위치에 대 한 유일한 방법입니다. 특히 지정된 된 레코드의 위치 앞에 레코드가 삭제 되 면 변경 합니다. 지정된 된 레코드 되어 동일한 절대 위치 사용 하 여 SQL 문을 사용 하 여 생성 되지 않는 한 레코드 집합 내의 개별 레코드의 순서가 보장 되지 않으므로 레코드 집합을 다시 만들면 다시 확신할 수 없습니다 이기도 한  **ORDERBY** 절.

관련된 정보 DAO 도움말의 "AbsolutePosition 속성" 항목을 참조 하세요.

##  <a name="setbookmark"></a>  CDaoRecordset::SetBookmark

지정한 책갈피를 포함 하는 레코드에 레코드 집합을 배치 하려면이 멤버 함수를 호출 합니다.

```
void SetBookmark(COleVariant varBookmark);
```

### <a name="parameters"></a>매개 변수

*varBookmark*<br/>
A [COleVariant](../../mfc/reference/colevariant-class.md) 특정 레코드에 대 한 책갈피 값을 포함 하는 개체입니다.

### <a name="remarks"></a>설명

레코드 집합 개체를 만들거나 열린 각 레코드에 이미 고유 책갈피 있습니다. 호출 하 여 현재 레코드에 대 한 책갈피를 검색할 수 있습니다 `GetBookmark` 고 값을 저장 하는 `COleVariant` 개체입니다. 호출 하 여 해당 레코드 돌아갑니다 나중 `SetBookmark` 저장 된 책갈피 값을 사용 합니다.

> [!NOTE]
>  호출 [Requery](#requery) DAO 책갈피를 변경 합니다.

유니코드 레코드 집합을 만들지 않는 경우, `COleVariant` 개체가 명시적으로 선언 해야 ANSI 합니다. 이 사용 하 여 가능 합니다 [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** *lpszSrc* **를** *vtSrc* **)**  형식으로 사용 하 여 생성자 *vtSrc* 로 설정 `VT_BSTRT` (ANSI) 또는 사용 하 여 합니다 `COleVariant` 함수 [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** *lpszSrc* **하십시오** *vtSrc* **)** 사용 하 여 *vtSrc* 로 `VT_BSTRT`합니다.

관련된 정보에 대 한 항목을 참조 "Bookmark 속성" 및 책갈피를 설정할 속성 "DAO 도움말에서.

##  <a name="setcachesize"></a>  CDaoRecordset::SetCacheSize

캐시 될 레코드의 수를 설정 하려면이 멤버 함수를 호출 합니다.

```
void SetCacheSize(long lSize);
```

### <a name="parameters"></a>매개 변수

*lSize*<br/>
레코드의 수를 지정합니다. 일반적인 값은 100입니다. 캐시를 해제 하는 0으로 설정 합니다. 설정은 5 및 1200 레코드 사이 여야 합니다. 캐시에는 상당한 양의 메모리를 사용할 수 있습니다.

### <a name="remarks"></a>설명

캐시에서 데이터를 다시 요청 되는 응용 프로그램이 실행 되는 동안 서버에서 가장 최근에 검색 된 데이터를 보유 하는 로컬 메모리에 공간이 있습니다. 데이터 캐싱 다이너셋 형식 레코드 집합 개체를 통해 원격 서버에서 데이터를 검색 하는 응용 프로그램의 성능을 향상 시킵니다. 데이터가 요청 되 면 Microsoft Jet 데이터베이스 엔진의 캐시는 요청 된 데이터를 먼저 확인 더 많은 시간을 사용 하는 서버에서 검색 하는 대신 합니다. ODBC 데이터 원본에서 제공 되지 않는 데이터 캐시에 저장 되지 않습니다.

모든 ODBC 데이터 원본에 연결 된 테이블을 같은 로컬 캐시를 가질 수 있습니다. 캐시를 만들려면 호출 원격 데이터 원본에서 레코드 집합 개체를 엽니다는 `SetCacheSize` 및 `SetCacheStart` 멤버 함수 및 호출을 `FillCache` 멤버 함수 또는 이동 작업 중 하나를 사용 하 여 레코드를 통해 단계. 합니다 *lSize* 의 매개 변수는 `SetCacheSize` 멤버 함수는 응용 프로그램이 한 번에 작업할 수 레코드의 수에 기반 할 수 있습니다. 예를 들어, 데이터 원본으로 레코드 집합을 사용 하 여 화면에 표시 되는, 하는 경우 전달할 수 있습니다 합니다 `SetCacheSize` *lSize* 20 개의 레코드를 한 번에 표시할 20으로 매개 변수입니다.

관련된 내용은 DAO 도움말의 "CacheSize CacheStart 속성" 항목을 참조 합니다.

##  <a name="setcachestart"></a>  CDaoRecordset::SetCacheStart

캐시할 레코드 집합의 첫 번째 레코드의 책갈피를 지정 하려면이 멤버 함수를 호출 합니다.

```
void SetCacheStart(COleVariant varBookmark);
```

### <a name="parameters"></a>매개 변수

*varBookmark*<br/>
A [COleVariant](../../mfc/reference/colevariant-class.md) 캐시할 레코드 집합의 첫 번째 레코드의 책갈피를 지정 하는 합니다.

### <a name="remarks"></a>설명

에 대 한 모든 레코드의 책갈피 값을 사용할 수는 *varBookmark* 의 매개 변수는 `SetCacheStart` 멤버 함수입니다. 현재 레코드를 사용 하 여 캐시를 시작, 사용 하 여 해당 레코드에 대 한 책갈피를 설정 하려는 레코드를 만들고 [SetBookmark](#setbookmark), 책갈피 값에 대 한 매개 변수로 전달 합니다 `SetCacheStart` 멤버 함수입니다.

Microsoft Jet 데이터베이스 엔진 캐시에서 캐시 범위 내에서 레코드를 요청 하 고 서버에서 캐시 범위 외부의 레코드를 요청 합니다.

캐시에서 검색 된 레코드에는 다른 사용자가 원본 데이터에 동시에 변경 내용을 반영 하지 않습니다.

모든 캐시 된 데이터의 업데이트를 적용 하려면 전달 합니다 *lSize* 의 매개 변수 `SetCacheSize` 0으로 호출 `SetCacheSize` 다시 캐시의 크기를 사용 하 여 원래 요청을 호출 합니다 `FillCache` 멤버 함수입니다.

유니코드 레코드 집합을 만들지 않는 경우, `COleVariant` 개체가 명시적으로 선언 해야 ANSI 합니다. 이 사용 하 여 가능 합니다 [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** *lpszSrc* **를** *vtSrc* **)**  형식으로 사용 하 여 생성자 *vtSrc* 로 설정 `VT_BSTRT` (ANSI) 또는 사용 하 여 합니다 `COleVariant` 함수 [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** *lpszSrc* **하십시오** *vtSrc* **)** 사용 하 여 *vtSrc* 로 `VT_BSTRT`합니다.

관련된 정보에 대 한 항목을 참조 CacheSize, CacheStart 속성 "DAO 도움말에서.

##  <a name="setcurrentindex"></a>  CDaoRecordset::SetCurrentIndex

테이블 형식 레코드 집합에 인덱스를 설정 하려면이 멤버 함수를 호출 합니다.

```
void SetCurrentIndex(LPCTSTR lpszIndex);
```

### <a name="parameters"></a>매개 변수

*lpszIndex*<br/>
설정할 인덱스의 이름을 포함 하는 포인터입니다.

### <a name="remarks"></a>설명

기본 테이블의 레코드는 특정 순서로 저장 되지 않습니다. 데이터베이스에서 반환 된 레코드의 순서를 변경 하는 인덱스를 설정 하지만 레코드가 저장 되는 순서에 영향을 주지 않습니다. 지정한 인덱스에 이미 정의 되어 있어야 합니다. 존재 하지 않는 인덱스 개체를 사용 하려는 경우 또는 인덱스를 호출할 때 설정 되어 있지 [Seek](#seek), MFC 예외를 throw 합니다.

호출 하 여 테이블에 대 한 새 인덱스를 만들면 [CDaoTableDef::CreateIndex](../../mfc/reference/cdaotabledef-class.md#createindex) 를 호출 하 여 기본 테이블 정의의 인덱스 컬렉션에 새 인덱스를 추가 하 고 [CDaoTableDef::Append](../../mfc/reference/cdaotabledef-class.md#append), 및 레코드 집합을 닫은 다음입니다.

기본 테이블 정의에 정의 된 인덱스에 의해서만 테이블 형식 레코드 집합에서 반환 된 레코드를 정렬할 수 있습니다. 다른 순서로 레코드를 정렬 하려면 다이너셋 형식 또는 SQL을 사용 하 여 스냅숏 형식 레코드 집합을 열 수 있습니다 **ORDERBY** 에 저장 된 절 [CDaoRecordset::m_strSort](#m_strsort)합니다.

관련된 정보 항목 "인덱스 개체" 및 "현재 인덱스" DAO 도움말의 정의 참조 하세요.

##  <a name="setfielddirty"></a>  CDaoRecordset::SetFieldDirty

변경 된 또는으로 변경 되지 않은 레코드 집합의 필드 데이터 멤버 플래그를 설정 하려면이 멤버 함수를 호출 합니다.

```
void SetFieldDirty(
    void* pv,
    BOOL bDirty = TRUE);
```

### <a name="parameters"></a>매개 변수

*pv*<br/>
NULL 레코드 집합의 필드 데이터 멤버의 주소를 포함합니다. NULL 인 경우 레코드 집합의 필드 데이터 멤버를 모든 플래그가 지정 됩니다. (C++ NULL 다릅니다 Null로 데이터베이스 용어에서 "값 필요"는 의미)

*bDirty*<br/>
필드 데이터 멤버 "더티" (변경)으로 플래그를 지정 하는 경우 TRUE입니다. 필드 데이터 멤버 "정리" (변경 되지 않음)으로 플래그가 지정 될 경우, 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

변경 되지 않은 필드를 표시 하면 필드 업데이트 되지 않습니다.

Framework 표시 DAO 레코드 필드 교환 (DFX) 메커니즘을 통해 데이터 소스에서 레코드를 기록 수는 되도록 필드 데이터 멤버를 변경 합니다. 필드의 값을 일반적으로 변경 필드 설정 더티 자동으로 호출할 필요가 거의 `SetFieldDirty` 수 있지만 사용자가 직접 할 때도 열은 명시적으로 업데이트 되거나 삽입 될에 관계 없이 값 필드 데이터에서를 확인 합니다. 멤버입니다. 또한 DFX 메커니즘 PSEUDONULL 사용을 사용합니다. 자세한 내용은 [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation)합니다.

이중 버퍼링 메커니즘을 사용 하지 않는 경우 필드의 값을 변경한 다음 설정 하지 않습니다 자동으로 필드 변경 된 상태로 보입니다. 이 경우를 명시적으로 커밋되지 않은 것으로 필드를 설정 해야 합니다. 에 포함 된 플래그 [m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) 이 자동 필드 검사를 제어 합니다.

> [!NOTE]
>  이 멤버 함수를 호출한 후에 호출 [편집할](#edit) 하거나 [AddNew](#addnew)합니다.

함수의 첫 번째 인수는 모든 함수를 적용에 대 한 NULL을 사용 하 여 `outputColumn` 필드 되지 **param** 필드에 `CDaoFieldExchange`입니다. 예를 들어 호출

[!code-cpp[NVC_MFCDatabase#6](../../mfc/codesnippet/cpp/cdaorecordset-class_6.cpp)]

설정이 적용만 `outputColumn` NULL 필드 **param** 필드에 영향을 받지 않습니다.

작업할를 **param**, 개별의 실제 주소를 제공 해야 합니다 **param** 와 같은 작업을 하려는:

[!code-cpp[NVC_MFCDatabase#7](../../mfc/codesnippet/cpp/cdaorecordset-class_7.cpp)]

즉, 모든 설정할 수 없습니다 **param** 수행할 수 있는 NULL로 필드 `outputColumn` 필드입니다.

`SetFieldDirty` 통해 구현 됩니다 `DoFieldExchange`합니다.

##  <a name="setfieldnull"></a>  CDaoRecordset::SetFieldNull

(특히 값이 없는 필요 없음) Null 또는 Null이 아닌 레코드 집합의 필드 데이터 멤버 플래그를 설정 하려면이 멤버 함수를 호출 합니다.

```
void SetFieldNull(
    void* pv,
    BOOL bNull = TRUE);
```

### <a name="parameters"></a>매개 변수

*pv*<br/>
NULL 레코드 집합의 필드 데이터 멤버의 주소를 포함합니다. NULL 인 경우 레코드 집합의 필드 데이터 멤버를 모든 플래그가 지정 됩니다. (C++ NULL 다릅니다 Null로 데이터베이스 용어에서 "값 필요"는 의미)

*bNull*<br/>
필드 데이터 멤버 (Null) 값이 없는 것으로 플래그가 지정 될 경우에 0이 아닙니다. 필드 데이터 멤버는 Null이 아닌으로 플래그를 설정 하는 경우 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

`SetFieldNull` 에 바인딩된 필드에 사용 되는 `DoFieldExchange` 메커니즘입니다.

레코드 집합에 새 레코드를 추가 하면 모든 필드 데이터 멤버는 처음 Null 값으로 설정 하 고 "더티" (변경)으로 플래그가 지정 됩니다. 데이터 원본에서 레코드를 검색 하는 경우 해당 열 중 이미 값이 있거나 null입니다. Null 필드에 적합 하지 않은 경우는 [CDaoException](../../mfc/reference/cdaoexception-class.md) throw 됩니다.

특히 현재 레코드의 필드를 호출 하는 값을 없는 것으로 지정 하려는 예를 들어, 이중 버퍼링 메커니즘을 사용 중인 경우 `SetFieldNull` 사용 하 여 *bNull* Null 플래그를 TRUE로 설정 합니다. 필드는 Null 이전에 표시 된 값을 지정 하려는 경우 새 값을 설정 하기만 하면 됩니다. Null 플래그를 제거할 필요가 없습니다 `SetFieldNull`합니다. 필드가 null이 허용 되는지 여부를 결정할 호출 [IsFieldNullable](#isfieldnullable)합니다.

이중 버퍼링 메커니즘을 사용 하지 않는 경우 필드의 값을 변경한 다음 설정 하지 않습니다 자동으로 필드와 더티 Null. 특히 더티 및 Null이 아닌 필드를 설정 해야 합니다. 에 포함 된 플래그 [m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) 이 자동 필드 검사를 제어 합니다.

DFX 메커니즘 PSEUDONULL 사용을 사용합니다. 자세한 내용은 [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation)합니다.

> [!NOTE]
>  이 멤버 함수를 호출한 후에 호출 [편집할](#edit) 하거나 [AddNew](#addnew)합니다.

함수의 첫 번째 인수는 함수에만 적용 됩니다에 대 한 NULL을 사용 하 여 `outputColumn` 필드 되지 **param** 필드에 `CDaoFieldExchange`입니다. 예를 들어 호출

[!code-cpp[NVC_MFCDatabase#8](../../mfc/codesnippet/cpp/cdaorecordset-class_8.cpp)]

설정이 적용만 `outputColumn` NULL 필드 **param** 필드에 영향을 받지 않습니다.

##  <a name="setfieldvalue"></a>  CDaoRecordset::SetFieldValue

서 수 위치 또는 문자열의 값을 변경 하 여 필드의 값을 설정 하려면이 멤버 함수를 호출 합니다.

```
virtual void SetFieldValue(
    LPCTSTR lpszName,
    const COleVariant& varValue);

virtual void SetFieldValue(
    int nIndex,
    const COleVariant& varValue);

void SetFieldValue(
    LPCTSTR lpszName,
    LPCTSTR lpszValue);

void SetFieldValue(
    int nIndex,
    LPCTSTR lpszValue);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
필드의 이름을 포함 하는 문자열에 대 한 포인터입니다.

*varValue*<br/>
에 대 한 참조를 [COleVariant](../../mfc/reference/colevariant-class.md) 필드의 내용이 값이 포함 된 개체입니다.

*nIndex*<br/>
정수 (0부터 시작) 레코드 집합의 필드 컬렉션에서 필드의 서 수 위치를 나타내는입니다.

*lpszValue*<br/>
필드의 내용이 값이 포함 된 문자열에 대 한 포인터입니다.

### <a name="remarks"></a>설명

사용 하 여 `SetFieldValue` 하 고 [GetFieldValue](#getfieldvalue) 실행된 시간 보다는 정적으로 사용 하 여 바인딩 열 필드를 동적으로 바인딩할 합니다 [DoFieldExchange](#dofieldexchange) 메커니즘입니다.

유니코드 레코드 집합을 만들지 않는 경우 중 하나를 사용 해야의 형태 `SetFieldValue` 포함 하지 않는 한 `COleVariant` 매개 변수를 또는 `COleVariant` 개체 명시적으로 선언 해야 ANSI 합니다. 이 사용 하 여 가능 합니다 [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** *lpszSrc* **를** *vtSrc* **)**  형식으로 사용 하 여 생성자 *vtSrc* 로 설정 `VT_BSTRT` (ANSI) 또는 사용 하 여 합니다 `COleVariant` 함수 [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** *lpszSrc* **하십시오** *vtSrc* **)** 사용 하 여 *vtSrc* 로 `VT_BSTRT`합니다.

관련된 정보에 대 한 "필드 개체" 속성과 "값" DAO 도움말의 항목을 참조 합니다.

##  <a name="setfieldvaluenull"></a>  CDaoRecordset::SetFieldValueNull

Null 값으로 필드를 설정 하려면이 멤버 함수를 호출 합니다.

```
void SetFieldValueNull(int nIndex);
void SetFieldValueNull(LPCTSTR lpszName);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
인덱스 0부터 시작 하 여 조회에 대 한 레코드에서 필드의 인덱스입니다.

*lpszName*<br/>
이름별 조회에 대 한 레코드에서 필드의 이름입니다.

### <a name="remarks"></a>설명

C++NULL은 Null 이며 데이터베이스 용어에서 의미와 동일 하지 않습니다 "값이 없는 것입니다."

관련된 정보에 대 한 "필드 개체" 속성과 "값" DAO 도움말의 항목을 참조 합니다.

##  <a name="setlockingmode"></a>  CDaoRecordset::SetLockingMode

레코드 집합에 대 한 잠금 유형을 설정 하려면이 멤버 함수를 호출 합니다.

```
void SetLockingMode(BOOL bPessimistic);
```

### <a name="parameters"></a>매개 변수

*bPessimistic*<br/>
잠금 유형을 나타내는 플래그입니다.

### <a name="remarks"></a>설명

호출 하는 즉시 잠긴 경우 비관적 잠금과 실제로 2k 페이지 편집 하는 레코드를 포함 하는 `Edit` 멤버 함수입니다. 호출할 때 페이지 잠금이 아닙니다 합니다 `Update` 또는 `Close` 멤버 함수 또는 이동 또는 찾기 작업 중 하나입니다.

레코드를 포함 하는 2 개의 K 페이지를 사용 하 여 레코드를 업데이트 하는 동안에 잠겨 때 낙관적 잠금이 적용 됩니다는 `Update` 멤버 함수입니다.

페이지에서 차단 된 경우 다른 사용자 같은 페이지에 레코드를 편집할 수 있습니다. 호출 하는 경우 `SetLockingMode` 0이 아닌 값을 전달 하 고 다른 사용자가 이미 잠긴 페이지를 호출할 때 예외가 throw 됩니다 `Edit`합니다. 다른 사용자가 잠긴된 페이지에서 데이터를 읽을 수 있습니다.

호출 하는 경우 `SetLockingMode` 값이 0 개 이상 호출할 `Update` 페이지 다른 사용자가 잠겨 있는 동안 예외가 발생 합니다. 다른 사용자가 레코드에 변경 내용을 볼 (및 변경 내용이 손실)을 호출 합니다 `SetBookmark` 현재 레코드의 책갈피 값을 사용 하 여 멤버 함수입니다.

ODBC 데이터 원본으로 작업할 경우에 잠금 모드는 낙관적 항상입니다.

##  <a name="setparamvalue"></a>  CDaoRecordset::SetParamValue

런타임 시 레코드 집합의 매개 변수 값을 설정 하려면이 멤버 함수를 호출 합니다.

```
virtual void SetParamValue(
    int nIndex,
    const COleVariant& varValue);

virtual void SetParamValue(
    LPCTSTR lpszName,
    const COleVariant& varValue);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
쿼리 정의 매개 변수 컬렉션에서 매개 변수의 숫자 위치입니다.

*var*<br/>
값을 설정 설명을 참조 하세요.

*lpszName*<br/>
설정 하려는 값 매개 변수의 이름입니다.

### <a name="remarks"></a>설명

매개 변수는 레코드 집합의 SQL 문자열의 일부로 설정 이미 있어야 합니다. 매개 변수 이름 또는 컬렉션의 인덱스 위치를 기준으로 액세스할 수 있습니다.

로 설정 하려면 값을 지정 된 `COleVariant` 개체입니다. 형식을 확인 하 고 원하는 값을 설정 하는 방법에 대 한 정보에 대 한 사용자 `COleVariant` 개체 클래스를 참조 하십시오 [COleVariant](../../mfc/reference/colevariant-class.md)합니다. 유니코드 레코드 집합을 만들지 않는 경우, `COleVariant` 개체가 명시적으로 선언 해야 ANSI 합니다. 이 사용 하 여 가능 합니다 [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** *lpszSrc* **를** *vtSrc* **)**  형식으로 사용 하 여 생성자 *vtSrc* 로 설정 `VT_BSTRT` (ANSI) 또는 사용 하 여 합니다 `COleVariant` 함수 [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** *lpszSrc* **하십시오** *vtSrc* **)** 사용 하 여 *vtSrc* 로 `VT_BSTRT`합니다.

##  <a name="setparamvaluenull"></a>  CDaoRecordset::SetParamValueNull

Null 값으로 매개 변수를 설정 하려면이 멤버 함수를 호출 합니다.

```
void SetParamValueNull(int nIndex);
void SetParamValueNull(LPCTSTR lpszName);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
인덱스 0부터 시작 하 여 조회에 대 한 레코드에서 필드의 인덱스입니다.

*lpszName*<br/>
이름별 조회에 대 한 레코드에서 필드의 이름입니다.

### <a name="remarks"></a>설명

C++NULL은 Null 이며 데이터베이스 용어에서 의미와 동일 하지 않습니다 "값이 없는 것입니다."

##  <a name="setpercentposition"></a>  CDaoRecordset::SetPercentPosition

레코드 집합에서 레코드의 비율을 기준으로 레코드 집합 개체의 현재 레코드의 대략적인 위치를 변경 하는 값을 설정 하려면이 멤버 함수를 호출 합니다.

```
void SetPercentPosition(float fPosition);
```

### <a name="parameters"></a>매개 변수

*fPosition*<br/>
0부터 100까지의 숫자입니다.

### <a name="remarks"></a>설명

다이너셋 형식 또는 스냅숏 형식 레코드 집합을 사용 하는 경우 먼저 채워야 레코드를 이동 하 여 마지막 레코드를 호출 하기 전에 `SetPercentPosition`입니다. 호출 하는 경우 `SetPercentPosition` 레코드를 완전 하 게 채운 전에 이동의 양을 값으로 표시 된 대로 액세스 하는 레코드의 수에 상대적입니다 [GetRecordCount](#getrecordcount)합니다. 이동할 수 있습니다 마지막 레코드를 호출 하 여 `MoveLast`입니다.

호출 했으면 `SetPercentPosition`, 해당 값에 해당 하는 대략적인 위치에 있는 레코드를 현재 됩니다.

> [!NOTE]
>  호출 `SetPercentPosition` 이동 현재 레코드를 레코드 집합의 특정 레코드를 권장 되지 않습니다. 호출 된 [SetBookmark](#setbookmark) 멤버 함수를 대신 합니다.

관련된 내용은 DAO 도움말의 "PercentPosition Property" 항목을 참조 합니다.

##  <a name="update"></a>  CDaoRecordset::Update

호출한 후에이 멤버 함수를 호출 합니다 `AddNew` 또는 `Edit` 멤버 함수입니다.

```
virtual void Update();
```

### <a name="remarks"></a>설명

이 호출을 완료 해야 합니다 `AddNew` 또는 `Edit` 작업 합니다.

둘 다 `AddNew` 고 `Edit` 데이터 원본에 저장 하기 위한 추가 또는 편집 데이터가 위치한 편집 버퍼를 준비 합니다. `Update` 데이터를 저장합니다. 표시 되거나 변경 된 것으로 검색 된 필드만 업데이트 됩니다.

가능 데이터 소스에서 트랜잭션을 지원 합니다 `Update` 호출 (및 해당 `AddNew` 또는 `Edit` 호출) 트랜잭션의 일부입니다.

> [!CAUTION]
> 호출 하는 경우 `Update` 호출 없이 첫 번째 `AddNew` 하거나 `Edit`, `Update` throw를 `CDaoException`입니다. 호출 하는 경우 `AddNew` 또는 `Edit`를 호출 해야 `Update` 호출 하기 전에 [MoveNext](#movenext) 하거나 레코드 집합 또는 데이터 원본 연결을 닫습니다. 그렇지 않은 경우 변경 내용을 통지 없이 손실 됩니다.

레코드 집합 개체를 잠그면 pessimistically 다중 사용자 환경에서, 레코드 잠긴 상태로 유지 됩니다 시간부터 `Edit` 업데이트가 완료 될 때까지 사용 됩니다. 레코드 집합 낙관적으로 잠겨 있으면 레코드 잠기고 데이터베이스의 업데이트 직전 미리 편집한 레코드와 비교 합니다. 레코드는 호출한 후에 변경 된 경우 `Edit`, `Update` 작업이 실패 하 고 MFC 예외를 throw 합니다. 사용 하 여 잠금 모드를 변경할 수 있습니다 `SetLockingMode`합니다.

> [!NOTE]
> 낙관적 잠금 ODBC 등 설치 가능한 ISAM 외부 데이터베이스 형식으로 항상 사용 됩니다.

관련된 정보에 대 한 "AddNew 메서드", "CancelUpdate 메서드", "Delete 메서드", "LastModified Property", "업데이트 방법" 및 DAO 도움말의 "EditMode 속성" 항목을 참조 합니다.

## <a name="see-also"></a>참고자료

[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CDaoTableDef 클래스](../../mfc/reference/cdaotabledef-class.md)<br/>
[CDaoWorkspace 클래스](../../mfc/reference/cdaoworkspace-class.md)<br/>
[CDaoDatabase 클래스](../../mfc/reference/cdaodatabase-class.md)<br/>
[CDaoQueryDef 클래스](../../mfc/reference/cdaoquerydef-class.md)<br/>
