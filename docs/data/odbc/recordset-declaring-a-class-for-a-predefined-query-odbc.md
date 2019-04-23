---
title: '레코드 집합: 미리 정의 된 쿼리 (ODBC)에 대 한 클래스 선언'
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC recordsets, queries
- predefined queries and recordsets
- stored procedures, and recordsets
- recordsets, predefined queries
- recordsets, stored procedures
ms.assetid: d27c4df9-dad2-4484-ba72-92ab0c8ff928
ms.openlocfilehash: d4ae9f21c4bd53a8050d6f8c3765bb9823d077ba
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59026529"
---
# <a name="recordset-declaring-a-class-for-a-predefined-query-odbc"></a>레코드 집합: 미리 정의 된 쿼리 (ODBC)에 대 한 클래스 선언

이 항목에서는 MFC ODBC 클래스에 적용됩니다.

이 항목에서는 (Microsoft SQL Server와 같이 저장된 프로시저를 라고도 함)는 미리 정의 된 쿼리에 대 한 레코드 집합 클래스를 만드는 방법에 설명 합니다.

> [!NOTE]
>  이 항목에서 파생 된 개체에 적용 됩니다 `CRecordset` 의 대량 행 페치 구현 되지 않았습니다. 대량 행 페치를 구현 하는 경우 프로세스 매우 비슷합니다. 대량 행 페치를 구현 하는 레코드 집합 및 하지 않는 차이점을 이해 하려면 [레코드 집합: (ODBC) 대량 레코드 페치](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)합니다.

일부 Dbms (데이터베이스 관리 시스템)를 사용 하면 미리 정의 된 쿼리를 만들고 함수 처럼 프로그램에서 호출할 수 있습니다. 쿼리 이름이, 매개 변수를 사용할 수 있습니다 및 레코드를 반환할 수 있습니다. 이 항목의 절차에는 레코드를 반환 합니다 (및 매개 변수를 받기도) 하는 미리 정의 된 쿼리를 호출 하는 방법을 설명 합니다.

데이터베이스 클래스는 미리 정의 된 쿼리를 업데이트 하는 것을 지원 하지 않습니다. 다이너셋 미리 정의 된 쿼리를 스냅숏 미리 정의 된 쿼리 간의 차이점 updateability 있지만 다른 사용자 (또는 프로그램의 다른 레코드 집합)가 변경 레코드 집합에 표시 되는지 아닙니다.

> [!TIP]
>  레코드를 반환 하지 않는 한 미리 정의 된 쿼리를 호출 하는 레코드 집합이 필요가 없습니다. 아래 설명 된 대로 SQL 문 준비 하지만 호출 하 여 실행 합니다 `CDatabase` 멤버 함수 [ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql)합니다.

호출 하는 미리 정의 된 쿼리를 관리 하기 위한 단일 레코드 집합 클래스를 만들 수 있지만 해야 할 작업의 일부 사용자가 직접. 마법사는이 용도로 클래스를 만들기를 지원 하지 않습니다.

#### <a name="to-create-a-class-for-calling-a-predefined-query-stored-procedure"></a>미리 정의 된 쿼리를 호출 하기 위한 클래스를 만들려면 (저장 프로시저)

1. 사용 합니다 [MFC ODBC 소비자 마법사](../../mfc/reference/adding-an-mfc-odbc-consumer.md) 에서 **클래스 추가** 쿼리에서 반환 되는 대부분의 열을 포함 테이블에 대 한 레코드 집합 클래스를 만듭니다. 이렇게 하면 시작할 수 있습니다.

1. 쿼리는 반환 되지만 마법사를 만들지 않고 모든 테이블의 모든 열에 대 한 필드 데이터 멤버를 수동으로 추가 합니다.

   예를 들어 쿼리에서 세 개의 열에서 두 개의 추가 테이블을 반환 하는 경우 (적절 한 데이터 형식)의 6 개 필드 데이터 멤버 클래스에 추가 합니다.

1. 수동으로 추가 [RFX](../../data/odbc/record-field-exchange-rfx.md) 함수에서 호출 합니다 [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) 하나 각 데이터 형식에 해당 하는 클래스의 멤버 함수는 필드 데이터 멤버를 추가 합니다.

    ```cpp
    Immediately before these RFX calls, call <MSHelp:link keywords="_mfc_CFieldExchange.3a3a.SetFieldType" TABINDEX="0">SetFieldType</MSHelp:link>, as shown here:
    pFX->SetFieldType( CFieldExchange::outputColumn );
    ```

    > [!NOTE]
    >  데이터 형식 및 설정 결과에 반환 하는 열의 순서를 알고 있어야 합니다. RFX 함수 순서 호출 `DoFieldExchange` 결과 집합 열 순서와 일치 해야 합니다.

