---
title: '레코드 집합: 레코드 집합 선택 (ODBC)를 기록 하는 방법'
ms.date: 11/04/2016
helpviewer_keywords:
- recordsets, selecting records
- record selection, ODBC recordsets
- SQL statements, recordset
- records, selecting
- recordsets, constructing SQL statements
- ODBC recordsets, selecting records
ms.assetid: 343a6a91-aa4c-4ef7-b21f-2f2bfd0d3787
ms.openlocfilehash: 310481a6ea6637de817bf29d528cbdfe70ae70db
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59041327"
---
# <a name="recordset-how-recordsets-select-records-odbc"></a>레코드 집합: 레코드 집합 선택 (ODBC)를 기록 하는 방법

이 항목에서는 MFC ODBC 클래스에 적용됩니다.

이 항목에 설명 합니다.

- [역할 및 레코드를 선택 하 여 옵션](#_core_your_options_in_selecting_records)합니다.

- [레코드 집합 SQL 문을 생성 하 고 레코드를 선택 하는 방법을](#_core_how_a_recordset_constructs_its_sql_statement)합니다.

- [선택 영역을 사용자 지정을 수행할 수 있는 작업](#_core_customizing_the_selection)합니다.

레코드 집합 드라이버에 SQL 문을 전송 하 여 ODBC 드라이버를 통해 데이터 원본에서 레코드를 선택 합니다. 전송 SQL 디자인 하 고 레코드 집합 클래스를 열고 하는 방법에 따라 달라 집니다.

##  <a name="_core_your_options_in_selecting_records"></a> 레코드 선택 옵션

다음 표에서 레코드를 선택 하 여 옵션을 보여 줍니다.

### <a name="how-and-when-you-can-affect-a-recordset"></a>방법 및 시기에 레코드 집합을 변경할 수 있습니다

|면 수|다음과 같은 작업을 수행할 수 있습니다.|
|--------------|-------------|
|사용 하 여 레코드 집합 클래스를 선언 합니다 **클래스 추가** 마법사|선택할 수 있는 테이블을 지정 합니다.<br /><br /> 포함할 열을 지정 합니다.<br /><br /> 참조 [MFC ODBC 소비자 추가](../../mfc/reference/adding-an-mfc-odbc-consumer.md)합니다.|
|레코드 집합 클래스 구현 완료|와 같은 멤버 함수를 재정의 `OnSetOptions` 응용 프로그램별 옵션을 설정 하거나 기본값을 변경 (고급). 매개 변수가 있는 레코드 집합을 원하는 경우 매개 변수 데이터 멤버를 지정 합니다.|
|레코드 집합 개체를 생성 합니다 (호출 하기 전에 `Open`)|사용 하기 위해 (가능한 경우 복합) 검색 조건을 지정는 **여기서** 레코드를 필터링 하는 절. 참조 [레코드 집합: 레코드 필터링 (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)합니다.<br /><br /> 사용할 정렬 순서를 지정 된 **ORDER BY** 레코드를 정렬 하는 절. 참조 [레코드 집합: 레코드 정렬 (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md)합니다.<br /><br /> 클래스에 추가 하는 모든 매개 변수에 대 한 매개 변수 값을 지정 합니다. 참조 [레코드 집합: 레코드 집합 (ODBC)를 매개 변수화](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)합니다.|

| 호출 하 여 레코드 집합의 쿼리를 실행할 `Open`| 마법사에서 설정 하는 기본 SQL 문자열을 대체 하는 사용자 지정 SQL 문자열을 지정 합니다. 참조 [crecordset:: Open](../../mfc/reference/crecordset-class.md#open) 에 *클래스 라이브러리 참조* 고 [SQL: 레코드 집합의 SQL 문 (ODBC) 사용자 지정](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md). |

| 호출 `Requery` 데이터 원본에서 최신 값으로 레코드 집합을 | 새 매개 변수, 필터 또는 정렬 지정 합니다. 참조 [레코드 집합: (ODBC) 레코드 집합 다시 쿼리](../../data/odbc/recordset-requerying-a-recordset-odbc.md). |

##  <a name="_core_how_a_recordset_constructs_its_sql_statement"></a> 레코드 집합의 SQL 문을 생성 하는 방법

레코드 집합 개체를 호출 하는 경우 [열려](../../mfc/reference/crecordset-class.md#open) 멤버 함수 `Open` 다음 재료 중 일부나 전부를 사용 하 여 SQL 문을 생성 합니다.

- 합니다 *lpszSQL* 전달 된 매개 변수가 `Open`합니다. NULL이 아닌 경우이 매개 변수 중 일부나 사용자 지정 SQL 문자열을 지정 합니다. 프레임 워크는 문자열을 구문 분석 합니다. 문자열 SQL 이면 **선택** 문이나 ODBC **호출** 문, 프레임 워크에서는 레코드 집합의 SQL 문으로 문자열을 사용 합니다. 프레임 워크에 공급 되는 SQL을 생성 하는 문자열 "선택" 또는 "{CALL"로 시작 하지 않으면, **FROM** 절.

- 반환한 문자열 [GetDefaultSQL](../../mfc/reference/crecordset-class.md#getdefaultsql)합니다. 기본적으로 마법사에서 레코드 집합에 대 한 지정 된 테이블의 이름 이지만 함수에서 반환 하는 항목을 변경할 수 있습니다. 프레임 워크 호출 `GetDefaultSQL` -문자열 "선택" 또는 "{CALL"로 시작 하지 않으므로, SQL 문자열을 생성 하는 데 사용 되는 테이블 이름으로 간주 됩니다.


- 필드 데이터 멤버 레코드의 테이블의 특정 열에 바인딩되어야 하는입니다. 프레임 워크를 버퍼로 사용, 이러한 멤버의 주소로 레코드 열을 바인딩합니다. 프레임 워크에서 테이블 열을 필드 데이터 멤버의 상관 관계를 확인 합니다 [RFX](../../data/odbc/record-field-exchange-using-rfx.md) 레코드 집합의 대량 RFX 함수를 호출 하거나 [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) 또는 [DoBulkFieldExchange ](../../mfc/reference/crecordset-class.md#dofieldexchange) 멤버 함수입니다.

- [필터](../../data/odbc/recordset-filtering-records-odbc.md) 에 포함 된 레코드 집합 있으면 합니다 [m_strFilter](../../mfc/reference/crecordset-class.md#m_strfilter) 데이터 멤버입니다. SQL을 생성 하려면이 문자열을 사용 하는 프레임 워크 **여기서** 절.

- 합니다 [정렬](../../data/odbc/recordset-sorting-records-odbc.md) 레코드 집합에 포함 되어 있는 경우 순서는 [m_strSort](../../mfc/reference/crecordset-class.md#m_strsort) 데이터 멤버입니다. SQL을 생성 하려면이 문자열을 사용 하는 프레임 워크 **ORDER BY** 절.

   > [!TIP]
   > SQL을 사용 하 **GROUP BY** 절 (및 합니다 **HAVING** 절)을 필터 문자열의 끝에 절을 추가 합니다.

- 모든 값 [매개 변수 데이터 멤버](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) 클래스에 지정 합니다. 호출 하기 바로 전에 매개 변수 값을 설정한 `Open` 또는 `Requery`합니다. 프레임 워크 바인딩하여 매개 변수 값을 "?"는 SQL 문자열의 자리 표시자입니다. 컴파일 타임에 자리 표시자를 사용 하 여 문자열을 지정 합니다. 런타임 시 프레임 워크를 전달 하면 매개 변수 값을 기반으로 하는 세부 정보를 채웁니다.

`Open` SQL 구문 **선택** 이러한 구성 요소에서 문입니다. 참조 [선택 사용자 지정](#_core_customizing_the_selection) 프레임 워크 재료를 사용 하는 방법에 대 한 세부 정보에 대 한 합니다.

문을 생성 한 후 `Open` SQL ODBC 드라이버 관리자 (및 메모리에 있을 경우 ODBC 커서 라이브러리)를 보냅니다는 보냅니다 ODBC 드라이버는 특정 DBMS에 대 한 합니다. 드라이버는 데이터 원본에서 선택 영역을 수행 하는 DBMS와 통신 하 고 첫 번째 레코드를 인출 합니다. 프레임 워크는 레코드 집합의 필드 데이터 멤버에 레코드를 로드합니다.

이러한 기술 함께 사용 하 여 열려는 [테이블](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md) 및 쿼리를 기반으로 생성 하는 [조인](../../data/odbc/recordset-performing-a-join-odbc.md) 여러 테이블. 추가 사용자 지정을 사용 하 여 호출할 수 있습니다 [미리 정의 된 쿼리](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md) (저장된 프로시저) 선택 테이블 디자인 타임에 알 수 없는 열 및 [바인딩할](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md) 대부분의 다른 수행할 수 있습니다 하거나 레코드 집합 필드 데이터 액세스 작업입니다. 레코드 집합을 사용자 지정 하 여 수행할 수 없는 작업을 수행할 수 [ODBC API 함수 호출](../../data/odbc/odbc-calling-odbc-api-functions-directly.md) 사용 하 여 SQL 문을 직접 실행 하거나 [CDatabase::ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql)합니다.

##  <a name="_core_customizing_the_selection"></a> 선택 영역을 사용자 지정

필터, 정렬 순서를 또는 매개 변수를 제공 하는 것 외에도 레코드 집합의 선택 영역을 사용자 지정 하는 다음 작업을 수행할 수 있습니다.

- 사용자 지정 SQL 문자열을 전달할 *lpszSQL* 호출 하는 경우 [오픈](../../mfc/reference/crecordset-class.md#open) 레코드 집합에 대 한 합니다. 아무 것도 전달 *lpsqSQL* 무엇 보다 우선 합니다 [GetDefaultSQL](../../mfc/reference/crecordset-class.md#getdefaultsql) 멤버 함수를 반환 합니다.

   자세한 내용은 참조 하세요. [SQL: 레코드 집합의 SQL 문 (ODBC) 사용자 지정](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md), 형식에 설명 하는 SQL 문 (또는 부분 문)를 전달할 수 있습니다 `Open` 프레임 워크를 수행 하는 역할을 사용 하 여 합니다.

    > [!NOTE]
    >  전달 하 여 사용자 지정 문자열 "선택" 또는 "{CALL"로 시작 하지 않으므로, MFC 테이블 이름이 포함 된 것으로 가정 합니다. 이 다음 글머리 기호 항목에도 적용 됩니다.

- 마법사가 레코드 집합의에서 작성 하는 문자열을 alter `GetDefaultSQL` 멤버 함수입니다. 함수의 반환 값을 변경 하는 코드를 편집 합니다. 기본적으로 마법사는 다음과 같이 기록 됩니다.는 `GetDefaultSQL` 단일 테이블 이름을 반환 하는 함수입니다.

   할 수 있습니다 `GetDefaultSQL` 에 전달할 수 있는 항목 중 하나를 반환 합니다 *lpszSQL* 매개 변수를 `Open`입니다. 사용자 지정 SQL 문자열을 전달 하지 않습니다 *lpszSQL*, 문자열을 사용 하는 프레임 워크는 `GetDefaultSQL` 반환 합니다. 최소한 `GetDefaultSQL` 단일 테이블 이름을 반환 해야 합니다. 여러 테이블 이름 전체를 반환 하도록 할 수도 있습니다 하지만 **선택** 문에서 ODBC **호출** 문 및 등입니다. 에 전달할 수의 목록을 *lpszSQL* -있거나 `GetDefaultSQL` 반환-참조 [SQL: 레코드 집합의 SQL 문 (ODBC) 사용자 지정](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)합니다.

   두 개 이상의 테이블의 조인을 수행 하는 경우 다시 작성 `GetDefaultSQL` SQL에 사용 되는 테이블 목록에 맞게 **FROM** 절. 자세한 내용은 참조 하세요. [레코드 집합: 조인 수행 (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)합니다.


- 수동으로 아마도 정보를 기반으로 가져와야 스키마에 대 한 데이터 원본의 런타임 시 추가 필드 데이터 멤버를 바인딩하십시오. 레코드 집합 클래스에 필드 데이터 멤버를 추가한 [RFX](../../data/odbc/record-field-exchange-using-rfx.md) 대량 RFX 함수를 호출 하기 위해 또는 합니다 [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) 또는 [DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) 멤버 함수 및 클래스 생성자에서 데이터 멤버의 초기화 합니다. 자세한 내용은 참조 하세요. [레코드 집합: (ODBC) 데이터 열 동적 바인딩](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)합니다.

- 멤버 함수는 레코드 집합을 같은 재정의 `OnSetOptions`, 응용 프로그램별 옵션을 설정 하거나 기본값을 재정의 합니다.

복잡 한 SQL 문을 기반으로 레코드 집합 하려는 경우 이러한 사용자 지정 기술 함께 사용 해야 합니다. 예를 들어, 아마도 SQL 절을 사용 하고자 할 및을 여러 테이블 조인 하는 키워드를 직접 지원 되지 않는 레코드 집합 또는 등이 있습니다.

## <a name="see-also"></a>참고자료

[레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[레코드 집합: 레코드 집합 업데이트 (ODBC)를 기록 하는 방법](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)<br/>
[ODBC 기본 사항](../../data/odbc/odbc-basics.md)<br/>
[SQL](../../data/odbc/sql.md)<br/>
[레코드 집합: 레코드 잠금 (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)