---
title: 'SQL: 레코드 집합의 SQL 문 (ODBC) 사용자 지정'
ms.date: 11/04/2016
helpviewer_keywords:
- recordsets, SQL statements
- ODBC recordsets, SQL statements
- SQL statements, customizing
- SQL statements, recordset
- customizing SQL statements
- overriding, SQL statements
- SQL, opening recordsets
ms.assetid: 72293a08-cef2-4be2-aa1c-30565fcfbaf9
ms.openlocfilehash: eabaab019ee94b0c5617573c534d920ec710e9b2
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59036197"
---
# <a name="sql-customizing-your-recordsets-sql-statement-odbc"></a>SQL: 레코드 집합의 SQL 문 (ODBC) 사용자 지정

이 항목에 설명 합니다.

- 프레임 워크 SQL 문을 생성 하는 방법

- SQL 문을 재정의 하는 방법

> [!NOTE]
>  이 정보는 MFC ODBC 클래스에 적용 됩니다. MFC DAO 클래스를 사용 하 여 작업 하는 경우 비교의 Microsoft Jet 데이터베이스 엔진 SQL 및 ANSI에 "SQL" DAO 도움말 항목을 참조 하세요.

## <a name="sql-statement-construction"></a>SQL 문 생성

레코드 집합 기반 SQL에서 주로 레코드 선택을 **선택** 문입니다. 재정의 된 버전의 마법사를 사용 하 여 클래스를 선언 하는 경우 기록 합니다 `GetDefaultSQL` 멤버 함수는 다음과 같습니다 (레코드 집합 클래스에 대 한 호출 `CAuthors`).

```cpp
CString CAuthors::GetDefaultSQL()
{
    return "AUTHORS";
}
```

이 재정의 기본적으로 마법사를 사용 하 여 지정한 테이블 이름을 반환 합니다. 예에서 테이블 이름은 "작성자"로 지정 합니다. 나중에 호출 하는 경우 레코드 집합의 `Open` 멤버 함수 `Open` 최종 생성 **선택** 폼의 문:

```
SELECT rfx-field-list FROM table-name [WHERE m_strFilter]
       [ORDER BY m_strSort]
```

여기서 `table-name` 호출 하 여 가져옵니다 `GetDefaultSQL` 하 고 `rfx-field-list` RFX 함수 호출에서 가져온 `DoFieldExchange`합니다. 통해 여러분이 얻는 결과이 **선택** 문을 바꾼 경우가 아니라면이 재정의 사용 하 여 런타임 시 매개 변수 또는 필터를 사용 하 여 기본 문을 수정할 수도 있습니다.

> [!NOTE]
>  공백 포함 (또는 포함 될 수 있습니다)는 열 이름을 지정 하면 이름을 대괄호로 묶어야 합니다. 예를 들어, "이름" 이름 "[이름]" 해야 합니다.

기본값을 재정의 하려면 **선택** 문, 전체를 포함 하는 문자열 전달 **선택** 문을 호출 하는 경우 `Open`합니다. 레코드 집합 자체 기본 문자열을 생성 하는 대신 제공한 문자열을 사용 합니다. 대체 문에 포함 된 경우는 **여기서** 절에서 필터를 지정 하지 않으면 `m_strFilter` 하는 두 개의 문을 필터링 합니다. 마찬가지로, 대체 문에 포함 된 경우는 **ORDER BY** 절에 정렬을 지정 하지 않으면 `m_strSort` 문이 있습니다 있도록 정렬 합니다.

> [!NOTE]
>  "따옴표" 할 필터 (또는 SQL 문의 다른 부분)에서 리터럴 문자열을 사용 하는 경우 (지정 된 구분 기호로 묶습니다) 이러한 문자열 리터럴 및 DBMS 관련 리터럴 접두사와 접미사 문자 (또는 문자).

DBMS에 따라 우선 외부 조인 등의 작업에 대 한 특별 한 구문 요구도 발생할 수 있습니다. ODBC 함수를 사용 하 여 DBMS에 대 한 드라이버에서이 정보를 가져옵니다. 예를 들어, 호출 `::SQLGetTypeInfo` 특정 데이터 형식의 경우와 같은 `SQL_VARCHAR`LITERAL_PREFIX 자 LITERAL_SUFFIX 요청을 합니다. 데이터베이스에 관계 없이 코드를 작성 하는 경우 참조 [부록 c: SQL 문법을](/sql/odbc/reference/appendixes/appendix-c-sql-grammar) 에 [ODBC 프로그래머 참조](/sql/odbc/reference/odbc-programmer-s-reference) 자세한 구문 정보에 대 한 합니다.

