---
title: CDatabase 클래스
ms.date: 11/04/2016
f1_keywords:
- CDatabase
- AFXDB/CDatabase
- AFXDB/CDatabase::CDatabase
- AFXDB/CDatabase::BeginTrans
- AFXDB/CDatabase::BindParameters
- AFXDB/CDatabase::Cancel
- AFXDB/CDatabase::CanTransact
- AFXDB/CDatabase::CanUpdate
- AFXDB/CDatabase::Close
- AFXDB/CDatabase::CommitTrans
- AFXDB/CDatabase::ExecuteSQL
- AFXDB/CDatabase::GetBookmarkPersistence
- AFXDB/CDatabase::GetConnect
- AFXDB/CDatabase::GetCursorCommitBehavior
- AFXDB/CDatabase::GetCursorRollbackBehavior
- AFXDB/CDatabase::GetDatabaseName
- AFXDB/CDatabase::IsOpen
- AFXDB/CDatabase::OnSetOptions
- AFXDB/CDatabase::Open
- AFXDB/CDatabase::OpenEx
- AFXDB/CDatabase::Rollback
- AFXDB/CDatabase::SetLoginTimeout
- AFXDB/CDatabase::SetQueryTimeout
- AFXDB/CDatabase::m_hdbc
helpviewer_keywords:
- CDatabase [MFC], CDatabase
- CDatabase [MFC], BeginTrans
- CDatabase [MFC], BindParameters
- CDatabase [MFC], Cancel
- CDatabase [MFC], CanTransact
- CDatabase [MFC], CanUpdate
- CDatabase [MFC], Close
- CDatabase [MFC], CommitTrans
- CDatabase [MFC], ExecuteSQL
- CDatabase [MFC], GetBookmarkPersistence
- CDatabase [MFC], GetConnect
- CDatabase [MFC], GetCursorCommitBehavior
- CDatabase [MFC], GetCursorRollbackBehavior
- CDatabase [MFC], GetDatabaseName
- CDatabase [MFC], IsOpen
- CDatabase [MFC], OnSetOptions
- CDatabase [MFC], Open
- CDatabase [MFC], OpenEx
- CDatabase [MFC], Rollback
- CDatabase [MFC], SetLoginTimeout
- CDatabase [MFC], SetQueryTimeout
- CDatabase [MFC], m_hdbc
ms.assetid: bd0de70a-e3c3-4441-bcaa-bbf434426ca8
ms.openlocfilehash: ebc36d82af9bfe12ab30a86214e58610b5eaab95
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62253716"
---
# <a name="cdatabase-class"></a>CDatabase 클래스

데이터 소스 작업을 할 수 있는 통로인 데이터 소스에 대한 연결을 나타냅니다.

## <a name="syntax"></a>구문

```
class CDatabase : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CDatabase::CDatabase](#cdatabase)|`CDatabase` 개체를 생성합니다. 호출 하 여 개체를 초기화 해야 합니다 `OpenEx` 또는 `Open`합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CDatabase::BeginTrans](#begintrans)|"트랜잭션" 시작-일련의 호출을 취소할 수는 `AddNew`, `Edit`를 `Delete`, 및 `Update` 클래스의 멤버 함수 `CRecordset` -연결된 된 데이터 원본에서. 데이터 원본에 대 한 트랜잭션을 지원 해야 `BeginTrans` 을 적용 합니다.|
|[CDatabase::BindParameters](#bindparameters)|호출 하기 전에 매개 변수를 바인딩할 수 있도록 `CDatabase::ExecuteSQL`입니다.|
|[CDatabase::Cancel](#cancel)|비동기 작업 또는 두 번째 스레드에서 프로세스를 취소합니다.|
|[CDatabase::CanTransact](#cantransact)|데이터 소스에서 트랜잭션을 지원 하면 0이 아닌 값을 반환 합니다.|
|[CDatabase::CanUpdate](#canupdate)|0이 아닌 경우 반환 된 `CDatabase` 개체는 업데이트할 수 있는 (읽기 전용이 아닌).|
|[CDatabase::Close](#close)|데이터 원본 연결을 닫습니다.|
|[CDatabase::CommitTrans](#committrans)|으로 시작 된 트랜잭션을 완료 `BeginTrans`합니다. 데이터 원본을 변경 하는 트랜잭션에 명령은 수행 됩니다.|
|[CDatabase::ExecuteSQL](#executesql)|SQL 문을 실행합니다. 데이터 레코드가 반환 됩니다.|
|[CDatabase::GetBookmarkPersistence](#getbookmarkpersistence)|책갈피가 레코드 집합 개체에 유지 하는 작업을 식별 합니다.|
|[CDatabase::GetConnect](#getconnect)|연결 하는 데 사용 하는 ODBC 연결 문자열을 반환 합니다 `CDatabase` 데이터 원본에 개체입니다.|
|[CDatabase::GetCursorCommitBehavior](#getcursorcommitbehavior)|열린 레코드 집합 개체에서 트랜잭션 커밋의 효과 식별 합니다.|
|[CDatabase::GetCursorRollbackBehavior](#getcursorrollbackbehavior)|열린 레코드 집합 개체에는 트랜잭션 롤백 효과 식별 합니다.|
|[CDatabase::GetDatabaseName](#getdatabasename)|현재 사용 중인 데이터베이스의 이름을 반환합니다.|
|[CDatabase::IsOpen](#isopen)|0이 아닌 경우 반환 된 `CDatabase` 개체 데이터 소스에 현재 연결 되어 있습니다.|
|[CDatabase::OnSetOptions](#onsetoptions)|표준 연결 옵션을 설정 하기 위해 프레임 워크에서 호출 됩니다. 기본 구현은 쿼리 제한 시간 값을 설정합니다. 호출 하 여 사전에 이러한 옵션을 설정할 수 있습니다 `SetQueryTimeout`합니다.|
|[CDatabase::Open](#open)|(ODBC 드라이버)를 통해 데이터 원본에 연결합니다.|
|[CDatabase::OpenEx](#openex)|(ODBC 드라이버)를 통해 데이터 원본에 연결합니다.|
|[CDatabase::Rollback](#rollback)|현재 트랜잭션 중 변경 내용을 취소 합니다. 데이터 원본에 정의 된 대로를 이전 상태로 반환는 `BeginTrans` 변경 되지 않고 호출 합니다.|
|[CDatabase::SetLoginTimeout](#setlogintimeout)|데이터 원본 연결 시도 시간 초과가 발생 하는 시간 (초) 수를 설정 합니다.|
|[CDatabase::SetQueryTimeout](#setquerytimeout)|초 후 데이터베이스 쿼리 작업 집합에는 시간이 초과 됩니다. 이후의 모든 레코드 집합에 영향을 줍니다 `Open`, `AddNew`를 `Edit`, 및 `Delete` 호출 합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CDatabase::m_hdbc](#m_hdbc)|데이터 원본에 대 한 데이터베이스 연결 (ODBC) 연결 핸들을 엽니다. 형식 *HDBC*합니다.|

## <a name="remarks"></a>설명

데이터 소스는 일부 데이터베이스 관리 시스템 (DBMS)에서 호스트 되는 데이터의 특정 인스턴스입니다. Microsoft SQL Server, Microsoft Access, Borland dBASE 및 xBASE을 예로 들 수 있습니다. 하나 이상의 있습니다 `CDatabase` 응용 프로그램에서 한 번에 활성 개체입니다.

> [!NOTE]
>  클래스를 사용 하 여 열린 데이터베이스 연결 (ODBC) 클래스가 아니라 데이터 액세스 개체 (DAO) 클래스를 사용 하 여 작업 하는 경우 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 대신 합니다. 자세한 내용은 문서를 참조 하세요. [개요: 데이터베이스 프로그래밍](../../data/data-access-programming-mfc-atl.md)합니다.

사용 하도록 `CDatabase`, 생성을 `CDatabase` 개체와 호출 해당 `OpenEx` 멤버 함수입니다. 이 연결을 엽니다. 그런 다음 생성 하는 경우 `CRecordset` 연결 된 데이터 원본에서 운영 하는 것에 대 한 개체 생성자에 전달 하십시오 레코드 집합에 대 한 포인터에 `CDatabase` 개체입니다. 과정을 마치면 연결을 사용 하 여 호출 합니다 `Close` 멤버 함수를 제거는 `CDatabase` 개체입니다. `Close` 이전에 닫지 않은 모든 레코드 집합을 닫습니다.

에 대 한 자세한 내용은 `CDatabase`, 문서를 참조 하세요 [데이터 원본 (ODBC)](../../data/odbc/data-source-odbc.md) 고 [개요: 데이터베이스 프로그래밍](../../data/data-access-programming-mfc-atl.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CDatabase`

