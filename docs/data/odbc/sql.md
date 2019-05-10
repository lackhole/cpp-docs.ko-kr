---
title: SQL
ms.date: 11/04/2016
helpviewer_keywords:
- database classes [C++], SQL statements
- SQL [C++]
- SQL [C++], ODBC
- ODBC [C++], SQL implementation
ms.assetid: e3923bc4-b317-4e0b-afd8-3cd403eb0faf
ms.openlocfilehash: 8f93d97530068695359273b523e7d2ae46de01cb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62329894"
---
# <a name="sql"></a>SQL

SQL (Structured Query Language)은 정의 쿼리, 수정 및 데이터를 제어할 수 있는 관계형 데이터베이스와 통신 하는 방법입니다. SQL 구문을 사용 하 여, 사용자가 지정한 조건에 따라 레코드를 추출 하는 문을 생성할 수 있습니다.

> [!NOTE]
>  이 정보는 MFC ODBC 클래스에 적용 됩니다. MFC DAO 클래스를 사용 하 여 작업 하는 경우에 DAO 도움말의 ANSI SQL 및 항목 비교 Microsoft Jet 데이터베이스 엔진 SQL 참조 하세요.

SQL 문 같은 키워드 동사를 사용 하 여 시작 **CREATE** 또는 **선택**합니다. SQL은 매우 강력한 언어입니다. 단일 문의 전체 테이블을 발생할 수 있습니다.

여러 버전의 SQL 각 개발 염두에서 특정 DBMS에 있습니다. MFC 데이터베이스 클래스에는 x / Open 해당 하는 SQL 문 및 SQL 액세스 그룹 일반적인 응용 프로그램 환경 (CAE) SQL 초안 (1991) 사양 집합을 인식 합니다. 이러한 문의 구문에 대 한 정보를 참조 부록 C 합니다 *ODBC SDK* *프로그래머 참고 자료* MSDN 라이브러리 cd 합니다.

이 항목에 설명 합니다.

