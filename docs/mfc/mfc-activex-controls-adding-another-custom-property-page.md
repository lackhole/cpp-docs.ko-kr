---
title: 'MFC ActiveX 컨트롤: 다른 사용자 지정 속성 페이지 추가'
ms.date: 11/04/2016
helpviewer_keywords:
- property pages [MFC], MFC ActiveX controls
- custom property pages [MFC]
- ActiveX controls [MFC], property pages
- MFC ActiveX controls [MFC], property pages
ms.assetid: fcf7e119-9f29-41a9-908d-e9b1607e08af
ms.openlocfilehash: 87b71fdddc5b52f66c34cdbcdb234c83616d0850
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160343"
---
# <a name="mfc-activex-controls-adding-another-custom-property-page"></a>MFC ActiveX 컨트롤: 다른 사용자 지정 속성 페이지 추가

경우에 따라 ActiveX 컨트롤 합당 한 속성 페이지에 들어가는 개수 보다 더 많은 속성을 가집니다. 이 경우 이러한 속성을 표시 하려면 ActiveX 컨트롤에 속성 페이지를 추가할 수 있습니다.

하나 이상의 속성 페이지에 이미 있는 ActiveX 컨트롤에 새 속성 페이지를 추가 하는 것이 논의 합니다. 스톡 속성을 추가 하는 방법은 페이지 (글꼴, 그림 또는 색) 문서를 참고 [MFC ActiveX 컨트롤: 스톡 속성 페이지를 사용 하 여](../mfc/mfc-activex-controls-using-stock-property-pages.md)입니다.

다음 절차는 ActiveX 컨트롤 마법사에서 만든 샘플 ActiveX 컨트롤 프레임 워크를 사용 합니다. 따라서 클래스 이름 및 식별자는이 예제에 고유 합니다.

속성 페이지를 사용 하 여 ActiveX 컨트롤에 대 한 자세한 내용은 다음 문서를 참조 하세요.

- [MFC ActiveX 컨트롤: 속성 페이지](../mfc/mfc-activex-controls-property-pages.md)

- [MFC ActiveX 컨트롤: 스톡 속성 페이지를 사용 하 여](../mfc/mfc-activex-controls-using-stock-property-pages.md)

    > [!NOTE]
    >  페이지 크기 ActiveX 컨트롤 속성 페이지에 대 한 표준 준수 하는 새 속성이 가장 좋습니다. 사진 및 색 스톡 속성 페이지 250 x 62 측정값 대화 상자 단위 (DLU). 표준 글꼴 속성 페이지는 250 x 110 Dlu입니다. ActiveX 컨트롤 마법사에서 만든 기본 속성 페이지는 250 x 62 DLU standard를 사용 합니다.

### <a name="to-insert-a-new-property-page-template-into-your-project"></a>프로젝트에 새 속성 페이지 템플릿 삽입 하려면

1. 컨트롤 프로젝트를 열고, 프로젝트 작업 영역에서 리소스 보기를 엽니다.

1. 바로 가기 메뉴를 열고 클릭 리소스 뷰에서 마우스 오른쪽 단추로 클릭 **리소스 추가**합니다.

1. 확장 된 **대화 상자** 노드를 선택한 **IDD_OLE_PROPPAGE_SMALL**합니다.

1. 클릭 **새로 만들기** 프로젝트에 리소스를 추가 합니다.

1. 속성 창을 새로 고쳐야 새 속성 페이지 템플릿을 선택 합니다.

1. 에 대 한 새 값을 입력 합니다 **ID** 속성입니다. 이 예제에서는 **IDD_PROPPAGE_NEWPAGE**합니다.

1. 클릭 **저장할** 도구 모음에서 합니다.

### <a name="to-associate-the-new-template-with-a-class"></a>새 템플릿 클래스를 사용 하 여 연결 하려면

1. 클래스 뷰를 엽니다.

1. 클래스 뷰 바로 가기 메뉴를 열고를 마우스 오른쪽 단추로 클릭 합니다.

1. 바로 가기 메뉴에서 클릭 **추가** 을 클릭 한 다음 **클래스 추가**합니다.

   열립니다는 [클래스 추가](../ide/add-class-dialog-box.md) 대화 상자.

1. 두 번 클릭 합니다 **MFC 클래스** 템플릿.

