---
title: '레코드 집합: 업데이트 (ODBC)에 대 한 자세한 정보'
ms.date: 11/04/2016
helpviewer_keywords:
- records, updating
- transactions, updating recordsets
- ODBC recordsets, updating
- multiuser environments, updates to recordsets
- scrolling, updates to recordsets
- updating recordsets
- recordsets, updating
ms.assetid: 0353a742-d226-4fe2-8881-a7daeffe86cd
ms.openlocfilehash: c29ff110fc507c4e449b2f3d082d98c159a35107
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59040770"
---
# <a name="recordset-more-about-updates-odbc"></a>레코드 집합: 업데이트 (ODBC)에 대 한 자세한 정보

이 항목에서는 MFC ODBC 클래스에 적용됩니다.

이 항목에 설명 합니다.

- [트랜잭션과 같은 기타 작업 업데이트에 미치는 영향](#_core_how_transactions_affect_updates)합니다.

- [업데이트 및 다른 사용자의](#_core_your_updates_and_the_updates_of_other_users)합니다.

- [Update 및 Delete 멤버 함수에 대 한 자세한](#_core_more_about_update_and_delete)합니다.

> [!NOTE]
>  이 항목에서 파생 된 개체에 적용 됩니다 `CRecordset` 의 대량 행 페치 구현 되지 않았습니다. 대량 행 페치를 구현한 경우이 정보 중 일부는 적용 되지 않습니다. 그러나 예를 들어, 호출할 수 없습니다는 `AddNew`, `Edit`를 `Delete`, 및 `Update` 멤버 함수를 트랜잭션을 수행할 수 있습니다. 대량 행 페치에 대 한 자세한 내용은 참조 하세요. [레코드 집합: (ODBC) 대량 레코드 페치](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)합니다.

##  <a name="_core_how_other_operations_affect_updates"></a> 다른 작업 업데이트에 미치는 영향

업데이트는 영향을 트랜잭션에 의해 적용 업데이트 시 트랜잭션을 완료 하기 전에 레코드 집합을 닫아 트랜잭션을 완료 하기 전에 스크롤.

###  <a name="_core_how_transactions_affect_updates"></a> 트랜잭션이 업데이트에 미치는 영향

이해를 초과 하는 방법 `AddNew`, `Edit`, 및 `Delete` 알아야 할 것이 작업을 하는 방법을 `BeginTrans`, `CommitTrans`, 및 `Rollback` 의 멤버 함수 [CDatabase](../../mfc/reference/cdatabase-class.md) 작동 업데이트 기능 [CRecordset](../../mfc/reference/crecordset-class.md)합니다.

기본적으로 호출 `AddNew` 하 고 `Edit` 즉시 호출 하는 경우 데이터 원본에 영향을 `Update`입니다. `Delete` 호출 즉시 적용 됩니다. 하지만 트랜잭션을 설정 하 고 이러한 호출의 일괄 처리를 실행할 수 있습니다. 업데이트를 커밋할 때까지 저장 되지 않습니다. 마음이 바뀌면 롤백할 수 있습니다 트랜잭션을 커밋하는 대신 합니다.

트랜잭션에 대 한 자세한 내용은 참조 하세요. [트랜잭션 (ODBC)](../../data/odbc/transaction-odbc.md)합니다.

###  <a name="_core_how_closing_the_recordset_affects_updates"></a> 레코드 집합을 닫는 업데이트에 미치는 영향

레코드 집합 또는 연결 된 해당 닫으면 `CDatabase` 진행 중인 트랜잭션 사용 하 여 개체 (호출 하지 않은 [CDatabase::CommitTrans](../../mfc/reference/cdatabase-class.md#committrans) 또는 [CDatabase::Rollback](../../mfc/reference/cdatabase-class.md#rollback)), 트랜잭션이 롤백됩니다. 자동으로 (하지 않는 한 데이터베이스 백 엔드는 Microsoft Jet 데이터베이스 엔진)를 백업 합니다.

> [!CAUTION]
>  Microsoft Jet 데이터베이스 엔진을 사용 하는 경우 명시적 트랜잭션 내에서 레코드 집합을 닫으면 얻지 수정 된 행 이나 명시적 트랜잭션이 커밋되거나 롤백될 때까지 설정 된 잠금이 해제 합니다. 해당 하면 항상 모두 닫기 레코드 집합을 열고 내부 또는 외부 명시적 Jet 트랜잭션 것이 좋습니다.

###  <a name="_core_how_scrolling_affects_updates"></a> 스크롤 업데이트에 미치는 영향

때 있습니다 [레코드 집합: 스크롤 (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) 레코드 집합에서 편집 버퍼 (이전 레코드를 먼저 저장 되지 않고는) 각 새 현재 레코드를 사용 하 여 채워집니다. 이전에 삭제 된 레코드를 통해 건너뜁니다 스크롤입니다. 후 스크롤 하는 경우는 `AddNew` 하거나 `Edit` 호출 하지 않고 호출 `Update`, `CommitTrans`, 또는 `Rollback` 먼저 모든 변경 내용이 손실 됩니다 (에 경고 없음)와 새 레코드를 편집 버퍼로 되므로으로 합니다. 편집 버퍼 스크롤한 레코드로 채워집니다, 그리고 저장된 된 레코드 해제 되 면 및 데이터 원본에 변경 되지 않습니다 발생 합니다. 이 둘 다에 적용 됩니다 `AddNew` 고 `Edit`입니다.

##  <a name="_core_your_updates_and_the_updates_of_other_users"></a> 업데이트 및 다른 사용자의 업데이트

레코드 집합을 사용 하 여 데이터를 업데이트 하려면 업데이트 내용을 다른 사용자에 게를 영향을 줍니다. 마찬가지로, 레코드 집합의 수명 동안 다른 사용자의 업데이트에 영향을 줄 있습니다.

다중 사용자 환경에서 다른 사용자가 레코드 집합에서 선택한 레코드의 일부를 포함 하는 레코드 집합을 열 수 있습니다. 레코드 집합에서 레코드를 검색 하기 전에 변경 내용이 반영 됩니다. 다이너셋은 레코드를 스크롤할 때마다를 검색 하기 때문에 레코드를 스크롤할 때마다 변경 내용을 반영 합니다. 스냅숏 하므로 처음에 레코드를 스크롤하고 전에 발생 하는 변경 내용만 반영을 스크롤하면 처음으로 레코드를 검색 합니다.

레코드 집합을 연 후 다른 사용자가 추가 된 레코드 수행 다시 쿼리하지 않는 한 레코드 집합에 나타나지 않습니다. 레코드 집합 다이너셋 이면 다른 사용자가 기존 레코드 편집 표시지 않습니다 다이너셋에 영향을 받는 레코드를 스크롤할 때. 레코드 집합 스냅숏으로 인 경우 스냅숏이 다시 쿼리 해도 편집 표시 되지 않습니다. 추가 된 레코드를 참조 하거나 호출 하 여 스냅숏 또는 다이너셋에 다른 사용자가 추가 된 레코드의 다른 사용자가 삭제 하려는 경우 [>crecordset:: Requery](../../mfc/reference/crecordset-class.md#requery) 레코드 집합을 다시 작성 해야 합니다. (다른 사용자의 삭제를 다이너셋에 표시 되는 참고 합니다.) 또한 호출 `Requery` 레코드를 보려면에 추가한 삭제 표시 되지 있지만.

> [!TIP]
>  스냅숏을 한 번에 전체 캐시 하려면, 호출 `MoveLast` 스냅숏을 연 직후입니다. 그런 다음 호출 `MoveFirst` 레코드를 사용 하 여 작업을 시작 합니다. `MoveLast` 모든 레코드를 통해 스크롤 동일 하지만 한 번에 모두 검색 하기. 그러나가 성능이 저하 되며 일부 드라이버에 대 한 필요가 없을 수도 있습니다.

업데이트가 다른 사용자에 미치는 영향에 해당 효과 비슷합니다.

##  <a name="_core_more_about_update_and_delete"></a> 업데이트 및 삭제 하는 방법에 대 한 자세한 내용

이 섹션에서는 사용 하는 데 추가 정보를 제공 `Update` 고 `Delete`입니다.

### <a name="update-success-and-failure"></a>업데이트 성공 및 실패

하는 경우 `Update` 성공 합니다 `AddNew` 또는 `Edit` 모드 종료 합니다. 시작 하는 `AddNew` 또는 `Edit` 모드를 다시 호출 합니다 `AddNew` 또는 `Edit`합니다.

하는 경우 `Update` 실패 (FALSE를 반환 하거나 예외를 throw)에 계속 남아 `AddNew` 또는 `Edit` 모드에 있는 함수에 따라 호출 하면 마지막으로 합니다. 다음 중 하나를 수행할 수 있습니다.

- 필드 데이터 멤버를 수정 하 고 시도 `Update` 다시 합니다.

- 호출 `AddNew` 필드 데이터 멤버를 Null로 다시 설정 하려면 필드 데이터 멤버의 값을 설정 하 고 호출 `Update` 다시 합니다.

- 호출 `Edit` 처음 호출 하기 전에 레코드 집합에 있던 값을 다시 로드 `AddNew` 하거나 `Edit`필드 데이터 멤버의 값을 설정 하 고, 다음 호출 `Update` 다시 합니다. 성공 하면 `Update` 호출 (이후는 제외는 `AddNew` 호출)를 필드 데이터 멤버를 새 값을 유지 합니다.

- 호출 `Move` (포함 `Move` AFX_MOVE_REFRESH, 0의 매개 변수를 사용 하 여)에 모든 변경 플러시하고 모든 종료 `AddNew` 또는 `Edit` 적용에서 모드입니다.

### <a name="update-and-delete"></a>Update 및 Delete

이 섹션에 모두 적용 됩니다 `Update` 고 `Delete`입니다.

에 `Update` 또는 `Delete` 작업을 하나의 레코드를 업데이트 해야 합니다. 해당 레코드는 레코드 집합의 필드의 데이터 값에 해당 하는 현재 레코드입니다. 다음 중 하나를 포함 하는 예외가 throw 된 일부 영향을 받는 없는 레코드 또는 둘 이상의 레코드는 영향을 이유로 경우 **RETCODE** 값:

- AFX_SQL_ERROR_NO_ROWS_AFFECTED

- AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED

이러한 예외가 throw 되는 경우에 계속 남아 있는 합니다 `AddNew` 또는 `Edit` 호출 했을 때 던 상태 `Update` 또는 `Delete`합니다. 이러한 예외는 표시 하는 가장 일반적인 시나리오는 다음과 같습니다. 여러분이 가장 발생 하기 쉬운:

- 업데이트 하거나 삭제할 레코드를 올바르게 식별에서 프레임 워크에 맞지 않는 AFX_SQL_ERROR_NO_ROWS_AFFECTED 낙관적 잠금 모드를 사용 하 고 다른 사용자가 방식으로 레코드를 수정 하는 경우.

- AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED 테이블을 업데이트 하는 경우 기본 키가 없는 또는 고유 인덱스 하 수 있는 열에에서 없는 테이블 행을 고유 하 게 식별 하는 레코드 집합입니다.

## <a name="see-also"></a>참고자료

[레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[레코드 집합: 레코드 집합 선택 (ODBC)를 기록 하는 방법](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)<br/>
[RFX(레코드 필드 교환)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[SQL](../../data/odbc/sql.md)<br/>
[예외: 데이터베이스 예외](../../mfc/exceptions-database-exceptions.md)