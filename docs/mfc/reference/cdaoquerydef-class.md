---
title: CDaoQueryDef 클래스
ms.date: 11/04/2016
f1_keywords:
- CDaoQueryDef
- AFXDAO/CDaoQueryDef
- AFXDAO/CDaoQueryDef::CDaoQueryDef
- AFXDAO/CDaoQueryDef::Append
- AFXDAO/CDaoQueryDef::CanUpdate
- AFXDAO/CDaoQueryDef::Close
- AFXDAO/CDaoQueryDef::Create
- AFXDAO/CDaoQueryDef::Execute
- AFXDAO/CDaoQueryDef::GetConnect
- AFXDAO/CDaoQueryDef::GetDateCreated
- AFXDAO/CDaoQueryDef::GetDateLastUpdated
- AFXDAO/CDaoQueryDef::GetFieldCount
- AFXDAO/CDaoQueryDef::GetFieldInfo
- AFXDAO/CDaoQueryDef::GetName
- AFXDAO/CDaoQueryDef::GetODBCTimeout
- AFXDAO/CDaoQueryDef::GetParameterCount
- AFXDAO/CDaoQueryDef::GetParameterInfo
- AFXDAO/CDaoQueryDef::GetParamValue
- AFXDAO/CDaoQueryDef::GetRecordsAffected
- AFXDAO/CDaoQueryDef::GetReturnsRecords
- AFXDAO/CDaoQueryDef::GetSQL
- AFXDAO/CDaoQueryDef::GetType
- AFXDAO/CDaoQueryDef::IsOpen
- AFXDAO/CDaoQueryDef::Open
- AFXDAO/CDaoQueryDef::SetConnect
- AFXDAO/CDaoQueryDef::SetName
- AFXDAO/CDaoQueryDef::SetODBCTimeout
- AFXDAO/CDaoQueryDef::SetParamValue
- AFXDAO/CDaoQueryDef::SetReturnsRecords
- AFXDAO/CDaoQueryDef::SetSQL
- AFXDAO/CDaoQueryDef::m_pDAOQueryDef
- AFXDAO/CDaoQueryDef::m_pDatabase
helpviewer_keywords:
- CDaoQueryDef [MFC], CDaoQueryDef
- CDaoQueryDef [MFC], Append
- CDaoQueryDef [MFC], CanUpdate
- CDaoQueryDef [MFC], Close
- CDaoQueryDef [MFC], Create
- CDaoQueryDef [MFC], Execute
- CDaoQueryDef [MFC], GetConnect
- CDaoQueryDef [MFC], GetDateCreated
- CDaoQueryDef [MFC], GetDateLastUpdated
- CDaoQueryDef [MFC], GetFieldCount
- CDaoQueryDef [MFC], GetFieldInfo
- CDaoQueryDef [MFC], GetName
- CDaoQueryDef [MFC], GetODBCTimeout
- CDaoQueryDef [MFC], GetParameterCount
- CDaoQueryDef [MFC], GetParameterInfo
- CDaoQueryDef [MFC], GetParamValue
- CDaoQueryDef [MFC], GetRecordsAffected
- CDaoQueryDef [MFC], GetReturnsRecords
- CDaoQueryDef [MFC], GetSQL
- CDaoQueryDef [MFC], GetType
- CDaoQueryDef [MFC], IsOpen
- CDaoQueryDef [MFC], Open
- CDaoQueryDef [MFC], SetConnect
- CDaoQueryDef [MFC], SetName
- CDaoQueryDef [MFC], SetODBCTimeout
- CDaoQueryDef [MFC], SetParamValue
- CDaoQueryDef [MFC], SetReturnsRecords
- CDaoQueryDef [MFC], SetSQL
- CDaoQueryDef [MFC], m_pDAOQueryDef
- CDaoQueryDef [MFC], m_pDatabase
ms.assetid: 9676a4a3-c712-44d4-8c5d-d1cc78288d3a
ms.openlocfilehash: 08fb2909a4fd2e5bda3dfc63d19224a515c7c699
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399748"
---
# <a name="cdaoquerydef-class"></a>CDaoQueryDef 클래스

일반적으로 데이터베이스에 저장되는 쿼리 정의 또는 "querydef"를 나타냅니다.

## <a name="syntax"></a>구문

