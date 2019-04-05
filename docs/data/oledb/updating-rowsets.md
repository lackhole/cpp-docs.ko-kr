---
title: 행 집합 업데이트
ms.date: 10/19/2018
helpviewer_keywords:
- rowsets, updating data
- updating data, rowsets
- updating rowsets
- rowsets
ms.assetid: 39588758-5c72-4254-a10d-cc2b1f473357
ms.openlocfilehash: 7151d897469993b2f9be3575eb11a08844af3c69
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59028362"
---
# <a name="updating-rowsets"></a>행 집합 업데이트

기본 데이터베이스 작업은 업데이트 또는 데이터 저장소에 데이터를 작성 하는 것입니다. OLE DB에서 업데이트 메커니즘은 간단합니다. 소비자 애플리케이션이 바인딩된 데이터 멤버의 값을 설정하고 행 집합에 해당 값을 쓴 다음 소비자가 공급자에게 데이터 저장소를 업데이트하도록 요청합니다.

소비자는 다음과 같은 유형의 행 집합 데이터에서 업데이트를 완료할 수: 행 내의 열 값을 설정 하 고 행 삽입, 행을 삭제 합니다. OLE DB 템플릿 클래스는 이러한 작업을 완료 하려면 [CRowset](../../data/oledb/crowset-class.md) 구현 하는 [IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85)) 인터페이스 및 다음 인터페이스 메서드를 재정의 합니다.

- [SetData](../../data/oledb/crowset-setdata.md) 변경 열 행 집합의 행에 값을 하며 SQL UPDATE 명령과 동일한 것으로 간주 합니다.

- [삽입](../../data/oledb/crowset-insert.md) 는 행 집합에 행을 삽입 하며 SQL INSERT 명령과 동일한 것으로 간주 합니다.

- [삭제](../../data/oledb/crowset-delete.md) 는 행 집합에서 행을 삭제 하며 SQL DELETE 명령과 동일한 것으로 간주 합니다.

## <a name="supporting-update-operations"></a>업데이트 작업 지원

사용 하 여 소비자를 만드는 경우는 **ATL OLE DB 소비자 마법사**하나를 선택 하 여 업데이트 작업을 지원할 수 있습니다, 또는 세 가지 중 확인란 **변경**를 **삽입**, 및 **삭제**합니다. 이러한 옵션을 선택 하면 마법사 수정 코드를 적절 하 게 선택한 변경 유형을 지원 하도록 합니다. 그러나 마법사를 사용 하지 않는 경우 다음 행 집합 속성을 설정 하려면 `VARIANT_TRUE` 업데이트를 지원 합니다.

- `DBPROPVAL_UP_CHANGE` 행의 데이터 값을 변경할 수 있습니다.

- `DBPROPVAL_UP_INSERT` 행을 삽입할 수 있습니다.

- `DBPROPVAL_UP_DELETE` 행을 삭제할 수 있습니다.

속성을 다음과 같이 설정합니다.

```cpp
CDBPropSet ps(DBPROPSET_ROWSET);

ps.AddProperty(DBPROP_IRowsetChange, true);
ps.AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE);
```

하나 이상의 열에 쓸 수 없으면 변경, 삽입 또는 삭제 작업이 실패할 수 있습니다. 이 문제를 해결 하려면 커서 맵을 수정 합니다.

## <a name="setting-data-in-rows"></a>행의 데이터 설정

[Crowset:: Setdata](../../data/oledb/crowset-setdata.md) 는 현재 행의 하나 이상 열에 데이터 값을 설정합니다. 열에 바인딩된 데이터 멤버의 값을 설정 하는 다음 코드 `Name` 하 고 `Units in Stock` 테이블의 `Products` 를 호출 하 `SetData` 행 집합의 100 번째 행에 해당 값을 쓰려면:

```cpp
// Instantiate a rowset based on the user record class
CTable<CAccessor<CProductAccessor>> product;
CSession session;

// Open the rowset and move to the 100th row
product.Open(session, "Product", &ps, 1);  // ps is the property set
product.MoveToBookmark(&bookmark, 0);      // Assume that bookmark is set to 100th row

// Change the values of columns "Name" and "Units in Stock" in the current row of the Product table
_tcscpy_s(product.m_ProductName, product.m_sizeOfProductName, _T( "Candle" ) );

product.m_UnitsInStock = 10000;

// Set the data
HRESULT hr = product.SetData();
```

## <a name="inserting-rows-into-rowsets"></a>행 집합에 행 삽입