- [ODBC 및 SQL 사이의 관계](#_core_open_database_connectivity_.28.odbc.29)합니다.

- [데이터베이스 클래스에서 사용 된 가장 일반적인 SQL 키워드](#_core_the_database_classes)합니다.

- [데이터베이스 클래스는 SQL을 사용 하는 방법을](#_core_how_the_database_classes_use_sql)합니다.

##  <a name="_core_open_database_connectivity_.28.odbc.29"></a> ODBC (open Database Connectivity)

데이터베이스 클래스는 SQL 코드에서 SQL 명령을 포함 하는 것이 아니라 호출 수준 인터페이스를 사용 하는 ODBC를 사용 하 여 구현 됩니다. ODBC SQL을 사용 하 여와 통신 하는 [데이터 원본](../../data/odbc/data-source-odbc.md) ODBC 드라이버를 통해. 이러한 드라이버는 SQL을 해석 하 고, Microsoft Access와 같은 특정 데이터베이스 형식으로 사용 하기 위해 필요한 경우 변환 합니다. ODBC SQL을 사용 하는 방법에 대 한 자세한 내용은 참조 하십시오 [ODBC](../../data/odbc/odbc-basics.md) 및 ODBC SDK *프로그래머 참고 자료* MSDN 라이브러리 cd 합니다.

##  <a name="_core_the_database_classes"></a> 데이터베이스 클래스

데이터베이스 클래스를 조작 하 고 기존 데이터를 업데이트할 수 있도록 고안 된 [데이터 원본](../../data/odbc/data-source-odbc.md)합니다. [MFC 응용 프로그램 마법사](../../mfc/reference/database-support-mfc-application-wizard.md)의 [MFC ODBC 소비자 마법사](../../mfc/reference/adding-an-mfc-odbc-consumer.md) (통해 액세스할 **클래스 추가**), 데이터베이스 클래스를 대부분의 SQL 문 생성 합니다.

데이터베이스 클래스는 데이터 조작 언어 (dml) SQL 부분을 사용 합니다. 이러한 명령은 사용 하 여 전체 또는 일부 데이터 원본의 사용, 새 레코드를 추가, 레코드를 편집 및 레코드를 삭제할 수 있습니다. 다음 표에서 가장 일반적인 SQL 키워드 및 방법 데이터베이스 클래스를 사용 합니다.

### <a name="some-common-sql-keywords"></a>일반적인 SQL 키워드

|SQL 키워드|마법사 및 데이터베이스 클래스 사용|
|-----------------|---------------------------------------------|
|**SELECT**|사용 해야 하는 테이블 및 데이터 원본에서 열을 식별 합니다.|
|**WHERE**|선택 항목을 범위를 좁히는 필터를 적용 합니다.|
|**ORDER BY**|레코드 집합에 정렬 순서를 적용 합니다.|
|**INSERT**|레코드 집합에 새 레코드를 추가 합니다.|
|**DELETE**|레코드 집합에서 레코드를 삭제 합니다.|
|**UPDATE**|레코드의 필드를 수정 합니다.|

또한 데이터베이스 클래스를 인식 ODBC **호출** 일부 데이터 소스에 대해 미리 정의 된 쿼리 (또는 저장된 프로시저)를 호출 하는 데 사용할 수 있는 문. ODBC 데이터베이스 드라이버 이러한 문을 해석 하 고 각 DBMS에 대 한 적절 한 명령을 대체 합니다.

> [!NOTE]
>  일부 Dbms 지원 **호출** 문입니다.

클래스에서 사용자가 제공한 문을 인식할 수 없는 경우 `CRecordset::Open`, 테이블 이름으로 해석 됩니다.

프레임 워크 SQL 문을 생성 하는 방법의 설명은 참조 하세요. [레코드 집합: 레코드 집합 선택 (ODBC)를 기록 하는 방법](../../data/odbc/recordset-how-recordsets-select-records-odbc.md) 고 [SQL: 레코드 집합의 SQL 문 (ODBC) 사용자 지정](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)합니다.

SQL 데이터베이스 C에 사용 되는 것과 비슷한 데이터 형식을 사용 하 고 C++입니다. 이러한 유사성 설명은 참조 하세요. [SQL: SQL 및 C++ 데이터 형식 (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)합니다.

SQL, 지원 되는 SQL 문, 데이터 형식, SQL core 문법 및 읽기 목록을 SQL에 대 한 권장 되는 게시의 목록을 포함 하는 방법에 대 한 자세한 정보를 찾을 수 있습니다 합니다 *ODBC SDK* *프로그래머 참고 자료*  MSDN 라이브러리 cd 합니다.

##  <a name="_core_how_the_database_classes_use_sql"></a> 데이터베이스 클래스는 SQL을 사용 하는 방법

데이터베이스 클래스에서 파생 된 레코드 집합은 ODBC를 사용 하 여 데이터 소스와 통신 하 고 ODBC SQL 문을 전송 하 여 데이터 원본에서 레코드를 검색 합니다. 이 항목에서는 데이터베이스 클래스와 SQL 간의 관계를 설명 합니다.

레코드 집합에 SQL 문의 여러 부분을 구축 하 여 SQL 문을 생성 한 `CString`합니다. 해당 문자열으로 생성 됩니다는 **선택** 레코드 집합을 반환 하는 문입니다.

레코드 집합에서 ODBC 데이터 원본에 SQL 문을 보내는를 호출 하면 ODBC 드라이버 관리자에서 ODBC 드라이버에 문을 전달 하 고 드라이버 원본 DBMS에 보냅니다. DBMS 레코드를 결과 집합을 반환 하 고 ODBC 드라이버 응용 프로그램에 레코드를 반환 합니다. 데이터베이스 클래스 수를 형식이 안전한에 결과 집합에 액세스 하는 프로그램 C++ 에서 파생 된 클래스 `CRecordset`합니다.

데이터베이스 클래스는 SQL을 사용 하는 방법에 대 한 자세한 정보를 제공 하는 다음 항목:

- [SQL: 레코드 집합의 SQL 문 (ODBC) 사용자 지정](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)

- [SQL: SQL 및 C++ 데이터 형식(ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)

- [SQL: SQL 직접 호출(ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)

## <a name="see-also"></a>참고자료

[ODBC(Open Database Connectivity)](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[ODBC 기본 사항](../../data/odbc/odbc-basics.md)