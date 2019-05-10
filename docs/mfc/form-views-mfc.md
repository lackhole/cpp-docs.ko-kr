---
title: 폼 뷰(MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- user interfaces [MFC], forms
- forms [MFC]
- applications [MFC], forms-based
- forms-based applications [MFC]
- forms [MFC], adding to applications
ms.assetid: efbe73c1-4ca4-4613-aac2-30d916e92c0e
ms.openlocfilehash: f93f65e949c18ddb1ad5dba859ba8c4832abac8f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392832"
---
# <a name="form-views-mfc"></a>폼 뷰(MFC)

모든 시각적 개체 폼을 추가할 수 있습니다 C++ 를 비롯 한 MFC 라이브러리를 지 원하는 응용 프로그램을 [forms 기반 응용 프로그램](../mfc/reference/creating-a-forms-based-mfc-application.md) (해당 뷰 클래스에서 파생 됩니다 하나 `CFormView`). 처음 Visual forms를 지원 하도록 응용 프로그램를 만들지 않은 경우 C++ 새 폼을 삽입 하면이 지원 기능을 추가 합니다. SDI 또는 MDI 응용 프로그램에서 구현 하는 기본 [문서/뷰 아키텍처](../mfc/document-view-architecture.md)선택 하면, 합니다 **새로 만들기** 명령 (기본적으로에 **파일** 메뉴), Visual C++ 사용 가능한 폼에서 선택 하 라는 메시지입니다.

SDI 응용 프로그램에 사용자가 합니다 **새로 만들기** 명령, 폼의 현재 인스턴스 계속 실행 되지만 선택한 양식 사용 하 여 응용 프로그램의 새 인스턴스를 찾을 수 없으면 하나 만들어집니다. MDI 응용 프로그램에서 폼의 현재 인스턴스 계속 해 서 사용자가 실행 된 **새로 만들기** 명령입니다.

> [!NOTE]
>  대화 상자 기반 응용 프로그램에 폼을 삽입할 수 있습니다 (해당 대화 상자 클래스를 기반으로 한 `CDialog` 및 없습니다 보기에서 클래스가 구현 되는 하나). 그러나 문서/뷰 아키텍처에 시각적 개체 없이 C++ 자동으로 구현 하지 않는 합니다 **파일**&#124;**새로 만들기** 기능. 사용자와 같은 다양 한 속성 페이지를 사용 하 여 탭된 대화 상자를 구현 하 여 추가 폼을 볼 수 있는 방법을 만들어야 합니다.

삽입할 때 새 폼을 응용 프로그램에 시각적 개체 C++ 는 다음 작업을 수행 합니다.

- 선택한 양식 스타일 클래스 중 하나를 기반으로 클래스를 만듭니다 (`CFormView`, `CRecordView`를 `CDaoRecordView`, 또는 `CDialog`).

- 적절 한 스타일을 사용 하 여 대화 상자 리소스를 만듭니다 (또는 아직으로 클래스와 연결 되지 않은 기존 대화 상자 리소스를 사용할 수 있습니다).

   기존 대화 상자 리소스를 선택 하면 대화 상자에 대 한 속성 페이지를 사용 하 여 이러한 스타일을 설정 해야 합니다. 대화 상자에 대 한 스타일을 포함 해야 합니다.

     **WS_CHILD**=On

     **WS_BORDER**=Off

     **WS_VISIBLE**=Off

     **WS_CAPTION**=Off

문서/뷰 아키텍처를 기반으로 하는 응용 프로그램에 대 한 합니다 **새 폼** 명령 (클래스 뷰에서 마우스 오른쪽 단추로 클릭)도:

- 만듭니다는 `CDocument`-기반 클래스

   만든 새 클래스를 대신 사용할 수 있는 기존 `CDocument`-프로젝트에서 클래스를 기반으로 합니다.

- 문서 템플릿 (에서 파생 된 `CDocument`) 문자열, 메뉴 및 아이콘 리소스를 사용 하 여 합니다.

   또한 템플릿을 기반으로 사용할 새 클래스를 만들 수 있습니다.

- 호출을 추가 합니다 `AddDocumentTemplate` 응용 프로그램의 `InitInstance` 코드입니다.

   Visual C++ 을 선택 하면 사용 가능한 폼의 목록에 폼을 추가 하는 각 새 폼을 만든이 코드를 추가 합니다 **새로 만들기** 명령. 이 코드는 폼의 연결 된 리소스 ID와 연결 된 문서, 뷰 및 새 폼 개체를 구성 하는 프레임 클래스의 이름을 포함 합니다.

   문서 템플릿 문서, 프레임 창 및 뷰 사이의 연결 역할을 합니다. 단일 문서에 대 한 많은 템플릿을 만들 수 있습니다.

자세한 내용은 다음을 참조하세요.

- [폼 기반 응용 프로그램 만들기](../mfc/reference/creating-a-forms-based-mfc-application.md)

- [프로젝트에 폼 삽입](../mfc/inserting-a-form-into-a-project.md)

## <a name="see-also"></a>참고자료

[사용자 인터페이스 요소](../mfc/user-interface-elements-mfc.md)
