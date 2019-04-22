---
title: '레코드 집합: 책갈피와 절대 위치 (ODBC)'
ms.date: 11/04/2016
f1_keywords:
- SetAbsolutePosition
helpviewer_keywords:
- CDBVariant class, bookmarks
- absolute positions, ODBC recordsets
- bookmarks, CDBVariant
- bookmarks, ODBC recordsets
- ODBC recordsets, absolute positions
- ODBC recordsets, bookmarks
- cursors [ODBC], absolute position in recordsets
- recordsets, bookmarks
- bookmarks
- SetAbsolutePosition method
- recordsets, absolute positions
- positioning records
- SetBookmark method
- record positioning
- GetBookmark method
- SetAbsolutePosition method, bookmarks
ms.assetid: 189788d6-33c1-41c5-9265-97db2a5d43cc
ms.openlocfilehash: c4a223f01b25b4c321ccfb4f4c03c3c5241381ec
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59023791"
---
# <a name="recordset-bookmarks-and-absolute-positions-odbc"></a>레코드 집합: 책갈피와 절대 위치 (ODBC)

이 항목에서는 MFC ODBC 클래스에 적용됩니다.

레코드 집합을 탐색할 때 특정 레코드를 반환 하는 방법은 해야 합니다. 책갈피와 절대 위치 레코드의 이러한 두 메서드를 제공합니다.

이 항목에 설명 합니다.

- [책갈피를 사용 하는 방법을](#_core_bookmarks_in_mfc_odbc)합니다.

- [절대 위치를 사용 하 여 현재 레코드를 설정 하는 방법을](#_core_absolute_positions_in_mfc_odbc)합니다.

##  <a name="_core_bookmarks_in_mfc_odbc"></a> MFC ODBC의 책갈피

책갈피는 레코드를 고유 하 게 식별합니다. 레코드 집합을 탐색할 때 없습니다 항상 있으므로 의존 하면 레코드의 절대 위치 레코드 집합에서 레코드를 삭제할 수 있습니다. 레코드의 위치를 추적 하기 위해 신뢰할 수 있는 방법은 해당 책갈피를 사용 하는 것입니다. 클래스 `CRecordset` 멤버 함수를 제공 합니다.

- 변수에 저장할 수 있도록 현재 레코드의 책갈피 가져오기 ([GetBookmark](../../mfc/reference/crecordset-class.md#getbookmark)).

- 이전에 변수로 저장 하는 해당 책갈피를 지정 하 여 지정된 된 레코드를 신속 하 게 이동 ([SetBookmark](../../mfc/reference/crecordset-class.md#setbookmark)).

다음 예에서는 현재 레코드를 표시 하 여 나중에 돌아가서 이러한 멤버 함수를 사용 하는 방법을 보여 줍니다.

```cpp
// rs is a CRecordset or
// CRecordset-derived object

CDBVariant varRecordToReturnTo;
rs.GetBookmark( varRecordToReturnTo );

// More code in which you
// move to other records

rs.SetBookmark( varRecordToReturnTo );
```

기본 데이터 형식에서 추출 해야 합니다 [CDBVariant 클래스](../../mfc/reference/cdbvariant-class.md) 개체입니다. 사용 하 여 값을 할당 `GetBookmark` 사용 하 여 해당 책갈피 돌아가서 `SetBookmark`합니다.

> [!NOTE]
>  ODBC 드라이버 및 레코드 집합 형식에 따라 책갈피 지원 되지 않을 수 있습니다. 책갈피를 호출 하 여 지원 되는지 여부를 쉽게 확인할 수 있습니다 [CRecordset::CanBookmark](../../mfc/reference/crecordset-class.md#canbookmark)합니다. 또한 책갈피는 지원 되는 경우 명시적으로 선택 해야를 지정 하 여 구현 하는 `CRecordset::useBookmarks` 옵션을 [crecordset:: Open](../../mfc/reference/crecordset-class.md#open) 멤버 함수입니다. 또한 특정 레코드 집합 작업 후 책갈피의 지를 확인 해야 합니다. 예를 들어 경우 없습니다 `Requery` 레코드 집합과 책갈피 수 이상 유효 하지 않습니다. 호출 [CDatabase::GetBookmarkPersistence](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) 안전 하 게 호출할 수 있는지 여부를 확인 하려면 `SetBookmark`합니다.

##  <a name="_core_absolute_positions_in_mfc_odbc"></a> MFC ODBC의 절대 위치

책갈피 외 클래스 `CRecordset` 서 수 위치를 지정 하 여 현재 레코드를 설정할 수 있습니다. 이 절대 위치 지정 호출 됩니다.

> [!NOTE]
>  절대 위치 앞 으로만 이동 가능한 레코드 집합에서 제공 되지 않습니다. 앞 으로만 이동 가능한 레코드 집합에 대 한 자세한 내용은 참조 하세요. [레코드 집합 (ODBC)](../../data/odbc/recordset-odbc.md)합니다.

절대 위치를 사용 하 여 현재 레코드 포인터를 이동 하려면 호출 [CRecordset::SetAbsolutePosition](../../mfc/reference/crecordset-class.md#setabsoluteposition)합니다. 값을 전달 하는 경우 `SetAbsolutePosition`, 서 수 위치 레코드가 현재 해당 하는 레코드입니다.

> [!NOTE]
>  레코드의 절대 위치는 신뢰할 수 없습니다. 레코드 집합에서 레코드를 삭제 하는 사용자, 모든 후속 레코드의 서 수 위치 변경 합니다. 책갈피는 현재 레코드를 이동 하기 위한 권장된 방법입니다. 자세한 내용은 [MFC ODBC에서 책갈피](#_core_bookmarks_in_mfc_odbc)합니다.

레코드 집합 탐색에 대 한 자세한 내용은 참조 하세요. [레코드 집합: 스크롤 (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)합니다.

## <a name="see-also"></a>참고자료

[레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)