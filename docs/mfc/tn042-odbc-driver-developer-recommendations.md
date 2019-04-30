---
title: 'TN042: ODBC 드라이버 개발자 권장 사항'
ms.date: 11/04/2016
f1_keywords:
- vc.odbc
helpviewer_keywords:
- ODBC drivers [MFC], writing
- databases [MFC], ODBC
- TN042
ms.assetid: ecc6b5d9-f480-4582-9e22-8309fe561dad
ms.openlocfilehash: 462f8229d995add79f48f34b7f81257710b4a8b8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62305413"
---
# <a name="tn042-odbc-driver-developer-recommendations"></a>TN042: ODBC 드라이버 개발자 권장 사항

> [!NOTE]
>  다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.

이 이는 ODBC 드라이버 작성기에 대 한 지침을 설명합니다. 일반 요구 사항 및 MFC 데이터베이스 클래스를 확인 하는 ODBC 기능 및 필요한 의미 체계 세부 정보를 다양 한 정도 설명 합니다. 필요한 세 가지를 지원 하기 위해 드라이버 기능인 `CRecordset` 모드를 엽니다 (**forwardOnly**, **스냅숏** 하 고 **다이너셋**) 설명 되어 있습니다.

## <a name="odbcs-cursor-library"></a>ODBC의 커서 라이브러리

MFC 데이터베이스 클래스는 대부분의 경우에서 대부분의 수준 1 ODBC 드라이버에서 제공 하는 기능을 초과 하는 사용자에 게 기능을 제공 합니다. 다행 스럽게도 ODBC의 커서 라이브러리는 데이터베이스 클래스 드라이버 사이의 계층 및이 추가 기능을 대부분 자동으로 제공 됩니다.

예를 들어 대부분의 1.0 드라이버는 뒤로 스크롤을 지원 하지 않습니다. 커서 라이브러리 수이 감지 하 고 드라이버에서 행을 캐시 되며에서 FETCH_PREV 호출에서 요청 제공 `SQLExtendedFetch`합니다.

커서 라이브러리 종속성의 또 다른 중요 한 예는 위치 지정된 업데이트 합니다. 대부분의 1.0 드라이버도 위치 지정된 업데이트 없지만 커서 라이브러리는 현재 캐시 된 데이터 값, 또는 캐시 된 타임 스탬프 값에 따라 데이터 원본에서 대상 행을 식별 하는 update 문이 생성 됩니다.

클래스 라이브러리에서는 여러 행 집합을 활용 하지 않습니다. 따라서 몇 가지 `SQLSetPos` 문은 1 행 집합의 행에 항상 적용 됩니다.

## <a name="cdatabases"></a>CDatabases

각 `CDatabase` 단일 할당 **HDBC**합니다. (경우 `CDatabase`의 `ExecuteSQL` 함수를 사용 하 고는 **HSTMT** 일시적으로 할당 됩니다.) 여러 만약 `CDatabase`의 필요할 경우 여러 **HDBC**초 이상이 **HENV** 지원 해야 합니다.

데이터베이스 클래스에는 커서 라이브러리가 필요합니다. `SQLSetConnections` 호출 **SQL_ODBC_CURSORS**합니다 **SQL_CUR_USE_ODBC**합니다.

`SQLDriverConnect`를 **SQL_DRIVER_COMPLETE** 에서 사용 하는 `CDatabase::Open` 데이터 원본에 연결 합니다.

드라이버를 지원 해야 합니다 `SQLGetInfo SQL_ODBC_API_CONFORMANCE`  >=  **SQL_OAC_LEVEL1**하십시오 `SQLGetInfo SQL_ODBC_SQL_CONFORMANCE`  >=  **SQL_OSC_MINIMUM**합니다.

에 대 한 지원 해야 하는 트랜잭션에 대 한 순서로 합니다 `CDatabase` 및 해당 종속 레코드 집합 `SQLGetInfo SQL_CURSOR_COMMIT_BEHAVIOR` 및 **SQL_CURSOR_ROLLBACK_BEHAVIOR** 있어야 **SQL_CR_PRESERVE**합니다. 이 고, 그렇지 트랜잭션 제어를 수행 하려는 시도 무시 됩니다.

`SQLGetInfo SQL_DATA_SOURCE_READ_ONLY` 지원 되어야 합니다. "Y"를 반환 하는 경우 데이터 원본에서 업데이트 작업이 수행 됩니다.

경우는 `CDatabase` 열릴 읽기 전용, 읽기 데이터 원본 설정 하려는 시도가 만들어집니다 `SQLSetConnectOption SQL_ACCESS_MODE`를 **SQL_MODE_READ_ONLY**합니다.

따옴표로 묶은 식별자 필요한 경우이 정보를 사용 하 여 드라이버에서 반환 되어야 합니다는 `SQLGetInfo SQL_IDENTIFIER_QUOTE_CHAR` 호출 합니다.

디버깅을 위해 `SQLGetInfo SQL_DBMS_VER` 하 고 **SQL_DBMS_NAME** 드라이버에서 검색 됩니다.

`SQLSetStmtOption SQL_QUERY_TIMEOUT` 및 **SQL_ASYNC_ENABLE** 에 대해 호출할 수는 `CDatabase`의 **HDBC**합니다.

`SQLError` any / all 인수는 NULL 사용 하 여 호출할 수 있습니다.

물론 `SQLAllocEnv`, `SQLAllocConnect`를 `SQLDisconnect` 고 `SQLFreeConnect` 지원 해야 합니다.

