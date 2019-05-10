---
title: 목록 컨트롤 스타일 변경
ms.date: 11/04/2016
helpviewer_keywords:
- styles [MFC], CListCtrl
- CListCtrl class [MFC], styles
- CListCtrl class [MFC], changing styles
ms.assetid: be74a005-0795-417c-9056-f6342aa74b26
ms.openlocfilehash: 2ba9ae81f7b1693be0df3565256a65e4e3561fd3
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344462"
---
# <a name="changing-list-control-styles"></a>목록 컨트롤 스타일 변경

목록 컨트롤의 창 스타일을 변경할 수 있습니다 ([CListCtrl](../mfc/reference/clistctrl-class.md)) 만든 후 언제 든 지 합니다. 창 스타일을 변경 하 여 컨트롤에서 사용 하는 보기의 종류를 변경 합니다. 예를 들어, 탐색기를 에뮬레이션할 제공할 수도 있습니다 메뉴 항목이 나 도구 모음 단추 컨트롤 여러 뷰 사이 전환: 아이콘 보기, 목록 뷰 및 등입니다.

예를 들어 사용자가 메뉴 항목을 선택 하면 호출을 만들 수 [GetWindowLong](/windows/desktop/api/winuser/nf-winuser-getwindowlonga) 컨트롤의 현재 스타일을 검색 한 다음 호출 하 [SetWindowLong](/windows/desktop/api/winuser/nf-winuser-setwindowlonga) 를 스타일 다시 설정 합니다. 자세한 내용은 [를 사용 하 여 목록 뷰 컨트롤](/windows/desktop/Controls/using-list-view-controls) Windows SDK의 합니다.

사용 가능한 스타일에 나와 [만들기](../mfc/reference/clistctrl-class.md#create)합니다. 스타일 **LVS_ICON**를 **LVS_SMALLICON**를 **LVS_LIST**, 및 **LVS_REPORT** 4 목록 컨트롤 뷰를 지정 합니다.

## <a name="extended-styles"></a>확장된 스타일

목록 컨트롤에 대 한 표준 스타일을 외에도 확장된 스타일 이라고 집합도가 있습니다. 이러한 스타일의 경우에서 설명한 [목록 뷰 스타일 확장](/windows/desktop/Controls/extended-list-view-styles) Windows SDK에서 다양 한 목록 컨트롤의 동작을 사용자 지정 하는 유용한 기능을 제공 합니다. (예: 가리키기 선택) 특정 스타일의 동작을 구현 하려면 호출할 [CListCtrl::SetExtendedStyle](../mfc/reference/clistctrl-class.md#setextendedstyle), 필요한 스타일을 전달 합니다. 다음 예제에서는 함수 호출을 보여 줍니다.

[!code-cpp[NVC_MFCControlLadenDialog#22](../mfc/codesnippet/cpp/changing-list-control-styles_1.cpp)]

> [!NOTE]
>  작동 하려면 가리키기 선택도 있어야 **LVS_EX_ONECLICKACTIVATE** 하거나 **LVS_EX_TWOCLICKACTIVATE** 설정 합니다.

## <a name="see-also"></a>참고자료

[CListCtrl 사용](../mfc/using-clistctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
