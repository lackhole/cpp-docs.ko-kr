---
title: 목록 컨트롤에서 알림 메시지 처리
ms.date: 11/04/2016
helpviewer_keywords:
- processing notifications [MFC]
- CListCtrl class [MFC], processing notifications
ms.assetid: 1f0e296e-d2a3-48fc-ae38-51d7fb096f51
ms.openlocfilehash: 2a7899c74bfcddcdc8d54f7d9eb894553115ad66
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160187"
---
# <a name="processing-notification-messages-in-list-controls"></a>목록 컨트롤에서 알림 메시지 처리

사용자가 열 머리글을 클릭 아이콘을 끌어, 레이블 및 등과 목록 컨트롤 편집 ([CListCtrl](../mfc/reference/clistctrl-class.md)) 해당 부모 창에 알림 메시지를 보냅니다. 이에 대한 응답으로 작업을 수행하려는 경우 이러한 메시지를 처리합니다. 예를 들어 사용자가 열 머리글을 클릭 하면 Microsoft Outlook 처럼 클릭 한 열의 내용에 따라 항목을 정렬 하는 것이 좋습니다.

뷰 또는 대화 상자 클래스에서 목록 컨트롤에서 WM_NOTIFY 메시지를 처리 합니다. 속성 창을 사용 하 여 만들기는 [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) switch 문 사용 하 여 처리기 함수는 알림 메시지를 처리 하는 기반입니다.

목록 컨트롤을 해당 부모 창에 보낼 수 알림의 목록을 참조 하세요 [목록 뷰 컨트롤 참조](/windows/desktop/Controls/list-view-control-reference) Windows SDK에 있습니다.

## <a name="see-also"></a>참고자료

[CListCtrl 사용](../mfc/using-clistctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
