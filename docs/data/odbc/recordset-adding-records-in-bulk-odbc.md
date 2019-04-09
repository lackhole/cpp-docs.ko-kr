---
title: '레코드 집합: (ODBC) 대량 레코드 추가'
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC recordsets, adding records
- recordsets, adding records
- bulk record additions to recordsets
ms.assetid: 4685f656-14b9-4f10-a1c5-147b2b89a0b4
ms.openlocfilehash: a2c3eab8bb4c0e8db76fceb5a2dafd16a4a07079
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59038611"
---
# <a name="recordset-adding-records-in-bulk-odbc"></a>레코드 집합: (ODBC) 대량 레코드 추가

이 항목에서는 MFC ODBC 클래스에 적용됩니다.

MFC [CRecordset](../../mfc/reference/crecordset-class.md) 클래스에는 테이블에 대량으로 새 레코드를 추가할 때 효율성을 개선 하는 최적화 합니다.

> [!NOTE]
> 이 항목에서 파생 된 개체에 적용 됩니다 `CRecordset` 의 대량 행 페치 구현 되지 않았습니다. 대량 행 페치를 사용 하는 경우 참조 [레코드 집합: (ODBC) 대량 레코드 페치](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)합니다.

에 대 한 새 옵션을 *dwOptions* 매개 변수를를 [crecordset:: Open](../../mfc/reference/crecordset-class.md#open) 멤버 함수 `optimizeBulkAdd`, 호출없이연속적으로여러레코드를추가할때성능을향상시킵니다`Requery` 또는 `Close`합니다. 첫 번째 더티 필드만 `Update` 호출 다음에 대 한 커밋되지 않은 것으로 표시 됩니다 `AddNew` / `Update` 호출 합니다.

데이터베이스 클래스를 활용 하기 위해 사용 중인 경우는 `::SQLSetPos` 편집을 추가 하는 것에 대 한 ODBC API 함수 및 레코드를 삭제 하는 중에이 최적화가 필요 없습니다.

ODBC 커서 라이브러리가 로드 또는 ODBC 드라이버는 추가 지원 하지 않는 경우 편집 및 삭제를 통해 `::SQLSetPos`,이 최적화는 bulk 개선 해야 성능을 추가 합니다. 이 최적화를 설정 합니다 *dwOptions* 에 매개 변수는 `Open` 다음과 레코드 집합에 대 한 호출:

```
appendOnly | optimizeBulkAdd
```

## <a name="see-also"></a>참고자료

[레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[레코드 집합: 추가, 업데이트 및 삭제할 레코드 (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)<br/>
[레코드 집합: 레코드 잠금 (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)