```
class CDaoQueryDef : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CDaoQueryDef::CDaoQueryDef](#cdaoquerydef)|`CDaoQueryDef` 개체를 생성합니다. 다음 호출 `Open` 또는 `Create`요구 사항에 따라 합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CDaoQueryDef::Append](#append)|저장 된 쿼리로 QueryDefs 컬렉션 데이터베이스의 쿼리 정의 추가합니다.|
|[CDaoQueryDef::CanUpdate](#canupdate)|쿼리는 데이터베이스를 업데이트할 수 있는 경우 0이 아닌 값을 반환 합니다.|
|[CDaoQueryDef::Close](#close)|쿼리 정의 개체를 닫습니다. 삭제는 C++ 개체와 완료 합니다.|
|[CDaoQueryDef::Create](#create)|기본 DAO 쿼리 정의 개체를 만듭니다. 쿼리 정의 사용 하 여 임시 쿼리 또는 호출 `Append` 데이터베이스에 저장 합니다.|
|[CDaoQueryDef::Execute](#execute)|쿼리 정의 개체로 정의 된 쿼리를 실행 합니다.|
|[CDaoQueryDef::GetConnect](#getconnect)|쿼리 정의 사용 하 여 연결 된 연결 문자열을 반환 합니다. 연결 문자열에는 데이터 원본을 식별 합니다. (Sql 통과 쿼리의 고, 그렇지 않으면 빈 문자열입니다.)|
|[CDaoQueryDef::GetDateCreated](#getdatecreated)|저장된 된 쿼리를 만든 날짜를 반환 합니다.|
|[CDaoQueryDef::GetDateLastUpdated](#getdatelastupdated)|저장된 된 쿼리를 마지막으로 업데이트 한 날짜를 반환 합니다.|
|[CDaoQueryDef::GetFieldCount](#getfieldcount)|쿼리 정의에서 정의 된 필드 수를 반환 합니다.|
|[CDaoQueryDef::GetFieldInfo](#getfieldinfo)|쿼리에 정의 된 지정된 된 필드에 대 한 정보를 반환 합니다.|
|[CDaoQueryDef::GetName](#getname)|쿼리 정의의 이름을 반환합니다.|
|[CDaoQueryDef::GetODBCTimeout](#getodbctimeout)|ODBC (예: ODBC 쿼리)를 사용 하는 시간 제한 값을 반환 합니다. 쿼리 정의 실행할 때. 쿼리의 작업 완료에 대 한 허용 하려면 기간 결정 합니다.|
|[CDaoQueryDef::GetParameterCount](#getparametercount)|쿼리에 정의 된 매개 변수 개수를 반환 합니다.|
|[CDaoQueryDef::GetParameterInfo](#getparameterinfo)|쿼리에 지정된 된 매개 변수에 대 한 정보를 반환합니다.|
|[CDaoQueryDef::GetParamValue](#getparamvalue)|쿼리에 지정된 된 매개 변수의 값을 반환합니다.|
|[CDaoQueryDef::GetRecordsAffected](#getrecordsaffected)|작업 쿼리를 영향을 받는 레코드 수를 반환 합니다.|
|[CDaoQueryDef::GetReturnsRecords](#getreturnsrecords)|쿼리 정의에서 정의 된 쿼리는 레코드를 반환 하는 경우 0이 아닌 값을 반환 합니다.|
|[CDaoQueryDef::GetSQL](#getsql)|쿼리 정의에서 정의 된 쿼리를 지정 하는 SQL 문자열을 반환 합니다.|
|[CDaoQueryDef::GetType](#gettype)|쿼리 형식을 반환 합니다: 삭제, 업데이트, 추가, 테이블 만들기 및 등입니다.|
|[CDaoQueryDef::IsOpen](#isopen)|쿼리 정의가 열려 있고 실행할 수 있습니다 하는 경우 0이 아닌 값을 반환 합니다.|
|[CDaoQueryDef::Open](#open)|데이터베이스의 QueryDefs 컬렉션에 저장 된 쿼리는 기존 정의 엽니다.|
|[CDaoQueryDef::SetConnect](#setconnect)|ODBC 데이터 원본에 대해 SQL 통과 쿼리를 위한 연결 문자열을 설정합니다.|
|[CDaoQueryDef::SetName](#setname)|쿼리 정의 만들 때 사용 중인 이름 바꾸기 저장 된 쿼리의 이름을 설정 합니다.|
|[CDaoQueryDef::SetODBCTimeout](#setodbctimeout)|ODBC에서 (예: ODBC 쿼리)를 사용 하는 시간 제한 값을 설정 하는 쿼리 정의 실행할 때.|
|[CDaoQueryDef::SetParamValue](#setparamvalue)|쿼리에 지정된 된 매개 변수의 값을 설정합니다.|
|[CDaoQueryDef::SetReturnsRecords](#setreturnsrecords)|쿼리 정의 레코드를 반환 하는지 여부를 지정 합니다. 이 특성을 true로 설정 해당 통과 쿼리를 SQL에만 유효 합니다.|
|[CDaoQueryDef::SetSQL](#setsql)|쿼리 정의에서 정의 된 쿼리를 지정 하는 SQL 문자열을 설정 합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CDaoQueryDef::m_pDAOQueryDef](#m_pdaoquerydef)|OLE 인터페이스 기본 DAO 쿼리 정의 개체에 대 한 포인터입니다.|
|[CDaoQueryDef::m_pDatabase](#m_pdatabase)|에 대 한 포인터를 `CDaoDatabase` 쿼리 정의 연결 된 개체입니다. 쿼리 정의 또는 데이터베이스에 저장 되어 있습니다.|

## <a name="remarks"></a>설명

쿼리 정의 쿼리 및 "만든 날짜" 및 "ODBC 시간 제한입니다."와 같은 속성을 설명 하는 SQL 문을 포함 하는 데이터 액세스 개체 저장 하지 않고 임시 쿼리 정의 개체를 만들 수도 있지만 것이 편리-하 고 훨씬 더 효율적으로-일반적으로 저장 하려면 데이터베이스의 쿼리를 다시 사용 합니다. A [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체는 해당 저장 된 쿼리 정의 포함 하는 QueryDefs 컬렉션 이라는 컬렉션을 유지 합니다.

> [!NOTE]
>  DAO 데이터베이스 클래스로 개방형 데이터베이스 연결 (ODBC)에 따라 MFC 데이터베이스 클래스와에서 다릅니다. 모든 DAO 데이터베이스 클래스 이름 "CDao" 접두사가 있습니다. 여전히 DAO 클래스를 사용 하 여 ODBC 데이터 원본 액세스 할 수 있습니다. 일반적으로 기반으로 DAO MFC 클래스는 ODBC를 기반으로 MFC 클래스 보다 더욱 강력한 DAO 기반 클래스를 통해 자신의 데이터베이스 엔진을 통해 ODBC 드라이버를 비롯 하 여 데이터를 액세스할 수 있습니다. DAO 기반 클래스는 또한 직접 DAO 호출 하지 않고도 클래스를 통해 테이블을 추가 하는 등의 데이터 정의 언어 (DDL) 작업을 지원 합니다.

## <a name="usage"></a>사용법

개체를 사용 쿼리 정의 하거나 기존에 저장 된 쿼리를 사용 하거나 새 쿼리나 임시 쿼리를 저장 합니다.

1. 먼저 생성 모든 경우에는 `CDaoQueryDef` 에 대 한 포인터를 제공 하는 개체를 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 쿼리 속한 개체입니다.

1. 다음 항목에 따라 다음을 수행 합니다.

   - 기존에 저장 된 쿼리를 사용 하려면 쿼리 정의 개체의 호출 [열고](#open) 멤버 함수, 저장 된 쿼리의 이름을 제공 합니다.

   - 저장된 된 새 쿼리를 만들려면 쿼리 정의 개체의 호출 [만들기](#create) 멤버 함수를 쿼리의 이름을 제공 합니다. 그런 다음 호출 [추가](#append) 데이터베이스의 QueryDefs 컬렉션에 추가 하 여 쿼리를 저장 합니다. `Create` 쿼리 정의 열린 상태로 넣습니다 호출한 후 따라서 `Create` 호출 하지 않으면 `Open`합니다.

   - 임시 쿼리 정의 만들려면 호출 `Create`합니다. 쿼리 이름에 대 한 빈 문자열을 전달 합니다. `Append`를 호출하지 마세요.

쿼리 정의 사용 하 여를 완료 하면 호출 해당 [닫기](#close) 멤버 함수, 쿼리 정의 개체를 삭제 합니다.

> [!TIP]
>  저장 된 쿼리를 만드는 가장 쉬운 방법은 만들고 Microsoft Access를 사용 하 여 데이터베이스에 저장 됩니다. 다음을 열고 MFC 코드에서 사용 합니다.

## <a name="purposes"></a>목적

다음과 같은 목적 중 하나에 대 한 쿼리 정의 사용할 수 있습니다.

- 만들려는 `CDaoRecordset` 개체

- 개체의 호출 `Execute` 직접 쿼리가 실행 또는 SQL 통과 쿼리를 실행 하는 멤버 함수

Select, 작업, 크로스탭, 삭제, 업데이트를 포함 하 여 쿼리의 모든 형식에 대 한 쿼리 정의 사용 하 고, 테이블 만들기, 데이터 정의 SQL 통과, 공용 구조체에 추가 하 고, 대량 쿼리 수 있습니다. 쿼리 형식은 SQL 문 제공 하는 내용에 따라 결정 됩니다. 쿼리 형식에 대 한 정보를 참조 하세요. 합니다 `Execute` 하 고 [GetType](#gettype) 멤버 함수입니다. 레코드 집합 행을 반환 하는 것에 대 한 일반적으로 사용 되 쿼리, 일반적으로 사용 하는 것은 **선택...**  키워드입니다. `Execute` 대량 작업에 대 한 가장 많이 사용 됩니다. 자세한 내용은 [Execute](#execute) 하 고 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)합니다.

## <a name="querydefs-and-recordsets"></a>쿼리 정 및 레코드 집합

쿼리 정의 만드는 데는 `CDaoRecordset` 개체, 일반적으로 만들거나 위에서 설명한 것 처럼 쿼리 정의 엽니다. 다음 호출 하는 경우 쿼리 정의 개체에 대 한 포인터를 전달 recordset 개체를 생성 [cdaorecordset:: Open](../../mfc/reference/cdaorecordset-class.md#open)합니다. 전달 하면 쿼리 정의 열린 상태에서 여야 합니다. 자세한 내용은 클래스를 참조 하세요 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)합니다.

열린 상태에 있지 않다면 (쿼리 정의 대 한 가장 일반적인 사용) 레코드 집합을 만들려면 쿼리 정의 사용할 수 없습니다. 쿼리 정의 호출 하 여 열린 상태에 배치 `Open` 또는 `Create`합니다.

## <a name="external-databases"></a>외부 데이터베이스

쿼리 정의 개체는 외부 데이터베이스 엔진의 기본 SQL 언어를 사용 하는 기본 방법입니다. 예를 들어 (Microsoft SQL Server에서 사용 되는) 같은 TRANSACT-SQL 쿼리를 만들고 쿼리 정의 개체에 저장 수 있습니다. Microsoft Jet 데이터베이스 엔진을 기반으로 하지 않는 SQL 쿼리를 사용 해야 할 경우 외부 데이터 원본을 가리키는 연결 문자열을 제공 해야 합니다. 유효한 연결 문자열을 사용 하 여 쿼리 데이터베이스 엔진을 무시 하 고 처리를 위해 외부 데이터베이스 서버에 직접 쿼리를 전달 합니다.

> [!TIP]
>  ODBC 테이블 작업을 수행 하는 기본 방법은 Microsoft Jet 연결 하는 것 (합니다. MDB) 데이터베이스입니다.

관련된 정보에 대 한 "QueryDef Object", "QueryDefs 컬렉션" 및 "CdbDatabase 개체" DAO SDK에서 항목을 참조 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CDaoQueryDef`

