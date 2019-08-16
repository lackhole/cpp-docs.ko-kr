---
title: 탭 컨트롤에 탭 추가
ms.date: 11/04/2016
helpviewer_keywords:
- tab controls [MFC], adding tabs
- putting tabs on CTabCtrls [MFC]
- CTabCtrl class [MFC], adding tabs
- tabs [MFC], adding to CTabCtrl class [MFC]
ms.assetid: 7f3d9340-e3c7-4c71-9912-be57534ecc78
ms.openlocfilehash: 8915b3af083ebe318e8527b2f83099bf61e7e3ce
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69509303"
---
# <a name="adding-tabs-to-a-tab-control"></a>탭 컨트롤에 탭 추가

탭 컨트롤 ([Ctabctrl](../mfc/reference/ctabctrl-class.md))을 만든 후 필요한 만큼 탭을 추가 합니다.

### <a name="to-add-a-tab-item"></a>탭 항목을 추가 하려면

1. [Tcitem](/windows/win32/api/commctrl/ns-commctrl-tcitemw) 구조를 준비 합니다.

1. [Ctabctrl:: InsertItem](../mfc/reference/ctabctrl-class.md#insertitem)를 호출 하 여 구조체를 전달 합니다.

1. 추가 탭 항목에 대해 1 단계와 2 단계를 반복 합니다.

자세한 내용은 Windows SDK에서 [탭 컨트롤 만들기](/windows/win32/Controls/tab-controls) 를 참조 하세요.

## <a name="see-also"></a>참고자료

[CTabCtrl 사용](../mfc/using-ctabctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
