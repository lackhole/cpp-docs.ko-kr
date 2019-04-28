---
title: 트리 컨트롤 스타일
ms.date: 11/04/2016
f1_keywords:
- TVS_SINGLEEXPAND
- TVS_LINESATROOT
- TVS_HASBUTTONS
- TVS_NOTOOLTIPS
- TVS_HASLINES
helpviewer_keywords:
- TVS_LINESATROOT [MFC]
- styles [MFC], CTreeCtrl
- styles [MFC], tree control
- TVS_HASLINES
- TVS_SINGLEEXPAND
- CTreeCtrl class [MFC], styles
- TVS_EDITLABELS [MFC]
- TVS_NOTOOLTIPS [MFC]
- TVS_HASBUTTONS [MFC]
- tree controls [MFC], styles
ms.assetid: f43faebd-a355-479e-888a-bf0673d5e1b4
ms.openlocfilehash: d03961c1c905689af5894897a59262c8f00e73fa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62181525"
---
# <a name="tree-control-styles"></a>트리 컨트롤 스타일

Tree 컨트롤 ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) 스타일 트리 컨트롤의 모양의 측면을 제어 합니다. 트리 컨트롤을 만들 때 초기 스타일을 설정 합니다. 검색 하 고 스타일을 사용 하 여 트리 컨트롤을 만든 후 변경할 수는 [GetWindowLong](/windows/desktop/api/winuser/nf-winuser-getwindowlonga) 하 고 [SetWindowLong](/windows/desktop/api/winuser/nf-winuser-setwindowlonga) Windows 함수를 지정 하 **GWL_STYLE** 에 대 한 합니다 *nIndex* 매개 변수입니다. 스타일의 전체 목록은 참조 하세요 [트리 뷰 컨트롤 창 스타일](/windows/desktop/Controls/tree-view-control-window-styles) Windows SDK에 있습니다.

합니다 **TVS_HASLINES** 스타일 해당 부모 항목에 자식 항목을 연결 하는 선을 그려 트리 컨트롤의 계층의 그래픽 표시를 향상 시킵니다. 이 스타일은 계층의 루트에 있는 항목을 연결 되지 않습니다. 이렇게 하려면 결합 해야 합니다 **TVS_HASLINES** 하 고 **TVS_LINESATROOT** 스타일입니다.

사용자 수 목록을 확장 하거나 축소 부모 항목의 자식 항목의 부모 항목을 두 번 클릭 합니다. 있는 트리 컨트롤을 **TVS_SINGLEEXPAND** 스타일을 사용 하면 확장을 선택 된 항목을 축소 하려면 선택 취소 되는 항목입니다. 선택한 항목을 한 번 클릭 마우스를 사용 하 고 해당 항목을 종결 하는 경우 확장 됩니다. 선택한 항목은 단일-단추를 클릭 하면 열려 있는 경우 축소 됩니다.

있는 트리 컨트롤을 **TVS_HASBUTTONS** 스타일 각 부모 항목의 왼쪽에 단추를 추가 합니다. 확장 또는 부모 항목을 두 번 클릭 하는 대신 자식 항목 축소 단추를 클릭할 수 있습니다. **TVS_HASBUTTONS** 계층의 루트에 있는 항목에 단추를 추가 하지 않습니다. 이렇게 하려면 결합 해야 **TVS_HASLINES**를 **TVS_LINESATROOT**, 및 **TVS_HASBUTTONS**합니다.

합니다 **TVS_EDITLABELS** 스타일을 사용 하면 사용자가 트리 컨트롤 항목의 레이블을 편집할 수 있습니다. 레이블 편집 하는 방법에 대 한 자세한 내용은 참조 하세요. [트리 컨트롤 레이블 편집](../mfc/tree-control-label-editing.md) 이 항목의에서 뒷부분에 있습니다.

합니다 **TVS_NOTOOLTIPS** 스타일 트리 뷰 컨트롤의 자동 도구 팁 기능을 사용 하지 않도록 설정 합니다. 이 기능에는 자동으로 전체 제목 현재 표시 되지 않으면 마우스 커서 아래에 있는 항목의 제목을 포함 하는 도구 설명이 표시 됩니다.

## <a name="see-also"></a>참고자료

[CTreeCtrl 사용](../mfc/using-ctreectrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
