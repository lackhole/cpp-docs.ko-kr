---
title: 'MFC: 문서 및 뷰를 이용한 데이터베이스 클래스 사용'
ms.date: 11/04/2016
helpviewer_keywords:
- documents [C++], database applications
- recordsets [C++], documents and views
- CRecordView class, using in database forms
- views [C++], database applications
- forms [C++], database applications
- record views [C++], form-based applications
- document/view architecture [C++], in databases
- database applications [C++], forms
- database classes [C++], MFC
- ODBC recordsets [C++], documents and views
- ODBC [C++], forms
ms.assetid: 83979974-fc63-46ac-b162-e8403a572e2c
ms.openlocfilehash: 78765d17b52889123f13c492699230834decba66
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59026294"
---
# <a name="mfc-using-database-classes-with-documents-and-views"></a>MFC: 문서 및 뷰를 이용한 데이터베이스 클래스 사용

문서/뷰 아키텍처 없이 MFC 데이터베이스 클래스를 사용할 수 있습니다. 이 항목에서는 문서 및 뷰를 사용 하 여 작업을 강조합니다. 설명:

- [폼 기반 응용 프로그램을 작성 하는 방법](#_core_writing_a_form.2d.based_application) 를 사용 하 여를 `CRecordView` 문서에 있는 주 뷰로 개체입니다.

- [문서와 뷰 레코드 집합 개체를 사용 하는 방법을](#_core_using_recordsets_in_documents_and_views)합니다.

- [기타 고려 사항](#_core_other_factors)합니다.

대체를 참조 하세요. [MFC: 문서 및 뷰 하지 않는 데이터베이스 클래스를 사용 하 여](../data/mfc-using-database-classes-without-documents-and-views.md)입니다.

##  <a name="_core_writing_a_form.2d.based_application"></a> 폼 기반 응용 프로그램 작성

대부분의 데이터 액세스 응용 프로그램 폼을 기반으로 합니다. 사용자 인터페이스는 사용자를 검사, 입력, 또는 데이터 편집 컨트롤을 포함 하는 폼 이며 기반 응용 프로그램 폼을 만들려면 클래스를 사용 하 여 `CRecordView`입니다. MFC 응용 프로그램 마법사를 실행 하 고 선택 **ODBC** 클라이언트 형식에는 **데이터베이스 지원** 페이지에서 프로젝트를 사용 하 여 `CRecordView` 뷰 클래스에 대 한 합니다.

폼 기반 응용 프로그램에서 각 레코드 뷰 개체에 대 한 포인터를 저장 한 `CRecordset` 개체입니다. 레코드 집합 및 데이터 원본 간에 데이터를 교환 하는 프레임 워크의 레코드 필드 교환 (RFX) 메커니즘입니다. 대화 상자 데이터 교환 (DDX) 메커니즘 레코드 집합 개체의 필드 데이터 멤버와 폼의 컨트롤 간에 데이터를 교환 합니다. `CRecordView` 또한 기본 제공 명령 처리기 함수 양식의 레코드 탐색에 대 한 합니다.

참조 응용 프로그램 마법사를 사용 하 여 form 기반 응용 프로그램을 만들려면 [폼 기반 MFC 응용 프로그램을 만드는](../mfc/reference/creating-a-forms-based-mfc-application.md) 하 고 [MFC 응용 프로그램 마법사, 데이터베이스 지원](../mfc/reference/database-support-mfc-application-wizard.md)합니다.

폼에 대 한 자세한 내용은 참조 하세요. [레코드 뷰](../data/record-views-mfc-data-access.md)합니다.

##  <a name="_core_using_recordsets_in_documents_and_views"></a> 레코드 집합을 문서 및 뷰를 사용 하 여

많은 간단한 폼 기반 응용 프로그램에 문서를 사용할 필요가 없습니다. 응용 프로그램이 더 복잡 한 문서를 데이터베이스에 대 한 프록시로 사용 하려면 원할 경우 저장 된 `CDatabase` 데이터 원본에 연결 하는 개체입니다. 일반적으로 폼 기반 응용 프로그램 보기에서 레코드 집합 개체에 대 한 포인터를 저장 합니다. 다른 종류의 데이터베이스 응용 프로그램 레코드 집합 저장 및 `CDatabase` 문서에는 개체입니다. 일부의 문서를 사용 하 여 데이터베이스 응용 프로그램의 예는 다음과 같습니다.

- 로컬 컨텍스트에서 레코드 집합에 액세스 하는 경우 만들기는 `CRecordset` 필요에 따라 문서 또는 뷰를 멤버 함수의 로컬 개체입니다.

   함수에서 지역 변수로 레코드 집합 개체를 선언 합니다. 임시 만들고 프레임 워크는 생성자에 NULL을 전달할 `CDatabase` 개체입니다. 대신 전달에 대 한 포인터를 `CDatabase` 개체입니다. 함수 내에서 레코드 집합을 사용 하 고 함수가 종료 될 때 자동으로 제거할 수 있도록 합니다.

   프레임 워크는 레코드 집합에서 반환 되는 정보를 사용 하 여 레코드 집합 생성자에 NULL을 전달 하면 `GetDefaultConnect` 만들려는 멤버 함수는 `CDatabase` 개체를 엽니다. 마법사 구현 `GetDefaultConnect` 있습니다.

- 레코드 집합 문서 수명 중에 액세스 하는 경우 하나 이상의 포함 `CRecordset` 문서에는 개체입니다.

   문서를 초기화할 때 또는 필요에 따라 레코드 집합 개체를 생성 합니다. 이미 존재 하거나 생성 하 고 아직 존재 하지 않는 경우 레코드 집합을 열고 경우 레코드 집합에 대 한 포인터를 반환 하는 함수를 작성할 수 있습니다. 닫기, 삭제, 필요에 따라 레코드 집합을 다시 호출 또는 해당 `Requery` 레코드를 새로 고치려면 멤버 함수입니다.

- 문서의 수명 동안 데이터 소스를 액세스 하는 경우 포함을 `CDatabase` 개체에 대 한 포인터를 저장 또는 `CDatabase` 에 개체.

   `CDatabase` 개체는 데이터 원본에 대 한 연결을 관리 합니다. 개체가 문서 생성 하는 동안 자동으로 생성 되 고 호출 하면 해당 `Open` 문서를 초기화할 때 멤버 함수입니다. 문서에 포인터를 전달 하는 문서 멤버 함수에서 레코드 집합 개체를 생성할 때 `CDatabase` 개체입니다. 이 데이터 원본과 각 레코드 집합을 연결합니다. 데이터베이스 개체는 일반적으로 문서를 닫을 때 소멸 됩니다. 레코드 집합 개체는 함수의 범위를 종료 하는 경우에 일반적으로 제거 됩니다.

##  <a name="_core_other_factors"></a> 다른 요소

폼 기반 응용 프로그램 종종 없는 프레임 워크의 문서 serialization 메커니즘을 사용 하 여 모든 않으므로 제거, 사용 안 함, 또는 교체 해야 할 수는 **새로 만들기** 하 고 **열기** 명령에는 **파일** 메뉴. 문서를 참조 [직렬화 합니다. Serialization vs입니다. 입/출력 데이터베이스](../mfc/serialization-serialization-vs-database-input-output.md)합니다.

확인 하려는 수도 프레임 워크를 지원할 수 있는 많은 사용자 인터페이스 기능을 활용 합니다. 예를 들어, 여러 개 사용할 수 있습니다 `CRecordView` 분할자 창에서 개체 여러 문서 MDI (인터페이스) 자식 창, 및 등 다른 다중 레코드 집합을 엽니다.

보기에 인쇄를 구현 하려는 경우, 폼을 사용 하 여 구현 인지 `CRecordView` 또는 다른 요소입니다. 파생 된 클래스 `CFormView`, `CRecordView` 않습니다 인쇄를 지원 하지 않습니다 하지만 재정의할 수는 `OnPrint` 인쇄할 수 있도록 하려면 멤버 함수입니다. 자세한 내용은 클래스를 참조 하세요 [CFormView](../mfc/reference/cformview-class.md)합니다.

문서 및 뷰를 전혀 사용 하지 않을 수도 있습니다. 이 경우 참조 [MFC: 문서 및 뷰 하지 않는 데이터베이스 클래스를 사용 하 여](../data/mfc-using-database-classes-without-documents-and-views.md)입니다.

## <a name="see-also"></a>참고자료

[MFC 데이터베이스 클래스](../data/mfc-database-classes-odbc-and-dao.md)