---
title: '레코드 집합: 아키텍처 (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- recordsets, data members
- field data members, recordset architecture
- field data members
- m_nParams data member, recordsets
- recordsets, architecture
- parameter data members in recordsets
- m_nFields data member
- ODBC recordsets, architecture
- m_nParams data member
- m_nFields data member, recordsets
ms.assetid: 47555ddb-11be-4b9e-9b9a-f2931764d298
ms.openlocfilehash: 5904a69f81dd1fbf22171a46040da5d4f5511588
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59039652"
---
# <a name="recordset-architecture-odbc"></a>레코드 집합: 아키텍처 (ODBC)

이 항목에서는 MFC ODBC 클래스에 적용됩니다.

이 항목에서는 레코드 집합 개체의 아키텍처를 구성 하는 데이터 멤버를 설명 합니다.

- [필드 데이터 멤버](#_core_field_data_members)

- [매개 변수 데이터 멤버](#_core_parameter_data_members)

- [M_nFields 및 m_nParams 데이터 멤버를 사용 하 여](#_core_using_m_nfields_and_m_nparams)

> [!NOTE]
>  이 항목에서 파생 된 개체에 적용 됩니다 `CRecordset` 의 대량 행 페치 구현 되지 않았습니다. 대량 행 페치를 구현 하는 경우에 아키텍처가 비슷합니다. 차이점을 이해 하려면 [레코드 집합: (ODBC) 대량 레코드 페치](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)합니다.

##  <a name="_core_a_sample_class"></a> 샘플 클래스

사용 하는 경우는 [MFC ODBC 소비자 마법사](../../mfc/reference/adding-an-mfc-odbc-consumer.md) 에서 **클래스 추가** 레코드 집합 클래스를 선언 하는 마법사에서 파생 된 `CRecordset`, 결과 클래스에는 다음과 같이 간단한 일반 구조 클래스:

```cpp
class CCourse : public CRecordset
{
public:
   CCourse(CDatabase* pDatabase = NULL);
   ...
   CString m_strCourseID;
   CString m_strCourseTitle;
   CString m_strIDParam;
};
```

클래스의 부분을 마법사 기록 집합이 [데이터 멤버 필드](#_core_field_data_members)합니다. 클래스를 만들 때 하나 이상의 필드 데이터 멤버를 지정 해야 합니다. 샘플과 클래스는 클래스에 매개 변수가 있으면 (데이터 멤버를 사용 하 여 `m_strIDParam`)를 수동으로 추가 해야 [매개 변수 데이터 멤버](#_core_parameter_data_members)합니다. 마법사는 클래스에 추가 매개 변수를 지원 하지 않습니다.

##  <a name="_core_field_data_members"></a> 필드 데이터 멤버

레코드 집합 클래스의 가장 중요 한 멤버는 필드 데이터 멤버입니다. 데이터 원본에서 선택한 각 열에 대 한 클래스는 해당 열에 대 한 적절 한 데이터 형식의 데이터 멤버를 포함 합니다. 예를 들어, 합니다 [샘플 클래스](#_core_a_sample_class) 이 부분에 표시 된 항목의 형식은 모두 두 명의 필드 데이터 멤버에 포함 되어 `CString`라는 `m_strCourseID` 및 `m_strCourseTitle`합니다.

프레임 워크 현재 레코드의 열을 자동으로 바인딩하여 레코드를 레코드 집합을 선택 합니다 (후는 `Open` 호출에서 첫 번째 레코드는 현재) 개체의 필드 데이터 멤버에 있습니다. 즉, 프레임 워크를 레코드 열 내용의 저장할 버퍼로 적절 한 필드 데이터 멤버를 사용 합니다.

사용자가 새 레코드를 스크롤하면 프레임 워크를 사용 하 여 필드 데이터 멤버 현재 레코드를 표시 합니다. 프레임 워크에는 이전 레코드의 값을 대체 필드 데이터 멤버를 새로 고칩니다. 필드 데이터 멤버는 현재 레코드를 업데이트 및 새 레코드를 추가 하는 것에 대 한에 사용 됩니다. 레코드 업데이트 프로세스의 일부로 해당 필드 데이터 멤버 또는 멤버에 직접 값을 할당 하 여 업데이트 값을 지정 합니다.

##  <a name="_core_parameter_data_members"></a> 매개 변수 데이터 멤버

클래스에 매개 변수가 있는지 하나 이상의 매개 변수 데이터 멤버입니다. 매개 변수가 있는 클래스를 사용 하면 쿼리의 기반으로 레코드 집합 정보를 얻거나 런타임 시 계산 수 있습니다.

일반적으로 매개 변수는 다음 예제와 같이 선택 항목을 줄일 수 있습니다. 기반으로 합니다 [샘플 클래스](#_core_a_sample_class) 이 항목의 시작 부분에서 레코드 집합 개체에는 다음 SQL 문을 실행할 수 있습니다.

```sql
SELECT CourseID, CourseTitle FROM Course WHERE CourseID = ?
```

"?"는 런타임 시 제공 하는 매개 변수 값에 대 한 자리 표시자입니다. 레코드 집합을 생성 하는 경우 설정 하 고 해당 `m_strIDParam` MATH101 데이터 멤버, 레코드 집합에 대 한 SQL 문을 적용 됩니다.

```sql
SELECT CourseID, CourseTitle FROM Course WHERE CourseID = MATH101
```

매개 변수 데이터 멤버를 정의 하면 SQL 문자열의 매개 변수에 대 한 프레임 워크를 알립니다. 프레임 워크는 ODBC를 자리 표시자를 대체할 값을 가져올 위치를 알 수 있는 매개 변수를 바인딩합니다. 예제에서는 결과 레코드 집합만 값인 MATH101 CourseID 열을 사용 하 여 Course 테이블에서 레코드를 포함 합니다. 이 레코드의 모든 지정 된 열을 선택 합니다. 많은 매개 변수 (및 자리 표시자)을 지정할 수 있습니다 필요에 따라 합니다.

> [!NOTE]
>  MFC는 매개 변수를 사용 하 여 자체 아무 작업도 수행 하지-특히 텍스트 대체를 수행 하지 않습니다. 대신 ODBC에 알려; 매개 변수를 가져올 위치 ODBC는 데이터를 검색 하 고 필요한 매개 변수화를 수행 합니다.

> [!NOTE]
>  매개 변수의 순서가 중요 합니다. 이 대 한 정보 및 매개 변수에 대 한 자세한 내용은 참조 [레코드 집합: 레코드 집합 (ODBC)를 매개 변수화](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)합니다.

##  <a name="_core_using_m_nfields_and_m_nparams"></a> M_nFields 및 m_nParams를 사용 하 여

마법사 클래스의 생성자에 쓰는 때 초기화 합니다 [m_nFields](../../mfc/reference/crecordset-class.md#m_nfields) 수를 지정 하는 데이터 멤버 [필드 데이터 멤버](#_core_field_data_members) 클래스에서. 추가 하는 경우 [매개 변수](#_core_parameter_data_members) 클래스에 추가 초기화를 [m_nParams](../../mfc/reference/crecordset-class.md#m_nparams) 매개 변수 데이터 멤버의 수를 지정 하는 데이터 멤버입니다. 프레임 워크 데이터 멤버와 함께 작동 하도록 이러한 값을 사용 합니다.

자세한 내용 및 예제를 참조 하세요. [레코드 필드 교환: RFX 사용](../../data/odbc/record-field-exchange-using-rfx.md)합니다.

## <a name="see-also"></a>참고자료

[레코드 집합(ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[레코드 집합: 테이블 (ODBC)에 대 한 클래스 선언](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)<br/>
[RFX(레코드 필드 교환)](../../data/odbc/record-field-exchange-rfx.md)