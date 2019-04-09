---
title: '레코드 집합: 레코드 집합 (ODBC)를 매개 변수화'
ms.date: 11/04/2016
helpviewer_keywords:
- parameterizing recordsets
- ODBC recordsets, parameterizing
- recordsets, parameterizing
- passing parameters, to queries at runtime
ms.assetid: 7d1dfeb6-5ee0-45e2-aacc-63bc52a465cd
ms.openlocfilehash: df67256c54cae3e2adb054d653d3e58bb91dd631
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59026164"
---
# <a name="recordset-parameterizing-a-recordset-odbc"></a>레코드 집합: 레코드 집합 (ODBC)를 매개 변수화

이 항목에서는 MFC ODBC 클래스에 적용됩니다.

하려는 경우가 있습니다 수 런타임에 레코드를 선택할 수 계산 하거나 최종 사용자에서 가져온 정보를 사용 하 여 합니다. 레코드 집합 매개 변수를 통해 목표를 달성할 수 있습니다.

이 항목에 설명 합니다.

- [매개 변수가 있는 레코드 집합의 목적은](#_core_parameterized_recordsets)합니다.

- [레코드 집합 매개 변수화 하려는 시점과 이유](#_core_when_to_use_parameters)합니다.

- [레코드 집합 클래스의 데이터 멤버 매개 변수를 선언 하는 방법을](#_core_parameterizing_your_recordset_class)합니다.

- [레코드 집합 개체에 런타임에 매개 변수 정보를 전달 하는 방법을](#_core_passing_parameter_values_at_run_time)합니다.

##  <a name="_core_parameterized_recordsets"></a> 매개 변수가 있는 레코드 집합

매개 변수가 있는 레코드 집합을 통해 런타임에 매개 변수 정보를 전달할 수 있습니다. 이 두 가지 중요 한 효과가 있습니다.

- 실행 속도가 빨라질 발생할 수 있습니다.

- 사용자에서 가져온 정보나 실행 시 계산 같은 디자인 타임에 사용할 수 없는 정보에 따라 런타임에 쿼리를 작성할 수 있습니다.

호출 하는 경우 `Open` 쿼리를 실행 하려면 레코드 집합 사용 하 여 매개 변수 정보를 완료 하려면 해당 **SQL SELECT** 문입니다. 모든 레코드 집합 매개 변수화 할 수 있습니다.

##  <a name="_core_when_to_use_parameters"></a> 매개 변수를 사용 하는 경우

매개 변수의 일반적인 용도 다음과 같습니다.

- 미리 정의 된 쿼리를 런타임 인수를 전달합니다.

   저장된 프로시저에 매개 변수를 전달할 전체 사용자 지정 ODBC를 지정 해야 합니다 **호출** 문-매개 변수 자리 표시자를 사용 하 여-호출 하는 경우 `Open`, 레코드 집합의 기본 SQL 문을 재정의 합니다. 자세한 내용은 [crecordset:: Open](../../mfc/reference/crecordset-class.md#open) 에 *클래스 라이브러리 참조* 및 [SQL: 레코드 집합의 SQL 문 (ODBC) 사용자 지정](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md) 고 [레코드 집합: 미리 정의 된 쿼리 (ODBC)에 대 한 클래스 선언](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)합니다.

- 다른 매개 변수 정보를 사용 하 여 다양 한 재쿼리를 효율적으로 수행 합니다.

   예를 들어 최종 사용자에 게 학생 등록 데이터베이스에 특정 학생에 대 한 정보를 조회 때마다 지정할 수 있습니다 학생의 이름 또는 ID 사용자에서 가져온 매개 변수로. 그런 다음 호출 하는 경우 레코드 집합의 `Requery` 만 해당 학생의 레코드를 선택 하는 멤버 함수를 쿼리 합니다.

   레코드 집합의 필터 문자열을 저장 `m_strFilter`, 아래와 같습니다.

    ```cpp
    "StudentID = ?"
    ```

   변수에서 학생 ID를 가져오는 `strInputID`합니다. 매개 변수 설정 하면 `strInputID` 나타내는 매개 변수 자리 표시자에 바인딩된 변수 값 (예: 학생 ID 100)는 "?" 필터 문자열에 있습니다.

   매개 변수 값을 다음과 같이 지정 합니다.

    ```cpp
    strInputID = "100";
    ...
    m_strParam = strInputID;
    ```

   이 방식으로 필터 문자열을 설정 하려고 하지 않습니다.

    ```cpp
    m_strFilter = "StudentID = 100";   // 100 is incorrectly quoted
                                       // for some drivers
    ```

   필터 문자열에 따옴표를 올바르게 사용 하는 방법의 자세한 내용은 참조 하세요. [레코드 집합: 레코드 필터링 (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)합니다.

   매개 변수 값이 다르면 새로운 학생 id 레코드 집합 다시 쿼리 해도 될 때마다

   > [!TIP]
   > 매개 변수를 사용 하면 단순히 필터 보다 더 효율적입니다. 데이터베이스 매개 변수가 있는 레코드 집합에 대 한 SQL을 처리 해야 합니다 **선택** 문을 한 번만 합니다. 매개 변수 없이 필터링 된 레코드 집합에 대 한 합니다 **선택** 문을 처리 해야 할 때마다 `Requery` 새 필터 값으로.

필터에 대 한 자세한 내용은 참조 하세요. [레코드 집합: 레코드 필터링 (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)합니다.

##  <a name="_core_parameterizing_your_recordset_class"></a> 레코드 집합 클래스를 매개 변수화

> [!NOTE]
> 이 섹션에서 파생 된 개체에 적용 됩니다 `CRecordset` 의 대량 행 페치 구현 되지 않았습니다. 대량 행 페치를 구현 하는 매개 변수를 사용 하는 경우에 유사한 프로세스가입니다. 자세한 내용은 참조 하세요. [레코드 집합: (ODBC) 대량 레코드 페치](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)합니다.

레코드 집합 클래스를 만들기 전에 필요한 매개 변수, 해당 데이터 형식 이란, 및 레코드 집합을 사용 하는 방법을 결정 합니다.

#### <a name="to-parameterize-a-recordset-class"></a>레코드 집합 클래스를 매개 변수화

1. 실행 합니다 [MFC ODBC 소비자 마법사](../../mfc/reference/adding-an-mfc-odbc-consumer.md) 에서 **클래스 추가** 여 클래스를 만듭니다.

1. 레코드 집합의 열에 대 한 필드 데이터 멤버를 지정 합니다.

1. 마법사 파일 프로젝트에 클래스를 작성,.h 파일이 있는 위치로 이동 후 수동으로 클래스 선언에 하나 이상의 매개 변수 데이터 멤버를 추가 합니다. 추가 다음 예제와 같을 수 있습니다, 스냅숏 클래스의 일부 하도록 쿼리에 응답할 학생 들에에서는 어떤 상급? "

    ```cpp
    class CStudentSet : public CRecordset
    {
    // Field/Param Data
        CString m_strFirstName;
        CString m_strLastName;
        CString m_strStudentID;
        CString m_strGradYear;

        CString m_strGradYrParam;
    };
    ```

   마법사에서 생성 된 필드 데이터 멤버 뒤에 매개 변수 데이터 멤버를 추가 합니다. 규칙을 각 사용자 정의 매개 변수 이름에 "Param" 라는 단어를 추가 하는 것입니다.

1. 수정 된 [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) .cpp 파일에서 멤버 함수 정의 합니다. 클래스에 추가한 각 매개 변수 데이터 멤버에 대해 RFX 함수 호출을 추가 합니다. RFX 함수를 작성 하는 방법에 대 한 내용은 [레코드 필드 교환: RFX 작동 방식](../../data/odbc/record-field-exchange-how-rfx-works.md)합니다. 에 대 한 단일 호출을 사용 하 여 매개 변수에 대해 RFX 호출 앞에 야 합니다.

    ```cpp
    pFX->SetFieldType( CFieldExchange::param );
    // RFX calls for parameter data members
    ```

1. 레코드 집합 클래스의 생성자에서 매개 변수 개수를 증가 `m_nParams`합니다.

   내용은 [레코드 필드 교환: 마법사 코드 사용](../../data/odbc/record-field-exchange-working-with-the-wizard-code.md)합니다.

1. 이 클래스의 레코드 집합 개체를 만드는 코드를 작성 하는 경우는 "?" 교체 매개 변수가 있는 SQL 문 문자열의 각 위치에서 기호 (물음표)입니다.

   런타임 시 "?" 자리 표시자는, 순서 대로 채워집니다, 매개 변수 값으로 전달 합니다. 후 첫 번째 매개 변수 데이터 멤버를 설정 합니다 [SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) 호출할 바뀝니다 첫 번째 "?"는 SQL 문자열에서 두 번째 매개 변수 데이터 멤버 바꿉니다 두 번째"?" 등.

> [!NOTE]
> 매개 변수 순서가 중요: RFX 순서에서 매개 변수에 대 한 호출에 `DoFieldExchange` 함수에는 SQL 문자열에 매개 변수 자리 표시자의 순서와 일치 해야 합니다.

> [!TIP]
> 작업할 가능성이 문자열은 지정한 문자열 (있는 경우)를 클래스에 대 한 [m_strFilter](../../mfc/reference/crecordset-class.md#m_strfilter) 데이터 멤버 이지만 일부 ODBC 드라이버 다른 SQL 절에서 매개 변수를 사용할 수 있습니다.

##  <a name="_core_passing_parameter_values_at_run_time"></a> 런타임에 매개 변수 값 전달

호출 하기 전에 매개 변수 값을 지정 해야 합니다 `Open` (예: 새 레코드 집합 개체) 또는 `Requery` (기존)에 대 한 합니다.

#### <a name="to-pass-parameter-values-to-a-recordset-object-at-run-time"></a>런타임 시 레코드 집합 개체에 매개 변수 값을 전달할

1. 레코드 집합 개체를 생성 합니다.

1. 문자열 또는 문자열 같은 준비는 `m_strFilter` SQL 문 또는 일부를 포함 하는 문자열입니다. 배치 "?" 자리 표시자 위치 매개 변수 정보를 이동 하는 것입니다.

1. 개체의 각 매개 변수 데이터 멤버에는 런타임 매개 변수 값을 할당 합니다.

1. 호출 된 `Open` 멤버 함수 (또는 `Requery`, 기존 레코드 집합에 대 한).

예를 들어, 런타임 시 얻은 정보를 사용 하 여 레코드 집합에 대 한 필터 문자열을 지정 한다고 가정 합니다. 클래스의 레코드 집합을 생성 하는 것으로 가정 `CStudentSet` 이전-라는 `rsStudents` -이제 특정 종류의 학생 정보에 대 한 다시 쿼리 하려는 합니다.

```cpp
// Set up a filter string with
// parameter placeholders
rsStudents.m_strFilter = "GradYear <= ?";

// Obtain or calculate parameter values
// to pass--simply assigned here
CString strGradYear = GetCurrentAcademicYear( );

// Assign the values to parameter data members
rsStudents.m_strGradYrParam = strGradYear;

// Run the query
if( !rsStudents.Requery( ) )
    return FALSE;
```

레코드 집합 레코드는 런타임 매개 변수에서 생성 된 필터는 지정 된 조건을 충족 하는 학생 들에 대 한 레코드를 포함 합니다. 이 경우 레코드 집합 선임 속한 모든 학생에 대 한 레코드를 포함합니다.

> [!NOTE]
>  필요한 경우 매개 변수 데이터 멤버의 값을 Null로 설정할 수 있습니다 사용 하 여 [SetParamNull](../../mfc/reference/crecordset-class.md#setparamnull)합니다. 매개 변수 데이터 멤버인 Null 인지 확인할 마찬가지로 있습니다를 사용 하 여 [IsFieldNull](../../mfc/reference/crecordset-class.md#isfieldnull)합니다.

## <a name="see-also"></a>참고자료

[레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[레코드 집합: 추가, 업데이트 및 삭제할 레코드 (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)<br/>
[레코드 집합: 레코드 집합 선택 (ODBC)를 기록 하는 방법](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)