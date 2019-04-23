---
title: 'SQL: SQL 및 C++ 데이터 형식 (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- data types [C++], SQL vs. C++
- SQL data types [C++]
- SQL [C++], vs. C++ data types
ms.assetid: 066e0070-d4da-435c-9c4b-f7cab3352c86
ms.openlocfilehash: 3efa36342b7d16968113acd818a7a1386e4cefcc
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59024350"
---
# <a name="sql-sql-and-c-data-types-odbc"></a>SQL: SQL 및 C++ 데이터 형식 (ODBC)

> [!NOTE]
>  이 정보는 MFC ODBC 클래스에 적용 됩니다. MFC DAO 클래스를 사용 하 여 작업 하는 경우 비교의 Microsoft Jet 데이터베이스 엔진 SQL 및 ANSI에 "SQL" DAO 도움말 항목을 참조 하세요.

다음 표에서 ANSI SQL 데이터 형식을 C++ 데이터 형식입니다. 부록 D의에서 제공 하는 C 언어 정보를 보완 하는이 *ODBC SDK* *프로그래머 참고 자료* MSDN 라이브러리 cd 합니다. 마법사는 대부분의 데이터 형식 매핑을 관리합니다. 마법사를 사용 하지 않는 경우 수동으로 필드 exchange 코드를 작성할 수 있도록 매핑 정보를 사용할 수 있습니다.

### <a name="ansi-sql-data-types-mapped-to-c-data-types"></a>ANSI SQL 데이터 형식에 매핑된 C++ 데이터 형식

|ANSI SQL 데이터 형식|C++ 데이터 형식|
|------------------------|---------------------|
|**CHAR**|`CString`|
|**DECIMAL**|`CString` 1|
|**SMALLINT**|**int**|
|**REAL**|**float**|
|**INTEGER**|**long**|
|**FLOAT**|**double**|
|**DOUBLE**|**double**|
|**NUMERIC**|`CString` 1|
|**VARCHAR**|`CString`|
|**LONGVARCHAR**|`CLongBinary`, `CString` 2|
|**BIT**|**BOOL**|
|**TINYINT**|**BYTE**|
|**BIGINT**|`CString` 1|
|**BINARY**|`CByteArray`|
|**VARBINARY**|`CByteArray`|
|**LONGVARBINARY**|`CLongBinary`, `CByteArray` 3|
|**DATE**|`CTime`, `CString`|
|**TIME**|`CTime`, `CString`|
|**TIMESTAMP**|`CTime`, `CString`|

1. ANSI **10 진수** 하 고 **숫자** 매핑할 `CString` 때문에 **SQL_C_CHAR** 기본 ODBC 전송 형식입니다.

2. 에 매핑할 때 기본적으로 255 자 넘는 문자 데이터는 잘립니다 `CString`합니다. 명시적으로 설정 하 여 잘림을 길이 확장할 수 있습니다 합니다 *nMaxLength* 인수의 `RFX_Text`합니다.

3. 255 자 초과 하 여 이진 데이터에 매핑된 경우 기본적으로 잘렸습니다. `CByteArray`합니다. 명시적으로 설정 하 여 잘림을 길이 확장할 수 있습니다 합니다 *nMaxLength* 인수의 `RFX_Binary`합니다.

ODBC 커서 라이브러리를 사용 하지 않는 경우에 두 개를 업데이트 하려고 할 때 또는 Microsoft SQL Server ODBC 드라이버와 MFC ODBC 데이터베이스 클래스를 사용 하 여 더 긴 가변 길이 필드 문제가 발생할 수 있습니다. ODBC 형식 **SQL_LONGVARCHAR** 하 고 **SQL_LONGVARBINARY**, 텍스트에 매핑 및 SQL Server 형식 이미지입니다. A `CDBException` 같은 호출에서 두 개 이상의 긴 가변 길이 필드를 업데이트 하는 경우 throw 되 `CRecordset::Update`합니다. 따라서 사용 하 여 동시에 여러 개의 긴 열을 업데이트 하지 않으면 `CRecordset::Update`합니다. ODBC API를 사용 하 여 동시에 여러 개의 긴 열을 업데이트할 수 있습니다 `SQLPutData`합니다. ODBC 커서 라이브러리를 사용할 수도 있습니다 하지만 커서 라이브러리를 사용할 필요가 없습니다 및 커서를 지 원하는 드라이버에서 SQL Server 드라이버와 같은 권장 되지 않습니다.

MFC ODBC 데이터베이스 클래스와 Microsoft SQL Server ODBC 드라이버는 ODBC 커서 라이브러리를 사용 하는 경우는 **ASSERT** 와 함께 발생할 수 있습니다는 `CDBException` 호출 하는 경우 `CRecordset::Update` 호출한 `CRecordset::Requery`합니다. 대신, 호출 `CRecordset::Close` 하 고 `CRecordset::Open` 대신 `CRecordset::Requery`합니다. 다른 방법은 ODBC 커서 라이브러리를 사용 하지는 하는 것입니다.

## <a name="see-also"></a>참고자료

[SQL](../../data/odbc/sql.md)<br/>
[SQL: SQL 직접 호출 (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)