[Crowset:: Insert](../../data/oledb/crowset-insert.md) 는 접근자의 데이터를 사용하여 새 행을 만들고 초기화합니다. `Insert` 현재 행 뒤 완전히 새로운 행을 만듭니다. 현재 행 다음 행으로 증가시킬지 또는 변경 되지 않은 상태로 그대로 둘 것인지를 지정 해야 합니다. 이렇게 하려면 *bGetRow* 매개 변수를 설정합니다.

```cpp
HRESULT Insert(int nAccessor = 0, bool bGetRow = false)
```

- **false** (기본값)이면 현재 행이 다음 행으로 증가합니다(이 경우 삽입된 행을 가리킴).

- **true** 는 현재 행 유지 위치를 지정 합니다.

다음 코드는 테이블의 열에 바인딩된 데이터 멤버의 값을 설정 `Products` 를 호출 하 `Insert` 행 집합의 100 번째 행을 한 후 해당 값을 사용 하 여 새 행을 삽입 합니다. 새 행에 정의 되지 않은 데이터를 방지 하려면 모든 열 값을 설정 하는 것이 좋습니다.

```cpp
// Instantiate a rowset based on the user record class
CTable<CAccessor<CProductAccessor>> product;
CSession session;

// Open the rowset and move to the 100th row
product.Open(session, "Product", &ps, 1);  // ps is the property set
product.MoveToBookmark(&bookmark, 0);      // Assume that bookmark is set to 100th row

// Set the column values for a row of the Product table, then insert the row
product.m_ProductID = 101;
_tcscpy_s(product.m_ProductName, product.m_sizeOfProductName, _T( "Candle" ) );

product.m_SupplierID = 27857;
product.m_CategoryID = 372;
_tcscpy_s(product.m_QuantityPerUnit, product.m_sizeOfQuantityPerUnit, _T( "Pack of 10" ) );

product.m_UnitPrice = 20;
product.m_UnitsInStock = 10000;
product.m_UnitsOnOrder = 5201;
product.m_ReorderLevel = 5000;
product.m_Discontinued = false;

// You must also initialize the status and length fields before setting/inserting data
// Set the column status values
m_dwProductIDStatus = DBSTATUS_S_OK;
m_dwProductNameStatus = DBSTATUS_S_OK;
m_dwSupplierIDStatus = DBSTATUS_S_OK;
m_dwCategoryIDStatus = DBSTATUS_S_OK;
m_dwQuantityPerUnitStatus = DBSTATUS_S_OK;
m_dwUnitPriceStatus = DBSTATUS_S_OK;
m_dwUnitsInStockStatus = DBSTATUS_S_OK;
m_dwUnitsOnOrderStatus = DBSTATUS_S_OK;
m_dwReorderLevelStatus = DBSTATUS_S_OK;
m_dwDiscontinuedStatus = DBSTATUS_S_OK;

// Set the column length value for column data members that are not fixed-length types.
// The value should be the length of the string that you are setting.
m_dwProductNameLength = 6;             // "Candle" has 6 characters
m_dwQuantityPerUnitLength = 10;        // "Pack of 10" has 10 characters

// Insert the data
HRESULT hr = product.Insert();
```

자세한 예제는 [CRowset::Insert](../../data/oledb/crowset-insert.md)를 참조하세요.

상태 및 길이 데이터 멤버를 설정하는 방법에 대한 자세한 내용은 [마법사 생성 접근자의 필드 상태 데이터 멤버](../../data/oledb/field-status-data-members-in-wizard-generated-accessors.md)를 참조하세요.

## <a name="deleting-rows-from-rowsets"></a>행 집합에서 행 삭제

[Crowset:: Delete](../../data/oledb/crowset-delete.md) 는 행 집합에서 현재 행을 삭제합니다. 다음 코드 호출 `Delete` 행 집합의 100 번째 행을 제거 하려면:

```cpp
// Instantiate a rowset based on the user record class
CTable<CAccessor<CProductAccessor>> product;
CSession session;

// Open the rowset and move to the 100th row
product.Open(session, "Product", &ps, 1);  // ps is the property set
product.MoveToBookmark(&bookmark, 0);      // Assume that bookmark is set to 100th row

// Delete the row
HRESULT hr = product.Delete();
```

## <a name="immediate-and-deferred-updates"></a>즉시 업데이트 및 지연된 업데이트

별도로 지정 하지 않으면 호출 된 `SetData`, `Insert`, 및 `Delete` 메서드는 데이터 저장소가 즉시 업데이트 합니다. 그러나 소비자가 모든 변경 내용을 로컬 캐시에 저장한 후 다음 업데이트 메서드 중 하나가 호출될 때 데이터 저장소에 전송하도록 업데이트를 연기할 수 있습니다.

