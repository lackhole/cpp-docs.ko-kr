---
title: 도구 설명을 사용하도록 설정
ms.date: 11/04/2016
helpviewer_keywords:
- initializing tool tips [MFC]
- enabling tool tips [MFC]
- tool tips [MFC], initializing
- tool tips [MFC], enabling
ms.assetid: 06b7c889-7722-4ce6-8b88-9efa50fe6369
ms.openlocfilehash: 892ed76ef7e021544505600110cd2569d6078312
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174954"
---
# <a name="enabling-tool-tips"></a>도구 설명을 사용하도록 설정

창의 자식 컨트롤에 대한 도구 설명 지원을 설정할 수 있습니다(예: 폼 뷰 또는 대화 상자의 컨트롤).

### <a name="to-enable-tool-tips-for-the-child-controls-of-a-window"></a>창의 자식 컨트롤에 대해 도구 설명을 사용하도록 설정하려면

1. 도구 설명을 제공하려는 창에 대해 `EnableToolTips`를 호출합니다.

1. 각 컨트롤에 대 한 문자열을 제공 하 [TTN_NEEDTEXT 알림](../mfc/handling-ttn-needtext-notification-for-tool-tips.md) 처리기입니다. 처리기는 자식 컨트롤을 포함하는 창의 메시지 맵에 있습니다(예: 폼 뷰 클래스). 이 처리기는 함수를 호출 하는 컨트롤을 식별 하 고 설정 합니다 **pszText** 도구 설명 컨트롤에서 사용 하는 텍스트를 지정 합니다.

## <a name="see-also"></a>참고자료

[CFrameWnd에서 파생되지 않은 창의 도구 설명](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)
