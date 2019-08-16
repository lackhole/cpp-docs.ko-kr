---
title: Rebar 컨트롤에서 알림 메시지 처리
ms.date: 11/04/2016
helpviewer_keywords:
- RBN_ notification messages, description of
- CReBarCtrl class [MFC], notification messages sent by
- RBN_ notification messages [MFC]
- notifications [MFC], CReBarCtrl
ms.assetid: 40f43a60-0c18-4d8d-8fab-213a095624f9
ms.openlocfilehash: 948990c8597c2ccdcec496252c6801c02a78cbf5
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507952"
---
# <a name="processing-notification-messages-in-a-rebar-control"></a>Rebar 컨트롤에서 알림 메시지 처리

Rebar 컨트롤의 부모 클래스에서 처리 하려는 모든 rebar 컨트롤 `OnChildNotify` (`CReBarCtrl`) 알림 메시지에 대 한 switch 문을 사용 하 여 처리기 함수를 만듭니다. 사용자가 rebar 컨트롤 위로 개체를 끌어서 rebar 밴드의 레이아웃을 변경 하 고 rebar 컨트롤에서 밴드를 삭제 하는 등의 방법으로 부모 창으로 알림을 보냅니다.

Rebar 컨트롤 개체에서 다음 알림 메시지를 보낼 수 있습니다.

- RBN_AUTOSIZE 자동으로 크기를 조정할 때 rebar 컨트롤 (RBS_AUTOSIZE 스타일을 사용 하 여 만듦)에서 보냅니다.

- RBN_BEGINDRAG 사용자가 대역 끌기를 시작할 때 rebar 컨트롤에서 보냅니다.

- RBN_CHILDSIZE 밴드의 자식 창 크기가 조정 될 때 rebar 컨트롤에서 보냅니다.

- RBN_DELETEDBAND을 삭제 한 후 rebar 컨트롤에서 보냅니다.

- 밴드가 삭제 될 때 rebar 컨트롤에서 보낸 RBN_DELETINGBAND입니다.

- RBN_ENDDRAG 사용자가 대역 끌기를 중지할 때 rebar 컨트롤에서 보냅니다.

- 컨트롤의 밴드 위로 개체를 끌 때 rebar 컨트롤 (RBS_REGISTERDROP 스타일을 사용 하 여 만듦)에서 RBN_GETOBJECT를 보냅니다.

- RBN_HEIGHTCHANGE 높이가 변경 될 때 rebar 컨트롤에서 보냅니다.

- RBN_LAYOUTCHANGED 사용자가 컨트롤의 밴드 레이아웃을 변경할 때 rebar 컨트롤에서 보냅니다.

이러한 알림에 대 한 자세한 내용은 Windows SDK의 [Rebar 컨트롤 참조](/windows/win32/controls/rebar-control-reference) 를 참조 하세요.

## <a name="see-also"></a>참고자료

[CReBarCtrl 사용](../mfc/using-crebarctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
