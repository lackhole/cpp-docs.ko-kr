---
title: 컨트롤에 항목 추가
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], adding items
ms.assetid: 715994bd-340d-4ad2-9882-411654137830
ms.openlocfilehash: 6c03be6f04746ec2e3146916d72cad637a204187
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69509331"
---
# <a name="adding-items-to-the-control"></a>컨트롤에 항목 추가

목록 컨트롤 ([CListCtrl](../mfc/reference/clistctrl-class.md))에 항목을 추가 하려면 보유 한 정보에 따라 여러 버전의 [InsertItem](../mfc/reference/clistctrl-class.md#insertitem) 멤버 함수 중 하나를 호출 합니다. 한 버전은 준비한 [Lvitem](/windows/win32/api/commctrl/ns-commctrl-lvitemw) 구조를 사용 합니다. 구조에 `LVITEM` 는 많은 멤버가 포함 되어 있으므로 list 컨트롤 항목의 특성을 보다 강력 하 게 제어할 수 있습니다.

구조에 대해 `iSubItem`두개의 중요 한 멤버 (보고서 뷰와 관련)는 및멤버입니다.`iItem` `LVITEM` 멤버 `iItem` 는 구조체에서 참조 하는 항목의 인덱스 (0부터 시작)이 `iSubItem` 고, 멤버는 하위 항목의 1부터 시작 하는 인덱스이 고, 구조체에 항목에 대 한 정보가 포함 되어 있으면 0입니다. 이러한 두 멤버를 사용 하 여 목록 컨트롤이 보고서 뷰에 있을 때 표시 되는 하위 항목 정보의 형식과 값을 항목당 결정할 수 있습니다. 자세한 내용은 [CListCtrl:: SetItem](../mfc/reference/clistctrl-class.md#setitem)를 참조 하세요.

추가 멤버는 항목의 텍스트, 아이콘, 상태 및 항목 데이터를 지정 합니다. "항목 데이터"는 목록 보기 항목과 연결 된 응용 프로그램 정의 값입니다. `LVITEM` 구조체에 대 한 자세한 내용은 [CListCtrl:: GetItem](../mfc/reference/clistctrl-class.md#getitem)를 참조 하세요.

다른 버전의 `InsertItem` 는 `LVITEM` 구조체의 멤버에 해당 하는 하나 이상의 개별 값을 사용 하 여 지원 하려는 멤버만 초기화할 수 있도록 합니다. 일반적으로 목록 컨트롤은 목록 항목의 저장소를 관리 하지만 "콜백 항목"을 사용 하 여 응용 프로그램에 일부 정보를 저장할 수 있습니다. 자세한 내용은이 항목의 콜백 [항목 및 콜백 마스크](../mfc/callback-items-and-the-callback-mask.md) 와 Windows SDK의 콜백 [항목 및 콜백 마스크](/windows/win32/Controls/using-list-view-controls) 를 참조 하세요.

자세한 내용은 [목록-뷰 항목 및 하위 항목 추가](/windows/win32/Controls/using-list-view-controls)를 참조 하세요.

## <a name="see-also"></a>참고자료

[CListCtrl 사용](../mfc/using-clistctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