## <a name="executesql"></a>ExecuteSQL

할당 하 고 임시를 해제 하는 것 외에도 **HSTMT**, `ExecuteSQL` 호출 `SQLExecDirect`, `SQLFetch`를 `SQLNumResultCol` 고 `SQLMoreResults`입니다. `SQLCancel` 에 대해 호출할 수는 **HSTMT**합니다.

## <a name="getdatabasename"></a>GetDatabaseName

`SQLGetInfo SQL_DATABASE_NAME` 호출 됩니다.

## <a name="begintrans-committrans-rollback"></a>BeginTrans, CommitTrans 롤백

`SQLSetConnectOption SQL_AUTOCOMMIT` 및 `SQLTransact SQL_COMMIT`, **SQL_ROLLBACK** 하 고 **SQL_AUTOCOMMIT** 트랜잭션 요청을 수행 하는 경우 호출 됩니다.

## <a name="crecordsets"></a>CRecordsets

`SQLAllocStmt`를 `SQLPrepare`, `SQLExecute` (에 대 한 `Open` 하 고 `Requery`), `SQLExecDirect` (업데이트 작업의 경우)의 `SQLFreeStmt` 지원 해야 합니다. `SQLNumResultCols` 및 `SQLDescribeCol` 결과 집합에서 다양 한 시간에 호출 됩니다.

`SQLSetParam` 매개 변수 데이터 바인딩에 대 한 광범위 하 게 되 고 **DATA_AT_EXEC** 기능입니다.

`SQLBindCol` 광범위 하 게 등록 하는 ODBC 사용 하 여 열 데이터 저장소 위치를 출력 합니다.

두 개의 `SQLGetData` 호출은 검색 하는 데 사용 됩니다 **SQL_LONG_VARCHAR** 하 고 **SQL_LONG_VARBINARY** 데이터입니다. 첫 번째 호출은 호출 하 여 열 값의 총 길이 찾으려고 시도 `SQLGetData` 유효한 pcbValue가 같지만 cbMaxValue 0입니다. PcbValue 보유 하는 경우 **SQL_NO_TOTAL**, 예외가 throw 됩니다. 이 고, 그렇지는 **HGLOBAL** 할당 되어 다른 `SQLGetData` 전체 결과 검색에 대 한 호출 합니다.

## <a name="updating"></a>업데이트하는 중

비관적 잠금 요청 되 면 `SQLGetInfo SQL_LOCK_TYPES` 쿼리 됩니다. 하는 경우 **SQL_LCK_EXCLUSIVE** 는 지원 되지 않는 예외가 throw 됩니다.

업데이트를 시도 `CRecordset` (**스냅숏** 또는 **다이너셋**) 두 번째 하면 **HSTMT** 할당할 합니다. 지원 하지 않는 드라이버에 대 한 두 번째 **HSTMT**, 커서 라이브러리에서는이 기능을 시뮬레이션 합니다. 아쉽게도 때로는 즉 첫 번째 현재 쿼리를 강제 적용 **HSTMT** 완료 된 후 두 번째 처리 **HSTMT**의 요청 합니다.

`SQLFreeStmt SQL_CLOSE` 및 **SQL_RESET_PARAMS** 고 `SQLGetCursorName` 업데이트 작업 도중에 호출 됩니다.

없으면 **CLongBinarys** 에 **outputColumns**, ODBC의 **DATA_AT_EXEC** 기능을 지원 해야 합니다. 여기에 반환 **SQL_NEED_DATA** 에서 `SQLExecDirect`, `SQLParamData` 고 `SQLPutData`입니다.

`SQLRowCount` 1 개의 레코드에서 업데이트 되었는지 확인 하려면 실행 한 후 호출 되는 `SQLExecDirect`합니다.

## <a name="forwardonly-cursors"></a>ForwardOnly 커서

만 `SQLFetch` 에 대 한 필요를 `Move` 작업 합니다. 사실은 **forwardOnly** 커서 업데이트를 지원 하지 않습니다.

## <a name="snapshot-cursors"></a>스냅숏 커서

스냅숏 기능을 사용 하려면 `SQLExtendedFetch` 지원 합니다. ODBC 커서 라이브러리 드라이버를 지원 하지 않는 경우 검색은 위에서 언급 했 듯이 `SQLExtendedFetch`, 자체 필요한 지원을 제공 합니다.

`SQLGetInfo`하십시오 **SQL_SCROLL_OPTIONS** 지원 해야 **SQL_SO_STATIC**합니다.

## <a name="dynaset-cursors"></a>다이너셋 커서

다이너셋을 여는 데 필요한 최소 지지도 다음과 같습니다.

`SQLGetInfo`하십시오 **SQL_ODBC_VER** 반환 해야 > "01"입니다.

`SQLGetInfo`하십시오 **SQL_SCROLL_OPTIONS** 지원 해야 **SQL_SO_KEYSET_DRIVEN**합니다.

`SQLGetInfo`하십시오 **SQL_ROW_UPDATES** "Y"를 반환 해야 합니다.

`SQLGetInfo`를 **SQL_POSITIONED_UPDATES** 지원 해야 **SQL_PS_POSITIONED_DELETE** 하 고 **SQL_PS_POSITIONED_UPDATE**합니다.

또한 비관적 잠금을 요청 하는 경우에 대 한 호출 `SQLSetPos` irow 1, FALSE fRefresh 및 떼 **SQL_LCK_EXCLUSIVE** 만들어집니다.

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
