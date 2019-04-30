---
title: 목록 컨트롤 소멸시키기
ms.date: 11/04/2016
helpviewer_keywords:
- list controls [MFC], destroying
- CListCtrl class [MFC], destroying controls
ms.assetid: 513ec820-3a02-49d2-b073-a6a7a3fc91b3
ms.openlocfilehash: 963da9e6db2f0fe063dee1ca19ab23f545ed5e76
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392890"
---
# <a name="destroying-the-list-control"></a>목록 컨트롤 소멸시키기

포함 하는 경우에 [CListCtrl](../mfc/reference/clistctrl-class.md) 개체 뷰 또는 대화 상자 클래스의 데이터 멤버와 해당 소유자가 제거 될 때 제거 됩니다. 사용 하는 경우는 [CListView](../mfc/reference/clistview-class.md), 프레임 워크 뷰를 제거 하는 경우 컨트롤을 제거 합니다.

목록 컨트롤 보다는 응용 프로그램에서 저장할 목록 데이터 중 일부에 대해 정렬 하는 경우 해당 할당 취소에 대 한 정렬 해야 합니다. 자세한 내용은 [콜백 항목 및 콜백 마스크](/windows/desktop/Controls/using-list-view-controls) Windows SDK에 있습니다.

또한 모든 이미지 목록 컨트롤을 만들어 list 컨트롤 개체를 사용 하 여 연결을 할당 취소에 대 한 담당 합니다.

## <a name="see-also"></a>참고자료

[CListCtrl 사용](../mfc/using-clistctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
