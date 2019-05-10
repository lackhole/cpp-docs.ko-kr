---
title: CDBException 클래스
ms.date: 11/04/2016
f1_keywords:
- CDBException
- AFXDB/CDBException
- AFXDB/CDBException::m_nRetCode
- AFXDB/CDBException::m_strError
- AFXDB/CDBException::m_strStateNativeOrigin
helpviewer_keywords:
- CDBException [MFC], m_nRetCode
- CDBException [MFC], m_strError
- CDBException [MFC], m_strStateNativeOrigin
ms.assetid: eb9e1119-89f5-49a7-b9d4-b91cee1ccc82
ms.openlocfilehash: bdfb9bd0b45fd241de4378a2caa19e7dd9f9bdf2
ms.sourcegitcommit: 18d3b1e9cdb4fc3a76f7a650c31994bdbd2bde64
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2019
ms.locfileid: "64877498"
---
# <a name="cdbexception-class"></a>CDBException 클래스

데이터베이스 클래스에서 발생하는 예외 상태를 나타냅니다.

## <a name="syntax"></a>구문

```
class CDBException : public CException
```

## <a name="members"></a>멤버

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CDBException::m_nRetCode](#m_nretcode)|ODBC Open Database Connectivity () 반환 코드, RETCODE 형식의 포함합니다.|
|[CDBException::m_strError](#m_strerror)|영숫자 측면에서 오류를 설명 하는 문자열을 포함 합니다.|
|[CDBException::m_strStateNativeOrigin](#m_strstatenativeorigin)|ODBC에서 반환 된 오류 코드를 기준으로 오류를 설명 하는 문자열을 포함 합니다.|

## <a name="remarks"></a>설명

클래스는 예외를 발생 시킨을 확인 하거나 예외를 설명 하는 텍스트 메시지를 표시 하려면를 사용할 수 있는 두 공용 데이터 멤버를 포함 합니다. `CDBException` 개체 생성 되며 데이터베이스 클래스의 멤버 함수에 의해 throw 됩니다.

> [!NOTE]
>  이 클래스는 MFC의 ODBC Open Database Connectivity () 클래스 중 하나입니다. 대신 최신 데이터 액세스 개체 (DAO) 클래스를 사용할 경우 사용 하 여 [CDaoException](../../mfc/reference/cdaoexception-class.md) 대신 합니다. 모든 DAO 클래스 이름에는 접두사로 "CDao"에 있습니다. 자세한 내용은 문서를 참조 하세요. [개요: 데이터베이스 프로그래밍](../../data/data-access-programming-mfc-atl.md)합니다.

예외는 외부 데이터 원본 등의 프로그램의 컨트롤 상태와 관련 된 비정상적인 실행의 경우 또는 네트워크 I/O 오류입니다. 정상적인 프로그램 실행 중에 예상 하는 오류는 일반적으로 간주 되지 예외.

범위 내에서 이러한 개체에 액세스할 수 있습니다는 **CATCH** 식입니다. Throw 할 수 있습니다 `CDBException` 사용 하 여 사용자 고유의 코드에서 개체를 `AfxThrowDBException` 전역 함수입니다.

일반적으로 되었거나 곧에서 예외 처리에 대 한 자세한 내용은 `CDBException` 문서를 참조 하는 개체를 [예외 처리 (MFC)](../../mfc/exception-handling-in-mfc.md) 및 [예외: 데이터베이스 예외](../../mfc/exceptions-database-exceptions.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CDBException`

## <a name="requirements"></a>요구 사항

**헤더:** afxdb.h

##  <a name="m_nretcode"></a>  CDBException::m_nRetCode

ODBC 응용 프로그램 프로그래밍 인터페이스 (API) 함수에서 반환 된 RETCODE 형식의 ODBC 오류 코드를 포함 합니다.

### <a name="remarks"></a>설명

이 형식은 ODBC에서 정의 된 접두사가 있는 SQL 코드 및 데이터베이스 클래스에서 정의 된 접두사가 있는 AFX_SQL 코드를 포함 합니다. 에 대 한는 `CDBException`를이 멤버는 다음 값 중 하나가 포함 됩니다.

- AFX_SQL_ERROR_API_CONFORMANCE 드라이버에는 `CDatabase::OpenEx` 또는 `CDatabase::Open` 호출 필요한 ODBC API 적합성 수준 (SQL_OAC_LEVEL1) 1에 맞지 않습니다.

- 데이터 원본에 AFX_SQL_ERROR_CONNECT_FAIL 연결 하지 못했습니다. NULL을 전달`CDatabase` 생성자를 레코드 집합 및 연결을 만드는 후속 시도에 대 한 포인터 기반 `GetDefaultConnect` 실패 했습니다.

- 에 대 한 저장소를 제공 하는 것 보다 더 많은 데이터를 요청 AFX_SQL_ERROR_DATA_TRUNCATED 있습니다. 제공 된 데이터 저장소에 대 한 증가 하는 방법은 `CString` 또는 `CByteArray` 데이터 형식 참조를 `nMaxLength` 인수에 대 한 [RFX_Text](record-field-exchange-functions.md#rfx_text) 및 [RFX_Binary](record-field-exchange-functions.md#rfx_binary) 아래 "매크로 및 전역입니다. "

- AFX_SQL_ERROR_DYNASET_NOT_SUPPORTED 호출 `CRecordset::Open` 다이너셋 요청 하지 못했습니다. 다이너셋은 드라이버에서 지원 되지 않습니다.

- AFX_SQL_ERROR_EMPTY_COLUMN_LIST 하려는 테이블을 엽니다 (제공한 어떤를 식별할 수 없는 프로시저 호출으로 또는 또는 **선택** 문) 레코드 필드 교환 (RFX () 함수 호출에서 식별 된 열이 없는 되지만 프로그램 `DoFieldExchange` 재정의 합니다.

- 함수는 RFX 유형의 AFX_SQL_ERROR_FIELD_SCHEMA_MISMATCH 프로그램 `DoFieldExchange` 재정의 레코드 집합의 열 데이터 형식이 호환 되지 않습니다.

- AFX_SQL_ERROR_ILLEGAL_MODE 있습니다 호출 `CRecordset::Update` 이전에 호출 하지 않고 `CRecordset::AddNew` 또는 `CRecordset::Edit`합니다.

- ODBC 드라이버에 잠금을 지원 하지 않으므로 AFX_SQL_ERROR_LOCK_MODE_NOT_SUPPORTED 레코드 업데이트에 대 한 잠금 요청을 수행할 수 없습니다.

- AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED 있습니다 호출 `CRecordset::Update` 또는 `Delete` 없는 고유 키를 사용 하 여 테이블에 대 한 여러 레코드를 변경 합니다.

- AFX_SQL_ERROR_NO_CURRENT_RECORD 있습니다 편집 하거나 이전에 삭제 된 레코드를 삭제 했습니다. 삭제 한 후 새 현재 레코드로 스크롤해야 합니다.

- 위치 지정 업데이트를 AFX_SQL_ERROR_NO_POSITIONED_UPDATES ODBC 드라이버를 지원 하지 않으므로 다이너셋에 대 한 요청을 수행할 수 없습니다.

- AFX_SQL_ERROR_NO_ROWS_AFFECTED 없습니다 호출 `CRecordset::Update` 또는 `Delete`, 하지만 작업을 시작 하는 경우 레코드를 더 이상 찾을 수 없습니다.

- AFX_SQL_ERROR_ODBC_LOAD_FAILED ODBC를 로드 하려고 합니다. DLL에 실패 했습니다. Windows를 찾을 수 없거나이 DLL을 로드할 수 없습니다. 이 오류는 치명적입니다.

- AFX_SQL_ERROR_ODBC_V2_REQUIRED 수준 2-규격 ODBC 드라이버를 필수적 요소 이므로 다이너셋에 대 한 요청을 수행할 수 없습니다.

- 데이터 원본에서 이전 버전과 스크롤을 지원 하지 않으므로 AFX_SQL_ERROR_RECORDSET_FORWARD_ONLY 스크롤해야 시도가 실패 했습니다.

- AFX_SQL_ERROR_SNAPSHOT_NOT_SUPPORTED 호출 `CRecordset::Open` 스냅숏을 요청 하지 못했습니다. 스냅숏은은 드라이버에서 지원 되지 않습니다. (이 이루어져야 경우 ODBC 커서 라이브러리 ODBCCURS 합니다. DLL 나타나지 않습니다.)

- AFX_SQL_ERROR_SQL_CONFORMANCE 드라이버에는 `CDatabase::OpenEx` 또는 `CDatabase::Open` 호출 "최소" (SQL_OSC_MINIMUM)의 필요한 ODBC SQL 적합성 수준에 맞지 않습니다.

- AFX_SQL_ERROR_SQL_NO_TOTAL The ODBC 드라이버의 총 크기를 지정할 수 없습니다. 한 `CLongBinary` 데이터 값입니다. 아마도 작업이 전역 메모리 블록을 미리 할당 하지 못했습니다 실패 했습니다.

- AFX_SQL_ERROR_RECORDSET_READONLY 하려는 읽기 전용 레코드 집합을 업데이트 하거나 데이터 원본 읽기 전용입니다. Update 작업이 이루어지지 레코드 집합을 사용 하 여 수행할 수 있습니다 또는 `CDatabase` 연관 된 개체입니다.

- SQL_ERROR 함수가 실패 했습니다. ODBC 함수에서 반환 된 오류 메시지 `SQLError` 에 저장 되는 `m_strError` 데이터 멤버입니다.

- SQL_INVALID_HANDLE 함수는 잘못 된 환경 핸들, 연결 핸들 또는 문 핸들 인해 실패 했습니다. 이 프로그래밍 오류를 나타냅니다. 추가 정보 없이 ODBC 함수에서 사용할 수 있는 `SQLError`합니다.

SQL 맨 앞에 나오는 코드는 ODBC에서 정의 됩니다. AFX 맨 앞에 나오는 코드는 AFXDB에서 정의 됩니다. H, MFC\INCLUDE에서 찾을 수 있습니다.

##  <a name="m_strerror"></a>  CDBException::m_strError

예외를 발생 시킨 오류를 설명 하는 문자열을 포함 합니다.

### <a name="remarks"></a>설명

영숫자 측면에서 오류를 설명 하는 문자열입니다. 자세한 내용 및 예제를 참조 하세요. `m_strStateNativeOrigin`합니다.

##  <a name="m_strstatenativeorigin"></a>  CDBException::m_strStateNativeOrigin

예외를 발생 시킨 오류를 설명 하는 문자열을 포함 합니다.

### <a name="remarks"></a>설명

문자열의 폼 "상태 %s, 네이티브 %ld, 원본 %s"를 순서 대로 형식 코드를 설명 하는 값으로 대체 됩니다 여기서 다음과 같습니다:::.

- SQLSTATE, 5 문자 오류 코드가 포함 된 null로 끝나는 문자열을 반환 합니다 *szSqlState* ODBC 함수의 매개 변수가 `SQLError`합니다. 부록 A에서에서 SQLSTATE 값 나와 [ODBC 오류 코드](/sql/odbc/reference/appendixes/appendix-a-odbc-error-codes)를 *ODBC 프로그래머 참조*합니다. 예제: "S0022".

- 에 반환 된 원시 오류 코드, 데이터 원본에 특정 합니다 *pfNativeError* 의 매개 변수는 `SQLError` 함수입니다. 예제: 207.

- 반환 된 오류 메시지 텍스트를 *szErrorMsg* 의 매개 변수는 `SQLError` 함수입니다. 이 메시지는 여러 개의 대괄호로 묶은 이름을 이루어져 있습니다. 오류가 사용자에 해당 원본에서 전달 되는, 각 ODBC 구성 요소 (데이터 원본, 드라이버, 드라이버 관리자)는 고유 이름을 추가 합니다. 이 정보는 오류의 출처를 정확 하 게 찾을 수 있습니다. 예: [Microsoft] [ODBC SQL Server Driver] [SQL Server]

프레임 워크가 오류 문자열을 해석 하 고 해당 구성 요소에 배치 `m_strStateNativeOrigin`같으면 `m_strStateNativeOrigin` 정보가 둘 이상의 오류를 오류 줄 바꿈 문자로 구분 됩니다. 프레임 워크에는 영숫자 오류 텍스트를 배치 `m_strError`합니다.

이 문자열을 구성 하는 데 코드에 대 한 자세한 내용은 참조는 [SQLError](/sql/odbc/reference/syntax/sqlerror-function) 함수는 *ODBC 프로그래머 참조*합니다.

### <a name="example"></a>예제

ODBC에서: "상태: S0022, 네이티브: 207, 원본:\[Microsoft]\[ODBC SQL Server Driver]\[SQL Server] 'ColName' 잘못 된 열 이름"

`m_strStateNativeOrigin`의 경우 "State:S0022,Native:207,Origin:\[Microsoft]\[ODBC SQL Server Driver]\[SQL Server]"

`m_strError`의 경우 "잘못 된 열 이름 'ColName'"

## <a name="see-also"></a>참고자료

[CException 클래스](../../mfc/reference/cexception-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CDatabase 클래스](../../mfc/reference/cdatabase-class.md)<br/>
[CRecordset 클래스](../../mfc/reference/crecordset-class.md)<br/>
[CFieldExchange 클래스](../../mfc/reference/cfieldexchange-class.md)<br/>
[CRecordset::Update](../../mfc/reference/crecordset-class.md#update)<br/>
[CRecordset::Delete](../../mfc/reference/crecordset-class.md#delete)<br/>
[CException 클래스](../../mfc/reference/cexception-class.md)
