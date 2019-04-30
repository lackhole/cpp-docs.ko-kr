---
title: MFC의 속성 시트 및 속성 페이지
ms.date: 11/04/2016
helpviewer_keywords:
- property pages [MFC], MFC
- controls [MFC], property sheets
- property sheets, MFC
- tab dialog boxes
ms.assetid: e1bede2b-0285-4b88-a052-0f8a372807a2
ms.openlocfilehash: fa8ee3518ad2b32e0eace77f0961eb86ccde1822
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391376"
---
# <a name="property-sheets-and-property-pages-in-mfc"></a>MFC의 속성 시트 및 속성 페이지

탭 대화 상자 라고도 하는 속성 시트에 속성 페이지를 포함 하는 대화 상자입니다. 각 속성 페이지 대화 상자 템플릿 리소스를 기반으로 하며 컨트롤을 포함 합니다. 최상위 탭을 사용 하 여 페이지에 묶여 있습니다. 탭은 페이지에 이름을 지정 하 고 용도 나타냅니다. 사용자는 컨트롤의 집합을 선택 하는 속성 시트의 탭을 클릭 합니다.

페이지를 사용 하 여 의미 있는 설정 속성 시트에 컨트롤을 그룹화 합니다. 포함 된 속성 시트에는 일반적으로 여러 컨트롤 자체에 있습니다. 이러한 모든 페이지에 적용 됩니다.

속성 시트 클래스에 기반한 [CPropertySheet](../mfc/reference/cpropertysheet-class.md)합니다. 속성 페이지 클래스에 기반한 [CPropertyPage](../mfc/reference/cpropertypage-class.md)합니다.

속성 시트는 일반적으로 보기에서 현재 선택 영역 등의 일부 외부 개체의 속성을 수정 하는 데 사용 되는 대화 상자의 특별 한 합니다. 속성 시트에 세 가지 주요 부분이: 한 번에 하나씩 표시 되 고 사용자가 해당 페이지를 선택 하는 각 페이지의 맨 위에 있는 탭을 포함 하는 대화 상자에서 하나 이상의 속성 페이지. 속성 시트 설정을 변경 하는 옵션의 몇 가지 유사한 그룹 있는 경우에 유용 합니다. 속성 시트를 쉽게 이해할 수 있는 방식으로 정보를 그룹화합니다.

> [!NOTE]
>  속성 시트를 사용 하 여 표시 하려는 경우 `CPropertySheet::DoModal`, 시스템에서 첫째 예외를 생성할 수 있습니다. 시스템 변경 하 려 하기 때문에이 예외가 발생 합니다 [창 스타일](../mfc/reference/styles-used-by-mfc.md#window-styles) 개체 생성 되기 전에 개체의 합니다. 이 예외 및 방지 하거나 처리 하는 방법에 대 한 자세한 내용은 참조 하세요. [CPropertySheet::DoModal](../mfc/reference/cpropertysheet-class.md#domodal)합니다.

## <a name="see-also"></a>참고자료

[속성 시트](../mfc/property-sheets-mfc.md)
