---
title: '레코드 집합: 합계 및 다른 집계 결과 (ODBC) 구하기'
ms.date: 11/04/2016
helpviewer_keywords:
- SQL, retrieving aggregate values from recordsets
- recordsets, retrieving SQL aggregate values
- retrieving SQL aggregate values from recordsets
- ODBC recordsets, retrieving SQL aggregate values
- SQL aggregate values
- SQL Server projects, retrieving aggregate values from recordsets
- SQL aggregate values, retrieving from recordsets
ms.assetid: 94500662-22a4-443e-82d7-acbe6eca447b
ms.openlocfilehash: e10f2e1574dae234d98d210784d4a8ddef3bb57e
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59025324"
---
# <a name="recordset-obtaining-sums-and-other-aggregate-results-odbc"></a>레코드 집합: 합계 및 다른 집계 결과 (ODBC) 구하기

이 항목에서는 MFC ODBC 클래스에 적용됩니다.

이 항목에서는 다음을 사용 하는 집계 결과를 얻는 방법을 설명 [SQL](../../data/odbc/sql.md) 키워드:

- **SUM** 숫자 데이터 형식의 열에 있는 값의 합계를 계산 합니다.

- **MIN** 숫자 데이터 형식의 열에서 가장 작은 값을 추출 합니다.

- **최대** 숫자 데이터 형식의 열에서 가장 큰 값을 추출 합니다.

- **AVG** 숫자 데이터 형식의 열에 있는 모든 값의 평균 값을 계산 합니다.

- **개수** 모든 데이터 형식의 열에 있는 레코드의 수를 계산 합니다.

데이터 원본에서 레코드를 추출 하기 보다는 데이터 원본에서 레코드에 대 한 통계 정보를 얻으려면 이러한 SQL 함수를 사용 합니다. 일반적으로 만든 레코드 집합 개로만 이루어진 값을 포함 하는 레코드 (모든 열 집계 경우). (사용 하는 경우 둘 이상의 레코드 수를 **GROUP BY** 절.) 이 값은 SQL 함수에 의해 추출 된 계산의 결과입니다.

> [!TIP]
>  SQL에 추가할 **GROUP BY** 절 (및를 **HAVING** 절)의 끝에 추가 하 여 SQL 문을 `m_strFilter`합니다. 예를 들어:

```
m_strFilter = "sales > 10 GROUP BY SALESPERSON_ID";
```

집계 결과를 얻는 필터링 및 열을 정렬 하 여 사용 하는 레코드 수를 제한할 수 있습니다.

> [!CAUTION]
>  일부 집계 연산자는 집계는 열에서 다른 데이터 형식을 반환 합니다.

- **합계** 및 **AVG** 다음 더 큰 데이터 형식을 반환할 수 있습니다 (예를 들어, 사용 하 여 호출 `int` 반환 **긴** 또는 **double**).

- **개수** 일반적으로 반환 **긴** 대상 열 형식에 관계 없이 합니다.

- **최대** 하 고 **MIN** 은 계산 열과 동일한 데이터 형식을 반환 합니다.

     예를 들어를 **클래스 추가** 만들어집니다 `long` `m_lSales` 사용 하 여 대체 해야 할 수 있지만 Sales 열을 수용 하기 위해는 `double m_dblSumSales` 집계 결과 수용 하기 위해 데이터 멤버입니다. 다음 예제를 참조하세요.

#### <a name="to-obtain-an-aggregate-result-for-a-recordset"></a>레코드 집합에 대 한 집계 결과 얻으려면

1. 에 설명 된 대로 레코드 집합을 만듭니다 [MFC ODBC 소비자 추가](../../mfc/reference/adding-an-mfc-odbc-consumer.md) 집계 결과를 얻으려면 원하는 열을 포함 합니다.

1. 수정 된 [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) 레코드 집합에 대 한 함수입니다. 열 이름을 나타내는 문자열 (두 번째 인수는 [RFX](../../data/odbc/record-field-exchange-using-rfx.md) 함수 호출) 열에 집계 함수를 나타내는 문자열을 사용 하 여 합니다. 예를 들어 바꿉니다.

    ```
    RFX_Long(pFX, "Sales", m_lSales);
    ```

     다음으로 바꿉니다.

    ```
    RFX_Double(pFX, "Sum(Sales)", m_dblSumSales)
    ```

1. 레코드 집합을 엽니다. 집계 작업의 결과에 그대로 `m_dblSumSales`합니다.

> [!NOTE]
>  마법사에는 실제로 Hungarian 접두사 없이 데이터 멤버 이름을 할당합니다. 예를 들어, 마법사에서 산출 `m_Sales` Sales 열에 대 한 보다는 `m_lSales` 이전 예제에 대 한 예시입니다.

사용 중인 경우는 [CRecordView](../../mfc/reference/crecordview-class.md) 데이터를 보려면 클래스, 새 데이터 멤버 값을 표시할 DDX 함수 호출을 변경 해야 합니다.이 경우에서 변경:

```
DDX_FieldText(pDX, IDC_SUMSALES, m_pSet->m_lSales, m_pSet);
```

대상:

```
DDX_FieldText(pDX, IDC_SUMSALES, m_pSet->m_dblSumSales, m_pSet);
```

## <a name="see-also"></a>참고자료

[레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[레코드 집합: 레코드 집합 선택 (ODBC)를 기록 하는 방법](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)