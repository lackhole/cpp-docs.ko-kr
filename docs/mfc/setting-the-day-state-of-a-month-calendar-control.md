---
title: MonthCalendar 컨트롤의 일 상태 설정
ms.date: 11/04/2016
f1_keywords:
- MCN_GETDAYSTATE
helpviewer_keywords:
- CMonthCalCtrl class [MFC], setting day state info
- MCN_GETDAYSTATE notification [MFC]
- month calendar controls [MFC], day state info
ms.assetid: 435d1b11-ec0e-4121-9e25-aaa6af812a3c
ms.openlocfilehash: b8a91c8b0c3bdef9256628b9226c5f3ff154ed7d
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907522"
---
# <a name="setting-the-day-state-of-a-month-calendar-control"></a>MonthCalendar 컨트롤의 일 상태 설정

Month calendar 컨트롤의 특성 중 하나는 해당 월의 각 날짜에 대 한 정보를 컨트롤의 일 상태 라고 하는 정보를 저장 하는 기능입니다. 이 정보는 현재 표시 된 달의 특정 날짜를 강조 하는 데 사용 됩니다.

> [!NOTE]
>  일 상태 정보를 표시 하려면 개체가MCS_DAYSTATE스타일을포함해야합니다.`CMonthCalCtrl`

일 상태 정보는 32 비트 데이터 형식인 **Monthdaystate**로 표시 됩니다. **Monthdaystate** 비트 필드의 각 비트 (1-31)는 한 달의 일 상태를 나타냅니다. 비트가 켜져 있으면 해당 날짜가 굵게 표시 됩니다. 그렇지 않으면 강조 표시 되지 않고 표시 됩니다.

Month calendar 컨트롤의 일 상태를 설정 하는 방법에는 [Cmonthcalctrl:: SetDayState](../mfc/reference/cmonthcalctrl-class.md#setdaystate) 에 대 한 호출을 사용 하거나 MCN_GETDAYSTATE 알림 메시지를 처리 하는 두 가지 방법이 있습니다.

## <a name="handling-the-mcn_getdaystate-notification-message"></a>MCN_GETDAYSTATE 알림 메시지 처리

MCN_GETDAYSTATE 메시지는 표시 되는 월의 일 수를 표시 하는 방법을 결정 하기 위해 컨트롤에서 보냅니다.

> [!NOTE]
>  이 컨트롤은 표시 된 달에 대해 이전 및 다음 달을 캐시 하므로 새 월을 선택할 때마다이 알림을 받게 됩니다.

이 메시지를 올바르게 처리 하려면 상태 정보를 요청 하는 기간 (월)의 수를 결정 하 고, 적절 한 값을 사용 하 여 **monthdaystate** 구조의 배열을 초기화 하 고, 관련 구조 멤버를 새으로 초기화 해야 합니다. 내용을. 필요한 단계를 자세히 설명 하는 다음 `CMonthCalCtrl` 절차에서는 *m_monthcal* 라는 개체와 **monthdaystate** objects *mdstate*의 배열을 가정 합니다.

#### <a name="to-handle-the-mcn_getdaystate-notification-message"></a>MCN_GETDAYSTATE 알림 메시지를 처리 하려면

1. [클래스 마법사](reference/mfc-class-wizard.md)를 사용 하 여 MCN_GETDAYSTATE 메시지에 대 한 알림 처리기를 *m_monthcal* 개체에 추가 합니다 ( [메시지를 함수에 매핑](../mfc/reference/mapping-messages-to-functions.md)참조).

1. 처리기의 본문에 다음 코드를 추가 합니다.

   [!code-cpp[NVC_MFCControlLadenDialog#26](../mfc/codesnippet/cpp/setting-the-day-state-of-a-month-calendar-control_1.cpp)]

   이 예에서는 *Pnmhdr* 포인터를 적절 한 형식으로 변환한 다음 요청 될 개월 수 (`pDayState->cDayState`)를 결정 합니다. 매월 현재 비트 필드 (`pDayState->prgDayState[i]`)가 0으로 초기화 된 다음 필요한 날짜가 설정 됩니다 (이 경우 매월 15 일).

## <a name="see-also"></a>참고자료

[CMonthCalCtrl 사용](../mfc/using-cmonthcalctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
