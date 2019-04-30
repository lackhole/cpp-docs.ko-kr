---
title: '레코드 집합: 레코드 잠금 (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- locks [C++], recordsets
- optimistic locking
- pessimistic locking in ODBC
- recordsets [C++], locking records
- optimistic locking, ODBC
- ODBC recordsets [C++], locking records
- data [C++], locking
ms.assetid: 8fe8fcfe-b55a-41a8-9136-94a7cd1e4806
ms.openlocfilehash: 1265899e7060527d7e586689eb4c3148eebc4080
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397798"
---
# <a name="recordset-locking-records-odbc"></a>레코드 집합: 레코드 잠금 (ODBC)

이 항목에서는 MFC ODBC 클래스에 적용됩니다.

이 항목에 설명 합니다.

- [사용 가능한 레코드 잠금 종류](#_core_record.2d.locking_modes)합니다.

- [레코드 집합에서 레코드를 업데이트 하는 동안 잠금 방법](#_core_locking_records_in_your_recordset)합니다.

레코드 집합을 사용 하 여 데이터 원본에서 레코드를 업데이트 하려고 하는 경우 동시에 다른 사용자가 레코드를 업데이트할 수 있도록 응용 프로그램 레코드를 잠글 수 있습니다. 시스템에서 두 명의 사용자가 레코드를 동시에 업데이트할 수 없습니다를 보장할 수 없는 경우에 동시에 두 사용자가 업데이트할 레코드의 상태가 정의 되지 않습니다.

> [!NOTE]
>  이 항목에서 파생 된 개체에 적용 됩니다 `CRecordset` 의 대량 행 페치 구현 되지 않았습니다. 대량 행 페치를 구현한 경우이 정보 중 일부는 적용 되지 않습니다. 예를 들어, 호출할 수 없습니다는 `Edit` 및 `Update` 멤버 함수입니다. 대량 행 페치에 대 한 자세한 내용은 참조 하세요. [레코드 집합: (ODBC) 대량 레코드 페치](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)합니다.

##  <a name="_core_record.2d.locking_modes"></a> 레코드 잠금 모드

두 데이터베이스 클래스를 제공 [레코드 잠금 모드](../../mfc/reference/crecordset-class.md#setlockingmode):

- 낙관적 잠금 (기본값)

- 비관적 잠금

레코드를 업데이트 하는 작업은 세 단계로 발생 합니다.

1. 호출 하 여 작업을 시작 합니다 [편집](../../mfc/reference/crecordset-class.md#edit) 멤버 함수입니다.

1. 현재 레코드의 적절 한 필드를 변경 합니다.

1. 작업-일반적으로 업데이트를 커밋합니다-호출 하 여 합니다 [업데이트](../../mfc/reference/crecordset-class.md#update) 멤버 함수입니다.

중에 데이터 원본에서 레코드를 잠급니다 낙관적 잠금는 `Update` 호출 합니다. 다중 사용자 환경에서 낙관적 잠금을 사용 하는 경우 응용 프로그램을 처리 하는 `Update` 실패 조건입니다. 호출 하면 즉시 레코드 잠금 비관적 잠금을 `Edit` 해제 하지 않습니다 때까지 호출 하 고 `Update` (오류를 통해 표시 되는 `CDBException` 값이 반환한 FALSE가 아니라 해당 하는 메커니즘을 `Update`). 동일한 레코드에 대 한 동시 액세스를 응용 프로그램의 완료 될 때까지 잠시 기다려야 할 수 있으므로에서는 다른 사용자에 대 한 성능 저하를 비관적 잠금 `Update` 프로세스입니다.

##  <a name="_core_locking_records_in_your_recordset"></a> 레코드 집합의 레코드 잠금

레코드 집합 개체를 변경 하려는 경우 [잠금 모드](#_core_record.2d.locking_modes) 기본값에서 변경 해야 호출 하기 전에 모드 `Edit`합니다.

#### <a name="to-change-the-current-locking-mode-for-your-recordset"></a>레코드 집합에 대 한 현재 잠금 모드를 변경 하려면

1. 호출 된 [SetLockingMode](../../mfc/reference/crecordset-class.md#setlockingmode) 멤버 함수를 지정 `CRecordset::pessimistic` 또는 `CRecordset::optimistic`합니다.

새 잠금 모드로 다시 변경 되거나 레코드 집합이 닫힐 때까지 적용 됩니다.

> [!NOTE]
>  비교적 적은 ODBC 드라이버는 현재 비관적 잠금을 지원 합니다.

## <a name="see-also"></a>참고자료

[레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[레코드 집합 조인 수행(ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)<br/>
[레코드 집합 레코드 추가, 업데이트 및 삭제(ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)