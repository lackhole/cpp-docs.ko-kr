---
title: '레코드 집합: AddNew를 편집 하 고 작업 (ODBC)를 삭제 하는 방법'
ms.date: 11/04/2016
helpviewer_keywords:
- records [C++], updating
- record editing [C++], in recordsets
- recordsets [C++], adding records
- records [C++], adding
- ODBC recordsets [C++], adding records
- recordsets [C++], editing records
- recordsets [C++], updating
- AddNew method
- ODBC recordsets [C++], deleting records
- records [C++], deleting in recordsets
- data in recordsets [C++]
- recordsets [C++], deleting records
- ODBC recordsets [C++], editing records
- records [C++], editing
ms.assetid: cab43d43-235a-4bed-ac05-67d10e94f34e
ms.openlocfilehash: e5fc6ad2a1fe00367cd8a0b1c53ac914b95018ab
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59033211"
---
# <a name="recordset-how-addnew-edit-and-delete-work-odbc"></a>레코드 집합: AddNew를 편집 하 고 작업 (ODBC)를 삭제 하는 방법

이 항목에서는 MFC ODBC 클래스에 적용됩니다.

이 항목에 설명 하는 방법을 `AddNew`, `Edit`, 및 `Delete` 클래스의 멤버 함수 `CRecordset` 작동 합니다. 다루는 항목은 다음과 같습니다.

