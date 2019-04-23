---
title: 다이너셋
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC recordsets, dynasets
- ODBC cursor library [ODBC], dynasets
- keyset-driven cursors in dynasets
- cursors [ODBC], keyset-driven cursors in dynasets
- cursor library [ODBC], dynaset availability
- recordsets [C++], dynasets
- dynasets
ms.assetid: 2867e6be-208e-4fe7-8bbe-b8697cb1045c
ms.openlocfilehash: 21c47546d14d9a121bdd0698fe96eb133dbc44a0
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59040412"
---
# <a name="dynaset"></a>다이너셋

다이너셋을 설명 하 고 설명 하는이 항목에서는 해당 [가용성](#_core_availability_of_dynasets)합니다.

> [!NOTE]
>  이 항목에서는 MFC ODBC 클래스를 포함 하 여 적용할 [CRecordset](../../mfc/reference/crecordset-class.md)합니다. 다이너셋 DAO 클래스에서에 대 한 정보를 참조 하세요 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)합니다. DAO를 사용 하 여 다이너셋 형식 레코드 집합을 열 수 있습니다.

다이너셋은 동적 속성을 사용 하 여 레코드 집합입니다. 다이너셋 모드 (일반적으로 다이너셋)의 레코드 집합 개체 수명 기간 동안 다음과 같은 방법으로 데이터 소스와 동기화가 유지 됩니다. 다중 사용자 환경에서 다른 사용자에 게 수 편집 다이너셋에 있는 레코드를 삭제 또는 다이너셋 표시 하는 테이블에 레코드를 추가 합니다. 응용 프로그램에 추가 하거나 삭제는 레코드 집합에서 레코드 다이너셋에 반영 됩니다. 다이너셋을 호출 하 여 다시 작성할 때까지 다른 사용자에 게 테이블에 추가 하는 레코드 다이너셋에 반영 되지 것입니다 해당 `Requery` 멤버 함수입니다. 다른 사용자가 레코드를 삭제 하는 경우 MFC 코드 레코드 집합에서 삭제를 건너뜁니다. 기존 레코드에 변경 된 다른 사용자의 편집 내용은 스크롤할 때 영향을 받는 레코드 즉시 다이너셋에 반영 됩니다.

마찬가지로, 다이너셋의 레코드를 편집 하는 명령은 다른 사용자가 사용 중인 다이너셋에 반영 됩니다. 추가 된 레코드는 다이너셋 다시 쿼리 하기 전에 다른 사용자에 게 다이너셋에 반영 되지 않습니다. 레코드를 삭제 하면 다른 사용자의 레코드 집합의 "deleted"로 표시 됩니다. 동일한 데이터베이스에 여러 연결이 있는 경우 (여러 `CDatabase` 개체)를 다른 사용자의 레코드 집합으로 동일한 상태의 해당 연결을 사용 하 여 관련 레코드 집합입니다.

다이너셋 가장 중요 한 경우 데이터는 항공편 예약 시스템의 예를 들어으로 동적 이어야 합니다.

