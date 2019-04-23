---
title: 레코드 뷰  (MFC Data Access)
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], record views
- ODBC recordsets [C++], record views
- databases [C++], record views
- record views [C++]
- forms [C++], data access tasks
ms.assetid: 562122d9-01d8-4284-acf6-ea109ab0408d
ms.openlocfilehash: 199f51f20dd42ee9105b4e09f579c1f48948745f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59040201"
---
# <a name="record-views--mfc-data-access"></a>레코드 뷰  (MFC Data Access)

이 섹션에서는 MFC ODBC 클래스에만 적용 됩니다. OLE DB 레코드 뷰에 대 한 자세한 내용은 [COleDBRecordView](../mfc/reference/coledbrecordview-class.md) 하 고 [사용 하 여 OLE DB 레코드 뷰](../data/oledb/using-ole-db-record-views.md)합니다.

폼 기반 데이터 액세스 응용 프로그램을 지원 하려면 클래스 라이브러리는 클래스를 제공 [CRecordView](../mfc/reference/crecordview-class.md)합니다. 레코드 뷰는 해당 컨트롤의 필드 데이터 멤버에 직접 매핑되는 폼 뷰 개체를 [레코드 집합](../data/odbc/recordset-odbc.md) 개체 (및 데이터 원본에 테이블 또는 쿼리 결과의 해당 열에 간접적으로). 해당 기본 클래스와 마찬가지로 [CFormView](../mfc/reference/cformview-class.md), `CRecordView` 대화 상자 템플릿 리소스를 기반으로 합니다.

## <a name="form-uses"></a>폼 사용

폼은 다음과 같은 여러 데이터 액세스 작업에 유용합니다.

- 데이터 입력

- 데이터의 읽기 전용 검사 수행

- 데이터 업데이트

## <a name="further-reading-about-record-views"></a>레코드 뷰에 대한 추가 자료

아래 항목의 자료는 ODBC 기반 및 DAO 기반 클래스 둘 다에 적용됩니다. ODBC의 경우 `CRecordView`를 사용하고 DAO의 경우에는 `CDaoRecordView`를 사용합니다.

다루는 주제는 다음과 같습니다.

- [레코드 뷰 클래스의 기능](../data/features-of-record-view-classes-mfc-data-access.md)

- [레코드 뷰의 데이터 교환](../data/data-exchange-for-record-views-mfc-data-access.md)

- [레코드 뷰를 사용 하 여 작업에서 역할](../data/your-role-in-working-with-a-record-view-mfc-data-access.md)

- [레코드 뷰 디자인 및 만들기](../data/designing-and-creating-a-record-view-mfc-data-access.md)

- [레코드 뷰 사용](../data/using-a-record-view-mfc-data-access.md)

## <a name="see-also"></a>참고자료

[데이터 액세스 프로그래밍 (MFC/ATL)](../data/data-access-programming-mfc-atl.md)<br/>
[ODBC 드라이버 목록](../data/odbc/odbc-driver-list.md)