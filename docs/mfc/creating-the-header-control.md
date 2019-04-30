---
title: 헤더 컨트롤 만들기
ms.date: 11/04/2016
helpviewer_keywords:
- CHeaderCtrl class [MFC], creating
- header controls [MFC], creating
ms.assetid: 7864d9d2-4a2c-4622-b58b-7b110a1e28d2
ms.openlocfilehash: 669b13cf566f24bfcd5a29ae41af1cdb90513f73
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62242317"
---
# <a name="creating-the-header-control"></a>헤더 컨트롤 만들기

헤더 컨트롤을 없습니다 대화 상자 편집기에서 직접 사용할 수 있습니다 (헤더 컨트롤을 포함 하는 목록 컨트롤을 추가할 수 있음).

### <a name="to-put-a-header-control-in-a-dialog-box"></a>대화 상자에 헤더 컨트롤을 배치 하려면

1. 수동으로 형식의 멤버 변수를 포함 [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md) 대화 상자 클래스에서입니다.

1. [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)만들고의 스타일을 설정 합니다 `CHeaderCtrl`, 배치 및 표시 합니다.

1. 헤더 컨트롤에 항목을 추가 합니다.

1. 처리 하는 데 필요한 모든 헤더 컨트롤 알림 메시지에 대 한 대화 상자 클래스의 처리기 함수를 매핑할 속성 창 사용 (참조 [함수에 메시지 매핑](../mfc/reference/mapping-messages-to-functions.md)).

### <a name="to-put-a-header-control-in-a-view-not-a-clistview"></a>헤더 컨트롤 (CListView 없습니다) 보기에 삽입할

1. 포함 된 [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md) 뷰 클래스에는 개체입니다.

1. 스타일, 위치 및 보기의 헤더 컨트롤 창을 표시 [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) 멤버 함수입니다.

1. 헤더 컨트롤에 항목을 추가 합니다.

1. 처리 하는 데 필요한 모든 헤더 컨트롤 알림 메시지에 대 한 뷰 클래스의 처리기 함수를 매핑할 속성 창 사용 (참조 [함수에 메시지 매핑](../mfc/reference/mapping-messages-to-functions.md)).

두 경우 모두 포함 된 컨트롤 개체는 뷰 또는 대화 상자 개체를 만들 때 생성 됩니다. 호출 해야 합니다 [CHeaderCtrl::Create](../mfc/reference/cheaderctrl-class.md#create) 컨트롤 창을 만들 수 있습니다. 컨트롤을 배치 하려면 호출 [CHeaderCtrl::Layout](../mfc/reference/cheaderctrl-class.md#layout) 컨트롤의 초기 크기와 위치를 확인 하려면 및 [SetWindowPos](../mfc/reference/cwnd-class.md#setwindowpos) 원하는 위치를 설정 합니다. 에 설명 된 대로 다음 항목을 추가할 [헤더 컨트롤에 항목 추가](../mfc/adding-items-to-the-header-control.md)합니다.

자세한 내용은 [헤더 컨트롤 만들기](/windows/desktop/Controls/header-controls) Windows SDK에 있습니다.

## <a name="see-also"></a>참고자료

[CHeaderCtrl 사용](../mfc/using-cheaderctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
