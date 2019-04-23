---
title: '레코드 집합: (ODBC) 레코드 집합 다시 쿼리'
ms.date: 11/04/2016
helpviewer_keywords:
- recordsets, requerying
- requerying recordsets
- Requery method
- ODBC recordsets, requerying
- refreshing recordsets
ms.assetid: 4ebc3b5b-5b91-4f51-a967-245223c6b8e1
ms.openlocfilehash: 7edc1c04da617f96165b25a47ce169b266ae0003
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59024597"
---
# <a name="recordset-requerying-a-recordset-odbc"></a>레코드 집합: (ODBC) 레코드 집합 다시 쿼리

이 항목에서는 MFC ODBC 클래스에 적용됩니다.

이 항목에서는 레코드 집합 개체를 사용 하 여 다시 쿼리 하는 방법을 설명 (즉, 새로 고침)를 사용 하 여 작업을 수행 하는 시기 및 데이터베이스에서 자체를 [Requery](../../mfc/reference/crecordset-class.md#requery) 멤버 함수입니다.

레코드 집합 다시 쿼리 하는 주 원인은 다음과 같습니다.

- 최신 또는 다른 사용자가 추가 된 레코드 및 다른 사용자 (삭제 하면 해당 이미에 반영 됩니다 레코드 집합)가 삭제 된 레코드에 대해 레코드 집합을 제공 합니다.

- 매개 변수 값 변경에 따라 레코드 집합을 새로 고칩니다.

##  <a name="_core_bringing_the_recordset_up_to_date"></a> 날짜를 레코드 집합 가져오기

자주 해야을 레코드 집합 개체를 최신 상태로 합니다. 다중 사용자 데이터베이스 환경에서 다른 사용자가 변경할 수는 데이터 레코드 집합의 수명 동안. 레코드 집합에 다른 사용자가 변경한 내용을 반영 하는 경우 및 다른 사용자의 변경 내용을 반영 하는 경우에 대 한 자세한 내용은 참조 하세요. [레코드 집합: 레코드 집합 업데이트 (ODBC)를 기록 하는 방법](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) 하 고 [다이너셋](../../data/odbc/dynaset.md)합니다.

##  <a name="_core_requerying_based_on_new_parameters"></a> 새 매개 변수를 기반으로 다시 쿼리

자주-만큼 중요 한 역할-이용 [Requery](../../mfc/reference/crecordset-class.md#requery) 매개 변수 값 변경에 따라 레코드의 새 집합을 선택 하는 것입니다.

> [!TIP]
>  쿼리 속도가 호출 하는 경우 더 빠른 경우가 훨씬 `Requery` 호출 하는 매개 변수 값을 변경 하 여 `Open` 다시 합니다.

##  <a name="_core_requerying_dynasets_vs.._snapshots"></a> 다이너셋 vs를 다시 쿼리 합니다. 스냅숏

다이너셋 동적 최신 데이터를 사용 하 여 레코드 집합을 제공 되며, 때문에 다른 사용자의 추가 반영 하도록 하려는 경우에 종종 다이너셋 requery 하려고 합니다. 스냅숏, 반면에 있으므로 아주 유용 보고서를 준비 하 고 합계를 계산 하는 등의 작업을 수행할 때 안전 하 게 정적 해당 내용에 사용할 수 있습니다. 여전히도 스냅숏을 다시 쿼리 하려는 경우가 있습니다. 다중 사용자 환경에서 다른 사용자 데이터베이스를 변경 하는 대로 스냅숏 데이터 데이터 원본과 동기화를 손실 될 수 있습니다.

#### <a name="to-requery-a-recordset-object"></a>레코드 집합 개체를 다시 쿼리

1. 호출 된 [Requery](../../mfc/reference/crecordset-class.md#requery) 개체의 멤버 함수입니다.

또는 닫을 수 있으며 원래 레코드 집합을 다시 열 수 있습니다. 두 경우 모두 새 레코드 집합의 데이터 원본 현재 상태를 나타냅니다.

예를 들어 참조 [레코드 뷰: 두 번째 레코드 집합에서 목록 상자 채우기](../../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md)합니다.

> [!TIP]
>  최적화 하기 위해 `Requery` 성능 레코드 집합의 변경 되지 않도록 [필터](../../data/odbc/recordset-filtering-records-odbc.md) 하거나 [정렬](../../data/odbc/recordset-sorting-records-odbc.md)합니다. 호출 하기 전에 매개 변수 값만 변경 `Requery`합니다.

경우는 `Requery` 실패 하면 호출 응용 프로그램이 정상적으로 종료 해야이 고, 그렇지 않으면 호출을 다시 시도할 수 있습니다. 에 대 한 호출 `Requery` 또는 `Open` 다양 한 이유로 실패할 수 있습니다. 아마도 네트워크 오류가 발생합니다. 호출 하는 동안 기존 데이터가 해제 되 면 새 데이터를 가져올 전에 다른 사용자 수 작동 하지 않습니다. 단독; 또는 또는 레코드 집합에 종속 된 테이블을 삭제할 수 없습니다.

## <a name="see-also"></a>참고자료

[레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[레코드 집합: 동적으로 데이터 열 바인딩 (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)<br/>
[레코드 집합: 만들 레코드 집합 및 닫기 (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)