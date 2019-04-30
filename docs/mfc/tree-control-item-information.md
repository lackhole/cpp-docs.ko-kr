---
title: 트리 컨트롤 항목 정보
ms.date: 11/04/2016
helpviewer_keywords:
- tree controls [MFC], item information
- CTreeCtrl class [MFC], item information
ms.assetid: 8dcab855-27de-49e9-95d8-f78ba963ea71
ms.openlocfilehash: e0eb8af4fbbb6f59c0dda75ec3705183ce916350
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407863"
---
# <a name="tree-control-item-information"></a>트리 컨트롤 항목 정보

트리 컨트롤 ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) 컨트롤의 항목에 대 한 정보를 검색 하는 멤버 함수의 수입니다. 합니다 [GetItem](../mfc/reference/ctreectrl-class.md#getitem) 항목과 연결 된 데이터의 일부 또는 전부를 검색 하는 멤버 함수입니다. 이 데이터 항목의 텍스트, 상태, 이미지, 하위 항목 개수 및 32 비트 응용 프로그램 정의 데이터 값을 포함할 수 있습니다. 이기도 한 [SetItem](../mfc/reference/ctreectrl-class.md#setitem) 항목과 연결 된 데이터의 일부 또는 전부를 설정할 수 있는 함수입니다.

합니다 [GetItemState](../mfc/reference/ctreectrl-class.md#getitemstate)를 [GetItemText](../mfc/reference/ctreectrl-class.md#getitemtext)를 [GetItemData](../mfc/reference/ctreectrl-class.md#getitemdata), 및 [GetItemImage](../mfc/reference/ctreectrl-class.md#getitemimage) 의 개별 특성을 검색 하는 멤버 함수는 항목입니다. 이러한 각 함수에는 해당 집합 함수는 항목의 특성을 설정 합니다.

합니다 [GetNextItem](../mfc/reference/ctreectrl-class.md#getnextitem) 멤버 함수는 현재 항목에 지정된 된 관계를 갖는 트리 컨트롤 항목을 검색 합니다. 이 함수는 항목의 부모, 표시 되는 다음 또는 이전 항목, 첫 번째 자식 항목 및 등을 검색할 수 있습니다. 멤버 함수는 트리를 트래버스할 수 있습니다. [GetRootItem](../mfc/reference/ctreectrl-class.md#getrootitem), [GetFirstVisibleItem](../mfc/reference/ctreectrl-class.md#getfirstvisibleitem)합니다 [GetNextVisibleItem](../mfc/reference/ctreectrl-class.md#getnextvisibleitem)를 [GetPrevVisibleItem](../mfc/reference/ctreectrl-class.md#getprevvisibleitem)를 [GetChildItem](../mfc/reference/ctreectrl-class.md#getchilditem), [GetNextSiblingItem](../mfc/reference/ctreectrl-class.md#getnextsiblingitem), [GetPrevSiblingItem](../mfc/reference/ctreectrl-class.md#getprevsiblingitem), [GetParentItem](../mfc/reference/ctreectrl-class.md#getparentitem)하십시오 [GetSelectedItem](../mfc/reference/ctreectrl-class.md#getselecteditem), 및 [ GetDropHilightItem](../mfc/reference/ctreectrl-class.md#getdrophilightitem)합니다.

합니다 [GetItemRect](../mfc/reference/ctreectrl-class.md#getitemrect) 멤버 함수는 트리 컨트롤 항목에 대 한 경계 사각형을 검색 합니다. 합니다 [GetCount](../mfc/reference/ctreectrl-class.md#getcount) 하 고 [GetVisibleCount](../mfc/reference/ctreectrl-class.md#getvisiblecount) 멤버 함수 트리 컨트롤의 항목 수 및 현재 표시 된 트리 컨트롤의 창에서 각각 항목 수를 검색 합니다. 호출 하 여 특정 항목을 표시 되는지 확실히 합니다 [EnsureVisible](../mfc/reference/ctreectrl-class.md#ensurevisible) 멤버 함수입니다.

## <a name="see-also"></a>참고자료

[CTreeCtrl 사용](../mfc/using-ctreectrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
