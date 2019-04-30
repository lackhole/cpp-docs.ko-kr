---
title: 트리 컨트롤과 통신
ms.date: 11/04/2016
helpviewer_keywords:
- tree controls [MFC], communicating with
- CTreeCtrl class [MFC], calling member functions
- communications, tree controls
- tree controls
ms.assetid: 680ad9ee-b11f-452d-93fa-501ca7d7e069
ms.openlocfilehash: 920608724ebb362b91efdcb3eab50b80acd20474
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62151261"
---
# <a name="communicating-with-a-tree-control"></a>트리 컨트롤과 통신

다른 메서드를 사용 하 여 멤버 함수를 호출 하는 [CTreeCtrl](../mfc/reference/ctreectrl-class.md) 개체를 생성 하는 방식에 따라 개체:

- 형식의 멤버 변수를 사용 하 여 대화 상자에서 트리 컨트롤 경우 `CTreeCtrl` 대화 상자 클래스에서 만든 합니다.

- 트리 컨트롤을 자식 창 인 경우 사용 된 `CTreeCtrl` 개체를 생성 하는 사용 되는 개체 (또는 포인터).

- 사용 중인 경우는 `CTreeView` 개체, 함수를 사용 하 여 [CTreeView::GetTreeCtrl](../mfc/reference/ctreeview-class.md#gettreectrl) 트리 컨트롤에 대 한 참조를 가져오려고 합니다. 이 값을 사용 하 여 다른 참조를 초기화 하거나에 대 한 참조의 주소를 할당할 수 있습니다는 `CTreeCtrl` 포인터입니다.

## <a name="see-also"></a>참고자료

[CTreeCtrl 사용](../mfc/using-ctreectrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
