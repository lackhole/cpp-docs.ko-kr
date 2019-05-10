---
title: 트리 컨트롤 부모 및 자식 항목
ms.date: 11/04/2016
helpviewer_keywords:
- parent items in CTreeCtrl [MFC]
- child items in tree control [MFC]
- CTreeCtrl class [MFC], parent and child items
- tree controls [MFC], parent and child items
ms.assetid: abcea1e4-fe9b-40d9-86dc-1db235f8f103
ms.openlocfilehash: 2961009e3f1b21c3caacec001c53f5e52740dd67
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62181673"
---
# <a name="tree-control-parent-and-child-items"></a>트리 컨트롤 부모 및 자식 항목

트리 컨트롤의 모든 항목 ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) 연결 된 자식 항목 이라고 하는 하위 항목의 목록을 가질 수 있습니다. 하나 이상의 자식 항목이 포함 된 항목을 부모 항목을 라고 합니다. 자식 항목을 해당 부모 항목 아래에 표시 되 고가 부모에 종속 됨을 나타냅니다 들여쓰기 됩니다. 부모가 없는 항목 계층의 최상위에 있고은 루트 항목 이라고 합니다.

특정된 시점에 자식 항목의 부모 항목의 목록 상태 수 중 확장 하거나 축소할 수입니다. 상태를 확장할 때 자식 항목에 부모 항목 아래에 표시 됩니다. 축소 된 경우에 자식 항목에 표시 되지 않습니다. 목록 확장 및 축소 된 상태로 부모 항목을 두 번 클릭할 때 또는 부모 있으면 자동으로 전환 합니다 **TVS_HASBUTTONS** 스타일을 사용자가 부모 항목과 연결 된 단추를 클릭 합니다. 응용 프로그램 확장 하거나 사용 하 여 자식 항목을 축소할 수는 [확장](../mfc/reference/ctreectrl-class.md#expand) 멤버 함수입니다.

호출 하 여 트리 컨트롤에 항목을 추가 합니다 [InsertItem](../mfc/reference/ctreectrl-class.md#insertitem) 멤버 함수입니다. 핸들을 반환 하는이 함수는 **HTREEITEM** 항목을 고유 하 게 식별 하는 형식입니다. 항목을 추가할 때 새 항목의 부모 항목의 핸들을 지정 해야 합니다. 지정 하는 경우 **NULL** 또는 **TVI_ROOT** 값에 대 한 부모 항목 핸들 대신 합니다 [TVINSERTSTRUCT](/windows/desktop/api/commctrl/ns-commctrl-tagtvinsertstructa) 구조 나 *hParent* 매개 변수 항목은 루트 항목으로 추가 됩니다.

트리 컨트롤 보냅니다를 [TVN_ITEMEXPANDING](/windows/desktop/Controls/tvn-itemexpanding) 알림 메시지 되려고 할 때 하위 항목의 부모 항목의 목록을 확장 하거나 축소할 수 있습니다. 알림이 변경 되지 않도록 하거나 자식 항목 목록의 상태에 종속 된 부모 항목의 특성을 설정할 기회를 제공 합니다. 트리 컨트롤 목록의 상태를 변경한 후 전송 된 [TVN_ITEMEXPANDED](/windows/desktop/Controls/tvn-itemexpanded) 알림 메시지입니다.

자식 항목의 목록을 확장 되 면 부모 항목을 기준으로 들여씁니다. 사용 하 여 들여쓰기 정도 설정할 수 있습니다 합니다 [SetIndent](../mfc/reference/ctreectrl-class.md#setindent) 멤버 함수 또는 사용 하 여 현재 크기를 검색 합니다 [GetIndent](../mfc/reference/ctreectrl-class.md#getindent) 멤버 함수입니다.

## <a name="see-also"></a>참고자료

[CTreeCtrl 사용](../mfc/using-ctreectrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
