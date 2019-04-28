---
title: 'MFC ActiveX 컨트롤: 스톡 속성 추가'
ms.date: 11/04/2016
helpviewer_keywords:
- BackColor property [MFC]
- properties [MFC], adding stock
- ForeColor property [MFC]
- MFC ActiveX controls [MFC], properties
- foreground colors, ActiveX controls
- foreground colors [MFC]
ms.assetid: 8b98c8c5-5b69-4366-87bf-0e61e6668ecb
ms.openlocfilehash: 940f61c9ce6ccb57843333582455e61c1f7ac73b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62225345"
---
# <a name="mfc-activex-controls-adding-stock-properties"></a>MFC ActiveX 컨트롤: 스톡 속성 추가

클래스에 의해 이미 구현 되어에 사용자 지정 속성에서 스톡 속성 다 `COleControl`합니다. `COleControl` 컨트롤에 대 한 공용 속성을 지 원하는 미리 정의 된 멤버 함수를 포함 합니다. 몇 가지 일반적인 속성 컨트롤의 캡션 및 전경색 및 배경색을 포함 합니다. 다른 스톡 속성에 대 한 내용은 참조 하세요 [스톡 속성 추가 마법사 지 속성](#_core_stock_properties_supported_by_classwizard) 이 문서의 뒷부분에 나오는. 속성에는 항상 DISP_STOCKPROP 접두사로 재고에 대 한 디스패치 맵 항목입니다.

이 문서에서는 속성 추가 마법사를 사용 하 여 ActiveX 컨트롤에 있는 스톡 속성 (이 예제의 경우 캡션)에 추가 하는 방법 및 결과 코드 수정 내용을 설명 합니다. 다루는 주제는 다음과 같습니다.

- [속성 추가 마법사를 사용 하 여 스톡 속성을 추가 하려면](#_core_using_classwizard_to_add_a_stock_property)

- [스톡 속성에 대 한 변경 내용을 속성 마법사 추가](#_core_classwizard_changes_for_stock_properties)

- [속성 추가 마법사에서 지원 되는 스톡 속성](#_core_stock_properties_supported_by_classwizard)

- [스톡 속성 및 알림](#_core_stock_properties_and_notification)

- [색 속성](#_core_color_properties)

    > [!NOTE]
    >  Visual Basic 사용자 지정 컨트롤에는 일반적으로 위쪽, 왼쪽, 너비, 높이, 정렬, 태그, 이름, TabIndex, TabStop, 및 부모 같은 속성이 있습니다. 그러나 ActiveX 컨트롤 컨테이너, 이러한 컨트롤 속성을 구현할 책임이 이며 ActiveX 컨트롤 해야 이러한 속성을 지원 하지 않으므로.

##  <a name="_core_using_classwizard_to_add_a_stock_property"></a> 사용 하는 속성 추가 마법사 스톡 속성을 추가 하려면

때문에 사용자 지정 속성을 추가 하는 보다 적은 코드가 필요 스톡 속성 추가 속성은 자동으로 처리에 대 한 지원은 `COleControl`합니다. 다음 절차에는 ActiveX 컨트롤 프레임 워크는 스톡 Caption 속성을 추가 하는 방법을 보여 줍니다 및 다른 스톡 속성 추가를 사용할 수도 있습니다. 캡션에 대 한 선택한 스톡 속성 이름으로 대체 합니다.

#### <a name="to-add-the-stock-caption-property-using-the-add-property-wizard"></a>속성 추가 마법사를 사용 하 여 주식 Caption 속성을 추가 하려면

1. 컨트롤의 프로젝트를 로드합니다.

1. 클래스 뷰에서 컨트롤의 라이브러리 노드를 확장합니다.

1. 컨트롤의 인터페이스 노드(라이브러리 노드의 두 번째 노드)를 마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 엽니다.

1. 바로 가기 메뉴에서 클릭 **추가** 을 클릭 한 다음 **속성 추가**합니다.

   열립니다는 [속성 추가 마법사](../ide/names-add-property-wizard.md)합니다.

1. 에 **속성 이름이** 상자를 클릭 합니다 **캡션**합니다.

1. **마침**을 클릭합니다.

##  <a name="_core_classwizard_changes_for_stock_properties"></a> 스톡 속성 추가 속성 마법사 변경

때문에 `COleControl` 지원 스톡 속성, 속성 추가 마법사가 어떤 방식으로든에서 클래스 선언을 변경 하 고 하지 않으면 속성의 디스패치 맵에 추가 합니다. 구현에 있는 컨트롤의 디스패치 맵에 다음 줄을 추가 하는 속성 추가 마법사 (합니다. Cpp) 됩니다.

[!code-cpp[NVC_MFC_AxUI#22](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-properties_1.cpp)]

컨트롤의 인터페이스 설명에 다음 줄을 추가 하는 (합니다. IDL) 파일:

[!code-cpp[NVC_MFC_AxUI#23](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-properties_2.idl)]

이 줄 할당 Caption 속성을 특정 id입니다. 알림 속성 바인딩 가능 하 고 값을 수정 하기 전에 데이터베이스에서 권한을 요청 합니다.

이렇게 하면 컨트롤의 사용자에 게 사용할 수 있는 캡션 속성입니다. 스톡 속성의 값을 사용 하려면 멤버 변수 또는 멤버 함수에 액세스 합니다 `COleControl` 기본 클래스입니다. 이러한 멤버 변수 및 멤버 함수에 대 한 자세한 내용은 스톡 속성 추가 마법사에서 지원 되는 속성을 다음 섹션을 참조 하세요.

##  <a name="_core_stock_properties_supported_by_classwizard"></a> 스톡 속성 지는 속성 추가 마법사

`COleControl` 클래스 9 스톡 속성을 제공 합니다. 속성 추가 마법사를 사용 하 여 원하는 속성을 추가할 수 있습니다.

|속성|디스패치 맵 항목|값에 액세스 하는 방법|
|--------------|------------------------|-------------------------|
|`Appearance`|DISP_STOCKPROP_APPEARANCE( )|값 만큼 액세스 가능 `m_sAppearance`합니다.|
|`BackColor`|DISP_STOCKPROP_BACKCOLOR( )|호출 하 여 액세스할 수 있는 값 `GetBackColor`합니다.|
|`BorderStyle`|DISP_STOCKPROP_BORDERSTYLE( )|값 만큼 액세스 가능 `m_sBorderStyle`합니다.|
|`Caption`|DISP_STOCKPROP_CAPTION( )|호출 하 여 액세스할 수 있는 값 `InternalGetText`합니다.|
|`Enabled`|DISP_STOCKPROP_ENABLED( )|값 만큼 액세스 가능 `m_bEnabled`합니다.|
|`Font`|DISP_STOCKPROP_FONT( )|문서를 참조 [MFC ActiveX 컨트롤: 글꼴을 사용 하 여](../mfc/mfc-activex-controls-using-fonts.md) 사용량에 대 한 합니다.|
|`ForeColor`|DISP_STOCKPROP_FORECOLOR( )|호출 하 여 액세스할 수 있는 값 `GetForeColor`합니다.|
|`hWnd`|DISP_STOCKPROP_HWND( )|값 만큼 액세스 가능 `m_hWnd`합니다.|
|`Text`|DISP_STOCKPROP_TEXT( )|호출 하 여 액세스할 수 있는 값 `InternalGetText`합니다. 이 속성은 동일 `Caption`에 속성 이름을 제외 하 고 있습니다.|
|`ReadyState`|DISP_STOCKPROP_READYSTATE()|값 만큼 액세스 가능 `m_lReadyState` 또는 `GetReadyState`|

##  <a name="_core_stock_properties_and_notification"></a> 스톡 속성 및 알림

대부분의 스톡 속성에 재정의 될 수 있는 알림 함수가 있습니다. 예를 들어 때마다 합니다 `BackColor` 속성이 변경 되는 `OnBackColorChanged` 함수 (컨트롤 클래스의 멤버 함수) 호출 됩니다. 기본 구현 (에서 `COleControl`) 호출은 `InvalidateControl`합니다. 이 상황에 대 한 응답에 추가 작업을 수행 하려는 경우이 함수를 재정의 합니다.

##  <a name="_core_color_properties"></a> 색 속성

주식을 사용할 수 있습니다 `ForeColor` 고 `BackColor` 속성 또는 컨트롤을 그릴 때 사용자 고유의 사용자 지정 색 속성입니다. 색 속성을 사용 하려면 호출을 [COleControl::TranslateColor](../mfc/reference/colecontrol-class.md#translatecolor) 멤버 함수입니다. 이 함수의 매개 변수는 선택적 색상표 핸들을 및 색 속성의 값입니다. 반환 값은는 **COLORREF** GDI를 전달할 수 있는 값과 같은 함수 `SetTextColor` 고 `CreateSolidBrush`입니다.

주식에 대 한 색 값 `ForeColor` 하 고 `BackColor` 속성 중 하나를 호출 하 여 액세스 합니다 `GetForeColor` 또는 `GetBackColor` 함수를 각각.

다음 예제에서는 컨트롤을 그릴 때 이러한 두 가지 색 속성을 사용 하는 방법을 보여 줍니다. 임시 초기화 **COLORREF** 변수 및 `CBrush` 개체를 호출 하 여 `TranslateColor`: 하나를 사용 하는 `ForeColor` 속성과 다른 사용을 `BackColor` 속성. 임시 `CBrush` 개체는 컨트롤의 사각형을 그리는 데 다음 및 텍스트 색을 사용 하도록 설정 됩니다는 `ForeColor` 속성입니다.

[!code-cpp[NVC_MFC_AxUI#24](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-properties_3.cpp)]

## <a name="see-also"></a>참고자료

[MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX 컨트롤: 속성](../mfc/mfc-activex-controls-properties.md)<br/>
[MFC ActiveX 컨트롤: 메서드](../mfc/mfc-activex-controls-methods.md)<br/>
[COleControl 클래스](../mfc/reference/colecontrol-class.md)