1. 에 **클래스 이름** 상자에 [MFC 클래스 마법사](../mfc/reference/mfc-add-class-wizard.md), 새 대화 상자 클래스에 대 한 이름을 입력 합니다. (이 예제에서는 `CAddtlPropPage`.)

1. 파일 이름을 변경 하려면 클릭 **변경**합니다. 구현 및 헤더 파일에 대 한 이름을 입력 하거나 기본 이름을 적용 합니다.

1. 에 **기본 클래스** 상자에서 `COlePropertyPage`합니다.

1. 에 **대화 상자 ID** 상자에서 **IDD_PROPPAGE_NEWPAGE**합니다.

9. 클릭 **완료** 여 클래스를 만듭니다.

컨트롤의 사용자가이 새 속성 페이지에 대 한 액세스를 허용 하려면 다음과 같이 변경 컨트롤의 속성 페이지 Id 매크로 섹션 (컨트롤 구현 파일에 있음):

[!code-cpp[NVC_MFC_AxUI#32](../mfc/codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_1.cpp)]

BEGIN_PROPPAGEIDS 매크로 (속성 페이지 수) 1에서 2의 두 번째 매개 변수를 증가 시켜야 하는 note 합니다.

또한 컨트롤 구현 파일을 수정 해야 합니다 (합니다. 헤더를 포함 하는 CPP) 파일 (합니다. H) 새 속성 페이지 클래스의 파일입니다.

다음 단계에서는 새 속성 페이지에 대 한 형식 이름 및 캡션을 제공 하는 두 개의 새 문자열 리소스를 만듭니다.

#### <a name="to-add-new-string-resources-to-a-property-page"></a>새 문자열 리소스 속성 페이지를 추가 하려면

1. 컨트롤 프로젝트를 열고, 리소스 보기를 엽니다.

1. 두 번 클릭 합니다 **문자열 테이블** 기존 문자열 테이블 리소스 문자열을 추가 하려는 폴더 및 다음 두 번 클릭 합니다.

   문자열 테이블을 창에서 열립니다.

1. 문자열 테이블의 끝에 있는 빈 줄을 선택 하 고 텍스트 또는 캡션 문자열을 입력 합니다: 예를 들어, "추가 속성 페이지입니다."

   열립니다는 **문자열 속성** 페이지 표시 **캡션** 하 고 **ID** 상자입니다. 합니다 **캡션** 상자에 입력 한 문자열이 포함 됩니다.

1. 에 **ID** 상자에서 선택 하거나 문자열에 대 한 ID를 입력 합니다. 마친 후 enter 키를 누릅니다.

   이 예제에서는 **IDS_SAMPLE_ADDPAGE** 새 속성 페이지의 형식 이름입니다.

1. 사용 하 여 3-4 단계를 반복 **IDS_SAMPLE_ADDPPG_CAPTION** ID 및 캡션에 대 한 "추가 속성 페이지"에 대 한 합니다.

1. 안에. 새 속성 페이지 클래스의 CPP 파일 (이 예제에서는 `CAddtlPropPage`) 수정 합니다 `CAddtlPropPage::CAddtlPropPageFactory::UpdateRegistry` IDS_SAMPLE_ADDPAGE로 전달 되도록 [AfxOleRegisterPropertyPageClass](../mfc/reference/registering-ole-controls.md#afxoleregisterpropertypageclass)다음 예제와 같이:

   [!code-cpp[NVC_MFC_AxUI#33](../mfc/codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_2.cpp)]

1. 생성자를 수정 `CAddtlPropPage` IDS_SAMPLE_ADDPPG_CAPTION에 전달 되도록는 `COlePropertyPage` 다음과 같은 생성자:

   [!code-cpp[NVC_MFC_AxUI#34](../mfc/codesnippet/cpp/mfc-activex-controls-adding-another-custom-property-page_3.cpp)]

후 필요한 수정 프로젝트를 다시 작성 및 테스트 컨테이너를 사용 하 여 새 속성 페이지를 테스트 합니다. 테스트 컨테이너에 액세스하는 방법은 [테스트 컨테이너로 속성 및 이벤트 테스트](../mfc/testing-properties-and-events-with-test-container.md) 를 참조하세요.

## <a name="see-also"></a>참고자료

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)
