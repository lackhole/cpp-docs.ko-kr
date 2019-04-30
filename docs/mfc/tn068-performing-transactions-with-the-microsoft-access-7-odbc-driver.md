---
title: 'TN068: Microsoft Access 7 ODBC 드라이버를 사용 하 여 트랜잭션 수행'
ms.date: 06/28/2018
f1_keywords:
- vc.data.odbc
helpviewer_keywords:
- TN068 [MFC]
- transactions [MFC], calling BeginTrans
- transactions [MFC], Microsoft Access
ms.assetid: d3f8f5d9-b118-4194-be36-a1aefb630c45
ms.openlocfilehash: 3121587f85c4ea19cc92e39569008b597d24ea58
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62363793"
---
# <a name="tn068-performing-transactions-with-the-microsoft-access-7-odbc-driver"></a>TN068: Microsoft Access 7 ODBC 드라이버를 사용 하 여 트랜잭션 수행

> [!NOTE]
> 다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.

이 이는 MFC ODBC 데이터베이스 클래스와 Microsoft ODBC Desktop Driver Pack 버전 3.0에에서 포함 된 Microsoft Access 7.0 ODBC 드라이버를 사용 하는 경우 트랜잭션을 수행 하는 방법에 설명 합니다.

## <a name="overview"></a>개요

트랜잭션을 수행 하는 데이터베이스 응용 프로그램, 경우에 호출 주의 해야 합니다 `CDatabase::BeginTrans` 고 `CRecordset::Open` 응용 프로그램에서 올바른 순서로 합니다. Microsoft Jet 데이터베이스 엔진을 사용 하 여 Microsoft Access 7.0 드라이버 및 Jet 응용 프로그램에 열린 커서에 있는 모든 데이터베이스에서 트랜잭션을 시작 하지는 필요 합니다. MFC ODBC 데이터베이스 클래스에 대해 열린 커서와 동일 개방적이 고 `CRecordset` 개체입니다.

호출 하기 전에 레코드 집합을 열면 `BeginTrans`, 모든 오류 메시지가 나타나지 않을 수 있습니다. 그러나 모든 레코드 집합 업데이트 사항이 영구적 호출한 후에 응용 프로그램은 `CRecordset::Update`, 및 업데이트는 롤백되지 다시 호출 하 여 `Rollback`입니다. 이 문제를 방지 하려면 `BeginTrans` 첫 번째 레코드 집합을 엽니다.

MFC 커서 commit 및 rollback 동작에 대 한 드라이버 기능을 확인합니다. 클래스 `CDatabase` 는 두 멤버 함수를 제공 `GetCursorCommitBehavior` 하 고 `GetCursorRollbackBehavior`에 열 때 모든 트랜잭션의 효과를 확인할 `CRecordset` 개체입니다. Microsoft Access 7.0 ODBC 드라이버의 경우 이러한 멤버 함수는 다음과 같이 반환 됩니다. `SQL_CB_CLOSE` Access 드라이버 커서 유지를 지원 하지 않기 때문입니다. 따라서 호출 해야 합니다 `CRecordset::Requery` 다음을 `CommitTrans` 또는 `Rollback` 작업 합니다.

호출할 수 없습니다 하나씩 여러 트랜잭션을 수행 해야 할 때 `Requery` 첫 번째 트랜잭션의 후 다음을 시작 합니다. 다음 호출 하기 전에 레코드 집합을 닫아야 `BeginTrans` Jet의 요구 사항을 충족 하기 위해. 이 기술 노트에서는이 상황을 처리 하는 두 가지 방법을 설명 합니다.

- 각 레코드 집합을 닫는 `CommitTrans` 또는 `Rollback` 작업 합니다.

- ODBC API 함수를 사용 하 여 `SQLFreeStmt`입니다.

## <a name="closing-the-recordset-after-each-committrans-or-rollback-operation"></a>각 CommitTrans 또는 롤백 작업 후 레코드 집합을 닫기

트랜잭션을 시작 하기 전에 레코드 집합 개체가 닫혀 있는지를 확인 합니다. 호출한 후 `BeginTrans`, 레코드 집합의 호출 `Open` 멤버 함수입니다. 호출 직후 레코드 집합을 닫고 `CommitTrans` 또는 `Rollback`합니다. 반복적으로 열고 닫는 레코드는 응용 프로그램의 성능이 느려질 수 있습니다 note 합니다.

## <a name="using-sqlfreestmt"></a>SQLFreeStmt를 사용 하 여

ODBC API 함수를 사용할 수도 있습니다 `SQLFreeStmt` 를 명시적으로 트랜잭션을 종료 한 후 커서를 닫습니다. 다른 트랜잭션을 시작, 호출 `BeginTrans` 뒤에 `CRecordset::Requery`입니다. 호출할 때 `SQLFreeStmt`, HSTMT 레코드 집합의 첫 번째 매개 변수로 지정 해야 하 고 *SQL_CLOSE* 두 번째 매개 변수로 합니다. 이 메서드는 결산 잔액과 개시 하는 모든 트랜잭션 시작 레코드 집합 보다 빠릅니다. 다음 코드는이 기술을 구현 하는 방법에 설명 합니다.

```cpp
CMyDatabase db;
db.Open("MYDATASOURCE");
CMyRecordset rs(&db);

// start transaction 1 and
// open the recordset
db.BeginTrans();
rs.Open();

// manipulate data

// end transaction 1
db.CommitTrans(); // or Rollback()

// close the cursor
::SQLFreeStmt(rs.m_hstmt, SQL_CLOSE);

// start transaction 2
db.BeginTrans();
// now get the result set
rs.Requery();

// manipulate data

// end transaction 2
db.CommitTrans();

rs.Close();
db.Close();
```

새 함수를 작성 하는이 기술을 구현 하는 또 다른 방법은 `RequeryWithBeginTrans`를 커밋한 후 다음 트랜잭션이 시작 하는 동안 호출 될 수 있습니다 또는 첫 번째 롤백. 이러한 함수를 작성 하려면 다음 단계를 수행 합니다.

1. 에 대 한 코드를 복사 `CRecordset::Requery( )` 에서 새 함수입니다.

2. 호출 직후에 다음 줄을 추가 `SQLFreeStmt`:

   `m_pDatabase->BeginTrans( );`

이제 트랜잭션의 각 쌍 사이이 함수를 호출할 수 있습니다.

```cpp
// start transaction 1 and
// open the recordset
db.BeginTrans();

rs.Open();

// manipulate data

// end transaction 1
db.CommitTrans();   // or Rollback()

// close the cursor, start new transaction,
// and get the result set
rs.RequeryWithBeginTrans();

// manipulate data

// end transaction 2
db.CommitTrans();   // or Rollback()
```

> [!NOTE]
> 레코드 집합 멤버 변수를 변경 해야 하는 경우이 기술을 사용 하지 마세요 *m_strFilter* 하거나 *m_strSort* 트랜잭션 간의 합니다. 각 레코드 집합을 종료 해야 경우 `CommitTrans` 또는 `Rollback` 작업 합니다.

## <a name="see-also"></a>참고자료

[번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)<br/>
[범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