1. 레코드 집합 클래스 생성자에 새 필드 데이터 멤버의 초기화를 수동으로 추가 합니다.

   또한 초기화 값을 증가 시켜야 합니다 [m_nFields](../../mfc/reference/crecordset-class.md#m_nfields) 데이터 멤버입니다. 마법사를 초기화 하는 쓰지만 필드 데이터 멤버를 추가 다룹니다. 예를 들어:

    ```cpp
    m_nFields += 6;
    ```

   일부 데이터 형식에서 초기화 되지 않습니다 여기서 예를 들어 `CLongBinary` 또는 바이트 배열입니다.

1. 쿼리 매개 변수를 사용할 경우 각 매개 변수, 각각에 대해 RFX 함수 호출 및 각 초기화에 대 한 매개 변수 데이터 멤버를 추가 합니다.

1. 값을 증가 시켜야 `m_nParams` 수행한 것 처럼 각 매개 변수를 추가 `m_nFields` 에 대 한이 절차의 4 단계에서 필드를 추가 합니다. 자세한 내용은 참조 하세요. [레코드 집합: 레코드 집합 (ODBC)를 매개 변수화](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)합니다.

1. 다음 양식 사용 하 여 SQL 문을 문자열을 수동으로 작성 합니다.

    ```
    {CALL proc-name [(? [, ?]...)]}
    ```

   여기서 **호출** 은 ODBC 키워드를 **proc 이름이** 은 알려진 데이터 원본에서 쿼리 이름 및 "?" 항목은 컨트롤 (있는 경우) 런타임 시 레코드 집합에를 입력 매개 변수 값에 대 한 자리 표시자 . 다음 예제에서는 하나의 매개 변수에 대 한 자리 표시자를 준비합니다.

    ```
    CString mySQL = "{CALL Delinquent_Accts (?)}";
    ```

1. 레코드 집합 열리는 코드에서 값을 설정할 레코드 집합의 매개 변수 데이터 멤버 및 호출을 `Open` 멤버 함수에 대 한 SQL 문자열을 전달 합니다 *lpszSQL* 매개 변수입니다. 대신, 반환 하는 문자열을 대체 하거나는 `GetDefaultSQL` 클래스 멤버 함수입니다.

다음 예제에서는 라는 미리 정의 된 쿼리를 호출 하는 절차를 보여 줍니다. `Delinquent_Accts`, 판매 지역 수에 대 한 매개 변수를 사용 하는 합니다. 이 쿼리는 3 개의 열을 반환 합니다. `Acct_No`, `L_Name`, `Phone`합니다. Customers 테이블에서 모든 열이 됩니다.

다음 레코드 집합은 쿼리에서 반환 및 매개 변수는 판매 구역 런타임에 요청 번호 열에 대 한 필드 데이터 멤버를 지정 합니다.

```cpp
class CDelinquents : public CRecordset
{
// Field/Param Data
    LONG m_lAcct_No;
    CString m_strL_Name;
    CString m_strPhone;
    LONG m_lDistParam;
    // ...
};
```

마법사를 제외 하 고 기록 하는 대로이 클래스 선언 되는 `m_lDistParam` 수동으로 추가 된 멤버입니다. 다른 멤버 여기 표시 되지 않습니다.

다음 예제에서 데이터 멤버에 대 한 초기화를 보여 줍니다.는 `CDelinquents` 생성자입니다.

```cpp
CDelinquents::CDelinquents(CDatabase* pdb)
   : CRecordset(pdb)
{
    // Wizard-generated params:
    m_lAcct_No = 0;
    m_strL_Name = "";
    m_strPhone = "";
    m_nFields = 3;
    // User-defined params:
    m_nParams = 1;
    m_lDistParam = 0;
}
```

초기화에 대 한 참고 [m_nFields](../../mfc/reference/crecordset-class.md#m_nfields) 하 고 [m_nParams](../../mfc/reference/crecordset-class.md#m_nparams)합니다. 마법사가 초기화 `m_nFields`; 초기화 `m_nParams`합니다.

다음 예제에서는 RFX 함수에 `CDelinquents::DoFieldExchange`:

```cpp
void CDelinquents::DoFieldExchange(CFieldExchange* pFX)
{
    pFX->SetFieldType(CFieldExchange::outputColumn);
    RFX_Long(pFX, "Acct_No", m_lAcct_No);
    RFX_Text(pFX, "L_Name", m_strL_Name);
    RFX_Text(pFX, "Phone", m_strPhone);
    pFX->SetFieldType(CFieldExchange::param);
    RFX_Long(pFX, "Dist_No", m_lDistParam);
}
```

세 반환 된 열에 대해 RFX 호출 하는 것 외에도이 코드는 런타임에 전달할 매개 변수 바인딩을 관리 합니다. 매개 변수는 키가 지정 된 `Dist_No` (구역 수) 열입니다.

다음 예제에는 SQL 문자열을 설정 하는 방법과 레코드 집합을 사용 하는 방법을 보여 줍니다.

```cpp
// Construct a CDelinquents recordset object
CDelinquents rsDel( NULL );
CString strSQL = "{CALL Delinquent_Accts (?)}"
// Specify a parameter value (obtained earlier from the user)
rsDel.m_lDistParam = lDistrict;
// Open the recordset and run the query
if( rsDel.Open( CRecordset::snapshot, strSQL ) )
    // Use the recordset ...
```

이 코드에서는 스냅숏을 생성 하 고, 사용자 로부터 이전에 가져온 매개 변수를 전달, 미리 정의 된 쿼리를 호출 합니다. 쿼리를 실행 하는 경우 지정 된 판매 지역에 대 한 레코드를 반환 합니다. 각 레코드는 계정 번호, 고객 성 및 고객의 전화 번호에 대 한 열을 포함합니다.

> [!TIP]
>  저장된 프로시저에서 반환 된 값 (출력 매개 변수)를 처리할 수도 있습니다. 자세한 내용 및 예제를 참조 하세요 [CFieldExchange::SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype)합니다.

## <a name="see-also"></a>참고자료

[레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[레코드 집합: (ODBC) 레코드 집합 다시 쿼리](../../data/odbc/recordset-requerying-a-recordset-odbc.md)<br/>
[레코드 집합: 테이블 (ODBC)에 대 한 클래스 선언](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)<br/>
[레코드 집합: 조인 수행 (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)