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
ms.openlocfilehash: 97abde8285a3baf307df79fd97d4f9a379c8f58f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507839"
---
# <a name="processing-tab-control-notification-messages"></a>탭 컨트롤 알림 메시지 처리

사용자가 탭 또는 단추를 클릭 하면 탭 컨트롤 ([Ctabctrl](../mfc/reference/ctabctrl-class.md))이 해당 부모 창에 알림 메시지를 보냅니다. 이에 대한 응답으로 작업을 수행하려는 경우 이러한 메시지를 처리합니다. 예를 들어 사용자가 탭을 클릭 하면 페이지를 표시 하기 전에 페이지에서 컨트롤 데이터를 미리 설정 해야 할 수 있습니다.

보기 또는 대화 상자 클래스의 탭 컨트롤에서 WM_NOTIFY 메시지를 처리 합니다. 속성 창를 사용 하 여 처리 되는 알림 메시지에 따라 switch 문을 사용 하 여 [Onchildnotify](../mfc/reference/cwnd-class.md#onchildnotify) 처리기 함수를 만듭니다. 탭 컨트롤이 부모 창에 보낼 수 있는 알림 목록에 대해서는 Windows SDK에서 [탭 컨트롤 참조](/windows/win32/controls/tab-control-reference) 의 **알림** 섹션을 참조 하세요.

## <a name="see-also"></a>참고자료

[CTabCtrl 사용](../mfc/using-ctabctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