레코드 집합 개체는 사용자 지정 SQL 문을 전달 하지 않은 경우에 레코드를 선택 하는 데 사용 하는 SQL 문을 생성 합니다. 주로에 전달 하는 값에 따라 달라 집니다 방식은 합니다 *lpszSQL* 의 매개 변수를 `Open` 멤버 함수입니다.

일반 SQL 형태의 **선택** 문은:

```
SELECT [ALL | DISTINCT] column-list FROM table-list
    [WHERE search-condition][ORDER BY column-list [ASC | DESC]]
```

추가 하는 한 가지 방법은 합니다 **DISTINCT** 레코드 집합의 SQL 문에 키워드는 첫 번째 RFX 함수 호출에 키워드를 포함할 `DoFieldExchange`합니다. 예를 들어:

```
...
    RFX_Text(pFX, "DISTINCT CourseID", m_strCourseID);
...
```

> [!NOTE]
>  읽기 전용으로 열린 레코드 집합에만이 기술을 사용 합니다.

## <a name="overriding-the-sql-statement"></a>SQL 문을 재정의

다음 테이블에 대 한 가능성을 보여 합니다 *lpszSQL* 매개 변수를 `Open`입니다. 테이블의 경우 표 다음에 설명 되어 있습니다.

**LpszSQL 매개 변수 및 결과 SQL 문자열**

|사례|LpszSQL에서 통과|결과 SELECT 문에|
|----------|------------------------------|------------------------------------|
|1|NULL|**SELECT** *rfx-field-list* **FROM** *table-name*<br /><br /> `CRecordset::Open` 호출 `GetDefaultSQL` 테이블 이름을 가져옵니다. 결과 문자열을 사용 하면 내용에 따라 2 ~ 5 사례 중 하나인 `GetDefaultSQL` 반환 합니다.|
|2|테이블 이름|**SELECT** *rfx-field-list* **FROM** *table-name*<br /><br /> 필드 목록에서 RFX 문에서 만들어진 `DoFieldExchange`합니다. 경우 `m_strFilter` 하 고 `m_strSort` 비어 있지 않으며, 추가 합니다 **여기서** 및/또는 **ORDER BY** 절.|
|3 \*|전체 **선택** 문 없이 **여기서** 하거나 **ORDER BY** 절|전달 합니다. 경우 `m_strFilter` 하 고 `m_strSort` 비어 있지 않으며, 추가 합니다 **여기서** 및/또는 **ORDER BY** 절.|
|4 \*|완전 **선택** 문을 사용 하 여를 **여기서** 및/또는 **ORDER BY** 절|전달 합니다. `m_strFilter` 및/또는 `m_strSort` 해야 비어 있거나 두 개의 필터를 유지 및/또는 정렬 문이 생성 됩니다.|
|5 \*|저장된 프로시저에 대 한 호출|전달 합니다.|

\* `m_nFields` 지정한 열 개수 보다 작거나 같아야 합니다 **선택** 문입니다. 에 지정 된 각 열의 데이터 형식을 합니다 **선택** 문을 해당 되는 RFX 출력 열의 데이터 형식과 동일 해야 합니다.

### <a name="case-1---lpszsql--null"></a>Case 1   lpszSQL = NULL

레코드 집합 선택에 따라 달라 집니다 `GetDefaultSQL` 될 때 반환 `CRecordset::Open` 호출 합니다. 2 ~ 5의 경우 가능한 문자열을 설명 합니다.

### <a name="case-2---lpszsql--a-table-name"></a>사례 2 lpszSQL = 테이블 이름

레코드 집합 레코드 필드 교환 (RFX)를 사용 하 여 레코드 집합 클래스의 재정의에서 호출 함수는 RFX에 제공 된 열 이름에서 열 목록을 작성할 `DoFieldExchange`합니다. 레코드 집합 클래스를 선언 하는 마법사를 사용 하는 경우이 여기서가 생깁니다 사례 1과 같은 결과 (마법사에서 지정한 테이블 이름이 전달). 사례 2 클래스를 작성 하는 마법사를 사용 하지 않는 경우 SQL 문을 생성에 대 한 가장 간단한 방법입니다.

다음 예제에서는 MFC 데이터베이스 응용 프로그램에서 레코드를 선택 하는 SQL 문을 생성 합니다. 프레임 워크를 호출 하는 경우는 `GetDefaultSQL` 멤버 함수는 테이블의 이름을 반환 합니다. `SECTION`합니다.

```cpp
CString CEnrollSet::GetDefaultSQL()
{
    return "SECTION";
}
```

