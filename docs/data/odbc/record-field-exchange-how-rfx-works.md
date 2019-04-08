---
title: '레코드 필드 교환: RFX 작동 방식'
ms.date: 11/04/2016
helpviewer_keywords:
- record editing [C++], using RFX
- RFX (ODBC) [C++], updating data in recordsets
- scrolling [C++]
- ODBC [C++], RFX
- data binding [C++], DFX
- scrolling [C++], RFX
- RFX (ODBC) [C++], binding fields and parameters
ms.assetid: e647cacd-62b0-4b80-9e20-b392deca5a88
ms.openlocfilehash: 7da9d480f16dcb6bc5ded0a1dff559b1b1ac4b38
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59032679"
---
# <a name="record-field-exchange-how-rfx-works"></a>레코드 필드 교환: RFX 작동 방식

이 항목에서는 RFX 과정을 설명 합니다. 이 고급 항목 포함:

- [RFX와 레코드 집합](#_core_rfx_and_the_recordset)

- [RFX 프로세스](#_core_the_record_field_exchange_process)

> [!NOTE]
>  이 항목에서 파생 된 클래스에 적용 됩니다 `CRecordset` 의 대량 행 페치 구현 되지 않았습니다. 대량 행 페치를 사용 하는 경우 대량 레코드 필드 교환 (대량 RFX) 구현 됩니다. 대량 RFX RFX와 비슷합니다. 차이점을 이해 하려면 [레코드 집합: (ODBC) 대량 레코드 페치](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)합니다.

##  <a name="_core_rfx_and_the_recordset"></a> RFX와 레코드 집합

한 레코드의 선택한 열을 포함 하는 편집 버퍼를 구성 하는 레코드 집합 개체의 필드 데이터 멤버를 함께 사용 합니다. 레코드 집합을 처음으로 열면 첫 번째 레코드 읽기를 RFX 바인딩 (연결 각) 선택 된 열을 적절 한 필드 데이터 멤버의 주소입니다. 레코드 집합에서 레코드를 업데이트할 때 RFX SQL 보낼 ODBC API 함수를 호출 하는 **업데이트** 하거나 **삽입** 드라이버는 문입니다. RFX 필드 데이터 멤버에 대 한 정보를 사용 하 여 쓸 열을 지정 합니다.

프레임 워크 버퍼를 백업 합니다 편집 특정 단계에서 필요에 따라 해당 내용을 복원할 수 있도록 합니다. RFX 새 레코드를 추가 하기 전과 기존 레코드를 편집 하기 전에 편집 버퍼를 백업 합니다. 후 일부 경우에 예를 들어 편집 버퍼를 복원 하는 `Update` 호출 다음 `AddNew`합니다. 사용자가 새로 변경된 된 편집 버퍼 버리는에서 예를 들어를 호출 하기 전에 다른 레코드로 이동 하는 경우에 편집 버퍼 복원 되지 않습니다 `Update`합니다.

데이터 원본에서 레코드 집합의 필드 데이터 멤버 사이 데이터를 교환 하는 것 외에도 RFX 바인딩 매개 변수를 관리 합니다. 매개 변수 데이터 멤버의 순서 대로 바인딩된 레코드 집합을 열면는 "?" SQL 문에서 자리 표시자는 `CRecordset::Open` 생성 합니다. 자세한 내용은 참조 하세요. [레코드 집합: 레코드 집합 (ODBC)를 매개 변수화](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)합니다.

레코드 집합 클래스의 재정의 `DoFieldExchange` 두 방향 모두에서 데이터를 이동 합니다. 모든 작업을 수행 합니다. RFX (DDX) 하는 대화 상자 데이터 교환 같은 클래스의 데이터 멤버에 대 한 정보를 해야합니다. 마법사의 특정 레코드 집합을 구현 하 여 필요한 정보를 제공 `DoFieldExchange` , 데이터를 기반으로 필드 마법사를 사용 하 여 지정한 멤버 이름 및 데이터 형식입니다.

##  <a name="_core_the_record_field_exchange_process"></a> 레코드 필드 교환 프로세스

이 섹션에서는 레코드 집합 개체를 열 및 추가 하면 RFX 이벤트 시퀀스를 설명 하 고, 업데이트 및 레코드를 삭제 합니다. 테이블 [의 레코드 집합을 열 때 RFX 작업](#_core_sequence_of_rfx_operations_during_recordset_open) 테이블과 [스크롤할 때 RFX 작업](#_core_sequence_of_rfx_operations_during_scrolling) 이 항목의 RFX 프로세스로 프로세스를 보여 줍니다는 `Move` 명령에 레코드 집합 및 RFX 업데이트를 관리 합니다. 이러한 프로세스 중 [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) 많은 다른 작업을 수행 하기 위해 호출 됩니다. 합니다 `m_nOperation` 의 데이터 멤버를 [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) 개체 작업은 요청을 확인 합니다. 읽을 도움이 될 수 있습니다 [레코드 집합: 레코드 집합 선택 (ODBC)를 기록 하는 방법](../../data/odbc/recordset-how-recordsets-select-records-odbc.md) 고 [레코드 집합: 어떻게 레코드 집합 업데이트 (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) 이 항목을 읽기 전에 합니다.

###  <a name="_mfc_rfx.3a_.initial_binding_of_columns_and_parameters"></a> RFX: 열 및 매개 변수의 초기 바인딩

순서 대로 레코드 집합 개체를 호출 하는 경우 다음 RFX 작업이 발생할 [열고](../../mfc/reference/crecordset-class.md#open) 멤버 함수:

- 프레임 워크를 호출 하는 레코드 집합 매개 변수 데이터 멤버에 있는 경우 `DoFieldExchange` 레코드 집합의 SQL 문 문자열의 매개 변수 자리 표시자에는 매개 변수를 바인딩합니다. 각 자리 표시자에 대 한 매개 변수 값의 형식 종속 표현을 사용 하는 데이터에는 **선택** 문입니다. 이 SQL 문의 준비 되었지만 실행 하기 전에 발생 합니다. 문 준비에 대 한 내용은 참조는 `::SQLPrepare` odbc에서 함수 *프로그래머 참고 자료*합니다.

- 프레임 워크 호출 `DoFieldExchange` 를 두 번째로 선택한 열의 값을 레코드 집합의 필드 데이터 멤버를 해당 바인딩할 합니다. 이 첫 번째 레코드의 열이 포함 된 편집 버퍼로 레코드 집합 개체를 설정 합니다.

- 레코드 집합에는 SQL 문을 실행 하 고 데이터 원본 첫 번째 레코드를 선택 합니다. 레코드의 열은 레코드 집합의 필드 데이터 멤버에 로드 됩니다.

다음 표에서 레코드 집합을 열 때 RFX 연산의 순서를 보여 줍니다.

### <a name="_core_sequence_of_rfx_operations_during_recordset_open"></a> 레코드 집합 열기 중 RFX 작업 시퀀스

|작업|DoFieldExchange 작업|Database/SQL 작업|
|--------------------|-------------------------------|-----------------------------|
|1. 레코드 집합을 엽니다.|||
||2. SQL 문을 작성 합니다.||
|||3. SQL을 보냅니다.|
||4. 매개 변수 데이터 멤버에 바인딩하십시오.||
||5. 열에 필드 데이터 멤버를 바인딩하십시오.||
|||6. ODBC에서 이동 하는 데이터를 채웁니다.|
||7. C + +에 대 한 데이터를 수정 합니다.||

레코드 집합 ODBC의 준비 된 실행을 사용 하 여 동일한 SQL 문을 사용 하 여 빠르게 다시 쿼리할 수 있도록 합니다. 준비 된 실행에 대 한 자세한 내용은 ODBC SDK를 참조 하세요 *프로그래머 참고 자료* MSDN 라이브러리에서.

###  <a name="_mfc_rfx.3a_.scrolling"></a> RFX: 스크롤

프레임 워크를 호출 하는 다른 레코드 사이를 스크롤하면 `DoFieldExchange` 새 레코드에 대 한 값을 사용 하 여 필드 데이터 멤버에 이전에 저장 된 값을 바꿔야 합니다.

다음 표에서 사용자가 레코드 간을 이동할 때 RFX 연산의 순서를 보여 줍니다.

### <a name="_core_sequence_of_rfx_operations_during_scrolling"></a> 스크롤 하는 동안 RFX 작업 시퀀스

|작업|DoFieldExchange 작업|Database/SQL 작업|
|--------------------|-------------------------------|-----------------------------|
|1. 호출 `MoveNext` 또는 기타 이동 기능 중 하나입니다.|||
|||2. ODBC에서 이동 하는 데이터를 채웁니다.|
||3. C + +에 대 한 데이터를 수정 합니다.||

###  <a name="_mfc_rfx.3a_.adding_new_records_and_editing_existing_records"></a> RFX: 새 레코드를 추가 하 고 기존 레코드를 편집 합니다.

새 레코드를 추가 하는 경우 레코드 집합에서 새 레코드의 콘텐츠를 구축 하는 편집 버퍼로 작동 합니다. 레코드를 추가할 때와 마찬가지로 레코드 편집에서는 레코드 집합의 필드 데이터 멤버의 값을 변경 합니다. RFX 관점에서 시퀀스는 다음과 같습니다.

1. 레코드 집합의 내용을 [AddNew](../../mfc/reference/crecordset-class.md#addnew) 하거나 [편집](../../mfc/reference/crecordset-class.md#edit) 멤버 함수로 인해 RFX 나중에 복원할 수 있도록 현재 편집 버퍼를 저장 합니다.

1. `AddNew` 또는 `Edit` RFX 변경 된 필드 데이터 멤버를 검색할 수 있도록 편집 버퍼에 필드를 준비 합니다.

   새 레코드를 가진 새 항목을 비교할 값이 없는 이전에 있으므로 `AddNew` PSEUDO_NULL 값으로 각 필드 데이터 멤버의 값을 설정 합니다. 나중에 호출할 때 `Update`, RFX PSEUDO_NULL 값을 사용 하 여 각 데이터 멤버의 값을 비교 합니다. 차이가 없으면 데이터 멤버가 설정 되었습니다. (PSEUDO_NULL Null 값이 true 인 레코드 열으로 같지는 않습니다도 이러한 중 하나는 c + + NULL와 동일 합니다.)

   달리 합니다 `Update` 에 대 한 호출 `AddNew`의 `Update` 에 대 한 호출 `Edit` PSEUDO_NULL 사용 하기 보다는 이전에 저장 된 값을 사용 하 여 업데이트 된 값을 비교 합니다. 차이점은 `AddNew` 값이 없는 이전에 저장 된 비교 합니다.

1. 직접를 편집 하려면 해당 값 또는 새 레코드를 채우려는 필드 데이터 멤버의 값을 설정 합니다. 이 호출을 포함할 수 있습니다 `SetFieldNull`합니다.

1. 호출 하 여 [업데이트](../../mfc/reference/crecordset-class.md#update) 2 단계에 설명 된 대로 변경 된 필드 데이터 멤버에 대 한 확인 (표를 참조 하십시오 [스크롤할 때 RFX 작업](#_core_sequence_of_rfx_operations_during_scrolling)). None으로 변경 된 경우 `Update` 0을 반환 합니다. 일부 필드 데이터 멤버가 변경 되 면 `Update` 준비 하 고 SQL 실행 **삽입** 레코드의 모든 업데이트 된 필드에 대 한 값을 포함 하는 문입니다.

1. 에 대 한 `AddNew`, `Update` 이전의 현재 레코드의 이전에 저장 된 값을 복원 하 여 완료 된 `AddNew` 호출 합니다. 에 대 한 `Edit`를 편집한 경우에 새 값에서에서 그대로 유지 됩니다.

다음 표에서 새 레코드를 추가 하거나 기존 레코드를 편집할 때 RFX 연산의 순서를 보여 줍니다.

### <a name="sequence-of-rfx-operations-during-addnew-and-edit"></a>AddNew 및 편집 하는 동안 RFX 작업 시퀀스

|작업|DoFieldExchange 작업|Database/SQL 작업|
|--------------------|-------------------------------|-----------------------------|
|1. 호출 `AddNew` 또는 `Edit`합니다.|||
||2. 편집 버퍼를 백업 합니다.||
||3. 에 대 한 `AddNew`, 필드 데이터 멤버를 "정리"으로 표시 및 Null입니다.||
|4. 레코드 집합 필드 데이터 멤버에 값을 할당 합니다.|||
|5. `Update`를 호출합니다.|||
||6. 변경 된 필드를 확인 합니다.||
||7. SQL을 생성 **삽입** 에 대 한 문을 `AddNew` 하거나 **업데이트** 문을 `Edit`합니다.||
|||8. SQL을 보냅니다.|
||9. 에 대 한 `AddNew`, 편집 버퍼 해당 백업 콘텐츠를 복원 합니다. 에 대 한 `Edit`, 백업을 삭제 합니다.||

### <a name="rfx-deleting-existing-records"></a>RFX: 기존 레코드를 삭제합니다.

레코드를 삭제 하 RFX는 모든 필드는 레코드가 삭제 되 고 떠나 해야 하는 알림으로 NULL로 설정 합니다. 다른 RFX 시퀀스 정보가 필요가 없습니다.

## <a name="see-also"></a>참고자료

[RFX](../../data/odbc/record-field-exchange-rfx.md)<br/>
[MFC ODBC 소비](../../mfc/reference/adding-an-mfc-odbc-consumer.md)<br/>
[매크로, 전역 함수 및 전역 변수](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[CFieldExchange 클래스](../../mfc/reference/cfieldexchange-class.md)<br/>
[CRecordset::DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)