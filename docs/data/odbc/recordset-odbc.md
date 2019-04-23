---
title: 레코드 집합(ODBC)
ms.date: 11/04/2016
helpviewer_keywords:
- recordsets, snapshots
- recordsets, creating
- dynamic recordsets
- forward-only recordsets
- recordsets, dynasets
- ODBC recordsets, CRecordset objects
- ODBC recordsets
- recordsets, about recordsets
- snapshots, ODBC recordsets
- dynasets
ms.assetid: 333337c5-575e-4d26-b5f6-47166ad7874d
ms.openlocfilehash: b201e152d83d3812253aa4803eebe715d726219d
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59034497"
---
# <a name="recordset-odbc"></a>레코드 집합(ODBC)

이 항목에서는 MFC ODBC 클래스에 적용됩니다.

A [CRecordset](../../mfc/reference/crecordset-class.md) 개체 데이터 원본에서 선택한 레코드 집합을 나타냅니다. 레코드에서 될 수 있습니다.

- 테이블입니다.

- 쿼리입니다.

- 하나 이상의 테이블에 액세스 하는 저장된 프로시저입니다.

테이블을 기반으로 하는 레코드 집합의 예로 Customer 테이블에 액세스 하는 "all customers". 쿼리의 예로 "Joe Smith에 대 한 모든 청구서." (미리 정의 된 쿼리를이 라고도 함) 저장된 프로시저를 기반으로 레코드 집합의 예로 "연체 계정의 모든" 백 엔드 데이터베이스의 저장된 프로시저를 호출 합니다. 레코드 집합은 다른 데이터 원본의 표 하지는 동일한 데이터 원본의 테이블 두 개 이상 참여할 수 있습니다.

> [!NOTE]
>  마법사를 사용 하 여 레코드 집합 클래스를 파생 하는 방법에 대 한 내용은 [MFC ODBC 소비자 추가](../../mfc/reference/adding-an-mfc-odbc-consumer.md) 하 고 [MFC 응용 프로그램 마법사, 데이터베이스 지원](../../mfc/reference/database-support-mfc-application-wizard.md)합니다.

> [!NOTE]
>  일부 ODBC 드라이버는 데이터베이스 뷰를 지원합니다. 이러한 관점에서 뷰는 SQL을 사용 하 여 만든 원래 쿼리 `CREATE VIEW` 문입니다. 마법사 현재 뷰를 지원 하지 않습니다 하지만이 지원을 직접 코딩할 수 있습니다.

##  <a name="_core_recordset_capabilities"></a> 레코드 집합 기능

모든 레코드 집합 개체는 다음과 같은 기능을 공유:

- 데이터 원본 읽기 전용이 아닌지, 레코드 집합 수를 지정할 수 있습니다 [업데이트할 수 있는](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)를 [추가](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md), 또는 읽기 전용입니다. 비관적 또는 낙관적 레코드를 업데이트할 수 있는 경우 선택할 수 있습니다 [잠금](../../data/odbc/recordset-locking-records-odbc.md) 메서드를 적절 한 잠금 지원을 제공 하는 드라이버를 제공 합니다. 데이터 원본 읽기 전용 이면 읽기 전용 레코드 집합이 됩니다.

- 멤버 함수를 호출할 수 있습니다 [스크롤](../../data/odbc/recordset-scrolling-odbc.md) 선택 된 레코드입니다.

- 할 수 있습니다 [필터](../../data/odbc/recordset-filtering-records-odbc.md) 레코드에서 사용할 수 있는 선택 된 레코드를 제한 합니다.

- 할 수 있습니다 [정렬](../../data/odbc/recordset-sorting-records-odbc.md) 하나 이상의 열을 기준으로 오름차순 또는 내림차순으로 레코드입니다.

- 할 수 있습니다 [매개 변수화](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) 하 여 런타임에 선택 될 레코드 집합입니다.

