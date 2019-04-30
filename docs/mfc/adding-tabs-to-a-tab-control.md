---
title: 탭 컨트롤에 탭 추가
ms.date: 11/04/2016
helpviewer_keywords:
- tab controls [MFC], adding tabs
- putting tabs on CTabCtrls [MFC]
- CTabCtrl class [MFC], adding tabs
- tabs [MFC], adding to CTabCtrl class [MFC]
ms.assetid: 7f3d9340-e3c7-4c71-9912-be57534ecc78
ms.openlocfilehash: f769de7bcf3e410cca717c17237d1e49ef8562c9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394769"
---
# <a name="adding-tabs-to-a-tab-control"></a>탭 컨트롤에 탭 추가

탭 컨트롤을 만든 후 ([CTabCtrl](../mfc/reference/ctabctrl-class.md))를 필요한 만큼 많은 탭을 추가 합니다.

### <a name="to-add-a-tab-item"></a>탭 항목을 추가 하려면

1. 준비 된 [TCITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtcitema) 구조입니다.

1. 호출 [CTabCtrl::InsertItem](../mfc/reference/ctabctrl-class.md#insertitem), 구조를 전달 합니다.

1. 추가 탭 항목에 대 한 1 및 2 단계를 반복 합니다.

자세한 내용은 [하는 Tab 컨트롤을 만드는](/windows/desktop/Controls/tab-controls) Windows SDK의 합니다.

## <a name="see-also"></a>참고자료

[CTabCtrl 사용](../mfc/using-ctabctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