- [레코드 추가 방법](#_core_adding_a_record)

- [추가 된 레코드 표시](#_core_visibility_of_added_records)

- [레코드 편집 방법](#_core_editing_an_existing_record)

- [레코드 삭제 방법](#_core_deleting_a_record)

> [!NOTE]
>  이 항목에서 파생 된 개체에 적용 됩니다 `CRecordset` 의 대량 행 페치 구현 되지 않았습니다. 대량 행 페치를 사용 하는 경우 참조 [레코드 집합: (ODBC) 대량 레코드 페치](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)합니다.

보완을 읽을 하려는 [레코드 필드 교환: RFX 작동 방식](../../data/odbc/record-field-exchange-how-rfx-works.md)는 RFX 업데이트 작업의 해당 역할에 설명 합니다.

##  <a name="_core_adding_a_record"></a> 레코드 추가

레코드 집합의 호출에서는 레코드 집합에 새 레코드를 추가 [AddNew](../../mfc/reference/crecordset-class.md#addnew) 멤버 함수를 호출 하 여 새 레코드의 필드 데이터 멤버의 값을 설정 합니다 [업데이트](../../mfc/reference/crecordset-class.md#update) 쓸 멤버 함수 데이터 원본에 레코드입니다.

호출에 대 한 전제 조건으로 `AddNew`, 레코드 집합 해야 열지 읽기 전용으로 합니다. 합니다 `CanUpdate` 및 `CanAppend` 멤버 함수를 사용 하 여 이러한 조건을 확인할 수 있습니다.

호출 하는 경우 `AddNew`:

- 레코드 편집 버퍼에 저장 됩니다 작업이 취소 되는 경우 해당 콘텐츠를 복원할 수 있습니다.

- 필드 데이터 멤버에는 나중에 변경 내용을 찾을 수 있도록 플래그가 지정 됩니다. 필드 데이터 멤버에도 표시 됩니다 (변경 되지 않음) 정리를 Null로 설정 합니다.

호출한 후 `AddNew`편집 버퍼를 나타내는 새, 빈 레코드를 값을 채울 수 있습니다. 이렇게 하려면 수동으로 설정한 값을 할당 하 여 합니다. 필드에 대 한 실제 데이터 값을 지정 하는 대신 호출할 수 있습니다 `SetFieldNull` Null 값을 지정 합니다.

변경 내용을 커밋하려면 호출 `Update`합니다. 호출 하는 경우 `Update` 새 레코드:

- ODBC 드라이버에서 지 원하는 경우는 `::SQLSetPos` MFC ODBC API 함수는 함수를 사용 하 여 데이터 원본에서 레코드를 추가 합니다. 사용 하 여 `::SQLSetPos`, MFC 레코드가 추가 된다 니 보다 효율적으로 생성 하 고 SQL 문을 처리 하는 없기 때문에 있습니다.

- 경우 `::SQLSetPos` 일 수 없습니다 사용 MFC는 다음을 수행 합니다.

   1. 내용이 검색 되 면 `Update` 없으며 0을 반환 합니다.

   1. 변경 내용이 없으면 `Update` SQL 구문 **삽입** 문입니다. 모든 더티 필드 데이터 멤버를 나타내는 열이 나열 되는 **삽입** 문입니다. 열을 포함 하도록 호출 합니다 [SetFieldDirty](../../mfc/reference/crecordset-class.md#setfielddirty) 멤버 함수:

        ```cpp
        SetFieldDirty( &m_dataMember, TRUE );
        ```

   1. `Update` 새 레코드 커밋을-합니다 **삽입** 문이 실행 되 고 트랜잭션이 진행에서 되지 않는 레코드를 테이블에 데이터 원본 (및 레코드 집합에 없는 경우 스냅숏을) 커밋.

   1. 저장된 된 레코드 편집 버퍼에 복원 됩니다. 이전의 현재 레코드를 `AddNew` 호출 없이 다시 현재는 합니다 **삽입** 문이 성공적으로 실행 되었습니다.

   > [!TIP]
   > 새 레코드의 완벽 한 제어를 위해 다음 방법을 사용 합니다: 값이 되며 다음 호출 하 여 Null 남아 있는 모든 필드를 명시적으로 설정 하는 모든 필드의 값을 설정 `SetFieldNull` 필드 및 매개 변수에 대 한 포인터를 사용 하 여 TRUE (기본값). 필드를 데이터 원본에 호출 되지 기록 되도록 하려는 경우 `SetFieldDirty` 필드 및 매개 변수에 FALSE에 대 한 포인터를 사용 하 여 고 필드의 값을 수정 하지 않습니다. 필드는 Null 일 수 있는지 여부를 결정할 호출 `IsFieldNullable`합니다.

   > [!TIP]
   > 레코드 집합 데이터 멤버 값을 변경 하는 경우를 검색 하려면 MFC 레코드 집합에 저장할 수 있는 각 데이터 형식에 적합 한 PSEUDO_NULL 값을 사용 합니다. PSEUDO_NULL 값 필드를 명시적으로 설정 해야 하 고 필드는 Null 표시할 이미 발생을 호출 해야 `SetFieldNull`, 두 번째 매개 변수에서 첫 번째 매개 변수를 FALSE 필드의 주소를 전달 합니다.

##  <a name="_core_visibility_of_added_records"></a> 추가 된 레코드 표시

경우는 추가 된 레코드를 레코드 집합 표시 추가 된 레코드 있고 경우에 따라 두 가지 작업에 따라 표시 되지 않습니다.

- 드라이버를 수 있습니다.

- 새로운 프레임 워크를 활용할 수 있습니다.

ODBC 드라이버에서 지 원하는 경우는 `::SQLSetPos` MFC ODBC API 함수는 함수를 사용 하 여 레코드를 추가 합니다. 사용 하 여 `::SQLSetPos`, 추가 된 레코드를 업데이트할 수 있는 모든 MFC 레코드 집합으로 표시 합니다. 함수에 대 한 지원은 추가 레코드 표시 되며 호출 해야 `Requery` 표시 합니다. 사용 하 여 `::SQLSetPos` 더 효율적 이기도 합니다.

##  <a name="_core_editing_an_existing_record"></a> 기존 레코드를 편집합니다.

레코드 집합에서 기존 레코드를 편집 하려면 레코드 집합의 레코드를 하려면 스크롤하고 [편집할](../../mfc/reference/crecordset-class.md#edit) 멤버 함수를 호출 하 여 새 레코드의 필드 데이터 멤버의 값을 설정 합니다 [업데이트](../../mfc/reference/crecordset-class.md#update)멤버 함수를 데이터 원본에 변경 된 레코드를 작성 합니다.

호출에 대 한 전제 조건으로 `Edit`를 업데이트할 수 있는 한 레코드를 레코드 집합 이어야 합니다. 합니다 `CanUpdate` 및 `IsDeleted` 멤버 함수를 사용 하 여 이러한 조건을 확인할 수 있습니다. 또한 현재 레코드가 이미 삭제 되지 않았고 레코드 집합의 레코드 여야 합니다 (둘 다 `IsBOF` 고 `IsEOF` 0을 반환).

호출 하는 경우 `Edit`, 레코드 편집 버퍼 (현재 레코드)에 저장 됩니다. 저장된 된 레코드의 값 필드에 변경 되었는지 여부를 검색 하려면 나중에 사용 됩니다.

호출한 후 `Edit`, 편집 버퍼는 여전히 현재 레코드 표시 되지만 필드 데이터 멤버의 변경 내용을 받아들일 준비가 되었습니다. 레코드를 변경 하려면 수동으로 편집 하려면 필드 데이터 멤버의 값을 설정 합니다. 필드에 대 한 실제 데이터 값을 지정 하는 대신 호출할 수 있습니다 `SetFieldNull` Null 값을 지정 합니다. 변경 내용을 커밋하려면 호출 `Update`합니다.

> [!TIP]
> 활용 `AddNew` 나 `Edit` 모드를 호출 `Move` 매개 변수를 사용 하 여 *AFX_MOVE_REFRESH*합니다.

호출에 대 한 전제 조건으로 `Update`, 레코드 집합은 비워둘 수 없습니다 및 현재 레코드 삭제 되지 않아야 합니다. `IsBOF`를 `IsEOF`, 및 `IsDeleted` 모든 0을 반환 합니다.

호출 하는 경우 `Update` 편집할 레코드:

- ODBC 드라이버에서 지 원하는 경우는 `::SQLSetPos` MFC ODBC API 함수는 함수를 사용 하 여 데이터 원본에서 레코드를 업데이트 합니다. 사용 하 여 `::SQLSetPos`, 드라이버 서버에 레코드를 업데이트 하 여 두 개의 서로 다른 경우 서버에서 해당 레코드를 사용 하 여 편집 버퍼를 비교 합니다. 사용 하 여 `::SQLSetPos`, MFC 수 업데이트 레코드를 보다 효율적으로 생성 하 고 SQL 문을 처리 하는 없기 때문에 있습니다.

   \- 또는 -

- 경우 `::SQLSetPos` 일 수 없습니다 사용 MFC는 다음을 수행 합니다.

   1. 변경 없이 되었으면 `Update` 없으며 0을 반환 합니다.

   1. 변경 내용이 없으면 `Update` SQL 구문 **업데이트** 문입니다. 에 나열 된 열을 **업데이트** 문을 변경 된 필드 데이터 멤버를 기반으로 합니다.

   1. `Update` 변경 내용을 커밋합니다-실행 합니다 **업데이트** 문-데이터 원본에는 레코드를 변경 하며 트랜잭션이 커밋되지는 않음 경우 진행 중인 (참조 [트랜잭션: 수행 된 트랜잭션 레코드 집합 (ODBC)에서](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md) 트랜잭션이 업데이트에 미치는 영향에 대 한 정보에 대 한). ODBC 변경 레코드의 복사본을 유지 합니다.

   1. 에 대 한 프로세스와는 달리 `AddNew`, `Edit` 프로세스는 저장된 된 레코드를 복원 하지 않습니다. 편집할된 레코드를 현재 레코드로 위치에 남아 있습니다.

   > [!CAUTION]
   > 호출 하 여 레코드 집합을 업데이트 하기 전에 `Update`, 레코드 집합 테이블 (또는 모든 행을 고유 하 게 식별할 수 있는 열 또는 테이블에 있는 고유 인덱스의 열)의 기본 키를 구성 하는 모든 열에 주의 합니다. 경우에 따라 프레임 워크 업데이트 테이블의 레코드를 식별 하 레코드 집합에서 선택한 열만을 사용할 수 있습니다. 필요한 모든 열이 없는 테이블의 여러 레코드가 업데이트 될 수 있습니다. 호출할 때 프레임 워크에서 예외를 throw 하는 예제의 경우 `Update`합니다.

   > [!TIP]
   > 호출 하는 경우 `AddNew` 나 `Edit` 호출 하기 전에 함수 호출 후 `Update`, 편집 버퍼 진행에서 새로 만들거나 편집한 레코드를 교체, 저장된 된 레코드를 사용 하 여 새로 고쳐집니다. 이 동작을 사용 하면 중단 하는 방법을 `AddNew` 나 `Edit` 새 세션을 시작 하 고: 진행률 레코드에 결함이 있는 인지를 확인 하는 경우 호출 하기만 하면 됩니다 `Edit` 또는 `AddNew` 다시 합니다.

##  <a name="_core_deleting_a_record"></a> 레코드 삭제

레코드 스크롤 및 레코드 집합의 호출에서는 레코드 집합에서 레코드를 삭제 [삭제](../../mfc/reference/crecordset-class.md#delete) 멤버 함수입니다. 와 달리 `AddNew` 하 고 `Edit`를 `Delete` 일치 하는 호출 하지 않아도 `Update`합니다.

호출에 대 한 전제 조건으로 `Delete`, 레코드 집합을 업데이트할 수 있어야 합니다 및 레코드에 있어야 합니다. 합니다 `CanUpdate`, `IsBOF`, `IsEOF`, 및 `IsDeleted` 멤버 함수를 사용 하 여 이러한 조건을 확인할 수 있습니다.

호출 하는 경우 `Delete`:

- ODBC 드라이버에서 지 원하는 경우는 `::SQLSetPos` MFC ODBC API 함수는 함수를 사용 하 여 데이터 원본에서 레코드를 삭제 합니다. 사용 하 여 `::SQLSetPos` 일반적으로 SQL을 사용 하 여 보다 효율적입니다.

   \- 또는 -

- 경우 `::SQLSetPos` 일 수 없습니다 사용 MFC는 다음을 수행 합니다.

   1. 편집 버퍼의 현재 레코드에서와 같이 지원 되지 않습니다 `AddNew` 고 `Edit`입니다.

   1. `Delete` SQL 구문 **삭제** 레코드를 제거 하는 문입니다.

      편집 버퍼의 현재 레코드에로 저장 되지 않습니다 `AddNew` 고 `Edit`입니다.

   1. `Delete` 삭제 커밋-실행 합니다 **삭제** 문입니다. 데이터 원본에서 레코드 삭제 표시 및 ODBC의 스냅숏으로 레코드인 경우.

   1. 삭제 된 레코드의 값은 레코드의 필드 데이터 멤버에 여전히 있지만 Null이 고 레코드 집합의 필드 데이터 멤버는 표시 된 `IsDeleted` 멤버 함수는 0이 아닌 값을 반환 합니다.

   > [!NOTE]
   > 레코드를 삭제 한 후 새 레코드의 데이터를 사용 하 여 편집 버퍼 업데이트나 다른 레코드를 스크롤하면 해야 합니다. 호출 하면 오류가 발생 `Delete` 다시 호출 또는 `Edit`합니다.

업데이트 작업에 사용 되는 SQL 문에 대 한 자세한 내용은 [SQL](../../data/odbc/sql.md)합니다.

## <a name="see-also"></a>참고자료

[레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[레코드 집합: 업데이트 (ODBC)에 대 한 자세한 정보](../../data/odbc/recordset-more-about-updates-odbc.md)<br/>
[RFX](../../data/odbc/record-field-exchange-rfx.md)