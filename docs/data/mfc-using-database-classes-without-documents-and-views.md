---
title: 'MFC: 문서 및 뷰 하지 않는 데이터베이스 클래스 사용'
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC applications [C++], without views
- documents [C++], applications without
- ODBC applications [C++]
- document/view architecture [C++], in databases
- files [C++], MFC
- database classes [C++], MFC
- CRecordView class, using in database applications
- database applications [C++], without views
- database applications [C++], application wizard options
- application wizards [C++], creating database applications
- ODBC [C++], file support in database applications
- ODBC applications [C++], without documents
- database applications [C++], without documents
- user interface [C++], drawing information
ms.assetid: 15bf52d4-91cf-4b1d-8b37-87c3ae70123a
ms.openlocfilehash: ab9946609fa20c4644873a684a754cbc8a41742f
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59024636"
---
# <a name="mfc-using-database-classes-without-documents-and-views"></a>MFC: 문서 및 뷰 하지 않는 데이터베이스 클래스 사용

경우에 따라 데이터베이스 응용 프로그램의 프레임 워크의 문서/뷰 아키텍처를 사용 하지 않을 수 있습니다. 이 항목에 설명 합니다.

- [문서를 사용할 필요가 없습니다 경우](#_core_when_you_don.92.t_need_documents) 문서 serialization 등입니다.

- [응용 프로그램 마법사 옵션](#_core_appwizard_options_for_documents_and_views) 직렬화 하지 않고 응용 프로그램을 지원 하기 위해 문서 관련 **파일** 메뉴와 같은 명령은 **새로 만들기**를 **열기** 를 **저장할**, 및 **다른 이름으로 저장**합니다.

- [최소한의 문서를 사용 하는 응용 프로그램을 사용 하는 방법을](#_core_applications_with_minimal_documents)합니다.

- [문서 없거나 뷰를 사용 하 여 응용 프로그램을 구성 하는 방법을](#_core_applications_with_no_document)합니다.

##  <a name="_core_when_you_don.92.t_need_documents"></a> 문서가 필요 하면 수행 되는 경우

일부 응용 프로그램은 고유한 개념이 문서. 이러한 응용 프로그램이은 일반적으로 파일의 전체 또는 대부분 저장소에서 메모리로 로드와 **파일 열기** 명령입니다. 저장소로 한 번에 업데이트 된 파일을 다시 작성 한 **파일 저장** 또는 **다른 이름으로 저장** 명령입니다. 데이터 파일은 어떤 사용자에 게 표시 합니다.

그러나 응용 프로그램의 일부 범주 문서를 필요 하지 않습니다. 데이터베이스 응용 프로그램은 트랜잭션 측면에서 작동합니다. 응용 프로그램 데이터베이스에서 레코드를 선택 하 고 한 번에 하나씩 종종 사용자에 게 제공 합니다. 어떤 사용자에 게는 일반적으로 단일 현재 레코드를 메모리에만 서버일 수 있습니다.

응용 프로그램 데이터를 저장 하는 것에 대 한 문서를 필요가 없으면, 프레임 워크의 문서/뷰 아키텍처의 일부 또는 전부를 사용 하 여 분배할 수 있습니다. 불필요 한 정도 방법을 선호 하는 방법에 따라 달라 집니다. 수행할 수 있습니다.

- 데이터 원본에 대 한 연결을 저장 하지만 serialization 등 일반 문서 기능은 사용 하지 않습니다 하는 장소로 최소 문서를 사용 합니다. 데이터의 여러 뷰가 필요에 한 번에 업데이트 하는 모든 뷰를 동기화 하 려 할 때 유용 합니다.

- 프레임 창에 그릴 직접 뷰를 사용 하는 대신 사용 합니다. 이 경우 문서를 생략 하 고 프레임 창 개체에 데이터 연결이 나 데이터를 저장 합니다.

##  <a name="_core_appwizard_options_for_documents_and_views"></a> 문서 및 뷰에 대 한 응용 프로그램 마법사 옵션

MFC 응용 프로그램 마법사 몇 가지 옵션이 **데이터베이스 지원을 선택**에 다음 표에 나열 됩니다. MFC 응용 프로그램 마법사를 사용 하 여 응용 프로그램을 만드는 경우 이러한 옵션은 모두 문서 및 뷰를 사용 하 여 응용 프로그램을 생성 합니다. 일부 옵션에는 문서 및 불필요 한 문서 기능을 생략 하는 뷰를 제공 합니다. 자세한 내용은 [MFC 응용 프로그램 마법사, 데이터베이스 지원](../mfc/reference/database-support-mfc-application-wizard.md)합니다.

|옵션|보기|문서|
|------------|----------|--------------|
|**없음**|`CView`에서 파생됩니다.|없는 데이터베이스 지원을 제공합니다. 기본 옵션입니다.<br /><br /> 선택 하는 경우는 **문서/뷰 아키텍처 지원** 옵션을 합니다 [MFC 응용 프로그램 마법사, 응용 프로그램 종류](../mfc/reference/application-type-mfc-application-wizard.md) serialization을 포함 하 여 전체 문서 지원을 받습니다 페이지 및 **새로 만들기** , **오픈**, **저장**, 및 **이름으로 저장** 명령을 합니다 **파일** 메뉴. 참조 [없는 문서를 사용 하 여 응용 프로그램](#_core_applications_with_no_document)합니다.|
|**헤더 파일만**|`CView`에서 파생됩니다.|응용 프로그램에 대 한 기본 수준의 데이터베이스 지원 제공합니다.<br /><br /> Afxdb.h를 포함 되어 있습니다. 연결 라이브러리를 추가 하지만 모든 데이터베이스 관련 클래스를 만들지 않습니다. 레코드 집합을 나중에 만들 하 고 하는 검사 하 고 레코드를 업데이트 하는 데 사용할 수 있습니다.|
|**파일을 지원 하지 않는 데이터베이스 뷰**|파생 `CRecordView`|제공 문서 지원 하지만 serialization 지원 되지 않습니다. 문서는 레코드 집합을 저장 하 고 여러 뷰; 조정 serialization을 지원 하지 않습니다 또는 **새로 만들기**, **열려**를 **저장**, 및 **이름으로 저장** 명령입니다. 참조 [최소한의 문서를 사용 하 여 응용 프로그램](#_core_applications_with_minimal_documents)합니다. 데이터베이스 뷰를 포함 하는 경우 데이터의 원본을 지정 해야 합니다.<br /><br /> 데이터베이스 헤더 파일, 연결 라이브러리, 레코드 보기 및 레코드 집합을 포함합니다. (사용 하 여 응용 프로그램에만 사용할 수는 **문서/뷰 아키텍처 지원** 에서 선택한 옵션을 [MFC 응용 프로그램 마법사, 응용 프로그램 종류](../mfc/reference/application-type-mfc-application-wizard.md) 페이지입니다.)|
|**파일을 지 원하는 데이터베이스 뷰**|파생 `CRecordView`|Serialization을 비롯 한 전체 문서 지원 제공 및 문서 관련 **파일** 메뉴 명령입니다. 일반적으로 데이터베이스 응용 프로그램 당 파일 별로 등 하지 않아도 serialization 대신 레코드 별로에서 작동 합니다. 그러나 serialization에 대 한 특수 사용을 해야 합니다. 참조 [최소한의 문서를 사용 하 여 응용 프로그램](#_core_applications_with_minimal_documents)합니다. 데이터베이스 뷰를 포함 하는 경우 데이터의 원본을 지정 해야 합니다.<br /><br /> 데이터베이스 헤더 파일, 연결 라이브러리, 레코드 보기 및 레코드 집합을 포함합니다. (사용 하 여 응용 프로그램에만 사용할 수는 **문서/뷰 아키텍처 지원** 에서 선택한 옵션을 [MFC 응용 프로그램 마법사, 응용 프로그램 종류](../mfc/reference/application-type-mfc-application-wizard.md) 페이지입니다.)|

Serialization 및 serialization에 대 한 대체 사용에 대 한 대안의 내용은 참조 하세요. [직렬화 합니다. Serialization vs입니다. 입/출력 데이터베이스](../mfc/serialization-serialization-vs-database-input-output.md)합니다.

##  <a name="_core_applications_with_minimal_documents"></a> 최소한의 문서를 사용 하 여 응용 프로그램

MFC 응용 프로그램 마법사에 양식 기반 데이터 액세스 응용 프로그램을 지 원하는 두 가지 옵션이 있습니다. 각 옵션은 만듭니다는 `CRecordView`-문서 및 뷰 클래스를 파생 합니다. 문서에서 떠날 다릅니다.

###  <a name="_core_a_document_without_file_support"></a> 파일을 지원 하지 않는 문서

응용 프로그램 마법사 데이터베이스 옵션을 선택 **데이터베이스 파일을 지원 하지 않는 뷰** 문서 serialization 필요 하지 않습니다. 문서는 다음과 같은 용도로 유용 합니다.

- 저장 하는 편리한 장소는 것을 `CRecordset` 개체입니다.

   이 사용이 일반적인 문서 개념과 비슷합니다: 데이터를 저장 하는 문서 (또는 경우 레코드 집합) 뷰를 문서의 뷰.

- 응용 프로그램 (예: 여러 레코드 뷰) 여러 뷰를 사용 하는 경우 문서 뷰 조정 지원 합니다.

   여러 뷰에 동일한 데이터를 표시 하는 경우 사용할 수 있습니다는 `CDocument::UpdateAllViews` 보기 데이터를 변경 하는 경우 모든 뷰에 대 한 업데이트를 조정 하는 멤버 함수입니다.

일반적으로 간단한 폼 기반 응용 프로그램에 대 한이 옵션을 사용 합니다. 응용 프로그램 마법사를 자동으로 이러한 응용 프로그램에 대 한 편리한 구조를 지원합니다.

###  <a name="_core_a_document_with_file_support"></a> 파일을 지 원하는 문서

응용 프로그램 마법사 데이터베이스 옵션 선택 **데이터베이스 파일을 지 원하는 뷰** 문서와 관련 된 또 다른 용도 설치한 경우 **파일** 메뉴 명령 및 문서 직렬화 합니다. 프로그램의 데이터 액세스 부분을 사용할 수 있습니다 문서 같은 방식에서 설명 된 대로 [파일을 지원 하지 않고 문서](#_core_a_document_without_file_support)합니다. 사용자의 기본 설정 또는 기타 유용한 정보를 저장 하는 직렬화 된 사용자 프로필 문서 읽기 및 쓰기를 예를 들어 문서의 serialization 기능을 사용할 수 있습니다. 자세한 내용은 참조 하세요. [직렬화 합니다. Serialization vs입니다. 입/출력 데이터베이스](../mfc/serialization-serialization-vs-database-input-output.md)합니다.

응용 프로그램 마법사에서이 옵션을 지원 하지만 문서를 serialize 하는 코드를 작성 해야 합니다. 문서 데이터 멤버에 직렬화 된 정보를 저장 합니다.

##  <a name="_core_applications_with_no_document"></a> 문서가 사용 하 여 응용 프로그램

문서 또는 뷰를 사용 하지 않는 응용 프로그램을 작성할 하려는 경우가 있습니다. 문서에 없는 데이터 저장 (같은 `CRecordset` 개체) 프레임 창 클래스 또는 응용 프로그램 클래스. 추가 요구 사항을 응용 프로그램 사용자 인터페이스를 제공 하는 여부에 따라 달라 집니다.

###  <a name="_core_database_support_with_a_user_interface"></a> 사용자 인터페이스를 사용 하 여 데이터베이스 지원

사용자 인터페이스 (이외의 예를 들어 콘솔 명령줄 인터페이스)에 있는 경우 응용 프로그램은 뷰가 아닌 프레임 창의 클라이언트 영역에 직접 그립니다. 이러한 응용 프로그램을 사용 하지 않습니다 `CRecordView`, `CFormView`, 또는 `CDialog` 일반적으로 사용 하지만 해당 기본 사용자 인터페이스에 대 한 `CDialog` 일반 대화 상자에 대 한 합니다.

###  <a name="_core_writing_applications_without_documents"></a> 문서가 없는 응용 프로그램 작성

응용 프로그램 마법사는 문서가 없는 응용 프로그램을 만드는 지원 하지 않으므로, 써야 사용자 고유의 `CWinApp`-클래스를 파생 하 고 필요한 경우 만들 수도 `CFrameWnd` 또는 `CMDIFrameWnd` 클래스입니다. 재정의 `CWinApp::InitInstance` 으로 응용 프로그램 개체를 선언 합니다.

```cpp
CYourNameApp theApp;
```

프레임 워크는 메시지 맵 메커니즘 및 기타 다양 한 기능에 계속 제공 합니다.

###  <a name="_core_database_support_separate_from_the_user_interface"></a> 사용자 인터페이스에서 분리 된 데이터베이스 지원

일부 응용 프로그램에는 사용자 인터페이스 없이 또는 최소한 하나에만 필요합니다. 예를 들어, 작성 하는:

- 중간 데이터 액세스 개체는 다른 응용 프로그램 (클라이언트) 응용 프로그램 및 데이터 원본 간에 데이터의 특수 한 처리에 대 한 호출입니다.

- 다른 또는 계산 않으며 일괄 처리 업데이트를 수행 하는 한 데이터베이스 형식에서 데이터를 이동 하는 응용 프로그램과 같은 사용자의 개입 없이 데이터를 처리 하는 응용 프로그램입니다.

문서가 소유 하기 때문에 합니다 `CRecordset` 개체에 포함 된 데이터 멤버로 저장 하려고 하는 것에 `CWinApp`-응용 프로그램 클래스를 파생 합니다. 대체 항목은 다음과 같습니다.

- 영구 상태로 두지 않는 `CRecordset` 전혀 개체입니다. 레코드 집합 클래스 생성자에 NULL을 전달할 수 있습니다. 이런 경우 프레임 워크를 만들고 임시 `CDatabase` 레코드 집합의 정보를 사용 하 여 `GetDefaultConnect` 멤버 함수입니다. 이것이 가장 가능성이 높은 대안입니다.

- 만들기는 `CRecordset` 전역 변수 개체입니다. 이 변수에서 동적으로 만든 레코드 집합 개체에 대 한 포인터가 되어야 합니다. 프로그램 `CWinApp::InitInstance` 재정의 합니다. 이 프레임 워크를 초기화 하기 전에 개체를 생성 하는 것을 방지 합니다.

- 문서 또는 보기의 컨텍스트 내에서 마찬가지로 레코드 집합 개체를 사용 합니다. 멤버 함수 응용 프로그램 또는 프레임 창 개체의 레코드 집합을 만듭니다.

## <a name="see-also"></a>참고자료

[MFC 데이터베이스 클래스](../data/mfc-database-classes-odbc-and-dao.md)