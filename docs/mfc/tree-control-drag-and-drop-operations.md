---
title: 트리 컨트롤 끌어서 놓기 작업
ms.date: 11/04/2016
helpviewer_keywords:
- CTreeCtrl class [MFC], drag and drop operations
- drag and drop [MFC], CTreeCtrl
- tree controls [MFC], drag and drop operations
ms.assetid: 3cf78b4c-4579-4fe1-9bc9-c5ab876e4af1
ms.openlocfilehash: c7febeec513d8004df2bd1cc42e4e97e027e9f17
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62167701"
---
# <a name="tree-control-drag-and-drop-operations"></a>트리 컨트롤 끌어서 놓기 작업

트리 컨트롤 ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) 항목을 끌기 시작할 때 알림을 보냅니다. 컨트롤에서 보냅니다를 [TVN_BEGINDRAG](/windows/desktop/Controls/tvn-begindrag) 사용자가 왼쪽된 마우스 단추를 사용 하 여 항목을 끌기 시작할 때 알림 메시지와 [TVN_BEGINRDRAG](/windows/desktop/Controls/tvn-beginrdrag) 사용자가 사용 하 여 끌기 시작 하면 알림 메시지 오른쪽 단추입니다. 트리 컨트롤에서 트리 컨트롤 TVS_DISABLEDRAGDROP 스타일을 지정 하 여 이러한 알림을 보내는 방지할 수 있습니다.

호출 하 여 끌기 작업 중에 표시할 이미지를 받아야 합니다 [CreateDragImage](../mfc/reference/ctreectrl-class.md#createdragimage) 멤버 함수입니다. 트리 컨트롤 끌고 있는 항목의 레이블을 기반으로 끌어 놓고 비트맵을 만듭니다. 트리 컨트롤 이미지 목록을 만듭니다 비트맵을 추가 하 고에 대 한 포인터를 반환 합니다 [CImageList](../mfc/reference/cimagelist-class.md) 개체입니다.

실제로 항목을 끄는 코드를 제공 해야 합니다. 이미지 목록 함수 끌기 기능을 사용 하 고 처리 하는 [WM_MOUSEMOVE](/windows/desktop/inputdev/wm-mousemove) 하 고 [WM_LBUTTONUP](/windows/desktop/inputdev/wm-lbuttonup) (또는 [WM_RBUTTONUP](/windows/desktop/inputdev/wm-rbuttonup)) 끌기 작업이 시작 된 후 전송 된 메시지입니다. 이미지 목록 함수에 대 한 자세한 내용은 참조 하세요. [CImageList](../mfc/reference/cimagelist-class.md) 에 *MFC 참조* 및 [이미지 나열](/windows/desktop/controls/image-lists) Windows sdk에서입니다. 트리 컨트롤 항목을 끌어 하는 방법에 대 한 자세한 내용은 참조 하세요. [트리 뷰 항목을 끌어](/windows/desktop/Controls/tree-view-controls), Windows SDK에도 합니다.

트리 컨트롤에서 항목을 끌어서 놓기 작업의 대상이 될 경우 대상 항목에 마우스 커서를 가져갈 때를 알 필요가 있습니다. 호출 하 여 확인할 수 있습니다 합니다 [HitTest](../mfc/reference/ctreectrl-class.md#hittest) 멤버 함수입니다. 지점 및 정수 또는의 주소 지정을 [TVHITTESTINFO](/windows/desktop/api/commctrl/ns-commctrl-tagtvhittestinfo) 마우스 커서의 현재 좌표를 포함 하는 구조입니다. 함수는 반환 될 때 정수 또는 구조 트리 컨트롤을 기준으로 마우스 커서의 위치를 나타내는 플래그를 포함 합니다. 커서가 트리 컨트롤의 항목 위에 있는 경우 구조는 항목 에서도의 핸들을 포함 합니다.

항목을 호출 하 여 끌어서 놓기 작업의 대상을 지정할 수 있습니다 합니다 [SetItem](../mfc/reference/ctreectrl-class.md#setitem) 상태를 설정 하려면 멤버 함수는 `TVIS_DROPHILITED` 값입니다. 이 상태에 있는 항목 끌어서 놓기 대상을 가리키는 데 스타일으로 그려집니다.

## <a name="see-also"></a>참고자료

[CTreeCtrl 사용](../mfc/using-ctreectrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
