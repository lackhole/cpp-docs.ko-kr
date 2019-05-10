---
title: 목록 항목 및 이미지 목록
ms.date: 11/04/2016
helpviewer_keywords:
- CImageList class [MFC], and list items
- image lists [MFC], list items
- CListCtrl class [MFC], image lists
- list items [MFC], image lists
ms.assetid: 317d095f-f978-47da-acb6-7bfe7dd3bc69
ms.openlocfilehash: 1679b5c59c6dd55ca47c70ea7c880493304ebf4e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62365275"
---
# <a name="list-items-and-image-lists"></a>목록 항목 및 이미지 목록

목록 컨트롤에는 "item" ([CListCtrl](../mfc/reference/clistctrl-class.md)) 아이콘, 레이블 및 기타 정보 ("하위")으로 구성 됩니다.

목록 컨트롤 항목에 대 한 아이콘 이미지 목록에 포함 됩니다. 하나의 이미지 목록 아이콘 보기에 사용 되는 큰 아이콘을 포함 합니다. 두 번째 (선택 사항) 이미지 목록 컨트롤의 다른 보기에서 사용 하기 위해 같은 아이콘의 더 작은 버전을 포함합니다. 세 번째 선택적 목록을 특정 보기에 있는 작은 아이콘을 앞에 표시에 대 한 확인란 같은 "state" 이미지를 포함합니다. 목록 컨트롤의 개별 헤더 항목에 표시 되는 이미지를 포함 하는 네 번째 선택적 목록은입니다.

> [!NOTE]
>  목록 뷰 컨트롤 LVS_SHAREIMAGELISTS 스타일으로 만들어진 하는 더 이상 사용 될 때 이미지 목록 제거 하는 일을 담당 합니다. 여러 목록 뷰 컨트롤에 동일한 이미지를 할당 하는 경우에이 스타일 목록을 지정 합니다. 그렇지 않은 경우 하나 이상의 컨트롤 같은 이미지 목록을 제거할 시도할 수 있습니다.

목록 항목에 대 한 자세한 내용은 참조 하세요. [목록 뷰에 이미지 나열](/windows/desktop/Controls/using-list-view-controls) 및 [항목과 하위 항목이](/windows/desktop/Controls/using-list-view-controls) Windows sdk에서입니다. 또한 클래스를 참조 하세요 [CImageList](../mfc/reference/cimagelist-class.md) 에 *MFC 참조* 및 [CImageList를 사용 하 여](../mfc/using-cimagelist.md) 이 제품군의 문서.

목록 컨트롤을 만들려면 목록에 새 항목을 삽입할 때 사용 되는 이미지 목록을 제공 해야 합니다. 다음 예제에서는이 절차를 보여 줍니다. 여기서 *줍* 형식의 포인터가 `CImageList` 및 *m_listctrl* 는 `CListCtrl` 데이터 멤버입니다.

[!code-cpp[NVC_MFCControlLadenDialog#19](../mfc/codesnippet/cpp/list-items-and-image-lists_1.cpp)]

그러나 목록 뷰 또는 목록 컨트롤에서 아이콘을 표시 하지 않으려는 경우 이미지 목록 필요는 없습니다.

## <a name="see-also"></a>참고자료

[CListCtrl 사용](../mfc/using-clistctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