##  <a name="_core_snapshots_and_dynasets"></a> 스냅숏 및 다이너셋

레코드 집합의 두 가지 보안 주체 유형을 가지: [스냅숏을](../../data/odbc/snapshot.md) 하 고 [다이너셋](../../data/odbc/dynaset.md)합니다. 클래스에서 지원 되는 둘 다 `CRecordset`합니다. 모든 레코드 집합의 공통 된 특성을 공유 하지만 자체 특수 한 방식으로 공통 기능을 확장 하기도 합니다. 스냅숏은 데이터의 정적 뷰를 제공 하며 보고서 및 특정 시간 데이터 보기를 필요로 하는 경우에 유용 합니다. 다이너셋 쿼리하거나 레코드 집합을 새로 고치지 않고도 레코드 집합에서 표시 하도록 다른 사용자가 수행한 업데이트 하려는 경우 유용 합니다. 업데이트 가능 또는 읽기 전용 스냅숏 및 다이너셋 수 있습니다. 추가 된 레코드를 반영 하거나 다른 사용자가 삭제 호출 [>crecordset:: Requery](../../mfc/reference/crecordset-class.md#requery)합니다.

`CRecordset` 에서는 두 가지 다른 유형의 레코드 집합: 동적 레코드 집합 및 정방향 전용 레코드 집합입니다. 동적 레코드 집합이 다이너셋;에 대해 비슷합니다. 그러나 동적 레코드 집합에서 모든 레코드를 추가 하거나 호출 하지 않고 삭제를 반영 하는 `CRecordset::Requery`합니다. 이러한 이유로 동적 레코드 집합은 일반적으로 DBMS의 처리 시간에 따른 비용이 많이 드는 및 대부분의 ODBC 드라이버를 지원 하지 않습니다. 반면, 앞 으로만 이동 가능한 레코드 집합 업데이트 또는 뒤로 스크롤할 필요 하지 않은 레코드 집합에 대 한 데이터 액세스의 가장 효율적인 방법을 제공 합니다. 예를 들어, 데이터를에서 마이그레이션하도록 하나의 데이터 원본 간에 해야 하는 앞으로 데이터를 이동 하는 전달 전용 레코드 집합을 사용할 수 있습니다. 앞 으로만 이동 가능한 레코드 집합을 사용 하려면 다음을 수행 해야 합니다.

- 옵션을 전달 `CRecordset::forwardOnly` 으로 *nOpenType* 의 매개 변수를 [오픈](../../mfc/reference/crecordset-class.md#open) 멤버 함수입니다.

- 지정할 `CRecordset::readOnly` 에 *dwOptions* 의 매개 변수 `Open`합니다.

    > [!NOTE]
    >  다이너셋 지원에 대 한 ODBC 드라이버 요구 사항에 대 한 자세한 내용은 [ODBC](../../data/odbc/odbc-basics.md)합니다. 시각적 개체의이 버전에 포함 된 ODBC 드라이버의 목록은 C++ 추가 드라이버를 얻는 방법에 대 한 자세한 내용은 참조 [ODBC 드라이버 목록](../../data/odbc/odbc-driver-list.md)합니다.

##  <a name="_core_your_recordsets"></a> 레코드 집합

모든 개별 테이블, 뷰 또는 저장된 프로시저에 액세스 하려면를 실행 하는 것에 대 한 일반적으로에서 파생 된 클래스를 정의 `CRecordset`합니다. (예외는 하나의 레코드 집합 두 개 이상의 테이블에서 열을 나타내는, 데이터베이스 조인.) 레코드 집합 클래스를 파생 하는 경우 설정한 레코드 필드 교환 (RFX) 메커니즘 또는 대량 레코드 필드 교환 (대량 RFX) 메커니즘에는 대화 상자 데이터 교환 (DDX) 메커니즘에 유사한 합니다. RFX 및 대량 RFX 간소화; 레코드 집합에 데이터 원본에서 데이터를 전송 RFX는 또한 데이터 원본에 레코드 집합에서 데이터를 전송합니다. 자세한 내용은 [Exchange RFX (레코드 필드)](../../data/odbc/record-field-exchange-rfx.md) 고 [레코드 집합: (ODBC) 대량 레코드 페치](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)합니다.

레코드 집합 개체는 선택한 모든 레코드에 액세스할을 수 있습니다. 사용 하 여 여러 선택한 레코드를 스크롤할 `CRecordset` 와 같은 멤버 함수 `MoveNext` 고 `MovePrev`입니다. 레코드 집합 개체는 동시에 선택한 레코드를 현재 레코드 중 하나만 나타냅니다. 레코드 집합 데이터베이스 쿼리에서 발생 하는 레코드 또는 테이블의 열에 해당 하는 클래스 멤버 변수를 선언 하 여 현재 레코드의 필드를 검사할 수 있습니다. 레코드 집합 데이터 멤버에 대 한 정보를 참조 하세요. [레코드 집합: 아키텍처 (ODBC)](../../data/odbc/recordset-architecture-odbc.md)합니다.

다음 항목에서는 레코드 집합 개체를 사용 하 여 세부 정보를 설명 합니다. 항목 기능 범주 및 순차적 읽기를 허용 하려면 자연 스러운 찾아보기에 나열 됩니다.

### <a name="topics-about-the-mechanics-of-opening-reading-and-closing-recordsets"></a>열기, 읽기 및 레코드 집합을 닫기에 대 한 메커니즘에 대 한 항목

- [레코드 집합: 아키텍처 (ODBC)](../../data/odbc/recordset-architecture-odbc.md)

- [레코드 집합: 테이블 (ODBC)에 대 한 클래스 선언](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)

- [레코드 집합: 만들 레코드 집합 및 닫기 (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)

- [레코드 집합: 스크롤 (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)

- [레코드 집합: 책갈피와 절대 위치 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)

- [레코드 집합: 레코드 필터링 (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)

- [레코드 집합: 레코드 정렬 (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md)

- [레코드 집합: 레코드 집합 (ODBC)를 매개 변수화](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)

### <a name="topics-about-the-mechanics-of-modifying-recordsets"></a>레코드 집합 수정에 대 한 메커니즘에 대 한 항목

- [레코드 집합: 추가, 업데이트 및 삭제할 레코드 (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)

- [레코드 집합: 레코드 잠금 (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)

- [레코드 집합: (ODBC) 레코드 집합 다시 쿼리](../../data/odbc/recordset-requerying-a-recordset-odbc.md)

### <a name="topics-about-somewhat-more-advanced-techniques"></a>고급 기술 어느 정도 대 한 항목

- [레코드 집합: 조인 수행 (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)

- [레코드 집합: 미리 정의 된 쿼리 (ODBC)에 대 한 클래스 선언](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)

- [레코드 집합: 동적으로 데이터 열 바인딩 (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)

- [레코드 집합: (ODBC) 대량 레코드 페치](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)

- [레코드 집합: 대형 데이터 항목 (ODBC)를 사용 하 여 작업](../../data/odbc/recordset-working-with-large-data-items-odbc.md)

- [레코드 집합: 합계 및 다른 집계 결과 (ODBC) 구하기](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)

### <a name="topics-about-how-recordsets-work"></a>레코드 집합의 작동 방법에 대 한 항목

- [레코드 집합: 레코드 집합 선택 (ODBC)를 기록 하는 방법](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)

- [레코드 집합: 레코드 집합 업데이트 (ODBC)를 기록 하는 방법](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)

## <a name="see-also"></a>참고자료

[ODBC(Open Database Connectivity)](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[MFC ODBC 소비](../../mfc/reference/adding-an-mfc-odbc-consumer.md)<br/>
[트랜잭션(ODBC)](../../data/odbc/transaction-odbc.md)