---
title: '레코드 집합: 레코드 필터링 (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- data [MFC], filtering
- recordsets [C++], filtering
- filtering recordsets
- ODBC recordsets [C++], filtering records
- filters [C++], recordset object
ms.assetid: 5c075f37-c837-464d-90c1-d028a9d1c175
ms.openlocfilehash: 050524df840be28d661da89d04b685a44238f88c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397863"
---
# <a name="recordset-filtering-records-odbc"></a>레코드 집합: 레코드 필터링 (ODBC)

이 항목에서는 MFC ODBC 클래스에 적용됩니다.

이 항목에서는 레코드 집합을 필터링 하는 사용할 수 있는 레코드의 특정 하위 집합만 선택 하는 방법에 설명 합니다. 예를 들어, 다음 MATH101 같은 특정 강좌에 클래스 부분에만 선택 하는 것이 좋습니다. 필터는 SQL의 내용으로 정의 된 검색 조건을 **여기서** 절. 프레임 워크가 레코드 집합의 SQL 문에 추가 합니다 **여기서** 절 선택 범위를 제한 합니다.

하지만 호출 하기 전에 개체를 생성 한 후에 레코드 집합 개체의 필터를 설정 해야 해당 `Open` 멤버 함수 (호출 하기 전에 또는 합니다 `Requery` 멤버 함수는 기존 레코드 집합에 대 한 개체 `Open` 멤버 함수에 이미 호출 된).

#### <a name="to-specify-a-filter-for-a-recordset-object"></a>레코드 집합 개체에 대 한 필터를 지정 하려면

1. 새 레코드 집합 개체를 생성 (호출을 준비 하거나 `Requery` 기존 개체에 대 한).

1. 개체의 값을 설정 [m_strFilter](../../mfc/reference/crecordset-class.md#m_strfilter) 데이터 멤버입니다.

   필터는 SQL의 내용이 포함 된 null로 끝나는 문자열로 **위치** 절 있지만 not 키워드 **여기서**합니다. 예를 들어 사용 합니다.

    ```
    m_pSet->m_strFilter = "CourseID = 'MATH101'";
    ```

   not

    ```
    m_pSet->m_strFilter = "WHERE CourseID = 'MATH101'";
    ```

    > [!NOTE]
    >  리터럴 문자열 "MATH101" 위의 단일 큰따옴표를 사용 하 여 표시 됩니다. ODBC SQL 사양에서 작은따옴표는 문자열 리터럴을 나타내는 데 사용 됩니다. 이 상황에서 DBMS의 따옴표 요구 사항에 대 한 ODBC 드라이버 설명서를 확인 합니다. 이 구문에 대해서도 설명 추가이 항목의 끝부분입니다.

1. 정렬 순서, 잠금 모드 또는 매개 변수 등 필요한 다른 옵션을 설정 합니다. 매개 변수를 지정 하는 것은 특히 유용 합니다. 필터를 매개 변수화 하는 방법에 대 한 내용은 [레코드 집합: 레코드 집합 (ODBC)를 매개 변수화](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)합니다.

1. 호출 `Open` 새 개체에 대 한 (또는 `Requery` 이전에 열린된 개체에 대 한).

> [!TIP]
>  레코드를 검색 하기 위한 가장 효율적인 방법은 가능성이 필터에서 매개 변수를 사용 합니다.

> [!TIP]
>  레코드 집합 필터에 대 한 유용 [조인](../../data/odbc/recordset-performing-a-join-odbc.md) 테이블 및 사용에 대 한 [매개 변수](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) 가져오거나 런타임에 계산 된 정보를 기반으로 합니다.

지정한 검색 조건을 충족 하는 레코드만 일부 레코드를 선택 합니다. 예를 들어, 과정 필터를 지정 하려면 위에서 설명한 (변수 가정 `strCourseID` 현재, 예를 들어 "MATH101"로 설정), 다음을 수행 합니다.

```
// Using the recordset pointed to by m_pSet

// Set the filter
m_pSet->m_strFilter = "CourseID = " + strCourseID;

// Run the query with the filter in place
if ( m_pSet->Open( CRecordset::snapshot, NULL, CRecordset::readOnly ) )

// Use the recordset
```

레코드 집합 MATH101에 대 한 모든 클래스 섹션에 대 한 레코드를 포함합니다.

문자열 변수를 사용 하 여 위의 예제에서 필터 문자열을 설정한 어떻게 알 수 있습니다. 일반적인 사용법입니다. 과정 ID에 대 한 리터럴 값 100을 지정 한다고 가정 하지만 다음 코드를 리터럴 값을 사용 하 여 올바르게 필터 문자열을 설정 하는 방법을 보여 줍니다.

```
m_strFilter = "StudentID = '100'";   // correct
```

작은따옴표 문자;의 사용 필터 문자열을 직접 설정 하는 경우에 **되지**:

```
m_strFilter = "StudentID = 100";   // incorrect for some drivers
```

ODBC 사양에 맞는 위의 인용 되지만 일부 Dbms에 다른 따옴표 필요할 수 있습니다. 자세한 내용은 참조 하세요. [SQL: 레코드 집합의 SQL 문 (ODBC) 사용자 지정](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)합니다.

> [!NOTE]
>  사용자 고유의 SQL 문자열을 전달 하 여 레코드 집합의 기본 SQL 문자열을 재정의 하려는 경우 `Open`, 사용자 지정 문자열에 있으면 필터를 설정 하지 않아야는 **여기서** 절. SQL 기본값을 재정의 하는 방법에 대 한 자세한 내용은 참조 하세요. [SQL: 레코드 집합의 SQL 문 (ODBC) 사용자 지정](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)합니다.

## <a name="see-also"></a>참고자료

[레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[레코드 집합 레코드 정렬(ODBC)](../../data/odbc/recordset-sorting-records-odbc.md)<br/>
[레코드 집합 레코드 집합의 레코드 선택 방법(ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)<br/>
[레코드 집합 레코드 집합의 레코드 업데이트 방법(ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)<br/>
[레코드 집합 레코드 잠금(ODBC)](../../data/odbc/recordset-locking-records-odbc.md)