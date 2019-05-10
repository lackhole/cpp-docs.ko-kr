---
title: '레코드 집합: 스크롤 (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- recordsets [C++], end of
- recordsets [C++], beginning of
- navigation [C++], recordsets
- recordsets [C++], moving to records
- ODBC recordsets, scrolling
- recordsets [C++], navigating
- scrolling [C++], recordsets
- Move method (recordsets)
ms.assetid: f38d2dcb-1e88-4e41-af25-98b00c276be4
ms.openlocfilehash: 5df8151664bd7e726087cb5323c1e4622264ad23
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397724"
---
# <a name="recordset-scrolling-odbc"></a>레코드 집합: 스크롤 (ODBC)

이 항목에서는 MFC ODBC 클래스에 적용됩니다.

레코드 집합을 연 후 필요한 값을 표시할 레코드에 액세스할 수 계산을 수행할 보고서를 생성 및 등입니다. 레코드 집합 내에서 레코드를 이동 하면 스크롤입니다.

이 항목에 설명 합니다.

- [레코드 집합에서 다른 하나의 레코드 스크롤 하는 방법을](#_core_scrolling_from_one_record_to_another)합니다.

- [아래 스크롤 지원 되는 상황과 지원 되지 않습니다](#_core_when_scrolling_is_supported)합니다.

##  <a name="_core_scrolling_from_one_record_to_another"></a> 다른 하나의 레코드 스크롤

클래스 `CRecordset` 제공 된 `Move` 레코드 집합 내에서 스크롤에 대 한 멤버 함수입니다. 이러한 함수는 행 집합에서 현재 레코드를 이동합니다. 대량 행 페치를 구현한 경우는 `Move` 작업 행 집합의 크기에 따라 레코드 집합의 위치를 조정 합니다. 대량 행 페치를 호출 하지 구현 하는 경우는 `Move` 함수는 레코드 집합의 만큼씩 하나의 레코드 때마다 합니다. 대량 행 페치에 대 한 자세한 내용은 참조 하세요. [레코드 집합: (ODBC) 대량 레코드 페치](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)합니다.

> [!NOTE]
>  레코드 집합을 탐색할 때 삭제 된 레코드 건너뛰지 않을 수 있습니다. 자세한 내용은 참조는 [IsDeleted](../../mfc/reference/crecordset-class.md#isdeleted) 멤버 함수입니다.

외에 `Move` 함수를 `CRecordset` 끝 또는 레코드 집합의 시작 부분 미리 스크롤 했는지 여부를 확인 하는 것에 대 한 멤버 함수를 제공 합니다.

스크롤 가능한 레코드 집합 인지를 확인 하려면 호출을 `CanScroll` 멤버 함수입니다.

#### <a name="to-scroll"></a>스크롤

1. 하나의 레코드 또는 행 집합을 전달: 호출 된 [MoveNext](../../mfc/reference/crecordset-class.md#movenext) 멤버 함수입니다.

1. 이전 레코드 또는 행 집합: 호출 된 [MovePrev](../../mfc/reference/crecordset-class.md#moveprev) 멤버 함수입니다.

1. 레코드 집합의 첫 번째 레코드를: 호출 된 [MoveFirst](../../mfc/reference/crecordset-class.md#movefirst) 멤버 함수입니다.

1. 레코드 집합의 마지막 레코드 또는 마지막 행 집합: 호출 된 [MoveLast](../../mfc/reference/crecordset-class.md#movelast) 멤버 함수입니다.

1. *N* 현재 위치를 기준으로 레코드: 호출 된 [이동](../../mfc/reference/crecordset-class.md#move) 멤버 함수입니다.

#### <a name="to-test-for-the-end-or-the-beginning-of-the-recordset"></a>레코드 집합의 시작 이나 끝에 대 한 테스트 하려면

1. 마지막 레코드를 지나서 스크롤 했습니까? 호출 된 [IsEOF](../../mfc/reference/crecordset-class.md#iseof) 멤버 함수입니다.

1. 첫 번째 레코드의 (뒤로 이동) 스크롤 했습니까? 호출 된 [IsBOF](../../mfc/reference/crecordset-class.md#isbof) 멤버 함수입니다.

다음 코드 예제에서는 `IsBOF` 및 `IsEOF` 에 어느 방향에서으로 스크롤 하는 경우 레코드 집합의 한계를 검색 합니다.

```
// Open a recordset; first record is current
CCustSet rsCustSet( NULL );
rsCustSet.Open( );

if( rsCustSet.IsBOF( ) )
    return;
    // The recordset is empty

// Scroll to the end of the recordset, past
// the last record, so no record is current
while ( !rsCustSet.IsEOF( ) )
    rsCustSet.MoveNext( );

// Move to the last record
rsCustSet.MoveLast( );

// Scroll to beginning of the recordset, before
// the first record, so no record is current
while( !rsCustSet.IsBOF( ) )
    rsCustSet.MovePrev( );

// First record is current again
rsCustSet.MoveFirst( );
```

`IsEOF` 마지막 레코드를 지난 레코드 집합이 있을 경우 0이 아닌 값을 반환 합니다. `IsBOF` 첫 번째 레코드의 모든 레코드) (이전 레코드 집합이 있을 경우 0이 아닌 값을 반환 합니다. 두 경우 모두에서 작동 하도록 현재 레코드가 있습니다. 호출 하는 경우 `MovePrev` 때 `IsBOF` 이미 TRUE 인지 호출 `MoveNext` 때 `IsEOF` 이 이미 true 인 경우 throw 하는 프레임 워크는 `CDBException`합니다. 사용할 수도 있습니다 `IsBOF` 고 `IsEOF` 빈 레코드 집합에 대 한 확인 합니다.

레코드 집합 탐색에 대 한 자세한 내용은 참조 하세요. [레코드 집합: 책갈피와 절대 위치 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)합니다.

##  <a name="_core_when_scrolling_is_supported"></a> 스크롤이 지원 되는

원래 SQL만 정방향 스크롤을 제공 하지만 ODBC 스크롤 기능을 확장 합니다. 스크롤 하는 것에 대 한 지원의 사용 가능한 수준 드라이버의 ODBC API 적합성 수준으로 응용 프로그램이 작동 하는 ODBC 드라이버에 따라 달라 집니다 ODBC 커서 라이브러리를 메모리로 로드 되었는지 여부 및 합니다. 자세한 내용은 [ODBC](../../data/odbc/odbc-basics.md) 고 [ODBC: ODBC 커서 라이브러리](../../data/odbc/odbc-the-odbc-cursor-library.md)합니다.

> [!TIP]
>  커서 라이브러리 사용 되는지 여부를 제어할 수 있습니다. 참조 된 *bUseCursorLib* 하 고 *dwOptions* 매개 변수를 [cdatabase:: Open](../../mfc/reference/cdatabase-class.md#open)합니다.

> [!NOTE]
>  MFC DAO 클래스와 달리 MFC ODBC 클래스의 집합을 하지 않습니다 `Find` 지정 된 조건을 충족 하는 다음 (또는 이전) 레코드 찾기에 대해 작동 합니다.

## <a name="see-also"></a>참고자료

[레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[CRecordset::CanScroll](../../mfc/reference/crecordset-class.md#canscroll)<br/>
[CRecordset::CheckRowsetError](../../mfc/reference/crecordset-class.md#checkrowseterror)<br/>
[레코드 집합 레코드 필터링(ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)