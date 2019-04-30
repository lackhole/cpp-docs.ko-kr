---
title: '레코드 집합: 레코드 정렬 (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- sorting data, recordset data
- ODBC recordsets, sorting
- recordsets, sorting
ms.assetid: b40b152e-0a91-452e-be7b-e5bc27f744c7
ms.openlocfilehash: 831f21901186ed0ae010b0f332327eefcba94b51
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62368632"
---
# <a name="recordset-sorting-records-odbc"></a>레코드 집합: 레코드 정렬 (ODBC)

이 항목에서는 MFC ODBC 클래스에 적용됩니다.

이 항목에서는 레코드 집합을 정렬 하는 방법에 설명 합니다. 정렬 기준으로 사용할 하나 이상의 열을 지정할 수 있으며 오름차순 또는 내림차순을 지정할 수 있습니다 (**ASC** 하거나 **DESC**; **ASC** 기본값) 지정 된 각 열에 대 한 합니다. 예를 들어 두 개의 열을 지정 하는 경우 레코드를 먼저 정렬 된 명명 된 첫 번째 열에 및 이라는 두 번째 열입니다. SQL **ORDER BY** 절 정의 정렬 합니다. 프레임 워크가 추가 되는 경우는 **ORDER BY** 레코드 집합의 SQL 절 쿼리, 선택 항목의 순서 지정 절 제어 합니다.

개체를 생성 하지만 호출 하기 전에 레코드 집합의 정렬 순서를 설정 해야 해당 `Open` 멤버 함수 (호출 하기 전에 또는 합니다 `Requery` 기존 레코드 집합에 대 한 멤버 함수 개체 `Open` 멤버 함수 되었습니다 이전 호출).

#### <a name="to-specify-a-sort-order-for-a-recordset-object"></a>레코드 집합 개체에 대 한 정렬 순서를 지정 하려면

1. 새 레코드 집합 개체를 생성 (호출을 준비 하거나 `Requery` 기존에 대 한).

1. 개체의 값을 설정 [m_strSort](../../mfc/reference/crecordset-class.md#m_strsort) 데이터 멤버입니다.

   정렬은 null로 끝나는 문자열입니다. 내용을 포함 합니다 **ORDER BY** 절이 있는데 not 키워드 **ORDER BY**합니다. 예를 들어 사용 합니다.

    ```
    recordset.m_strSort = "LastName DESC, FirstName DESC";
    ```

   not

    ```
    recordset.m_strSort = "ORDER BY LastName DESC, FirstName DESC";
    ```

1. 매개 변수, 필터 및 잠금 모드 등 필요한 다른 옵션을 설정 합니다.

1. 호출 `Open` 새 개체에 대 한 (또는 `Requery` 기존 개체에 대 한).

선택한 레코드를 정렬 된 지정 된 대로 합니다. 예를 들어 마지막 이름을 기준으로 내림차순의 학생 레코드 집합을 정렬 하려면 다음을 수행 합니다.

```cpp
// Construct the recordset
CStudentSet rsStudent( NULL );
// Set the sort
rsStudent.m_strSort = "LastName DESC, FirstName DESC";
// Run the query with the sort in place
rsStudent.Open( );
```

레코드 집합에는 모든 내림차순 정렬 (내림차순) 마지막 이름별 다음 이름으로 학생 레코드를 포함 합니다.

> [!NOTE]
>  사용자 고유의 SQL 문자열을 전달 하 여 레코드 집합의 기본 SQL 문자열을 재정의 하려는 경우 `Open`, 사용자 지정 문자열에 있는 경우 정렬을 설정 하지 마십시오는 **ORDER BY** 절.

## <a name="see-also"></a>참고자료

[레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[레코드 집합 레코드 집합 매개 변수화(ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)<br/>
[레코드 집합 레코드 필터링(ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)