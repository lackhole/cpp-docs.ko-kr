---
title: 날짜 및 시간 선택 컨트롤에서 사용자 지정 서식 문자열 사용
ms.date: 11/04/2016
helpviewer_keywords:
- CDateTimeCtrl class [MFC], display styles
- DateTimePicker control [MFC], display styles
- DateTimePicker control [MFC]
ms.assetid: 7d577f03-6ca0-4597-9093-50b78f304719
ms.openlocfilehash: 8da5ecaf473d6d3c35ddc1b95ac856ce8c12f163
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411629"
---
# <a name="using-custom-format-strings-in-a-date-and-time-picker-control"></a>날짜 및 시간 선택 컨트롤에서 사용자 지정 서식 문자열 사용

기본적으로 날짜 및 시간 선택 컨트롤 세 가지의 형식 (각 형식에 해당 하는 고유 스타일) 현재 날짜 또는 시간을 표시 하기 위한 형식을 제공 합니다.

- **DTS_LONGDATEFORMAT** "Wednesday, 2000년 1월 3일"와 같은 출력을 생성 하는 긴 형식으로 날짜를 표시 합니다.

- **DTS_SHORTDATEFORMAT** "1/3/00"와 같은 출력을 생성 하는 짧은 형식으로 날짜를 표시 합니다.

- **DTS_TIMEFORMAT** "오후 5시 31분: 42"와 같은 출력을 생성 하는 긴 형식으로 시간을 표시 합니다.

그러나 사용자 지정 서식 문자열을 사용 하 여 날짜 또는 시간의 모양을 사용자 지정할 수 있습니다. 이 사용자 지정 문자열 기존 형식 문자, 비 문자 또는 둘의 조합으로 이루어져 있습니다. 사용자 지정 문자열 빌드되면 호출할 [CDateTimeCtrl::SetFormat](../mfc/reference/cdatetimectrl-class.md#setformat) 사용자 지정 문자열에 전달 합니다. 다음 날짜 및 시간 선택 컨트롤을 사용자 지정 형식 문자열을 사용 하 여 현재 값이 표시 됩니다.

다음 예제 코드 (여기서 *줍* 는 `CDateTimeCtrl` 개체) 한 가지 가능한 해결 방법을 보여 줍니다.

[!code-cpp[NVC_MFCControlLadenDialog#7](../mfc/codesnippet/cpp/using-custom-format-strings-in-a-date-and-time-picker-control_1.cpp)]

사용자 지정 형식 문자열 외에도 날짜 및 시간 선택 컨트롤도 지원 [콜백 필드](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md)합니다.

## <a name="see-also"></a>참고자료

[CDateTimeCtrl 사용](../mfc/using-cdatetimectrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
