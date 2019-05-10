---
title: 데이터베이스 응용 프로그램을 만드는 작업 시퀀스
ms.date: 11/04/2016
helpviewer_keywords:
- applications [MFC], database
- database applications [MFC]
- database applications [MFC], creating
- MFC, database applications
ms.assetid: 9371da59-8536-43cd-8314-706ad320e2ec
ms.openlocfilehash: efd6b12b186ce0ef1c0caf57f313f6aa50425fec
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62308500"
---
# <a name="sequence-of-operations-for-creating-database-applications"></a>데이터베이스 응용 프로그램을 만드는 작업 시퀀스

다음 표에서 데이터베이스 응용 프로그램에서 역할 및 프레임 워크의 역할을 보여 줍니다.

> [!NOTE]
>  시각적 개체 C++ 환경 및 마법사 지원 하지 않습니다 DAO (하지만 DAO 클래스에 포함 되어 있으며 계속 사용할 수 있습니다). 새 MFC 프로젝트에 대 한 ODBC를 사용 하는 것이 좋습니다. DAO 기존 응용 프로그램 유지 관리에 사용 해야 합니다.

### <a name="creating-database-applications"></a>데이터베이스 응용 프로그램 만들기

|작업|너 해|프레임 워크|
|----------|------------|------------------------|
|MFC ODBC 또는 DAO 클래스를 사용할지 여부를 결정 합니다.|ODBC를 사용 하 여 새 MFC 프로젝트에 대 한 합니다. 기존 응용 프로그램을 유지 하기 위해서만 DAO를 사용 합니다. 자세한 내용은 문서를 참조 [데이터 액세스 프로그래밍](../data/data-access-programming-mfc-atl.md)합니다.|프레임 워크는 데이터베이스 액세스를 지 원하는 클래스를 제공 합니다.|
|데이터베이스 옵션을 사용 하 여 기본 응용 프로그램을 만듭니다.|MFC 응용 프로그램 마법사를 실행 합니다. 데이터베이스 지원 페이지의 옵션을 선택 합니다. 레코드 뷰를 만드는 옵션을 선택한 경우도 지정 합니다.<br /><br />데이터 원본 및 테이블 이름 또는 이름<br />-이름을 쿼리 합니다.|MFC 응용 프로그램 마법사 파일 만들고 필요한 포함을 지정 합니다. 지정할 옵션에 따라 파일 레코드 집합 클래스를 포함할 수 있습니다.|
|데이터베이스 폼 또는 폼을 디자인 합니다.|시각적 개체를 사용 하 여 C++ 대화 상자 편집기 레코드 뷰 클래스에 대해 대화 상자 템플릿 리소스에 컨트롤을 배치 합니다.|MFC 응용 프로그램 마법사를 입력 하는 빈 대화 상자 템플릿 리소스를 만듭니다.|
|필요에 따라 추가 레코드 보기 및 레코드 집합 클래스를 만듭니다.|클래스 및 대화 상자 편집기 디자인 뷰를 만들려면 클래스 뷰를 사용 합니다.|클래스 뷰 새 클래스에 대해 추가 파일을 만듭니다.|
|코드에서 필요에 따라 레코드 집합 개체를 만듭니다. 각 레코드 집합을 사용 하 여 레코드를 조작 하는 중...|레코드 집합에서 파생 된 클래스에 기반한 [CRecordset](../mfc/reference/crecordset-class.md) 마법사를 사용 하 여 합니다.|ODBC 레코드 필드 교환 (RFX)를 사용 하 여 데이터베이스 레코드 집합의 필드 데이터 멤버와 데이터를 교환 하 합니다. 레코드 뷰를 사용 하는 경우 대화 상자 데이터 교환 (DDX) 레코드 집합 및 레코드 뷰 컨트롤 간에 데이터를 교환 합니다.|
|... 또는 만드는 명시적인 [CDatabase](../mfc/reference/cdatabase-class.md) 열려는 각 데이터베이스에 대 한 코드에서.|데이터베이스 개체에 대해 레코드 집합 개체를 기반 합니다.|데이터베이스 개체는 데이터 원본에 대 한 인터페이스를 제공합니다.|
|데이터 열을 레코드 집합을 동적으로 바인딩하십시오.|Odbc에서 바인딩을 관리 하려면 레코드 집합 파생된 클래스에 코드를 추가 합니다. 문서를 참조 [레코드 집합: (ODBC) 데이터 열 동적 바인딩](../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)합니다.||

## <a name="see-also"></a>참고자료

[프레임워크를 기반으로 구축](../mfc/building-on-the-framework.md)<br/>
[MFC 애플리케이션을 빌드하는 작업 시퀀스](../mfc/sequence-of-operations-for-building-mfc-applications.md)<br/>
[OLE 애플리케이션을 만드는 작업 시퀀스](../mfc/sequence-of-operations-for-creating-ole-applications.md)<br/>
[ActiveX 컨트롤을 만드는 작업 시퀀스](../mfc/sequence-of-operations-for-creating-activex-controls.md)
