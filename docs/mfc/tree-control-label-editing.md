---
title: 트리 컨트롤 레이블 편집
ms.date: 11/04/2016
helpviewer_keywords:
- editing tree control labels
- CTreeCtrl class [MFC], editing labels
- label editing in CTreeCtrl class [MFC]
- tree controls [MFC], label editing
ms.assetid: 6cde2ac3-43ee-468f-bac2-cf1a228ad32d
ms.openlocfilehash: 446db94ec49859e2213f00d205df57e332c85af2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388152"
---
# <a name="tree-control-label-editing"></a>트리 컨트롤 레이블 편집

사용자를 직접 트리 컨트롤에서 항목의 레이블을 편집할 수 ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) 있는 합니다 **TVS_EDITLABELS** 스타일입니다. 사용자는 포커스가 있는 항목의 레이블을 클릭 하 여 편집을 시작 합니다. 응용 프로그램이 사용 하 여 편집을 시작 합니다 [EditLabel](../mfc/reference/ctreectrl-class.md#editlabel) 멤버 함수입니다. 트리 컨트롤을 편집할 때 알림이 시작 및 취소 또는 완료 된 경우를 보냅니다. 편집이 완료 되 면 책임이 있습니다 항목의 레이블을 업데이트에 대 한 적절 한 경우입니다.

경우 레이블 편집을 시작 하면 트리 컨트롤 보냅니다를 [TVN_BEGINLABELEDIT](/windows/desktop/Controls/tvn-beginlabeledit) 알림 메시지입니다. 이 알림 메시지를 처리 하 여 일부 레이블을 편집할 수를 다른 편집할 수 없도록 합니다. 편집을 사용 하면 0을 반환 하 고 0이 아닌 반환 되지 합니다.

레이블 편집 취소 되었거나 완료할 경우 트리 컨트롤 보냅니다를 [TVN_ENDLABELEDIT](/windows/desktop/Controls/tvn-endlabeledit) 알림 메시지입니다. 합니다 *lParam* 매개 변수는의 주소를 [NMTVDISPINFO](/windows/desktop/api/commctrl/ns-commctrl-tagtvdispinfoa) 구조입니다. 합니다 **항목** 멤버를 [TVITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtvitema) 항목을 식별 하 고 편집된 된 텍스트를 포함 하는 구조입니다. 항목의 레이블을 업데이트를 적절 하 게 하는 경우 아마도 편집된 된 문자열을 확인 한 후 책임이 있습니다. 합니다 *pszText* 소속 `TV_ITEM` 편집이 취소 하는 경우 0입니다.

레이블 편집 중 일반적으로 응답 하는 [TVN_BEGINLABELEDIT](/windows/desktop/Controls/tvn-beginlabeledit) 알림 메시지를 사용 하 여 레이블 편집에 사용 되는 편집 컨트롤에 대 한 포인터를 가져올 수 있습니다 합니다 [GetEditControl](../mfc/reference/ctreectrl-class.md#geteditcontrol) 멤버 함수입니다. 편집 컨트롤을 호출할 수 있습니다 [SetLimitText](../mfc/reference/cedit-class.md#setlimittext) 멤버 함수를 입력할 수 있는 텍스트 또는 서브 클래스를 가로채 고 잘못 된 문자가 삭제 편집 컨트롤의 양을 제한 합니다. 단, 편집 컨트롤만 표시 됩니다 *한 후* **TVN_BEGINLABELEDIT** 보내집니다.

## <a name="see-also"></a>참고자료

[CTreeCtrl 사용](../mfc/using-ctreectrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
