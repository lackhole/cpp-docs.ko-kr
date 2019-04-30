---
title: 도구 모음 컨트롤에서 드롭다운 단추 사용
ms.date: 11/04/2016
f1_keywords:
- TBN_DROPDOWN
- TBSTYLE_EX_DRAWDDARROWS
helpviewer_keywords:
- CToolBarCtrl class [MFC], drop-down buttons
- toolbars [MFC], drop-down buttons
- drop-down buttons in toolbars
- TBSTYLE_EX_DRAWDDARROWS
- TBN_DROPDOWN notification [MFC]
ms.assetid: b859f758-d2f6-40d9-9c26-0ff61993b9b2
ms.openlocfilehash: 8d1a13b1921f111d97bb515e7932a0116277f9ed
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411606"
---
# <a name="using-drop-down-buttons-in-a-toolbar-control"></a>도구 모음 컨트롤에서 드롭다운 단추 사용

표준 누름 단추 외에도 도구 모음 드롭다운 단추를 가질 수도 있습니다. 연결 된 아래쪽 화살표의 드롭다운 단추 일반적으로 표시 됩니다.

> [!NOTE]
>  연결 된 아래쪽 화살표는 확장 스타일 TBSTYLE_EX_DRAWDDARROWS 설정 된 경우에 표시 됩니다.

이 화살표 (또는 단추 자체에 없는 화살표 있는 경우) 사용자가 도구 모음 컨트롤의 부모에 TBN_DROPDOWN 알림 메시지가 보내집니다. 그런 다음이 알림 메시지를 처리 하 고 팝업 메뉴를 표시할 수 있습니다. Internet Explorer의 동작과 비슷합니다.

다음 절차에서는 팝업 메뉴를 사용 하 여 드롭다운 도구 모음 단추를 구현 하는 방법을 보여 줍니다.

### <a name="to-implement-a-drop-down-button"></a>드롭다운 단추를 구현 하려면

1. 한 번에 `CToolBarCtrl` 개체가 생성 된, 다음 코드를 사용 하 여 TBSTYLE_EX_DRAWDDARROWS 스타일을 설정 합니다.

   [!code-cpp[NVC_MFCControlLadenDialog#36](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_1.cpp)]

1. 에 대 한 새 TBSTYLE_DROPDOWN 스타일을 설정 ([InsertButton](../mfc/reference/ctoolbarctrl-class.md#insertbutton) 하거나 [AddButtons](../mfc/reference/ctoolbarctrl-class.md#addbuttons)) 또는 기존 ([SetButtonInfo](../mfc/reference/ctoolbarctrl-class.md#setbuttoninfo)) 드롭다운 단추 수 있는 단추입니다. 다음 예제에서는 수정에 기존 단추는 `CToolBarCtrl` 개체:

   [!code-cpp[NVC_MFCControlLadenDialog#37](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_2.cpp)]

1. 도구 모음 개체의 부모 클래스에 TBN_DROPDOWN 처리기를 추가 합니다.

   [!code-cpp[NVC_MFCControlLadenDialog#38](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_3.cpp)]

1. 새 처리기에서 적절 한 팝업 메뉴를 표시 합니다. 다음 코드는 하나의 메서드를 보여 줍니다.

   [!code-cpp[NVC_MFCControlLadenDialog#39](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_4.cpp)]

## <a name="see-also"></a>참고자료

[CToolBarCtrl 사용](../mfc/using-ctoolbarctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
