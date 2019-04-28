---
title: 트랜잭션(ODBC)
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC recordsets [C++], updating
- transactions [C++], MFC ODBC classes
- ODBC [C++], transactions
- recordsets [C++], updating
- databases [C++], transactions
- recordsets [C++], transactions
- ODBC recordsets [C++], transactions
ms.assetid: a2ec0995-2029-45f2-8092-6efd6f2a77f4
ms.openlocfilehash: a151ec5ca2b4bdc19bfa7dc626aebda0740a2c9e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62329922"
---
# <a name="transaction-odbc"></a>트랜잭션(ODBC)

이 항목에서는 MFC ODBC 클래스에 적용됩니다.

트랜잭션이 그룹 또는 일괄 처리를 일련의 업데이트를 하는 방법은 [데이터 원본](../../data/odbc/data-source-odbc.md) 한 번에 커밋된 모두 또는 트랜잭션을 롤백하는 경우 커밋된 모두가 있도록 합니다. 트랜잭션을 사용 하지 않는 데이터 원본의 변경 내용이 필요할 때 커밋되는 대신 자동으로 커밋됩니다.

> [!NOTE]
>  일부 ODBC 데이터베이스 드라이버는 트랜잭션을 지원 합니다. 호출 된 `CanTransact` 멤버 함수에 [CDatabase](../../mfc/reference/cdatabase-class.md) 또는 [CRecordset](../../mfc/reference/crecordset-class.md) 드라이버 지정된 된 데이터베이스에 대 한 트랜잭션을 지원 하는지 여부를 결정 하는 개체입니다. `CanTransact` 알려주지 않습니다 데이터 원본 전체 트랜잭션 지원을 제공 하는지 여부입니다. 도 호출 해야 합니다 `CDatabase::GetCursorCommitBehavior` 하 고 `CDatabase::GetCursorRollbackBehavior` 후 `CommitTrans` 하 고 `Rollback` 열기 트랜잭션의 효과를 확인 `CRecordset` 개체입니다.

에 대 한 호출을 `AddNew` 및 `Edit` 의 멤버 함수는 `CRecordset` 영향을 호출 하는 경우 즉시 데이터 원본 개체 `Update`합니다. `Delete` 호출도 즉시 적용 됩니다. 반면에 대 한 여러 호출로 구성 된 트랜잭션을 사용할 수 있습니다 `AddNew`, `Edit`를 `Update`, 및 `Delete`를 호출할 때까지 커밋되지 않은 수행 되는 `CommitTrans` 명시적으로 합니다. 트랜잭션을 설정 하 여 해당 사용자에 게 롤백할 수 있는 기능을 유지 하면서 일련의 이러한 호출을 실행할 수 있습니다. 중요 한 리소스를 사용할 수 없는 경우 다른 상황으로 인해 완료 되 고 전체 트랜잭션을 롤백할 수 있습니다 트랜잭션을 커밋하는 대신 합니다. 이 경우 데이터 원본에 영향을 트랜잭션에 속하는 변경 내용은 없습니다.

> [!NOTE]
>  현재 클래스 `CRecordset` 대량 행 페치를 구현한 경우 데이터 원본에 대 한 업데이트를 지원 하지 않습니다. 즉, 호출을 만들 수 없습니다 `AddNew`, `Edit`하십시오 `Delete`, 또는 `Update`. 그러나 업데이트를 수행 하 고 다음 지정 된 트랜잭션 내에서 해당 함수를 호출 하려면 함수를 직접 있습니다 것을 작성할 수 있습니다. 대량 행 페치에 대 한 자세한 내용은 참조 하세요. [레코드 집합: (ODBC) 대량 레코드 페치](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)합니다.

> [!NOTE]
>  트랜잭션 레코드 집합에 영향을 미치는 외에도 ODBC를 사용으로 직접 실행 하는 SQL 문에 영향을 **HDBC** 연관 하 `CDatabase` 개체나 ODBC **HSTMT** 기반 **HDBC**합니다.

트랜잭션은 동시에 업데이트 해야 하는 여러 레코드가 있는 경우 특히 유용 합니다. 이 경우 마지막 업데이트가 적용 되기 전에 예외가 발생 하는 경우 발생할 수 있는 것과 같은 절반만 완료 된 트랜잭션을 방지 하려고 합니다. 업데이트로 트랜잭션으로 그룹화 변경 으로부터 복구 (롤백) 되 고 트랜잭션 이전의 상태로 레코드를 반환 합니다. 예를 들어 계정 B에서 A money를 전송 하는 은행, 하는 경우 모두 b에서 A와 deposit 출금 금액을 올바르게 처리 하는 데 성공 해야 합니다 또는 전체 거래가 실패 해야 합니다.

데이터베이스 클래스를 통해 트랜잭션을 수행 `CDatabase` 개체입니다. A `CDatabase` 개체가 나타내는 데이터 원본에 연결 하 고 하나 이상의 레코드와 연결 된 `CDatabase` 레코드 집합 멤버 함수를 통해 데이터베이스의 테이블에서 개체를 실행 합니다.

> [!NOTE]
>  트랜잭션의 수준이 하나만 지원 됩니다. 트랜잭션을 중첩할 수 없습니다 또는 여러 데이터베이스 개체가 확장할 수 있습니다.

트랜잭션을 수행 하는 방법에 대 한 자세한 정보를 제공 하는 다음 항목:

- [트랜잭션: 레코드 집합에서 트랜잭션 수행(ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)

- [트랜잭션: 트랜잭션이 업데이트에 미치는 영향(ODBC)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)

## <a name="see-also"></a>참고자료

[ODBC(Open Database Connectivity)](../../data/odbc/open-database-connectivity-odbc.md)