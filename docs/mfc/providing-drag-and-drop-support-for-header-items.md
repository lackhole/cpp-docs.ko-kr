---
title: 헤더 항목에 대한 끌어서 놓기 지원 제공
ms.date: 11/04/2016
helpviewer_keywords:
- HDS_DRAGDROP style
- header items in header controls
- CHeaderCtrl class [MFC], drag and drop support
- HDN_ notifications [MFC]
ms.assetid: 93a152ec-804f-488f-b260-b3a438d0dc0f
ms.openlocfilehash: f30ad029742a01280abda85cbd1a81104d01d8cd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62297036"
---
# <a name="providing-drag-and-drop-support-for-header-items"></a>헤더 항목에 대한 끌어서 놓기 지원 제공

헤더 항목에 대 한 끌어서 놓기 지원 제공 하려면 HDS_DRAGDROP 스타일을 지정 합니다. 헤더 항목에 대 한 끌어서 놓기 지원이 사용자 헤더 컨트롤의 머리글 항목을 다시 정렬 하는 기능을 제공 합니다. 기본 동작은 머리글 항목을 삭제 하는 경우 끌고 있는 헤더 항목의 반투명 한 끌기 이미지를 및 새 위치를 나타내는 시각적 표시기를 제공 합니다.

로 일반적인 끌어서 놓기 기능을 사용 하 여 기본 끌어서 놓기 동작을 HDN_BEGINDRAG 및 HDN_ENDDRAG 알림을 처리 하 여 확장할 수 있습니다. 재정의 하 여 끌기 이미지의 모양을 사용자 지정할 수도 있습니다는 [CHeaderCtrl::CreateDragImage](../mfc/reference/cheaderctrl-class.md#createdragimage) 멤버 함수입니다.

> [!NOTE]
>  목록 컨트롤에 포함 된 헤더 컨트롤의 끌어서 놓기 지원을 제공 하는 경우의 스타일 확장 섹션을 참조 합니다 [목록 컨트롤 스타일 변경](../mfc/changing-list-control-styles.md) 항목입니다.

## <a name="see-also"></a>참고자료

[CHeaderCtrl 사용](../mfc/using-cheaderctrl.md)
