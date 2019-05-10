---
title: 컨트롤에 항목 추가
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], adding items
ms.assetid: 715994bd-340d-4ad2-9882-411654137830
ms.openlocfilehash: 88e008f06fb669db1c13872b1a58555eeb357d86
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394782"
---
# <a name="adding-items-to-the-control"></a>컨트롤에 항목 추가

목록 컨트롤에 항목을 추가 ([CListCtrl](../mfc/reference/clistctrl-class.md)), 여러 버전 중 하나를 호출 합니다 [InsertItem](../mfc/reference/clistctrl-class.md#insertitem) 있는 정보에 따라 멤버 함수입니다. 한 버전은는 [LV_ITEM](/windows/desktop/api/commctrl/ns-commctrl-taglvitema) 준비 하는 구조입니다. 때문에 `LV_ITEM` 구조에 많은 멤버가 포함 되어, 목록 컨트롤 항목의 특성을 더욱 자세하게 제어할 수 있습니다.

두 가지 중요 한 멤버 (인증과 관련 하 여 보고서 뷰)를 `LV_ITEM` 구조는 합니다 `iItem` 및 `iSubItem` 멤버입니다. 합니다 `iItem` 멤버는 구조를 참조 하는 항목의 0부터 시작 인덱스 및 `iSubItem` 구조 항목에 대 한 정보를 포함 하는 경우 멤버는 1부터 시작 인덱스는 하위 항목의 0입니다. 이러한 두 멤버를 사용 하 여 확인할 있습니다, 항목, 형식 및 목록 컨트롤을 보고서 뷰에 표시 되는 하위 항목 정보 값입니다. 자세한 내용은 [CListCtrl::SetItem](../mfc/reference/clistctrl-class.md#setitem)합니다.

추가 멤버 항목의 텍스트, 아이콘, 상태 및 항목 데이터를 지정합니다. "데이터 항목" 목록 보기 항목을 사용 하 여 연결 된 응용 프로그램 정의 값입니다. 에 대 한 자세한 내용은 합니다 `LV_ITEM` 구조체를 참조 하십시오 [CListCtrl::GetItem](../mfc/reference/clistctrl-class.md#getitem)합니다.

다른 버전의 `InsertItem` 하나 이상의 별도 값, 멤버에 해당 하는 `LV_ITEM` 구조를 지원 하려면 멤버만 초기화할 수 있습니다. 일반적으로 목록 컨트롤에 목록 항목의 저장소를 관리 하지만에 저장할 수 있습니다 정보의 일부 응용 프로그램 대신 "콜백 항목입니다."를 사용 하 여 자세한 내용은 [콜백 항목 및 콜백 마스크](../mfc/callback-items-and-the-callback-mask.md) 이 항목의 및 [콜백 항목 및 콜백 마스크](/windows/desktop/Controls/using-list-view-controls) Windows SDK에 있습니다.

자세한 내용은 [목록 뷰 항목 추가 및 하위 항목](/windows/desktop/Controls/using-list-view-controls)합니다.

## <a name="see-also"></a>참고자료

[CListCtrl 사용](../mfc/using-clistctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
