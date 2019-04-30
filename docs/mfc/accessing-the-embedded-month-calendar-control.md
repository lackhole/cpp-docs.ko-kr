---
title: 포함된 MonthCalendar 컨트롤 액세스
ms.date: 11/04/2016
helpviewer_keywords:
- DateTimePicker control [MFC], accessing month calendar
- CDateTimeCtrl class [MFC], accessing embedded control
- month calendar controls [MFC], embedded in date/time picker
- CMonthCalCtrl class [MFC], changing the font
- month calendar controls [MFC], changing the font
- DateTimePicker control [MFC]
ms.assetid: 355e97ed-cf81-4df3-a2f8-9ddbbde93227
ms.openlocfilehash: dfe6fa220e19deebd86e7c8b7bd25dab60165f73
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392923"
---
# <a name="accessing-the-embedded-month-calendar-control"></a>포함된 MonthCalendar 컨트롤 액세스

포함 된 month calendar 컨트롤 개체에서 액세스할 수 있습니다는 `CDateTimeCtrl` 에 대 한 호출을 사용 하 여 개체를 [GetMonthCalCtrl](../mfc/reference/cdatetimectrl-class.md#getmonthcalctrl) 멤버 함수입니다.

> [!NOTE]
>  포함 된 month calendar 컨트롤의 날짜 및 시간 선택 컨트롤에 없는 경우에 사용 합니다 **DTS_UPDOWN** 스타일 집합을 지정 합니다.

포함 된 컨트롤이 표시 되기 전에 특정 특성을 수정 하려는 경우에 유용 합니다. 이를 위해 처리 합니다 **DTN_DROPDOWN** 알림을 month calendar 컨트롤을 검색 (사용 하 여 [CDateTimeCtrl::GetMonthCalCtrl](../mfc/reference/cdatetimectrl-class.md#getmonthcalctrl))를 수정 하 고 합니다. 아쉽게도 month calendar 컨트롤 지속 되지 않습니다.

즉, 사용자가 달력 컨트롤의 표시를 요청 하는 경우 새 monthcalendar 컨트롤 만들어집니다 (전에 **DTN_DROPDOWN** 알림). 컨트롤이 소멸 될 (후 합니다 **DTN_CLOSEUP** 알림)가 해제 된 경우. 즉, 포함 된 컨트롤이 표시 되기 전에 수정 특성이 포함 된 컨트롤이 닫힐 때 손실 됩니다.

다음 예제에 대 한 처리기를 사용 하 여이 절차에서는 합니다 **DTN_DROPDOWN** 알림. 코드를 호출 하 여 month calendar 컨트롤의 배경색을 변경 [SetMonthCalColor](../mfc/reference/cdatetimectrl-class.md#setmonthcalcolor), 회색입니다. 코드는 다음과 같습니다.

[!code-cpp[NVC_MFCControlLadenDialog#5](../mfc/codesnippet/cpp/accessing-the-embedded-month-calendar-control_1.cpp)]

에서 설명한 대로 포함 된 컨트롤이 닫힐 때 month calendar 컨트롤의 속성을 모든 수정 두 가지 예외가 손실 됩니다. 첫 번째 예외에서 month calendar 컨트롤의 색 이미 설명 했습니다. 두 번째 예외는 month calendar 컨트롤에 사용할 글꼴입니다. 호출 하 여 기본 글꼴을 수정할 수 있습니다 [CDateTimeCtrl::SetMonthCalFont](../mfc/reference/cdatetimectrl-class.md#setmonthcalfont), 기존 글꼴의 핸들을 전달 합니다. 다음 예제에서는 (여기서 `m_dtPicker` 개체인 날짜 및 시간 컨트롤) 가능한 방법 중 하나를 보여 줍니다.

[!code-cpp[NVC_MFCControlLadenDialog#6](../mfc/codesnippet/cpp/accessing-the-embedded-month-calendar-control_2.cpp)]

호출 하 여 글꼴 변경 되 면 `CDateTimeCtrl::SetMonthCalFont`, 새 글꼴에 저장 되 고 다음 번 월별 달력을 표시할 수를 사용 합니다.

## <a name="see-also"></a>참고자료

[CDateTimeCtrl 사용](../mfc/using-cdatetimectrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
