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
ms.openlocfilehash: c75b560509738e071accdc3dba31dfdea35a14aa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62307759"
---
# <a name="setting-the-day-state-of-a-month-calendar-control"></a>MonthCalendar 컨트롤의 일 상태 설정

Monthcalendar 컨트롤의 특성 중 하나에 컨트롤의 일 상태와 각 요일에 대 한 참조 정보를 저장 하는 기능입니다. 이 정보는 현재 표시 된 달에 대 한 특정 날짜를 강조 하기 위해 사용 됩니다.

> [!NOTE]
>  `CMonthCalCtrl` 개체 일 상태 정보를 표시할 MCS_DAYSTATE 스타일이 있어야 합니다.

일 상태 정보는 32 비트 데이터 형식으로 표현 됩니다 **MONTHDAYSTATE**합니다. 각 비트를 **MONTHDAYSTATE** 비트 필드 (1 ~ 31) 하루에 한 달의 상태를 나타냅니다. 해당 날짜를 표시할 잠시에 있으면 굵게; 그렇지 않은 경우 없음 강조를 사용 하 여 표시 됩니다.

Month calendar 컨트롤의 일 상태 설정에 대 한 두 가지가 있습니다: 호출 하 여 명시적으로 [CMonthCalCtrl::SetDayState](../mfc/reference/cmonthcalctrl-class.md#setdaystate) 하거나 MCN_GETDAYSTATE 알림 메시지를 처리 하 여 합니다.

## <a name="handling-the-mcngetdaystate-notification-message"></a>MCN_GETDAYSTATE 알림 메시지를 처리합니다.

MCN_GETDAYSTATE 메시지 표시 개월 내 날짜를 표시 하는 방법을 확인 하려면 컨트롤에서 전송 됩니다.

> [!NOTE]
>  컨트롤에 표시 된 달에 점에서 이전 및 다음 월을 캐시 하므로 새 달을 선택할 때마다이 알림을 받게 됩니다.

이 메시지를 올바르게 처리 하려면 알아내야 일 상태 정보를 개월 수에 대해 요청 배열을 초기화할 **MONTHDAYSTATE** 적절 한 값과 관련 된 구조체 멤버 초기화를 사용 하 여 구조 새 정보입니다. 다음 절차는 데 필요한 단계를 자세히 보여 주는 것을 전제로 `CMonthCalCtrl` 라는 개체 *m_monthcal* 배열과 **MONTHDAYSTATE** 개체 *mdState*.

#### <a name="to-handle-the-mcngetdaystate-notification-message"></a>MCN_GETDAYSTATE 알림 메시지 처리

1. MCN_GETDAYSTATE 메시지에 대 한 알림 처리기를 추가 속성 창을 사용 하 여 *m_monthcal* 개체 (참조 [함수에 메시지 매핑](../mfc/reference/mapping-messages-to-functions.md)).

1. 처리기의 본문에 다음 코드를 추가 합니다.

   [!code-cpp[NVC_MFCControlLadenDialog#26](../mfc/codesnippet/cpp/setting-the-day-state-of-a-month-calendar-control_1.cpp)]

   로 변환 합니다 *pNMHDR* 적절 한 형식에 대 한 포인터는 다음 몇 달의 정보를 요청 하는 결정 (`pDayState->cDayState`). 매월 현재 비트 필드 (`pDayState->prgDayState[i]`) 0과 다음 필요한 인스턴스화될 날짜 (이 예제의 경우 각 월의 15 일)에 설정 됩니다.

## <a name="see-also"></a>참고자료

[CMonthCalCtrl 사용](../mfc/using-cmonthcalctrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