## <a name="requirements"></a>요구 사항

**헤더:** afxdb.h

##  <a name="begintrans"></a>  CDatabase::BeginTrans

연결된 된 데이터 소스를 사용 하 여 트랜잭션을 시작 하려면이 멤버 함수를 호출 합니다.

```
BOOL BeginTrans();
```

### <a name="return-value"></a>반환 값

변경 내용이 커밋되기만 수동으로; 호출이 성공한 경우 0이 아닌 값 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

트랜잭션 구성에 대 한 하나 이상의 호출을 `AddNew`, `Edit`, `Delete`, 및 `Update` 의 멤버 함수는 `CRecordset` 개체입니다. 트랜잭션을 시작 하기 전에 합니다 `CDatabase` 개체 해야 이미 대부분이에 연결 될 데이터 소스를 호출 하 여 해당 `OpenEx` 또는 `Open` 멤버 함수입니다. 트랜잭션이 호출 [CommitTrans](#committrans) 데이터 원본에 대 한 변경 내용 모두 적용 (및 작업) 호출 또는 [롤백](#rollback) 전체 트랜잭션을 중단 합니다. 호출 `BeginTrans` 후 트랜잭션에 관련된 된 모든 레코드 집합을 열고으로 실제 가까운 업데이트 작업 가능한 합니다.

> [!CAUTION]
>  ODBC 드라이버에 따라 호출 하기 전에 레코드 집합 열기 `BeginTrans` 호출할 때 문제가 발생할 수 있습니다 `Rollback`합니다. 사용 하는 특정 드라이버를 확인 해야 합니다. 예를 들어 Microsoft ODBC Desktop Driver Pack 3.0에 포함 된 Microsoft Access 드라이버를 사용할 때 열린 커서에 있는 모든 데이터베이스에서 트랜잭션을 시작 하지 해야 하는 Jet 데이터베이스 엔진의 요구 사항에 대해 고려해 야 합니다. MFC 데이터베이스 클래스에서 열린 커서 의미 개방적이 고 `CRecordset` 개체입니다. 자세한 내용은 [기술 참고 68](../../mfc/tn068-performing-transactions-with-the-microsoft-access-7-odbc-driver.md)합니다.

`BeginTrans` 요청 된 동시성 및 데이터 원본 기능에 따라 서버에서 데이터 레코드를 잠글 수도 있습니다. 잠금 데이터에 대 한 자세한 문서를 참고 [레코드 집합: 레코드 잠금 (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)합니다.

사용자 정의 트랜잭션 문서에서 설명 됩니다 [트랜잭션 (ODBC)](../../data/odbc/transaction-odbc.md)합니다.

`BeginTrans` 상태는 트랜잭션 시퀀스 롤백할 수 설정 (반대로). 모든 현재 트랜잭션이 커밋 롤백에 대 한 새 상태를 설정 하려면 다음 호출 `BeginTrans` 다시 합니다.

> [!CAUTION]
>  호출 `BeginTrans` 호출 하지 않고 다시 `CommitTrans` 또는 `Rollback` 오류가 발생 합니다.

호출 된 [CanTransact](#cantransact) 드라이버 지정된 된 데이터베이스에 대 한 트랜잭션을 지원 하는지 여부를 결정 하는 멤버 함수입니다. 또한를 호출 해야 [GetCursorCommitBehavior](#getcursorcommitbehavior) 하 고 [GetCursorRollbackBehavior](#getcursorrollbackbehavior) 커서 보존에 대 한 지원을 확인 하기 위해.

트랜잭션에 대 한 자세한 내용은 문서 참조 [트랜잭션 (ODBC)](../../data/odbc/transaction-odbc.md)합니다.

### <a name="example"></a>예제

  문서를 참조 [트랜잭션: 레코드 집합 (ODBC)에서 트랜잭션 수행](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)합니다.

##  <a name="bindparameters"></a>  CDatabase::BindParameters

재정의 `BindParameters` 해야 할 때 호출 하기 전에 매개 변수를 바인딩할 [CDatabase::ExecuteSQL](#executesql)합니다.

```
virtual void BindParameters(HSTMT hstmt);
```

### <a name="parameters"></a>매개 변수

*hstmt*<br/>
매개 변수를 바인딩하 시겠습니까 ODBC 문 핸들입니다.

### <a name="remarks"></a>설명

결과 필요 하지 않은 경우이 방법은 유용 합니다. 저장된 프로시저에서 설정 합니다.

재정의 호출 `SQLBindParameters` 및 관련 매개 변수를 바인딩할 ODBC 함수입니다. 호출 하기 전에 재정의 호출 하는 MFC `ExecuteSQL`합니다. 호출할 필요가 없습니다 `SQLPrepare`; `ExecuteSQL` 호출 `SQLExecDirect` 하 고 제거 합니다 *hstmt*를 한 번만 사용 됩니다.

##  <a name="cancel"></a>  CDatabase::Cancel

데이터 소스는 진행 중인 비동기 작업 또는 프로세스를 두 번째 스레드에서 취소를 요청 하려면이 멤버 함수를 호출 합니다.

```
void Cancel();
```

### <a name="remarks"></a>설명

MFC ODBC 클래스에 비동기 처리를 사용 하지는 note 비동기 작업을 수행 하려면 직접 ODBC API 함수를 호출 해야 [SQLSetConnectOption](/sql/odbc/reference/syntax/sqlsetconnectoption-function)합니다. 자세한 내용은 [비동기 실행](/sql/odbc/reference/develop-app/asynchronous-execution)합니다.

##  <a name="cantransact"></a>  CDatabase::CanTransact

데이터베이스 트랜잭션이 있는지 여부를 확인 하려면이 멤버 함수를 호출 합니다.

```
BOOL CanTransact() const;
```

### <a name="return-value"></a>반환 값

0이 아닌 경우가를 사용 하 여 레코드 집합 `CDatabase` 개체 트랜잭션을 허용 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

트랜잭션에 대 한 자세한 문서를 참조 [트랜잭션 (ODBC)](../../data/odbc/transaction-odbc.md)합니다.

##  <a name="canupdate"></a>  CDatabase::CanUpdate

확인 하려면이 멤버 함수를 호출 하는지 여부를 `CDatabase` 개체 업데이트를 허용 합니다.

```
BOOL CanUpdate() const;
```

### <a name="return-value"></a>반환 값

0이 아닌 값을 `CDatabase` 업데이트를 허용 하는 개체, 그렇지 않으면 0, 어느 것을 나타내는 전달 TRUE *bReadOnly* 열릴 때를 `CDatabase` 개체 또는 데이터 원본 자체는 읽기 전용입니다. 데이터 소스는 ODBC API 함수를 호출 하는 경우 읽기 전용 `SQLGetInfo` SQL_DATASOURCE_READ_ONLY "y"를 반환 합니다.

### <a name="remarks"></a>설명

일부 드라이버 업데이트를 지원 합니다.

##  <a name="cdatabase"></a>  CDatabase::CDatabase

`CDatabase` 개체를 생성합니다.

```
CDatabase();
```

### <a name="remarks"></a>설명

호출 해야 개체를 생성 한 후 해당 `OpenEx` 또는 `Open` 멤버 함수는 지정 된 데이터 원본에 연결 합니다.

편리할 수 있습니다 것 포함 하는 `CDatabase` 문서 클래스에는 개체입니다.

### <a name="example"></a>예제

이 예제를 사용 하 여 `CDatabase` 에 `CDocument`-클래스를 파생 합니다.

[!code-cpp[NVC_MFCDatabase#9](../../mfc/codesnippet/cpp/cdatabase-class_1.h)]

[!code-cpp[NVC_MFCDatabase#10](../../mfc/codesnippet/cpp/cdatabase-class_2.cpp)]

##  <a name="close"></a>  CDatabase::Close

데이터 원본에서 분리 하려는 경우이 멤버 함수를 호출 합니다.

```
virtual void Close();
```

### <a name="remarks"></a>설명

관련 된 모든 레코드 집합을 닫아야 합니다 `CDatabase` 이 멤버 함수를 호출 하기 전에 개체입니다. 때문에 `Close` 제거 하지 않습니다는 `CDatabase` 개체를 열어 새 연결을 동일한 데이터 원본 또는 다른 데이터 원본 개체를 다시 사용할 수 있습니다.

모든 보류 중인 `AddNew` 또는 `Edit` 데이터베이스를 사용 하 여 레코드 집합의 문을 취소 하 고 보류 중인 모든 트랜잭션이 롤백됩니다. 모든 레코드 집합에 종속 된 `CDatabase` 개체는 정의 되지 않은 상태로 유지 됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDatabase#12](../../mfc/codesnippet/cpp/cdatabase-class_3.cpp)]

##  <a name="committrans"></a>  CDatabase::CommitTrans

트랜잭션이 완료 될 때이 멤버 함수를 호출 합니다.

```
BOOL CommitTrans();
```

### <a name="return-value"></a>반환 값

업데이트를 성공적으로 커밋 되었으면 0이 아닌 값 그렇지 않으면 0입니다. 경우 `CommitTrans` 실패 하면 데이터 원본의 상태 정의 되지 않습니다. 해당 상태를 확인 하기 위해 데이터를 확인 해야 합니다.

### <a name="remarks"></a>설명

트랜잭션이 일련의 호출에 구성 된를 `AddNew`, `Edit`, `Delete`, 및 `Update` 의 멤버 함수를 `CRecordset` 에 대 한 호출으로 시작 하는 개체를 [BeginTrans](#begintrans) 멤버 함수입니다. `CommitTrans` 트랜잭션을 커밋합니다. 기본적으로 업데이트 된 커밋된 즉시; 호출 `BeginTrans` 될 때까지 지연 될 업데이트의 약정 하면 `CommitTrans` 라고 합니다.

호출할 때까지 `CommitTrans` 트랜잭션을 종료를 호출 하면 합니다 [롤백](#rollback) 트랜잭션을 중단 하 고 데이터 원본을 원래 상태로 유지 하는 멤버 함수입니다. 새 트랜잭션을 시작 하려면 호출 `BeginTrans` 다시 합니다.

트랜잭션에 대 한 자세한 내용은 문서 참조 [트랜잭션 (ODBC)](../../data/odbc/transaction-odbc.md)합니다.

### <a name="example"></a>예제

  문서를 참조 [트랜잭션: 레코드 집합 (ODBC)에서 트랜잭션 수행](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)합니다.

##  <a name="executesql"></a>  CDatabase::ExecuteSQL

SQL 명령 직접 실행 해야 할 경우이 멤버 함수를 호출 합니다.

```
void ExecuteSQL(LPCTSTR lpszSQL);
```

### <a name="parameters"></a>매개 변수

*lpszSQL*<br/>
유효한 SQL 명령이 실행을 포함 하는 null로 끝나는 문자열에 대 한 포인터입니다. 전달할 수는 [CString](../../atl-mfc-shared/reference/cstringt-class.md)합니다.

### <a name="remarks"></a>설명

Null로 끝나는 문자열로 명령을 만듭니다. `ExecuteSQL` 데이터 레코드를 반환 하지 않습니다. 레코드에서 작동 하도록 하려는 경우 레코드 집합 개체를 대신 사용 합니다.

데이터 원본에 대 한 명령의 대부분은 데이터 선택, 새 레코드를 삽입, 레코드를 삭제 및 레코드 편집 명령을 지원 레코드 집합 개체를 통해 발급 됩니다. 그러나 일부 ODBC 기능 직접 지 데이터베이스 클래스를 사용 하 여 직접 SQL 호출을 수행 해야 경우가 있으므로 `ExecuteSQL`합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDatabase#13](../../mfc/codesnippet/cpp/cdatabase-class_4.cpp)]

##  <a name="getbookmarkpersistence"></a>  CDatabase::GetBookmarkPersistence

특정 작업 후 레코드 집합 개체에 책갈피가 유지되는지 확인하려면 이 멤버 함수를 호출합니다.

```
DWORD GetBookmarkPersistence() const;
```

### <a name="return-value"></a>반환 값

레코드 집합 개체에 책갈피를 유지하는 작업을 식별하는 비트 마스크입니다. 자세한 내용은 설명을 참조하세요.

### <a name="remarks"></a>설명

예를 들어 `CRecordset::GetBookmark`와 `CRecordset::Requery`를 차례로 호출하면 `GetBookmark`에서 가져온 책갈피가 더 이상 유효하지 않게 될 수 있습니다. `GetBookmarkPersistence`를 호출하기 전에 `CRecordset::SetBookmark`를 호출해야 합니다.

다음 테이블에는 `GetBookmarkPersistence`의 반환 값에 대해 결합할 수 있는 비트 마스크 값이 나와 있습니다.

|비트 마스크 값|책갈피 유지|
|-------------------|--------------------------|
|SQL_BP_CLOSE|책갈피는 유효 기간이 `Requery` 작업 합니다.|
|SQL_BP_DELETE|다음 행에 대 한 책갈피가 유효를 `Delete` 해당 행에 대 한 작업입니다.|
|SQL_BP_DROP|책갈피는 유효 기간이 `Close` 작업 합니다.|
|SQL_BP_SCROLL|이후 책갈피 유효 `Move` 작업 합니다. 따라서 `CRecordset::CanBookmark`에서 반환되는 책갈피가 레코드 집합에서 지원되는지를 쉽게 파악할 수 있습니다.|
|SQL_BP_TRANSACTION|트랜잭션이 커밋되거나 롤백된 후에 책갈피가 유효합니다.|
|SQL_BP_UPDATE|다음 행에 대 한 책갈피가 유효는 `Update` 해당 행에 대 한 작업입니다.|
|SQL_BP_OTHER_HSTMT|레코드 집합 개체 하나와 연결된 책갈피가 두 번째 레코드 집합에서도 유효합니다.|

이 반환 값에 대 한 자세한 내용은 ODBC API 함수를 참조 하세요. `SQLGetInfo` Windows SDK에 있습니다. 책갈피에 대 한 자세한 내용은 문서를 참조 하세요. [레코드 집합: 책갈피와 절대 위치 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)합니다.

##  <a name="getconnect"></a>  CDatabase::GetConnect

호출 하는 동안 사용 된 연결 문자열을 검색 하려면이 멤버 함수를 호출 `OpenEx` 또는 `Open` 연결 된 `CDatabase` 데이터 원본에 개체입니다.

```
const CString GetConnect() const;
```

### <a name="return-value"></a>반환 값

**상수**[CString](../../atl-mfc-shared/reference/cstringt-class.md) 하는 경우 연결 문자열을 포함 하 `OpenEx` 또는 `Open` 되었으면이 고, 그렇지 않으면 호출 빈 문자열입니다.

### <a name="remarks"></a>설명

참조 [cdatabase:: Open](#open) 연결 문자열은 생성 하는 방법에 대 한 합니다.

##  <a name="getcursorcommitbehavior"></a>  CDatabase::GetCursorCommitBehavior

확인 하려면이 멤버 함수를 호출 하는 방법을 [CommitTrans](#committrans) 열기 레코드 집합 개체에는 커서에 영향을 주는 합니다.

```
int GetCursorCommitBehavior() const;
```

### <a name="return-value"></a>반환 값

열린 레코드 집합 개체에는 트랜잭션 효과 나타내는 값입니다. 자세한 내용은 설명을 참조하세요.

### <a name="remarks"></a>설명

다음 표에서 가능한 반환 값에 대 한 `GetCursorCommitBehavior` 및 open 레코드 집합에 대 한 해당 영향입니다.

|반환 값|CRecordset 개체에 미치는 영향|
|------------------|----------------------------------|
|SQL_CB_CLOSE|호출 `CRecordset::Requery` 바로 다음에 오는 트랜잭션 커밋입니다.|
|SQL_CB_DELETE|호출 `CRecordset::Close` 바로 다음에 오는 트랜잭션 커밋입니다.|
|SQL_CB_PRESERVE|일반적으로 계속 `CRecordset` 작업 합니다.|

이 반환 값에 대 한 자세한 내용은 ODBC API 함수를 참조 하세요. `SQLGetInfo` Windows SDK에 있습니다. 트랜잭션에 대 한 자세한 내용은 문서 참조 [트랜잭션 (ODBC)](../../data/odbc/transaction-odbc.md)합니다.

##  <a name="getcursorrollbackbehavior"></a>  CDatabase::GetCursorRollbackBehavior

확인 하려면이 멤버 함수를 호출 하는 방법을 [롤백](#rollback) 열기 레코드 집합 개체에는 커서에 영향을 주는 합니다.

```
int GetCursorRollbackBehavior() const;
```

### <a name="return-value"></a>반환 값

열린 레코드 집합 개체에는 트랜잭션 효과 나타내는 값입니다. 자세한 내용은 설명을 참조하세요.

### <a name="remarks"></a>설명

다음 표에서 가능한 반환 값에 대 한 `GetCursorRollbackBehavior` 및 open 레코드 집합에 대 한 해당 영향입니다.

|반환 값|CRecordset 개체에 미치는 영향|
|------------------|----------------------------------|
|SQL_CB_CLOSE|호출 `CRecordset::Requery` 바로 다음에 오는 트랜잭션 롤백.|
|SQL_CB_DELETE|호출 `CRecordset::Close` 바로 다음에 오는 트랜잭션 롤백.|
|SQL_CB_PRESERVE|일반적으로 계속 `CRecordset` 작업 합니다.|

이 반환 값에 대 한 자세한 내용은 ODBC API 함수를 참조 하세요. `SQLGetInfo` Windows SDK에 있습니다. 트랜잭션에 대 한 자세한 내용은 문서 참조 [트랜잭션 (ODBC)](../../data/odbc/transaction-odbc.md)합니다.

##  <a name="getdatabasename"></a>  CDatabase::GetDatabaseName

(된 "데이터베이스" 라고 명명 된 개체를 정의 하는 데이터 원본) 현재 연결 된 데이터베이스의 이름을 검색 하려면이 멤버 함수를 호출 합니다.

```
CString GetDatabaseName() const;
```

### <a name="return-value"></a>반환 값

A [CString](../../atl-mfc-shared/reference/cstringt-class.md) 성공할 경우 데이터베이스 이름이 포함 된, 비어 있는 `CString`합니다.

### <a name="remarks"></a>설명

이것이에 지정 된 데이터 원본 이름 (DSN)와 동일 합니다 `OpenEx` 또는 `Open` 호출 합니다. 어떤 `GetDatabaseName` 반환 ODBC에 따라 달라 집니다. 일반적으로 데이터베이스는 테이블의 컬렉션. 이 엔터티는 이름이 `GetDatabaseName` 반환 합니다.

예를 들어 제목에는이 이름이 표시 하려면 할 수 있습니다. ODBC에서 이름을 검색 하는 동안 오류가 발생 하면 `GetDatabaseName` 빈 반환 `CString`합니다.

##  <a name="isopen"></a>  CDatabase::IsOpen

확인 하려면이 멤버 함수를 호출 하는지 여부를 `CDatabase` 개체 데이터 소스에 현재 연결 되어 있습니다.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>반환 값

0이 아닌 값을 `CDatabase` 개체 현재 연결 되어 그렇지 않으면 0입니다.

##  <a name="m_hdbc"></a>  CDatabase::m_hdbc

ODBC 데이터 원본 연결에 대 한 공용 핸들을 포함 합니다.-"연결 핸들입니다."

### <a name="remarks"></a>설명

일반적으로이 멤버 변수를 직접 액세스 하지 않아도 해야 합니다. 호출할 때 프레임 워크는 핸들을 할당 하는 대신 `OpenEx` 또는 `Open`합니다. 프레임 워크를 호출 하면 핸들을 할당 취소 합니다 **삭제** 연산자는 `CDatabase` 개체입니다. `Close` 멤버 함수 핸들을 할당을 취소 하지 않습니다.

그러나 일부 상황에서는 해야 핸들을 직접 사용 합니다. 예를 들어, 클래스를 통해가 대신 직접 ODBC API 함수를 호출 해야 할 경우 `CDatabase`를 매개 변수로 전달 하 여 연결 핸들을 해야 할 수 있습니다. 아래 코드 예제를 참조 하세요.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDatabase#15](../../mfc/codesnippet/cpp/cdatabase-class_5.cpp)]

##  <a name="onsetoptions"></a>  CDatabase::OnSetOptions

프레임 워크를 사용 하 여 SQL 문을 직접 실행 하는 경우이 멤버 함수를 호출 합니다 `ExecuteSQL` 멤버 함수입니다.

```
virtual void OnSetOptions(HSTMT hstmt);
```

### <a name="parameters"></a>매개 변수

*hstmt*<br/>
옵션은 설정 되는 ODBC 문 핸들입니다.

### <a name="remarks"></a>설명

`CRecordset::OnSetOptions` 또한이 멤버 함수를 호출합니다.

`OnSetOptions` 로그인 제한 시간 값을 설정합니다. 에 대 한 이전 호출 된 경우는 `SetQueryTimeout` 멤버 함수 및 `OnSetOptions` ; 현재 값을 반영 그렇지 않은 경우 기본 값을 설정 합니다.

> [!NOTE]
>  MFC 4.2 이전 `OnSetOptions` 하거나 snychronous 또는 비동기 처리 모드를 설정할 수도 있습니다. MFC 4.2 부터는 모든 작업은 동기입니다. 비동기 작업을 수행 하려면 ODBC API 함수 직접 호출 해야 `SQLSetPos`합니다.

재정의할 필요가 없습니다 `OnSetOptions` 시간 제한 값을 변경 합니다. 대신, 쿼리 제한 시간 값을 사용자 지정 하려면 호출 `SetQueryTimeout` ; 레코드 집합을 만들기 전에 `OnSetOptions` 새 값이 사용 됩니다. 값이 설정 된 모든 레코드 집합 또는 직접 SQL 호출에 대해 후속 작업에 적용 됩니다.

재정의 `OnSetOptions` 추가 옵션을 설정 하려는 경우. 재정의 기본 클래스를 호출 해야 `OnSetOptions` ODBC API 함수를 호출 전후 `SQLSetStmtOption`합니다. 프레임 워크의 기본 구현에서 설명 된 방법을 따라 `OnSetOptions`합니다.

##  <a name="open"></a>  CDatabase::Open

새로 생성 된 초기화 하려면이 멤버 함수를 호출 `CDatabase` 개체입니다.

```
virtual BOOL Open(
    LPCTSTR lpszDSN,
    BOOL bExclusive = FALSE,
    BOOL bReadOnly = FALSE,
    LPCTSTR lpszConnect = _T("ODBC;"),
    BOOL bUseCursorLib = TRUE);
```

### <a name="parameters"></a>매개 변수

*lpszDSN*<br/>
데이터 원본 이름 지정-ODBC 관리자 프로그램을 통해 ODBC를 사용 하 여 등록 된 이름입니다. DSN 값에 지정 된 경우 *lpszConnect* (형태로 "DSN =\<데이터 소스 >")를 다시 지정 하지 않아야 하 *lpszDSN*합니다. 이 예에서 *lpszDSN* NULL 이어야 합니다. 그렇지 않으면 사용자가 데이터 소스를 선택할 수 있는 데이터 원본 대화 상자를 사용 하 여 사용자를 표시 하려는 경우 NULL을 전달할 수 있습니다. 자세한 내용은 설명을 참조 하십시오.

*bExclusive*<br/>
클래스 라이브러리의이 버전에서 지원 되지 않습니다. 현재이 매개 변수는 TRUE는 어설션이 실패 합니다. 데이터 원본 (만 국한 되지 않고) 공유에 항상 열려 있습니다.

*bReadOnly*<br/>
읽기 전용 데이터 원본에 대 한 업데이트를 금지 하는 연결 하려는 경우 TRUE입니다. 이 특성을 상속 하는 모든 종속 레코드 집합. 기본값은 FALSE입니다.

*lpszConnect*<br/>
연결 문자열을 지정합니다. 가능한 경우 데이터 원본 이름, 데이터 원본, 사용자 인증 문자열 (암호, 데이터 원본 하나 필요로 하는 경우) 및 기타 정보에 유효한 사용자 ID를 포함 한 정보를 연결 하는 연결 문자열입니다. 전체 연결 문자열에 문자열 "ODBC;"가 붙어야 (대문자 또는 소문자). "ODBC;"는 ODBC 데이터 원본에 연결 되어 있음을 나타내려면 문자열이 사용 됩니다 이 경우 위쪽 호환성에 대 한 클래스 라이브러리의 이후 버전에는 비 ODBC 데이터 원본을 지원할 수 있습니다.

*bUseCursorLib*<br/>
ODBC 커서 라이브러리 DLL을 로드 하려면 TRUE로 지정 합니다. 커서 라이브러리 (드라이버를 지 원하는) 경우에 효과적으로 다이너셋을 사용 하지 못하도록 기본 ODBC 드라이버의 일부 기능을 마스크 합니다. 커서 라이브러리가 로드 하는 경우 지원 전용 커서는 정적 스냅샷 및 정방향 전용 커서입니다. 기본값은 TRUE입니다. 레코드 집합 개체를 직접 만들려는 경우 `CRecordset` 에서 파생을 하지 않고도 하지 커서 라이브러리를 로드 해야 합니다.

### <a name="return-value"></a>반환 값

0이 아닌 연결이 성공적으로 이루어집니다. 그렇지 않으면 사용자가 선택 하는 경우에 0 자세한 연결 정보를 묻는 대화 상자가 표시 될 때 취소 합니다. 다른 모든 경우에는 프레임 워크에는 예외가 throw 됩니다.

### <a name="remarks"></a>설명

레코드 집합 개체를 생성 하는 사용 하기 전에 데이터베이스 개체를 초기화 합니다.

> [!NOTE]
>  호출 된 [OpenEx](#openex) 멤버 함수는 데이터 원본에 연결 하 고 데이터베이스 개체를 초기화 하는 기본 방법입니다.

경우에 매개 변수를 프로그램 `Open` 호출에 연결 하는 데 충분 한 정보가 없는, ODBC 드라이버 사용자 로부터 필요한 정보를 가져오기 위한 대화 상자를 엽니다. 호출 하는 경우 `Open`, 연결 문자열에 *lpszConnect*에 개별적으로 저장 됩니다 합니다 `CDatabase` 개체를 호출 하 여 수를 [GetConnect](#getconnect) 멤버 함수입니다.

호출 하기 전에 사용자가 직접 대화 상자를 열 수 있습니다 `Open` 정보를 가져오려면 암호와 같은 사용자의 다음 추가 정보를 전달할 연결 문자열에 `Open`입니다. 또는 응용 프로그램 호출의 시간을 재사용할 수 있도록 하는 다음을 전달 하는 연결 문자열을 저장 하는 것이 좋습니다 `Open` 에 `CDatabase` 개체입니다.

여러 수준의 로그인 권한 부여에 대 한 연결 문자열을 사용할 수도 있습니다 (각각 다른 `CDatabase` 개체) 또는 다른 데이터 소스 관련 정보를 전달 합니다. 연결 문자열에 대 한 자세한 내용은 Windows SDK에서 5 장을 참조 하세요.

있기 연결 시도가 시간 초과 대 한 경우, 예를 들어 DBMS 호스트를 사용할 수 없습니다. 연결 시도가 실패 하면 `Open` throw를 `CDBException`입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDatabase#14](../../mfc/codesnippet/cpp/cdatabase-class_6.cpp)]

##  <a name="openex"></a>  CDatabase::OpenEx

새로 생성 된 초기화 하려면이 멤버 함수를 호출 `CDatabase` 개체입니다.

```
virtual BOOL OpenEx(
    LPCTSTR lpszConnectString,
    DWORD dwOptions = 0);
```

### <a name="parameters"></a>매개 변수

*lpszConnectString*<br/>
ODBC 연결 문자열을 지정합니다. 데이터 원본 이름 뿐만 아니라 사용자 ID 및 암호 등의 다른 선택적 정보가 포함 됩니다. 예를 들어, "DSN SQLServer_Source; = UID = SA; PWD abc123 = "가능한 연결 문자열입니다. NULL을 전달 하는 경우 *lpszConnectString*, 데이터 원본 대화 상자에는 데이터 원본을 선택 하 라는 메시지가 나타납니다.

*dwOptions*<br/>
다음 값의 조합을 지정 하는 비트 마스크입니다. 기본값은 0, 공유 쓰기 액세스를 사용 하 여 ODBC 커서 라이브러리 DLL 로드 되지 것입니다,으로 데이터베이스를 열 수를 의미 및 ODBC 연결 대화 상자에 연결 하는 데 충분 한 정보가 없는 경우에 표시 됩니다.

- `CDatabase::openExclusive` 클래스 라이브러리의이 버전에서 지원 되지 않습니다. 데이터 원본 (만 국한 되지 않고) 공유에 항상 열려 있습니다. 현재이 옵션을 지정 하는 어설션이 실패 합니다.

- `CDatabase::openReadOnly` 읽기 전용 데이터 소스를 엽니다.

- `CDatabase::useCursorLib` ODBC 커서 라이브러리 DLL을 로드 합니다. 커서 라이브러리 (드라이버를 지 원하는) 경우에 효과적으로 다이너셋을 사용 하지 못하도록 기본 ODBC 드라이버의 일부 기능을 마스크 합니다. 커서 라이브러리가 로드 하는 경우 지원 전용 커서는 정적 스냅샷 및 정방향 전용 커서입니다. 레코드 집합 개체를 직접 만들려는 경우 `CRecordset` 에서 파생을 하지 않고도 하지 커서 라이브러리를 로드 해야 합니다.

- `CDatabase::noOdbcDialog` 충분 한 연결 정보를 제공 하는 여부에 관계 없이 ODBC 연결 대화 상자를 표시 하지 않습니다.

- `CDatabase::forceOdbcDialog` 항상 ODBC 연결 대화 상자를 표시 합니다.

### <a name="return-value"></a>반환 값

0이 아닌 연결이 성공적으로 이루어집니다. 그렇지 않으면 사용자가 선택 하는 경우에 0 자세한 연결 정보를 묻는 대화 상자가 표시 될 때 취소 합니다. 다른 모든 경우에는 프레임 워크에는 예외가 throw 됩니다.

### <a name="remarks"></a>설명

레코드 집합 개체를 생성 하는 사용 하기 전에 데이터베이스 개체를 초기화 합니다.

경우는 *lpszConnectString* 매개 변수에서 프로그램 `OpenEx` 호출이 연결을 만드는 데 충분 한 정보를 포함 하지, ODBC 드라이버를 제공 하지 않은 사용자 로부터 필요한 정보를 얻으려면 대화 상자를 엽니다 설정 `CDatabase::noOdbcDialog` 나 `CDatabase::forceOdbcDialog` 에 *dwOptions* 매개 변수입니다. 호출 하는 경우 `OpenEx`, 연결 문자열에 *lpszConnectString*에 개별적으로 저장 됩니다 합니다 `CDatabase` 개체를 호출 하 여 수를 [GetConnect](#getconnect) 멤버 함수입니다.

호출 하기 전에 사용자가 직접 대화 상자를 열 수 있습니다 `OpenEx` 정보를 가져와서 암호와 같은 사용자의 연결 문자열에 전달 하는 정보를 추가 `OpenEx`합니다. 또는 응용 프로그램 호출의 시간을 재사용할 수 있도록 하는 다음을 전달 하는 연결 문자열을 저장 하는 것이 좋습니다 `OpenEx` 에 `CDatabase` 개체입니다.

여러 수준의 로그인 권한 부여에 대 한 연결 문자열을 사용할 수도 있습니다 (각각 다른 `CDatabase` 개체) 또는 다른 데이터 소스 관련 정보를 전달 합니다. 연결 문자열에 대 한 자세한 내용은의 6 장 참조를 *ODBC 프로그래머 참조*합니다.

있기 연결 시도가 시간 초과 대 한 경우, 예를 들어 DBMS 호스트를 사용할 수 없습니다. 연결 시도가 실패 하면 `OpenEx` throw를 `CDBException`입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDatabase#11](../../mfc/codesnippet/cpp/cdatabase-class_7.cpp)]

##  <a name="rollback"></a>  CDatabase::Rollback

트랜잭션 중에 수행 된 변경 내용이 되돌릴이 멤버 함수를 호출 합니다.

```
BOOL Rollback();
```

### <a name="return-value"></a>반환 값

트랜잭션이 성공적으로 취소 된; 경우 0이 아닌 값 그렇지 않으면 0입니다. 경우는 `Rollback` 데이터 원본 및 트랜잭션 호출이 실패 하면 상태는 정의 되지 않습니다. 경우 `Rollback` 0을 반환 합니다. 해당 상태를 확인 하려면 데이터 소스를 확인 해야 합니다.

### <a name="remarks"></a>설명

모든 `CRecordset` `AddNew`, `Edit`합니다 `Delete`, 및 `Update` 마지막 실행 호출 [BeginTrans](#begintrans) 해당 호출 시 존재 하는 상태로 롤백됩니다.

호출한 후 `Rollback`조치 트랜잭션이 이며 호출 해야 `BeginTrans` 다른 트랜잭션에 대 한 다시 합니다. 호출 하기 전에 현재 레코드가 `BeginTrans` 한 후 다시 현재 레코드가 됩니다 `Rollback`합니다.

롤백 후 레코드 롤백 이전에 유지 됩니다. 레코드 집합 및 롤백 후 데이터 원본 상태에 대 한 자세한 내용은 문서 참조 [트랜잭션 (ODBC)](../../data/odbc/transaction-odbc.md)합니다.

### <a name="example"></a>예제

  문서를 참조 [트랜잭션: 레코드 집합 (ODBC)에서 트랜잭션 수행](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)합니다.

##  <a name="setlogintimeout"></a>  CDatabase::SetLoginTimeout

이 멤버 함수를 호출, 호출 하기 전에 `OpenEx` 또는 `Open` -데이터를 시도 하기 전에 허용 되는 시간 (초) 기본값을 재정의 하려면 소스 연결 시간이 초과 합니다.

```
void SetLoginTimeout(DWORD dwSeconds);
```

### <a name="parameters"></a>매개 변수

*dwSeconds*<br/>
연결 시도 하기 전까지 허용 시간 (초) 수 시간이 초과 됩니다.

### <a name="remarks"></a>설명

DBMS를 사용할 수 없는 예를 들어 하는 경우 연결 시도가 시간 초과 수 있습니다. 호출 `SetLoginTimeout` 는 초기화 되지 않은 생성 한 후 `CDatabase` 개체 하지만 호출 하기 전에 `OpenEx` 또는 `Open`합니다.

로그인 시간 제한의 기본값은 15 초입니다. 일부 데이터 원본 로그인 제한 시간 값을 지정 하는 기능을 지원 합니다. 데이터 원본 제한 시간을 지원 하지 않으면 추적 출력을 만들지만 되지 않는 예외를 가져옵니다. 값이 0 이면 "infinite"입니다.

##  <a name="setquerytimeout"></a>  CDatabase::SetQueryTimeout

후속 작업을 연결 된 데이터 원본 시간 초과 하기 전까지 허용 시간 (초) 기본값을 재정의 하려면이 멤버 함수를 호출 합니다.

```
void SetQueryTimeout(DWORD dwSeconds);
```

### <a name="parameters"></a>매개 변수

*dwSeconds*<br/>
쿼리 시도 하기 전까지 허용 시간 (초) 수 시간이 초과 됩니다.

### <a name="remarks"></a>설명

네트워크 액세스 문제, 과도 한 쿼리 처리 시간 등으로 인해 작업 시간이 초과 될 수 있습니다. 호출 `SetQueryTimeout` 레코드 집합을 열기 전에 또는 레코드 집합의 호출 하기 전에 `AddNew`하십시오 `Update` 또는 `Delete` 쿼리 제한 시간 값을 변경 하려는 경우 멤버 함수입니다. 설정은 모든 후속 `Open`, `AddNew`를 `Update`, 및 `Delete` 와 연결 된 모든 레코드 집합에 대 한 호출 `CDatabase` 개체입니다. 연 후 레코드 집합에 대 한 쿼리 제한 시간 값을 변경 하는 경우에 레코드 집합에 대 한 값을 변경 되지 않습니다. 예를 들어, 후속 `Move` 작업 새 값을 사용 하지 않습니다.

쿼리 제한 시간에 대 한 기본값은 15 초입니다. 일부 데이터 원본 쿼리 제한 시간 값을 설정 하는 기능을 지원 합니다. 쿼리 제한 시간 값이 0으로 설정한 경우 시간 제한 없이 발생 합니다. 데이터 소스와의 통신에 응답을 중지할 수 있습니다. 이 동작은 개발 하는 동안 유용할 수 있습니다. 데이터 원본 제한 시간을 지원 하지 않으면 추적 출력을 만들지만 되지 않는 예외를 가져옵니다.

## <a name="see-also"></a>참고자료

[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CRecordset 클래스](../../mfc/reference/crecordset-class.md)
