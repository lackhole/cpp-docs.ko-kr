---
title: 폼 기반 MFC 애플리케이션 만들기
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfcforms.project
helpviewer_keywords:
- applications [MFC], forms-based
- forms-based applications [MFC]
ms.assetid: 048d2f7d-b60d-4386-ad8e-71d49af9c05e
ms.openlocfilehash: 6810a6c7fce91865a92d048129da29305e22abc1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62372333"
---
# <a name="creating-a-forms-based-mfc-application"></a>폼 기반 MFC 애플리케이션 만들기

폼에 사용자에 액세스 하 고 데이터를 변경할 수 있도록 하는 컨트롤을 사용 하 여 대화 상자입니다. 다양 한 폼에서에서 사용자가 선택 하는 응용 프로그램을 개발할 수도 있습니다. 폼 기반 응용 프로그램을 클릭 하 여 사용자 액세스 폼을 수 있습니다는 일반적으로 **새로 만들기** 에서 합니다 **파일** 메뉴. 사용자에 대 한 액세스를 부여 하지 않습니다 대화 상자 기반 응용 프로그램을 **새로 만들기** 옵션을 **파일** 메뉴, 폼 기반 응용 프로그램으로 간주 됩니다.

단일 문서 인터페이스 (SDI) 폼 기반 응용 프로그램에 하나의 인스턴스만을 동시에 실행할 수 있도록 특정 양식의 수 있습니다. 새 폼을 선택 하 여 SDI 폼 기반 응용 프로그램에서 여러 폼을 동시에 실행할 수 있기를 **새로 만들기** 옵션을 **파일** 메뉴.

다중 문서 인터페이스 (MDI) 폼 기반 응용 프로그램을 만드는 경우 응용 프로그램이 동일한 형식의 여러 인스턴스를 지원할 수 있게 됩니다.

여러 최상위 문서 지원을 통해 응용 프로그램을 만들 경우 데스크톱은 문서에 대 한 암시적 부모가 고 문서 프레임은 응용 프로그램의 클라이언트 영역에 제한 되지 않습니다. 여러 인스턴스는 자체 프레임, 메뉴 및 작업 표시줄 아이콘을 사용 하 여 각각의 문서를 열 수 있습니다. 선택 하면 되지만 개별적으로 후속 인스턴스의 문서를 닫을 수 있습니다 합니다 **종료** 에서 옵션을 **파일** 메뉴 초기 인스턴스를 응용 프로그램의 모든 인스턴스를 닫습니다.

SDI, MDI 및 여러 최상위 문서 응용 프로그램은 모든 폼 기반으로 하며 문서/뷰 아키텍처를 사용 합니다.

모든 대화 상자 기반 응용 프로그램 정의는 양식 기반입니다. 대화 상자 기반 응용 프로그램을 작성 및 액세스 메서드를 폼을 사용자 고유의 추가로 관리 해야 합니다 문서/뷰 아키텍처를 사용 하지 않습니다.

폼 기반 응용 프로그램에 대 한 기본 클래스는 [CFormView](../../mfc/reference/cformview-class.md)합니다. 응용 프로그램에 데이터베이스 지원, 경우에서 파생 되는 모든 클래스를 선택할 수도 있습니다 `CFormView`합니다. 폼에서 파생 된 모든 창인지 `CFormView` 에서 상속 된 클래스에서 또는 `CFormView`합니다.

와 같은 기본 클래스를 사용 하는 경우에 [CView](../../mfc/reference/cview-class.md)를 할 수 있습니다 나중에 응용 프로그램에서 폼 기반 [MFC 클래스 추가](../../mfc/reference/adding-an-mfc-class.md) 에서 파생 `CFormView` 확인 하 고는 **DocTemplate 생성 리소스** 의 확인란을 선택 합니다 [MFC 클래스 마법사](../../mfc/reference/document-template-strings-mfc-add-class-wizard.md)합니다.

마법사를 사용 하 여 완료 되 면 프로젝트가 열리며, 선택한 경우 `CFormView` (또는 클래스에서 상속 되는 `CFormView`) 기본 클래스로 대화 상자 기반 응용 프로그램을 시각적 개체를 만든 경우 또는 C++ 대화 상자 편집기를 엽니다. 이 시점에서 폼을 만들 준비가 되었습니다.

### <a name="to-begin-creating-a-forms-based-mfc-executable"></a>폼 기반 MFC 실행 파일을 만들기 시작

1. 지침을 따르고 [MFC 응용 프로그램을 만드는](../../mfc/reference/creating-an-mfc-application.md)합니다.

1. MFC 응용 프로그램 마법사에서 [응용 프로그램 종류](../../mfc/reference/application-type-mfc-application-wizard.md) 페이지에서 선택 합니다 **문서/뷰 아키텍처 지원** 확인란 합니다.

1. 선택 **단일 문서**하십시오 **여러 문서**, 또는 **여러 최상위 문서**합니다.

    > [!NOTE]
    >  기본적으로 SDI, MDI 또는 여러 최상위 문서 인터페이스 응용 프로그램을 선택 했다면 `CView` 의 응용 프로그램의 뷰에 대 한 기본 클래스로 설정 됩니다는 [생성 된 클래스](../../mfc/reference/generated-classes-mfc-application-wizard.md) 마법사의 페이지입니다. 폼 기반 응용 프로그램을 만들려면 선택 해야 `CFormView` 응용 프로그램의 보기에 대 한 기본 클래스입니다. 참고 마법사는 폼 기반 응용 프로그램에 대 한 인쇄 지원 되지 않습니다.

1. 마법사의 다른 페이지에서 원하는 다른 프로젝트 옵션을 설정 합니다.

1. 클릭 **완료** 기본 응용 프로그램을 생성 합니다.

자세한 내용은 다음을 참조하세요.

- [파생 된 뷰 클래스](../../mfc/derived-view-classes-available-in-mfc.md)

- [문서/뷰 아키텍처의 대체](../../mfc/alternatives-to-the-document-view-architecture.md)

- [애플리케이션 디자인 선택](../../mfc/application-design-choices.md)

## <a name="see-also"></a>참고자료

[MFC 응용 프로그램 마법사](../../mfc/reference/mfc-application-wizard.md)<br/>
[폼 뷰](../../mfc/form-views-mfc.md)<br/>
[파일 탐색기 스타일 MFC 응용 프로그램 만들기](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md)<br/>
[웹 브라우저 스타일 MFC 응용 프로그램 만들기](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)