> [!NOTE]
> 다이너셋을 사용 하려면 다이너셋을 지 원하는 데이터 원본에 대 한 ODBC 드라이버가 있어야 합니다 및 ODBC 커서 라이브러리가 로드 되지 않아야 합니다. 자세한 내용은 [다이너셋 가용성](#_core_availability_of_dynasets)합니다.

레코드 집합 다이너셋 임을 지정 하려면 `CRecordset::dynaset` 첫 번째 매개 변수로 `Open` 레코드 집합 개체의 멤버 함수입니다.

> [!NOTE]
> 업데이트할 수 있는 다이너셋에 대 한 ODBC 드라이버에는 어느 위치 지정된 update 문을 지원 해야 합니다 또는 `::SQLSetPos` ODBC API 함수입니다. MFC를 사용 하는 둘 다 지 원하는 경우 `::SQLSetPos` 효율성에 대 한 합니다.

##  <a name="_core_availability_of_dynasets"></a> 다이너셋 가용성

MFC 데이터베이스 클래스는 다음 요구 사항을 충족 하는 경우 다이너셋을 지원 합니다.

- ODBC 커서 라이브러리 DLL이 데이터 원본에 대 한 사용 되지 않아야 합니다.

   커서 라이브러리를 사용 하는 경우 일부 기능이 다이너셋 지원 하기 위해 필요한 기본 ODBC 드라이버의 마스크 합니다. 다이너셋을 사용 하려면 (및이 섹션의 나머지 부분에 설명 된 대로 ODBC 드라이버가 다이너셋에 필요한 기능을가지고) 하는 경우 MFC 만들면 커서 라이브러리를 로드 하지 않도록 할 수 있습니다는 `CDatabase` 개체입니다. 자세한 내용은 [ODBC](../../data/odbc/odbc-basics.md) 하며 [OpenEx](../../mfc/reference/cdatabase-class.md#openex) 또는 [열기](../../mfc/reference/cdatabase-class.md#open) 클래스의 멤버 함수 `CDatabase`합니다.

   ODBC 용어에서 다이너셋 및 스냅숏을 라고 커서입니다. 커서에는 레코드 집합에서 해당 위치는 추적에 사용 되는 메커니즘입니다.

- 데이터 원본에 대 한 ODBC 드라이버는 키 집합 커서를 지원 해야 합니다.

   키 집합 커서 시작 하 고 키 집합을 저장 하 여 테이블에서 데이터를 관리 합니다. 키를 사용자가 특정 레코드를 스크롤할 때 테이블에서 현재 데이터를 가져오기 위해 사용 됩니다. 드라이버가이 지원을 제공 하는지 여부를 결정할 호출을 `::SQLGetInfo` 사용 하 여 ODBC API 함수를 *SQL_SCROLL_OPTIONS* 매개 변수입니다.

   키 집합을 지원 하지 않는 다이너셋을 열려고 하는 경우 얻게 된 `CDBException` AFX_SQL_ERROR_DYNASET_NOT_SUPPORTED 값 반환 코드를 사용 하 여 합니다.

- 데이터 원본에 대 한 ODBC 드라이버 확장 페치 지원 해야 합니다.

   확장 페치는 뒤로 스크롤할 수 있을 뿐만 아니라 SQL 쿼리 결과 레코드에서 전달 하는 기능입니다. 드라이버는이 기능을 지원 하는지 여부를 결정할 호출을 `::SQLGetFunctions` 사용 하 여 ODBC API 함수를 *SQL_API_SQLEXTENDEDFETCH* 매개 변수입니다.

업데이트할 수 있는 다이너셋 (또는 해당 문제에 대 한 스냅숏)를 하려는 경우 ODBC 드라이버를 지원 해야 합니다 중 하나는 `::SQLSetPos` ODBC API 함수 또는 위치 지정된 업데이트 합니다. `::SQLSetPos` SQL 문을 보내기 하지 않고 데이터 소스를 업데이트 하는 MFC 기능을 사용 합니다. 이 지원을 사용할 수 있는 경우 MFC SQL을 사용 하 여 업데이트를 수행 하는 것 보다 우선적으로 사용 됩니다. 드라이버 지원 하는지 여부를 결정할 `::SQLSetPos`, 호출 `::SQLGetInfo` 사용 하 여 합니다 *SQL_POS_OPERATIONS* 매개 변수입니다.

SQL 구문을 사용 하는 위치 지정된 업데이트 (양식의 **WHERE CURRENT OF** \<cursorname >) 데이터 원본에 테이블의 특정 행을 식별 하 합니다. 드라이버 위치 지정된 업데이트를 지원 하는지 여부를 결정할 호출 `::SQLGetInfo` 사용 하 여 합니다 *SQL_POSITIONED_STATEMENTS* 매개 변수입니다.

일반적으로 MFC 다이너셋 (그러나 정방향 전용 레코드 집합)에 수준 2 API 규칙을 사용 하 여 ODBC 드라이버가 필요합니다. 데이터 원본에 대 한 드라이버 수준 1 API 집합을 따르는 경우 모두 업데이트 가능 하 고 읽기 전용 스냅숏 및 정방향 전용 레코드 집합 하지만 하지 다이너셋 여전히 사용할 수 있습니다. 하지만 수준 1 드라이버 확장 페치를 지 원하는 경우 다이너셋 및 키 집합 커서를 지원할 수 있습니다. ODBC 적합성 수준에 대 한 자세한 내용은 참조 하세요. [ODBC](../../data/odbc/odbc-basics.md)합니다.

> [!NOTE]
> 스냅숏과 다이너셋 둘 다 사용 하려는 경우 두 가지에 기반 해야 `CDatabase` 개체 (두 개의 서로 다른 연결).

ODBC 커서 라이브러리에 의해 유지 관리 하는 중간 저장소를 사용 하는 스냅숏 달리 다이너셋 스크롤 하는 즉시 직접 데이터 원본에서에서 레코드를 가져옵니다. 이렇게 하면 원래 데이터 원본과 동기화 다이너셋에서 선택한 레코드.

시각적 개체의이 버전에 포함 된 ODBC 드라이버의 목록은 C++ 추가 드라이버를 얻는 방법에 대 한 자세한 내용은 참조 [ODBC 드라이버 목록](../../data/odbc/odbc-driver-list.md)합니다.

## <a name="see-also"></a>참고자료

[ODBC(Open Database Connectivity)](../../data/odbc/open-database-connectivity-odbc.md)