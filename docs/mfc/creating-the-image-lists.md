---
title: 이미지 목록 만들기
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], creating image lists for
- image lists [MFC], creating for CListCtrl
- lists [MFC], image
ms.assetid: c2768515-deba-49e8-a6f3-5be6482afb19
ms.openlocfilehash: 844bfe71f7b03f299f57b0fd4558b7e9eacf67c2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62242239"
---
# <a name="creating-the-image-lists"></a>이미지 목록 만들기

이미지 목록 만들기 동일 무엇을 사용할지 [CListView](../mfc/reference/clistview-class.md) 하거나 [CListCtrl](../mfc/reference/clistctrl-class.md)합니다.

> [!NOTE]
>  수만 필요한 이미지 목록에서 목록 컨트롤이 포함 된 경우는 `LVS_ICON` 스타일입니다.

클래스를 사용 하 여 `CImageList` (큰 아이콘, 작은 아이콘 및 상태)에 하나 이상의 이미지 목록을 만듭니다. 참조 [CImageList](../mfc/reference/cimagelist-class.md)를 살펴보고 [뷰 이미지 목록](/windows/desktop/Controls/using-list-view-controls) Windows SDK의 합니다.

호출 [CListCtrl::SetImageList](../mfc/reference/clistctrl-class.md#setimagelist) 각 이미지 목록에 적절 한에 대 한 포인터를 전달 `CImageList` 개체입니다.

## <a name="see-also"></a>참고자료

[CListCtrl 사용](../mfc/using-clistctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
