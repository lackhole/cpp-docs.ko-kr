---
title: '레코드 필드 교환: 마법사 코드 사용'
ms.date: 11/04/2016
helpviewer_keywords:
- DoFieldExchange method, overriding
- Unicode, with database classes
- field data members, declaring
- RFX (ODBC), wizard code
- RFX (ODBC), implementing
- field data members
- ODBC, RFX
- m_nParams data member, initializing
- m_nFields data member
- m_nParams data member
- overriding, DoFieldExchange
- m_nFields data member, initializing
ms.assetid: f00d882a-ff1b-4a75-9717-98d8762bb237
ms.openlocfilehash: 82f0d946cac3429150250e2df5d1bfd674ec30ee
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59041295"
---
# <a name="record-field-exchange-working-with-the-wizard-code"></a>레코드 필드 교환: 마법사 코드 사용

이 항목에서는 코드를 설명 하는 MFC 응용 프로그램 마법사 및 **클래스 추가** (에 설명 된 대로 [MFC ODBC 소비자 추가](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) RFX와 코드를 수정 하려는 방법을 지원 하기 위해 작성 합니다.

> [!NOTE]
>  이 항목에서 파생 된 클래스에 적용 됩니다 `CRecordset` 의 대량 행 페치 구현 되지 않았습니다. 대량 행 페치를 사용 하는 경우 대량 레코드 필드 교환 (대량 RFX) 구현 됩니다. 대량 RFX RFX와 비슷합니다. 차이점을 이해 하려면 [레코드 집합: (ODBC) 대량 레코드 페치](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)합니다.

MFC 응용 프로그램 마법사를 사용 하 여 레코드 집합 클래스를 만들 때 또는 **클래스 추가**, 마법사는 데이터 원본에 따라 테이블 및 열 선택 마법사에서 수행한 다음 RFX와 관련 된 요소를 씁니다.

- 레코드 집합 클래스에서 레코드 집합 필드 데이터 멤버의 선언

- 재정 `CRecordset::DoFieldExchange`

- 레코드 집합 클래스 생성자의 레코드 집합 필드 데이터 멤버의 초기화

##  <a name="_core_the_field_data_member_declarations"></a> 필드 데이터 멤버 선언

마법사 클래스에 대해 다음과 유사한.h 파일에서 레코드 집합 클래스 선언을 작성할 `CSections`:

```cpp
class CSections : public CRecordset
{
public:
   CSections(CDatabase* pDatabase = NULL);
   DECLARE_DYNAMIC(CSections)

// Field/Param Data
   CString   m_strCourseID;
   CString   m_strInstructorID;
   CString   m_strRoomNo;
   CString   m_strSchedule;
   CString   m_strSectionNo;

// Overrides
   // Wizard generated virtual function overrides
   protected:
   virtual CString GetDefaultConnect();  // Default connection string
   virtual CString GetDefaultSQL();      // Default SQL for Recordset
   virtual void DoFieldExchange(CFieldExchange* pFX);  // RFX support

// Implementation
#ifdef _DEBUG
   virtual void AssertValid() const;
   virtual void Dump(CDumpContext& dc) const;
#endif

};
```

매개 변수 데이터 멤버 또는 직접 바인딩할 수 있는 새 필드 데이터 멤버를 추가 하는 경우 마법사에서 생성 된 후 추가 합니다.

또한 마법사를 재정의 하는 공지를 `DoFieldExchange` 클래스의 멤버 함수 `CRecordset`합니다.

##  <a name="_core_the_dofieldexchange_override"></a> DoFieldExchange 재정

[DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) 는 RFX의 핵심입니다. 프레임 워크 호출 `DoFieldExchange` 든 지 데이터 원본에 레코드 집합 또는 레코드 집합에 데이터 원본에서 데이터를 이동 해야 합니다. `DoFieldExchange` 또한 지원에 대 한 정보를 가져오는 필드를 통해 데이터 멤버를 [IsFieldDirty](../../mfc/reference/crecordset-class.md#isfielddirty) 및 [IsFieldNull](../../mfc/reference/crecordset-class.md#isfieldnull) 멤버 함수입니다.

다음 `DoFieldExchange` 에 대 한 재정의는 `CSections` 클래스입니다. 마법사는 레코드 집합 클래스에 대 한.cpp 파일에서 함수를 씁니다.

```cpp
void CSections::DoFieldExchange(CFieldExchange* pFX)
{
   pFX->SetFieldType(CFieldExchange::outputColumn);
   RFX_Text(pFX, "CourseID", m_strCourseID);
   RFX_Text(pFX, "InstructorID", m_strInstructorID);
   RFX_Text(pFX, "RoomNo", m_strRoomNo);
   RFX_Text(pFX, "Schedule", m_strSchedule);
   RFX_Text(pFX, "SectionNo", m_strSectionNo);
}
```

함수의 다음 주요 기능을 확인 합니다.

- 이 섹션에서는 함수 필드 맵을 라고 합니다.

- 에 대 한 호출 `CFieldExchange::SetFieldType`을 통해는 `pFX` 포인터입니다. 이 호출의 끝에 all RFX 함수 호출 하는 지정 `DoFieldExchange` 또는 다음 호출을 `SetFieldType` 출력 열입니다. 자세한 내용은 [CFieldExchange::SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype)합니다.

- 몇 번 호출 하는 `RFX_Text` 전역 함수-필드 데이터 멤버에 하나씩 (모두 `CString` 예에서 변수). 이러한 호출은 데이터 원본에 열 이름 및 필드 데이터 멤버 간의 관계를 지정 합니다. RFX 함수에는 실제 데이터 전송을 수행합니다. 클래스 라이브러리는 모든 일반 데이터 형식에 대해 RFX 함수를 제공합니다. RFX 함수에 대 한 자세한 내용은 참조 하세요. [레코드 필드 교환: RFX 함수를 사용 하 여](../../data/odbc/record-field-exchange-using-the-rfx-functions.md)입니다.

    > [!NOTE]
    >  결과 집합의 열 순서는 RFX 함수 호출의 순서와 일치 해야 `DoFieldExchange`합니다.

- 합니다 `pFX` 에 대 한 포인터를 [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) 프레임 워크를 호출할 때 전달 되는 개체 `DoFieldExchange`합니다. 합니다 `CFieldExchange` 작업을 지정 하는 개체는 `DoFieldExchange` 방향 전송 및 기타 컨텍스트 정보를 수행 하는 것입니다.

##  <a name="_core_the_recordset_constructor"></a> 레코드 집합 생성자

마법사에서 작성 하는 레코드 집합 생성자 RFX와 관련 된 두 가지를 포함 합니다.

- 각 필드 데이터 멤버에 대 한 초기화

- 초기화 된 [m_nFields](../../mfc/reference/crecordset-class.md#m_nfields) 필드 데이터 멤버의 수를 포함 하는 데이터 멤버

에 대 한 생성자는 `CSections` 레코드 집합 예제는 다음과 같습니다.

```cpp
CSections::CSections(CDatabase* pdb)
   : CRecordset(pdb)
{
   m_strCourseID = "";
   m_strInstructorID = "";
   m_strRoomNo = "";
   m_strSchedule = "";
   m_strSectionNo = "";
   m_nFields = 5;
}
```

> [!NOTE]
>  새 열을 동적으로 바인딩하는 경우 마찬가지로 수동으로 필드 데이터 멤버 추가 하는 경우 증분 해야 `m_nFields`합니다. 와 같은 다른 코드 줄을 추가 하 여이 수행 합니다.

```cpp
m_nFields += 3;
```

세 가지 새 필드 추가 대 한 코드입니다. 매개 변수 데이터 멤버를 추가 하는 경우 초기화 해야 합니다 [m_nParams](../../mfc/reference/crecordset-class.md#m_nparams) 매개 변수 데이터 멤버의 수를 포함 하는 데이터 멤버입니다. 배치는 `m_nParams` 초기화는 괄호 밖에 있습니다.

## <a name="see-also"></a>참고자료

[RFX](../../data/odbc/record-field-exchange-rfx.md)