- [Crowset:: Update](../../data/oledb/crowset-update.md) 보류 중인 마지막 fetch를 이후 현재 행에 대 한 변경 내용을 모두 전송 또는 `Update` 를 호출 합니다.

- [Crowset:: Updateall](../../data/oledb/crowset-updateall.md) 보류 중인 마지막 fetch를 이후 모든 행에 대 한 변경 내용을 모두 전송 또는 `Update` 를 호출 합니다.

Update update 메서드에서 사용 되는 명령에 대 한 변경의 의미가 특정 및 SQL와 혼동 되지 않습니다 **업데이트할** 명령 (`SetData` SQL 동일 **업데이트** 명령) .

지연 된 업데이트는 예를 들어 일련의 뱅킹 트랜잭션;와 같은 경우 유용 한 트랜잭션이 취소 되 면 마지막 커밋된 후에 일련의 변경 될 때까지 보내지 않습니다 때문에 변경 내용을 취소할 수 있습니다. 또한 공급자는 보다 효율적으로 변경 내용을 하나의 네트워크 호출에 포함할 수 있습니다.

지연 된 업데이트를 지원 하려면 설정 해야 합니다 `DBPROP_IRowsetChange` 에 설명 된 속성과 함께 속성 **업데이트 작업 지원**:

```cpp
pPropSet->AddProperty(DBPROP_IRowsetUpdate, true);
```

호출 하는 경우 `Update` 또는 `UpdateAll`, 메서드는 데이터 저장소에 로컬 캐시에서 변경 내용을 전송 하 고 다음 로컬 캐시를 지웁니다. 있기 때문에 현재 행에 대해서만 변경 내용을 전송 하는 업데이트, 응용 프로그램에서 업데이트 되는 행을 업데이트 하 고 업데이트 하는 경우 계속 추적 해야 합니다. 다음 예제에서는 두 개의 연속 행을 업데이트하는 방법을 보여 줍니다.

```cpp
// Instantiate a rowset based on the user record class
CTable<CAccessor<CProductAccessor>> product;
CSession session;

// Open the rowset and move to the 100th row
product.Open(session, "Product", &ps, 1);  // ps is the property set
product.MoveToBookmark(&bookmark, 0);      // Assume that bookmark is set to 100th row

// Change the values of columns "Name" and "Units in Stock" in the 100th row of the Product table
_tcscpy_s(product.m_ProductName, product.m_sizeOfProductName, _T( "Wick" ) );

product.m_UnitsInStock = 10000;

HRESULT hr = product.SetData();  // No changes made to row 100 yet
product.Update();                 // Update row 100 now

// Change the values of columns "Name" and "Units in Stock" in the 101st row of the Product table
product.MoveNext();

_tcscpy_s(product.m_ProductName, product.m_sizeOfProductName _T( "Wax" ) );

product.m_UnitsInStock = 500;

HRESULT hr = product.SetData();  // No changes made to row 101 yet
product.Update();                 // Update row 101 now
```

보류 중인 변경 내용이 전송 되도록 하려면를 호출 해야 `Update` 다른 행으로 이동 하기 전에 합니다. 그러나 이 작업이 길거나 비효율적인 경우(예: 애플리케이션에서 수백 개의 행을 업데이트해야 하는 경우) `UpdateAll` 을 사용하여 한 번에 모든 행을 업데이트할 수 있습니다.

예를 들어 경우 첫 번째 `Update` 호출을 위의 코드에서 누락 하면 100 행 상태로 유지 됩니다. 변경 되지 않지만 101 행은 변경 됩니다. 이후에 응용 프로그램 해야 호출할 `UpdateAll` 하거나 100 행 및 호출 돌아가 `Update` 업데이트할 행에 대 한 합니다.

마지막으로, 변경 내용을 연기하는 주요 이유는 변경 내용을 취소할 수 있기 때문입니다. [CRowset::Undo](../../data/oledb/crowset-undo.md) 를 호출하면 로컬 변경 캐시의 상태가 보류 중인 변경 전의 데이터 저장소 상태로 롤백됩니다. 것이 중요 한 사실은 `Undo` 되지 않습니다 1 단계 (최신 변경 전의 상태)는 로컬 캐시의 상태를 다시; 아니라 해당 행에 대 한 로컬 캐시를 지웁니다. 또한 `Undo` 현재 행에만 영향을 줍니다.

## <a name="see-also"></a>참고자료

[OLE DB 소비자 템플릿 작업](../../data/oledb/working-with-ole-db-consumer-templates.md)<br/>
[CRowset 클래스](../../data/oledb/crowset-class.md)<br/>
[IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85))<br/>