## <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

##  <a name="append"></a>  CDaoQueryDef::Append

이 멤버 함수를 호출한 후 호출 [만들기](#create) 를 새 쿼리 정의 개체를 만듭니다.

```
virtual void Append();
```

### <a name="remarks"></a>설명

`Append` 데이터베이스의 QueryDefs 컬렉션에 개체를 추가 하 여 데이터베이스의 쿼리 정의 저장 합니다. 추가 하지 않고 임시 개체로 쿼리 정의 사용할 수 있지만 호출 해야 유지 되도록 하려는 경우 `Append`합니다.

임시 쿼리 정의 추가 하려는 경우 MFC 형식의 예외를 throw [CDaoException](../../mfc/reference/cdaoexception-class.md)합니다.

##  <a name="canupdate"></a>  CDaoQueryDef::CanUpdate

쿼리 정의 수정할 수 있는지 여부를 결정 하는이 멤버 함수를 호출 합니다.-예: 해당 이름 또는 SQL 문자열을 변경 합니다.

```
BOOL CanUpdate();
```

### <a name="return-value"></a>반환 값

쿼리 정의; 수정이 허용 된 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

경우에 쿼리 정의 수정할 수 있습니다.

- 읽기 전용으로 열려 있는 데이터베이스 따르지 않습니다.

- 데이터베이스에 대 한 권한을 업데이트 해야합니다.

   이 보안 기능 구현 했는지에 따라 달라 집니다. MFC 보안;에 대 한 지원을 제공 하지 않습니다. 구현 해야이 직접 직접 DAO 호출 또는 Microsoft Access를 사용 하 여. DAO 도움말의 "권한 속성" 항목을 참조 하세요.

##  <a name="cdaoquerydef"></a>  CDaoQueryDef::CDaoQueryDef

`CDaoQueryDef` 개체를 생성합니다.

```
CDaoQueryDef(CDaoDatabase* pDatabase);
```

### <a name="parameters"></a>매개 변수

*pDatabase*<br/>
개방적이 고 포인터로 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체입니다.

### <a name="remarks"></a>설명

개체는 데이터베이스의 QueryDefs 컬렉션, 컬렉션에 저장 될 새 쿼리 또는 임시 쿼리를 저장할 필요가 저장 하는 기존 쿼리 정의 나타낼 수 있습니다. 다음 단계는 쿼리 정의의 형식에 따라 달라 집니다.

- 개체는 기존 쿼리 정의 나타내는 개체의 호출 [열려](#open) 멤버 함수를 초기화 합니다.

- 개체를 저장할 새 쿼리 정의 나타내는 개체의 호출 [만들기](#create) 멤버 함수입니다. 이 데이터베이스의 QueryDefs 컬렉션에 개체를 추가합니다. 그런 다음 호출 `CDaoQueryDef` 개체의 특성을 설정 하는 멤버 함수입니다. 마지막으로 호출 [Append](#append)합니다.

- 개체는 임시 쿼리 정의 (데이터베이스에 저장 하지 않음)를 나타내는 경우 호출 `Create`, 쿼리 이름에 대 한 빈 문자열을 전달 합니다. 호출 후 `Create`, 직접 해당 특성을 설정 하 여 쿼리 정의 초기화 합니다. `Append`를 호출하지 마세요.

쿼리 정의의 특성을 설정 하려면 사용할 수 있습니다 합니다 [SetName](#setname)를 [SetSQL](#setsql)를 [SetConnect](#setconnect)를 [SetODBCTimeout](#setodbctimeout), 및 [SetReturnsRecords](#setreturnsrecords) 멤버 함수입니다.

쿼리 정의 개체를 완료 하면 호출 해당 [닫기](#close) 멤버 함수입니다. 쿼리 정의에 대 한 포인터를 사용 하는 경우 사용 합니다 **삭제** 제거할 연산자는 C++ 개체입니다.

##  <a name="close"></a>  CDaoQueryDef::Close

쿼리 정의 개체를 사용 하 여 완료 하면이 멤버 함수를 호출 합니다.

```
virtual void Close();
```

### <a name="remarks"></a>설명

쿼리 정의 닫으면 기본 DAO 개체를 해제 하지만 저장된 된 DAO 쿼리 정의 개체를 제거 하지 않습니다 또는 C++ `CDaoQueryDef` 개체입니다. 이것이 동일 [CDaoDatabase::DeleteQueryDef](../../mfc/reference/cdaodatabase-class.md#deletequerydef), DAO (없는 경우 임시 쿼리 정의)에서 데이터베이스의 QueryDefs 컬렉션의 쿼리 정의 삭제 하는 합니다.

##  <a name="create"></a>  CDaoQueryDef::Create

저장된 된 새 쿼리를 만들거나 새 임시 쿼리를이 멤버 함수를 호출 합니다.

```
virtual void Create(
    LPCTSTR lpszName = NULL,
    LPCTSTR lpszSQL = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
데이터베이스에 저장 된 쿼리의 고유 이름입니다. 문자열에 대 한 자세한 내용은 DAO 도움말의 "CreateQueryDef 메서드" 항목을 참조 합니다. 기본값인 빈 문자열을 수락 하는 경우에 임시 쿼리 정의 생성 됩니다. 이러한 쿼리 QueryDefs 컬렉션에 저장 되지 않습니다.

*lpszSQL*<br/>
쿼리를 정의 하는 SQL 문자열입니다. 기본값은 NULL 수락 하면 나중에 호출 해야 [SetSQL](#setsql) 문자열을 설정 합니다. 그때 까지는 쿼리 정의 되지 않습니다. 그러나; 레코드 집합을 열려고 정의 되지 않은 쿼리를 사용할 수 있습니다. 세부 정보에 대 한 설명을 참조 하세요. SQL 문은 쿼리 정의 QueryDefs 컬렉션에 추가 하기 전에 정의 되어야 합니다.

### <a name="remarks"></a>설명

이름을 전달 하는 경우 *lpszName*를 호출할 수 있습니다 [추가](#append) QueryDefs 컬렉션 데이터베이스의 쿼리 정의 저장 합니다. 그렇지 않으면 개체가 임시 쿼리 정의 이며 저장 되지 않습니다. 두 경우 모두 쿼리 정의 열린 상태로 이며 하거나 만드는 데 사용할 수는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체 또는 쿼리 정의 호출 [Execute](#execute) 멤버 함수입니다.

SQL 문을 제공 하지 않는 경우 *lpszSQL*를 사용 하 여 쿼리를 실행할 수 없습니다 `Execute` 하지만 레코드 집합을 만들려면 사용할 수 있습니다. 이 경우 MFC는 레코드 집합의 기본 SQL 문을 사용합니다.

##  <a name="execute"></a>  CDaoQueryDef::Execute

쿼리 정의 개체로 정의 된 쿼리를 실행 하려면이 멤버 함수를 호출 합니다.

```
virtual void Execute(int nOptions = dbFailOnError);
```

### <a name="parameters"></a>매개 변수

*nOptions*<br/>
쿼리의 특징을 결정 하는 정수입니다. 관련된 내용은 DAO 도움말의 "메서드 실행" 항목을 참조 합니다. 비트 OR 연산자를 사용할 수 있습니다 ( **&#124;**)이이 인수에 대 한 다음 상수를 결합 합니다.

- `dbDenyWrite` 다른 사용자에 게 쓰기 권한을 거부 합니다.

- `dbInconsistent` 일관성 없는 업데이트 합니다.

- `dbConsistent` 일관 된 업데이트 합니다.

- `dbSQLPassThrough` SQL 통과 합니다. SQL 문이 ODBC 데이터베이스 처리를 위해 전달할 수 있습니다.

- `dbFailOnError` 기본 값입니다. 롤백할 오류가 발생 하면 업데이트 및 오류 보고서 사용자에 게 합니다.

- `dbSeeChanges` 다른 사용자가 편집 하는 데이터를 변경 하는 경우 런타임 오류를 생성 합니다.

> [!NOTE]
>  조건에 대 한 설명은 "일관성이 없는" 및 "일관성" DAO 도움말의 "메서드 실행" 항목을 참조 합니다.

### <a name="remarks"></a>설명

만이 방식으로 실행을 위해 사용 되는 쿼리 정의 개체는 다음 쿼리 유형 중 하나를 나타낼 수 있습니다.

- 작업 쿼리

- SQL 통과 쿼리

`Execute` select 쿼리 등의 레코드를 반환 하는 쿼리에 대해 작동 하지 않습니다. `Execute` 일반적으로 대량 작업 쿼리의 경우와 같은 **업데이트**를 **삽입**, 또는 **SELECT INTO**, 또는 데이터 정의 언어 (DDL) 작업에 대 한 합니다.

> [!TIP]
>  ODBC 데이터 원본을 사용 하는 기본 방법은 Microsoft Jet에 테이블을 연결 하는 것 (합니다. MDB) 데이터베이스입니다. 자세한 내용은 DAO 도움말에서 "DAO 사용 하 여 외부 데이터베이스에 액세스" 항목을 참조 하세요.

호출 된 [GetRecordsAffected](#getrecordsaffected) 최신 영향을 받는 레코드의 수를 확인 하려면 쿼리 정의 개체의 멤버 함수 `Execute` 호출 합니다. 예를 들어 `GetRecordsAffected` 삭제, 업데이트 또는 삽입 작업 쿼리를 실행 하는 경우 레코드의 수에 대 한 정보를 반환 합니다. 반환 된 개수 하위를 업데이트 하거나 삭제 하는 경우 관련된 테이블의 변경 내용이 적용 하는 것을 반영 되지 않습니다.

둘 다를 포함 하는 경우 `dbInconsistent` 하 고 `dbConsistent` 결과 기본적으로 모두를 포함 하는 경우 또는 `dbInconsistent`합니다.

`Execute` 레코드 집합을 반환 하지 않습니다. 사용 하 여 `Execute` MFC 형식의 예외를 throw 하면 레코드를 선택 하는 쿼리 [CDaoException](../../mfc/reference/cdaoexception-class.md)합니다.

##  <a name="getconnect"></a>  CDaoQueryDef::GetConnect

쿼리 정의 데이터 원본과 연결 된 연결 문자열을 가져오기 위해이 멤버 함수를 호출 합니다.

```
CString GetConnect();
```

### <a name="return-value"></a>반환 값

A [CString](../../atl-mfc-shared/reference/cstringt-class.md) 쿼리 정의 대 한 연결 문자열을 포함 합니다.

### <a name="remarks"></a>설명

이 함수는 ODBC 데이터 원본 및 특정 ISAM 드라이버 에서만 사용 됩니다. Microsoft Jet을 사용 하 여 사용 되지 않습니다 (합니다. MDB) 데이터베이스 이 경우 `GetConnect` 빈 문자열을 반환 합니다. 자세한 내용은 [SetConnect](#setconnect)합니다.

> [!TIP]
>  ODBC 테이블 작업을 수행 하는 기본 방법은에 연결 하는 것을 합니다. MDB 데이터베이스입니다. 자세한 내용은 DAO 도움말에서 "DAO 사용 하 여 외부 데이터베이스에 액세스" 항목을 참조 하세요.

연결 문자열에 대 한 자세한 내용은 DAO 도움말의 "연결 속성" 항목을 참조 하세요.

##  <a name="getdatecreated"></a>  CDaoQueryDef::GetDateCreated

쿼리 정의 개체를 만든 날짜를 가져오려면이 함수를 호출 합니다.

```
COleDateTime GetDateCreated();
```

### <a name="return-value"></a>반환 값

A [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 쿼리 정의 생성 된 시간과 날짜를 포함 하는 개체입니다.

### <a name="remarks"></a>설명

관련된 내용은 DAO 도움말의 "DateCreated LastUpdated 속성" 항목을 참조 합니다.

##  <a name="getdatelastupdated"></a>  CDaoQueryDef::GetDateLastUpdated

이 멤버 함수 개체를 가져와 날짜 쿼리 정의 마지막으로 업데이트 하는 호출-때의 모든 속성 변경 된 해당 이름, 해당 SQL 문자열 또는 연결 문자열 등입니다.

```
COleDateTime GetDateLastUpdated();
```

### <a name="return-value"></a>반환 값

A [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 쿼리 정의가 마지막으로 업데이트 된 시간과 날짜를 포함 하는 개체입니다.

### <a name="remarks"></a>설명

관련된 내용은 DAO 도움말의 "DateCreated LastUpdated 속성" 항목을 참조 합니다.

##  <a name="getfieldcount"></a>  CDaoQueryDef::GetFieldCount

쿼리에서 필드 수를 검색 하려면이 멤버 함수를 호출 합니다.

```
short GetFieldCount();
```

### <a name="return-value"></a>반환 값

쿼리에 정의 된 필드 수입니다.

### <a name="remarks"></a>설명

`GetFieldCount` 쿼리 정의의 모든 필드를 반복 하는 데 유용 합니다. 이 위해 사용 하 여 `GetFieldCount` 와 함께에서 [GetFieldInfo](#getfieldinfo)합니다.

##  <a name="getfieldinfo"></a>  CDaoQueryDef::GetFieldInfo

다양 한 종류의 쿼리 정의에 정의 된 필드에 대 한 정보를 가져오려면이 함수를 호출 합니다.

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
인덱스에서 조회에 대 한 쿼리 정의 필드 컬렉션에서 원하는 필드의 0부터 시작 하는 인덱스입니다.

*fieldinfo*<br/>
에 대 한 참조를 `CDaoFieldInfo` 요청 된 정보를 반환 하는 개체입니다.

*dwInfoOptions*<br/>
검색할 필드에 대 한 정보를 지정 하는 옵션입니다. 사용 가능한 옵션은 어떤 문제를 일으킬 있습니다를 반환 하는 함수 함께 나와 있습니다.

- (기본값) AFX_DAO_PRIMARY_INFO 이름, 유형, 크기, 특성

- 더하기 AFX_DAO_SECONDARY_INFO 기본 정보: 필요한 서 수 위치 0 길이, 원본 필드, 외부 이름, 원본 테이블에 정렬 순서를 허용 합니다.

- AFX_DAO_ALL_INFO 기본 및 보조 데이터베이스 정보가 더하기: 기본 값, 유효성 검사 텍스트, 유효성 검사 규칙

*lpszName*<br/>
이름별 조회에 대 한 원하는 필드의 이름을 포함 하는 문자열입니다. 사용할 수는 [CString](../../atl-mfc-shared/reference/cstringt-class.md)합니다.

### <a name="remarks"></a>설명

반환 되는 정보에 대 한 *fieldinfo*를 참조 합니다 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) 구조입니다. 이 구조에서 설명이 포함 된 정보에 해당 하는 멤버가 *dwInfoOptions* 위에 있습니다. 한 수준의 정보를 요청 하는 경우 모든 이전 수준의 정보를 가져옵니다.

##  <a name="getname"></a>  CDaoQueryDef::GetName

쿼리 정의 나타내는 쿼리 이름을 검색 하려면이 멤버 함수를 호출 합니다.

```
CString GetName();
```

### <a name="return-value"></a>반환 값

쿼리의 이름입니다.

### <a name="remarks"></a>설명

쿼리 정의 이름은 고유 사용자 정의 이름입니다. 쿼리 정의 이름에 대 한 자세한 내용은 DAO 도움말에서 "이름 속성" 항목을 참조 하세요.

##  <a name="getodbctimeout"></a>  CDaoQueryDef::GetODBCTimeout

ODBC 데이터 원본에 쿼리 시간이 초과 되기 전에 현재 제한 시간을 검색 하려면이 멤버 함수를 호출 합니다.

```
short GetODBCTimeout();
```

### <a name="return-value"></a>반환 값

차이인 초를 쿼리 하기 전에 시간이 초과 됩니다.

### <a name="remarks"></a>설명

이 시간 제한에 대 한 내용은 DAO 도움말의 "ODBCTimeout 속성" 항목을 참조 하세요.

> [!TIP]
>  ODBC 테이블 작업을 수행 하는 기본 방법은 Microsoft Jet 연결 하는 것 (합니다. MDB) 데이터베이스입니다. 자세한 내용은 DAO 도움말에서 "DAO 사용 하 여 외부 데이터베이스에 액세스" 항목을 참조 하세요.

##  <a name="getparametercount"></a>  CDaoQueryDef::GetParameterCount

저장된 된 쿼리 매개 변수 개수를 검색 하려면이 멤버 함수를 호출 합니다.

```
short GetParameterCount();
```

### <a name="return-value"></a>반환 값

쿼리에 정의 된 매개 변수의 수입니다.

### <a name="remarks"></a>설명

`GetParameterCount` 쿼리 정의에서 모든 매개 변수를 반복 하는 데 유용 합니다. 이 위해 사용 하 여 `GetParameterCount` 와 함께에서 [GetParameterInfo](#getparameterinfo)합니다.

관련된 정보에 대 한 "매개 변수 개체", "매개 변수 컬렉션" 및 "매개 변수 선언 ()"에서 SQL DAO 도움말 항목을 참조 합니다.

##  <a name="getparameterinfo"></a>  CDaoQueryDef::GetParameterInfo

쿼리 정의에 정의 된 매개 변수 정보를 가져오려면이 함수를 호출 합니다.

```
void GetParameterInfo(
    int nIndex,
    CDaoParameterInfo& paraminfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

void GetParameterInfo(
    LPCTSTR lpszName,
    CDaoParameterInfo& paraminfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>매개 변수

*nIndex*<br/>
인덱스에서 조회에 대 한 쿼리 정의 매개 변수 컬렉션에서 원하는 매개 변수의 0부터 시작 하는 인덱스입니다.

*paraminfo*<br/>
에 대 한 참조를 [CDaoParameterInfo](../../mfc/reference/cdaoparameterinfo-structure.md) 요청 된 정보를 반환 하는 개체입니다.

*dwInfoOptions*<br/>
검색할 매개 변수에 대 한 정보를 지정 하는 옵션입니다. 사용 가능한 옵션은 다음과 같습니다. 함수가를 반환 하면 새로운 함께

- (기본값) AFX_DAO_PRIMARY_INFO 이름, 형식

*lpszName*<br/>
이름별 조회에 대 한 원하는 매개 변수의 이름을 포함 하는 문자열입니다. 사용할 수는 [CString](../../atl-mfc-shared/reference/cstringt-class.md)합니다.

### <a name="remarks"></a>설명

반환 되는 정보에 대 한 *paraminfo*를 참조 합니다 [CDaoParameterInfo](../../mfc/reference/cdaoparameterinfo-structure.md) 구조입니다. 이 구조에서 설명이 포함 된 정보에 해당 하는 멤버가 *dwInfoOptions* 위에 있습니다.

관련된 내용은 "매개 변수 선언 ()"에서 SQL DAO 도움말 항목을 참조 하세요.

##  <a name="getparamvalue"></a>  CDaoQueryDef::GetParamValue

쿼리 정의 매개 변수 컬렉션에 저장 된 지정된 된 매개 변수의 현재 값을 검색 하려면이 멤버 함수를 호출 합니다.

```
virtual COleVariant GetParamValue(LPCTSTR lpszName);
virtual COleVariant GetParamValue(int nIndex);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
매개 변수 이름으로 조회에 대해 원하는 값의 이름입니다.

*nIndex*<br/>
인덱스에서 조회에 대 한 쿼리 정의 매개 변수 컬렉션에서 매개 변수의 0부터 시작 하는 인덱스입니다. 호출 하 여이 값을 가져올 수 있습니다 [GetParameterCount](#getparametercount) 하 고 [GetParameterInfo](#getparameterinfo)합니다.

### <a name="return-value"></a>반환 값

클래스의 개체 [COleVariant](../../mfc/reference/colevariant-class.md) 매개 변수의 값이 들어 있는입니다.

### <a name="remarks"></a>설명

매개 변수 이름 또는 컬렉션의 서 수 위치에 액세스할 수 있습니다.

관련된 내용은 "매개 변수 선언 ()"에서 SQL DAO 도움말 항목을 참조 하세요.

##  <a name="getrecordsaffected"></a>  CDaoQueryDef::GetRecordsAffected

마지막 호출 영향을 받는 레코드 수를 확인 하려면이 멤버 함수 호출 [Execute](#execute)합니다.

```
long GetRecordsAffected();
```

### <a name="return-value"></a>반환 값

영향을 받은 레코드 수입니다.

### <a name="remarks"></a>설명

반환 된 개수 하위를 업데이트 하거나 삭제 하는 경우 관련된 테이블의 변경 내용이 적용 하는 것을 반영 되지 않습니다.

관련된 내용은 DAO 도움말의 "RecordsAffected Property" 항목을 참조 하세요.

##  <a name="getreturnsrecords"></a>  CDaoQueryDef::GetReturnsRecords

쿼리 정의 레코드를 반환 하는 쿼리 기반 인지 여부를 확인 하려면이 멤버 함수를 호출 합니다.

```
BOOL GetReturnsRecords();
```

### <a name="return-value"></a>반환 값

쿼리 정의 쿼리를 기반으로 하는 경우 0이 아닌 반환 하는 레코드입니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 멤버 함수는 통과 쿼리를 SQL에만 사용 됩니다. SQL 쿼리에 대 한 자세한 내용은 참조는 [Execute](#execute) 멤버 함수입니다. SQL 통과 쿼리를 사용 하 여 작업에 대 한 자세한 내용은 참조는 [SetReturnsRecords](#setreturnsrecords) 멤버 함수입니다.

관련된 내용은 DAO 도움말의 "ReturnsRecords Property" 항목을 참조 합니다.

##  <a name="getsql"></a>  CDaoQueryDef::GetSQL

쿼리 정의 기반이 되는 쿼리를 정의 하는 SQL 문을 검색 하려면이 멤버 함수를 호출 합니다.

```
CString GetSQL();
```

### <a name="return-value"></a>반환 값

쿼리 정의 기반이 되는 쿼리를 정의 하는 SQL 문입니다.

### <a name="remarks"></a>설명

다음 키워드, 테이블 이름 등에 대 한 문자열을 parse 것입니다.

관련 내용은 "SQL 속성", "비교의 Microsoft Jet 데이터베이스 엔진 SQL 및 ANSI SQL" 및 "쿼리는 데이터베이스와 SQL 코드" DAO 도움말 항목을 참조 합니다.

##  <a name="gettype"></a>  CDaoQueryDef::GetType

쿼리 정의의 쿼리 유형을 결정 하려면이 멤버 함수를 호출 합니다.

```
short GetType();
```

### <a name="return-value"></a>반환 값

쿼리 정의에서 정의 된 쿼리 형식입니다. 값에 대 한 설명을 참조 하세요.

### <a name="remarks"></a>설명

쿼리 유형에 어떤 문자열에서 지정 된 쿼리 정의 SQL 쿼리 정의 만들거나는 기존 쿼리 정의 호출 하는 경우 설정한 [SetSQL](#setsql) 멤버 함수입니다. 이 함수에 의해 반환 되는 쿼리 형식에는 다음 값 중 하나일 수 있습니다.

- `dbQSelect` 선택

- `dbQAction` 작업

- `dbQCrosstab` 크로스탭

- `dbQDelete` Delete

- `dbQUpdate` 업데이트

- `dbQAppend` 추가

- `dbQMakeTable` 테이블 만들기

- `dbQDDL` 데이터 정의

- `dbQSQLPassThrough` 통과

- `dbQSetOperation` 공용 구조체

- `dbQSPTBulk` 사용한 `dbQSQLPassThrough` 레코드를 반환 하지 않는 쿼리를 지정 합니다.

> [!NOTE]
>  설정 하지 않은 SQL 통과 쿼리를 만들려면를 `dbSQLPassThrough` 상수입니다. 이 설정은 자동으로 Microsoft Jet 데이터베이스 엔진에 의해 querydef 개체를 만들고 연결 문자열을 설정 합니다.

SQL 문자열에 대 한 자세한 내용은 [GetSQL](#getsql)합니다. 쿼리 형식에 대 한 정보를 참조 하세요 [Execute](#execute)합니다.

##  <a name="isopen"></a>  CDaoQueryDef::IsOpen

확인 하려면이 멤버 함수를 호출 여부를 `CDaoQueryDef` 개체가 현재 열려 있습니다.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>반환 값

0이 아닌 값을 `CDaoQueryDef` 개체가 현재 열려 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

쿼리 정의 호출에 사용 하기 전에 열린 상태에서 여야 합니다 [Execute](#execute) 만들려면를 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체입니다. 넣을 쿼리 정의 열린 상태로 호출 하거나 [만들기](#create) (예: 새 쿼리 정의) 또는 [엽니다](#open) (에 기존 쿼리 정의).

##  <a name="m_pdatabase"></a>  CDaoQueryDef::m_pDatabase

에 대 한 포인터를 포함 합니다 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 쿼리 정의 개체와 연결 된 개체입니다.

### <a name="remarks"></a>설명

데이터베이스에 직접 액세스 해야 할 경우에이 포인터를 사용 하 여-예를 들어, 다른 쿼리 정의 또는 레코드 집합에 대 한 포인터를 가져올 데이터베이스의 컬렉션 개체입니다.

##  <a name="m_pdaoquerydef"></a>  CDaoQueryDef::m_pDAOQueryDef

OLE 인터페이스 기본 DAO 쿼리 정의 개체에 대 한 포인터를 포함합니다.

### <a name="remarks"></a>설명

이 포인터 완결성 및 다른 클래스와의 일관성을 위해 제공 됩니다. 그러나 MFC DAO 쿼리 정의 보다 완벽 하 게 캡슐화 하므로 없는 필요할 수 있습니다. 를 사용는 경우 이렇게 신중 하 게, 수행 하는 경우가 포인터의 값을 변경 하지 마십시오 특히 합니다.

##  <a name="open"></a>  CDaoQueryDef::Open

데이터베이스의 QueryDefs 컬렉션에서 이전에 저장 된 쿼리 정의 열려면이 멤버 함수를 호출 합니다.

```
virtual void Open(LPCTSTR lpszName = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
열려는 저장 된 쿼리 정의의 이름을 포함 하는 문자열입니다. 사용할 수는 [CString](../../atl-mfc-shared/reference/cstringt-class.md)합니다.

### <a name="remarks"></a>설명

호출할 수 있습니다 쿼리 정의 연 후 해당 [Execute](#execute) 만들려는 쿼리 정의 사용 하 여 또는 멤버 함수는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 개체입니다.

##  <a name="setconnect"></a>  CDaoQueryDef::SetConnect

쿼리 정의 개체의 연결 문자열을 설정 하려면이 멤버 함수를 호출 합니다.

```
void SetConnect(LPCTSTR lpszConnect);
```

### <a name="parameters"></a>매개 변수

*lpszConnect*<br/>
연결 된 연결 문자열을 포함 하는 문자열 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체입니다.

### <a name="remarks"></a>설명

ODBC 및 필요에 따라 특정 ISAM 드라이버 추가 정보를 전달 하는 연결 문자열 사용 됩니다. Microsoft Jet 용 사용 되지 않습니다 (합니다. MDB) 데이터베이스입니다.

> [!TIP]
>  ODBC 테이블 작업을 수행 하는 기본 방법은에 연결 하는 것을 합니다. MDB 데이터베이스입니다.

ODBC 데이터 원본에 SQL 통과 쿼리를 나타내는 쿼리 정의 실행 하기 전에 연결 문자열 설정 `SetConnect` 호출 [SetReturnsRecords](#setreturnsrecords) 쿼리 레코드를 반환 하는지 여부를 지정 합니다.

연결 문자열의 구조 및 연결 문자열 구성 요소 예제에 대 한 자세한 내용은 DAO 도움말의 "연결 속성" 항목을 참조 하세요.

##  <a name="setname"></a>  CDaoQueryDef::SetName

임시 없는 쿼리 정의의 이름을 변경 하려는 경우이 멤버 함수를 호출 합니다.

```
void SetName(LPCTSTR lpszName);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
연결 된 실제적 쿼리에 대 한 새 이름을 포함 하는 문자열로 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체입니다.

### <a name="remarks"></a>설명

쿼리 정의 이름은 고유한, 사용자 정의 이름입니다. 호출할 수 있습니다 `SetName` 쿼리 정의 하기 전에 개체 QueryDefs 컬렉션에 추가 됩니다.

##  <a name="setodbctimeout"></a>  CDaoQueryDef::SetODBCTimeout

ODBC 데이터 원본에 쿼리 시간이 초과 되기까지의 시간 제한을 설정 하려면이 멤버 함수를 호출 합니다.

```
void SetODBCTimeout(short nODBCTimeout);
```

### <a name="parameters"></a>매개 변수

*nODBCTimeout*<br/>
차이인 초를 쿼리 하기 전에 시간이 초과 됩니다.

### <a name="remarks"></a>설명

이 멤버 함수를 사용 하면 연결 된 데이터 원본 "시간이 초과 됩니다."에 대 한 후속 작업 (초) 기본값 재정의 네트워크 액세스 문제, 과도 한 쿼리 처리 시간 등으로 인해 작업 시간이 초과 될 수 있습니다. 호출 `SetODBCTimeout` 쿼리 제한 시간 값을 변경 하려는 경우이 쿼리 정의 사용 하 여 쿼리를 실행 하기 전에 합니다. (ODBC 연결을 다시 사용, 시간 제한 값을는 같은 연결에서 모든 클라이언트에 대해 동일 합니다.)

쿼리 제한 시간에 대 한 기본값은 60 초입니다.

##  <a name="setparamvalue"></a>  CDaoQueryDef::SetParamValue

런타임에 쿼리 정의에서 매개 변수의 값을 설정 하려면이 멤버 함수를 호출 합니다.

```
virtual void SetParamValue(
    LPCTSTR lpszName,
    const COleVariant& varValue);

virtual void SetParamValue(
    int nIndex,
    const COleVariant& varValue);
```

### <a name="parameters"></a>매개 변수

*lpszName*<br/>
설정 하려는 값 매개 변수의 이름입니다.

*varValue*<br/>
값을 설정 설명을 참조 하세요.

*nIndex*<br/>
쿼리 정의 매개 변수 컬렉션에서 매개 변수의 서 수 위치입니다. 호출 하 여이 값을 가져올 수 있습니다 [GetParameterCount](#getparametercount) 하 고 [GetParameterInfo](#getparameterinfo)합니다.

### <a name="remarks"></a>설명

매개 변수는 쿼리 정의 SQL 문자열의 일부로 설정 이미 있어야 합니다. 매개 변수 이름 또는 컬렉션의 서 수 위치에 액세스할 수 있습니다.

로 설정 하려면 값을 지정 된 `COleVariant` 개체입니다. 형식을 확인 하 고 원하는 값을 설정 하는 방법에 대 한 정보에 대 한 사용자 `COleVariant` 개체 클래스를 참조 하십시오 [COleVariant](../../mfc/reference/colevariant-class.md)합니다.

##  <a name="setreturnsrecords"></a>  CDaoQueryDef::SetReturnsRecords

외부 데이터베이스에 SQL 통과 쿼리를 설정 하는 프로세스의 일부로이 멤버 함수를 호출 합니다.

```
void SetReturnsRecords(BOOL bReturnsRecords);
```

### <a name="parameters"></a>매개 변수

*bReturnsRecords*<br/>
외부 데이터베이스의 쿼리를 레코드로 반환 하는 경우 TRUE를 전달합니다 그렇지 않으면 FALSE입니다.

### <a name="remarks"></a>설명

이러한 경우 쿼리 정의 만들기 및 다른를 사용 하 여 해당 속성을 설정 해야 합니다 `CDaoQueryDef` 멤버 함수입니다. 외부 데이터베이스에 대 한 참조 [SetConnect](#setconnect)합니다.

##  <a name="setsql"></a>  CDaoQueryDef::SetSQL

쿼리 정의 실행 하는 SQL 문을 설정 하려면이 멤버 함수를 호출 합니다.

```
void SetSQL(LPCTSTR lpszSQL);
```

### <a name="parameters"></a>매개 변수

*lpszSQL*<br/>
실행에 적합 한 전체 SQL 문을 포함 하는 문자열입니다. 이 문자열의 구문은 DBMS에 따라 하는 쿼리 대상입니다. Microsoft Jet 데이터베이스 엔진에서 사용 되는 구문의 자세한 내용은 "SQL 문의 코드 빌드" DAO 도움말의 항목을 참조 합니다.

### <a name="remarks"></a>설명

일반적인 사용 `SetSQL` SQL 통과 쿼리에서 사용 하기 위해 쿼리 정의 설정 합니다. (대상 DBMS에서 SQL 통과 쿼리의 구문을 DBMS에 대 한 설명서 참조).

## <a name="see-also"></a>참고자료

[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CDaoRecordset 클래스](../../mfc/reference/cdaorecordset-class.md)<br/>
[CDaoDatabase 클래스](../../mfc/reference/cdaodatabase-class.md)<br/>
[CDaoTableDef 클래스](../../mfc/reference/cdaotabledef-class.md)<br/>
[CDaoException 클래스](../../mfc/reference/cdaoexception-class.md)
