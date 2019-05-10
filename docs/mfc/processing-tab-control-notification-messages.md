---
title: 탭 컨트롤 알림 메시지 처리
ms.date: 11/04/2016
helpviewer_keywords:
- notifications [MFC], tab controls
- CTabCtrl class [MFC], processing notifications
- notifications [MFC], processing in CTabCtrl
- processing notifications [MFC]
- tab controls [MFC], processing notifications
ms.assetid: 758ccb7a-9e73-48f8-9073-23f7cb09918c
ms.openlocfilehash: 4be9074f3e7d7ce4321402d27fc26283a52436e9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391389"
---
# <a name="processing-tab-control-notification-messages"></a>탭 컨트롤 알림 메시지 처리

사용자 탭 또는 단추, tab 컨트롤을 클릭 합니다 ([CTabCtrl](../mfc/reference/ctabctrl-class.md)) 해당 부모 창에 알림 메시지를 보냅니다. 이에 대한 응답으로 작업을 수행하려는 경우 이러한 메시지를 처리합니다. 예를 들어 사용자가 탭을 클릭 하면 표시 하기 전에 페이지의 컨트롤 데이터를 미리 설정 하는 것이 좋습니다.

클래스 뷰 또는 대화 상자에서에서 탭 컨트롤에서 WM_NOTIFY 메시지를 처리 합니다. 속성 창을 사용 하 여 만들기는 [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) switch 문 사용 하 여 처리기 함수는 알림 메시지를 처리 하는 기반입니다. 탭 컨트롤을 해당 부모 창에 보낼 수 알림의 목록을 참조 하세요. 합니다 **알림을** 부분 [탭 컨트롤 참조](/windows/desktop/controls/tab-control-reference) Windows SDK의 합니다.

## <a name="see-also"></a>참고자료

[CTabCtrl 사용](../mfc/using-ctabctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