SQL에 대 한 열의 이름을 가져오는 **선택** 문, 프레임 워크 호출을 `DoFieldExchange` 멤버 함수입니다.

```cpp
void CEnrollSet::DoFieldExchange(CFieldExchange* pFX)
{
    pFX->SetFieldType(CFieldExchange::outputColumn);
    RFX_Text(pFX, "CourseID", m_strCourseID);
    RFX_Text(pFX, "InstructorID", m_strInstructorID);
    RFX_Text(pFX, "RoomNo", m_strRoomNo);
    RFX_Text(pFX, "Schedule", m_strSchedule);
    RFX_Text(pFX, "SectionNo", m_strSectionNo);
}
```

완료 되 면 SQL 문을 다음과 같이 표시 됩니다.

```sql
SELECT CourseID, InstructorID, RoomNo, Schedule, SectionNo
    FROM SECTION
```

### <a name="case-3---lpszsql--a-selectfrom-statement"></a>Case 3   lpszSQL = a SELECT/FROM Statement

Rfx를 자동으로 생성 하는 대신 열 목록을 직접 지정 합니다. 이 경우 작업을 수행 하는 것이 좋습니다.

- 지정 하려는 합니다 **DISTINCT** 키워드 다음 **선택**합니다.

   에 나열 된 대로 열 목록 열 이름 및 형식을 동일한 순서로 일치 해야 `DoFieldExchange`합니다.

- ODBC 함수를 사용 하 여 열 값을 수동으로 검색 하는 이유가 `::SQLGetData` rfx 바인딩하고 있습니다에 대 한 열을 검색 하는 대신 합니다.

   예를 들어, 응용 프로그램을 배포한 후 응용 프로그램의 고객 데이터베이스 테이블에 추가 된 새 열을 수용 하려면 할 수 있습니다. 마법사를 사용 하 여 클래스를 선언 하는 시간에 알 수 없었던 이러한 추가 필드 데이터 멤버를 추가 해야 합니다.

   에 나열 된 대로 열 목록 열 이름 및 형식을 동일한 순서로 일치 해야 `DoFieldExchange`고 뒤에 직접 바인딩한 열 이름입니다. 자세한 내용은 참조 하세요. [레코드 집합: (ODBC) 데이터 열 동적 바인딩](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)합니다.

- 여러 테이블을 지정 하 여 테이블을 조인 하려는 합니다 **FROM** 절.

   내용 및 예제를 참조 하세요. [레코드 집합: 조인 수행 (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)합니다.

### <a name="case-4---lpszsql--selectfrom-plus-where-andor-order-by"></a>사례 4 lpszSQL = SELECT / FROM 및 WHERE 및/또는 ORDER BY

모든 지정할: 열 목록 (RFX 호출 기반 `DoFieldExchange`)의 내용과 테이블 목록에서를 **여기서** 및/또는 **ORDER BY** 절. 지정 하는 경우에 **여기서** 및/또는 **ORDER BY** 절이 방식이으로 사용 하지 마십시오 `m_strFilter` 및/또는 `m_strSort`합니다.

### <a name="case-5---lpszsql--a-stored-procedure-call"></a>사례 5 lpszSQL = 저장 된 프로시저 호출

작성 해야 합니다 (예: Microsoft SQL Server 데이터베이스의 저장된 프로시저)는 미리 정의 된 쿼리를 호출 해야 할 경우는 **호출** 전달 하는 문자열에는 문을 *lpszSQL*합니다. 마법사 미리 정의 된 쿼리를 호출 하는 것에 대 한 레코드 집합 클래스를 선언 하는 것을 지원 하지 않습니다. 모든 미리 정의 된 쿼리에 레코드를 반환 합니다.

미리 정의 된 쿼리 레코드를 반환 하지 않으면 하는 경우 사용할 수 있습니다 합니다 `CDatabase` 멤버 함수 `ExecuteSQL` 직접. 레코드를 반환 하는 미리 정의 된 쿼리를 수동으로 작성 해야는 RFX 호출 `DoFieldExchange` 모든 열에 대 한 프로시저에서 반환 합니다. RFX 호출은 동일한 순서 여야 하 고 미리 정의 된 쿼리와 동일한 형식을 반환 해야 합니다. 자세한 내용은 참조 하세요. [레코드 집합: 미리 정의 된 쿼리 (ODBC)에 대 한 클래스 선언](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)합니다.

## <a name="see-also"></a>참고자료

[SQL: SQL 및 C++ 데이터 형식 (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)<br/>
[SQL: SQL 직접 호출 (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)
