---
title: 애플리케이션에서 속성 시트 사용
ms.date: 11/04/2016
helpviewer_keywords:
- dialog templates [MFC], property sheets
- dialog resources
- property pages [MFC], property sheets
- DoModal method property sheets
- AddPage method [MFC]
- property sheets, about property sheets
- Create method [MFC], property sheets
- CPropertyPage class [MFC], styles
ms.assetid: 240654d4-152b-4e3f-af7b-44234339206e
ms.openlocfilehash: 4fd68f57db082ab0b0da0e8248e0be239c63c99a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411528"
---
# <a name="using-property-sheets-in-your-application"></a>애플리케이션에서 속성 시트 사용

응용 프로그램에서 속성 시트를 사용 하려면 다음 단계를 수행 합니다.

1. 각 속성 페이지 대화 상자 템플릿 리소스를 만듭니다. 사용자 수로 전환 하 한 페이지에서 다른 레이아웃을 각 페이지 최대한 일관 되 게 되므로 점을 염두에 두십시오.

   모든 페이지에 대 한 대화 상자 템플릿 동일한 크기 일 필요가 없습니다. 속성 페이지에 대 한 속성 시트에 할당할 공간 크기를 확인 하는 가장 큰 페이지의 크기를 사용 하는 프레임 워크입니다.

   속성 페이지 대화 상자 템플릿 리소스를 만들면 다음과 같은 스타일 속성 대화 상자 속성 시트에 지정 해야 합니다.

   - 설정 합니다 **캡션** 편집 상자에는 **일반** 이 페이지에 대 한 탭에 표시 하려는 텍스트 페이지입니다.

   - 설정 합니다 **스타일** 목록 상자에는 **스타일** 페이지를 **자식**합니다.

   - 설정 합니다 **테두리** 목록 상자에는 **스타일** 페이지를 **Thin**합니다.

   - 했는지를 **Titlebar** 확인란을 **스타일** 페이지를 선택 합니다.

   - 있는지 확인 합니다 **사용 안 함** 확인란 합니다 **기타 스타일** 페이지가 선택 되어.

1. 만들기는 [CPropertyPage](../mfc/reference/cpropertypage-class.md)-각 속성 페이지 대화 상자 템플릿에 해당 하는 클래스를 파생 합니다. 참조 [클래스 추가](../ide/adding-a-class-visual-cpp.md)합니다. 선택 `CPropertyPage` 기본 클래스입니다.

1. 이 속성 페이지에 대 한 값을 보유 하는 변수 멤버를 만듭니다. 속성 페이지에 멤버 변수를 추가 하기 위한 프로세스 이므로 정확 하 게 대화 상자에서 멤버 변수 추가 동일 속성 페이지는 특수 한 대화 상자. 자세한 내용은 [대화 상자 컨트롤에 대 한 멤버 변수 정의](../windows/defining-member-variables-for-dialog-controls.md)합니다.

1. 생성 된 [CPropertySheet](../mfc/reference/cpropertysheet-class.md) 소스 코드의 개체입니다. 생성 하는 일반적으로 `CPropertySheet` 속성 시트를 표시 하는 명령에 대 한 처리기에서 개체입니다. 이 개체는 전체 속성 시트를 나타냅니다. 모달 속성 시트를 만드는 경우 합니다 [DoModal](../mfc/reference/cpropertysheet-class.md#domodal) 함수를 프레임 워크는 기본적으로 세 명령 단추를 제공 합니다. 확인을 취소 하 고 적용 합니다. 프레임 워크를 사용 하 여 만든 모덜리스 속성 시트에 대 한 명령 단추가 없습니다 만듭니다는 [만들기](../mfc/reference/cpropertysheet-class.md#create) 함수입니다. 클래스를 파생 해야 `CPropertySheet` 다른 컨트롤 (예: 미리 보기 창)을 추가 하거나 모덜리스 속성 시트를 표시 하려는 경우가 아니면 합니다. 이 단계 모덜리스 속성 시트에 대 한 필요한 이므로 속성 시트를 닫고를 사용할 수 있는 모든 기본 컨트롤을 포함 하지 않습니다.

1. 속성 시트에 추가할 각 페이지에서 다음을 수행 합니다.

   - 각각에 대해 하나의 개체를 생성 합니다. `CPropertyPage`-이 프로세스의 앞부분에서 만든 클래스를 파생 합니다.

   - 호출 [CPropertySheet::AddPage](../mfc/reference/cpropertysheet-class.md#addpage) 각 페이지에 대 한 합니다.

   일반적으로 만드는 개체를 합니다 `CPropertySheet` 만들어지기를 `CPropertyPage` 이 단계에서는 개체입니다. 그러나 구현 하는 경우는 `CPropertySheet`-파생 클래스를 포함할 수 있습니다를 `CPropertyPage` 개체를 `CPropertySheet` 개체와 호출 `AddPage` 에서 각 페이지에 대 한는 `CPropertySheet`-클래스 생성자를 파생 합니다. `AddPage` 추가 된 `CPropertyPage` 속성 시트의 페이지 목록을 개체 하지만 실제로 해당 페이지의 창을 만들지 않습니다. 따라서 필요한 경우가 아니라면 호출 속성 시트 창의 생성 될 때까지 기다릴 `AddPage`; 호출할 수 있습니다 `AddPage` 속성 시트의 생성자에서.

   기본적으로 속성 시트에 속성 시트의 단일 행에 들어가는 것 보다 더 많은 탭 탭이 여러 행에 스택 됩니다. 호출 스택 사용 하지 않으려면 [CPropertySheet::EnableStackedTabs](../mfc/reference/cpropertysheet-class.md#enablestackedtabs) 매개 변수 설정한 **FALSE**합니다. 호출 해야 `EnableStackedTabs` 속성 시트를 만들 때.

1. 호출 [CPropertySheet::DoModal](../mfc/reference/cpropertysheet-class.md#domodal) 하거나 [만들기](../mfc/reference/cpropertysheet-class.md#create) 속성 시트를 표시 합니다. 호출 `DoModal` 모달 대화 상자로 속성 시트를 만들어야 합니다. 호출 **만들기** 모덜리스 대화 상자로 속성 시트를 만들려고 합니다.

1. 속성 페이지 및 속성 시트의 소유자 간에 데이터를 교환 합니다. 이 문서에 설명 되어 [데이터 교환](../mfc/exchanging-data.md)합니다.

속성 시트를 사용 하는 방법의 예 참조는 MFC 일반 샘플 [PROPDLG](../overview/visual-cpp-samples.md)합니다.

## <a name="see-also"></a>참고자료

[속성 시트](../mfc/property-sheets-mfc.md)
