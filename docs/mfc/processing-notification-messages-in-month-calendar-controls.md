---
title: MonthCalendar 컨트롤에서 알림 메시지 처리
ms.date: 11/04/2016
helpviewer_keywords:
- CMonthCalCtrl class [MFC], notifications
- CMonthCalCtrl class [MFC], day states
- month calendar controls [MFC], notification messages
- notifications [MFC], for CMonthCalCtrl
- notifications [MFC], month calendar control
ms.assetid: 607c3e90-0756-493b-9503-ce835a50c7ab
ms.openlocfilehash: fc0bb475a95450c281c92b500083c9502df50931
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346141"
---
# <a name="processing-notification-messages-in-month-calendar-controls"></a>MonthCalendar 컨트롤에서 알림 메시지 처리

사용자와 상호 작용 하면서 month calendar 컨트롤 (날짜를 선택 하거나 다른 달 보는), 컨트롤 (`CMonthCalCtrl`) 해당 부모 창에 알림 메시지를 전송 합니다. 일반적으로 뷰 또는 대화 상자 개체입니다. 이에 대한 응답으로 작업을 수행하려는 경우 이러한 메시지를 처리합니다. 예를 들어 사용자가 보려는 새로운 달을 선택 하면 강조 해야 하는 날짜 집합을 제공할 수 있습니다.

속성 창을 사용하면 구현하려는 해당 메시지의 부모 클래스에 알림 처리기를 추가할 수 있습니다.

다음은 month calendar 컨트롤에서 보낸 다양 한 알림에 설명 합니다.

- MCN_GETDAYSTATE 요청 정보에 대 한 일 굵게 표시 합니다. 이 알림 처리에 대 한 내용은 참조 하세요 [Monthcalendar 컨트롤의 일 상태 설정](../mfc/setting-the-day-state-of-a-month-calendar-control.md)합니다.

- 선택한 날짜 또는 날짜 범위 변경 된 부모에 게 MCN_SELCHANGE 알리는 합니다.

- 부모 개체를 명시적으로 날짜 선택 된 내용이 게 MCN_SELECT 알리는 합니다.

## <a name="see-also"></a>참고자료

[CMonthCalCtrl 사용](../mfc/using-cmonthcalctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
