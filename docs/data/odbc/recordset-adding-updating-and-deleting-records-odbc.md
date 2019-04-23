---
title: '레코드 집합: 추가, 업데이트 및 삭제할 레코드 (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- records [C++], updating
- record editing [C++], in recordsets
- recordsets [C++], adding records
- records [C++], adding
- ODBC recordsets [C++], adding records
- recordsets [C++], editing records
- recordsets [C++], updating
- records [C++], deleting
- AddNew method
- ODBC recordsets [C++], deleting records
- data in recordsets [C++]
- record editing [C++]
- recordsets [C++], deleting records
- ODBC recordsets [C++], editing records
- records [C++], editing
ms.assetid: 760c8889-bec4-482b-a8f2-319792a6af98
ms.openlocfilehash: 28c885119816c1df662cc0b941e02cb3cf747f3d
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59024610"
---
# <a name="recordset-adding-updating-and-deleting-records-odbc"></a>레코드 집합: 추가, 업데이트 및 삭제할 레코드 (ODBC)

이 항목에서는 MFC ODBC 클래스에 적용됩니다.

> [!NOTE]
>  보다 효율적으로 대량에서 레코드를 추가할 이제 있습니다. 자세한 내용은 참조 하세요. [레코드 집합: (ODBC) 대량 레코드 추가](../../data/odbc/recordset-adding-records-in-bulk-odbc.md)합니다.

> [!NOTE]
>  이 항목에서 파생 된 개체에 적용 됩니다 `CRecordset` 의 대량 행 페치 구현 되지 않았습니다. 대량 행 페치를 사용 하는 경우 참조 [레코드 집합: (ODBC) 대량 레코드 페치](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)합니다.

스냅숏을 업데이트할 수 및 다이너셋에 추가할 수 있습니다 (업데이트)를 편집 하 고 레코드를 삭제 합니다. 이 항목에 설명 합니다.

