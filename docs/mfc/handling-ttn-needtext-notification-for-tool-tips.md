---
title: 도구 설명에 대한 TTN_NEEDTEXT 알림 처리
ms.date: 11/04/2016
f1_keywords:
- TTN_NEEDTEXT
helpviewer_keywords:
- TTN_NEEDTEXT message [MFC]
- notifications [MFC], tool tips
- tool tips [MFC], notifications
ms.assetid: d0370a65-21ba-4676-bcc5-8cf851bbb15c
ms.openlocfilehash: 97db98322cd7c0d14e46f54a055bbc646c90d785
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62240391"
---
# <a name="handling-ttnneedtext-notification-for-tool-tips"></a>도구 설명에 대한 TTN_NEEDTEXT 알림 처리

일부로 [도구 설명을 사용 하도록 설정](../mfc/enabling-tool-tips.md)을 처리 하는 **TTN_NEEDTEXT** 소유자 창의 메시지 맵에 다음 항목을 추가 하 여 메시지:

[!code-cpp[NVC_MFCControlLadenDialog#40](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_1.cpp)]

*memberFxn*<br/>
이 단추에 대 한 텍스트가 필요할 때 호출 되는 멤버 함수입니다.

도구 설명의 ID는 항상 0입니다.

클래스 정의에서 처리기 함수를 다음과 같이 선언 합니다.

[!code-cpp[NVC_MFCControlLadenDialog#53](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_2.h)]

기울임꼴로 표시 된 매개 변수는:

*ID*<br/>
알림을 전송 하는 컨트롤의 식별자입니다. 사용되지 않습니다. 컨트롤 id에서 가져온 것은 **NMHDR** 구조입니다.

*pNMHDR*<br/>
에 대 한 포인터를 [NMTTDISPINFO](/windows/desktop/api/commctrl/ns-commctrl-tagnmttdispinfoa) 구조입니다. 이 구조에 대해서도 설명에 대 한 자세한 [The TOOLTIPTEXT 구조체](../mfc/tooltiptext-structure.md)합니다.

*pResult*<br/>
결과 코드에 대 한 포인터를 반환 하기 전에 설정할 수 있습니다. **TTN_NEEDTEXT** 처리기를 무시할 수는 *pResult* 매개 변수입니다.

폼 보기 알림 처리기의 예:

[!code-cpp[NVC_MFCControlLadenDialog#54](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_3.cpp)]

호출 `EnableToolTips` (이 조각에서 가져온 `OnInitDialog`):

[!code-cpp[NVC_MFCControlLadenDialog#55](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_4.cpp)]

## <a name="see-also"></a>참고자료

[CFrameWnd에서 파생되지 않은 창의 도구 설명](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)
