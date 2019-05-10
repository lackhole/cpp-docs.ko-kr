---
title: 날짜 및 시간 선택 컨트롤의 알림 메시지 처리
ms.date: 11/04/2016
f1_keywords:
- DTN_CLOSEUP
- DTN_DATETIMECHANGE
- DTN_DROPDOWN
helpviewer_keywords:
- DTN_DROPDOWN notification [MFC]
- DTN_DATETIMECHANGE notification [MFC]
- DTN_CLOSEUP notification [MFC]
- DateTimePicker control [MFC], handling notifications
- CDateTimeCtrl class [MFC], handling notifications
- DTN_FORMAT notification [MFC]
- DateTimePicker control [MFC]
ms.assetid: ffbe29ab-ff80-4609-89f7-260b404439c4
ms.openlocfilehash: ce84863744629d30248f94b94448d776177f9841
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64339547"
---
# <a name="processing-notification-messages-in-date-and-time-picker-controls"></a>날짜 및 시간 선택 컨트롤의 알림 메시지 처리

사용자가 날짜 및 시간 선택 컨트롤, 컨트롤 상호 작용 하는 대로 (`CDateTimeCtrl`) 해당 부모 창에 알림 메시지를 전송 합니다. 일반적으로 뷰 또는 대화 상자 개체입니다. 이에 대한 응답으로 작업을 수행하려는 경우 이러한 메시지를 처리합니다. 예를 들어 사용자가 포함 된 month calendar 컨트롤에 표시할 날짜 및 시간 선택 열리면 DTN_DROPDOWN 알림 전송 됩니다.

속성 창을 사용하면 구현하려는 해당 메시지의 부모 클래스에 알림 처리기를 추가할 수 있습니다.

다음 목록에는 날짜 및 시간 선택 컨트롤에서 보낸 다양 한 알림을 설명 합니다.

- DTN_DROPDOWN 표시 되려고 포함된 된 month calendar 컨트롤의 부모에 알립니다. DTS_UPDOWN 스타일이 설정 되지 않은 경우에이 알림이 전송 됩니다. 이 알림에 대 한 자세한 내용은 참조 하세요. [포함 된 Month Calendar 컨트롤 액세스](../mfc/accessing-the-embedded-month-calendar-control.md)합니다.

- DTN_CLOSEUP 알립니다 포함된 된 month calendar 컨트롤의 부모를 닫아야 합니다. DTS_UPDOWN 스타일이 설정 되지 않은 경우에이 알림이 전송 됩니다.

- 컨트롤의 변경 내용이 발생 하는 부모에 게 DTN_DATETIMECHANGE 알리는 합니다.

- DTN_FORMAT 콜백 필드에 표시 하는 데 필요한 텍스트는 부모에 알립니다. 이 알림 및 콜백 필드에 대 한 자세한 내용은 참조 하세요. [날짜 및 시간 선택 컨트롤에서 콜백 필드 사용](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md)합니다.

- DTN_FORMATQUERY 콜백 필드에 표시 되는 문자열의 최대 허용 크기를 제공 하는 부모를 요청 합니다. 이 알림 처리를 컨트롤의 디스플레이 내에서 깜빡임을 항상 올바르게 표시 출력을 제어할 수 있습니다. 이 알림에 대 한 자세한 내용은 참조 하세요. [날짜 및 시간 선택 컨트롤에서 콜백 필드 사용](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md)합니다.

- 사용자가 날짜 및 시간 선택 내용을 편집을 완료 했음을 부모 컨트롤 DTN_USERSTRING에 알립니다. DTS_APPCANPARSE 스타일 설정 된 경우에이 알림이 전송 됩니다.

- 사용자 콜백 필드에 입력 되므로 DTN_WMKEYDOWN 부모를 알립니다. 날짜 및 시간 선택 컨트롤에서 콜백이 아닌 필드에 대 한 지원 같은 키보드 응답을 에뮬레이트 하려면이 알림을 처리 합니다. 이 알림에 대 한 자세한 내용은 참조 하세요. [DTP 컨트롤에서 콜백 필드를 지 원하는](/windows/desktop/Controls/date-and-time-picker-controls) Windows SDK에 있습니다.

## <a name="see-also"></a>참고자료

[CDateTimeCtrl 사용](../mfc/using-cdatetimectrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
