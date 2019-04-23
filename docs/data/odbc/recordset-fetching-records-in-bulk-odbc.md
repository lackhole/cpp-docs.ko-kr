---
title: '레코드 집합: (ODBC) 대량 레코드 페치'
ms.date: 11/04/2016
helpviewer_keywords:
- bulk row fetching, implementing
- ODBC recordsets, bulk row fetching
- bulk record field exchange
- bulk row fetching
- bulk RFX functions
- recordsets, bulk row fetching
- DoBulkFieldExchange method
- fetching ODBC records in bulk
- RFX (ODBC), bulk
- rowsets, bulk row fetching
- RFX (ODBC), bulk row fetching
ms.assetid: 20d10fe9-c58a-414a-b675-cdf9aa283e4f
ms.openlocfilehash: 2fdcbf18fcb0d97ba7b2a39aa9bbbd79e65a4112
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59027768"
---
# <a name="recordset-fetching-records-in-bulk-odbc"></a>레코드 집합: (ODBC) 대량 레코드 페치

이 항목에서는 MFC ODBC 클래스에 적용됩니다.

클래스 `CRecordset` 즉, 여러 레코드 데이터 원본에서 한 번에 하나의 레코드를 검색 하지 않고 단일 인출 하는 동안 한 번에 검색할 수 있습니다는 대량 행 페치에 대 한 지원을 제공 합니다. 파생 된만 대량 행 페치를 구현할 수 있습니다 `CRecordset` 클래스입니다. 레코드 집합 개체를 데이터 원본에서 데이터 전송 프로세스에 대량 레코드 필드 교환 (대량 RFX) 라고 합니다. 대량 행 페치를 사용 하지 않는 경우는 `CRecordset`-파생된 클래스에서 데이터 레코드 필드 교환 (RFX)를 통해 전송 됩니다. 자세한 내용은 [Exchange RFX (레코드 필드)](../../data/odbc/record-field-exchange-rfx.md)합니다.

이 항목에 설명 합니다.