- [레코드 집합을 업데이트할 수 있는지 여부를 확인 하는 방법을](#_core_determining_whether_your_recordset_is_updatable)합니다.

- [새 레코드를 추가 하는 방법을](#_core_adding_a_record_to_a_recordset)합니다.

- [기존 레코드를 편집 하는 방법](#_core_editing_a_record_in_a_recordset)합니다.

- [레코드를 삭제 하는 방법을](#_core_deleting_a_record_from_a_recordset)합니다.

업데이트 되는 방법에 대 한 자세한 내용은 출력 및 업데이트 내용을 다른 사용자에 게 표시 하는 방법을 참조 하세요 [레코드 집합: 레코드 집합 업데이트 (ODBC)를 기록 하는 방법을](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)합니다. 일반적으로 추가, 편집 또는 레코드를 삭제 하는 경우 레코드 집합 데이터 원본을 즉시 변경 합니다. 관련 된 업데이트 그룹을 트랜잭션으로 일괄 처리할 수도 있습니다. 트랜잭션이 진행에서 중이면 트랜잭션을 커밋할 때까지 업데이트 최종 되지 않습니다. 이 통해 다시 수행 하거나 변경 내용을 롤백할 수 있습니다. 트랜잭션에 대 한 정보를 참조 하세요 [트랜잭션 (ODBC)](../../data/odbc/transaction-odbc.md)합니다.

다음 표에서 다양 한 업데이트 특성을 가진 레코드 집합에 대해 사용할 수 있는 옵션을 보여 줍니다.

### <a name="recordset-readupdate-options"></a>레코드 집합 읽기/업데이트 옵션

|형식|읽기|레코드 편집|레코드 삭제|새로 추가 (추가)|
|----------|----------|-----------------|-------------------|------------------------|
|읽기 전용|Y|N|N|N|
|추가 전용|Y|N|N|Y|
|완벽 하 게 업데이트할 수 있는|Y|Y|Y|Y|

##  <a name="_core_determining_whether_your_recordset_is_updatable"></a> 결정 하는지 여부를 레코드 집합은 업데이트 가능한

레코드 집합 개체는 데이터 원본을 업데이트할 수 있고으로 업데이트할 수 있는 레코드 집합을 연 경우 업데이트할 수 있습니다. ODBC 드라이버의 기능을 사용 하면 SQL 문에서 의해서도 집니다 및 메모리에서 ODBC 커서 라이브러리 인지 합니다. 읽기 전용 레코드 집합 또는 데이터 원본을 업데이트할 수 없습니다.

#### <a name="to-determine-whether-your-recordset-is-updatable"></a>레코드 집합을 업데이트할 수 있는지 여부를 확인 하려면

1. 레코드 집합 개체의 호출 [CanUpdate](../../mfc/reference/crecordset-class.md#canupdate) 멤버 함수입니다.

   `CanUpdate` 레코드 집합을 업데이트할 수 있으면 0이 아닌 값을 반환 합니다.

기본적으로 레코드 집합을 완벽 하 게 업데이트할 수 (수행할 수 있습니다 `AddNew`, `Edit`, 및 `Delete` 작업). 하지만 사용할 수 있습니다 합니다 [appendOnly](../../mfc/reference/crecordset-class.md#open) 업데이트할 수 있는 레코드 집합을 열 수 있습니다. 레코드 집합 열이 방식으로 추가할 수만 사용 하 여 새 레코드의 `AddNew`합니다. 편집 하거나 기존 레코드를 삭제할 수 없습니다. 레코드 집합을 호출 하 여 추가 대해서만 열려 있는지 여부를 테스트할 수 있습니다 합니다 [CanAppend](../../mfc/reference/crecordset-class.md#canappend) 멤버 함수입니다. `CanAppend` 레코드 집합은 완벽 하 게 업데이트 가능 하거나 추가 대해서만 열려 있는 경우 0이 아닌 값을 반환 합니다.

다음 코드를 사용 하는 방법을 보여 줍니다 `CanUpdate` 레코드 집합 개체에 대 한 호출 `rsStudentSet`:

```cpp
if( !rsStudentSet.Open( ) )
    return FALSE;
if( !rsStudentSet.CanUpdate( ) )
{
    AfxMessageBox( "Unable to update the Student recordset." );
    return;
}
```

> [!CAUTION]
>  호출 하 여 레코드 집합을 업데이트 하기 전에 `Update`, 레코드 집합 테이블 (또는 모든 테이블에 있는 고유 인덱스의 열)의 기본 키를 구성 하는 모든 열에 주의 합니다. 경우에 따라 프레임 워크 업데이트 테이블의 레코드를 식별 하 레코드 집합에서 선택한 열만을 사용할 수 있습니다. 필요한 모든 열이 없는 테이블의 참조 무결성이 손상 테이블의 여러 레코드가 업데이트 될 수 있습니다. 호출할 때 프레임 워크에서 예외를 throw 하는 예제의 경우 `Update`합니다.

##  <a name="_core_adding_a_record_to_a_recordset"></a> 레코드 집합에 레코드를 추가합니다.

경우 레코드 집합에 새 레코드를 추가할 수 있습니다 해당 [CanAppend](../../mfc/reference/crecordset-class.md#canappend) 멤버 함수는 0이 아닌 값을 반환 합니다.

#### <a name="to-add-a-new-record-to-a-recordset"></a>레코드 집합에 새 레코드를 추가 하려면

1. 레코드 집합을 추가 해야 합니다.

1. 레코드 집합 개체의 호출 [AddNew](../../mfc/reference/crecordset-class.md#addnew) 멤버 함수입니다.

   `AddNew` 편집 버퍼로 작동 하는 레코드 집합을 준비 합니다. 모든 필드 데이터 멤버는 특수 한 값을 Null로 설정 하 고 호출할 때 값 데이터 소스에 기록 됩니다 (더티) 변경 하도록 변경 되지 않은 것으로 표시 [업데이트](../../mfc/reference/crecordset-class.md#update)합니다.

1. 새 레코드의 필드 데이터 멤버의 값을 설정 합니다.

   필드 데이터 멤버에 값을 할당 합니다. 할당 하지 않으면 해당 데이터 원본에 기록 되지 않습니다.

1. 레코드 집합 개체의 호출 `Update` 멤버 함수입니다.

   `Update` 데이터 원본에 새 레코드를 작성 하 여 추가 완료 합니다. 호출에 실패 하면 발생 하는 방법에 대 한 정보에 대 한 `Update`를 참조 하세요 [레코드 집합: 레코드 집합 업데이트 (ODBC)를 기록 하는 방법을](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)합니다.

추가 된 레코드 레코드 집합에 표시 되는 시기 및 레코드 추가 방법에 대 한 정보를 참조 하세요. [레코드 집합: AddNew를 편집 및 삭제 작업 (ODBC) 어떻게](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md)합니다.

다음 예제에서는 새 레코드를 추가 하는 방법을 보여 줍니다.

```cpp
if( !rsStudent.Open( ) )
    return FALSE;
if( !rsStudent.CanAppend( ) )
    return FALSE;                      // no field values were set
rsStudent.AddNew( );
rsStudent.m_strName = strName;
rsStudent.m_strCity = strCity;
rsStudent.m_strStreet = strStreet;
if( !rsStudent.Update( ) )
{
    AfxMessageBox( "Record not added; no field values were set." );
    return FALSE;
}
```

> [!TIP]
>  취소 하는 `AddNew` 또는 `Edit` 호출, 다른 호출을 수행 하는 단순히 `AddNew` 또는 `Edit` 호출 하거나 `Move` 사용 하 여를 *AFX_MOVE_REFRESH* 매개 변수입니다. 데이터 멤버는 이전 값으로 다시 설정 되며, 원하는 여전히 `Edit` 또는 `Add` 모드입니다.

##  <a name="_core_editing_a_record_in_a_recordset"></a> 레코드 집합에서 레코드 편집

경우에 기존 레코드를 편집할 수 레코드 집합의 [CanUpdate](../../mfc/reference/crecordset-class.md#canupdate) 멤버 함수는 0이 아닌 값을 반환 합니다.

#### <a name="to-edit-an-existing-record-in-a-recordset"></a>레코드 집합에서 기존 레코드를 편집 하려면

1. 레코드 집합을 업데이트할 수 있는지 확인 합니다.

1. 업데이트 하려는 레코드를 스크롤하십시오.

1. 레코드 집합 개체의 호출 [편집](../../mfc/reference/crecordset-class.md#edit) 멤버 함수입니다.

   `Edit` 편집 버퍼로 작동 하는 레코드 집합을 준비 합니다. 모든 필드 데이터 멤버는 레코드 집합 알 수 있습니다 나중에 변경 된 여부 되도록 표시 됩니다. 변경 된 필드 데이터 멤버에 대 한 새 값이 호출 하는 경우 데이터 원본에 쓰는지 [업데이트](../../mfc/reference/crecordset-class.md#update)합니다.

1. 새 레코드의 필드 데이터 멤버의 값을 설정 합니다.

   필드 데이터 멤버에 값을 할당 합니다. 이러한 값을 할당 하지 않으면 변경 되지 않습니다.

1. 레코드 집합 개체의 호출 `Update` 멤버 함수입니다.

   `Update` 데이터 원본에 변경 된 레코드를 작성 하 여 편집을 완료 합니다. 호출에 실패 하면 발생 하는 방법에 대 한 정보에 대 한 `Update`를 참조 하세요 [레코드 집합: 레코드 집합 업데이트 (ODBC)를 기록 하는 방법을](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)합니다.

레코드를 편집한 후 편집할된 레코드에는 현재 레코드 유지 됩니다.

다음 예제는 `Edit` 작업 합니다. 사용자가 편집 하려는 레코드로 이동 가정 합니다.

```cpp
rsStudent.Edit( );
rsStudent.m_strStreet = strNewStreet;
rsStudent.m_strCity = strNewCity;
rsStudent.m_strState = strNewState;
rsStudent.m_strPostalCode = strNewPostalCode;
if( !rsStudent.Update( ) )
{
    AfxMessageBox( "Record not updated; no field values were set." );
    return FALSE;
}
```

> [!TIP]
> 취소 하는 `AddNew` 또는 `Edit` 호출, 다른 호출을 수행 하는 단순히 `AddNew` 또는 `Edit` 호출 하거나 `Move` 사용 하 여를 *AFX_MOVE_REFRESH* 매개 변수입니다. 데이터 멤버는 이전 값으로 다시 설정 되며, 원하는 여전히 `Edit` 또는 `Add` 모드입니다.

##  <a name="_core_deleting_a_record_from_a_recordset"></a> 레코드 집합에서 레코드를 삭제합니다.

경우에 레코드를 삭제할 수 레코드 집합의 [CanUpdate](../../mfc/reference/crecordset-class.md#canupdate) 멤버 함수는 0이 아닌 값을 반환 합니다.

#### <a name="to-delete-a-record"></a>레코드 삭제 하려면

1. 레코드 집합을 업데이트할 수 있는지 확인 합니다.

1. 업데이트 하려는 레코드를 스크롤하십시오.

1. 레코드 집합 개체의 호출 [삭제](../../mfc/reference/crecordset-class.md#delete) 멤버 함수입니다.

   `Delete` 즉시 삭제, 레코드 집합 및 데이터 원본에서 레코드를 표시 합니다.

   와 달리 `AddNew` 하 고 `Edit`를 `Delete` 에 없습니다 `Update` 호출 합니다.

1. 다른 레코드를 스크롤하십시오.

   > [!NOTE]
   >  레코드 집합을 탐색할 때 삭제 된 레코드 건너뛰지 않을 수 있습니다. 자세한 내용은 참조는 [IsDeleted](../../mfc/reference/crecordset-class.md#isdeleted) 멤버 함수입니다.

다음 예제는 `Delete` 작업 합니다. 사용자는 삭제 하는 사용자가 레코드를 옮겨 졌음을 가정 합니다. 후 `Delete` 는 호출을 고려해 야 새 레코드로 이동 합니다.

```
rsStudent.Delete( );
rsStudent.MoveNext( );
```

효과 대 한 자세한 합니다 `AddNew`, `Edit`, 및 `Delete` 멤버 함수를 참조 하세요. [레코드 집합: 레코드 집합 업데이트 (ODBC)를 기록 하는 방법을](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)합니다.

## <a name="see-also"></a>참고자료

[레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[레코드 집합: 레코드 잠금 (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)