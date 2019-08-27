---
title: '연습: MFC 자유 곡선 응용 프로그램 (2 부)를 업데이트 하는 중'
ms.date: 04/25/2019
helpviewer_keywords:
- walkthroughs [MFC]
ms.assetid: 602df5c2-17d4-4cd9-8cf6-dff652c4cae5
ms.openlocfilehash: d4655c0a4a8847642b75575e324a291e39bbf42a
ms.sourcegitcommit: 283cb64fd7958a6b7fbf0cd8534de99ac8d408eb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64558167"
---
# <a name="walkthrough-updating-the-mfc-scribble-application-part-2"></a>연습: MFC 자유 곡선 응용 프로그램 (2 부)를 업데이트 하는 중

[1 부](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md) 자유 곡선 응용 프로그램의이 연습에서는 클래식 Office Fluent 리본을 추가 하는 방법에 설명 했습니다. 이 부분에는 리본 패널 및 사용자가 메뉴 및 명령을 대신 사용할 수 있는 컨트롤을 추가 하는 방법을 보여 줍니다.

## <a name="prerequisites"></a>전제 조건

[Visual C++ 샘플](../overview/visual-cpp-samples.md)

##  <a name="top"></a> 섹션

이 연습 부분에는 다음 단원이 있습니다.

- [리본 메뉴에 새 패널 추가](#addnewpanel)

- [도움말 패널 리본에 추가](#addhelppanel)

- [리본에 펜 패널 추가](#addpenpanel)

- [리본 색 단추 추가](#addcolorbutton)

- [문서 클래스에 색 멤버 추가](#addcolormember)

- [펜을 초기화 하 고 기본 설정 저장](#initpensave)

##  <a name="addnewpanel"></a> 리본 메뉴에 새 패널 추가

이러한 단계에 추가 하는 방법을 보여 줍니다는 **뷰** 도구 모음 및 상태 표시줄의 표시 유형을 제어 하는 확인란이 두 개를 포함 하는 패널 그리고를 **창** 세로 방향된 분할 포함 된 패널 만들기 및 다중 문서 인터페이스 (MDI) 창 정렬을 제어 하는 단추입니다.

### <a name="to-add-a-view-panel-and-window-panel-to-the-ribbon-bar"></a>리본 표시줄에 창 패널을 보기 패널을 추가 하려면

1. 명명 된 패널을 만드는 `View`, 상태 표시줄 및 도구 모음을 설정/해제 하는 확인란이 두 개 있는 합니다.

   1. **도구 상자**, 끌어를 **패널** 에 **홈** 범주. 다음 두 가지를 끌어 **확인란** 패널에 있습니다.

   1. 해당 속성을 수정 하는 패널을 클릭 합니다. 변경 **캡션** 에 `View`입니다.

   1. 해당 속성을 수정 하려면 첫 번째 확인란을 클릭 합니다. 변경 **ID** 하 `ID_VIEW_TOOLBAR` 하 고 **캡션** 에 `Toolbar`입니다.

   1. 해당 속성을 수정 하려면 두 번째 확인란을 클릭 합니다. 변경 **ID** 하 `ID_VIEW_STATUS_BAR` 하 고 **캡션** 에 `Status Bar`입니다.

1. 명명 된 패널을 만드는 `Window` 분할 단추를 포함 합니다. 사용자가 분할 단추를 클릭 하면 바로 가기 메뉴에 자유 곡선 응용 프로그램에 이미 정의 된 세 가지 명령이 표시 됩니다.

   1. **도구 상자**, 끌어를 **패널** 에 **홈** 범주. 놓습니다를 **단추** 패널에 있습니다.

   1. 해당 속성을 수정 하는 패널을 클릭 합니다. 변경 **캡션** 에 `Window`입니다.

   1. 단추를 클릭합니다. 변경 **캡션** 하 `Windows`, **키** 에 `w`를 **큰 이미지 인덱스** 에 `1`, 및 **분할 모드** `False`입니다. 줄임표를 클릭 한 다음 ( **...** ) 옆에 **메뉴 항목** 열려는 합니다 **항목 편집기** 대화 상자.

   1. 클릭 **추가** 세 번 세 개의 단추를 추가 합니다.

   1. 첫 번째 단추를 클릭 한 다음 변경 **캡션** 하 `New Window`, 및 **ID** 에 `ID_WINDOW_NEW`입니다.

   1. 두 번째 단추를 클릭 한 다음 변경 **캡션** 하 `Cascade`, 및 **ID** 에 `ID_WINDOW_CASCADE`입니다.

   1. 세 번째 단추를 클릭 한 다음 변경 **캡션** 하 `Tile`, 및 **ID** 에 `ID_WINDOW_TILE_HORZ`입니다.

1. 변경 사항을 저장한 다음 애플리케이션을 빌드하고 실행합니다. **뷰** 하 고 **창** 패널을 표시 합니다. 제대로 작동 하는지 확인 하려면 단추를 클릭 합니다.

##  <a name="addhelppanel"></a> 도움말 패널 리본에 추가

이제 이름이 지정 된 리본 단추에 자유 곡선 응용 프로그램에 정의 된 두 개의 메뉴 항목을 할당할 수 있습니다 **도움말 항목** 하 고 **에 대 한 Scribble**합니다. 라는 새 패널에 단추가 추가 됩니다 **도움말**합니다.

### <a name="to-add-a-help-panel"></a>도움말 패널을 추가 하려면

1. **도구 상자**, 끌어를 **패널** 에 **홈** 범주. 다음 두 가지를 끌어 **단추** 패널에 있습니다.

1. 해당 속성을 수정 하는 패널을 클릭 합니다. 변경 **캡션** 에 `Help`입니다.

1. 첫 번째 단추를 클릭 합니다. 변경 **캡션** 하 `Help Topics`, 및 **ID** 에 `ID_HELP_FINDER`입니다.

1. 두 번째 단추를 클릭 합니다. 변경 **캡션** 하 `About Scribble...`, 및 **ID** 에 `ID_APP_ABOUT`입니다.

1. 변경 사항을 저장한 다음 애플리케이션을 빌드하고 실행합니다. A **도움말** 두 리본 단추가 포함 된 패널을 표시 합니다.

   > [!IMPORTANT]
   > 클릭할 때 합니다 **도움말 항목** 단추를 자유 곡선 응용 프로그램 이라는 압축된 (.chm) HTML 도움말 파일을 엽니다 *your_project_name*. chm. 결과적으로 프로젝트가 Scribble 라는 프로젝트 이름으로 도움말 파일을 이름을 해야 합니다.

##  <a name="addpenpanel"></a> 리본에 펜 패널 추가

이제 펜의 색과 두께 제어 하는 단추에 표시할 패널을 추가 합니다. 이 패널에 굵은 /가 펜을 전환 하는 확인란을 포함 합니다. 해당 기능이 유사 합니다 **두꺼운 선** 자유 곡선 응용 프로그램에서 메뉴 항목입니다.

원래 Scribble 응용 프로그램에는 사용자가 클릭할 때 표시 되는 대화 상자에서 펜 너비를 선택할 수 있습니다 **펜 너비** 메뉴. 리본 표시줄에 새 컨트롤에 대 한 충분 한 공간에 있으므로 리본의 두 콤보 상자를 사용 하 여 대화 상자를 바꿀 수 있습니다. 얇은 펜의 너비를 조정 하는 콤보 상자 및 다른 콤보 상자 굵게 펜의 너비를 조정 합니다.

#### <a name="to-add-a-pen-panel-and-combo-boxes-to-the-ribbon"></a>리본 메뉴에 펜 패널 및 콤보 상자를 추가 하려면

1. **도구 상자**, 끌어를 **패널** 에 **홈** 범주. 놓습니다를 **확인란** 두 개의 **콤보 상자** 패널에 있습니다.

1. 해당 속성을 수정 하는 패널을 클릭 합니다. 변경 **캡션** 에 `Pen`입니다.

1. 확인란을 클릭 합니다. 변경 **캡션** 하 `Use Thick`, 및 **ID** 에 `ID_PEN_THICK_OR_THIN`입니다.

1. 첫 번째 콤보 상자를 클릭 합니다. 변경 **캡션** 하 `Thin Pen`, **ID** 를 `ID_PEN_THIN_WIDTH`, **형식** 를 `Drop List`를 **데이터** 를 `1;2;3;4;5;6;7;8;9;`, 및 **텍스트** 에 `2`입니다.

1. 두 번째 콤보 상자를 클릭 합니다. 변경 **캡션** 하 `Thick Pen`, **ID** 를 `ID_PEN_THICK_WIDTH`, **형식** 를 `Drop List`를 **데이터** 를 `5;6;7;8;9;10;11;12;13;14;15;16;17;18;19;20;`, 및 **텍스트** 에 `5`입니다.

1. 새 콤보 상자의 모든 펜 옵션에 대 한 메뉴 항목을 만들어야 하므로 모든 기존 메뉴 항목에 해당 하지.

   1. 에 **리소스 뷰** 창을 열려면 합니다 **IDR_SCRIBBTYPE** 메뉴 리소스입니다.

   1. 클릭 **펜** 펜 메뉴를 엽니다. 누른 **여기에 입력** 유형과 `Thi&n Pen`합니다.

   1. 열에 입력 한 텍스트를 마우스 오른쪽 단추로 클릭 합니다 **속성** 창 및 변경 된 ID 속성을 `ID_PEN_THIN_WIDTH`입니다.

   1. 모든 펜 메뉴 항목에 대 한 이벤트 처리기를 만듭니다. 마우스 오른쪽 단추로 클릭 합니다 **이번 & n 펜** 메뉴 항목을 생성 하 고 클릭 **이벤트 처리기 추가**합니다. 합니다 **이벤트 처리기 마법사** 표시 됩니다.

   1. 에 **클래스 목록** 마법사에서 선택 상자 **CScribbleDoc** 클릭 하 고 **추가 및 편집**합니다. 명령을 라는 이벤트 처리기를 만들고 `CScribbleDoc::OnPenThinWidth`합니다.

   1. 다음 코드를 `CScribbleDoc::OnPenThinWidth`에 추가합니다.

        ```cpp
        // Get a pointer to the ribbon bar
        CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx*) AfxGetMainWnd())->GetRibbonBar();
        ASSERT_VALID(pRibbon);

        // Get a pointer to the Thin Width combo box
        CMFCRibbonComboBox* pThinComboBox = DYNAMIC_DOWNCAST(
        CMFCRibbonComboBox, pRibbon->FindByID(ID_PEN_THIN_WIDTH));

        //Get the selected value
        int nCurSel = pThinComboBox->GetCurSel();
        if (nCurSel>= 0)
        {
            m_nThinWidth = atoi(CStringA(pThinComboBox->GetItem(nCurSel)));
        }

        // Create a new pen using the selected width
        ReplacePen();
        ```

1. 그런 다음 메뉴 굵게 펜에 대 한 항목 및 이벤트 처리기를 만듭니다.

   1. 에 **리소스 뷰** 창을 열려면 합니다 **IDR_SCRIBBTYPE** 메뉴 리소스입니다.

   1. 클릭 **펜** 펜 메뉴를 엽니다. 누른 **여기에 입력** 유형과 `Thic&k Pen`합니다.

   1. 표시 하려면 입력 한 텍스트를 마우스 오른쪽 단추로 클릭 합니다 **속성** 창입니다. ID 속성을 변경 `ID_PEN_THICK_WIDTH`합니다.

   1. 마우스 오른쪽 단추로 클릭 합니다 **굵게 펜** 메뉴 항목을 생성 하 고 클릭 **이벤트 처리기 추가**합니다. 합니다 **이벤트 처리기 마법사** 표시 됩니다.

   1. 에 **클래스 목록** 마법사의 상자 **CScribbleDoc** 클릭 하 고 **추가 및 편집**합니다. 명령을 라는 이벤트 처리기를 만들고 `CScribbleDoc::OnPenThickWidth`합니다.

   1. 다음 코드를 `CScribbleDoc::OnPenThickWidth`에 추가합니다.

        ```cpp
        // Get a pointer to the ribbon bar
        CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx *) AfxGetMainWnd())->GetRibbonBar();
        ASSERT_VALID(pRibbon);

        CMFCRibbonComboBox* pThickComboBox = DYNAMIC_DOWNCAST(
            CMFCRibbonComboBox, pRibbon->FindByID(ID_PEN_THICK_WIDTH));
        // Get the selected value
        int nCurSel = pThickComboBox->GetCurSel();
        if (nCurSel>= 0)
        {
            m_nThickWidth = atoi(CStringA(pThickComboBox->GetItem(nCurSel)));
        }

        // Create a new pen using the selected width
        ReplacePen();
        ```

1. 변경 사항을 저장한 다음 애플리케이션을 빌드하고 실행합니다. 새 단추와 콤보 상자를 표시 되어야 합니다. Scribble을 다른 펜 너비를 사용해 보세요.

##  <a name="addcolorbutton"></a> 펜 패널 색 단추 추가

그런 다음 추가 [CMFCRibbonColorButton](../mfc/reference/cmfcribboncolorbutton-class.md) 사용자 수 있는 개체 scribble 색에서입니다.

### <a name="to-add-a-color-button-to-the-pen-panel"></a>펜 패널로 색 단추를 추가 하려면

1. 색 단추를 추가 하려면 먼저 해당 메뉴 항목을 만듭니다. 에 **리소스 뷰** 창을 열려면 합니다 **IDR_SCRIBBTYPE** 메뉴 리소스입니다. 클릭 합니다 **펜** 펜 메뉴를 열려면 메뉴 항목입니다. 누른 **여기에 입력** 유형과 `&Color`합니다. 표시 하려면 입력 한 텍스트를 마우스 오른쪽 단추로 클릭 합니다 **속성** 창입니다. ID를 `ID_PEN_COLOR`로 변경합니다.

1. 이제 색 단추를 추가 합니다. **도구 상자**, 끌어를 **색 단추** 에 **펜** 패널.

1. 색 단추를 클릭 합니다. 변경 **캡션** 하 `Color`, **ID** 를 `ID_PEN_COLOR`, **Simple Look** 를 `True`를 **큰 이미지 인덱스** 를 `1`, 및 **분할 모드** 하려면 `False`합니다.

1. 변경 사항을 저장한 다음 애플리케이션을 빌드하고 실행합니다. 새 색 단추에 표시 되어야 합니다 **펜** 패널입니다. 그러나 이벤트 처리기를 아직 없기 때문에 사용할 수 없습니다. 다음 단계에는 색 단추에 대 한 이벤트 처리기를 추가 하는 방법을 보여 줍니다.

##  <a name="addcolormember"></a> 문서 클래스에 색 멤버 추가

원래 Scribble 응용 프로그램에 펜 색 없으므로 구현에 써야 합니다. 문서 클래스에 새 구성원을 추가 펜 색입니다. 문서를 저장 하려면 `CscribbleDoc`합니다.

### <a name="to-add-a-color-member-to-the-document-class"></a>문서 클래스에 색 구성원을 추가 하려면

1. Scribdoc.h에서는 `CScribbleDoc` 클래스를 찾습니다는 `// Attributes` 섹션입니다. 정의 후 다음 코드 줄을 추가 합니다 `m_nThickWidth` 데이터 멤버입니다.

   ```cpp
   // Current pen color
   COLORREF m_penColor;
   ```

1. 모든 문서 목록에 사용자가 이미 그린 스트로크 합니다. 정의한 모든 스트로크를 `CStroke` 개체입니다. `CStroke` 클래스는 클래스를 수정 해야 하므로 펜 색에 대 한 정보를 포함 하지 않습니다. Scribdoc.h에서를 `CStroke` 클래스를 정의 후 다음 코드 줄을 추가 합니다 `m_nPenWidth` 데이터 멤버입니다.

   ```cpp
   // Pen color for the stroke
   COLORREF m_penColor;
   ```

1. Scribdoc.h, 추가 새 `CStroke` 생성자 매개 변수를 가진 너비와 색을 지정 합니다. 뒤에 코드의 다음 줄을 추가 합니다 `CStroke(UINT nPenWidth);` 문입니다.

   ```cpp
   CStroke(UINT nPenWidth, COLORREF penColor);
   ```

1. Scribdoc.cpp에서 새 구현을 추가 `CStroke` 생성자입니다. 구현 후 다음 코드를 추가 합니다 `CStroke::CStroke(UINT nPenWidth)` 생성자입니다.

   ```cpp
   // Constructor that uses the document's current width and color
   CStroke::CStroke(UINT nPenWidth, COLORREF penColor)
   {
       m_nPenWidth = nPenWidth;
       m_penColor = penColor;
       m_rectBounding.SetRectEmpty();
   }
   ```

1. 두 번째 줄을 변경 합니다 `CStroke::DrawStroke` 같이 메서드.

   ```cpp
   if (!penStroke.CreatePen(PS_SOLID, m_nPenWidth, m_penColor))
   ```

1. 문서 클래스에 대 한 기본 펜 색을 설정 합니다. Scribdoc.cpp에서 다음 줄을 추가 합니다 `CScribbleDoc::InitDocument`뒤의 `m_nThickWidth = 5;` 문입니다.

   ```cpp
   // default pen color is black
   m_penColor = RGB(0, 0, 0);
   ```

1. Scribdoc.cpp, 변경의 첫 번째 줄은 `CScribbleDoc::NewStroke` 다음 방법입니다.

   ```cpp
   CStroke* pStrokeItem = new CStroke(m_nPenWidth, m_penColor);
   ```

1. 마지막 줄을 변경 합니다 `CScribbleDoc::ReplacePen` 메서드는 다음과 같습니다.

   ```cpp
   m_penCur.CreatePen(PS_SOLID, m_nPenWidth, m_penColor);
   ```

1. 추가 된 `m_penColor` 이전 단계에서 멤버입니다. 이제 멤버를 설정 하는 색 단추에 대 한 이벤트 처리기를 만듭니다.

   1. 에 **리소스 뷰** 창 IDR_SCRIBBTYPE 메뉴 리소스를 엽니다.

   1. 마우스 오른쪽 단추로 클릭 합니다 **Color** 메뉴 항목을 클릭 **이벤트 처리기 추가**합니다. 합니다 **이벤트 처리기 마법사** 나타납니다.

   1. 에 **클래스 목록** 마법사에서 선택 상자 **CScribbleDoc** 클릭 하 고는 **추가 및 편집** 단추입니다. 이 명령은 만듭니다는 `CScribbleDoc::OnPenColor` 이벤트 처리기 스텁 합니다.

1. 에 대 한 스텁을 바꿉니다는 `CScribbleDoc::OnPenColor` 이벤트 처리기를 다음 코드로 바꿉니다.

   ```cpp
   void CScribbleDoc::OnPenColor()
   {
       // Change pen color to reflect color button's current selection
       CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx*) AfxGetMainWnd())->GetRibbonBar();
       ASSERT_VALID(pRibbon);

       CMFCRibbonColorButton* pColorBtn = DYNAMIC_DOWNCAST(
           CMFCRibbonColorButton, pRibbon->FindByID(ID_PEN_COLOR));

       m_penColor = pColorBtn->GetColor();
       // Create new pen using the selected color
       ReplacePen();
   }
   ```

1. 변경 사항을 저장한 다음 애플리케이션을 빌드하고 실행합니다. 이제 색 단추를 누르고 펜의 색을 변경할 수 있습니다.

##  <a name="initpensave"></a> 펜을 초기화 하 고 기본 설정 저장

다음으로, 색 및 펜의 두께 초기화 합니다. 마지막으로 저장 하 고 파일에서 그리기 색을 로드 합니다.

### <a name="to-initialize-controls-on-the-ribbon-bar"></a>리본 표시줄에 있는 컨트롤을 초기화 하려면

1. 리본 메뉴 모음에서 펜을 초기화 합니다.

   scribdoc.cpp, 다음 코드를 추가할 합니다 `CScribbleDoc::InitDocument` 메서드 뒤를 `m_sizeDoc = CSize(200,200)` 문입니다.

   ```cpp
   // Reset the ribbon UI to its initial values
   CMFCRibbonBar* pRibbon =
       ((CMDIFrameWndEx*) AfxGetMainWnd())->GetRibbonBar();
   ASSERT_VALID(pRibbon);

   CMFCRibbonColorButton* pColorBtn = DYNAMIC_DOWNCAST(
       CMFCRibbonColorButton,
       pRibbon->FindByID(ID_PEN_COLOR));

   // Set ColorButton to black
   pColorBtn->SetColor(RGB(0, 0, 0));

   CMFCRibbonComboBox* pThinComboBox = DYNAMIC_DOWNCAST(
       CMFCRibbonComboBox,
       pRibbon->FindByID(ID_PEN_THIN_WIDTH));

   // Set Thin pen combobox to 2
   pThinComboBox->SelectItem(1);

   CMFCRibbonComboBox* pThickComboBox = DYNAMIC_DOWNCAST(
       CMFCRibbonComboBox,
       pRibbon->FindByID(ID_PEN_THICK_WIDTH));

   // Set Thick pen combobox to 5
   pThickComboBox->SelectItem(0);
   ```

1. 파일을 그릴 색을 저장 합니다. Scribdoc.cpp, 다음 문을 추가 합니다 `CStroke::Serialize` 메서드 뒤를 `ar << (WORD)m_nPenWidth;` 문입니다.

   ```cpp
   ar << (COLORREF)m_penColor;
   ```

1. 파일에서 그리기 색을 마지막으로 로드 합니다. 에 코드의 다음 줄을 추가 합니다 `CStroke::Serialize` 메서드 뒤를 `m_nPenWidth = w;` 문입니다.

   ```cpp
   ar >> m_penColor;
   ```

1. 이제 색에서 scribble 및 드로잉을 파일로 저장 합니다.

## <a name="conclusion"></a>결론

MFC 자유 곡선 응용 프로그램을 업데이트 했습니다. 기존 응용 프로그램을 수정 하는 경우이 연습 가이드로 사용 합니다.

## <a name="see-also"></a>참고자료

[연습](../mfc/walkthroughs-mfc.md)<br/>
[연습: MFC 자유 곡선 애플리케이션 업데이트(1부)](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md)
