---
title: 날짜 및 시간 선택 컨트롤에서 콜백 필드 사용
ms.date: 11/04/2016
f1_keywords:
- DTN_FORMATQUERY
- DTN_FORMAT
helpviewer_keywords:
- DateTimePicker control [MFC], callback fields
- callback fields in CDateTimeCtrl class [MFC]
- CDateTimeCtrl class [MFC], callback fields
- CDateTimeCtrl class [MFC], handling DTN_FORMAT and DTN_FORMATQ
- DTN_FORMATQUERY notification [MFC]
- DTN_FORMAT notification [MFC]
- DateTimePicker control [MFC]
ms.assetid: 404f4ba9-cba7-4718-9faa-bc6b274a723f
ms.openlocfilehash: 874f73df3dda3a720d4346ae3fb0136c662221db
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403583"
---
# <a name="using-callback-fields-in-a-date-and-time-picker-control"></a>날짜 및 시간 선택 컨트롤에서 콜백 필드 사용

날짜 및 시간 선택 필드를 정의 하는 표준 형식 문자 외에도 콜백 필드로 사용자 지정 형식 문자열의 특정 부분을 지정 하 여 출력을 사용자 지정할 수 있습니다. 콜백 필드를 선언 하려면 하나 이상의 "X" 문자 (ASCII 코드가 88) 형식 문자열 본문의 아무 곳 이나 포함 합니다. 예를 들어 다음 문자열 "' 임: 'yy '/' MM '/' dd' (일 'X')'" 컨트롤이 날짜 및 시간 선택기 뒤에 월, 날짜 및 마지막 날짜의 연도와 현재 값을 표시 합니다.

> [!NOTE]
>  수가 X 콜백을 필드 표시 되는 문자의 수를 일치 하지 않습니다.

"X" 문자를 반복 하 여 사용자 지정 문자열의 여러 콜백 필드를 구분할 수 있습니다. 따라서 형식 문자열 "XXddddMMMdd', ' yyyXXX" "XX" 및 "XXX"의 두 고유 콜백 필드를 포함 합니다.

> [!NOTE]
>  콜백 필드 유효한 필드로 처리 됩니다. 따라서 응용 프로그램 되므로 DTN_WMKEYDOWN 알림 메시지를 처리할 준비가 되어 있어야 합니다.

날짜 및 시간 선택 컨트롤에서 콜백 필드를 구현 하는 작업은 세 부분으로 구성 합니다.

- 사용자 지정 서식 문자열을 초기화

- DTN_FORMATQUERY 알림 처리

- DTN_FORMAT 알림 처리

## <a name="initializing-the-custom-format-string"></a>사용자 지정 서식 문자열을 초기화

호출 하 여 사용자 지정 문자열을 초기화 `CDateTimeCtrl::SetFormat`합니다. 자세한 내용은 [날짜 및 시간 선택 컨트롤에서 사용자 지정 서식 문자열 사용 하 여](../mfc/using-custom-format-strings-in-a-date-and-time-picker-control.md)입니다. 사용자 지정 형식 문자열을 설정 하는 일반적인 위치에는 `OnInitDialog` 포함 된 대화 상자 클래스의 함수 또는 `OnInitialUpdate` 포함 된 뷰 클래스의 함수입니다.

## <a name="handling-the-dtnformatquery-notification"></a>DTN_FORMATQUERY 알림 처리

컨트롤 형식 문자열을 구문 분석 하 고 콜백 필드를 발견 하면, 응용 프로그램 DTN_FORMAT 및 DTN_FORMATQUERY 알림 메시지를 보냅니다. 콜백 필드 문자열 알림의 포함 되므로 콜백 필드를 쿼리 하는 것을 확인할 수 있습니다.

현재 콜백 필드에 표시 되는 문자열의 픽셀에서의 최대 허용 크기를 검색할 DTN_FORMATQUERY 알림 메시지가 전송 됩니다.

이 값을 올바르게 계산할 계산 해야 필드에 대 한 대체 문자열의 너비와 높이 컨트롤의 글꼴을 사용 하 여 합니다. 호출 하 여 문자열의 실제 계산 방법은 간단 합니다 [함께 GetTextExtentPoint32](/windows/desktop/api/wingdi/nf-wingdi-gettextextentpoint32a) Win32 함수입니다. 크기가 결정 되 면 응용 프로그램으로 값을 전달 하 고 처리기 함수를 종료 합니다.

다음 예제에서는 콜백 문자열의 크기를 제공 하는 한 가지 방법은 같습니다.

[!code-cpp[NVC_MFCControlLadenDialog#8](../mfc/codesnippet/cpp/using-callback-fields-in-a-date-and-time-picker-control_1.cpp)]

현재 콜백 필드의 크기는 계산 된 필드의 값을 제공 해야 합니다. DTN_FORMAT 알림 메시지에 대 한 처리기에서 수행 됩니다.

## <a name="handling-the-dtnformat-notification"></a>DTN_FORMAT 알림 처리

DTN_FORMAT 알림 대체 되는 문자열을 요청 하는 응용 프로그램에서 사용 됩니다. 다음 예제에서는 가능한 방법 중 하나를 보여 줍니다.

[!code-cpp[NVC_MFCControlLadenDialog#9](../mfc/codesnippet/cpp/using-callback-fields-in-a-date-and-time-picker-control_2.cpp)]

> [!NOTE]
>  에 대 한 포인터를 **NMDATETIMEFORMAT** 적절 한 형식으로 알림 처리기의 첫 번째 매개 변수를 캐스팅 하 여 구조를 찾을 수 있습니다.

## <a name="see-also"></a>참고자료

[CDateTimeCtrl 사용](../mfc/using-cdatetimectrl.md)<br/>
[컨트롤](../mfc/controls-mfc.md)