- [CRecordset 대량 행 페치는 지원](#_core_how_crecordset_supports_bulk_row_fetching)합니다.

- [대량 행 페치를 사용 하는 경우 몇 가지 특별 한 고려](#_core_special_considerations)합니다.

- [대량 레코드 필드 교환을 구현 하는 방법을](#_core_how_to_implement_bulk_record_field_exchange)합니다.

##  <a name="_core_how_crecordset_supports_bulk_row_fetching"></a> CRecordset 대량 행 페치는 지원

레코드 집합 개체를 열기 전에 사용 하 여 행 집합 크기를 정의할 수 있습니다는 `SetRowsetSize` 멤버 함수입니다. 행 집합 크기 레코드 수를 단일 인출 하는 동안 검색 하도록 지정 합니다. 대량 행 페치 구현 되는 기본 행 집합 크기는 25입니다. 대량 행 페치 구현 되지 않은 경우 행 집합 크기가 1로 고정 됩니다.

행 집합 크기를 초기화 한 후에 호출 하는 [열고](../../mfc/reference/crecordset-class.md#open) 멤버 함수입니다. 지정 해야 합니다 `CRecordset::useMultiRowFetch` 옵션을는 *dwOptions* 대량 행 페치를 구현 하는 매개 변수입니다. 또한 설정할 수 있습니다는 `CRecordset::userAllocMultiRowBuffers` 옵션입니다. 대량 레코드 필드 교환 메커니즘 배열을 사용 하 여 여러 행을 인출 하는 동안 검색 데이터의 저장. 이러한 저장소 버퍼 프레임 워크에서 자동으로 할당할 수 있습니다 하거나 수동으로 할당할 수 있습니다. 지정 하는 `CRecordset::userAllocMultiRowBuffers` 옵션 할당 할 것을 의미 합니다.

다음 표에서에서 제공 하는 멤버 함수가 나와 `CRecordset` 대량 행 페치를 지원 하도록 합니다.

|멤버 함수|설명|
|---------------------|-----------------|
|[CheckRowsetError](../../mfc/reference/crecordset-class.md#checkrowseterror)|가져오는 동안 발생 하는 모든 오류를 처리 하는 가상 함수입니다.|
|[DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange)|대량 레코드 필드 교환으로 구현 합니다. 자동으로 호출 전송 하기 위해 여러 데이터 행을 레코드 집합 개체를 데이터 원본에서.|
|[GetRowsetSize](../../mfc/reference/crecordset-class.md#getrowsetsize)|행 집합 크기에 대 한 현재 설정을 검색합니다.|
|[GetRowsFetched](../../mfc/reference/crecordset-class.md#getrowsfetched)|페치 후 실제로 검색 된 행의 수를 알려줍니다. 대부분의 경우에는 불완전 한 행 집합을 사용 하 여 인출 된 경우가 아니면 행 집합 크기입니다.|
|[GetRowStatus](../../mfc/reference/crecordset-class.md#getrowstatus)|행 집합 내의 특정 행에 대 한 인출 상태를 반환합니다.|
|[RefreshRowset](../../mfc/reference/crecordset-class.md#refreshrowset)|데이터 및 행 집합 내의 특정 행의 상태를 새로 고칩니다.|
|[SetRowsetCursorPosition](../../mfc/reference/crecordset-class.md#setrowsetcursorposition)|행 집합 내의 특정 행에 커서를 이동합니다.|
|[SetRowsetSize](../../mfc/reference/crecordset-class.md#setrowsetsize)|지정된 된 값으로 행 집합 크기에 대 한 설정을 변경 하는 가상 함수입니다.|

##  <a name="_core_special_considerations"></a> 특별 고려 사항

성능 향상을 대량 행 페치 있지만 일부 기능은 다르게 작동 합니다. 대량 행 페치를 구현 하기 전에 다음 사항을 고려 합니다.

- 프레임 워크를 자동으로 호출 된 `DoBulkFieldExchange` 레코드 집합 개체를 데이터 원본에서 데이터를 전송할 멤버 함수입니다. 그러나 데이터 다시 데이터 원본에는 레코드 집합에서 하지 전송 됩니다. 호출 된 `AddNew`, `Edit`, `Delete`, 또는 `Update` 실패 한 어설션의 멤버 함수 결과입니다. 하지만 `CRecordset` 현재 메커니즘을 제공 하지 않는 데이터의 대량 행을 업데이트 하는 것에 대 한 ODBC API 함수를 사용 하 여 사용자 고유의 함수를 작성할 수 있습니다 `SQLSetPos`합니다. 에 대 한 자세한 내용은 `SQLSetPos`를 참조 합니다 *ODBC SDK 프로그래머 참고 자료* MSDN 설명서에서.

- 멤버 함수 `IsDeleted`, `IsFieldDirty`를 `IsFieldNull`를 `IsFieldNullable`를 `SetFieldDirty`, 및 `SetFieldNull` 대량 행 페치를 구현 하는 레코드 집합에서 사용할 수 없습니다. 호출할 수 있습니다 `GetRowStatus` 대신 `IsDeleted`, 및 `GetODBCFieldInfo` 대신 `IsFieldNullable`합니다.

- `Move` 작업 행 집합에서 레코드 집합의 위치를 조정 합니다. 예를 들어, 10의 초기 행 집합 크기를 사용 하 여 100 개의 레코드가 있는 레코드 집합을 엽니다. `Open` 1 행에서 행 1 ~ 10이 고 현재 레코드를 인출 합니다. 에 대 한 호출 `MoveNext` 다음 행이 아닌 다음 행 집합을 인출 합니다. 이 행 집합 행 11에서 행 11 ~ 20, 현재 레코드를 사용 하 여 구성 됩니다. 유의 `MoveNext` 및 `Move( 1 )` 대량 행 페치는 구현 될 경우 해당 됩니다. `Move( 1 )` 현재 레코드의 1 행부터 시작 하는 행 집합을 인출 합니다. 이 예제에서는 호출 `Move( 1 )` 호출한 후 `Open` 2 행에 있는 현재 레코드 2 11 ~ 행으로 구성 된 행을 인출 합니다. 자세한 내용은 참조는 [이동](../../mfc/reference/crecordset-class.md#move) 멤버 함수입니다.

- 레코드 필드 교환 달리 마법사는 대량 레코드 필드 교환을 지원 하지 않습니다. 즉, 수동으로 필드 데이터 멤버를 선언 하 고 수동으로 재정의 해야 합니다 `DoBulkFieldExchange` 대량 RFX 함수에 대 한 호출을 작성 하 여 합니다. 자세한 내용은 [레코드 필드 교환 함수](../../mfc/reference/record-field-exchange-functions.md) 에 *클래스 라이브러리 참조*합니다.

##  <a name="_core_how_to_implement_bulk_record_field_exchange"></a> 대량 레코드 필드 교환을 구현 하는 방법

대량 레코드 필드 교환 레코드 집합 개체를 데이터 원본에서 데이터의 행 집합을 전송합니다. 대량 RFX 함수에는 행 집합의 각 데이터 항목의 길이 저장 하는 배열 뿐만 아니라이 데이터를 저장 하는 배열을 사용 합니다. 클래스 정의에서 필드 데이터 멤버 배열 데이터에 액세스에 대 한 포인터 정의 해야 합니다. 또한 길이의 배열 액세스에 대 한 포인터의 집합을 정의 해야 합니다. 매개 변수 데이터 멤버 포인터를 선언할 수 없습니다. 대량 레코드 필드 교환을 사용 하는 경우 매개 변수 데이터 멤버를 선언 선언 레코드 필드 교환을 사용 하는 경우와 같습니다. 다음 코드는 간단한 예제를 보여 줍니다.

```cpp
class MultiRowSet : public CRecordset
{
public:
   // Field/Param Data
      // field data members
      long* m_rgID;
      LPSTR m_rgName;

      // pointers for the lengths
      // of the field data
      long* m_rgIDLengths;
      long* m_rgNameLengths;

      // input parameter data member
      CString m_strNameParam;

   .
   .
   .
}
```

이러한 저장소 버퍼를 수동으로 할당 하거나 할당을 수행 하는 프레임 워크에서. 지정 버퍼를 직접 할당 해야 합니다는 `CRecordset::userAllocMultiRowBuffers` 옵션을는 *dwOptions* 에서 매개 변수는 `Open` 멤버 함수입니다. 최소 행 집합 크기와 같은 배열의 크기를 설정 해야 합니다. 프레임 워크는 할당 하려는 경우 null 포인터를 초기화 해야 합니다. 이 레코드 집합 개체의 생성자에서 일반적으로 수행 됩니다.

```cpp
MultiRowSet::MultiRowSet( CDatabase* pDB )
   : CRecordset( pDB )
{
   m_rgID = NULL;
   m_rgName = NULL;
   m_rgIDLengths = NULL;
   m_rgNameLengths = NULL;
   m_strNameParam = "";

   m_nFields = 2;
   m_nParams = 1;

   .
   .
   .
}
```

마지막으로 재정의 해야 합니다는 `DoBulkFieldExchange` 멤버 함수입니다. 필드 데이터 멤버에 대 한 대량 RFX 함수를; 호출 모든 매개 변수 데이터 멤버에 대해 RFX 함수를 호출 합니다. SQL 문 또는 저장된 프로시저를 전달 하 여 레코드 집합을 연 경우 `Open`, 대량 RFX 호출을 수행 하는 순서는 레코드 집합의 열 순서와 일치 해야;는 RFX 순서 매개 변수 일치 해야 합니다에 대해를 호출 하는 마찬가지로 순서는 SQL 문이나 저장된 프로시저에서 매개 변수입니다.

```cpp
void MultiRowSet::DoBulkFieldExchange( CFieldExchange* pFX )
{
   // call the Bulk RFX functions
   // for field data members
   pFX->SetFieldType( CFieldExchange::outputColumn );
   RFX_Long_Bulk( pFX, _T( "[colRecID]" ),
                  &m_rgID, &m_rgIDLengths );
   RFX_Text_Bulk( pFX, _T( "[colName]" ),
                  &m_rgName, &m_rgNameLengths, 30 );

   // call the RFX functions for
   // for parameter data members
   pFX->SetFieldType( CFieldExchange::inputParam );
   RFX_Text( pFX, "NameParam", m_strNameParam );
}
```

> [!NOTE]
>  호출 해야 합니다 `Close` 전에 파생 된 멤버 함수 `CRecordset` 클래스 범위를 벗어납니다. 이렇게 하면 프레임 워크에 의해 할당 된 메모리 해제 됩니다. 더 좋은 프로그래밍 항상 명시적으로 호출 하는 방법은 `Close`대량 행 페치 구현 여부에 관계 없이 합니다.

레코드 필드 교환 (RFX)에 대 한 자세한 내용은 참조 하세요. [레코드 필드 교환: RFX 작동 방식](../../data/odbc/record-field-exchange-how-rfx-works.md)합니다. 매개 변수를 사용 하는 방법에 대 한 자세한 내용은 참조 하십시오 [CFieldExchange::SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) 고 [레코드 집합: 레코드 집합 (ODBC)를 매개 변수화](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)합니다.

## <a name="see-also"></a>참고자료

[레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[CRecordset::m_nFields](../../mfc/reference/crecordset-class.md#m_nfields)<br/>
[CRecordset::m_nParams](../../mfc/reference/crecordset-class.md#m_nparams)

