---
title: 'SQL: SQL 직접 호출 (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- SQL, direct calls from ODBC
- SQL, calling directly from ODBC
- ODBC, SQL calls
- SQL calls
- direct SQL calls from ODBC
ms.assetid: 091988d2-f5a5-4c2d-aa09-8779a9fb9607
ms.openlocfilehash: fd528e7abb713e4b3eb2bd5388a29958a1bb006c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62329974"
---
# <a name="sql-making-direct-sql-calls-odbc"></a>SQL: SQL 직접 호출 (ODBC)

이 항목에 설명 합니다.

- 직접 SQL을 사용 하는 경우 호출 합니다.

- [데이터 원본에 대 한 호출 SQL을 직접 만드는 방법을](#_core_making_direct_sql_function_calls)합니다.

> [!NOTE]
>  이 정보는 MFC ODBC 클래스에 적용 됩니다. MFC DAO 클래스를 사용 하 여 작업 하는 경우 비교의 Microsoft Jet 데이터베이스 엔진 SQL 및 ANSI에 "SQL" DAO 도움말 항목을 참조 하세요.

##  <a name="_core_when_to_call_sql_directly"></a> SQL 직접 호출 하는 경우

새 테이블을 만들려면 (삭제) 테이블을 삭제, 기존 테이블 변경, 인덱스, 만들기 및 변경 하는 다른 SQL 함수를 수행 합니다 [데이터 원본 (ODBC)](../../data/odbc/data-source-odbc.md) 스키마 데이터베이스를 사용 하 여 데이터 원본에 직접 SQL 문을 실행 해야 합니다 정의 언어 (DDL)입니다. 마법사를 사용 하 여 (디자인 타임) 테이블에 대 한 레코드 집합을 만들 때 레코드를 나타내기 위해 테이블의 열을 선택할 수 있습니다. 이 값은 열 또는 다른 사용자 데이터 원본의 테이블에 나중에 추가할 프로그램 컴파일한 후에 대 한 허용 하지 않습니다. 데이터베이스 클래스 DDL에 직접 지원 하지 않지만 런타임에 동적으로 새 열을 레코드 집합에 바인딩하는 코드를 작성할 수 있습니다. 이 바인딩 작업을 수행 하는 방법에 대 한 자세한 내용은 [레코드 집합: (ODBC) 데이터 열 동적 바인딩](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)합니다.

스키마 또는 DDL 함수를 수행할 수 있는 다른 도구를 변경 하려면 DBMS를 사용할 수 있습니다. 또한 레코드를 반환 하지 않는 하는 미리 정의 된 쿼리 (저장된 프로시저)를 호출 하는 등의 SQL 문을 보내기 위한 ODBC 함수 호출을 사용할 수 있습니다.

##  <a name="_core_making_direct_sql_function_calls"></a> 직접 SQL 함수 호출

사용 하 여 SQL 호출을 직접 실행할 수 있습니다는 [CDatabase 클래스](../../mfc/reference/cdatabase-class.md) 개체입니다. SQL 문 문자열을 설정 (에 일반적으로 `CString`)에 전달 합니다 [CDatabase::ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql) 멤버 함수에 `CDatabase` 개체입니다. ODBC 함수 호출을 사용 하 여 일반적으로 레코드를 반환 하는 SQL 문을 보내야 하는 경우 레코드 무시 됩니다.

## <a name="see-also"></a>참고자료

[SQL](../../data/odbc/sql.md)