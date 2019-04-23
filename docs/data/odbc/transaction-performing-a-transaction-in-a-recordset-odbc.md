---
title: '트랜잭션: 레코드 집합 (ODBC)에서 트랜잭션 수행'
ms.date: 11/04/2016
helpviewer_keywords:
- transactions, updating recordsets
ms.assetid: cf1d6b48-7fb8-4903-84f7-a1822054534d
ms.openlocfilehash: 9e06d61d3d86233e136b0b3fe78f149a6778649b
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59035243"
---
# <a name="transaction-performing-a-transaction-in-a-recordset-odbc"></a>트랜잭션: 레코드 집합 (ODBC)에서 트랜잭션 수행

이 항목에서는 레코드 집합에서 트랜잭션을 수행 하는 방법에 설명 합니다.

> [!NOTE]
>  트랜잭션의 수준이 하나만 지원 됩니다. 트랜잭션을 중첩할 수 없습니다.

#### <a name="to-perform-a-transaction-in-a-recordset"></a>레코드 집합에서 트랜잭션을 수행 하려면

1. 호출 된 `CDatabase` 개체의 `BeginTrans` 멤버 함수입니다.

1. 하지 대량 행 페치를 구현한 경우 호출 합니다 `AddNew/Update`, `Edit/Update`, 및 `Delete` 필요한 횟수 만큼 동일한 데이터베이스의 하나 이상의 레코드 집합 개체의 멤버 함수입니다. 자세한 내용은 참조 하세요. [레코드 집합: 추가, 업데이트 및 삭제 (ODBC) 레코드](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)합니다. 대량 행 페치를 구현한 경우 데이터 소스를 업데이트 하는 고유한 함수를 작성 해야 합니다.

1. 마지막으로 호출 합니다 `CDatabase` 개체의 `CommitTrans` 멤버 함수입니다. 업데이트 중 하나에서 오류가 발생할 경우 변경 내용을 취소 하려면 호출 해당 `Rollback` 멤버 함수입니다.

다음 예제에서는 학생이 등록 된 모든 클래스에서 제거 학교 등록 데이터베이스에서 학생의 등록을 삭제 하려면 두 개의 레코드 집합을 사용 합니다. 때문에 `Delete` 레코드 집합 모두에서 호출 성공 해야 하며, 트랜잭션이 필요 합니다. 예제에 있다고 가정 `m_dbStudentReg`, 형식 멤버 변수의 `CDatabase` 데이터 원본 및 레코드 집합 클래스에 이미 연결 되어 `CEnrollmentSet` 및 `CStudentSet`합니다. `strStudentID` 변수에 사용자에서 가져온 값이 포함 됩니다.

```
BOOL CEnrollDoc::RemoveStudent( CString strStudentID )
{
    // remove student from all the classes
    // the student is enrolled in

    if ( !m_dbStudentReg.BeginTrans( ) )
        return FALSE;

    CEnrollmentSet rsEnrollmentSet(&m_dbStudentReg);
    rsEnrollmentSet.m_strFilter = "StudentID = " + strStudentID;

    if ( !rsEnrollmentSet.Open(CRecordset::dynaset) )
        return FALSE;

    CStudentSet rsStudentSet(&m_dbStudentReg);
    rsStudentSet.m_strFilter = "StudentID = " + strStudentID;

    if ( !rsStudentSet.Open(CRecordset::dynaset) )
        return FALSE;

    TRY
    {
        while ( !rsEnrollmentSet.IsEOF( ) )
        {
            rsEnrollmentSet.Delete( );
            rsEnrollmentSet.MoveNext( );
        }

        // delete the student record
        rsStudentSet.Delete( );

        m_dbStudentReg.CommitTrans( );
    }

    CATCH_ALL(e)
    {
        m_dbStudentReg.Rollback( );
        return FALSE;
    }
    END_CATCH_ALL

    rsEnrollmentSet.Close( );
    rsStudentSet.Close( );

    return TRUE;

}
```

> [!NOTE]
>  호출 `BeginTrans` 호출 하지 않고 다시 `CommitTrans` 또는 `Rollback` 오류가 발생 합니다.

## <a name="see-also"></a>참고자료

[트랜잭션(ODBC)](../../data/odbc/transaction-odbc.md)<br/>
[트랜잭션: 트랜잭션이 업데이트 (ODBC)에 미치는 영향](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)<br/>
[CDatabase 클래스](../../mfc/reference/cdatabase-class.md)<br/>
[CRecordset 클래스](../../mfc/reference/crecordset-class.md)