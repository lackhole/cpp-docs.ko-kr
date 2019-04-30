---
title: 트리 컨트롤 항목 상태 개요
ms.date: 11/04/2016
helpviewer_keywords:
- states, CTreeCtrl items
- tree controls [MFC], item states overview
- CTreeCtrl class [MFC], item states
ms.assetid: 2db11ae0-0d87-499d-8c1f-5e0dbe9e94c8
ms.openlocfilehash: 57c6714073f4939ffb791a78454e9eac6342309b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392468"
---
# <a name="tree-control-item-states-overview"></a>트리 컨트롤 항목 상태 개요

트리 컨트롤의 각 항목 ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) 현재 상태가 있습니다. 예를 들어, 사용 안 함, 확장 된 등에 항목 선택할 수 있습니다. 대부분의 경우 트리 컨트롤 항목의 상태 항목의 선택과 같은 사용자 동작을 반영 하도록 자동으로 설정 합니다. 사용 하 여 항목의 상태도 설정할 수 있지만 합니다 [SetItemState](../mfc/reference/ctreectrl-class.md#setitemstate) 멤버 함수를 사용 하 여 항목의 현재 상태를 검색 하 고는 [GetItemState](../mfc/reference/ctreectrl-class.md#getitemstate) 멤버 함수입니다. 전체 목록은 항목 상태를 참조 하세요 [트리 뷰 컨트롤 상수](/windows/desktop/Controls/tree-view-control-item-states) Windows SDK에 있습니다.

으로 지정 된 항목의 현재 상태를 *nState* 매개 변수입니다. 트리 컨트롤 항목의 상태 항목을 선택 하거나 항목에 포커스를 설정 하는 등의 사용자 작업을 반영 하도록 변경 될 수 있습니다. 또한 응용 프로그램을 비활성화 하거나 숨길 항목 또는 오버레이 이미지 또는 상태 이미지를 지정 하는 항목의 상태를 변경 될 수 있습니다.

지정 하거나 항목의 상태를 변경 하는 경우는 *nStateMask* 매개 변수는 상태를 설정 하려면 비트를 지정 하며 *nState* 이러한 비트에 대 한 새 값을 포함 하는 매개 변수. 다음 예제에서는 부모 항목의 현재 상태를 변경 하는 예를 들어 (지정 된 *hParentItem*)에 `CTreeCtrl` 개체 (`m_treeCtrl`)를 `TVIS_EXPANDPARTIAL`:

[!code-cpp[NVC_MFCControlLadenDialog#71](../mfc/codesnippet/cpp/tree-control-item-states-overview_1.cpp)]

상태가 변경 되는 또 다른 예로 항목의 오버레이 이미지를 설정 하는 것입니다. 이를 위해 *nStateMask* 포함 해야 합니다는 `TVIS_OVERLAYMASK` 값 및 *nState* 사용 하 여 8 비트를 왼쪽 이동 오버레이 이미지에 1부터 시작 인덱스를 포함 해야 합니다는 [ INDEXTOOVERLAYMASK](/windows/desktop/api/commctrl/nf-commctrl-indextooverlaymask) 매크로입니다. 인덱스 0을 지정 하지 오버레이 이미지 수 있습니다. 오버레이 이미지 해야 추가한 오버레이 이미지의 트리 컨트롤의 목록에 대 한 이전 호출을 [CImageList::SetOverlayImage](../mfc/reference/cimagelist-class.md#setoverlayimage) 함수입니다. 1부터; 추가할 이미지의 인덱스를 지정 하는 함수 이 인덱스가 INDEXTOOVERLAYMASK 매크로 사용 합니다. 트리 컨트롤에는 최대 4 개의 오버레이 이미지 있을 수 있습니다.

항목의 상태 이미지를 설정 하려면 *nStateMask* 포함 해야 합니다는 `TVIS_STATEIMAGEMASK` 값 및 *nState* 사용 하 여 12 비트를 왼쪽으로 이동 하는 상태 이미지의에 1부터 시작 인덱스를 포함 해야 합니다는 [ INDEXTOSTATEIMAGEMASK](/windows/desktop/api/commctrl/nf-commctrl-indextostateimagemask) 매크로입니다. 인덱스 없음 상태 이미지를 지정 합니다. 0이 될 수 있습니다. 이미지 오버레이 및 상태에 대 한 자세한 내용은 참조 하세요. [트리 컨트롤 이미지 목록](../mfc/tree-control-image-lists.md)합니다.

## <a name="see-also"></a>참고자료

[CTreeCtrl 사용](../mfc/using-ctreectrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
