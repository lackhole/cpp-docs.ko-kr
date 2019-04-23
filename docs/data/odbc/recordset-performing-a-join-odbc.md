---
title: '레코드 집합: 조인 수행 (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- joins [C++], in recordsets
- data binding [C++], recordset columns
- recordsets [C++], binding data
- data binding [C++], columns in recordsets
- filters [C++], join conditions for recordsets
- ODBC recordsets [C++], joins
- recordsets [C++], joining tables
ms.assetid: ca720900-a156-4780-bf01-4293633bea64
ms.openlocfilehash: 9e589f00ec0512794d14accc6bb33c0e7adbd378
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59035415"
---
# <a name="recordset-performing-a-join-odbc"></a>레코드 집합: 조인 수행 (ODBC)

이 항목에서는 MFC ODBC 클래스에 적용됩니다.

## <a name="what-a-join-is"></a>무엇을 조인은

일반적인 데이터 액세스 작업, 조인 작업을 사용 하면 단일 레코드 집합 개체를 사용 하 여 둘 이상의 테이블에서 데이터로 작업할 수 있습니다. 두 개 이상의 테이블을 조인 열에서 각 테이블에 포함 될 수 있지만 응용 프로그램에 단일 테이블로 표시 된 레코드 집합을 생성 합니다. 조인 모든 테이블, 때로는 SQL의 모든 열을 사용 하는 경우에 따라 **선택** 조인 절을 사용 하 여 각 테이블의 열 중 일부만 있습니다. 데이터베이스 클래스에는 읽기 전용으로 조인 하지만 불가능 조인을 지원 합니다.

조인 된 테이블의 열을 포함 하는 레코드를 선택 하려면 다음 항목이 필요 합니다.

- 조인 되는 모든 테이블의 이름이 포함 된 테이블 목록입니다.

- 참여 하는 모든 열 이름이 포함 된 열 목록입니다. 이름이 같지만 서로 다른 테이블의 열은 테이블 이름으로 정규화 됩니다.

- 필터 (SQL **여기서** 절) 테이블을 조인 열을 지정 하는 합니다. 이 필터 형식은 "Table1.KeyCol Table2.KeyCol =" 실제로 조인 작업을 수행 하 고 있습니다.

SQL 키워드에 의해 조인 된 여러 쌍의 열을 연결 하 여 동일한 방식으로 두 개 이상의 테이블을 조인할 수 있습니다 **AND**합니다.

## <a name="see-also"></a>참고자료

[레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[레코드 집합: 미리 정의 된 쿼리 (ODBC)에 대 한 클래스 선언](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)<br/>
[레코드 집합: 테이블 (ODBC)에 대 한 클래스 선언](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)<br/>
[레코드 집합: (ODBC) 레코드 집합 다시 쿼리](../../data/odbc/recordset-requerying-a-recordset-odbc.md)