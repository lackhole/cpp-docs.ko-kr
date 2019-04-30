---
title: 헤더 컨트롤 및 목록 컨트롤
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], with CHeaderCtrl
- CListCtrl class [MFC], header controls
- CHeaderCtrl class [MFC], with CListCtrl
- controls [MFC], header
- header controls [MFC]
- header controls [MFC], list controls used with
ms.assetid: b20194b1-1a6b-4e2f-b890-1b3cca6650bc
ms.openlocfilehash: 934b54de3266138225087d5519af2be51972cf9d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62240077"
---
# <a name="header-control-and-list-control"></a>헤더 컨트롤 및 목록 컨트롤

대부분의 경우에 포함 된 헤더 컨트롤 사용을 [CListCtrl](../mfc/reference/clistctrl-class.md) 하거나 [CListView](../mfc/reference/clistview-class.md) 개체입니다. 그러나 별도 헤더 컨트롤 개체의 열 이나 행을 정렬 된 데이터를 조작 하는 등 바람직하지 경우가 많습니다.는 [CView](../mfc/reference/cview-class.md)-파생 개체입니다. 이러한 경우에 많이 모양과 포함 된 헤더 컨트롤의 기본 동작을 제어를 해야합니다.

Standard를 제공 하는 헤더 컨트롤로 하려는 일반적인 경우 기본 동작을 사용 하는 것이 좋습니다 [CListCtrl](../mfc/reference/clistctrl-class.md) 하거나 [CListView](../mfc/reference/clistview-class.md) 대신 합니다. 사용 하 여 `CListCtrl` 목록 뷰 공용 컨트롤에 포함 된 기본 헤더 컨트롤의 기능을 하려는 경우. 사용 하 여 [CListView](../mfc/reference/clistview-class.md) 뷰 개체에 포함 된 기본 헤더 컨트롤의 기능을 하려는 경우.

> [!NOTE]
>  사용 하 여 목록 뷰 컨트롤을 만들 경우 이러한 컨트롤 기본 제공 헤더 컨트롤에만 포함 된 **LVS_REPORT** 스타일입니다.

대부분의 경우에서 포함된 된 헤더 컨트롤의 모양은 포함 하는 목록 뷰 컨트롤의 스타일을 변경 하 여 수정할 수 있습니다. 또한 부모 목록 뷰 컨트롤의 멤버 함수를 통해 헤더 컨트롤에 대 한 정보를 가져올 수 있습니다. 그러나 완전 하 게 제어 및 액세스, 특성 및 포함 된 헤더 컨트롤의 스타일에 대 한 헤더 컨트롤 개체에 대 한 포인터를 얻을 수 있도록 것이 좋습니다.

포함 된 헤더 컨트롤 개체에서 액세스할 수 있습니다 `CListCtrl` 나 `CListView` 해당 클래스에 대 한 호출을 사용 하 여 `GetHeaderCtrl` 멤버 함수입니다. 다음 코드에서는이 보여 줍니다.

[!code-cpp[NVC_MFCControlLadenDialog#14](../mfc/codesnippet/cpp/header-control-and-list-control_1.cpp)]

## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아볼 항목

- [이미지 목록과 헤더 컨트롤 함께 사용](../mfc/using-image-lists-with-header-controls.md)

## <a name="see-also"></a>참고자료

[CHeaderCtrl 사용](../mfc/using-cheaderctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
