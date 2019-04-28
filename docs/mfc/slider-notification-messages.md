---
title: 슬라이더 알림 메시지
ms.date: 11/04/2016
helpviewer_keywords:
- CSliderCtrl class [MFC], notifications
- slider controls [MFC], notification messages
- messages, notification
- notifications [MFC], CSliderCtrl
ms.assetid: b9121104-3889-4a10-92bf-f3723f1af9d0
ms.openlocfilehash: bee2d602512ea1a6af39b0bb218ee7333b399c80
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62307330"
---
# <a name="slider-notification-messages"></a>슬라이더 알림 메시지

슬라이더 컨트롤을 부모 슬라이더 컨트롤의 방향에 따라 하 또는 WM_VSCROLL 메시지를 전송 하 여 사용자 작업의 부모 창을 알립니다. 이러한 메시지를 처리 하려면 부모 창에 하 고 wm_hscroll 및 WM_VSCROLL 메시지에 대 한 처리기를 추가 합니다. [OnHScroll](../mfc/reference/cwnd-class.md#onhscroll) 및 [OnVScroll](../mfc/reference/cwnd-class.md#onvscroll) 슬라이더에 대 한 포인터의 위치, 알림 코드 멤버 함수는 전달 된 [CSliderCtrl](../mfc/reference/csliderctrl-class.md) 개체입니다. 형식의 포인터는 `CScrollBar *` 가리키는 경우에을 `CSliderCtrl` 개체입니다. 슬라이더 컨트롤을 조작 하는 경우에이 포인터를 형식 캐스팅 해야 합니다.

스크롤 막대를 알림 코드를 사용 하는 대신 슬라이더 컨트롤 다양 한 알림 코드를 보냅니다. 슬라이더 컨트롤을 사용자가 키보드를 사용 하 여 슬라이더 컨트롤과 상호 작용할 때에 TB_BOTTOM, TB_LINEDOWN, TB_LINEUP, 및 TB_TOP 알림 코드를 보냅니다. TB_THUMBPOSITION 및 TB_THUMBTRACK 알림 메시지를 사용자가 마우스를 사용 하는 경우에 전송 됩니다. 두 경우 모두 TB_ENDTRACK, TB_PAGEDOWN, 및 TB_PAGEUP 알림 코드를 전송 됩니다.

다음 표는 슬라이더 컨트롤 알림 메시지 및 알림 메시지를 발생 시키는 이벤트 (가상 키 코드 또는 마우스 이벤트). (에서 표준 가상 키 코드 목록은 Winuser.h 참조).

|알림 메시지|알림 메시지를 보내도록를 유발 하는 이벤트|
|--------------------------|-------------------------------------------|
|TB_BOTTOM|VK_END|
|TB_ENDTRACK|WM_KEYUP (사용자는 관련 가상 키 코드를 전송 하는 키를 해제 하는 데 사용)|
|TB_LINEDOWN|VK_RIGHT 또는 VK_DOWN|
|TB_LINEUP|VK_LEFT 또는 VK_UP|
|TB_PAGEDOWN|VK_NEXT (사용자 또는 슬라이더의 오른쪽 아래에 있는 채널을 클릭 하는 데 사용)|
|TB_PAGEUP|VK_PRIOR (사용자 또는 슬라이더의 왼쪽 위에 있는 채널을 클릭 하는 데 사용)|
|TB_THUMBPOSITION|WM_LBUTTONUP 다음 TB_THUMBTRACK 알림 메시지|
|TB_THUMBTRACK|슬라이더를 이동 (사용자가 슬라이더를 끌)|
|TB_TOP|VK_HOME|

## <a name="see-also"></a>참고자료

[CSliderCtrl 사용](../mfc/using-csliderctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
